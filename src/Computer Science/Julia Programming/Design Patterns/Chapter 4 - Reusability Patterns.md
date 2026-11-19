---
dg-publish: true
---
# Reusability as an Architectural Objective in Julia
Software reusability—the capacity to compose new abstractions from existing components without duplicating implementation logic—constitutes a foundational objective in large-scale quantitative systems. Adherence to the *Do Not Repeat Yourself* (`DRY`) principle prevents the proliferation of divergent bug fixes, inconsistent domain invariants, and brittle maintenance surfaces.

In classical object-oriented programming (`OOP`), reusability is frequently pursued through *implementation inheritance*, wherein a subclass inherits both the state fields and the method implementations of a parent class. While conceptually direct, deep inheritance hierarchies couple subtypes to the internal representation of their supertypes, leading to the *fragile base class* problem and rigid single-inheritance bottlenecks. As established in [[Chapter 1 - Modules, Packages, and Data Types]] and [[Chapter 2 - Designing Functions and Interfaces]], Julia separates data representation from behavioral dispatch: concrete types cannot be subtyped, and generic functions operate across open method tables. Consequently, Julia achieves reusability not through implementation inheritance, but through three orthogonal architectural mechanisms:

$$
\begin{gather}
\textbf{Definition: The Three Orthogonal Reusability Axes in Julia} \\[5mm]
\text{1. Delegation (Composition): } \text{A wrapper type embeds an existing concrete} \\[2mm]
\text{instance and selectively forwards method calls to its public interface.} \\[3.5mm]
\text{2. Holy Traits (Behavioral Dispatch): } \text{Types are mapped to singleton trait} \\[2mm]
\text{values, enabling orthogonal polymorphism across unrelated type hierarchies.} \\[3.5mm]
\text{3. Parametric Types (Structural Abstraction): } \text{Type parameters factor out} \\[2mm]
\text{combinatorial variants while preserving static specialization and memory layout.}
\end{gather}
$$

Each pattern addresses a distinct structural axis: delegation reuses concrete implementations across *has-a* boundaries, Holy traits decouple behavioral classification from nominal *is-a* hierarchies, and parametric types collapse families of structurally identical types into a single generic definition. Together with the hygienic metaprogramming facilities introduced in [[Chapter 3 - Macros and Metaprogramming]], these patterns form the core toolkit for building extensible, zero-overhead quantitative libraries in Julia.

---
# The Delegation Pattern: Composition and Selective Method Forwarding
*Delegation* is a structural design pattern in which a composite type wraps an existing *delegate* (or *underlying*) instance via a *has-a* relationship and forwards selected function calls to that wrapped instance. Rather than inheriting fields or internal state, the wrapper relies exclusively on the delegate's published programming interface.

In production quantitative environments, modifying an upstream component directly is often infeasible or undesirable:
*   **Proprietary or Licensed Dependencies:** The upstream component may reside in a vendor-supplied package whose source code is inaccessible or governed by licensing restrictions.
*   **Mission-Critical Stability:** A core ledger or pricing kernel may be shared across multiple teams; altering its concrete layout risks introducing regressions into unrelated systems.
*   **Legacy Coupling:** Modifying heavily tested legacy modules incurs disproportionate verification overhead compared to wrapping them in a clean adapter.

```easy-tikz
title $\text{Selective Delegation vs. Monolithic Class Inheritance}$
show x from -7.0 to 7.0 and y from -3.5 to 3.5
axes on the edges
set show_axis_label = false
size 14 x 8
set displayAlign = "right"
R_oop_base: shade where x >= -6.2 and x <= -1.2 and y >= 1.5 and y <= 2.6, in teal, opacity 0.18, outlined
R_oop_sub: shade where x >= -6.2 and x <= -1.2 and y >= -2.5 and y <= -1.1, in red, opacity 0.18, outlined
R_del_wrap: shade where x >= 1.2 and x <= 6.2 and y >= 1.5 and y <= 2.6, in orange, opacity 0.18, outlined
R_del_core: shade where x >= 1.2 and x <= 6.2 and y >= -2.5 and y <= -1.1, in green, opacity 0.18, outlined
draw an arrow from (-3.7, -1.1) to (-3.7, 1.5), in red, thick
draw an arrow from (3.7, 1.5) to (3.7, -1.1), in orange, thick
write "$\\text{OOP Base Class (All Methods)}$" at (-3.7, 1.85) in teal
write "$\\text{Subclass (Inherits Unwanted API)}$" at (-3.7, -2.0) in red
write "$\\text{Wrapper (Selected API Only)}$" at (3.7, 1.85) in orange
write "$\\text{Account (Core Implementation)}$" at (3.7, -2.0) in green
```

### Primary Banking System (`BankingCore`)
Consider a foundational banking kernel that defines an abstract account hierarchy and a concrete `Account{T<:Real}` structure. In Julia 1.8 and later, `const` field annotations on `mutable struct` definitions enforce *partial mutability*: the account identifier and opening date remain immutable after construction, while the balance may be updated in place. Furthermore, Julia 1.11 introduced the `public` keyword to declare non-exported symbols that form part of the supported programming interface.

```julia
module BankingCore

using Dates

export AbstractAccount, LiquidAccount, Account
export account_number, balance, date_opened
export deposit!, withdraw!, transfer!
public underlying_account

abstract type AbstractAccount end
abstract type LiquidAccount <: AbstractAccount end

# Account{T<:Real} <: LiquidAccount
# Core bank account with immutable identifier and opening date, and mutable balance.
mutable struct Account{T<:Real} <: LiquidAccount
    const account_number::String
    balance::T
    const date_opened::Date

    function Account{T}(account_number::String, balance::Real, date_opened::Date) where {T<:Real}
        isempty(strip(account_number)) && throw(ArgumentError("account_number must be non-empty"))
        converted_balance = convert(T, balance)
        converted_balance >= zero(T) || throw(DomainError(balance, "initial balance must be non-negative"))
        return new{T}(account_number, converted_balance, date_opened)
    end
end

function Account(account_number::String, balance::T, date_opened::Date) where {T<:Real}
    return Account{T}(account_number, balance, date_opened)
end

# Accessors
account_number(a::Account) = a.account_number
balance(a::Account) = a.balance
date_opened(a::Account) = a.date_opened
underlying_account(a::Account) = a

# Mutating operations
function deposit!(a::Account{T}, amount::Real) where {T<:Real}
    amount > zero(amount) || throw(DomainError(amount, "deposit amount must be positive"))
    a.balance += convert(T, amount)
    return a.balance
end

function withdraw!(a::Account{T}, amount::Real) where {T<:Real}
    amount > zero(amount) || throw(DomainError(amount, "withdrawal amount must be positive"))
    amt = convert(T, amount)
    amt <= a.balance || throw(ArgumentError("insufficient funds"))
    a.balance -= amt
    return a.balance
end

function transfer!(from::Account, to::Account, amount::Real)
    from !== to || throw(ArgumentError("cannot transfer to the same account"))
    withdraw!(from, amount)
    deposit!(to, amount)
    return amount
end

function transfer!(from::LiquidAccount, to::LiquidAccount, amount::Real)
    return transfer!(underlying_account(from), underlying_account(to), amount)
end

end # module BankingCore
```

Notice the architectural separation in `BankingCore`:
*   **Invariant Enforcement:** Inner constructors validate non-empty account identifiers and non-negative balances before an instance can exist in memory.
*   **Transaction Ordering:** `transfer!` executes `withdraw!` prior to `deposit!`, ensuring that an insufficient-funds `ArgumentError` aborts the operation before the destination balance is modified.
*   **Generic Cross-Product Dispatch:** Defining `transfer!(from::LiquidAccount, to::LiquidAccount, amount::Real)` via `underlying_account` allows any future `LiquidAccount` wrapper to participate in heterogeneous transfers without duplicating validation logic.

### Composing `SavingsAccount` via Manual Forwarding
To introduce an interest-bearing `SavingsAccount` without modifying `BankingCore`, one wraps an `Account{T}` instance alongside an `interest_rate::R` field.

```julia
module SavingsProducts

using Dates
using ..BankingCore

export SavingsAccount, interest_rate, accrue_daily_interest!

# SavingsAccount{T<:Real, R<:Real} <: LiquidAccount
# Interest-bearing account delegating core ledger operations to an `Account{T}`.
struct SavingsAccount{T<:Real, R<:Real} <: LiquidAccount
    acct::Account{T}
    interest_rate::R

    function SavingsAccount{T, R}(acct::Account{T}, interest_rate::R) where {T<:Real, R<:Real}
        interest_rate >= zero(R) || throw(DomainError(interest_rate, "interest_rate must be non-negative"))
        return new{T, R}(acct, interest_rate)
    end
end

function SavingsAccount(acct::Account{T}, interest_rate::R) where {T<:Real, R<:Real}
    return SavingsAccount{T, R}(acct, interest_rate)
end

function SavingsAccount(account_number::String, balance::T, date_opened::Date, interest_rate::R) where {T<:Real, R<:Real}
    return SavingsAccount{T, R}(Account(account_number, balance, date_opened), interest_rate)
end

# Manual delegation to the underlying Account
BankingCore.underlying_account(sa::SavingsAccount) = sa.acct
BankingCore.account_number(sa::SavingsAccount) = account_number(sa.acct)
BankingCore.balance(sa::SavingsAccount) = balance(sa.acct)
BankingCore.date_opened(sa::SavingsAccount) = date_opened(sa.acct)
BankingCore.deposit!(sa::SavingsAccount, amount::Real) = deposit!(sa.acct, amount)
BankingCore.withdraw!(sa::SavingsAccount, amount::Real) = withdraw!(sa.acct, amount)

# Domain-specific extensions
interest_rate(sa::SavingsAccount) = sa.interest_rate

function accrue_daily_interest!(sa::SavingsAccount; day_count::Real = 365)
    day_count > zero(day_count) || throw(DomainError(day_count, "day_count must be positive"))
    interest = balance(sa) * sa.interest_rate / day_count
    iszero(interest) && return balance(sa)
    return deposit!(sa, interest)
end

end # module SavingsProducts
```

> [!warning]+ Warning: Concrete-Only `transfer!` Pitfall
> If `transfer!` were defined solely for `(from::SavingsAccount, to::SavingsAccount, amount::Real)`, heterogeneous transfers between a `SavingsAccount` and a standard `Account` would fail with a `MethodError`. By subtyping `LiquidAccount` and implementing `BankingCore.underlying_account(sa::SavingsAccount) = sa.acct`, `SavingsAccount` automatically inherits cross-product `transfer!` support from `BankingCore`.

### Reducing Boilerplate via Hygienic Metaprogramming and Modern Packages
Manual forwarding becomes repetitive when a wrapper exposes dozens of methods from its delegate. As detailed in [[Chapter 3 - Macros and Metaprogramming]], hygienic macros can generate these one-line forwarding methods at compile time.

```julia
module DelegationMacros

export @delegate

function _parse_target(target_expr)
    if target_expr isa Expr && target_expr.head === :. && length(target_expr.args) == 2 && target_expr.args[2] isa QuoteNode
        return target_expr.args[1], target_expr.args[2].value
    end
    throw(ArgumentError("@delegate expects WrapperType.field, got $(repr(target_expr))"))
end

function _parse_funcs(funcs_expr)
    if funcs_expr isa Expr && (funcs_expr.head === :tuple || funcs_expr.head === :vect)
        return funcs_expr.args
    elseif funcs_expr isa Symbol || (funcs_expr isa Expr && funcs_expr.head === :.)
        return Any[funcs_expr]
    end
    throw(ArgumentError("@delegate expects a function name or tuple/vector of functions, got $(repr(funcs_expr))"))
end

# @delegate WrapperType.field (f1, f2, ...)
# Generate `@inline` forwarding methods from `WrapperType` to `getfield(x, :field)`.
macro delegate(target_expr, funcs_expr)
    wrapper_type, field_sym = _parse_target(target_expr)
    funcs = _parse_funcs(funcs_expr)
    exprs = Expr[]
    for f in funcs
        push!(exprs, quote
            @inline function $(esc(f))(x::$(esc(wrapper_type)), args...; kwargs...)
                return $(esc(f))(getfield(x, $(QuoteNode(field_sym))), args...; kwargs...)
            end
        end)
    end
    return Expr(:block, exprs...)
end

end # module DelegationMacros
```

Inspecting `@macroexpand` on `@delegate SavingsAccount.acct (balance, deposit!)` reveals that `x`, `args`, and `kwargs` are automatically renamed via `gensym` hygiene, while `$(esc(f))` and `$(esc(wrapper_type))` resolve in the caller's module scope. The `@inline` annotation ensures that the compiler eliminates the wrapper call overhead entirely. Note, however, that single-receiver forwarding macros only dispatch on the first argument `x::WrapperType`; multi-receiver operations such as `transfer!(from, to, amount)` still require `underlying_account` or explicit two-argument methods.

In production codebases, dedicated ecosystem packages provide richer forwarding syntax:

```julia
# Illustrative excerpt (ForwardMethods.jl)
using ForwardMethods

struct SavingsAccountWrapper{T<:Real, R<:Real}
    acct::Account{T}
    interest_rate::R
end

@forward_methods SavingsAccountWrapper field = :acct account_number balance date_opened deposit! withdraw!
```

```julia
# Illustrative excerpt (Delegate.jl)
using Delegate

@delegate_onefield SavingsAccountWrapper acct [account_number, balance, date_opened, deposit!, withdraw!]
```

> [!info]+ Remark: Ecosystem Maintenance of `Lazy.jl`
> Earlier Julia literature frequently recommended `Lazy.@forward` for method delegation. In modern Julia ecosystems, `Lazy.jl` is largely unmaintained and introduces heavy unrelated dependencies. Lightweight, single-purpose packages such as `ForwardMethods.jl` or `Delegate.jl`—or a local 15-line hygienic `@delegate` macro—are preferred.

### Selective Forwarding: `CertificateOfDepositAccount`
A decisive advantage of delegation over OOP implementation inheritance is *selective forwarding*. A certificate of deposit (`CD`) shares account metadata (`account_number`, `balance`, `date_opened`) with `Account`, but must structurally forbid arbitrary withdrawals and transfers prior to maturity.

```julia
module CertificateOfDepositProducts

using Dates
using ..BankingCore
using ..DelegationMacros

export CertificateOfDepositAccount, interest_rate, maturity_date
export is_matured, accrue_term_interest!

# CertificateOfDepositAccount{T<:Real, R<:Real} <: AbstractAccount
# Term-locked account that selectively forwards read-only metadata while forbidding
# arbitrary `withdraw!` and `transfer!` operations.
struct CertificateOfDepositAccount{T<:Real, R<:Real} <: AbstractAccount
    acct::Account{T}
    interest_rate::R
    maturity_date::Date

    function CertificateOfDepositAccount{T, R}(
        acct::Account{T},
        interest_rate::R,
        maturity_date::Date,
    ) where {T<:Real, R<:Real}
        interest_rate >= zero(R) || throw(DomainError(interest_rate, "interest_rate must be non-negative"))
        maturity_date >= date_opened(acct) || throw(ArgumentError("maturity_date cannot precede date_opened"))
        return new{T, R}(acct, interest_rate, maturity_date)
    end
end

function CertificateOfDepositAccount(
    account_number::String,
    balance::T,
    date_opened::Date,
    interest_rate::R,
    maturity_date::Date,
) where {T<:Real, R<:Real}
    return CertificateOfDepositAccount{T, R}(
        Account(account_number, balance, date_opened),
        interest_rate,
        maturity_date,
    )
end

@delegate CertificateOfDepositAccount.acct (
    BankingCore.account_number,
    BankingCore.balance,
    BankingCore.date_opened,
)

interest_rate(cd::CertificateOfDepositAccount) = cd.interest_rate
maturity_date(cd::CertificateOfDepositAccount) = cd.maturity_date
is_matured(cd::CertificateOfDepositAccount, on_date::Date) = on_date >= cd.maturity_date

function accrue_term_interest!(cd::CertificateOfDepositAccount; day_count::Real = 365)
    day_count > zero(day_count) || throw(DomainError(day_count, "day_count must be positive"))
    days = Dates.value(cd.maturity_date - date_opened(cd))
    interest = balance(cd) * cd.interest_rate * (days / day_count)
    iszero(interest) && return balance(cd)
    return deposit!(cd.acct, interest)
end

end # module CertificateOfDepositProducts
```

Because `CertificateOfDepositAccount` subtypes `AbstractAccount` rather than `LiquidAccount` and omits `withdraw!` and `transfer!` from `@delegate`, any attempt to withdraw from a `CD` fails at dispatch time with a `MethodError`. In contrast, monolithic OOP inheritance would force `CertificateOfDepositAccount` to inherit `withdraw!` and override it to throw a runtime exception, violating the *Liskov Substitution Principle* (`LSP`).

### Ecosystem Studies and Architectural Considerations
Delegation appears pervasively across the Julia ecosystem:

```julia
# Illustrative excerpt (OffsetArrays.jl)
struct OffsetArray{T, N, AA<:AbstractArray{T, N}} <: AbstractArray{T, N}
    parent::AA
    offsets::NTuple{N, Int}
end

Base.parent(A::OffsetArray) = A.parent
@inline Base.size(A::OffsetArray) = size(parent(A))
@inline Base.axes(A::OffsetArray) = map((ax, off) -> OffsetAxis(ax, off), axes(parent(A)), A.offsets)
```

> [!info]+ Remark: Evolution of Machine Learning Wrappers
> Older Julia texts illustrated delegation using `ScikitLearn.jl` wrappers. `ScikitLearn.jl` is now effectively unmaintained and has been superseded by `MLJ.jl`, which provides a native, type-stable model interface. When building custom estimator wrappers, all fields must remain strictly typed:
>
> ```julia
> mutable struct FittedEstimator{M}
>     const model::M
>     fitted::Bool
> end
>
> @delegate FittedEstimator.model (predict, transform)
> ```
>
> Using a parametric field `const model::M` instead of an untyped `model` field preserves type inference across delegated `predict` and `transform` calls.

When evaluating delegation, two architectural trade-offs warrant attention:
1.  **Indirection Overhead:** Because `@delegate` methods are marked `@inline` and forward to concrete or parametric fields, LLVM eliminates the wrapper indirection during compilation, yielding zero runtime overhead.
2.  **Utilization Rate:** If a wrapper forwards only a tiny fraction of a large delegate's interface, embedding the entire delegate may introduce unnecessary memory footprint or coupling. Conversely, if a wrapper forwards nearly every method without adding domain invariants, a type alias or direct use of the underlying type may be simpler.

---
# The Holy Traits Pattern: Orthogonal Polymorphism Across Type Hierarchies
While delegation reuses implementations across *has-a* relationships, many quantitative problems require *orthogonal polymorphism*: classifying types along behavioral dimensions that cut across existing nominal *is-a* hierarchies (see [[Chapter 2 - Designing Functions and Interfaces]]). Named after Tim Holy, the *Holy Traits* pattern maps types to singleton *trait* values at compile time and dispatches on those trait values via multiple dispatch.

> [!danger]+ Intuition: Why Holy Traits Incur Zero Runtime Overhead
> Because `LiquidityStyle(::Type{T})` returns a singleton instance (such as `IsLiquid()` or `IsIlliquid()`) whose value is uniquely determined by the compile-time type `T`, Julia's type inference and constant propagation resolve the two-step call `tradable(LiquidityStyle(x), x)` to the exact target method at compile time, eliminating all runtime branching.

$$
\begin{gather}
\textbf{Definition: The Holy Traits Dispatch Pattern} \\[5mm]
\text{1. Trait Hierarchy: } \text{Define an abstract trait type } \mathcal{T} \text{ and concrete} \\[2mm]
\text{singleton subtypes } \tau_1, \tau_2 \dots <: \mathcal{T}. \\[3.5mm]
\text{2. Trait Assignment: } \text{Map each data type } D \text{ to a trait instance via} \\[2mm]
\text{a pure type-level function } \text{trait}(::\text{Type}\{<:D\}) = \tau_i(). \\[3.5mm]
\text{3. Trait-Gated Dispatch: } \text{Route generic functions } f(x) \text{ through a} \\[2mm]
\text{two-argument helper } f(\text{trait}(x), x) \text{ specialized on } \tau_i.
\end{gather}
$$

```easy-tikz
title $\text{Orthogonal Holy Traits: Asset and Literature Converging into LiquidityStyle}$
show x from -7.0 to 7.0 and y from -3.5 to 3.5
axes on the edges
set show_axis_label = false
size 14 x 8
set displayAlign = "right"
R_asset: shade where x >= -6.2 and x <= -1.8 and y >= 1.5 and y <= 2.6, in teal, opacity 0.18, outlined
R_lit: shade where x >= 1.8 and x <= 6.2 and y >= 1.5 and y <= 2.6, in orange, opacity 0.18, outlined
R_trait: shade where x >= -2.5 and x <= 2.5 and y >= -0.3 and y <= 0.7, in green, opacity 0.18, outlined
R_liq: shade where x >= -5.6 and x <= -1.2 and y >= -2.6 and y <= -1.6, in purple, opacity 0.18, outlined
R_illiq: shade where x >= 1.2 and x <= 5.6 and y >= -2.6 and y <= -1.6, in red, opacity 0.18, outlined
draw an arrow from (-4.0, 1.5) to (-1.0, 0.7), in teal, thick
draw an arrow from (4.0, 1.5) to (1.0, 0.7), in orange, thick
draw an arrow from (-1.0, -0.3) to (-3.4, -1.6), in purple, thick
draw an arrow from (1.0, -0.3) to (3.4, -1.6), in red, thick
write "$\\text{Asset Hierarchy}$" at (-4.0, 1.85) in teal
write "$\\text{Literature Hierarchy}$" at (4.0, 1.85) in orange
write "$\\text{LiquidityStyle(::Type)}$" at (0, -0.1) in green
write "$\\text{IsLiquid()}$" at (-3.4, -2.3) in purple
write "$\\text{IsIlliquid()}$" at (3.4, -2.3) in red
```

### Failure Modes of Naive Type Branching
Without traits, developers often resort to `isa` conditional chains or closed `Union` aliases:
*   **Fragile Conditionals:** Writing `if x isa Cash || x isa Investment` inside every pricing or risk function violates the *Open/Closed Principle*. Adding a new liquid asset class requires locating and editing every conditional branch across the codebase.
*   **Closed `Union` Aliases:** Defining `const LiquidInvestments = Union{Investment, Cash}` prevents downstream packages from registering new liquid types without modifying the upstream `Union` definition.
*   **Parametric Invariance Bug:** In Julia, parametric container types are *invariant* (see [[Chapter 1 - Modules, Packages, and Data Types]]). A function signature `total_value(assets::Vector{Asset})` rejects `Vector{Stock}` even when `Stock <: Asset`. The correct covariant signature is `AbstractVector{<:Asset}`.

### Modernized Personal Asset Management (`AssetLiquidity`)
The following self-contained module demonstrates Holy Traits applied to asset liquidity classification, using strictly typed fields, `ISIN` identifiers, and typed `ArgumentError` contracts.

```julia
module AssetLiquidity

export Asset, Property, Investment, Cash
export House, Apartment, FixedIncome, Equity, DerivativeContract
export Residence, Stock, TreasuryBill, Money
export LiquidityStyle, IsLiquid, IsIlliquid
export tradable, market_price

abstract type Asset end
abstract type Property <: Asset end
abstract type Investment <: Asset end
abstract type Cash <: Asset end

abstract type House <: Property end
abstract type Apartment <: Property end

abstract type FixedIncome <: Investment end
abstract type Equity <: Investment end
abstract type DerivativeContract <: Investment end

struct Residence <: House
    location::String
    appraised_value::Float64
end

struct Stock <: Equity
    ticker::String
    name::String
end

struct TreasuryBill <: FixedIncome
    isin::String
    face_value::Float64
end

struct Money{T<:Real} <: Cash
    currency::Symbol
    amount::T
end

# 1. Trait hierarchy
abstract type LiquidityStyle end
struct IsLiquid <: LiquidityStyle end
struct IsIlliquid <: LiquidityStyle end

# 2. Trait assignment (defaulting to IsIlliquid)
LiquidityStyle(::Type) = IsIlliquid()
LiquidityStyle(::Type{<:Cash}) = IsLiquid()
LiquidityStyle(::Type{<:Investment}) = IsLiquid()
LiquidityStyle(x) = LiquidityStyle(typeof(x))

# 3. Trait-gated interface
tradable(x) = tradable(LiquidityStyle(x), x)
tradable(::IsLiquid, x) = true
tradable(::IsIlliquid, x) = false

market_price(x) = market_price(LiquidityStyle(x), x)
market_price(::IsIlliquid, x) = throw(ArgumentError("$(typeof(x)) is illiquid and has no continuous market price"))
market_price(::IsLiquid, x) = throw(ArgumentError("no market_price method implemented for liquid type $(typeof(x))"))
market_price(::IsLiquid, x::Money) = Float64(x.amount)
market_price(::IsLiquid, x::Stock) = 100.0 # Placeholder for live market feed lookup

end # module AssetLiquidity
```

Notice that `LiquidityStyle(::Type) = IsIlliquid()` accepts any `Type`, not merely `Type{<:Asset}`. This enables completely unrelated hierarchies—such as a `Literature` hierarchy with `RareBook <: Literature`—to opt into `LiquidityStyle(::Type{RareBook}) = IsLiquid()` without subtyping `Asset`:

```julia
using .AssetLiquidity

abstract type Literature end

struct RareBook <: Literature
    title::String
    isbn::String
    catalog_price::Float64
end

AssetLiquidity.LiquidityStyle(::Type{RareBook}) = IsLiquid()
AssetLiquidity.market_price(::IsLiquid, b::RareBook) = b.catalog_price
```

### Multi-Valued Traits and Real-World Usage
Traits are not restricted to binary classifications. Julia's `Base` library uses the multi-valued trait `Base.IteratorSize` to classify iterators into `SizeUnknown()`, `HasLength()`, `HasShape{N}()`, and `IsInfinite()`.

```julia
# Base.IteratorSize classifies iterators at compile time
Base.IteratorSize(1:5)                  # HasShape{1}()
Base.IteratorSize(Iterators.repeated(1)) # IsInfinite()

# Attempting to materialize an infinite iterator into a BitArray throws ArgumentError
try
    BitArray(Iterators.repeated(1))
catch err
    err # ArgumentError("infinite-size iterable used in BitArray constructor")
end
```

Similarly, `Base.IteratorEltype` and `Base.IndexStyle` (`IndexLinear()` vs. `IndexCartesian()`) govern generic array and iteration algorithms without constraining concrete type hierarchies.

In the plotting ecosystem, `Makie.jl` employs multi-valued traits via `ConversionTrait` to determine how user-supplied data is transformed into plottable geometries:

```julia
# Illustrative excerpt (Makie.jl)
abstract type ConversionTrait end
struct NoConversion <: ConversionTrait end
struct PointBased <: ConversionTrait end
abstract type GridBased <: ConversionTrait end
struct CellGrid <: GridBased end
struct VertexGrid <: GridBased end

conversion_trait(::Type{<:Heatmap}) = CellGrid()
conversion_trait(::Type{<:Surface}) = VertexGrid()
```

> [!info]+ Remark: Evolution of `Makie.jl` Trait Names
> Earlier literature referenced `AbstractPlotting.jl` and a trait named `SurfaceLike`. `AbstractPlotting.jl` has since been merged directly into `Makie.jl`, and `SurfaceLike` was superseded by the `GridBased` hierarchy (`CellGrid` and `VertexGrid`).

### `SimpleTraits.jl` versus Pure Holy Traits
The `SimpleTraits.jl` package offers macros (`@traitdef`, `@traitimpl`, `@traitfn`) to reduce the boilerplate of writing Holy Traits:

```julia
# Illustrative excerpt (SimpleTraits.jl)
using SimpleTraits

@traitdef IsLiquidTrait{X}
@traitimpl IsLiquidTrait{Cash}
@traitimpl IsLiquidTrait{Investment}

@traitfn tradable_st(x::X) where {X; IsLiquidTrait{X}} = true
@traitfn tradable_st(x::X) where {X; !IsLiquidTrait{X}} = false
```

While `SimpleTraits.jl` is expressive, pure zero-dependency Holy Traits are generally preferred in modern Julia packages because they offer transparent type inference, clear `@methods` introspection, and seamless integration with Julia 1.9+ Package Extensions (where downstream extensions can define trait implementations for third-party types without type piracy). Packages seeking formal interface verification may also pair Holy Traits with `RequiredInterfaces.jl` or `Interfaces.jl`.

---
# The Parametric Type Pattern: Combinatorial Collapse and Type-Level Metadata
As discussed in [[Chapter 1 - Modules, Packages, and Data Types]], parametric types allow a single type definition to represent an entire family of concrete types parameterized by types or compile-time constants (`isbits` values such as integers or tuples of symbols).

$$
\begin{gather}
\textbf{Definition: Parametric Combinatorial Collapse} \\[5mm]
\text{Given } k \text{ independent axes of variation with cardinalities } n_1, \dots, n_k, \\[2mm]
\text{a parametric type } T\{P_1, \dots, P_k\} \text{ collapses } \prod_{i=1}^k n_i \text{ distinct} \\[2mm]
\text{concrete structures into a single generic definition while preserving} \\[2mm]
\text{full static specialization at compile time.}
\end{gather}
$$

```easy-tikz
title $\text{Parametric Type Combinatorial Collapse and UnionAll Subtyping}$
show x from -7.0 to 7.0 and y from -3.5 to 3.5
axes on the edges
set show_axis_label = false
size 14 x 8
set displayAlign = "right"
R_union: shade where x >= -3.4 and x <= 3.4 and y >= 1.5 and y <= 2.6, in teal, opacity 0.18, outlined
R_conc1: shade where x >= -6.4 and x <= -0.6 and y >= -1.8 and y <= -0.4, in orange, opacity 0.18, outlined
R_conc2: shade where x >= 0.6 and x <= 6.4 and y >= -1.8 and y <= -0.4, in green, opacity 0.18, outlined
draw an arrow from (-3.5, -0.4) to (-1.2, 1.5), in orange, thick
draw an arrow from (3.5, -0.4) to (1.2, 1.5), in green, thick
write "$\\text{LabeledArray\\{(:x, :y)\\} (UnionAll)}$" at (0, 1.85) in teal
write "$\\text{LabeledArray\\{(:x, :y), Int, 2, Matrix\\{Int\\}\\}}$" at (-3.5, -1.2) in orange
write "$\\text{LabeledArray\\{(:x, :y), Float64, 2, Matrix\\{Float64\\}\\}}$" at (3.5, -1.2) in green
```

### Multi-Asset Trading Engine (`TradingEngine`)
Consider a trading engine that must represent single-leg trades across equities and equity options, as well as two-leg pair trades. A naive non-parametric design would define separate `StockTrade` and `StockOptionTrade` structs, duplicating `trade_sign` (named to avoid shadowing `Base.sign`) and `payment` logic. Using `@enum` provides compact, type-safe `isbits` enumerations for trade directions and option styles.

```julia
module TradingEngine

export Trade, Investment, Equity, DerivativeContract
export Stock, StockOption, TradeDirection, Long, Short, OptionKind, Call, Put
export SingleTrade, PairTrade, trade_sign, payment

abstract type Trade end
abstract type Investment end
abstract type Equity <: Investment end
abstract type DerivativeContract <: Investment end

# Direction of a trade: Long = 1 (cash outflow on entry) or Short = -1 (cash inflow on entry).
@enum TradeDirection Long = 1 Short = -1

# Option contract style: Call or Put.
@enum OptionKind Call Put

struct Stock <: Equity
    ticker::String
    name::String
end

struct StockOption <: DerivativeContract
    ticker::String
    strike::Float64
    kind::OptionKind
    contract_multiplier::Int
end

function StockOption(ticker::String, strike::Float64, kind::OptionKind; contract_multiplier::Int = 100)
    contract_multiplier > 0 || throw(DomainError(contract_multiplier, "contract_multiplier must be positive"))
    return StockOption(ticker, strike, kind, contract_multiplier)
end

struct SingleTrade{I<:Investment, Q<:Real, P<:Real} <: Trade
    instrument::I
    direction::TradeDirection
    quantity::Q
    price::P

    function SingleTrade{I, Q, P}(
        instrument::I,
        direction::TradeDirection,
        quantity::Q,
        price::P,
    ) where {I<:Investment, Q<:Real, P<:Real}
        quantity > zero(Q) || throw(DomainError(quantity, "quantity must be positive"))
        price >= zero(P) || throw(DomainError(price, "price must be non-negative"))
        return new{I, Q, P}(instrument, direction, quantity, price)
    end
end

function SingleTrade(instrument::I, direction::TradeDirection, quantity::Q, price::P) where {I<:Investment, Q<:Real, P<:Real}
    return SingleTrade{I, Q, P}(instrument, direction, quantity, price)
end

trade_sign(t::SingleTrade) = Int(t.direction)
payment(t::SingleTrade) = -trade_sign(t) * t.quantity * t.price
payment(t::SingleTrade{<:StockOption}) = -trade_sign(t) * t.quantity * t.price * t.instrument.contract_multiplier

struct PairTrade{L1<:SingleTrade, L2<:SingleTrade} <: Trade
    leg1::L1
    leg2::L2
end

payment(pt::PairTrade) = payment(pt.leg1) + payment(pt.leg2)

end # module TradingEngine
```

> [!info]+ Remark: `@enum` versus Singleton Types
> `@enum` values (`Long`, `Short`) are compact `isbits` integers ideal for runtime state fields. When compile-time dispatch on the direction itself is required, singleton types (`struct Long end; struct Short end`) are preferable.

> [!warning]+ Warning: Avoiding Non-Concrete `UnionAll` Fields
> Defining `PairTrade{T}` with fields `leg1::SingleTrade{T}` where `SingleTrade` has additional unfixed parameters (`Q`, `P`) creates a non-concrete `UnionAll` field type, forcing heap allocation and dynamic dispatch. Parameterizing `PairTrade{L1<:SingleTrade, L2<:SingleTrade}` over the full concrete leg types guarantees concrete field layout.

Using `TradingEngine`, a covered call—long 100 shares at \$187.00 and short 1 call contract (multiplier 100) at \$2.50—evaluates to a net cash flow of `-18450.0` (`payment(pt) == -18450.0`, or `18450.0` net capital outlay).

### Ecosystem Case Studies: `ColorTypes.jl` and `NamedDims.jl`
Parametric types underpin high-performance scientific libraries:

```julia
# Illustrative excerpt (ColorTypes.jl)
abstract type Colorant{T, N} end
abstract type Color{T, N} <: Colorant{T, N} end
abstract type AbstractRGB{T} <: Color{T, 3} end

struct RGB{T<:Fractional} <: AbstractRGB{T}
    r::T
    g::T
    b::T
end
```

Similarly, `NamedDims.jl` attaches dimension names to arrays at the type level using a tuple of symbols `L`:

```julia
# Illustrative excerpt (NamedDims.jl)
struct NamedDimsArray{L, T, N, A<:AbstractArray{T, N}} <: AbstractArray{T, N}
    data::A
end
```

The following self-contained `LabeledArray` demonstrates how type-level metadata enables zero-overhead dimension tracking and `UnionAll` subtyping:

```julia
module LabeledArrays

export LabeledArray, dimnames

struct LabeledArray{L, T, N, A<:AbstractArray{T, N}} <: AbstractArray{T, N}
    data::A

    function LabeledArray{L, T, N, A}(data::A) where {L, T, N, A<:AbstractArray{T, N}}
        L isa NTuple{N, Symbol} || throw(ArgumentError("L must be an NTuple{$N, Symbol}"))
        return new{L, T, N, A}(data)
    end
end

function LabeledArray(data::A, names::NTuple{N, Symbol}) where {T, N, A<:AbstractArray{T, N}}
    return LabeledArray{names, T, N, A}(data)
end

Base.size(a::LabeledArray) = size(a.data)
Base.getindex(a::LabeledArray, i::Vararg{Int, N}) where {N} = a.data[i...]
dimnames(::Type{<:LabeledArray{L}}) where {L} = L
dimnames(a::LabeledArray) = dimnames(typeof(a))

end # module LabeledArrays
```

Here, `LabeledArray{(:x, :y), Int, 2, Matrix{Int}} <: LabeledArray{(:x, :y)}` evaluates to `true`, allowing functions to dispatch on dimension names regardless of element type or backing storage.

> [!info]+ Remark: `NamedDims.jl` and `DimensionalData.jl`
> While `NamedDims.jl` provides lightweight type-level dimension names, `DimensionalData.jl` extends this concept with full coordinate axes, lookup indices, and metadata for large-scale scientific and quantitative datasets.

---
# Architectural Synthesis: Composing Reusability Patterns in Modern Julia
Selecting the appropriate reusability pattern depends on the structural relationship between the existing abstraction and the new capability:

| Pattern | Structural Relationship | Primary Mechanism | Ideal Use Case |
| :--- | :--- | :--- | :--- |
| **Delegation** | *Has-a* (Composition) | Wrapper struct + `@inline` forwarding | Adapting or restricting concrete types |
| **Holy Traits** | Orthogonal classification | Singleton traits + two-step dispatch | Cross-hierarchy behavioral polymorphism |
| **Parametric Types** | Structural family | Type parameters + `UnionAll` subtyping | Collapsing combinatorial type variants |

In modern Julia architectures, these three patterns compose naturally: a parametric wrapper type can delegate core storage operations to an underlying `AbstractArray` while opting into ecosystem-wide Holy Traits via `public` interfaces and Julia 1.9+ Package Extensions.
