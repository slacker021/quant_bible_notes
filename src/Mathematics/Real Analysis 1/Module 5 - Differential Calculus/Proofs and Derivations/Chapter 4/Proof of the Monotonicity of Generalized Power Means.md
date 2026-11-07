---
dg-publish: true
---
Let $x = (x_1, \dots, x_n)$ with $x_i > 0$, and let $\alpha = (\alpha_1, \dots, \alpha_n)$ with $\alpha_i > 0$ and $\sum_{i=1}^n \alpha_i = 1$.

For $t \neq 0$, the power mean is defined by:
$$
\begin{gather}
M_t := \left( \sum_{i=1}^n \alpha_i x_i^t \right)^{1/t} \tag{1}
\end{gather}
$$

### Step 1: Continuity at $t = 0$
Taking the natural logarithm of $M_t$:
$$
\begin{gather}
\ln M_t = \frac{1}{t} \ln\left( \sum_{i=1}^n \alpha_i x_i^t \right) \tag{2}
\end{gather}
$$

As $t \to 0$, $\sum_{i=1}^n \alpha_i x_i^t \to \sum_{i=1}^n \alpha_i = 1$, so $\ln\left(\sum \alpha_i x_i^t\right) \to 0$. This represents an indeterminate form $\frac{0}{0}$.

Applying L'Hôpital's Rule with respect to $t$:
$$
\begin{gather}
\lim_{t \to 0} \ln M_t = \lim_{t \to 0} \frac{\frac{d}{dt}\ln\left( \sum_{i=1}^n \alpha_i x_i^t \right)}{\frac{d}{dt}(t)} = \lim_{t \to 0} \frac{\frac{\sum_{i=1}^n \alpha_i x_i^t \ln x_i}{\sum_{i=1}^n \alpha_i x_i^t}}{1} = \frac{\sum_{i=1}^n \alpha_i \ln x_i}{1} = \sum_{i=1}^n \alpha_i \ln x_i \tag{3}
\end{gather}
$$

Exponentiating equation (3):
$$
\begin{gather}
\lim_{t \to 0} M_t = \exp\left( \sum_{i=1}^n \alpha_i \ln x_i \right) = \prod_{i=1}^n x_i^{\alpha_i} = M_0 \tag{4}
\end{gather}
$$
proving that $t \mapsto M_t$ is continuous at $t = 0$.

### Step 2: Monotonicity for $0 < s < t$
Let $0 < s < t$. Define $p := \frac{t}{s} > 1$.
Consider the convex function $g(u) = u^p$ for $u \ge 0$. Because $p > 1$, $g''(u) = p(p-1)u^{p-2} > 0$ for $u > 0$, so $g$ is strictly convex.

Set $u_i := x_i^s$. Applying Jensen's Inequality to $g$:
$$
\begin{gather}
g\left( \sum_{i=1}^n \alpha_i u_i \right) \le \sum_{i=1}^n \alpha_i g(u_i) \tag{5}
\end{gather}
$$
with equality if and only if all $u_i$ are identical (all $x_i$ are identical).

Substituting $u_i = x_i^s$ and $g(u) = u^p = u^{t/s}$:
$$
\begin{gather}
\left( \sum_{i=1}^n \alpha_i x_i^s \right)^{t/s} \le \sum_{i=1}^n \alpha_i (x_i^s)^{t/s} = \sum_{i=1}^n \alpha_i x_i^t \tag{6}
\end{gather}
$$

Taking the $\frac{1}{t}$-th power on both sides (since $t > 0$, the mapping $y \mapsto y^{1/t}$ is strictly increasing):
$$
\begin{gather}
\left( \sum_{i=1}^n \alpha_i x_i^s \right)^{1/s} \le \left( \sum_{i=1}^n \alpha_i x_i^t \right)^{1/t} \implies M_s \le M_t \tag{7}
\end{gather}
$$

### Step 3: Monotonicity for Negative Exponents
For $s < t < 0$, setting $y_i = \frac{1}{x_i}$, we have $M_t(x; \alpha) = \frac{1}{M_{-t}(y; \alpha)}$. Because $-s > -t > 0$, Step 2 proves that $M_{-t}(y) \le M_{-s}(y) \implies \frac{1}{M_{-t}(y)} \ge \frac{1}{M_{-s}(y)} \implies M_t(x) \ge M_s(x)$, which is $M_s \le M_t$.

Combining with continuity at $t = 0$, $t \mapsto M_t(x; \alpha)$ is strictly increasing across all of $\mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
