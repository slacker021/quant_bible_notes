---
dg-publish: true
---
There is a special [[Chapter 2 - Elementary Set Theory|subset]] of the economy dedicated to trading [[Chapter 2 - Financial Instruments and Securities|financial securities]] and other instruments. Mathematically, this can be modeled as an adapted [[Chapter 1 - Vector Space of Linear Maps|vector]] or [[Chapter 1 - Measurable Spaces|probability space]]: 
$$
\begin{gather}
\textbf{Definition: Financial Market} \\[5mm]
\text{Let }(\Omega, \mathcal{F}, \{\mathcal{F}_t\}_{t \in [0,T]}, \mathbb{P}) \text{ be a filtered probability space satisfying} \\ \text{ the usual conditions of right-continuity and completeness, where } \\[2mm]
\Omega \text{ is the sample space of all possible future states of the world, } \\[2mm]
\mathcal{F }\text{ is the global } \sigma\text{-algebra of verifiable economic events up to time horizon } T,  \\[2mm]
\{\mathcal{F}_t\}_{t \in [0,T]} \text{is a filtration representing the monotonic flow of market information revealing itself} \\[2mm]
\text{over time, and } \mathbb{P} \text{ is the real-world (physical) probability measure governing state occurences. }
\end{gather}
$$
The fundamental transaction that occurs in these markets is *trading*, which can be done by initiating *orders*. 

---
# Primary and Secondary Markets
Not all markets are made equal, with most markets being classified as *primary* or *secondary* markets. While both markets provide an avenue for trading activity and deals to be made, both have distinct roles that allow the whole financial market to function smoothly. 

### Similarities
On the surface, both types of markets are similar: 
- Both markets deal with the exact same underlying financial securities. 
- Both markets operate under strict regulatory frameworks designed to protect investors, ensure fair disclosure, and maintain market integrity. Without regulatory frameworks and guardrails in place, no one would wanna invest in the markets. 
- Both types of markets are dependent on another, where a feedback loop is formed. 
- The *information efficiency*, which is how fast and smoothly information reaches the market, of the secondary market directly impacts the primary market. Issuers looking to issue securities in the primary market mainly rely on the consensus prices established by trading in the secondary market. 

### Primary Markets
The defining characteristic of the primary market is that **funds flow directly from investor to issuer:**
- The primary market is the avenue for the establishing of newly-created and listed securities. 
- Because the issuer is selling created securities, this market provides a direct infusion of cash to the issuing entity, facilitating actual capital formation and *allocative efficiency* in the economy. 
- Deals exclusively with **newly created** securities being offered to the public or placed privately for the very first time. 
- The primary market, at least in theory, enables capital to be raised efficiently such that available funds in the economy are directed to the borrowers and enterprises that'll make the most productive use of them. 
- Transactions are primarily facilitated by *investment banks* or *underwriters*, which are entities who advise the issuer, underwrite (purchase) the securities, and distribute them to the public. Securities may be sold through public offerings, private placements to institutional investors, auctions (which is common for government bonds), or preemptive rights issues. 
- In the case of equities (but this could be applied to other instruments), primary markets provide an avenue for *initial public offerings* (IPOs). 

### Secondary Markets
The defining characteristic of the secondary market is that the **original issuer receives no funds from the transaction:**
- Assets in the secondary market simply change hands with other market participants, where cash flows directly from the buyer of the asset to the seller. 
- Deals exclusively with **existing or already-issued** securities. 
- Provides **liquidity and price discovery**, which gives investors the ability to quickly reverse an investment for cash and provides continuous transparent information regarding the consensus value of an asset. 
- Reduces search and transaction costs associated with finding a *counterparty*. 
- Transactions are facilitated by *brokers and dealers (market makers)*. 
- *Order-driven* secondary markets involves buyers and sellers being matched directly, such as in an *auction market.*
- *Quote-driven* markets involve market makers trading from their own inventory. Market makers profit from the *bid-ask* spread, which is the range between the buying and selling prices offered by a security. The *bid* price is the highest price on the market that an investor is willing to pay for a security while the *ask* price is the lowest price on the market that an investor is willing to sell a security. 

### Call or Continuous
Depending on the type of market that the investor is operating in, their orders may be matched at different time intervals. 

###### Call Auction Market
A *call auction* is a trading mechanism where buyers and sellers submit their orders to buy or sell assets at specific prices: 
- These orders are collected over a set period and then executed at a price that best matches supply and demand.
- Call auctions help determine prices by aggregating orders to increase liquidity and reduce transaction costs.
- Used worldwide to facilitate fair trading. 
- Call auction rules vary by exchange. 
- In a call auction, buyers set a max price at which they purchase the assets and sellers set a minimum price at which they are willing to sell assets.
- The buy and sell orders for a specific security are executed at specific times during a trading session. 
- The *auctioneer* is responsible for soliciting buy and sell orders that they then match supply with demand. 
- Increases liquidity and reduces transaction costs. 
- Doesn't allow for market orders. 
- Most market openings function in this manner. 
###### Continuous Trading
- Immediate execution
- Facilitates all orders as rapidly as possible during regular trading hours. 
- Most common in secondary markets.
- Requires market makers for maximum liquidity.
- Works for market orders

### Market Intermediation
Most market participants don't directly trade in the market as doing so requires them to have a seat on the exchange, which is expensive. Furthermore, this requires finding a corresponding buyer or seller to do the deal with, which is tedious to do manually. Instead, participants tend to rely on **brokers and market makers** to make trading easier. Both of these play a critical role in the markets but also have vastly different roles. 

###### Broker
- Individual or firm that acts as an intermediary between an investor and a securities exchange. 
- Charges fees or commissions for their services. 
- *Full-service* brokers provide research, investment plans, market intelligence, along with other services. They may also cross-sell other financial products and services that their brokerage firm offers, which is ideal for offering private clients a more tailored solution. 
- *Discount* brokers charge little or no fees but lack many of the services that full-service brokers are offering. 
- Most brokers are now online, which means orders are made over distributed computer networks. 
- Must be registered with local financial regulatory authorities to be licensed to deal with clients. 
- They merely hold the assets on behalf of their clients but don't actually own them. 

###### Market Maker
Market makers actively quote two-sided markets in a particular security, providing bids and offers (asks) along with the market size of each: 
- Provides liquidity and profits from the difference in the bid-ask spread. 
- They may trade for their own accounts, which are known as *principal trades*. 
- Designated market makers have exclusive responsibilities for specific securities, ensuring orderly and fair trading. 
- A broker may also be a market maker. 
- A market maker may be an individual trader or large institution, with most being large institutions because they need to handle large trading volumes. 
- Must be continuously quoting prices, volume at which they're willing to trade, as well as the frequency of time they'll quote at the best bid and best offer prices. 
- Must be ready for any market condition at any time so as to keep facilitating smooth transactions. 
- Compensated for the risk of holding securities that may decline in value after they're purchased from sellers and before they're sold to buyers. 

# Market Efficiency
_Market efficiency_ broadly refers to how effectively a financial market aggregates information, minimizes friction, and allocates scarce capital across competing economic uses. In quantitative finance and economic theory, market efficiency is categorized into three interrelated dimensions: _allocative efficiency_, _productive (operational) efficiency_, and _informational efficiency_.

### Allocative Efficiency
Allocative efficiency concerns the dynamic distribution of financial resources to their most productively beneficial opportunities across time and states of the world: 
$$
\begin{gather}  
\textbf{Definition: Allocative Efficiency (Pareto Optimality)} \\[5mm] 
\text{Let } x^i(\omega) \in \mathbb{R}^n_+ \text{ denote the state-contingent asset allocation or consumption vector} \\[2mm]
\text{of agent } i \in {1, \dots, I} \text{ given state } \omega \in \Omega \text{ on a filtered probability space }  \\[2mm]
(\Omega, \mathcal{F}, {\mathcal{F}_t}_{t \ge 0}, \mathbb{P}). \ \text{An allocation } {x^i(\omega)}_{i=1}^I \text{ is allocatively efficient (Pareto optimal) 
if there exists} \\[2mm]
\text{no alternative feasible allocation } {\hat{x}^i(\omega)}_{i=1}^I \text{ such that} \\[3.5mm] \mathbb{E}^{\mathbb{P}}\left[ U^i(\hat{x}^i) \right] \ge \mathbb{E}^{\mathbb{P}}\left[ U^i(x^i) \right] \quad \forall i \in {1, \dots, I} \\[3.5mm] \text{with a strict inequality holding for at least one economic agent } k: \\[3.5mm] \mathbb{E}^{\mathbb{P}}\left[ U^k(\hat{x}^k) \right] > \mathbb{E}^{\mathbb{P}}\left[ U^k(x^k) \right]  
\end{gather}
$$


### Productive (Operational) Efficiency
Productive efficiency measures the transaction cost structure and operational friction involved in executing financial transfers and market-making operations: 
$$
\begin{gather} 
 \textbf{Definition: Productive (Operational) Efficiency} \\[5mm] \text{Let } C(v) \text{ denote the total transaction friction cost incurred when executing a trading volume } v, \\[2mm]
\text{incorporating explicit fees, bid-ask spreads } \mathcal{S}_{\text{bid-ask}}, \text{ and price impact } \Delta P(v): \\[3.5mm] C(v) = \text{Commissions} + v \cdot \left( \frac{P_{\text{ask}} - P_{\text{bid}}}{2} \right) + f(\Delta P(v)) \\[3.5mm] \text{A financial market mechanism is productively efficient if, given technology and market architecture,} \\ \text{the expected transaction cost per unit volume is minimized across all feasible market mechanisms:} \\[3.5mm] \min_{\text{Mechanism}} \mathbb{E}\left[ C(v) \right] \end{gather}
$$

### Informational Efficiency
$$
\begin{gather}
\textbf{Definition: Informational Efficiency} \\[5mm]
\text{Let } \mathcal{H}_t \text{ denote the information filtration available to market participants at time } t, \text{ and let } S_j(t)  \\[2mm]
\text{be the price process of asset } j. \text{ A market is informationally efficient with respect to } \mathcal{H}_t \text{ if the } \\[2mm]
\text{discounted price process } \frac{S_j(t)}{S_0(t)} \text{ follows a martingale under the equivalent risk-neutral measure } \mathbb{P}:  \\[3.5mm]
S_j(t) = \mathbb{E}^{\mathbb{P}} \left[ \frac{S_0(t)}{S_0(T)} S_j(T) ,\Bigg|, \mathcal{H}_t \right]  \\[3.5mm]
\text{Equivalently, under measure } \mathbb{P}, \text{ the excess return process } e_{j, t+1} = R_{j, t+1} - r_{j, t+1}  \\[2mm]
\text{satisfies a fair game: } \\[3.5mm] 
\mathbb{E}^{\mathbb{P}}\left[ e_{j, t+1} \mid \mathcal{H}_t \right] = 0
\end{gather}
$$
Informational efficiency is categorized into three distinct regimes based on the scope of the information set $\mathcal{H}_t$:
- **Weak-Form Efficiency:** $\mathcal{H}_t$ consists solely of past price and volume histories $\Phi_t^{\text{past}}$. Past price patterns cannot be utilized to forecast future excess returns.
- **Semi-Strong Form Efficiency:** $\mathcal{H}_t$ encompasses all publicly available information $\Phi_t^{\text{public}}$, including earnings announcements, financial statements, and macroeconomic releases. Prices adjust instantaneously to public news.
- **Strong-Form Efficiency:** $\mathcal{H}_t$ contains all public and private (insider) information $\Phi_t^{\text{all}}$. No economic participant can systematically earn excess risk-adjusted returns.

---
# Order Types
There are many order types that a market participant can initiate so as to complete a transaction. Investors can use different order types to complement their trading strategy, but many of the more complex order types are combinations of simpler order types. Below are the most common and simplest order types: 

### Market Orders 
A _market order_ directs the executing broker or trading system to buy or sell a security immediately at the best currently available price: 
- **Bid Price:** The highest price a buyer in the market is willing to pay.
- **Ask (Offer) Price:** The lowest price a seller in the market is willing to accept.
- **Bid-Ask Spread:** The numerical difference between the ask price and the bid price. The spread represents a fundamental component of transaction friction.
- Preferable for purchasing large units of securities that are highly traded (liquid).
- Completed nearly instantaneously at a price very close to the latest posted price the investor can see. 
- Not ideal for securities that have low liquidity since the price the investor can purchase or sell it for will likely be far from the last price displayed. 

###  Limit Orders
A _limit order_ sets a specific price boundary representing the worst acceptable execution terms: 
- A **buy limit order** specifies a maximum purchase price. 
- A **sell limit order** specifies a minimum sale price. 
- Execution of a limit order is uncertain as market prices may not reach the specified limit price. 
- Provides greater control for the investor
- Ideal for securities that have low liquidity, where the investor can time the sale for the next price upswing. In the case of selling, the investor can time the next downswing. 

### Stop Orders
A _stop order_ remains inactive until a predetermined _stop price_ is breached by market trades. Upon reaching the stop price, the order transforms into a standard market order: 
- **Stop-Loss Order:** Converts to a market sell order if prices drop to or below the stop price, utilized to limit downside risk.
- **Stop-Buy Order:** Converts to a market buy order if prices rise to or above the stop price, frequently used to limit losses on *short* positions.
- Opposite of a limit order
- Versatile as it's meant for limiting losses or taking advantage of market breakouts. 
- Critical for allowing investors to limit their risk if they aren't keeping an active eye on the market. 
- May not execute at the exact price, which is known as *slippage.*

### Time-in-Force Instructions
In addition to the three basic order types the investor can execute, they can also specify how long the execution can be valid for: 
- **Day Order:** Automatically cancels if unexecuted by the close of the current trading session.
- **Good-Til-Canceled (GTC):** Remains active across multiple trading sessions until explicitly canceled or executed.
- **Fill-or-Kill (FOK):** Requires immediate full execution or immediate cancellation.

# Margin 
*Margin* is money borrowed from a broker to purchase securities, which involves using existing assets as *collateral*. This increases both potential gains and losses. Using margin involves the creation of a **margin account**, which must maintain a minimum balance to continue trading. Failing to maintain the margin account's minimum leads to a *margin call*, which requires the investor to restore the cash supply to the minimum amount. Using margin also comes with interest, which increases investment costs. Margin trading is generally used for short-term investing due to its risks and costs.

### Margin Long Positions
For *long positions*, _margin_ is defined as the proportion of total asset market value provided by equity:
$$\begin{align} 
&\textbf{Definition: Margin on Long Position} \\[5mm] \text{Margin} & = \frac{\text{Market Value of Assets} - \text{Amount Borrowed}}{\text{Market Value of Assets}}  \\[2mm]
& = \frac{\text{equity}}{\text{Market value of assets}}
\end{align}$$

The long position of a margin position has three main components
- **Initial Margin:** The minimum percentage of equity required at the time of purchase, established by regulatory authorities or brokerage institutions.
- **Maintenance Margin:** The minimum allowable equity percentage required continuously during the holding period.
- **Margin Call:** A demand issued when position equity drops below the maintenance threshold, requiring the investor to deposit additional cash or collateral, or face forced liquidation.

> [!info]+ Remark 1
> Maintenance Price Threshold Let $P$ represent the share price at which a margin call occurs for a long position of $N$ shares purchased at price $P_0$ with borrowed capital $L$ under a maintenance margin requirement $M_m$:
> 
> $$M_m = \frac{N P - L}{N P} \implies P = \frac{L}{N(1 - M_m)} \tag{1}$$

>[!info]+ Remark 2
>As a point of clarification, the margin account of the trader isn't debited nor credited. The only thing that changes in the margin account's value is the equity. However, the trader can opt to fund or withdraw funds from the margin account. With the former, the increased sensitivity to price changes with higher margin amounts enables the investor to increase capital flow to their account should the price move to favor their position. 
### Margin Short Sales
For short positions, margin is calculated relative to the market value of the shorted securities:
$$
\begin{align} 
& \textbf{Definition: Margin on Short Position} \\[5mm] 
\text{Margin} &= \frac{\text{Total Account Assets} - \text{Market Value of Short Securities}}{\text{Market Value of Short Securities}}  \\[2mm]
&= \frac{\text{Equity}}{\text{Market Value of Short Securities}}
\end{align}
$$

### Intraday Margin Behavior
As the trading session goes on, the balance in the margin account fluctuates depending on the value of the trader's position. Account equity fluctuates dynamically, causing the account's current margin percentage to move up or down in real time. 

###### Margin Fluctuation for Long Positions
In a **long position**, an investor purchases securities using a combination of cash (equity) and borrowed funds (a loan from the broker): 
- **When Asset Price Increases ($\uparrow$):**
    - The cash per unit value of the assets increases while the borrowed loan amount remains constant.
    - Net worth (equity) increases cash per unit with the asset price.
    - The account margin percentage **increases**. If the equity rises sufficiently above the initial margin requirement, it creates excess equity, which can be withdrawn or used as collateral to purchase additional securities.
- **When Asset Price Decreases ($\downarrow$):**
    - The cash per unit value of the assets decreases while the loan balance stays fixed.
    - Net worth (equity) decreases cash per unit with the price decline.
    - The account margin percentage **decreases**. If the price falls to or below the maintenance price threshold $P$, a margin call is triggered:
	$$
    P = \frac{L}{N(1 - M_m)} \tag{2}
    $$
        _(where $L$ is the loan amount, $N$ is the number.

###### Margin Fluctuations for Short Positions
In a short sale, an investor borrows securities from a lender to sell them immediately in the market, creating an obligation to buy back (*cover*) the securities in the future: 
- **Cash Credit Balance (Fixed):** At execution, the account receives a cash credit consisting of the proceeds from the short sale _plus_ the initial margin deposited by the investor. This total asset cash balance remains fixed.
- **Short Liability (Fluctuating):** The liability is the market value of the borrowed securities that must be repurchased.
- **Equity Fluctuation:** Equity ($\text{Fixed Cash Assets} - \text{Market Value of Short Liability}$) fluctuates inversely with the value of the underlying securities.
    - **When Price Falls ($\downarrow$):** The cost to repurchase the securities drops (liability decreases). Since cash assets are fixed, account equity **increases** (unrealized profit), driving up the short margin percentage.
    - **When Price Rises ($\uparrow$):** The cost to repurchase the security rises (liability increases). Equity drops per cash unit, driving down the short margin percentage. If the price rises too high, equity falls below the maintenance margin requirement, triggering a margin call.

