---
dg-publish: true
---
# The Architecture of Financial Claims
In classical economic theory, decision problems under certainty focus on the allocation of endowment capital across consumption horizons. When uncertainty is introduced, decision-making necessarily expands to the selection and valuation of financial assets. While tangible assets consist of physical, material property (such as real estate, machinery, and physical commodities), financial assets represent intangible, legally enforceable claims to future economic benefits or cash flow streams.

Modern capitalist economies coordinate the allocation of capital, intertemporal consumption smoothing, and risk transfer through four fundamental financial instruments: *Cash, Credit, Equity, and Derivatives*. When these contracts are standardized, fungible, and freely traded across secondary liquid marketplaces, they constitute *Securities*.

---
# Relative Asset Pricing and Numeraire Mechanics

### The Concept of Relative Price
In an exchange economy devoid of an exogenous, absolute metric of value, the price of an asset can be expressed only relative to another asset chosen as the benchmark or accounting coordinate. Formally, this framework is established on a filtered probability space: 
$$
\begin{gather}
\textbf{Definition: Relative Asset Price Process} \\[5mm]
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \in [0, T]}, \mathbb{P}) \text{ be a filtered probability space satisfying the usual conditions,} \\[2mm]
\text{modeling the stochastic environment and information filtration of a financial market} \\[2mm]
\text{over the finite investment horizon } [0, T]. \text{ Let } \mathcal{A} \text{ denote the collection of strictly positive,} \\[2mm]
\text{non-worthless financial assets available in the economy. For any chosen reference asset } \\[2mm]
Y \in \mathcal{A} \text{ acting as the numeraire, the relative price process of an asset } X \in \mathcal{A} \\[2mm]
\text{denominated in units of } Y \text{ at time } t \in [0, T] \text{ is an } \mathcal{F}_t\text{-adapted, strictly positive stochastic process} \\[2mm]
X_Y(t): \Omega \times [0, T] \to \mathbb{R}_{>0}. \text{ Formally, } X_Y(t) \text{ defines the exchange ratio:} \\[3.5mm]
1 \text{ unit of } X \text{ at time } t \equiv X_Y(t) \text{ units of numeraire } Y \text{ at time } t
\end{gather}
$$
(see [[Probability Spaces and Filtrations]])

If the economy possesses an abstract, unobservable unit of account wherein nominal spot price processes are denoted by $S^X(t)$ and $S^Y(t)$, the relative price process evaluates to the algebraic ratio:
$$
\begin{gather}
X_Y(t) = \frac{S^X(t)}{S^Y(t)} \tag{1}
\end{gather}
$$

### Foundational Pricing Axioms
To eliminate structural internal contradictions and prevent trivial, riskless money-pumps between market participants, the relative pricing operator must satisfy three core algebraic axioms:
$$
\begin{gather}
\textbf{Axiom: Inverse Price Symmetry (Reciprocal Relation)} \\[5mm]
\text{For any two strictly positive assets } X, Y \in \mathcal{A}, \text{ the price of numeraire } Y \text{ denominated} \\[2mm]
\text{in units of asset } X \text{ at time } t \text{ is the exact multiplicative inverse of } X_Y(t)\text{:} \\[3.5mm]
Y_X(t) = \frac{1}{X_Y(t)}
\end{gather}
$$

The identity $X_Y(t) \cdot Y_X(t) = 1$ must hold $\mathbb{P}$-almost surely for all $t \in [0, T]$. If $X_Y(t) \cdot Y_X(t) > 1$, an agent could simultaneously purchase $X$ using $Y$ and sell $X$ for $Y$, generating unbounded, riskless spot arbitrage: 
$$
\begin{gather}
\textbf{Axiom: Numeraire Transitivity (Chain Rule of Relative Prices)} \\[5mm]
\text{For any triplet of non-worthless financial assets } X, Y, Z \in \mathcal{A}, \text{ the relative price of } X \\[2mm]
\text{in terms of } Y \text{ can be factored through an arbitrary intermediate asset } Z\text{:} \\[3.5mm]
X_Y(t) = X_Z(t) \cdot Z_Y(t) = \frac{X_Z(t)}{Y_Z(t)} 
\end{gather}
$$

The *Axiom of Numeraire Transitivity* guarantees triangular consistency across decentralized exchange networks, ensuring that currency cross-rates and relative valuation metrics are invariant to the sequence of intermediate transaction pairs.

$$
\begin{gather}
\textbf{Axiom: Linearity of Asset Portfolios} \\[5mm]
\text{Let a portfolio } P \text{ consist of a linear combination of } N \text{ underlying assets } \{X^i\}_{i=1}^N \subset \mathcal{A} \\[2mm]
\text{held in predictable, self-financing quantities } \{\Delta^i(t)\}_{i=1}^N. \text{ The relative price process} \\[2mm]
\text{of portfolio } P \text{ relative to numeraire } Z \in \mathcal{A} \text{ satisfies linear additivity:} \\[3.5mm]
P_Z(t) = \left[ \sum_{i=1}^N \Delta^i(t) X^i \right]_Z (t) = \sum_{i=1}^N \Delta^i(t) X_Z^i(t) 
\end{gather}
$$

(see [[Vector Spaces and Linear Maps]])

---
# The Fundamental Theorems of Asset Pricing
The foundational axioms of relative pricing provide an algebraic baseline for spot transactions. However, pricing contracts across time and resolving future uncertainty require dynamic stochastic principles. Modern mathematical finance links the economic concept of no-arbitrage to the probabilistic concept of a [[martingale]]: 
$$
\begin{gather}
\textbf{Theorem: The First Fundamental Theorem of Asset Pricing (FTAP)} \\[5mm]
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \in [0, T]}, \mathbb{P}) \text{ be a filtered probability space governing the financial economy.} \\[2mm]
\text{Assume that the market model admits a strictly positive, tradeable numeraire asset } Y \in \mathcal{A}. \\[2mm]
\text{The market satisfies the condition of No Free Lunch with Vanishing Risk (NFLVR)} \\[2mm]
\text{if and only if there exists a probability measure } \mathbb{P}^Y \text{ equivalent to the physical measure } \mathbb{P} \\[2mm]
(\mathbb{P}^Y \sim \mathbb{P}) \text{ such that the discounted relative price process } X_Y(t) \text{ is a local martingale} \\[2mm]
\text{under } \mathbb{P}^Y \text{ for every admissible, tradeable asset } X \in \mathcal{A}.
\end{gather}
$$
(see [[Proof of the First Fundamental Theorem of Asset Pricing]])

Under the equivalent martingale measure $\mathbb{P}^Y$, for any evaluation dates $0 \le s \le t \le T$, the relative price process satisfies the conditional expectation:
$$
\begin{gather}
X_Y(s) = \mathbb{E}^{\mathbb{P}^Y} \left[ X_Y(t) \mid \mathcal{F}_s \right] \quad \mathbb{P}\text{-almost surely} \tag{2}
\end{gather}
$$

>[!danger]+ Intuition: Martingales vs. Economic Equilibrium
>Absence of arbitrage is strictly a statement about the impossibility of self-financing "free lunches"; it does not imply Walrasian or general economic equilibrium (where aggregate supply equals aggregate demand). An economy with severe market clearing frictions, excess supply, or capital rationing can remain entirely free of pure arbitrage as long as instantaneous price dislocations cannot be converted into riskless profits. Under the risk-neutral measure $\mathbb{P}^Y$, probabilities do not measure historical occurrence frequencies; they represent normalized state prices (Arrow-Debreu prices) that discount future states of nature according to their marginal utility of wealth.

$$
\begin{gather}
\textbf{Theorem: The Second Fundamental Theorem of Asset Pricing} \\[5mm]
\text{Assume that the financial market satisfies NFLVR (the set of equivalent local martingale} \\[2mm]
\text{measures } \mathcal{M}^e(Y) \text{ is non-empty). The market is complete (every contingent claim } H \in L^1(\Omega, \mathcal{F}_T, \mathbb{P}^Y) \\[2mm]
\text{can be perfectly replicated by an admissible self-financing trading strategy) if and only if} \\[2mm]
\text{the equivalent martingale measure } \mathbb{P}^Y \text{ is strictly unique: } |\mathcal{M}^e(Y)| = 1.
\end{gather}
$$
(see [[Proof of The Second Fundamental Theorem of Asset Pricing]])

If the equivalent martingale measure is unique, all derivative claims possess a single, unambiguous no-arbitrage price. If multiple equivalent martingale measures exist, the market is incomplete, and contingent claims possess an interval of viable no-arbitrage prices bounded by super-hedging and sub-hedging costs.

---
# The Four Fundamental Financial Instruments
Every complex security in modern financial markets represents a contractual combination or structural derivative of four foundational instruments: **Cash, Credit, Equity, and Derivatives**:
![[four_fundamental_instruments.png]]
(see [[Tikz Code - Taxonomy of the Four Fundamental Financial Instruments]])
### 1. Cash and the Money Market Numeraire
In modern monetary theory and stochastic finance, cash is the *spot reference asset* serving as the immediate liquid unit of account: 
$$
\begin{gather}
\textbf{Definition: Money Market Account (Cash Process)} \\[5mm]
\text{Let } r(t) \ge 0 \text{ be an } \mathcal{F}_t\text{-adapted, locally integrable short-rate process. The continuous} \\[2mm]
\text{money market account } M(t) \text{ represents the risk-free cash accumulation process:} \\[3.5mm]
M(t) := \exp\left( \int_0^t r(s) \, ds \right), \quad M(0) = 1  \\[3.5mm]
dM(t) = r(t) M(t) \, dt 
\end{gather}
$$

While nominal physical currency yields a nominal interest rate of zero ($dC(t) = 0$), fiat currency in an inflationary economy experiences continuous purchasing power depreciation. Let $\Pi(t)$ denote the price level of a standardized basket of consumption goods, governed by $d\Pi(t) = \pi(t) \Pi(t) dt + \sigma_\Pi(t) \Pi(t) dW_t^\Pi$. The real purchasing power of cash $C_{\text{real}}(t) := \frac{C(t)}{\Pi(t)}$ follows:
$$
\begin{gather}
dC_{\text{real}}(t) = -\pi(t) C_{\text{real}}(t) \, dt - \sigma_\Pi(t) C_{\text{real}}(t) \, dW_t^\Pi + \sigma_\Pi^2(t) C_{\text{real}}(t) \, dt \tag{3}
\end{gather}
$$

Cash serves as an immediate, friction-free medium of exchange, yet holding non-interest-bearing currency incurs an opportunity cost equal to the forgone short rate $r(t)$ plus the purchasing power erosion of inflation $\pi(t)$.

### 2. Credit: Intertemporal Debt Contracts
Credit is an intertemporal financial contract where a borrower obtains immediate spot capital at time $t$ by issuing a legally binding, senior liability promising the delivery of specified cash flows at future horizons $\{T_k\}_{k=1}^K$.

The elementary building block of all credit and fixed-income contracts is the *default-free zero-coupon bond*: 
$$
\begin{gather}
\textbf{Definition: Zero-Coupon Bond} \\[5mm]
\text{A zero-coupon bond } P(t, T) \text{ is a contract that guarantees the delivery of exactly} \\[2mm]
1 \text{ unit of nominal cash at maturity } T \ge t, \text{ with zero intermediate cash flows.} \\[3.5mm]
\text{Under the risk-neutral measure } \mathbb{Q} \text{ with cash numeraire } M(t)\text{:} \\[3.5mm]
P(t, T) = \mathbb{E}^{\mathbb{Q}}\left[ \exp\left( -\int_t^T r(s) \, ds \right) \;\middle|\; \mathcal{F}_t \right] 
\end{gather}
$$

In corporate and sovereign debt markets, credit contracts incorporate **default risk**. Let $\tau: \Omega \to [0, \infty)$ denote a random stopping time representing the default event of the issuer, governed by a hazard rate process $\lambda(t)$. If default occurs at $\tau \le T$, the creditor recovers a fractional recovery rate $R \in [0, 1)$ of the par value. The defaultable bond price $P^d(t, T)$ satisfies:
$$
\begin{gather}
P^d(t, T) = \mathbb{E}^{\mathbb{Q}}\left[ \exp\left( -\int_t^T (r(s) + (1 - R)\lambda(s)) \, ds \right) \;\middle|\; \mathcal{F}_t \right] \tag{4}
\end{gather}
$$

Credit obligations occupy the most senior position in corporate capital structure: creditors must be paid in full prior to any distribution of cash or assets to equity owners.

### 3. Equity: Subordinated Residual Claims
Equity represents perpetual, residual ownership of an enterprise. Unlike credit, equity contracts specify no fixed coupon obligations and have no maturity date. Equity holders assume the primary downside risk of the operating enterprise; in return, they retain an uncapped legal claim to all residual cash flows (earnings, liquidating dividends) and voting governance rights.

Under *Robert Merton*'s (1974) structural model of corporate capital structure, corporate equity is modeled analytically as a contingent claim on total firm assets.
$$
\begin{gather}
\textbf{Definition: Merton's Structural Formulation of Corporate Equity} \\[5mm]
\text{Let } V(t) \text{ denote the total unobserved enterprise value of a firm at time } t, \text{ and let the firm} \\[2mm]
\text{be financed by a single class of zero-coupon debt with face value } D \text{ maturing at horizon } T. \\[2mm]
\text{Under limited liability, the equity value } E(T) \text{ at maturity is an exact European call option} \\[2mm]
\text{on firm assets with strike price equal to the debt face value } D\text{:} \\[3.5mm]
E(T) = \max(V(T) - D, \, 0) \\[3.5mm]
\text{The value of corporate debt at maturity satisfies the conservation of enterprise value:} \\[3.5mm]
D(T) = \min(V(T), \, D) = D - \max(D - V(T), \, 0)
\end{gather}
$$

The second equation in the definition above demonstrates that holding defaultable corporate debt is economically equivalent to holding risk-free sovereign debt while writing an unhedged put option on the firm's assets to the equity holders.

>[!warning]+ Warning: Equity as a Pricing Numeraire
>While dividend-reinvested equity indices are often deployed as numeraires in derivative pricing (such as the *share measure* $\mathbb{P}^S$), an asset can serve as a valid numeraire only if its price process remains strictly positive almost surely: $S_t > 0$ $\mathbb{P}$-a.s. For defaultable corporations modeled by step 12, if $V(T) \le D$, equity value collapses to zero ($E(T) = 0$). Because $\mathbb{P}(E(T) = 0) > 0$, the Radon-Nikodym derivative $\frac{d\mathbb{P}^E}{d\mathbb{Q}}$ is non-invertible, destroying measure equivalence. Equity in a defaultable entity cannot serve as an equivalent martingale numeraire across states of bankruptcy.

### 4. Financial Derivatives: Pure Contingent Claims
A *financial derivative* is a bilateral contractual agreement whose economic value and future cash flows derive entirely from the price level, rate, or performance of an external reference variable (the underlying instrument $S_t$).

Unlike spot cash, credit, or equity, financial derivatives are primarily unfunded or require an initial margin fraction strictly smaller than the underlying notional value: 
$$
\begin{gather}
\textbf{Definition: General Contingent Claim Payoff Functional} \\[5mm]
\text{Let } \{S(t)\}_{t \in [0, T]} \text{ be the adapted price path of an underlying reference security. The terminal} \\[2mm]
\text{payoff of a European path-dependent contingent claim } V(T) \text{ is an } \mathcal{F}_T\text{-measurable functional } \Phi\text{:} \\[3.5mm]
V(T) = \Phi\left( \{S(u)\}_{0 \le u \le T} \right)
\end{gather}
$$

The taxonomy of derivatives spans several fundamental settlement geometries:
1. **Vanilla European Claims:** Payoff depends exclusively on the terminal spot price at horizon $T$: $V(T) = f(S(T))$. Examples include European calls ($f(S) = \max(S - K, 0)$) and puts ($f(S) = \max(K - S, 0)$).
2. **Path-Dependent Exotic Claims:** Payoff depends on the historical trajectory across $[0, T]$. For continuous Asian options, the payoff evaluates to $f\left(\frac{1}{T}\int_0^T S(u) du\right)$; for barrier options, payoff depends on the first passage time $\tau_B := \inf\{t \ge 0 \mid S(t) = B\}$.
3. **American and Bermudan Contingent Claims:** The holder possesses the legal right to exercise the contract at an optimal stopping time $\tau \in \mathcal{T}_{[0, T]}$ prior to or at maturity:
   $$V(t) = \operatorname{ess\,sup}_{\tau \in \mathcal{T}_{[t, T]}} \mathbb{E}^{\mathbb{Q}}\left[ \exp\left(-\int_t^\tau r(s) ds\right) f(S(\tau)) \;\middle|\; \mathcal{F}_t \right] \tag{5}$$

Derivatives are zero-sum in nominal cash flow settlement between counterparties: every dollar of profit realized by the long counterparty is offset by a dollar of loss incurred by the short counterparty. However, in economic welfare, derivatives are non-zero-sum: they enable the unbundling, trading, and transfer of specific market risks (e.g., interest rate duration, currency exposure, equity volatility) from risk-averse agents to entities capable of absorbing them.

---
# Taxonomy of Marketable Financial Securities
Marketable financial securities are categorized according to their term to maturity, legal structure, and priority of claim: 
![[maturity_structure_of_securities.png]]
(see [[Tikz Code - Taxonomy and Maturity Structure of Marketable Securities]])
### Money Market Instruments

Money market instruments are short-term debt obligations characterized by maturities of one year or less, high liquidity, large institutional transaction denominations, and minimal default risk.
* **Treasury Bills (T-Bills):** Short-term promissory obligations issued by sovereign governments (commonly at 4, 13, 26, and 52-week auctions). T-bills pay no explicit periodic coupons; they are issued at a discount to face value and mature at par, serving as the empirical proxy for the risk-free asset $R_F$.
* **Certificates of Deposit (CDs):** Time deposits issued by commercial banks that restrict early withdrawal but offer fixed or floating yields above baseline sovereign debt.
* **Commercial Paper:** Unsecured short-term promissory notes issued by large corporations to finance immediate operating working capital, typically maturing within 270 days to avoid formal registration requirements.
* **Repurchase Agreements (Repos):** Short-term collateralized loans wherein an institution sells a high-grade security (such as government debt) to a cash provider with an agreement to repurchase the security at a slightly higher price at a specified future date. The price differential determines the repo rate.

### Capital Market Debt Instruments
Capital market instruments possess maturities exceeding one year, trading across medium-term and long-term investment horizons.
* **Treasury Notes and Bonds:** Sovereign coupon-bearing debt. Medium-term notes mature between 1 and 10 years; long-term bonds mature between 10 and 30 years. These instruments pay semi-annual coupons and return par value at maturity.
* **Corporate Bonds:** Debt instruments issued by private corporations, rated by credit agencies according to default likelihood (investment grade versus high-yield/junk). Corporate bonds carry higher risk premiums (credit spreads) over sovereign baselines and frequently contain embedded optionality (call provisions allowing the corporation to retire debt early when interest rates drop).
* **Municipal Bonds:** Debt obligations issued by regional or local state entities (states, cities, school districts). Municipal debt is typically exempt from federal (and often state) income taxation.

##### Municipal Bond Taxable Equivalent Yield
Because municipal bond interest is exempt from income taxation, an investor must evaluate the security on an after-tax equivalent basis to compare its return to taxable sovereign or corporate bonds: 
$$
\begin{gather}
\textbf{Proposition: Taxable Equivalent Yield (Par Bond)} \\[5mm]
\text{Let } Y_m \text{ denote the nominal yield on a tax-exempt municipal bond selling at par value,} \\[2mm]
\text{and let } t_m \in [0, 1) \text{ denote the investor's marginal income tax rate. The taxable equivalent} \\[2mm]
\text{yield } Y_t \text{ that leaves the investor indifferent between the two assets is:} \\[3.5mm]
Y_t = \frac{Y_m}{1 - t_m}
\end{gather}
$$

>[!warning]+ Warning: Discount Municipal Bonds and Capital Gains Taxation
>The relation in step 16 holds strictly if and only if the municipal bond sells at par value ($P = F$) and the yield curve is flat. If a municipal bond trades at a market discount ($P < F$), only the periodic coupon cash flow $C$ remains tax-exempt. The accretion of the market discount to par $(F - P)$ over the holding period is classified under tax law as a capital gain or ordinary income, taxed at the capital gains tax rate $t_{cg}$. For a discount bond maturing in one period:
>
>$$P = \frac{C + F - t_{cg}(F - P)}{1 + Y_{\text{after-tax}}} \tag{6}$$
>
>Failing to account for the taxation of the discount accretion overstates the after-tax yield of deep-discount municipal bonds.

### Equity Securities
* **Preferred Stock:** A hybrid equity security with statutory characteristics of both debt and common stock. Preferred stock pays a specified periodic dividend (fixed dollar amount or percentage of par). In exchange for dividend priority over common stock, preferred shares usually surrender voting control and do not participate in operating profit growth beyond the fixed dividend. Unpaid preferred dividends accumulate if specified as cumulative preferred.
* **Common Stock:** Represents the core residual ownership of a corporation. Holders possess voting rights to elect the board of directors and approve major corporate actions. Dividends on common stock are discretionary, declared by the board of directors out of free cash flow. In return for bearing junior subordination risk in corporate bankruptcy, common shareholders retain limited liability: the maximum financial loss is strictly bounded by the initial capital invested.

---
# Empirical Risk and Return: The Historical Baseline
To ground theoretical asset pricing in empirical reality, consider the historical long-term return and risk data that tracks annualized performance across major asset classes from 1926 through 2011, within the context of the US securities market:
$$
\begin{gather}
\textbf{Table: Historical Return and Risk Across Asset Classes (1926–2011)} \\
\begin{array}{lcc}
\hline
\textbf{Asset Class} & \textbf{Arithmetic Mean Return (\%)} & \textbf{Standard Deviation (\%)} \\
\hline
\text{U.S. Treasury Bills} & 3.6 & 3.1 \\
\text{Long-Term Government Bonds} & 6.1 & 9.8 \\
\text{Long-Term Corporate Bonds} & 6.4 & 8.4 \\
\text{Large Company Common Stocks} & 11.8 & 20.3 \\
\text{Small Company Common Stocks} & 16.5 & 32.5 \\
\text{Consumer Price Index (Inflation)} & 3.1 & 4.2 \\
\hline
\end{array}
\end{gather}
$$

Three empirical facts emerge from the historical records above:
1. **The Equity Risk Premium:** Large company common stocks delivered an average nominal return of $11.8\%$ compared to $3.6\%$ for Treasury bills, establishing an average historical equity risk premium of:
   $$\mathbb{E}[R_M - R_F] \approx 11.8\% - 3.6\% = 8.2\% \tag{7}$$
2. **The Size Premium:** Small capitalization stocks exhibited higher average returns ($16.5\%$) alongside higher dispersion ($\sigma = 32.5\%$), reflecting compensation for liquidity risk and higher distress exposure.
3. **Purchasing Power Preservation:** U.S. Treasury bills generated an average return of $3.6\%$ against an inflation rate of $3.1\%$, yielding a modest historical real risk-free rate of approximately $0.5\%$. Fixed-income instruments with longer duration (government and corporate bonds) delivered positive real returns, compensating investors for maturity and credit risks.

---
# Collective Investment Vehicles and Indirect Investing
Direct investment in individual capital market instruments requires research overhead, monitoring costs, and capital scale to achieve diversification. Consequently, modern financial systems utilize collective investment vehicles to pool capital.

### Structure of Investment Companies
* **Open-End Mutual Funds:** Issue and redeem shares directly with investors continuously at the fund's **Net Asset Value (NAV)** calculated once daily at market close:
  $$\text{NAV}_t = \frac{\text{Market Value of Fund Assets}_t - \text{Total Liabilities}_t}{\text{Total Shares Outstanding}_t} \tag{8}$$
  Open-end funds face redemption liquidity risk: sudden outflows force portfolio managers to liquidate underlying securities, potentially generating adverse price impact.
* **Closed-End Investment Companies:** Issue a fixed number of shares via an initial public offering (IPO), after which shares trade on secondary stock exchanges like common equity. The market price $P_t$ of a closed-end share is determined by supply and demand, frequently trading at a persistent discount or premium to its Net Asset Value:
  $$\text{Discount}_t = \frac{\text{NAV}_t - P_t}{\text{NAV}_t} \tag{9}$$
  This persistent deviation is the "closed-end fund puzzle," driven by managerial expense drag, unrealized tax liabilities, and noise trader sentiment.
* **Exchange-Traded Funds (ETFs):** Investment companies that trade on secondary exchanges throughout the trading day at market-determined prices, but incorporate a continuous creation and redemption arbitrage mechanism. Authorized Participants (APs) exchange baskets of underlying securities for creation units of ETF shares (and vice versa). If an ETF trades at a discount to NAV, APs purchase the discounted ETF shares, redeem them for the underlying basket, and sell the underlying assets, keeping the market price close to the intrinsic NAV.

### Alternative Investment Structures
* **Hedge Funds:** Private investment partnerships unconstrained by public mutual fund regulatory limits. Hedge funds can utilize leverage, execute short sales, trade exotic derivatives, and invest in illiquid assets. Fee structures commonly follow the "2 and 20" model: a $2\%$ annual management fee on total assets under management (AUM) combined with a $20\%$ incentive fee on net profits above a hurdle rate, subject to a high-water mark.
* **Private Equity and Venture Capital:** Pooled funds that purchase controlling equity stakes in private operating companies or early-stage startups. Capital is committed for long lock-up periods (typically 7 to 10 years). Value creation relies on financial restructuring, operational improvements, and strategic exits via IPO or corporate acquisition.
* **Sovereign Wealth Funds (SWFs):** State-owned investment vehicles funded by national foreign exchange surpluses, commodity exports (e.g., petroleum), or fiscal reserves. Characterized by long investment horizons, SWFs act as countercyclical macro allocators in global financial markets.

---
# Mathematical Foundations of Market Indexes
Market indexes serve as benchmarks for evaluating active investment performance, calculating systematic risk parameters ($\beta$), and constructing passive replication products.

### Weighting Methodologies
An index of $N$ constituent assets at time $t$ has constituent prices $\{P_{i,t}\}_{i=1}^N$ and shares outstanding $\{Q_{i,t}\}_{i=1}^N$. The index level $I_t$ is determined by the allocation weight $w_{i,t}$ assigned to each constituent.

##### 1. Price-Weighted Index
In a price-weighted index (e.g., the Dow Jones Industrial Average, Nikkei 225), the weight assigned to each security is proportional strictly to its nominal per-share market price:
$$
\begin{gather}
w_{i,t} = \frac{P_{i,t}}{\sum_{j=1}^N P_{j,t}} \tag{10} \\[3.5mm]
I_t = \frac{\sum_{i=1}^N P_{i,t}}{D_t} \tag{11}
\end{gather}
$$

where $D_t$ represents the index **divisor**. A price-weighted index mirrors the performance of a portfolio containing exactly one share of each constituent stock. 

A stock trading at $\$200$ per share exerts ten times the influence of a stock trading at $\$20$, regardless of total market capitalization.

When a stock undergoes an $m$-for-1 split or a constituent is replaced, the nominal sum of constituent prices shifts abruptly from $\sum P_{\text{old}}$ to $\sum P_{\text{new}}$. To ensure index continuity ($I_{t+} = I_{t-}$), the divisor must adjust recursively:
$$
\begin{gather}
\frac{\sum_{i=1}^N P_{i,t}^{\text{old}}}{D_{t-}} = \frac{\sum_{i=1}^N P_{i,t}^{\text{new}}}{D_{t+}} \implies D_{t+} = D_{t-} \cdot \frac{\sum_{i=1}^N P_{i,t}^{\text{new}}}{\sum_{i=1}^N P_{i,t}^{\text{old}}} \tag{12}
\end{gather}
$$

##### 2. Value-Weighted (Market-Capitalization-Weighted) Index
In a value-weighted index (e.g., *S&P 500, MSCI World*), the weight of each security is proportional to its aggregate market capitalization:
$$
\begin{gather}
w_{i,t} = \frac{P_{i,t} Q_{i,t}}{\sum_{j=1}^N P_{j,t} Q_{j,t}} = \frac{M_{i,t}}{\sum_{j=1}^N M_{j,t}} \tag{13} \\[3.5mm]
I_t = \frac{\sum_{i=1}^N P_{i,t} Q_{i,t}}{\sum_{i=1}^N P_{i,0} Q_{i,0}} \times I_0 = \frac{M_t}{B_t} \times I_0 \tag{14}
\end{gather}
$$

where $M_t := \sum_{i=1}^N P_{i,t} Q_{i,t}$ is total market capitalization and $B_t$ is the base market value divisor.

Value-weighted indexes are **macroconsistent**: they reflect the aggregate market portfolio held by all investors in macroeconomic equilibrium. A value-weighted index is naturally self-rebalancing: as asset prices fluctuate, the market capitalization shifts in proportion to price changes, requiring zero transaction turnover for a buy-and-hold strategy.

Modern indexes commonly employ **free-float adjustments**, scaling $Q_{i,t}$ by a float factor $f_i \in (0, 1]$ to exclude illiquid insider stakes, sovereign holdings, and cross-corporate ownership.

##### 3. Equal-Weighted Index
In an equal-weighted index, an identical dollar amount is allocated to each constituent security at every rebalancing interval $t$:
$$
\begin{gather}
w_{i,t} = \frac{1}{N} \quad \forall i \in \{1, 2, \dots, N\} \tag{15}
\end{gather}
$$

An equal-weighted index de-emphasizes mega-cap companies and tilts aggregate exposure toward smaller-capitalization firms. Maintaining equal weights requires periodic portfolio rebalancing: the portfolio manager must sell shares of outperforming assets and purchase shares of underperforming assets, generating transaction costs.

---
# Mathematical Aggregation: Arithmetic vs. Geometric Compounding
The choice of mathematical aggregation scheme determines the return dynamics of an index.

### Arithmetic Aggregation
An arithmetically compounded index traces the value of a physical, buy-and-hold basket of assets:
$$
\begin{gather}
I_t^{\text{arith}} = I_{t-1}^{\text{arith}} \sum_{i=1}^N w_{i,t-1} \left( \frac{P_{i,t}}{P_{i,t-1}} \right) \tag{16}
\end{gather}
$$

Arithmetic aggregation preserves value-additivity: the dollar value of the index corresponds to the sum of the dollar values of its constituent holdings.

### Geometric Aggregation
A geometrically compounded index calculates the geometric mean of constituent price changes:
$$
\begin{gather}
I_t^{\text{geom}} = I_{t-1}^{\text{geom}} \prod_{i=1}^N \left( \frac{P_{i,t}}{P_{i,t-1}} \right)^{w_{i,t-1}} \tag{17}
\end{gather}
$$

For an equal-weighted geometric index ($w_i = \frac{1}{N}$):
$$
\begin{gather}
I_t^{\text{geom}} = I_{t-1}^{\text{geom}} \left( \prod_{i=1}^N \frac{P_{i,t}}{P_{i,t-1}} \right)^{\frac{1}{N}} \tag{18}
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Jensen's Volatility Drag in Geometric Indexing} \\[5mm]
\text{For any set of positive constituent price returns } R_{i,t} := \frac{P_{i,t}}{P_{i,t-1}} - 1, \text{ the return of a} \\[2mm]
\text{geometrically aggregated index is strictly less than or equal to the return of an arithmetically} \\[2mm]
\text{aggregated index:} \\[3.5mm]
R_t^{\text{geom}} \le R_t^{\text{arith}} \tag{31} \\[3.5mm]
\text{with equality holding if and only if all constituent returns are identical: } R_{1,t} = R_{2,t} = \dots = R_{N,t}. \\[2mm]
\text{Under lognormal continuous-time diffusion with average constituent variance } \bar{\sigma}^2\text{:} \\[3.5mm]
\mathbb{E}[R_t^{\text{arith}}] - \mathbb{E}[R_t^{\text{geom}}] \approx \frac{1}{2} \operatorname{Var}(R_i) 
\end{gather}
$$
(see [[Proof of Jensen's Inequality for Geometric Indices]])

Because the natural logarithm is strictly concave ($\frac{d^2 \ln x}{dx^2} = -\frac{1}{x^2} < 0$), Jensen's inequality dictates:
$$
\begin{gather}
\ln\left( \frac{1}{N}\sum_{i=1}^N \frac{P_{i,t}}{P_{i,t-1}} \right) > \frac{1}{N}\sum_{i=1}^N \ln\left( \frac{P_{i,t}}{P_{i,t-1}} \right) = \ln\left[ \left( \prod_{i=1}^N \frac{P_{i,t}}{P_{i,t-1}} \right)^{\frac{1}{N}} \right] \tag{19}
\end{gather}
$$

Exponentiating both sides proves step 31. A geometric index understates the long-term wealth created by holding an actual portfolio of securities.

---
# Computational Implementation in Julia
The following production-grade Julia implementation demonstrates:
1. Municipal bond after-tax equivalent yield calculation across par and discount regimes.
2. Price-weighted index construction with automated divisor adjustments following stock splits.
3. Market-capitalization-weighted and equal-weighted index simulation.
4. Numerical proof of Jensen's volatility drag in geometric vs. arithmetic aggregation.

```julia
# ==============================================================================
# Quant's Bible: Financial Instruments, Securities, and Index Engineering
# Language: Julia 1.x
# Packages: LinearAlgebra, Statistics, DataFrames
# ==============================================================================

using LinearAlgebra
using Statistics
using DataFrames

"""
    municipal_taxable_equivalent_yield(Y_m, tax_rate; P=100.0, F=100.0, t_cg=0.20)

Computes the taxable equivalent yield for municipal debt.
Handles both par bonds and market-discount bonds subject to capital gains tax.
"""
function municipal_taxable_equivalent_yield(
    Y_m::T, 
    tax_rate::T; 
    P::T = 100.0, 
    F::T = 100.0, 
    t_cg::T = 0.20
) where {T<:AbstractFloat}
    @assert 0.0 <= tax_rate < 1.0 "Income tax rate must reside in [0, 1)."
    @assert P > 0.0 && F > 0.0 "Prices and face values must be strictly positive."

    if P >= F
        # Standard par or premium tax-exempt formula
        return Y_m / (one(T) - tax_rate)
    else
        # Discount bond: Accretion of discount (F - P) is subject to capital gains tax
        # Approximate single-period yield adjustment
        capital_gain = F - P
        taxable_capital_gain = capital_gain * t_cg
        after_tax_cash_flow = (P * Y_m) + F - taxable_capital_gain
        after_tax_yield = (after_tax_cash_flow - P) / P
        return after_tax_yield / (one(T) - tax_rate)
    end
end

"""
    struct StockState{T<:AbstractFloat}

Holds the nominal state of a single stock constituent.
"""
struct StockState{T<:AbstractFloat}
    price::T
    shares::T
end

"""
    simulate_price_weighted_index(prices_pre, split_ratios, prices_post)

Calculates a price-weighted index with exact recursive divisor updates
following stock splits and corporate actions.
"""
function simulate_price_weighted_index(
    prices_pre::Vector{T},
    split_ratios::Vector{T},
    prices_post::Vector{T};
    initial_divisor::T = T(length(prices_pre))
) where {T<:AbstractFloat}

    sum_pre = sum(prices_pre)
    index_pre = sum_pre / initial_divisor

    # Adjusted post-split prices before trading day dynamics
    prices_adjusted_split = prices_pre ./ split_ratios
    sum_split = sum(prices_adjusted_split)

    # Divisor update relation: preserves index continuity
    updated_divisor = initial_divisor * (sum_split / sum_pre)

    # Final post-market session index level
    sum_post = sum(prices_post)
    index_post = sum_post / updated_divisor

    return (
        initial_index   = index_pre,
        updated_divisor = updated_divisor,
        final_index     = index_post
    )
end

"""
    compare_aggregation_schemes(price_matrix, weights)

Demonstrates the Jensen's Inequality gap between Arithmetic
and Geometric compounding across an N-asset universe over T periods.
"""
function compare_aggregation_schemes(
    price_matrix::Matrix{T},
    weights::Vector{T}
) where {T<:AbstractFloat}

    T_periods, N_assets = size(price_matrix)
    @assert length(weights) == N_assets "Weight vector dimension mismatch."
    @assert isapprox(sum(weights), one(T)) "Weights must sum to unity."

    arith_index = zeros(T, T_periods)
    geom_index  = zeros(T, T_periods)

    arith_index[1] = 100.0
    geom_index[1]  = 100.0

    for t in 2:T_periods
        price_relatives = price_matrix[t, :] ./ price_matrix[t - 1, :]
        
        # Arithmetic aggregation
        arith_return = dot(weights, price_relatives)
        arith_index[t] = arith_index[t - 1] * arith_return
        
        # Geometric aggregation
        log_relatives = log.(price_relatives)
        geom_return = exp(dot(weights, log_relatives))
        geom_index[t] = geom_index[t - 1] * geom_return
    end

    return DataFrame(
        Period = 1:T_periods,
        Arithmetic_Index = arith_index,
        Geometric_Index = geom_index,
        Drag = arith_index .- geom_index
    )
end

# ------------------------------------------------------------------------------
# Numerical Execution and Demonstration
# ------------------------------------------------------------------------------

# 1. Municipal Bond Equivalent Yield Demonstration
Y_muni = 0.045       # 4.50% tax-exempt yield
tax_marginal = 0.35  # 35% marginal bracket
equiv_par = municipal_taxable_equivalent_yield(Y_muni, tax_marginal, P=100.0, F=100.0)
equiv_disc = municipal_taxable_equivalent_yield(Y_muni, tax_marginal, P=85.0, F=100.0, t_cg=0.20)

println("Municipal Bond Taxable Equivalent Yield Analysis:")
println("Par Bond Equivalent Yield:      ", round(equiv_par * 100, digits=3), "%")
println("Discount Bond Equivalent Yield: ", round(equiv_disc * 100, digits=3), "%\n")

# 2. Price-Weighted Divisor Adjustment
# 3-stock universe: Stock 1 splits 2-for-1
p_pre = Float64[100.0, 50.0, 30.0]
splits = Float64[2.0, 1.0, 1.0]     # Asset 1 executes 2:1 split
p_post = Float64[55.0, 52.0, 29.0]  # Next-day realized prices

pw_results = simulate_price_weighted_index(p_pre, splits, p_post)
println("Price-Weighted Index Divisor Adjustment:")
println("Initial Index:   ", round(pw_results.initial_index, digits=3))
println("Updated Divisor: ", round(pw_results.updated_divisor, digits=4))
println("Final Index:     ", round(pw_results.final_index, digits=3), "\n")

# 3. Arithmetic vs. Geometric Compounding Drag
# Synthesize 5 periods of volatile price evolution across 3 assets
P_history = Float64[
    100.0  100.0  100.0;
    120.0   90.0  105.0;
    110.0  115.0   95.0;
    135.0   80.0  110.0;
    125.0  105.0  115.0
]
w_equal = fill(1.0 / 3.0, 3)
drag_df = compare_aggregation_schemes(P_history, w_equal)

println("Empirical Verification of Jensen's Inequality Drag in Indexing:")
println(drag_df)
```
