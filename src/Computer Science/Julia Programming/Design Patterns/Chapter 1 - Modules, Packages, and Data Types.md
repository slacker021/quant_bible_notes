---
dg-publish: true
---
# Namespaces and Lexical Scoping
The architectural foundation of Julia is built upon its nominal type system and multiple dispatch paradigm. Rather than coupling behaviors to class definitions as in traditional object-oriented systems, Julia decouples data structures from generic functions. The language relies on explicit first-class namespaces termed **modules** to isolate functional components—allowing independent mathematical models, economic risk engines, and custom numerical types to be developed and integrated without symbol collisions.

> [!question]+ Application: Resolving Identifier Ambiguity Across Quantitative Libraries
> Namespace collisions frequently emerge when integrating multiple third-party quantitative finance libraries. For instance, both an equity portfolio library and a credit risk engine may export an identifier designated as `duration`. Module prefixes resolve this lexical ambiguity by preserving independent bindings in memory:
> 
> ```julia
> using EquityPortfolios
> using CreditRiskEngine
> 
> # Ambiguity resolved via explicit module namespace qualification
> equity_holding_period = EquityPortfolios.duration(equity_asset)
> bond_macaulay_duration = CreditRiskEngine.duration(fixed_income_asset)
> ```
> 
> The qualifying prefix directs the runtime compiler to the precise method table defined within that target module environment.

Entities defined within a module—including abstract types, composite structures, generic functions, and constant parameters—are encapsulated within that module's global scope. Exposing bindings across module boundaries requires navigating the lexical module hierarchy using relative or absolute path resolution.

### Lexical Module Hierarchy and Path Resolution
Julia organizes modules into a hierarchical tree starting from the root environment `Main`. The path resolution rules dictate how symbols and submodule definitions are located across physical and logical boundaries: 
```
       Main (Root Environment)
      /    \
  ModuleA   ModuleB
  /     \
SubA1   SubA2
```

##### Absolute Resolution (No Leading Dots)
When a `using` or `import` statement is executed without leading dots, Julia initiates an absolute top-level lookup:
```julia
using LinearAlgebra
using FinancialInstruments
```
*   **The Resolution Mechanism:** The package loader queries the active project environment (`Project.toml`) and the global package environment search path (`LOAD_PATH`). It searches strictly for top-level registered packages, installed dependencies, or standard library modules.
*   **The Operational Constraint:** Absolute resolution cannot locate a local submodule defined within a project file unless that file has been formally packaged, loaded into `Main`, or added to the active environment path.

##### Relative Resolution: Current Scope (`.`)
A single leading dot initiates a relative search starting from the currently active lexical scope:
```julia
using .ChildModule
```
*   **The Resolution Mechanism:** The compiler searches strictly downward within the namespace of the executing module to locate an inner module or a submodule evaluated into that scope via `include()`.
*   **The Operational Use Case:** Single-dot syntax is required within a parent orchestrator module (or directly at the interactive `Main` REPL prompt) after a source file containing a submodule has been evaluated into that scope.

##### Relative Resolution: Parent Scope (`..`)
Two leading dots instruct the path resolution algorithm to traverse one level up the module hierarchy:
```julia
module SubModuleA
    using ..SubModuleB
end
```
*   **The Resolution Mechanism:** The compiler exits the current submodule scope, steps upward into the enclosing parent module scope, and searches for the target binding there.
*   **The Operational Use Case:** This pattern allows sibling submodules residing in the same parent container to reference shared types, utility functions, or common numerical constants without exposing them to global scope.

##### Relative Resolution: Grandparent Scope (`...`)
Three leading dots step two levels upward in the module tree:
```julia
module ParentContainer
    module SubModuleA
        module DeepSubModule
            using ...SiblingModule
        end
    end
end
```
*   **The Resolution Mechanism:** The compiler exits `DeepSubModule`, traverses its parent `SubModuleA`, and accesses bindings declared within the grandparent container `ParentContainer`.

### Architectural Pattern: Decoupling File Inclusions from Namespace Resolution
A critical architectural principle in Julia is the strict separation between physical source code ingestion (`include`) and logical namespace resolution (`using` / `import`). 

> [!warning]+ Warning: The Type Fragmentation Trap of Recursive Inclusions
> Calling `include("Instruments.jl")` inside multiple submodules causes the Julia parser to evaluate the source file multiple distinct times. Each evaluation constructs a completely distinct module instance in memory.
> 
> Consequently, structures defined within those modules—such as `ModuleA.Instruments.YieldCurve` and `ModuleB.Instruments.YieldCurve`—are assigned distinct type tags by the runtime compiler. Even if their field names and memory layouts are identical, they cannot interoperate. Passing an instance of one into a method expecting the other triggers an immediate runtime `MethodError`.

To guarantee absolute type uniformity, a single parent orchestrator file evaluates child source files into its own scope exactly once. Sibling submodules then leverage relative double-dot syntax (`using ..Instruments`) to access the unified type definitions.

> [!example]- Example: Institutional Multi-Asset Portfolio and Valuation System
> Below is the component file defining an abstract taxonomy and concrete composite types for financial instruments:
> 
> ```julia
> # File path: src/Instruments.jl
> module Instruments
> 
>     export FinancialInstrument, Equity, FixedIncome, ZeroCouponBond, Stock
> 
>     abstract type FinancialInstrument end
>     abstract type Equity <: FinancialInstrument end
>     abstract type FixedIncome <: FinancialInstrument end
> 
>     struct Stock{T<:Real} <: Equity
>         ticker::String
>         current_price::T
>         beta::T
>     end
> 
>     struct ZeroCouponBond{T<:Real} <: FixedIncome
>         cusip::String
>         face_value::T
>         maturity_years::T
>     end
> 
> end # module Instruments
> ```
> 
> Below is the sibling source file defining valuation and risk routines operating across the instrument types:
> 
> ```julia
> # File path: src/ValuationEngine.jl
> module ValuationEngine
> 
>     # Traverse upward into the parent container to access the unified Instruments binding
>     using ..Instruments
> 
>     export present_value, duration
> 
>     """
>         present_value(bond::ZeroCouponBond, discount_rate::Real)
> 
>     Evaluate the continuous-compounding present value of a zero-coupon bond:
>     PV = F * exp(-r * t)
>     """
>     function present_value(bond::ZeroCouponBond{T}, discount_rate::Real)::T where {T<:Real}
>         return bond.face_value * exp(-discount_rate * bond.maturity_years)
>     end
> 
>     """
>         present_value(equity::Stock, discount_rate::Real)
> 
>     The present value of an equity asset under current market pricing.
>     """
>     function present_value(equity::Stock{T}, discount_rate::Real)::T where {T<:Real}
>         return equity.current_price
>     end
> 
>     """
>         duration(bond::ZeroCouponBond)
> 
>     Evaluate the Macaulay duration of a zero-coupon bond, which identically equals its maturity.
>     """
>     function duration(bond::ZeroCouponBond{T})::T where {T<:Real}
>         return bond.maturity_years
>     end
> 
> end # module ValuationEngine
> ```
> 
> To integrate these modules cleanly, an orchestrator parent module loads both source files exactly once and re-exports the required API:
> 
> ```julia
> # File path: src/PortfolioSystem.jl
> module PortfolioSystem
> 
>     # Evaluate child source files into PortfolioSystem scope exactly once
>     include("Instruments.jl")
>     include("ValuationEngine.jl")
> 
>     # Reach downward into child scopes to expose bindings
>     using .Instruments
>     using .ValuationEngine
> 
>     # Expose unified interface to downstream callers
>     export Instruments, ValuationEngine
>     export FinancialInstrument, Equity, FixedIncome, Stock, ZeroCouponBond
>     export present_value, duration
> 
> end # module PortfolioSystem
> ```
> 
> An execution script loads the orchestrator into the root `Main` environment and executes valuation algorithms without type fragmentation:
> 
> ```julia
> # File path: main.jl
> include("src/PortfolioSystem.jl")
> using .PortfolioSystem
> 
> # Instantiate concrete assets using floating-point registers
> apple_stock = Stock("AAPL", 225.50, 1.15)
> treasury_bill = ZeroCouponBond("912796ZV8", 1000.0, 0.5)
> treasury_bond = ZeroCouponBond("912828ZG2", 1000.0, 5.0)
> 
> market_risk_free_rate = 0.045
> 
> portfolio = FinancialInstrument[apple_stock, treasury_bill, treasury_bond]
> 
> present_values = Float64[present_value(asset, market_risk_free_rate) for asset in portfolio]
> 
> println("Valuation Results:")
> for (asset, pv) in zip(portfolio, present_values)
>     println("  Asset: ", asset, " => Present Value: \$", round(pv, digits=2))
> end
> ```

---
# Package Architecture and Modern Public API Design
As quantitative systems expand, modules are organized into a standardized directory structure called a **package**. A package is a collection of files managed by Julia's package manager (`Pkg`) featuring an independent environment, reproducible dependencies, and automated test pipelines.

### Automated Package Construction via `PkgTemplates.jl`
Production financial engineering workflows avoid manual directory setup. Instead, developers utilize `PkgTemplates.jl` to generate project scaffolds equipped with continuous integration, semantic licensing, and testing harnesses: 
```julia
using PkgTemplates

template = Template(;
    user = "quant-group",
    authors = ["Quantitative Strategies Division <research@fund.com>"],
    julia = v"1.11",
    plugins = [
        License(; name = "MIT"),
        Git(; manifest = false, ssh = true),
        Tests(; project = true),
    ]
)

template("AlgorithmicPortfolio")
```

The resulting package repository adheres to the canonical Julia layout:
```
AlgorithmicPortfolio/
├── Project.toml
├── src/
│   └── AlgorithmicPortfolio.jl
├── test/
│   └── runtests.jl
└── LICENSE
```

---
# The Public API: Distinguishing `export` and `public`
In early versions of Julia, developers could only mark a symbol as user-facing by exporting it into the global namespace via `export`. Unexported symbols were informally treated as private internal implementation details. 

Beginning in **Julia 1.11**, the language introduced the formal `public` keyword to cleanly differentiate between exported symbols, supported non-exported API symbols, and private internals:

| Classification | Keyword | Behavior on `using ModuleName` | Intended Usage |
| :--- | :--- | :--- | :--- |
| **Exported API** | `export` | Ingested directly into the caller's active namespace. | Core primary methods, mathematical operators, and dominant constructors. |
| **Public API** | `public` | Retained within the module namespace; requires qualification (`Mod.sym`). | Stable, supported interface functions that should not pollute global namespaces. |
| **Private Internals** | *None* | Inaccessible without deep inspection; subject to breaking modifications. | Helper kernels, low-level memory allocations, and internal cache state. |

Programmatic introspection of a symbol's stability classification is verified via `Base.ispublic`:
```julia
Base.ispublic(ModuleName, :symbol_name) # Evaluates to true if marked via public or export
```

The stability classification can also be specified in the module's code: 
```julia
module FixedIncomeAnalytics

    export yield_to_maturity
    public macaulay_duration, modified_duration

    """
        yield_to_maturity(price, par, coupon, maturity)

    Calculate the periodic yield to maturity (YTM) using internal analytical solvers.
    """
    function yield_to_maturity(price::T, par::T, coupon::T, maturity::Real)::Float64 where {T<:Real}
        _validate_positive(price, par)
        return (coupon + (par - price) / maturity) / ((par + price) / 2.0)
    end

    """
        macaulay_duration(price, par, coupon, maturity, ytm)

    Evaluate the Macaulay duration of a coupon-bearing bond.
    """
    function macaulay_duration(price::T, par::T, coupon::T, maturity::Real, ytm::Real)::Float64 where {T<:Real}
        _validate_positive(price, par)
        # Analytical duration formulation
        c_rate = coupon / par
        term_factor = (1.0 + ytm)
        return (term_factor / ytm) - (term_factor + maturity * (c_rate - ytm)) / (c_rate * ((term_factor^maturity) - 1.0) + ytm)
    end

    function modified_duration(price::T, par::T, coupon::T, maturity::Real, ytm::Real)::Float64 where {T<:Real}
        mac_dur = macaulay_duration(price, par, coupon, maturity, ytm)
        return mac_dur / (1.0 + ytm)
    end

    # Internal private validation kernel
    function _validate_positive(values::Real...)
        for v in values
            v > 0 || throw(ArgumentError("input value must be strictly positive"))
        end
    end

end # module FixedIncomeAnalytics
```

Callers importing this module observe a clean separation of interface concerns:
```julia
using .FixedIncomeAnalytics

# Exported symbols execute directly without qualification
ytm = yield_to_maturity(950.0, 1000.0, 50.0, 5.0)

# Public unexported symbols require explicit module qualification
mac_dur = FixedIncomeAnalytics.macaulay_duration(950.0, 1000.0, 50.0, 5.0, ytm)
mod_dur = FixedIncomeAnalytics.modified_duration(950.0, 1000.0, 50.0, 5.0, ytm)
```

---
# Conflict Resolution and Identifier Aliasing
When two disparate packages export identical identifiers, loading both into an environment creates a namespace collision. Julia does not fail at load time; instead, it raises an error upon the first unqualified usage of the ambiguous symbol.

To resolve collisions cleanly, Julia provides local identifier aliasing via the `as` keyword:
```julia
using RiskModels: value_at_risk as parametric_var
using HistoricalSimulation: value_at_risk as hist_var

# Explicitly separated bindings execute without ambiguity
loss_threshold_1 = parametric_var(portfolio, 0.99)
loss_threshold_2 = hist_var(portfolio, 0.99)
```

> [!warning]+ Warning: Method Extension Differences Between `using` and `import`
> The choice between `using` and `import` dictates method table mutability:
> 
> *   `using ModuleName: function_name`: Brings `function_name` into the active scope. Methods cannot be added to this function without explicitly prefixing the call:
>     ```julia
>     function ModuleName.function_name(x::CustomType) ... end
>     ```
> *   `import ModuleName: function_name`: Brings `function_name` into the active scope while granting explicit permission to extend its method table directly:
>     ```julia
>     function function_name(x::CustomType) ... end
>     ```

---
# Dependency Management and Project Environments
Modern quantitative workflows enforce deterministic, reproducible computational environments across research and live execution nodes.

### The Dual Architecture: `Project.toml` and `Manifest.toml`
Package management is governed by two complementary files residing at the root of a project environment:
1.  **`Project.toml`:** Declares high-level project metadata, direct dependencies, and semantic version compatibility constraints (`[compat]`).
2.  **`Manifest.toml`:** An auto-generated, cryptographically locked representation of the complete dependency DAG (Directed Acyclic Graph). It records exact package versions, Git tree hashes, and transitive dependencies.

```TOML
name = "StatisticalArbitrage"
uuid = "a1b2c3d4-e5f6-7a8b-9c0d-1e2f3a4b5c6d"
authors = ["Quantitative Research Group"]
version = "1.0.0"
[deps]
DataFrames = "a93c0a0e-b570-5145-a23b-dc3d89e2b225"
Distributions = "31c24e10-a188-53ff-8764-1c3230a0eb4d"
LinearAlgebra = "37e2e46d-f89d-539d-b4ee-838fcccc9c8e"
[compat]
julia = "1.11"
DataFrames = "1.6"
Distributions = "0.25"
```

### Version-Tagged Manifests
Beginning in Julia 1.11, the runtime recognizes version-specific manifests (e.g., `Manifest-v1.11.toml`). This enhancement allows multi-version continuous integration pipelines and disparate developer workstations to maintain isolated dependency resolution graphs within the exact same Git repository branch.

### The Acyclic Dependency Principle
Julia's compilation model mandates that module dependency topologies form a Directed Acyclic Graph (DAG). If `ModuleA` imports `ModuleB`, `ModuleB` cannot directly or transitively import `ModuleA`: 
```
    Cyclic Dependency (Illegal)
       ┌──────────┐
       ▼          │
  ModuleA ────► ModuleB
  
  
    Acyclic Resolution via Shared Abstraction (Compliant)
       ┌──────────┐
       │ Common   │
       │ Abstract │
       │ Types    │
       └────▲─────┘
            │
     ┌──────┴──────┐
     │             │
  ModuleA       ModuleB
```
Circular references prevent static compilation, invalidate method specialization trees, and induce precompilation deadlocks. When two modules require mutual awareness, the structural solution requires factoring the shared abstract types and protocol definitions into a lightweight third foundation module.

---
# Modern Type Design: Abstract, Concrete, and Union Types
Julia's type system is nominal, dynamic, and expressive. Unlike object-oriented languages where types inherit data fields and methods from parent classes, Julia decouples inheritance entirely from field storage: concrete types cannot subtype other concrete types.

### Abstract Type Taxonomies
Abstract types serve exclusively as structural nodes in the type graph. They cannot be directly instantiated and contain no storage fields. Their primary purpose is to define semantic categories and behavioral contracts that govern multiple dispatch:
```julia
abstract type Asset end
abstract type CashEquivalence <: Asset end
abstract type MarketEquity <: Asset end
abstract type DebtSecurity <: Asset end
abstract type DerivativeContract <: Asset end
```

Subtyping is declared using the `<:` operator. Type relationships are introspected programmatically via `supertype` and `subtypes`:
```julia
using InteractiveUtils

supertype(MarketEquity)  # Returns Asset
subtypes(Asset)          # Returns [CashEquivalence, DebtSecurity, DerivativeContract, MarketEquity]
```

---
# Struct Mutability and Partial Mutability
Concrete composite types are declared with the `struct` keyword and are immutable by default. Once an instance of an immutable struct is constructed, its fields cannot be modified:
```julia
struct LimitOrder{T<:Real}
    order_id::Int64
    ticker::String
    price::T
    volume::Int64
end
```
Because their byte layouts are deterministic and invariant, the Julia compiler can allocate immutable struct instances directly on the stack rather than on the heap, eliminating garbage collection overhead during rapid order-book updates.

### Mutable Structs and Field-Level `const`
When an algorithm requires in-place field updates (e.g., tracking a dynamically fluctuating asset price), the type is declared as a `mutable struct`.

Historically, making a structure mutable rendered all of its fields variable, forfeiting compiler optimizations. Julia 1.8 introduced **partial mutability**, allowing individual fields of a `mutable struct` to be declared permanently immutable via the `const` annotation:
```julia
mutable struct OrderBookTracker{T<:Real}
    const asset_symbol::String
    const exchange_mic::String
    last_traded_price::T
    total_volume_accumulated::Int64
end
```

In this structure, `asset_symbol` and `exchange_mic` are fixed at instantiation and protected against corruption, while `last_traded_price` and `total_volume_accumulated` can be updated in-place without reallocating the wrapper object.

##### Runtime Type Redefinition via World Age Mechanics
Prior to Julia 1.12, evaluating a modified `struct` definition within an active session triggered an invalidation error, necessitating a full REPL restart. 

Beginning in **Julia 1.12**, the runtime incorporates dynamic struct redefinition backed by Julia's internal **world age mechanism**. When a structure is redefined in global scope, the runtime increments the current world age and creates a new type binding for subsequent executions. Pre-existing instances and methods compiled under earlier world ages remain valid within their historical execution context, streamlining iterative quantitative development.

### Union Types and Nullable Data Modeling
A `Union` type represents an abstract type formed by the set-theoretic union of its type arguments:
$$\text{Union}\{T_1, T_2, \dots, T_n\} = \{x \mid x \in T_1 \lor x \in T_2 \lor \dots \lor x \in T_n\} \tag{1}$$

In quantitative datasets, missing market indicators or uninitialized limit orders are modeled using `Union{T, Nothing}`:
```julia
struct MarketQuote{T<:Real}
    bid::Union{T, Nothing}
    ask::Union{T, Nothing}
    timestamp_ns::Int64
end

# Constructing a quote with an empty ask book
quote_entry = MarketQuote{Float64}(101.25, nothing, 1718000000000)
```
The Julia compiler optimizes `Union{T, Nothing}` aggressively; when `T` is an `isbits` type (such as `Float64` or `Int64`), the union is stored inline using an additional byte flag, entirely avoiding heap allocation.

---
# Advanced Parametric Types, Conversions, and Argument Fixing
Parametric types permit structures and functions to be parameterized by types or value constants, enabling generic numerical algorithms to execute at machine-level efficiency.

## Parametric Composites and Type Invariance
A parametric composite type specializes its internal layout based on the specific type arguments provided at instantiation:
```julia
struct PortfolioHolding{Q<:Integer, P<:Real}
    ticker::String
    quantity::Q
    acquisition_price::P

    # Inner constructor enforcing state validity
    function PortfolioHolding(ticker::String, quantity::Q, acquisition_price::P) where {Q<:Integer, P<:Real}
        quantity >= 0 || throw(ArgumentError("holding quantity must be non-negative"))
        acquisition_price > zero(P) || throw(ArgumentError("acquisition price must be strictly positive"))
        return new{Q, P}(ticker, quantity, acquisition_price)
    end
end

# Dependent financial values are evaluated via functions rather than redundant state
market_exposure(h::PortfolioHolding) = h.quantity * h.acquisition_price
```

### The Invariance Principle
Parametric composite types in Julia are invariant. While `Float64` is a subtype of `Real` (`Float64 <: Real`), a vector of floating-point numbers is **not** a subtype of a vector of real numbers:
$$\text{Vector}\{\text{Float64}\} \not\subset \text{Vector}\{\text{Real}\} \tag{2}$$
Translating step 2 into the code below evaluates to false:
```julia
Vector{Float64} <: Vector{Real} # Evaluates to false
```

> [!danger]+ Intuition: Memory Layout and Boxing Overhead
> The mathematical rationale for invariance is grounded in computer hardware memory layouts. A `Vector{Float64}` is laid out in physical memory as a contiguous block of raw 64-bit IEEE floats. 
> 
> In contrast, a `Vector{Real}` must be capable of holding any concrete subtype of `Real` simultaneously (e.g., an `Int64`, a `Float32`, and a `Rational{Int128}`). Consequently, a `Vector{Real}` must store pointers to boxed objects scattered across the heap. If Julia allowed a `Vector{Float64}` to be treated as a `Vector{Real}`, one could attempt to insert an integer into a contiguous floating-point array, causing memory corruption.
> 
> To write methods that operate generically across all real vectors, one must use existential covariant type bounds:
> ```julia
> function aggregate_portfolio(holdings::Vector{<:Real}) ... end
> ```

### Contemporary Array Architecture and `Memory{T}`
Beginning in **Julia 1.11**, the foundational architecture of the standard `Array` underwent a major transformation. The legacy C runtime wrappers were replaced by pure Julia implementations backed by the new primitive buffer type:
$$\text{Memory}\{T\} \tag{3}$$
A `Memory{T}` instance represents a contiguous, non-resizable, 1D heap allocation managed directly by the Julia runtime. Modern multidimensional `Array{T, N}` structures are lightweight wrappers containing a `Memory{T}` buffer, an offset reference, and dimension tuples. 

This decoupling reduces structural memory footprint, accelerates garbage collection traversals, and permits custom allocator integration for latency-sensitive financial order routing.

---
### Explicit Type Coercion and the Four Automatic Conversion Boundaries
Type conversion in Julia is non-magical and explicit. Unlike languages that automatically cast floating-point numbers to integers, Julia avoids automatic coercion during standard function calls. Explicit conversion is invoked via constructors `T(x)` or the `convert(T, x)` interface:
```julia
integer_shares = 100
float_shares = Float64(integer_shares)          # Preferred explicit constructor syntax
converted_shares = convert(Float64, integer_shares) # Direct conversion protocol
```

Automatic conversion via `convert` is restricted to four specific language evaluation boundaries:
```
                      Conversion Boundaries
                                │
       ┌────────────────────────┼────────────────────────┐
       ▼                        ▼                        ▼
 1. Array Element         2. Struct Field          3. Declared Return
    Assignment               Assignment               Type Boundary
    A[i] = v                 obj.field = v            f()::T = v
                                │
                                ▼
                         4. Typed Global / Local
                            Assignment
                            x::T = v
```

1.  **Array Assignment:** Assigning a value into a typed array:
```julia
    portfolio_weights = zeros(Float64, 3)
    portfolio_weights[1] = 1 # Implicitly evaluates convert(Float64, 1)
```
2.  **Struct Field Assignment:** Assigning a value to a typed field during instantiation or mutable field mutation.
3.  **Explicit Return Annotations:** Returning a value from a function whose definition declares an explicit return type:
```julia
    function compute_alpha()::Float64
        return 1 # Implicitly evaluates convert(Float64, 1)
    end
```
4.  **Typed Variable Bindings:** Assigning a value to a variable declared with an explicit type signature:
```julia
    local risk_limit::Float64 = 500_000 # Implicitly evaluates convert(Float64, 500_000)
```

---
# Argument Fixing via the Unified `Base.Fix{N}` Operator
Julia 1.12 generalized the specialized two-argument binders (`Base.Fix1`, `Base.Fix2`) into a unified parametric type:
$$\text{Base.Fix}\{N\}(f, x) \tag{4}$$
`Base.Fix{N}` binds the $N$-th positional argument of a generic function $f$ to a fixed value $x$ at compile time, constructing a callable functor of reduced arity.

```julia
# A three-argument compound interest formula: A(P, r, t) = P * (1 + r)^t
compound_accrual(principal, rate, years) = principal * (1.0 + rate)^years

# Fix the 2nd positional argument (rate) to 5% (0.05)
accrue_at_5pct = Base.Fix{2}(compound_accrual, 0.05)

# The new callable takes 2 arguments: principal and years
balance = accrue_at_5pct(10_000.0, 10.0) # Evaluates compound_accrual(10_000.0, 0.05, 10.0)
```

> [!info]+ Remark: Positional Re-indexing Under Arity Contraction
> Binding an argument via `Base.Fix{N}` contracts the arity of the function from $K$ to $K - 1$. 
> 
> When chaining argument binders, subsequent positional indices refer to the **remaining uncurried slots**, not the original parameter positions of the underlying function. In complex production pipelines, standard anonymous functions (`p -> compound_accrual(p, 0.05, 10.0)`) are generally preferred for clarity unless zero-overhead functor dispatch is specifically required.
