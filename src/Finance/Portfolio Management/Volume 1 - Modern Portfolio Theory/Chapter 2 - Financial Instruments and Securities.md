---
dg-publish: true
---
[[Chapter 1 - The Theory of Choices|Chapter 1 demonstrates]], a core part of making decisions is the selection of assets. While there're numerous types of assets, both *tangible* (real, material, and capable of being physically perceived) and *tangible* assets (lacks physical substance), most economies revolve around four fundamental instruments: *Cash, Credit, Equity, and Derivative*. 

---
# Asset Pricing
### Concept of Price
In any economy, the purchase of a good or service comes with a *price*. Intuitively speaking, the price is the cost of acquiring the good or service that someone in the economy is providing. Due to the many forms of goods and services being available in the economy, it's often possible to price these goods and services in terms of one another. Formally, this can be defined as *relative asset price:*
$$
\begin{gather}
\textbf{Definition: Relative Asset Price} \\[5mm]
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \ge 0}, \mathbb{P}) \text{ be a filtered probability space representing the} \\
\text{stochastic environment and information flow of a financial economy over a time horizon } \\
t \in [0,T]. \text{ Additionally, let } \mathcal{A} \text{ denote the set of strictly positive non-worthless} \\
\text{financial assets available in the economy. For any two assets } X \text{ and } Y \in \mathcal{A},  \\
\text{the asset } Y \text{ is selected to serve as the reference asset or numeraire. } \\
\text{The price process of asset } X \text{ relative to numeraire } Y \text{ at time } t \text{ is defined as an } \\ \mathcal{F}_t\text{-adapted strictly positive stochastic process denoted by } X_{Y}(t). \text{ Formally, } X_{Y}(t) \\
\text{represents the number of units of asset Y required to acquire one unit of asset } X \text{ at time } t:  \\[2.5mm]

\text{1 unit of } X = X_{Y}(t) \text{ units of Y } \iff X_{t} = X_{Y}(t) \cdot Y_{t} \text{ for } X_{Y}(t)
\end{gather}
$$
(See [[Chapter 1 - Measurable and Probability Spaces|probability spaces]] for more information)

### Foundational Axioms
From this pairwise algebraic definition arises several structural properties. These properties are considered to be the fundamental [[Chapter 1 - Basic Rules of Logic|assumptions]] of financial mathematics that provide a non-ambiguous and grounded approach to understanding pricing:  
$$
\begin{gather}
\textbf{Axiom: Inverse Price Symmetry (Reciporocal Relation)} \\[5mm]
\text{If neither asset } X \text{ nor asset } Y \text{ is worthless } (0 < X_{Y}(t) < \infty), \text{ the price of asset } Y  \\
\text{using asset } X \text{ as the numeraire, } \text{ denoted by } Y_{X}(t), \text{ is the multiplicative inverse of } X_{Y}(t):  \\[2.5mm]

Y_{X}(t) = \frac{1}{X_{Y}(t)}
\end{gather}
$$
To prevent risk-free *arbitrage* opportunities between economic participants, the identity $X_Y(t) \cdot Y_X(t) = 1$ must hold almost surely at all times $t$. 

$$
\begin{gather}
\textbf{Axiom: Change of Numeraire (Transitivity): } \\[5mm]
\text{For any valid non-zero assets } X,Y,Z \in \mathcal{A}, \text{ the price of asset } X \text{ in terms of } \\
\text{numeraire } Y \text{ can be decomposed through an intermediate reference asset } Z:  \\[2.5mm]
X_Y(t) = X_Z(t) \cdot Z_Y(t) = \frac{X_Z(t)}{Y_Z(t)}
\end{gather}
$$
This coordinate transformation relation allows for the translation of pricing problems across arbitrary reference frames. 

$$
\begin{gather}
\textbf{Axiom: Linearity of Asset Combinations} \\[5mm]
\text{Let } P_{t} = \sum_{i = 1}^N \Delta^i(t) \cdot X^i \text{ represent a portfolio formed by linear combinations of assets } \\
X^i \in \mathcal{A} \text{ held in quantities } \Delta^i(t). \text{ The price process of the portfolio } P \text{ relative to }\ \\
\text{numeraire } Z \text{ exhibits linearity: } \\[2.5mm]
P_Z(t) = \left[ \sum_{i=1}^N \Delta^i(t) \cdot X^i \right]_Z (t) = \sum_{i=1}^N \Delta^i(t) \cdot X_Z^i(t)
\end{gather}
$$
(see [[Chapter 2 - Finite-Dimensional Vector Spaces|linear combinations]] for more information)

### The Fundamental Theorem of Asset Pricing
These three axioms, along with the definition of a [[Chapter 4 - Filtrations and Martingales|martingale]], can be used to construct an important fact: 
$$
\begin{gather}
\textbf{Theorem 1: The Fundmental Theorem of Asset Pricing (Part 1)} \\[5mm]
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \ge 0}, \mathbb{P}) \text{ be a filtered probabiblity space governing the financial economy over a } \\
\text{finite time horizon } t \in [0,T]. \text{ Let } Y \text{ be a strictly positive, non-worthless no-arbitrage reference asset.} \\[2.5mm]

\text{If there exists a probability measure } \mathbb{P}^Y \text{ (equivalent to the real-world measure } \mathbb{P}) \text{ under which the } \\
\text{relative prices processes } X_Y(t) \text{ are } \mathbb{P}^Y\text{-martingales for every valid no-arbitrage asset } X,  \\
\text{then the financial economy contains no arbitrage opportunities. } 
\end{gather}
$$
(see [[Chapter 1 - Measurable Spaces|measure theory]] for more information and [[Finance/Portfolio Management/Volume 1 - Modern Portfolio Theory/Proofs and Derivations/Chapter 2/Proof of Theorem 1|proof]] for verification)

In formal measure-theoretic notation, for any time $s \le t \le T$, the normalized price process satisfies the conditional expectation:
$$X_Y(s) = \mathbb{E}^{\mathbb{P}^Y} \left[ X_Y(t) \mid \mathcal{F}_s \right] \quad \text{almost surely} \tag{1}$$
This theorem establishes an equivalence between the economic concept of economic equilibrium, which is an economic state where supply and demand for a specific asset are equal, and the mathematical concept of a martingale, which is a "fair game."

In real-world economies, assets carry risk premia, causing prices to drift upwards over time under the physical probability measure $\mathbb{P}$. However, adjusting the probability weights placed on future states of the world, shifting from the real-world measure $\mathbb{P}$ to a numeraire-specific martingale measure $\mathbb{P}^Y$, all expected excess returns are systematically neutralized. Under $\mathbb{P}^Y$, probabilities do not represent the physical likelihood of an event occurring. Instead, $\mathbb{P}^Y(A)$ represents the **state price** or economic cost (measured in units of numeraire $Y$) required today to deliver one unit of $Y$ at maturity $T$ if event $A$ occurs. If asset prices follow a martingale under this adjusted probability measure, future expected relative values equal current relative values. Consequently, no economic participant can construct a trading strategy that guarantees a risk-free profit out of nothing.

In other words, prices in the economy are based off some sorta benchmark. A relative price is the price of a good or service in terms of another good or service. This is the foundation of *barter*, which is trading goods or services directly for other goods or services. It's the oldest form of commerce that forms the foundation of trade. However, the fundamental flaw barter is the *lack of a double coincidence of wants*. This is further complicated by the absence of a common measure of value and the indivisibility of goods. 

---
# The Four Fundamental Financial Instruments
### The Need for Cash
While the aforementioned axioms and theorems provide an un-ambiguous and useful means of comparing the values of other goods based on an asset, as relative pricing suggest, this comparison doesn't always work. It would be much easier if there was a universal and common measure of value that could be utilized as a universal financial solvent of sorts. While cash is often seen as an intuitive economic concept, it could also be given an un-ambiguous definition that fits in a precise mathematical framework: 
$$\begin{gather}
\textbf{Definition: Cash} \\[5mm]
\text{Cash is a spot reference coordinate and arbitrage asset exhibiting a non-zero rate } \\
\text{of time depreciation. While it serves as an immediate liquid unit of account for spot transactions, } \\
\text{it lacks an independent pricing martingale measure } \mathbb{P} \text{ across time.}
\end{gather}
$$
In social science and political economy, cash is legal tender used for purchasing goods, receiving services, and paying off debts. For cash to have value, the economy its operating in must recognize it to be the universal store of value. It's cash that also provides the base unit of value that other financial instruments are to be measured under. 

### Credit: Borrowing Against the Future
Acquiring goods and services, in the hypothetical economy that this framework cooked up, is done with cash. Acquiring more goods and services is as simple as forking over more cash to spend. However, the economic agent may not always have the needed cash on hand. In a cash-based society, the only way for the agent to acquire more goods and services is to come up with more cash. The agent can achieve this in one of two ways: 
1. Increase the amount of effort they put into their work. In some economies, more input yields more output. The more output they provide, the more cash they're given as compensation. 
2. Increase the amount of assets they own, especially of the cash-generating sort. These assets can bring in extra income or be sold at a higher price. 
Alas, doing one of two of these steps is easier said than done. In such a circumstance, the agent may opt for a third option: Credit-fueled spending: 
$$
\begin{gather} \textbf{Definition: Credit} \\[5mm] 
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \ge 0}, \mathbb{P}) \text{ be a filtered probability space governing the economy.} \\ \text{Credit is an intertemporal financial contract wherein a borrower acquires immediate}
\\ \text{spot numeraire at time } t \text{ by issuing an enforceable liability process } L_t \text{ against}  \\
\text{their stochastic future cash flows or wealth endowment } \mathcal{F}_T. \\
\text{Formally, credit is represented as a short position in a no-arbitrage reference asset—}  \\
\text{either a zero-coupon bond } B^T \text{ or a money market account } M(t) \text{ satisfying } \\[2.5mm]
dM_{\$}(t) = r(t) M_{\$}(t) \, dt, \\[2.5mm]
\text{requiring the future delivery of } (1 + \delta L(t,T)) \text{ units of numeraire at maturity } T, \\
\text{priced under the appropriate martingale measure } \mathbb{P}^T \text{ adjusted for default risk.} 
\end{gather}
$$
In simpler terms, credit extends the agent's purchasing power by enabling them to borrow money against the future. However, this requires the agent to pay back the original cash they borrowed, *principal*, along with the cost, *interest.* 

###### Lending and Borrowing
In a deal involving credit, there're two sides of the agreement: *Lender* and *borrower:*
- **Lender:** The lender provides the cash, along with the interest policy. The lender takes on the risk of *default*, which is the risk that the borrower fails to pay back the credit. 
- **Borrower:** The borrower promises to pay the lender the principal and interest. The borrower runs the risk of failing to repay the lender. 

### Equity: A Form of Ownership
Most economies have some idea of ownership in something. In political economy, ownership refers to having legal rights over some resource or asset. It includes the right to use, exclude others, and benefit from property. Ownership structures differ by economic systems, and the type of ownership shapes incentives, control, and wealth distribution. 

In modern financial markets, there is a unique form of ownership that enables enterprises to operate as a dynamic nexus of contracts. This is referred to as *equity*, which is the difference between an entity's assets and liabilities. Equity occupies the lowest tier of the capital structure because it's subordinated to all credit obligations. 

Equity holders assume the ultimate downside risk caused by the value of their equity dropping. In exchange for this, equity holders retain perpetual un-capped claim on all excess returns and capital appreciation generated by the equity. 

Formally speaking, equity can be formally defined as
$$
\begin{gather}
\textbf{Definition: Equity } \\[5mm]
\text{Let } (\Omega, \mathcal{F}, \{\mathcal{F}_{t} \}_{t \geq 0}, \mathbb{P}) \text{ be a filtered probability space representing the economy. } \\
\text{Equity is a perpetual and subordinated financial claim } S_{t} \text{ representing the residual } \\
\text{ownership interest in an economic asset process } A_{t} \text{ after satisfying all senior credit } \\
\text{liabilities } L_{t}. \text{ Formally, over a liability settlement horizon } T \text{ with total debt obligation } D,  \\
\text{equity is a continuous contingent claim whose terminal value relative to numeraire } Y \text{ is } \\
\text{given by } \\[2.5mm]
S_{Y}(T) = \text{max}(A_{Y}(T) - D \cdot Y_{Y}(T), 0) \\[2.5mm]
\text{and whose price process}\textemdash\text{when adjusted for reinvested cash yields } \tilde{S}_{t}\textemdash\text{serves as a valid } \\
\text{reference asset generating the equivalent of stock measure } \mathbb{P}^{S}. 
\end{gather}
$$

### Derivative: A Zero-Sum Game
Derivatives are by far the most complex financial instrument among the four, with these having an esoteric reputation. At its core, however, a financial derivative is an agreement entailing the transfer of economic risk from the physical ownership of the asset. 

A financial derivative contract is a legally enforceable agreement between two counterparties: A *long* position, which is the position expecting the price of the underlying asset to rise, and the *short* position, which is the position expecting the price of the underlying asset to decline. Both have their future cash flows, obligations, or value are from or contingent upon the price, rate, or performance of one or more specified reference variables or underlying instruments, which is denoted by $S_{t}$. 

Mathematically, if $S_T$ represents the terminal price of the underlying asset at expiration date $T$, the value or payoff of a general derivative claim $V_T$ at maturity is a deterministic or state-contingent function $f(S_T)$ of the underlying instrument:
$$V_T = f(S_T) \tag{2}$$

###### Key Structural Elements
While there are a wide variety of classes of financial derivatives, every financial derivative possesses five fundamental characteristics: 
1. **Underlying Reference Variable**
	- The asset, rate, benchmark, or event from which the contract extracts its economic value. 
	- Underlyings span equities, credit, cash instruments. 
2. **Notional Amount** $(N)$
	The agreed-upon quantitative scale or principle units upon which intermediate or terminal cash flow calculations are determined. 
3. **Delayed Performance/Temporal Disconnection**
	Unlike *spot transactions*, where agreement, payment, and asset transfer occur concurrently, a derivative contract establishes economic terms today for an exchange or settlement that occurs at a pre-specified future date $T$. 
4. **Unfunded**
	- Zero or small amounts of capital is required to acquire the underlying asset outright at the time the contract is created or entered to, which is denoted by $t=0$. 
	- Certain derivative contract may enforce a *premium*, which is the cost of entering the contract. 
	- Consequently, derivatives are considered *contingent claims*. 
5. **Settlement Mechanics**
	- Contract maturity, which is denoted by $T$, dictates when the contract is to take place. 
	- One way for the contract to mature is via **physical delivery** of the underlying asset, which involves the transfer of the physical asset in exchange for the contract price. 
	- Another way for the contract to mature is via **cash settlement**, which involves the net payment of the profit or loss $f(S_{T})$ between the counterparties. 

---
# Securities
It was initially established that an asset is anything of economic value that is owned or can be controlled. Modern financial markets, however, mostly function on a unique form of financial claim: *Security*. While an asset can be tangible or intangible, a security is a specific category of financial asset that represents a *fungible* claim. Fungibility means identical units that can be exchanged without loss of value, enabling ownership to be exchanged effortlessly with another item of the same kind and value. 

In addition to fungibility, securities also exhibit increased *liquidity*. Liquidity refers to the ease with which an asset can be converted into cash without a loss in value. 

Due to the vast amount of securities in existence, this chapter'll only focus on securities traded in modern financial marketplaces.  
### Types of Marketable Securities
An investor can choose to purchase directly any one of a number of different securities, many of which represent a type of claim on a private or government entity. Alternatively, the investor can opt to purchase securities through an intermediary, which bundles a set of direct investments and then sells the shares in the portfolio of financial instruments it holds. Below is a visual aid in helping remember the structure of marketable securities: 
![[visual_aid_for_family_of_securities.png]]
Investments in debt that have a maturity of less than one year are *money market securities*, which can be issued by a government or private entity. Investments with maturities of a year or longer are *capital market* instruments, which come in the form of equity or credit. In the case of credit-based capital market instruments, these can be issued by government or private entities. The final category of security are derivative instruments. In the case of securities, the four derivative classes are *forwards, futures, options, and swaps.*

Below are notable examples of securities that make the bulk of financial activity in modern markets: 
###### Money Market Securities
- Short-term debt instruments
- Offered by governments, financial institutions, and corporations
- Have maturities of one year or less
- Relatively large minimum transaction sizes
- Some money market securities may not be publicly traded
- Doesn't promise significant return
- Considered safe and liquid
- Offer higher interest rates than default savings account
- Common examples are *Certificates of Deposits, Municipal notes,* and *Treasury Bills or Bonds*

###### Short-Term Treasury Bills
- Short-term IOUs offered by a government
- Usually offered in 91, 182, and 365-day maturities
- Has a *face value*, which is the amount of cash the investor receives at maturity
- Has a *coupon rate*, which is the interest received during the interest payoff interval
- Considered a proxy for *risk-free* investment due to having a low rate of default

###### Interbank Offered Rate
- Interest rate for short-term loans between banks to manage liquidity
- Interbank lending usually occurs overnight
- Primarily determined by *commercial banks*
- In foreign exchange, the *interbank rate* is the currency exchange rate between banks, often including a premium for consumers. 
- Usually reserved for large credit-worthy institutions

###### Treasury Notes or Bonds
- Broad range of maturity premium
- Can last from one to ten years for medium-term notes, and ten years or longer for long-term bonds
- Most notes and bonds pay interest twice a year and repay principal on the maturity date
- The government can force the note/bondholder to sell it back to the government, which usually occurs in the last five years of the bond or note's life. This is referred to as *callability.*
- Generally considered safe from default

###### Municipal Bonds
- Generally sold by political entities such as states, counties, airport authorities, school districts, and other entities who form a smaller part of the government
- Higher risk of default
- Tends to be tax-exempt, which means they tend to sell at a lower promised yield than nonmunicipals of the same risk. The equivalent yield, the discounted value of after-tax cash flows must be compared with pre-tax cash flows. The following simple formula can be used to approximate the taxable equivalent yield: 
$$ \text{Taxable equivalent yield } = \frac{\text{Tax-exempt municipal yield}}{1 - \text{marginal tax rate}} \tag{3}$$
This approximation holds exactly only if municipal bonds sell at par, the treasuries they are
being compared to sell at par, and the yield curve is flat. This method of taxable yield estimation should be used carefully for municipal bonds selling at below par since the *capital gains* may be subject to taxation. 

###### Corporate Bonds
- Issued by corporate for-profit entities
- Have a relatively high risk of default
- Creditworthiness of issuer is usually rated by dedicated agencies
- The nature of their claims tend to differ from corporation to corporation
- Are callable

###### Preferred Stock
- A major form of equity
- Pays shareholders periodic payments in the form of *dividends*
- Return on principal is usually nonexistent
- Failure to repay dividends doesn't imply bankruptcy or default
- First class of shareholders to be paid off
- Paid off after creditholders

###### Common Stock
- Represents ownership claim on earnings and assets of a corporation
- Corporation can choose to pay dividends to common stock holders or reinvest earnings
- Holder of common stock has *limited liability*, which shields them from bankruptcy. The most the common stockholder can lose is whatever they put in. 
- One of the riskiest securities one can buy

---
# Indirect Investing
While an investor can directly purchase the instruments mentioned in this chapter, as well as many other investment options not mentioned here, doing so may be difficult. Research, funding, and effort are required to make an informed investing decision that investors may not have the time or willingness for. In these cases, the investor may opt to indirectly invest through various means. 

Most collective indirect investing vehicles fall under two categories: *Actively Managed* and *Passively-Managed*: 
1. **Actively Managed**
	- Aims to outperform a benchmark
	- Strategically purchases securities that may outperform other
	- Focused on generating *alpha*, which are excess returns above a benchmark
	- Adjust holdings based on economic trends, sector shifts, or company fundamentals
	- Take calculated risk to deliver superior performance
	- Charges relatively higher fees
2. **Passively Managed**
	- Replicates the performance of a benchmark by mimicking their makeup
	- Delivers returns based on said benchmark 
	- Minimizes trading and turnover of underlying assets
	- Keep costs low and through automation and rule-based investing
	- Provide diversification aligned with the benchmark's composition 
	- Charges relatively lower expense ratios and fees, as well as being more tax-efficient

While there're many collective investment vehicles, below are currently the most popular investment vehicles for both retail and institutional investors:

###### Mutual Funds
- Takes on the form of investment companies with shares that can be purchased
- Holds on to a portfolio of securities in line with a policy and objective
- Usually focus on a single strategy and time horizon, rather than focusing on utilizing many strategies at once
- *Open-Ended* funds are purchased (and sold) directly from (and to) the mutual fund. They're purchased (and sold) at the value of the net assets standing behind each share, where the *net asset value* is determined once a day, at a stated time. 
- *Closed-Ended* funds sell a predetermined number of shares in the fund, where the proceeds (minus the cost) are taken to purchase the underlying assets. Owning shares in a closed-end fund is like owning a share in a corporation, but the assets of the corporation are equity and credit securities. The shares of a closed-end fund tend to sell at a discount or premium to their net asset value due to the perceived quality of management and certain tax liabilities. 
- Charges moderate fees
- Can be actively or passively managed

###### Hedge Funds
- Actively managed
- Uses a wider range of strategies that aren't available to public investment schemes
- Can opt to invest in esoteric assets that are difficult to value or are illiquid
- Requires a high minimum investment or net worth
- Usually targets wealthy investors or those with specific accreditation
- Private and doesn't accept funds from the public
- Hedge fund compensation usually includes a singe-digit percent management fee and a double-digit incentive fee. The incentive fee usually only applies if the fund meets a return threshold
- Highly illiquid and requires investors to keep their funds locked in for relatively long periods of time
- Not as strictly regulated by the government as opposed to public investment schemes
- The managers and executives themselves are usually investors and have a major stake in the enterprise
- Returns are based on the ability of the manager to make returns regardless of market conditions

###### Private Equity
- Actively managed
- Focuses on private and assets not listed on public exchanges
- Caters to wealthy investors and institutions
- Esoteric fee structure
- Illiquid and requires investors to keep their cash locked in for long periods

###### Pension Funds
- Catered towards employees for retirement savings, and therefore, aren't open to investment for the public
- More common in the public than private sector
- Uses a wide variety of assets and strategies to make returns 
- Very long time horizon
- Pension guarantee is based on salary and years of service
- Early withdrawals are usually impossible
- Inflation protection is usually poor, leading to a decline in purchasing power over the years

###### Sovereign Wealth Funds
- State-owned investment vehicles
- Invests primarily in assets located in the home country, but can also include assets outside of the home state
- Not open to the public, with the government being the only entity who can invest
- Aims to boost the host country's economy through strategic investments
- Uses a wide variety of investment strategies and assets
- Funds are often drawn from surplus reserves
- Near-infinite time horizon

---
# Return Characteristics of Assets
One of the core tenets of portfolio management are risk and return, where investors like high return but dislike high risk. The tradeoff between risk and return is complex, requiring a rigorous and un-ambiguous definition of both terms, but a simple way to visualize the relationship with risk and return is through the following diagram:
![[risk_return_matrix.png]]

When discussing the tradeoff between potential risk and return, it's important to understand what is meant by "return." There are many ways to measure return but in most cases, the following definition of return will be used: 
$$
\begin{gather}
\textbf{Definition: Holding Period Return} \\[5mm]
\text{The sum of the change in the market price of a security and } \\
\text{any income received over a period, divided by the price of the security at the start } \\
\text{of the holding period. }
\end{gather}
$$
In describing securities, there are several factors that should affect risk. These included
- The maturity of the investment, where longer investments tend to be riskier
- Risk characteristic and creditworthiness of the issuer or guarantor of the investment
- Nature and priority of the claims the investment has on income and assets
- Liquidity of the instrument and type of economy it's traded in
# Indexes

### Three Classes of Indices
With the many types of assets available for investing in the market, there comes many ways to track their performance. While one manner of tracking their performance is through measuring returns, this method of tracking falls short for understanding the evolution of their asset prices changing overtime, especially when multiple assets are tracked together as a whole. Therefore, better means of tracking the evolution of asset prices are required. When tracking the performance of an asset or group of assets, their performance can be measured in the form of an *index*. Indices can be categorized along four primary structural dimensions: 
1. **Weighting Methodology**
2. **Mathematical Aggregation**
3. **Underlying Asset Class Coverage**
4. **Cash-Flow Accounting**

$$
\begin{gather}
\textbf{Definition: Index} \\[5mm]
\text{An index represents a standardized and quantifiable proxy for measuring the} \\
\text{continuous price or tota return dynamics of a defined basket of financial securities. } \\
\end{gather}
$$

The weight $w_{i,t}$ assigned to constituent security $i$ at time $t$ dictates how idiosyncratic price shocks transmit to aggregate index performance. Broadly speaking, there're three main types of indices: *Price-weighted, value-weighted, and Equal-Weighted*
###### Price-Weighted Index
$$
\begin{gather}
\textbf{Definition: Price-Weighted Index} \\[5mm]
\text{If } P_{i,t} \text{ is the price of an asset, then the individual weight of each} \\
\text{asset is measured as } \\[2.5mm]
w_{i,t} = \frac{P_{i,t}}{\sum^N_{j=1} P_{j,t}} \\[2.5mm]
\text{The index level } I_{t} \text{ at time } t \text{is expressed as an adjusted advisor that absorbs corporate} \\
\text{actions such as stock splits, reverse splits, and constituent replacements: } \\[2.5mm]
I_t = \frac{\sum_{i=1}^N P_{i,t}}{D_t}
\end{gather}
$$
One notable characteristic of a price-weighted index is that a higher-priced asset exerts a disproportionate influence on total performance regardless of the asset's underlying enterprise value. 

###### Value-Weighted Index
$$
\begin{gather}
\textbf{Definition: Value-Weighted Index} \\[5mm]
\text{If } P_{i,t} \text{ is the price of an asset and } Q_{i,t} \text{ is the total number of units of the asset in the economy, } \\
\text{then the individual weight of each asset is measured as} \\[2.5mm]
w_{i,t} = \frac{P_{i,t} \, Q_{i,t}}{\sum_{j=1}^N P_{j,t} \, Q_{j,t}} \\[2.5mm]
\text{The index relative to a base data value } I_{0} \text{ is } \\[2.5mm]
I_t = \frac{\sum_{i=1}^N P_{i,t} \, Q_{i,t}}{\sum_{i=1}^N P_{i,0} \, Q_{i,0}} \times I_0
\end{gather}
$$
This index has three primary characteristics: 
1. This form of indexing is macroconsistent because it reflects aggregate investor holdings in equilibrium. However, *concentration risk* can emerge from when a large asset dominates the index weight. 
2. This excludes closely-held assets, such as government holdings and insider stakes, to prevent market distortions during passive replication. 
3. Can be used to implement upper limits on single-asset weights to satisfy regulatory diversification constraints for collective investment schemes. 

###### Equal-Weighted (Unweighted) Indices
$$
\begin{gather}
\textbf{Definition: Equal-Weighted Indices} \\[5mm]
\text{An index where every asset is assigned an identical portfolio weight},  \\
\text{where } w_{i,t} = \frac{1}{N} \text{at each balancing interval. }
\end{gather}
$$
This is useful for de-emphasizing securities with large weights and amplifies exposure to smaller entities relative to capitalization weighting. This form of indexing requires periodic portfolio rebalancing, including higher transaction turnover. 

### Classification by Mathematical Aggregation 
In the architecture of index construction and quantitative benchmark design, the choice of aggregation scheme is a fundamental structural decision. It dictates not only how constituent price shocks propagate through the index, but also what economic or mathematical reality the benchmark represents. There are two main ways of aggregation across modern index construction: *Arithmetic mean compounding* and *geometric averaging*. 

###### Arithmetic Averaging
$$
\begin{gather}
\textbf{Definition: Arithmetic Averaging} \\[5mm]
\text{Measures the additing relative performance of constituent security } \\
\text{prices or total capitalization of an asset across a single period. } \\
\text{The index value at a specific time } t \text{ is defined as 
} \\[2.5mm]
I_{t} = I_{t-1} \cdot \left(\sum^N_{i=1} w_{i,t} \frac{P_{i,t}}{P_{i,t-1}}\right)
\end{gather}
$$
Arithmetic value-weighted indices provide an accurate representation of aggregate market value and total changes in sectoral wealth over time. This is critical in value-weighted indices, where arithmetic averaging preserves direct proportional mapping to aggregate market capitalization and total corporate wealth. Arithmetically averaged value-weighted indices are the only benchmarks that're macroconsistent. Macroconsistency guarantees that all market participants can hold the index portfolio simultaneously in aggregate equilibrium without forcing artificial trade flows. (see [[Chapter 2 - Expected Value|arithmetic averaging]]) for more information)

###### Geometric Averaging
$$
\begin{gather}
\textbf{Definition: Geometric Averaging} \\[5mm]
\text{Measures relative performance via multiplicative compounding across } \\
\text{constituent price relatives. It calculates the } N\text{th root of the product of } \\
\text{relative price changes. } \\[2.5mm]
 I_t = I_{t-1} \times \left( \prod_{i=1}^N \frac{P_{i,t}}{P_{i,t-1}} \right)^{\frac{1}{N}}
\end{gather}
$$
This means of measuring the average down-weights high-growth assets and overweights slower-growth assets, systematically understating true long-term price appreciation relative to arithmetic measures. This method of averaging incorporates continuous rebalancing or substitution. 