---
dg-publish:
---
In the presence of economic uncertainty, choice theory requires mapping financial securities into an evaluation framework governed by probability distributions. Following the institutional mechanisms of [[Chapter 3 - Financial Markets|financial markets]] and the axiomatic utility preferences formulated in [[Chapter 1 - The Theory of Choices|the theory of choices]], an investor evaluates uncertain future wealth through the statistical characteristics of the available investment opportunity set. 

Mathematically, let the investment horizon be defined across a single period $t \in [0, 1]$ on a probability space $(\Omega, \mathcal{F}, \mathbb{P})$, where asset returns represent real-valued random variables.

---
# Expected Return of Risky Assets

### Determining the Average Outcome
The central tendency of an uncertain asset return is characterized by its expectation under the physical probability measure $\mathbb{P}$: 
$$
\begin{gather}
\textbf{Definition: Asset Rate of Return} \\[5mm]
\text{Let } P_{i,0} \text{ be the current purchase price of asset } i \text{ at time } t = 0, \text{ and let } P_{i,1}(\omega) \text{ and } D_{i,1}(\omega) \\
\text{denote the terminal price and cash dividend/yield at time } t = 1 \text{ under state } \omega \in \Omega. \\
\text{The rate of return random variable } R_i: \Omega \to \mathbb{R} \text{ is defined as:} \\[2.5mm]
R_i(\omega) = \frac{P_{i,1}(\omega) - P_{i,0} + D_{i,1}(\omega)}{P_{i,0}}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Expected Return (Discrete State Space)} \\[5mm]
\text{Let } \Omega = \{\omega_1, \omega_2, \dots, \omega_M\} \text{ be a finite partition of economic states with associated} \\
\text{probabilities } p_m = \mathbb{P}(\{\omega_m\}) \text{ satisfying } p_m \ge 0 \text{ and } \sum_{m=1}^M p_m = 1. \\
\text{The expected return of asset } i, \text{ denoted } \bar{R}_i \text{ or } \mathbb{E}[R_i], \text{ is:} \\[2.5mm]
\bar{R}_i = \mathbb{E}[R_i] = \sum_{m=1}^M p_m R_{im}
\end{gather}
$$

$$
\begin{gather}
\textbf{Proposition: Linearity of Asset Expectations} \\[5mm]
\text{Let } \{R_i\}_{i=1}^N \text{ be a collection of asset return random variables on } (\Omega, \mathcal{F}, \mathbb{P}) \\
\text{and let } \{X_i\}_{i=1}^N \in \mathbb{R} \text{ be arbitrary deterministic portfolio weights. Then:} \\[2.5mm]
\mathbb{E}\left[ \sum_{i=1}^N X_i R_i \right] = \sum_{i=1}^N X_i \mathbb{E}[R_i] = \sum_{i=1}^N X_i \bar{R}_i
\end{gather}
$$
(see [[Proof of Linearity of Asset Expectations|proof]])

---
# Dispersion of Returns as a Proxy for Risk

### Measures of Dispersion
To quantify the severity of potential deviations from expected outcome, modern portfolio theory relies on the second central moment of the return distribution.

$$
\begin{gather}
\textbf{Definition: Return Variance and Standard Deviation} \\[5mm]
\text{The variance of the return of asset } i, \text{ denoted } \sigma_i^2 \text{ or } \text{Var}(R_i), \text{ measures the} \\
\text{expected squared deviation of returns around their mean:} \\[2.5mm]
\sigma_i^2 = \mathbb{E}\left[ (R_i - \bar{R}_i)^2 \right] = \sum_{m=1}^M p_m (R_{im} - \bar{R}_i)^2 \\[2.5mm]
\text{The standard deviation, denoted } \sigma_i, \text{ is the unique positive square root of variance:} \\[2.5mm]
\sigma_i = \sqrt{\sigma_i^2}
\end{gather}
$$

> [!info]+ Remark: Asymmetric Dispersion Metrics
> While variance treats upside and downside departures symmetrically, investors typically experience disutility strictly from downside realizations. The textbook identifies alternative measures of dispersion:
> 
> $$
> \begin{gather}
> \textbf{Definition: Semi-Variance and Mean Absolute Deviation (MAD)} \\[5mm]
> \text{The semi-variance below the mean } \bar{R}_i \text{ is defined as:} \\[2.5mm]
> S_i^2 = \mathbb{E}\left[ \min(0, R_i - \bar{R}_i)^2 \right] = \sum_{m: R_{im} < \bar{R}_i} p_m (R_{im} - \bar{R}_i)^2 \\[2.5mm]
> \text{The Mean Absolute Deviation (MAD) is defined as:} \\[2.5mm]
> \text{MAD}_i = \mathbb{E}\left[ |R_i - \bar{R}_i| \right] = \sum_{m=1}^M p_m |R_{im} - \bar{R}_i|
> \end{gather}
> $$
> When return distributions are normal, ranking portfolios via semi-variance or MAD yields identical efficient sets to standard variance. Consequently, variance remains the primary analytical proxy for financial risk.

---
# Covariance and Correlation Structures

### The Co-Movement of Risky Assets
The interaction between two uncertain assets cannot be understood through isolated variances; it requires formalizing their joint dispersion: 
$$
\begin{gather}
\textbf{Definition: Covariance} \\[5mm]
\text{Let } R_i \text{ and } R_j \text{ be square-integrable random variables on } (\Omega, \mathcal{F}, \mathbb{P}). \\
\text{The covariance between asset } i \text{ and asset } j, \text{ denoted } \sigma_{ij} \text{ or } \text{Cov}(R_i, R_j), \text{ is:} \\[2.5mm]
\sigma_{ij} = \mathbb{E}\left[ (R_i - \bar{R}_i)(R_j - \bar{R}_j) \right] = \sum_{m=1}^M p_m (R_{im} - \bar{R}_i)(R_{jm} - \bar{R}_j) \\[2.5mm]
\text{Equivalently, expanding the expectation yields:} \\[2.5mm]
\sigma_{ij} = \mathbb{E}[R_i R_j] - \bar{R}_i \bar{R}_j
\end{gather}
$$

$$
\begin{gather}
\textbf{Proposition: Symmetry and Reflexivity of Covariance} \\[5mm]
\text{For any assets } i \text{ and } j: \\[2.5mm]
\text{1. Symmetry: } \sigma_{ij} = \sigma_{ji} \\
\text{2. Reflexivity: } \sigma_{ii} = \mathbb{E}\left[(R_i - \bar{R}_i)^2\right] = \sigma_i^2
\end{gather}
$$
(see [[Proof of Symmetry and Reflexivity of Covariance|proof]])
$$
\begin{gather}
\textbf{Definition: Pearson Correlation Coefficient} \\[5mm]
\text{The correlation coefficient } \rho_{ij} \text{ standardizes covariance by the product of individual volatilities:} \\[2.5mm]
\rho_{ij} = \frac{\sigma_{ij}}{\sigma_i \sigma_j} \implies \sigma_{ij} = \rho_{ij} \sigma_i \sigma_j
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Cauchy-Schwarz Bounds on Correlation} \\[5mm]
\text{For any two non-degenerate asset return random variables } R_i \text{ and } R_j, \\
\text{the correlation coefficient is strictly bounded within the closed interval:} \\[2.5mm]
-1 \le \rho_{ij} \le 1
\end{gather}
$$
(see [[Proof of Cauchy-Schwarz Bounds on Correlation|proof]])

---
# Two-Asset Portfolio Theory

### Portfolio Mechanics
Let an investor construct a portfolio combining two risky assets with weights $X_1$ and $X_2$: 
$$
\begin{gather}
\textbf{Axiom: Capital Budget Constraint} \\[5mm]
\text{Let } X_i \text{ represent the proportion of investable wealth allocated to asset } i. \\
\text{In a fully invested portfolio, the weights satisfy the affine hyper-plane constraint:} \\[2.5mm]
X_1 + X_2 = 1 \implies X_2 = 1 - X_1
\end{gather}
$$

> [!info]+ Remark: Short Sales Constraints
> - **Short Sales Allowed:** $X_i \in (-\infty, \infty)$. A negative weight ($X_i < 0$) indicates a short position, borrowing the security to sell immediately with an obligation to cover later.
> - **Short Sales Prohibited:** $X_i \ge 0$ for all $i$, constraining the weight vector to the unit simplex: $X_1 \in [0, 1]$.

$$
\begin{gather}
\textbf{Theorem: Expected Return and Variance of a Two-Asset Portfolio} \\[5mm]
\text{Let a portfolio } p \text{ consist of asset 1 and asset 2 with weights } X_1 \text{ and } X_2 = 1 - X_1. \\
\text{The expected return of the portfolio is:} \\[2.5mm]
\bar{R}_p = X_1 \bar{R}_1 + X_2 \bar{R}_2 \\[2.5mm]
\text{The variance of the portfolio is:} \\[2.5mm]
\sigma_p^2 = X_1^2 \sigma_1^2 + X_2^2 \sigma_2^2 + 2 X_1 X_2 \sigma_{12} = X_1^2 \sigma_1^2 + X_2^2 \sigma_2^2 + 2 X_1 X_2 \rho_{12} \sigma_1 \sigma_2
\end{gather}
$$
(see [[Proof of Expected Return and Variance of a Two-Asset Portfolio|proof]])
### The Diversification Regime Under Varying Correlation
The geometry of the portfolio possibility curve in $(\sigma_p, \bar{R}_p)$ space is dictated by $\rho_{12}$: 
$$
\begin{gather}
\textbf{Proposition: Extreme Correlation Regimes} \\[5mm]
\text{\textbf{Case 1: Perfect Positive Correlation }} (\rho_{12} = 1) \\
\sigma_p^2 = (X_1 \sigma_1 + X_2 \sigma_2)^2 \implies \sigma_p = X_1 \sigma_1 + X_2 \sigma_2 \quad (X_1, X_2 \ge 0) \\
\text{The risk-return locus forms a straight line in } (\sigma, \bar{R}) \text{ space. No diversification gain exists.} \\[3.5mm]
\text{\textbf{Case 2: Zero Correlation }} (\rho_{12} = 0) \\
\sigma_p = \sqrt{X_1^2 \sigma_1^2 + X_2^2 \sigma_2^2} < X_1 \sigma_1 + X_2 \sigma_2 \quad \forall X_1 \in (0, 1) \\
\text{The locus bows strictly to the left. Total portfolio risk is strictly less than the weighted average risk.} \\[3.5mm]
\text{\textbf{Case 3: Perfect Negative Correlation }} (\rho_{12} = -1) \\
\sigma_p^2 = (X_1 \sigma_1 - X_2 \sigma_2)^2 \implies \sigma_p = |X_1 \sigma_1 - X_2 \sigma_2| \\
\text{The locus forms two linear segments touching the vertical axis } \sigma_p = 0.
\end{gather}
$$
(see [[Proof of Extreme Correlation Regimes|proof]])
$$
\begin{gather}
\textbf{Corollary: Riskless Arbitrage Portfolio Under Perfect Negative Correlation} \\[5mm]
\text{If } \rho_{12} = -1, \text{ there exists a unique allocation } X_1^* \in (0, 1) \text{ that eliminates all portfolio risk } (\sigma_p = 0): \\[2.5mm]
X_1 \sigma_1 - (1 - X_1) \sigma_2 = 0 \implies X_1^* = \frac{\sigma_2}{\sigma_1 + \sigma_2}, \quad X_2^* = \frac{\sigma_1}{\sigma_1 + \sigma_2}
\end{gather}
$$
(see [[Proof of Riskless Arbitrary Portfolio Under Perfect Negative Correlation|proof]])
$$
\begin{gather}
\textbf{Lemma: Two-Asset Minimum Variance Portfolio (MVP)} \\[5mm]
\text{Under general correlation } \rho_{12} < 1, \text{ the allocation } X_1^* \text{ that minimizes total portfolio variance } \sigma_p^2 \\
\text{subject to } X_1 + X_2 = 1 \text{ is given by the first-order condition } \frac{d\sigma_p^2}{dX_1} = 0: \\[2.5mm]
\frac{d}{dX_1}\left[ X_1^2 \sigma_1^2 + (1 - X_1)^2 \sigma_2^2 + 2 X_1(1 - X_1)\sigma_{12} \right] = 0 \\[2.5mm]
\implies 2 X_1 \sigma_1^2 - 2(1 - X_1)\sigma_2^2 + 2(1 - 2X_1)\sigma_{12} = 0 \\[2.5mm]
X_1^* = \frac{\sigma_2^2 - \sigma_{12}}{\sigma_1^2 + \sigma_2^2 - 2\sigma_{12}} = \frac{\sigma_2^2 - \rho_{12}\sigma_1\sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{12}\sigma_1\sigma_2}
\end{gather}
$$

---
# General $N$-Asset Portfolio Formulation

### Algebraic Formulation
When moving from 2 assets to $N$ assets, portfolio return remains linear while portfolio risk incorporates an expanding covariance matrix.

$$
\begin{gather}
\textbf{Definition: General } N\text{-Asset Portfolio} \\[5mm]
\text{Let } \mathbf{X} = [X_1, X_2, \dots, X_N]^T \in \mathbb{R}^N \text{ denote the vector of asset weights satisfying } \mathbf{X}^T \mathbf{1} = 1, \\
\text{where } \mathbf{1} = [1, 1, \dots, 1]^T. \text{ Let } \bar{\mathbf{R}} = [\bar{R}_1, \bar{R}_2, \dots, \bar{R}_N]^T \text{ be the expected return vector,} \\
\text{and let } \mathbf{\Sigma} \in \mathbb{R}^{N \times N} \text{ be the symmetric covariance matrix with entries } \mathbf{\Sigma}_{ij} = \sigma_{ij}. \\[2.5mm]
\text{The expected return of the } N\text{-asset portfolio is:} \\[2.5mm]
\bar{R}_p = \sum_{i=1}^N X_i \bar{R}_i = \mathbf{X}^T \bar{\mathbf{R}} \\[2.5mm]
\text{The variance of the } N\text{-asset portfolio is:} \\[2.5mm]
\sigma_p^2 = \sum_{i=1}^N \sum_{j=1}^N X_i X_j \sigma_{ij} = \sum_{i=1}^N X_i^2 \sigma_i^2 + \sum_{i=1}^N \sum_{\substack{j=1 \\ j \neq i}}^N X_i X_j \sigma_{ij} = \mathbf{X}^T \mathbf{\Sigma} \mathbf{X}
\end{gather}
$$

$$
\begin{gather}
\textbf{Proposition: Decomposition of Variance and Covariance Terms} \\[5mm]
\text{In an } N\text{-asset portfolio variance expansion, the total number of terms is } N^2: \\
\text{1. Exactly } N \text{ terms represent individual variance components } (i = j). \\
\text{2. Exactly } N^2 - N = N(N - 1) \text{ terms represent pairwise covariance components } (i \neq j). \\
\text{By symmetry } (\sigma_{ij} = \sigma_{ji}), \text{ there are } \frac{N(N - 1)}{2} \text{ unique covariance values.}
\end{gather}
$$

---
# The Limits of Diversification

### Systematic vs. Unsystematic Risk
As $N$ expands, the contribution of individual asset variances rapidly decays to zero, while the average covariance dictates portfolio risk.

$$
\begin{gather}
\textbf{Theorem: Asymptotic Diversification Theorem} \\[5mm]
\text{Consider an equally weighted portfolio where } X_i = \frac{1}{N} \text{ for all } i \in \{1, \dots, N\}. \\
\text{Define the average asset variance } \bar{\sigma}^2 \text{ and the average covariance } \bar{\text{Cov}} \text{ as:} \\[2.5mm]
\bar{\sigma}^2 = \frac{1}{N} \sum_{i=1}^N \sigma_i^2, \qquad \bar{\text{Cov}} = \frac{1}{N(N - 1)} \sum_{i=1}^N \sum_{\substack{j=1 \\ j \neq i}}^N \sigma_{ij} \\[2.5mm]
\text{The portfolio variance can be exactly expressed as:} \\[2.5mm]
\sigma_p^2 = \frac{1}{N} \bar{\sigma}^2 + \left(1 - \frac{1}{N}\right) \bar{\text{Cov}} \\[2.5mm]
\text{Taking the asymptotic limit as } N \to \infty \text{ yields:} \\[2.5mm]
\lim_{N \to \infty} \sigma_p^2 = \bar{\text{Cov}}
\end{gather}
$$
(see [[Proof of Asymptotic Diversification Theorem|proof]])
$$
\begin{gather}
\textbf{Corollary: Dichotomy of Financial Risk} \\[5mm]
\text{The total risk of an asset can be partitioned into two orthogonal components:} \\[2.5mm]
\text{\textbf{Total Risk}} = \text{\textbf{Diversifiable (Unique/Idiosyncratic) Risk}} + \text{\textbf{Systematic (Market) Risk}} \\[2.5mm]
\text{1. Diversifiable Risk: } \frac{1}{N} \bar{\sigma}^2 \to 0 \text{ as } N \to \infty. \text{ Risk unique to individual firms} \\
\text{is neutralized through collective diversification.} \\[2.5mm]
\text{2. Systematic Risk: } \bar{\text{Cov}}. \text{ The co-movement generated by macroeconomic factors} \\
\text{cannot be diversified away, defining the irreducible lower bound of portfolio variance.}
\end{gather}
$$
(see [[Proof of Dichotomy of Financial Risk|proof]])

> [!warning]+ Warning: The Fallacy of Zero-Covariance Assumptions
> The asymptotic reduction of risk to zero ($\lim_{N \to \infty} \sigma_p^2 = 0$) holds strictly if and only if assets are mutually uncorrelated ($\bar{\text{Cov}} = 0$). In economic reality, widespread exposure to aggregate monetary, business-cycle, and institutional shocks establishes an empirical bound $\bar{\text{Cov}} > 0$. Therefore, naive expansion of asset quantities cannot eliminate systematic market volatility.