---
dg-publish:
---
The evaluation of [[Chapter 2 - Financial Instruments and Securities|financial securities]] requires a rigorous mathematical framework to quantify the trade-off between expected outcomes and uncertainty. _Modern Portfolio Theory_ (MPT), originally pioneered by Harry Markowitz, formalizes the process of asset selection by treating investment decisions as a mean-variance optimization problem within a defined [[probability space]]. Rather than assessing the risk of individual assets in isolation, the theory focuses on the covariance structure of the entire portfolio, demonstrating that appropriately structured combinations of assets can fundamentally alter the overall risk-return profile. 

---
# The Opportunity Set Under Risk
The fundamental premise of portfolio theory is that economic agents operate under conditions of risk, meaning the future payoff of any given asset must be described by a set of outcomes and their associated probabilities. This requires the establishment of summary statistical metrics to evaluate the opportunity set available within a [[Chapter 3 - Financial Markets|financial market]].

### Expected Return and Dispersion
The most frequently utilized attributes of an asset's return distribution are its measure of central tendency and its measure of dispersion. The _expected return_ is the probability-weighted average of all possible future returns: 
$$\begin{gather} \textbf{Definition: Expected Return of an Asset} \\[5mm] \text{Let } R_{ij} \text{ denote the } j\text{-th possible return for security } i, \text{ and } P_{ij} \text{ be the} \\ \text{probability of that return occurring. The expected return } \overline{R}_i \text{ is defined as} \\[2.5mm] \overline{R}_i = \mathbb{E}[R_i] = \sum_{j=1}^{M} P_{ij} R_{ij} \end{gather}
$$

To quantify the uncertainty or risk associated with this expected return, the [[variance (or standard deviation) of the return distribution]] is utilized. Variance measures the average squared deviation of the possible returns from the expected return: 
$$
\begin{gather} \textbf{Definition: Variance of an Asset} \\[5mm] \text{The variance } \sigma_i^2 \text{ of the return on asset } i \text{ is calculated as:} \\[2.5mm] \sigma_i^2 = \mathbb{E}[(R_i - \overline{R}_i)^2] = \sum_{j=1}^{M} P_{ij} (R_{ij} - \overline{R}_i)^2 \end{gather}
$$

### Portfolio Expected Return and Variance
An investor rarely holds a single asset. The return on a portfolio of assets is a weighted average of the returns on the individual assets contained within it: 
$$
\begin{gather} \textbf{Definition: Expected Return}  \\[5mm]  \text{Let } X_i \text{ denote the fraction of the total portfolio value invested in asset } i. \text{ The expected} \\ \text{return on the portfolio } \overline{R}_p \text{ is} \\[2.5mm] \overline{R}_p = \sum_{i=1}^{N} X_i \overline{R}_i \end{gather}
$$

While the expected return of a portfolio is a simple linear combination of its constituents, the risk of a portfolio is structurally more complex. It depends heavily on the *covariance*, which measures the directional relationship between the returns of the constituent assets: 
$$
\begin{gather} \textbf{Definition: Portfolio Variance} \\[5mm] \text{Let } \sigma_{ij} \text{ denote the covariance between the returns of asset } i \text{ and asset } j. \\ \text{The variance of a portfolio } \sigma_p^2 \text{ containing } N \text{ assets is given by:} \\[2.5mm] \sigma_p^2 = \sum_{i=1}^{N} X_i^2 \sigma_i^2 + \sum_{i=1}^{N} \sum_{\substack{j=1 \ j \neq i}}^{N} X_i X_j \sigma_{ij} \end{gather}
$$

> [!info]+ Remark: Correlation and Covariance 
> The covariance $\sigma_{ij}$ can be decomposed into the standard deviations of the two assets and their _correlation coefficient_ $\rho_{ij}$: 
> $$
> \begin{gather} \sigma_{ij} = \rho_{ij} \sigma_i \sigma_j \tag{1} \end{gather}
> $$
> The correlation coefficient is bounded such that $-1 \le \rho_{ij} \le 1$. The magnitude and sign of $\rho_{ij}$ are the primary determinants of the portfolio's total variance.



### The Principle of Diversification
The mathematical architecture of portfolio variance reveals an elegant property: as the number of assets $N$ increases, the contribution of individual asset variances $\sigma_i^2$ to the total portfolio variance approaches zero, while the contribution of the covariance terms $\sigma_{ij}$ comes to dominate. This demonstrates that the risk of a well-diversified portfolio is dictated almost entirely by the average covariance between the securities it contains, not their individual variances.

If assets are not perfectly positively correlated ($\rho_{ij} < 1$), combining them into a portfolio reduces the overall standard deviation to a level strictly lower than the weighted average of the individual standard deviations.

> [!example]+ Example: Two-Asset Diversification 
> Consider two assets, $A$ and $B$, each with a standard deviation of $20\%$. If half the portfolio is invested in each ($X_A = 0.5, X_B = 0.5$), and the assets are perfectly uncorrelated ($\rho_{AB} = 0$), the portfolio variance is calculated as
> $$\sigma_p^2 = (0.5)^2(0.20)^2 + (0.5)^2(0.20)^2 + 2(0.5)(0.5)(0)(0.20)(0.20) = 0.02 \tag{2}$$
> The portfolio standard deviation is $\sqrt{0.02} \approx 14.14\%$. This is significantly lower than the $20\%$ risk of either asset held in isolation, structurally illustrating the mathematical benefit of diversification.


---
# Delineating Efficient Portfolios
Having established the risk and return properties of asset combinations, the objective is to identify the optimal portfolios that rational, utility-maximizing economic agents would choose. It is inherently assumed that investors exhibit risk aversion; they require higher expected returns to justify higher levels of risk, and seek minimum variance for any targeted level of expected return.

### The Markowitz Efficient Frontier
By evaluating all possible combinations of available risky assets, an _opportunity set_ (or feasible set) is constructed in mean-variance space. The leftward, uppermost boundary of this geometric set defines the most efficient portfolios mathematically possible: 
$$
\begin{gather} \textbf{Theorem: The Efficient Frontier} \\[5mm] \text{A portfolio is considered Markowitz-efficient if no other feasible portfolio exists} \\ \text{that offers a higher expected return for the same or lower variance, and no other} \\ \text{portfolio offers a lower variance for the same or higher expected return. The focus of} \\ \text{all such optimal portfolios forms the efficient frontier}. \end{gather}
$$
(see [[Proof of the Efficient Frontier|proof]])

The geometric shape of the efficient frontier is strictly convex toward the vertical (expected return) axis. This convexity is a direct mathematical consequence of imperfect correlation among the underlying assets, guaranteeing that interior portfolios can always be combined to produce a boundary portfolio with a superior risk-return profile.

### The Risk-Free Asset and the Capital Market Line
The classic Markowitz frontier deals exclusively with risky assets. A fundamental shift occurs when a _risk-free asset_ (such as a short-term government treasury bill) is introduced to the market, allowing the investor to lend or borrow capital at a guaranteed rate $R_F$.

Because the risk-free asset has a variance of zero and a covariance of zero with all other assets, combinations of the risk-free asset and any risky portfolio form a straight line in mean-variance space.
$$
\begin{gather} \textbf{Theorem: The Capital Market Line (CML)} \\[5mm] \text{When riskless lending and borrowing at rate } R_F \text{ are permitted, the efficient frontier} \\ \text{becomes a straight line originating at } R_F \text{ and tangent to the risky-asset efficient frontier.} \\ \text{This line dominates all other portfolios and is mathematically defined by the equation} \\[2.5mm] \overline{R}_p = R_F + \frac{\overline{R}_M - R_F}{\sigma_M} \sigma_p \end{gather}
$$

In this equation, $M$ denotes the _tangency portfolio_ (often representing the theoretical market portfolio). **The existence of the Capital Market Line implies that the optimal combination of risky assets is identical for all investors, regardless of their individual risk tolerance.** An investor merely adjusts their position along the CML by altering the proportion of wealth allocated to the risk-free asset versus the tangency portfolio $M$.

> [!warning]+ Warning: Assumptions of the CML 
> The derivation of the Capital Market Line relies on strict neoclassical assumptions, including homogenous expectations among all market participants, the complete absence of market frictions (such as taxes or transaction costs), and the ability to borrow and lend limitless capital at the exact same risk-free rate. If these normative conditions fail to hold, the linear nature of the frontier degrades and requires more complex equilibrium adjustments.

