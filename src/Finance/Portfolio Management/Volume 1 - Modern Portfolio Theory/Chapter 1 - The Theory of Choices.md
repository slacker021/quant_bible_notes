---
dg-publish: true
---
# Prelude: Mean-Variance Optimization
Prior to the mid-twentieth century, the discipline of investment analysis was characterized by heuristic rules of thumb, qualitative balance sheet assessments, and localized valuation techniques championed by figures such as *Benjamin Graham* and *David Dodd*. While security analysis provided valuable microeconomic insights into the intrinsic earnings power of corporations, it lacked a coherent mathematical framework for evaluating combinations of assets. Risk was colloquially acknowledged, yet it was evaluated strictly at the level of the isolated security. An asset exhibiting wide return fluctuations was branded as inherently dangerous, while an asset with stable nominal coupons was deemed universally safe.

In 1952, *Harry Markowitz* published his doctoral dissertation, *Portfolio Selection*, establishing the mathematical foundation of modern financial economics. Markowitz introduced a fundamental insight: an investor must not evaluate an asset's risk in isolation, but rather through its marginal contribution to the aggregate risk of a portfolio. By modeling asset returns as random variables defined on an underlying probability space and quantifying risk via the second statistical moment (variance), Markowitz demonstrated that non-perfect correlation among asset returns permits the elimination of unsystematic risk without a commensurate reduction in expected return. This mathematical phenomenon represents what financial economists frequently refer to as the only genuine "free lunch" in economics. 

Within the architecture of the *Quant's Bible*, *Modern Portfolio Theory (MPT)* is not treated as an unassailable description of empirical market reality. Rather, it serves as the foundational normative benchmark. It formalizes how an idealized, risk-averse economic agent ought to allocate capital when decisions are constrained strictly to the first two statistical moments of a return distribution.

### The Future of Portfolio Construction
Progress continues to be made within the sphere of quantitative analysis. In the past, the use of quantitative methods within finance was seen as nonsensical. After all, finance was—and in many ways, continues to be—an art that required strong intuition and the ability to "read the room." Nowadays, however, the landscape is now flipped on its head: Quantitative analysis is now the norm while qualitative measures are seen as "irrational." While such a view is reductive and dangerous, it highlights the appeal and power of quantitative research within a historically qualitative domain. Perhaps it is better to think that both quantitative and qualitative frameworks have their place in the markets. After all, finance is both an art and a science—which is what makes the interdisciplinary field of quantitative finance so beautiful in the first place. 

The acceptance of quantitative techniques by the investment community in various markets around the world have grown at a rate that early pioneers, such as Harry Markowitz, would not have dreamed of then. Will the field continue to evolve, rendering the rendering today's truths less true than tomorrow? Perhaps. Despite this, the eager quant researcher shall press on and continue to learn—knowing more about capital markets now than what previous researchers did decades ago. There is still a lot more to learn, with the author of the Quant's Bible believing that there are securities and strategies that have expected returns above the riskless rate. 

---
# The Probability Space and Asset Returns
To establish portfolio theory on rigorous mathematical grounds, let the uncertainty of future economic states be modeled by a complete probability space $(\Omega, \mathcal{F}, \mathbb{P})$, where:
1. $\Omega$ is the sample space containing all possible realized economic states of nature at the investment horizon $T$;
2. $\mathcal{F}$ is the $\sigma$-algebra of measurable events (see [[Probability Spaces and Random Variables]]);
3. $\mathbb{P}$ is the physical (historical) probability measure.

Let the investment universe consist of $N \in \mathbb{N}$ risky financial assets. For each asset $i \in \{1, 2, \dots, N\}$, the price at inception $t = 0$ is a strictly positive deterministic constant $P_i(0) \in \mathbb{R}_{>0}$. The asset's terminal value at horizon $T$ is an $\mathcal{F}$-measurable positive random variable $P_i(T): \Omega \to \mathbb{R}_{>0}$, which incorporates capital appreciation and all intermediate cash disbursements (such as dividends or coupon payments): 
$$
\begin{gather}
\textbf{Definition: Discrete Asset Return} \\[5mm]
\text{The discrete rate of return for asset } i \text{ over the horizon } [0, T] \text{ is the real-valued random variable} \\[2mm]
R_i: \Omega \to \mathbb{R} \text{ defined by the relative price change:} \\[3.5mm]
R_i(\omega) := \frac{P_i(T, \omega) - P_i(0)}{P_i(0)} = \frac{P_i(T, \omega)}{P_i(0)} - 1
\end{gather}
$$

The stochastic properties of the $N$-dimensional asset universe are fully captured by the random return vector $\mathbf{R}: \Omega \to \mathbb{R}^N$:
$$
\begin{gather}
\mathbf{R}(\omega) := \begin{bmatrix} R_1(\omega) \\ R_2(\omega) \\ \vdots \\ R_N(\omega) \end{bmatrix} \tag{1}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Expected Return Vector and Covariance Matrix} \\[5mm]
\text{Assume that } R_i \in L^2(\Omega, \mathcal{F}, \mathbb{P}) \text{ for every } i \in \{1, 2, \dots, N\}. \text{ The expected return vector} \\[2mm]
\boldsymbol{\mu} \in \mathbb{R}^N \text{ is the first statistical moment of } \mathbf{R}\text{:} \\[3.5mm]
\boldsymbol{\mu} := \mathbb{E}[\mathbf{R}] = \begin{bmatrix} \mathbb{E}[R_1] \\ \mathbb{E}[R_2] \\ \vdots \\ \mathbb{E}[R_N] \end{bmatrix} = \begin{bmatrix} \mu_1 \\ \mu_2 \\ \vdots \\ \mu_N \end{bmatrix}  \\[5mm]
\text{The covariance matrix } \boldsymbol{\Sigma} \in \mathbb{R}^{N \times N} \text{ is the second centered joint moment of } \mathbf{R}\text{:} \\[3.5mm]
\boldsymbol{\Sigma} := \mathbb{E}\left[(\mathbf{R} - \boldsymbol{\mu})(\mathbf{R} - \boldsymbol{\mu})^T\right] = \begin{bmatrix}
\sigma_1^2 & \sigma_{12} & \cdots & \sigma_{1N} \\
\sigma_{21} & \sigma_2^2 & \cdots & \sigma_{2N} \\
\vdots & \vdots & \ddots & \vdots \\
\sigma_{N1} & \sigma_{N2} & \cdots & \sigma_N^2
\end{bmatrix} 
\end{gather}
$$
where $\sigma_i^2 := \operatorname{Var}(R_i) = \mathbb{E}[(R_i - \mu_i)^2]$ is the variance of asset $i$, and $\sigma_{ij} := \operatorname{Cov}(R_i, R_j) = \mathbb{E}[(R_i - \mu_i)(R_j - \mu_j)]$ is the covariance between asset $i$ and asset $j$. The correlation coefficient is the normalized inner product:
$$
\begin{gather}
\rho_{ij} := \frac{\sigma_{ij}}{\sigma_i \sigma_j} \in [-1, 1] \tag{2}
\end{gather}
$$
$$
\begin{gather}
\textbf{Proposition: Spectral Geometry of the Covariance Matrix} \\[5mm]
\text{The covariance matrix } \boldsymbol{\Sigma} \text{ is symmetric and positive semi-definite. That is, } \boldsymbol{\Sigma} = \boldsymbol{\Sigma}^T \text{ and:} \\[3.5mm]
\mathbf{x}^T \boldsymbol{\Sigma} \mathbf{x} \ge 0 \quad \forall \mathbf{x} \in \mathbb{R}^N \\[3.5mm]
\text{Furthermore, } \boldsymbol{\Sigma} \text{ is strictly positive definite } (\boldsymbol{\Sigma} \in \mathbb{S}_{++}^N, \text{ meaning } \mathbf{x}^T \boldsymbol{\Sigma} \mathbf{x} > 0 \text{ for all } \mathbf{x} \neq \mathbf{0}) \\[2mm]
\text{if and only if no non-trivial linear combination of the assets constitutes a risk-free asset.}
\end{gather}
$$
*(see [[Proof of Positive Semi-Definiteness of Covariance Matrices]])*

---
# The Portfolio Allocation Vector
An investor distributes their total financial wealth $W_0 \in \mathbb{R}_{>0}$ across the $N$ available assets. Let $h_i \in \mathbb{R}$ represent the nominal monetary currency allocated to asset $i$: 
$$
\begin{gather}
\textbf{Definition: Portfolio Weight Vector} \\[5mm]
\text{The portfolio weight vector } \mathbf{w} \in \mathbb{R}^N \text{ is the vector of capital fractions:} \\[3.5mm]
\mathbf{w} := \begin{bmatrix} w_1 \\ w_2 \\ \vdots \\ w_N \end{bmatrix}, \quad \text{where } w_i := \frac{h_i}{W_0}
\end{gather}
$$

By the conservation of capital, the weights must satisfy the affine budget constraint:
$$
\begin{gather}
\sum_{i=1}^N w_i = \mathbf{w}^T \mathbf{1} = 1 \tag{3}
\end{gather}
$$

where $\mathbf{1} := [1, 1, \dots, 1]^T \in \mathbb{R}^N$ is the vector of ones. The allowable investment policies are categorized according to short-sale restrictions:
1. **Unconstrained Allocation:** Short selling is permitted without institutional limits: $\mathbf{w} \in \mathbb{R}^N$ subject to $\mathbf{w}^T \mathbf{1} = 1$. Negative weights ($w_i < 0$) represent short positions.
2. **Long-Only Allocation:** Short selling is strictly prohibited: $\mathbf{w} \in \Delta^{N-1}$, where $\Delta^{N-1} := \{\mathbf{w} \in \mathbb{R}^N \mid \mathbf{w}^T \mathbf{1} = 1, \, w_i \ge 0 \ \forall i\}$ is the standard $(N-1)$-dimensional probability simplex.

The aggregate return of a portfolio formed by weight vector $\mathbf{w}$ is the linear inner product:
$$
\begin{gather}
R_p := \sum_{i=1}^N w_i R_i = \mathbf{w}^T \mathbf{R} \tag{4}
\end{gather}
$$

Applying the linearity of the mathematical expectation operator and the bilinear structure of the variance operator yields the mean and variance of the portfolio:
$$
\begin{gather}
\mu_p := \mathbb{E}[R_p] = \mathbb{E}[\mathbf{w}^T \mathbf{R}] = \mathbf{w}^T \mathbb{E}[\mathbf{R}] = \mathbf{w}^T \boldsymbol{\mu} \tag{5} \\[5mm]
\sigma_p^2 := \operatorname{Var}(R_p) = \operatorname{Var}(\mathbf{w}^T \mathbf{R}) = \mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w} = \sum_{i=1}^N \sum_{j=1}^N w_i w_j \sigma_{ij} \tag{6}
\end{gather}
$$

The standard deviation (volatility) is the Euclidean norm induced by the covariance metric: $\sigma_p = \sqrt{\mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w}}$.

---
# The Two-Asset Opportunity Set
To illustrate the mathematical mechanics of diversification, consider an economic setting restricted to two risky assets ($N = 2$). The portfolio weights satisfy $w_1 + w_2 = 1$, allowing the allocation to be parameterized by a single scalar parameter $w_1 = w$ and $w_2 = 1 - w$.

The portfolio expected return and variance expand to:
$$
\begin{gather}
\mu_p(w) = w \mu_1 + (1 - w)\mu_2 \tag{7} \\[5mm]
\sigma_p^2(w) = w^2 \sigma_1^2 + (1 - w)^2 \sigma_2^2 + 2w(1 - w)\sigma_1 \sigma_2 \rho_{12} \tag{8}
\end{gather}
$$

$$
\begin{align}
& \textbf{Proposition: Two-Asset Global Minimum Variance Portfolio (MVP)} \\[5mm]
& \text{Assume that } \sigma_1, \sigma_2 > 0 \text{ and } \rho_{12} \in [-1, 1). \text{ The unique portfolio weight } w^* \in \mathbb{R} \\[2mm]
& \text{that minimizes total portfolio variance } \sigma_p^2(w) \text{ is given by:} \\[3.5mm]
& \hspace{1.5 in} w^* = \frac{\sigma_2^2 - \sigma_{12}}{\sigma_1^2 + \sigma_2^2 - 2\sigma_{12}} = \frac{\sigma_2^2 - \rho_{12}\sigma_1 \sigma_2}{\sigma_1^2 + \sigma_2^2 - 2\rho_{12}\sigma_1 \sigma_2}  \\[3.5mm]
& \text{Furthermore, the minimum attainable variance satisfies:} \\[3.5mm]
& \hspace{1.5 in} \sigma_{p, \min}^2 = \frac{\sigma_1^2 \sigma_2^2 (1 - \rho_{12}^2)}{\sigma_1^2 + \sigma_2^2 - 2\rho_{12}\sigma_1 \sigma_2} 
\end{align}
$$

*(see [[Proof of the Minimum Variance Portfolio Formulation]])*

The geometric curvature of the opportunity set in the $(\sigma_p, \mu_p)$ plane depends entirely on the correlation coefficient $\rho_{12}$:
```
     μ (Return)
     ^
     |         / (ρ = +1: Straight line connecting Asset 2 to Asset 1)
μ_1 -+        / 
     |       /  . (ρ = 0: Smooth convex curve bowing leftward)
     |      /  .
     |     /  .   <-- Minimum Variance Portfolio (MVP)
     |    /  .
μ_2 -+   *  .  <-- (ρ = -1: Hyper-efficient piecewise linear boundary touching σ=0)
     |    \   .
     |     \    .
     +------+------> σ (Volatility)
     0     σ_2   σ_1
```

1. **Perfect Positive Correlation ($\rho_{12} = 1$):**
   The variance simplifies to a perfect square:
   $$\sigma_p^2 = (w\sigma_1 + (1 - w)\sigma_2)^2 \implies \sigma_p = |w\sigma_1 + (1 - w)\sigma_2| \tag{9}$$
   For long-only allocations ($w \in [0, 1]$), $\sigma_p = w\sigma_1 + (1 - w)\sigma_2$. The relationship between risk and return is strictly linear:
   $$\mu_p = \mu_2 + \left(\frac{\mu_1 - \mu_2}{\sigma_1 - \sigma_2}\right)(\sigma_p - \sigma_2) \tag{10}$$
   Diversification provides no reduction in variance below the linear weighted average of the two assets.

2. **Perfect Negative Correlation ($\rho_{12} = -1$):**
   The variance simplifies to:
   $$\sigma_p^2 = (w\sigma_1 - (1 - w)\sigma_2)^2 \implies \sigma_p = |w\sigma_1 - (1 - w)\sigma_2| \tag{11}$$
   Setting $\sigma_p = 0$ yields the zero-risk weight:
   $$w^* = \frac{\sigma_2}{\sigma_1 + \sigma_2} \in (0, 1) \tag{12}$$
   A completely riskless synthetic asset can be constructed from two volatile securities, yielding a guaranteed return of $\mu_p^* = \frac{\sigma_2 \mu_1 + \sigma_1 \mu_2}{\sigma_1 + \sigma_2}$.

3. **Imperfect Correlation ($-1 < \rho_{12} < 1$):**
   The second derivative of portfolio volatility with respect to the portfolio weight is strictly positive:
   $$\frac{d^2 \sigma_p}{dw^2} > 0 \tag{13}$$
   The portfolio possibilities curve bows strictly leftward toward the vertical axis, establishing that $\sigma_p(w) < w\sigma_1 + (1 - w)\sigma_2$ for all $w \in (0, 1)$.

>[!example]- Example: Elton-Gruber Empirical Stock-Bond Opportunity Set
>To examine this geometry consider an institutional asset allocator selecting between large-cap common stocks (Asset 1) and long-term corporate bonds (Asset 2):
>
>* **Asset 1 (Equities / S&P):** Expected return $\mu_S = 11.80\%$, standard deviation $\sigma_S = 20.30\%$.
>* **Asset 2 (Corporate Bonds):** Expected return $\mu_B = 6.40\%$, standard deviation $\sigma_B = 8.40\%$.
>* **Empirical Pairwise Correlation:** $\rho_{SB} = 0.2312$, yielding a covariance of:
>  $$\sigma_{SB} = \rho_{SB}\sigma_S \sigma_B = 0.2312 \times 20.30 \times 8.40 = 39.425 \tag{14}$$
>
>Substituting these empirical moments into the minimum variance weight formula of step 14:
>$$w_S^* = \frac{8.40^2 - 39.425}{20.30^2 + 8.40^2 - 2(39.425)} = \frac{70.56 - 39.425}{412.09 + 70.56 - 78.85} = \frac{31.135}{403.80} \approx 0.0771 \tag{15}$$
>
>The global minimum variance portfolio allocates approximately $7.71\%$ to common stocks and $92.29\%$ to corporate bonds. The resulting expected return and standard deviation are:
>$$\mu_{p, \min} = (0.0771)(11.80\%) + (0.9229)(6.40\%) = 0.9098\% + 5.9066\% = 6.816\% \tag{16}$$
>$$\sigma_{p, \min} = \sqrt{(0.0771)^2(20.30)^2 + (0.9229)^2(8.40)^2 + 2(0.0771)(0.9229)(39.425)} \approx 7.83\% \tag{17}$$
>
>The portfolio standard deviation ($7.83\%$) is lower than the standard deviation of corporate bonds held in isolation ($8.40\%$), despite common stocks exhibiting more than double the risk of bonds ($20.30\%$). Adding a high-risk asset with low correlation systematically reduces total portfolio variance.

---
# The General $N$-Asset Markowitz Optimization Problem
In a financial market comprising $N$ risky securities with expected return vector $\boldsymbol{\mu} \in \mathbb{R}^N$ and positive-definite covariance matrix $\boldsymbol{\Sigma} \in \mathbb{S}_{++}^N$, the Markowitz optimization problem can be formulated in two mathematically equivalent ways:
1. **Variance Minimization:** Minimize portfolio variance $\sigma_p^2 = \mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w}$ subject to achieving a target expected return $\mathbf{w}^T \boldsymbol{\mu} = \mu_0$ and the budget constraint $\mathbf{w}^T \mathbf{1} = 1$.
2. **Utility Maximization:** Maximize expected quadratic utility $U(\mathbf{w}) = \mathbf{w}^T \boldsymbol{\mu} - \frac{\lambda}{2} \mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w}$ subject to $\mathbf{w}^T \mathbf{1} = 1$, where $\lambda > 0$ represents the investor's Pratt-Arrow coefficient of absolute risk aversion.

### Analytical Derivation of the Unconstrained Efficient Frontier
Consider the variance minimization formulation with unconstrained short sales ($\mathbf{w} \in \mathbb{R}^N$):
$$
\begin{gather}
\min_{\mathbf{w} \in \mathbb{R}^N} \ \frac{1}{2} \mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w} \tag{18} \\[3.5mm]
\text{subject to} \quad \mathbf{w}^T \mathbf{1} = 1 \quad \text{and} \quad \mathbf{w}^T \boldsymbol{\mu} = \mu_0 \tag{19}
\end{gather}
$$

The factor $\frac{1}{2}$ is introduced without loss of generality to simplify first-order differentiation. Define the Lagrangian function $\mathcal{L}: \mathbb{R}^N \times \mathbb{R} \times \mathbb{R} \to \mathbb{R}$ with Lagrange multipliers $\gamma_1, \gamma_2 \in \mathbb{R}$:
$$
\begin{gather}
\mathcal{L}(\mathbf{w}, \gamma_1, \gamma_2) = \frac{1}{2}\mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w} - \gamma_1 (\mathbf{w}^T \mathbf{1} - 1) - \gamma_2 (\mathbf{w}^T \boldsymbol{\mu} - \mu_0) \tag{20}
\end{gather}
$$

Because $\boldsymbol{\Sigma} \in \mathbb{S}_{++}^N$, the objective function is strictly convex over $\mathbb{R}^N$, guaranteeing that the stationary point of the first-order Karush-Kuhn-Tucker (KKT) conditions constitutes the unique global minimum (see [[Linear Analysis: Positive Definite Matrices]]).

Differentiating $\mathcal{L}$ with respect to $\mathbf{w}$ and setting the gradient to zero:
$$
\begin{gather}
\nabla_{\mathbf{w}} \mathcal{L} = \boldsymbol{\Sigma} \mathbf{w} - \gamma_1 \mathbf{1} - \gamma_2 \boldsymbol{\mu} = \mathbf{0} \tag{21} \\[3.5mm]
\implies \mathbf{w} = \gamma_1 \boldsymbol{\Sigma}^{-1} \mathbf{1} + \gamma_2 \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{22}
\end{gather}
$$

To eliminate the multipliers $(\gamma_1, \gamma_2)$, premultiply step 20 by $\mathbf{1}^T$ and $\boldsymbol{\mu}^T$:
$$
\begin{gather}
\mathbf{1}^T \mathbf{w} = \gamma_1 (\mathbf{1}^T \boldsymbol{\Sigma}^{-1} \mathbf{1}) + \gamma_2 (\mathbf{1}^T \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}) = 1 \tag{22} \\[3.5mm]
\boldsymbol{\mu}^T \mathbf{w} = \gamma_1 (\boldsymbol{\mu}^T \boldsymbol{\Sigma}^{-1} \mathbf{1}) + \gamma_2 (\boldsymbol{\mu}^T \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}) = \mu_0 \tag{23}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Merton's Fundamental Frontier Constants} \\[5mm]
\text{Define the scalar constants induced by the inner products of } \mathbf{1} \text{ and } \boldsymbol{\mu} \text{ under metric } \boldsymbol{\Sigma}^{-1}\text{:} \\[3.5mm]
A := \mathbf{1}^T \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} = \boldsymbol{\mu}^T \boldsymbol{\Sigma}^{-1} \mathbf{1}  \\[2mm]
B := \boldsymbol{\mu}^T \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu}  \\[2mm]
C := \mathbf{1}^T \boldsymbol{\Sigma}^{-1} \mathbf{1} \\[2mm]
D := BC - A^2 
\end{gather}
$$

By the Cauchy-Schwarz inequality on inner product spaces (see [[Metric Spaces and Topological Boundaries]]), because $\boldsymbol{\mu}$ and $\mathbf{1}$ are not linearly collinear (provided asset expected returns are not identical), $D = BC - A^2 > 0$.

Expressing the system of equations of step 22 and step 23 in matrix form:
$$
\begin{gather}
\begin{bmatrix} C & A \\ A & B \end{bmatrix} \begin{bmatrix} \gamma_1 \\ \gamma_2 \end{bmatrix} = \begin{bmatrix} 1 \\ \mu_0 \end{bmatrix} \tag{24}
\end{gather}
$$

Inverting the $2 \times 2$ coefficient matrix yields the unique Lagrange multipliers:
$$
\begin{gather}
\begin{bmatrix} \gamma_1 \\ \gamma_2 \end{bmatrix} = \frac{1}{D} \begin{bmatrix} B & -A \\ -A & C \end{bmatrix} \begin{bmatrix} 1 \\ \mu_0 \end{bmatrix} = \begin{bmatrix} \frac{B - A\mu_0}{D} \\ \frac{C\mu_0 - A}{D} \end{bmatrix} \tag{25}
\end{gather}
$$

Substituting $\gamma_1$ and $\gamma_2$ from step 28 back into the allocation equation of step 20 yields the optimal weight vector:
$$
\begin{gather}
\mathbf{w}^*(\mu_0) = \left(\frac{B - A\mu_0}{D}\right) \boldsymbol{\Sigma}^{-1} \mathbf{1} + \left(\frac{C\mu_0 - A}{D}\right) \boldsymbol{\Sigma}^{-1} \boldsymbol{\mu} \tag{26}
\end{gather}
$$

$$
\begin{align}
& \textbf{Theorem: Parabolic and Hyperbolic Frontier Geometry} \\[5mm]
& \text{The minimum attainable portfolio variance for a target return } \mu_0 \text{ is given by the quadratic form:} \\[3.5mm]
& \hspace{1.5 in} \sigma_p^2(\mu_0) = \frac{C\mu_0^2 - 2A\mu_0 + B}{D} = \frac{1}{C} + \frac{C}{D}\left(\mu_0 - \frac{A}{C}\right)^2 \tag{30} \\[3.5mm]
& \text{In the } (\sigma_p^2, \mu_p) \text{ plane, the boundary is an exact parabola with vertex at the Global Minimum} \\[2mm]
& \text{Variance Portfolio (GMVP):} \\[3.5mm]
& \hspace{1.5 in} \mu_{\text{GMVP}} = \frac{A}{C}, \quad \sigma_{\text{GMVP}}^2 = \frac{1}{C}, \quad \mathbf{w}_{\text{GMVP}} = \frac{1}{C}\boldsymbol{\Sigma}^{-1}\mathbf{1} \tag{31} \\[3.5mm]
& \text{In the standard } (\sigma_p, \mu_p) \text{ plane, the efficient boundary forms the upper branch of a hyperbola:} \\[3.5mm]
& \hspace{1.5 in} \frac{\sigma_p^2}{1/C} - \frac{(\mu_p - A/C)^2}{D/C^2} = 1 \tag{32}
\end{align}
$$
*(see [[Proof of Merton's Efficient Frontier Representation]])*

---
# The Two-Fund Separation Theorem

A profound mathematical property of the Markowitz unconstrained efficient frontier is that the entire hyperbola can be generated as an affine linear combination of any two distinct efficient portfolios: 
$$
\begin{gather}
\textbf{Theorem: Two-Fund Monetary Separation} \\[5mm]
\text{Let } \mathbf{w}_1^* \text{ and } \mathbf{w}_2^* \text{ be two distinct optimal portfolio vectors lying on the efficient frontier} \\[2mm]
\text{corresponding to target returns } \mu_1 \ne \mu_2. \text{ Then any frontier portfolio } \mathbf{w}^*(\mu_0) \text{ can be expressed as:} \\[3.5mm]
\mathbf{w}^*(\mu_0) = \alpha \mathbf{w}_1^* + (1 - \alpha) \mathbf{w}_2^* \tag{33} \\[3.5mm]
\text{where the scalar fraction } \alpha \in \mathbb{R} \text{ evaluates to } \alpha = \frac{\mu_0 - \mu_2}{\mu_1 - \mu_2}.
\end{gather}
$$
*(see [[Proof of the Two-Fund Separation Theorem]])*

This result has major financial implications: an investment institution does not need to engineer bespoke portfolios from thousands of individual securities for every client. The firm can construct two distinct mutual funds located along the efficient frontier; any investor can achieve their optimal allocation simply by dividing capital between those two funds.

---
# The Efficient Frontier in the Presence of a Riskless Asset
Now introduce a risk-free financial security (such as short-term sovereign Treasury bills) with deterministic rate of return $R_F \in \mathbb{R}_{>0}$ and zero variance ($\sigma_F^2 = 0, \operatorname{Cov}(R_F, R_i) = 0 \ \forall i$).

Let $w_0 \in \mathbb{R}$ represent the fraction of capital allocated to the riskless asset, and let $\mathbf{w} \in \mathbb{R}^N$ represent the weights allocated across the $N$ risky assets. The budget constraint requires:
$$
\begin{gather}
w_0 + \sum_{i=1}^N w_i = w_0 + \mathbf{w}^T \mathbf{1} = 1 \implies w_0 = 1 - \mathbf{w}^T \mathbf{1} \tag{27}
\end{gather}
$$

The expected return and standard deviation of the combined portfolio simplify to:
$$
\begin{gather}
\mu_c = w_0 R_F + \mathbf{w}^T \boldsymbol{\mu} = R_F + \mathbf{w}^T (\boldsymbol{\mu} - R_F \mathbf{1}) \tag{28} \\[3.5mm]
\sigma_c = \sqrt{\mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w}} \tag{29}
\end{gather}
$$

### The Capital Market Line and the Tangency Portfolio
The optimal combination of risky assets maximizes the reward-to-risk ratio, known as the **Sharpe Ratio** $\theta(\mathbf{w})$:
$$
\begin{gather}
\max_{\mathbf{w} \in \mathbb{R}^N} \ \theta(\mathbf{w}) = \frac{\mathbf{w}^T (\boldsymbol{\mu} - R_F \mathbf{1})}{\sqrt{\mathbf{w}^T \boldsymbol{\Sigma} \mathbf{w}}} \tag{30}
\end{gather}
$$

Because the objective function $\theta(\mathbf{w})$ is homogeneous of degree zero ($\theta(k \mathbf{w}) = \theta(\mathbf{w})$ for any $k > 0$), scaling the weight vector leaves the Sharpe ratio invariant. To solve step 37 analytically, consider the unnormalized vector $\mathbf{z} := \lambda \mathbf{w}$. Setting the gradient of $\theta(\mathbf{w})$ to zero yields the classic system of simultaneous linear equations:
$$
\begin{gather}
\boldsymbol{\Sigma} \mathbf{z} = \boldsymbol{\mu} - R_F \mathbf{1} \implies \mathbf{z} = \boldsymbol{\Sigma}^{-1}(\boldsymbol{\mu} - R_F \mathbf{1}) \tag{31}
\end{gather}
$$

Normalizing the vector $\mathbf{z}$ so that its components sum to unity recovers the unique **Tangency Portfolio** $\mathbf{w}_T$:
$$
\begin{gather}
\mathbf{w}_T = \frac{\mathbf{z}}{\mathbf{z}^T \mathbf{1}} = \frac{\boldsymbol{\Sigma}^{-1}(\boldsymbol{\mu} - R_F \mathbf{1})}{\mathbf{1}^T \boldsymbol{\Sigma}^{-1}(\boldsymbol{\mu} - R_F \mathbf{1})} = \frac{\boldsymbol{\Sigma}^{-1}(\boldsymbol{\mu} - R_F \mathbf{1})}{A - C R_F} \tag{32}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: The Capital Market Line (CML)} \\[5mm]
\text{The linear locus connecting the risk-free rate } (0, R_F) \text{ through the risky tangency portfolio } (\sigma_T, \mu_T) \\[2mm]
\text{dominates the entire risky Markowitz efficient frontier. Its equation in } (\sigma, \mu) \text{ space is:} \\[3.5mm]
\mu_c(\sigma_c) = R_F + \left(\frac{\mu_T - R_F}{\sigma_T}\right) \sigma_c \tag{40}
\end{gather}
$$

```
     μ (Return)
     ^
     |                           / (CML: Capital Market Line)
     |                         /
μ_T -+-----------------------* (Tangency Portfolio T)
     |                     / .
     |                   /   .   <-- Risky Efficient Frontier
     |                 /      .
     |               /         .
R_F -+-------------/            .
     |                            . (GMVP)
     |                             .
     +-------------+---------+---------> σ (Volatility)
     0            σ_T
```

##### Dual Borrowing and Lending Rates ($R_B > R_L$)
The classical derivation assumes investors can borrow and lend at the identical rate $R_F$. In actual financial markets, institutional lending (risk-free) rates $R_L$ are strictly lower than borrowing rates $R_B$ ($R_B > R_L$). Under differential rates, the Capital Market Line fractures into a piecewise envelope:
1. **Lending Segment:** For $\sigma \in [0, \sigma_{T_L}]$, the frontier is linear:
   $$\mu_c = R_L + \left(\frac{\mu_{T_L} - R_L}{\sigma_{T_L}}\right)\sigma_c \tag{33}$$
   where $T_L$ is the tangency portfolio calculated using $R_L$.
2. **Risky Boundary Segment:** For $\sigma \in (\sigma_{T_L}, \sigma_{T_B})$, the investor is fully invested in risky assets without borrowing or lending. The efficient frontier follows the curved Markowitz hyperbola between $T_L$ and $T_B$.
3. **Borrowing Segment:** For $\sigma \ge \sigma_{T_B}$, the investor leverages risky portfolio $T_B$ by borrowing capital at rate $R_B$:
   $$\mu_c = R_B + \left(\frac{\mu_{T_B} - R_B}{\sigma_{T_B}}\right)\sigma_c \tag{34}$$
   where $T_B$ is the tangency portfolio calculated using $R_B$.

Single-fund monetary separation breaks down: investors with varying risk tolerances do not hold the same risky portfolio. Highly risk-averse investors hold a mix of $R_L$ and $T_L$, moderately risk-averse investors hold varying portfolios along the curved arc between $T_L$ and $T_B$, and aggressive investors borrow at $R_B$ to lever up portfolio $T_B$.

---
# Simplification of the Covariance Structure: The Single-Index Model
A primary barrier to implementing full Markowitz optimization in large asset universes is the sheer volume of required statistical parameters. For $N$ assets, an analyst must estimate:
* $N$ expected returns $\mu_i$;
* $N$ variances $\sigma_i^2$;
* $\frac{N(N-1)}{2}$ unique covariances $\sigma_{ij}$.

For $N = 1{,}000$ securities, this requires estimating $1{,}000 + 1{,}000 + 499{,}500 = 501{,}500$ parameters. Small estimation errors in individual covariances compound across matrix inversion, causing severe out-of-sample portfolio instability.

In 1963, William Sharpe introduced the **Single-Index Model (SIM)**, positing that asset returns co-vary solely due to their shared sensitivity to an aggregate market index $R_m$: 
$$
\begin{gather}
\textbf{Definition: The Single-Index Model (Sharpe)} \\[5mm]
\text{The return of security } i \in \{1, 2, \dots, N\} \text{ is decomposed as:} \\[3.5mm]
R_i = \alpha_i + \beta_i R_m + e_i  \\[3.5mm]
\text{subject to the following structural assumptions:} \\[2mm]
\text{1. Zero residual expectation: } \mathbb{E}[e_i] = 0 \quad \forall i \\[2mm]
\text{2. Orthogonality with the index: } \operatorname{Cov}(e_i, R_m) = \mathbb{E}[e_i (R_m - \mu_m)] = 0 \quad \forall i \\[2mm]
\text{3. Zero residual cross-covariance: } \operatorname{Cov}(e_i, e_j) = \mathbb{E}[e_i e_j] = 0 \quad \forall i \ne j
\end{gather}
$$

Let $\sigma_m^2 := \operatorname{Var}(R_m)$ denote market variance, and let $\sigma_{ei}^2 := \operatorname{Var}(e_i)$ denote the unsystematic (idiosyncratic) variance of asset $i$. The moments of the asset universe simplify to:
$$
\begin{gather}
\mu_i = \alpha_i + \beta_i \mu_m \tag{35} \\[3.5mm]
\sigma_i^2 = \beta_i^2 \sigma_m^2 + \sigma_{ei}^2 \tag{36} \\[3.5mm]
\sigma_{ij} = \beta_i \beta_j \sigma_m^2 \quad \forall i \ne j \tag{37}
\end{gather}
$$

The Single-Index Model collapses the required parameter set from $\mathcal{O}(N^2)$ to exactly $3N + 2$ parameters: $N$ alphas ($\alpha_i$), $N$ betas ($\beta_i$), $N$ residual variances ($\sigma_{ei}^2$), along with $\mu_m$ and $\sigma_m^2$. For $N = 1{,}000$, the input requirement drops from $501{,}500$ down to $3{,}002$ parameters—a reduction of over $99.4\%$.

---
# The Elton-Gruber-Padberg Cutoff Algorithm
A major pedagogical and practical breakthrough in modern portfolio theory was achieved by Edwin Elton, Martin Gruber, and Manfred Padberg (1976). They proved that under the Single-Index Model, the optimal portfolio can be solved without inverting the covariance matrix, using a simple ranking device: the **excess return-to-beta ratio**: 
$$
\begin{gather}
\text{Ranking Metric: } \frac{\mu_i - R_F}{\beta_i} \tag{38}
\end{gather}
$$

Securities are sorted in descending order based on step 45. The optimal portfolio consists of selecting all securities whose excess return-to-beta ratio exceeds a unique scalar cutoff threshold $C^*$: 
$$
\begin{gather}
\textbf{Definition: The Elton-Gruber Cutoff Rate } C_i \\[5mm]
\text{For a candidate portfolio containing the top } i \text{ ranked securities, the cutoff value } C_i \text{ is defined as:} \\[3.5mm]
C_i := \frac{\sigma_m^2 \sum_{j=1}^i \frac{(\mu_j - R_F)\beta_j}{\sigma_{ej}^2}}{1 + \sigma_m^2 \sum_{j=1}^i \frac{\beta_j^2}{\sigma_{ej}^2}} \tag{46}
\end{gather}
$$

The optimal cutoff rate $C^*$ is the value $C_i$ where all included securities $j \le i$ satisfy $\frac{\mu_j - R_F}{\beta_j} > C^*$, and all excluded securities $k > i$ satisfy $\frac{\mu_k - R_F}{\beta_k} \le C^*$. Once $C^*$ is identified, the relative unnormalized weights $Z_i$ and the final normalized portfolio weights $X_i$ evaluate directly to:
$$
\begin{gather}
Z_i = \frac{\beta_i}{\sigma_{ei}^2}\left(\frac{\mu_i - R_F}{\beta_i} - C^*\right) \tag{39} \\[3.5mm]
X_i = \frac{Z_i}{\sum_{j \in \text{included}} Z_j} \tag{40}
\end{gather}
$$

>[!example]- Example:  10-Security Optimal Selection 
>To demonstrate this procedure, consider a 10-security universe. Let the riskless interest rate be $R_F = 5\%$ and the market index variance be $\sigma_m^2 = 10$.
>
>The securities are ranked in descending order according to their excess return-to-beta ratios:
>
>| Security $i$ | Mean Return $\mu_i$ | Excess Return $\mu_i - R_F$ | Beta $\beta_i$ | Unsystematic Risk $\sigma_{ei}^2$ | Ratio $\frac{\mu_i - R_F}{\beta_i}$ |
>| :--- | :---: | :---: | :---: | :---: | :---: |
>| **1** | $15.0\%$ | $10.0\%$ | $1.0$ | $50$ | **$10.0$** |
>| **2** | $17.0\%$ | $12.0\%$ | $1.5$ | $40$ | **$8.0$** |
>| **3** | $12.0\%$ | $7.0\%$ | $1.0$ | $20$ | **$7.0$** |
>| **4** | $17.0\%$ | $12.0\%$ | $2.0$ | $10$ | **$6.0$** |
>| **5** | $11.0\%$ | $6.0\%$ | $1.0$ | $40$ | **$6.0$** |
>| **6** | $11.0\%$ | $6.0\%$ | $1.5$ | $30$ | **$4.0$** |
>| **7** | $11.0\%$ | $6.0\%$ | $2.0$ | $40$ | **$3.0$** |
>| **8** | $7.0\%$ | $2.0\%$ | $0.8$ | $16$ | **$2.5$** |
>| **9** | $7.0\%$ | $2.0\%$ | $1.0$ | $20$ | **$2.0$** |
>| **10** | $5.6\%$ | $0.6\%$ | $0.6$ | $6$ | **$1.0$** |
>
>Applying the cumulative summation formulas from step 40:
>
>| Security $i$ | $\frac{(\mu_i - R_F)\beta_i}{\sigma_{ei}^2}$ | $\frac{\beta_i^2}{\sigma_{ei}^2}$ | $\sum_{j=1}^i \frac{(\mu_j - R_F)\beta_j}{\sigma_{ej}^2}$ | $\sum_{j=1}^i \frac{\beta_j^2}{\sigma_{ej}^2}$ | Cutoff $C_i$ |
>| :--- | :---: | :---: | :---: | :---: | :---: |
>| **1** | $0.200$ | $0.0200$ | $0.200$ | $0.0200$ | **$1.67$** |
>| **2** | $0.450$ | $0.05625$ | $0.650$ | $0.07625$ | **$3.69$** |
>| **3** | $0.350$ | $0.0500$ | $1.000$ | $0.12625$ | **$4.42$** |
>| **4** | $2.400$ | $0.4000$ | $3.400$ | $0.52625$ | **$5.43$** |
>| **5** | $0.150$ | $0.0250$ | $3.550$ | $0.55125$ | **$5.45$** |
>| **6** | $0.300$ | $0.0750$ | $3.850$ | $0.62625$ | **$5.30$** |
>| **7** | $0.300$ | $0.1000$ | $4.150$ | $0.72625$ | **$5.02$** |
>| **8** | $0.100$ | $0.0400$ | $4.250$ | $0.76625$ | **$4.91$** |
>| **9** | $0.100$ | $0.0500$ | $4.350$ | $0.81625$ | **$4.75$** |
>| **10** | $0.060$ | $0.0600$ | $4.410$ | $0.87625$ | **$4.52$** |
>
>Evaluating the stopping rule:
>* For Security 5: $\frac{\mu_5 - R_F}{\beta_5} = 6.0 > C_5 = 5.45$.
>* For Security 6: $\frac{\mu_6 - R_F}{\beta_6} = 4.0 < C_5 = 5.45$.
>
>The optimal cutoff rate is definitively established at **$C^* = 5.45$**. Exactly the top 5 securities enter the optimal portfolio.
>
>Computing the unnormalized and normalized portfolio weights using steps 39 and 40:
>* $Z_1 = \frac{1.0}{50}(10.0 - 5.45) = 0.0910$
>* $Z_2 = \frac{1.5}{40}(8.0 - 5.45) = 0.0956$
>* $Z_3 = \frac{1.0}{20}(7.0 - 5.45) = 0.0775$
>* $Z_4 = \frac{2.0}{10}(6.0 - 5.45) = 0.1100$
>* $Z_5 = \frac{1.0}{40}(6.0 - 5.45) = 0.0138$
>* Sum of $Z_j = 0.0910 + 0.0956 + 0.0775 + 0.1100 + 0.0138 = 0.3879$
>
>Normalizing to obtain final capital allocations $X_i$:
>$$X_1 = \frac{0.0910}{0.3879} \approx 23.46\%, \quad X_2 = \frac{0.0956}{0.3879} \approx 24.65\%, \quad X_3 = \frac{0.0775}{0.3879} \approx 19.98\% \tag{41}$$
>$$X_4 = \frac{0.1100}{0.3879} \approx 28.36\%, \quad X_5 = \frac{0.0138}{0.3879} \approx 3.55\% \tag{42}$$
>
>Securities 6 through 10 receive exactly zero allocation ($X_6 = \dots = X_{10} = 0\%$).

---
# Computational Implementation in Julia
The principles discussed above may be implemented in the Julia programming language, with use of its current libraries, to reduce the amount of boilerplate code required to run things from scratch: 
```julia
# ==============================================================================
# Language: Julia 1.x
# Packages: PortfolioOptimisers, LinearAlgebra, Statistics, DataFrames
# ==============================================================================

using LinearAlgebra
using Statistics
using DataFrames
using PortfolioOptimisers

"""
    elton_gruber_sim(mu, beta, sigma_e2, sigma_m2, Rf)

Executes the Elton-Gruber-Padberg cutoff algorithm for the Single-Index Model.
Returns the optimal cutoff rate C*, the boolean inclusion vector, and normalized weights.
"""
function elton_gruber_sim(
    mu::AbstractVector{T},
    beta::AbstractVector{T},
    sigma_e2::AbstractVector{T},
    sigma_m2::T,
    Rf::T
) where {T<:AbstractFloat}
    
    n = length(mu)
    @assert length(beta) == n && length(sigma_e2) == n "Dimension mismatch across input vectors."
    
    # Step 1: Calculate excess return to beta ratio
    excess_return = mu .- Rf
    ratio = excess_return ./ beta
    
    # Step 2: Sort securities in descending order of ratio
    perm = sortperm(ratio, rev=true)
    sorted_mu = mu[perm]
    sorted_beta = beta[perm]
    sorted_sigma_e2 = sigma_e2[perm]
    sorted_ratio = ratio[perm]
    
    # Step 3: Compute running cumulative sums for C_i calculation
    term1 = (sorted_mu .- Rf) .* sorted_beta ./ sorted_sigma_e2
    term2 = (sorted_beta .^ 2) ./ sorted_sigma_e2
    
    cum_term1 = cumsum(term1)
    cum_term2 = cumsum(term2)
    
    C_values = zeros(T, n)
    for i in 1:n
        C_values[i] = (sigma_m2 * cum_term1[i]) / (one(T) + sigma_m2 * cum_term2[i])
    end
    
    # Step 4: Determine optimal cutoff C*
    k_star = 0
    for i in 1:n
        if sorted_ratio[i] > C_values[i]
            k_star = i
        else
            break
        end
    end
    
    C_star = C_values[k_star]
    
    # Step 5: Compute unnormalized and normalized portfolio weights
    Z = zeros(T, n)
    for i in 1:k_star
        Z[i] = (sorted_beta[i] / sorted_sigma_e2[i]) * (sorted_ratio[i] - C_star)
    end
    
    sum_Z = sum(Z)
    sorted_weights = Z ./ sum_Z
    
    # Map sorted allocations back to original asset indexing
    final_weights = zeros(T, n)
    final_weights[perm] = sorted_weights
    
    return (
        C_star = C_star,
        cutoff_index = k_star,
        sorted_table = DataFrame(
            Asset = perm,
            Mean = sorted_mu,
            Beta = sorted_beta,
            ResidualVar = sorted_sigma_e2,
            Ratio = sorted_ratio,
            Cutoff = C_values,
            Weight = sorted_weights
        ),
        weights = final_weights
    )
end

# ------------------------------------------------------------------------------
# Verification against the 10-security example
# ------------------------------------------------------------------------------

mu_data       = Float64[15.0, 17.0, 12.0, 17.0, 11.0, 11.0, 11.0, 7.0, 7.0, 5.6]
beta_data     = Float64[1.0,  1.5,  1.0,  2.0,  1.0,  1.5,  2.0,  0.8, 1.0, 0.6]
sigma_e2_data = Float64[50.0, 40.0, 20.0, 10.0, 40.0, 30.0, 40.0, 16.0, 20.0, 6.0]
sigma_m2_val  = 10.0
Rf_val        = 5.0

sim_results = elton_gruber_sim(mu_data, beta_data, sigma_e2_data, sigma_m2_val, Rf_val)

println("Optimal Cutoff Rate (C*): ", round(sim_results.C_star, digits=4))
println("Included Assets Count:    ", sim_results.cutoff_index)
println("\nSorted Security Optimization Table:")
println(sim_results.sorted_table)

# ------------------------------------------------------------------------------
# Full Quadratic Optimization via PortfolioOptimisers.jl Architecture
# ------------------------------------------------------------------------------

"""
    solve_markowitz_portfolio(mu, Sigma, target_ret)

Constructs and optimizes a traditional Markowitz mean-variance portfolio using
the high-level abstractions of PortfolioOptimisers.jl.
"""
function solve_markowitz_portfolio(
    mu::AbstractVector{T},
    Sigma::AbstractMatrix{T},
    Rf::T
) where {T<:AbstractFloat}

    # Instantiate the portfolio object
    port = Portfolio(
        mu = mu,
        cov = Sigma,
        rf = Rf
    )
    
    # Configure unconstrained budget and long-only simplex bounds
    port.budget = 1.0
    port.lowerbounds = zeros(T, length(mu))
    port.upperbounds = ones(T, length(mu))
    
    # Solve for the Tangency Portfolio (Maximum Sharpe Ratio)
    w_tangency = optimal_portfolio(port, type = :Sharpe)
    
    return w_tangency
end
```

---
# Epistemological Limitations and Estimation Risk
While Modern Portfolio Theory provides an elegant mathematical structure for normative capital allocation, its uncritical application in practical quantitative finance is subject to profound epistemological breakdowns.

### 1. Estimation Error Maximization
As established by Richard Michaud (1989), the mean-variance optimizer acts as an **estimation error maximizer**. Quadratic optimization requires computing $\boldsymbol{\Sigma}^{-1}(\boldsymbol{\mu} - R_F \mathbf{1})$. In sample estimations:
* Errors in expected returns $\hat{\boldsymbol{\mu}}$ are exponentially more destructive to portfolio efficiency than errors in variances or covariances (Chopra and Ziemba, 1993).
* The algorithm assigns the largest capital weights to assets that exhibit the largest upward sample measurement bias in expected returns and the largest downward bias in risk, leading to hyper-fragile, concentrated portfolios out-of-sample.

### 2. Structural Instability and Shrinkage Solutions
To stabilize matrix inversion when the observation window $T$ is not substantially larger than the asset universe dimension $N$, institutional practitioners replace the standard sample covariance matrix $\hat{\boldsymbol{\Sigma}}$ with regularized, Stein-type shrinkage estimators (Ledoit & Wolf, 2004):
$$
\begin{gather}
\boldsymbol{\Sigma}_{\text{shrunk}} = \delta \mathbf{F} + (1 - \delta)\hat{\boldsymbol{\Sigma}} \tag{41}
\end{gather}
$$

where $\mathbf{F}$ is a structured shrinkage target (such as the Single-Index covariance matrix or a constant correlation matrix) and $\delta \in [0, 1]$ is the asymptotically optimal shrinkage intensity parameter.

### 3. Departures from Gaussian Normality
Markowitz optimization relies on the implicit assumption that asset return distributions are completely characterized by their first two moments. This holds true if:
1. Investor utility functions are strictly quadratic ($U(W) = W - \frac{b}{2}W^2$), which introduces the absurd economic implication of satiation and negative marginal utility beyond $W = 1/b$; or
2. Asset returns follow an elliptical distribution (such as the multivariate normal).

Empirical financial time series systematically violate multivariate normality. Asset returns exhibit pronounced **leptokurtosis** (fat tails), negative skewness (asymmetric crash risk), and time-varying conditional volatility regimes (heteroskedasticity). When fat-tailed distributions dominate, variance severely underestimates tail risk, necessitating modern extensions such as Conditional Value-at-Risk (CVaR / Expected Shortfall) optimization and higher-moment tensor expansions.