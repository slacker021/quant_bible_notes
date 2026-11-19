---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f, g: [a, \infty) \to \mathbb{R}$ be functions satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B], \quad g \in C^1[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Because $g$ is continuous on $[a, B]$, $g \in \mathcal{R}[a, B]$. The product of two Riemann integrable functions is Riemann integrable, and therefore:
$$
\begin{gather}
fg \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{2}
\end{gather}
$$
Assume that the following two hypotheses are satisfied:
1. The primitive of $f$ is uniformly bounded on $[a, \infty)$:
$$
\begin{gather}
\exists M > 0 \quad \text{such that} \quad \left| \int_a^u f(t)\,dt \right| \le M \quad \text{for all } u \ge a \tag{3}
\end{gather}
$$
2. The function $g$ is monotonic on $[a, \infty)$ and vanishes at infinity:
$$
\begin{gather}
\lim_{x \to \infty} g(x) = 0 \tag{4}
\end{gather}
$$
---
# Step 1
Define the accumulation function $F: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
F(u) := \int_a^u f(t)\,dt \tag{5}
\end{gather}
$$
By hypothesis step 3, $|F(u)| \le M$ for all $u \ge a$.

Let $B_1, B_2 \in [a, \infty)$ satisfy $B_1 \le B_2$. By the interval additivity of the Riemann integral:
$$
\begin{gather}
\int_{B_1}^{B_2} f(t)\,dt = \int_a^{B_2} f(t)\,dt - \int_a^{B_1} f(t)\,dt = F(B_2) - F(B_1) \tag{6}
\end{gather}
$$

Applying the triangle inequality to step 6:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(t)\,dt \right| \le |F(B_2)| + |F(B_1)| \le M + M = 2M \tag{7}
\end{gather}
$$
---
# Step 2
The monotonicity of $g$ combined with $\lim_{x \to \infty} g(x) = 0$ determines the sign of $g$:
1. If $g$ is monotonically decreasing (non-increasing), then $g(x) \ge 0$ for all $x \ge a$. Suppose for contradiction that there existed $x_0 \ge a$ with $g(x_0) < 0$. Then for all $x \ge x_0$, monotonicity would imply $g(x) \le g(x_0) < 0$, which contradicts $\lim_{x \to \infty} g(x) = 0$.
2. If $g$ is monotonically increasing (non-decreasing), then $g(x) \le 0$ for all $x \ge a$. Suppose for contradiction that there existed $x_0 \ge a$ with $g(x_0) > 0$. Then for all $x \ge x_0$, monotonicity would imply $g(x) \ge g(x_0) > 0$, which contradicts $\lim_{x \to \infty} g(x) = 0$.

In both cases, $g(x)$ maintains a constant weak sign on $[a, \infty)$, and $|g(x)|$ is monotonically non-increasing to $0$.

---
# Step 3

Let $B_1, B_2 \in [a, \infty)$ satisfy $a \le B_1 < B_2$.

Consider first the case where $g$ is monotonically non-increasing. By step 2, $g(x) \ge 0$ for all $x \in [B_1, B_2]$. The function $g$ restricted to $[B_1, B_2]$ is non-negative and monotonic decreasing.

By Bonnet's form of the Second Mean-Value Theorem for Integrals, there exists an intermediate point $\xi \in [B_1, B_2]$ such that:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)g(x)\,dx = g(B_1) \int_{B_1}^\xi f(x)\,dx \tag{8}
\end{gather}
$$

Consider next the case where $g$ is monotonically non-decreasing. By step 2, the negated function $-g(x) \ge 0$ is non-negative and monotonically non-increasing on $[B_1, B_2]$. Applying Bonnet's theorem to $(-g(x))f(x)$:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)\big( -g(x) \big)\,dx = \big( -g(B_1) \big) \int_{B_1}^\xi f(x)\,dx \tag{9}
\end{gather}
$$
Multiplying step 9 by $-1$ recovers the identical relation:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)g(x)\,dx = g(B_1) \int_{B_1}^\xi f(x)\,dx \tag{10}
\end{gather}
$$

Thus, step 10 holds universally for some intermediate point $\xi \in [B_1, B_2]$.

Taking the absolute value of both sides of step 10:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| = |g(B_1)| \left| \int_{B_1}^\xi f(x)\,dx \right| \tag{11}
\end{gather}
$$

Because $B_1 \le \xi \le B_2$, applying the uniform primitive bound of step 7 evaluated across $[B_1, \xi]$ yields:
$$
\begin{gather}
\left| \int_{B_1}^\xi f(x)\,dx \right| \le 2M \tag{12}
\end{gather}
$$

Substituting step 12 into step 11:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le 2M |g(B_1)| \tag{13}
\end{gather}
$$
---
# Step 4
An independent deduction proceeds by integration by parts for $g \in C^1[a, \infty)$. Define $v(x) := \int_{B_1}^x f(t)\,dt$, so that $v(B_1) = 0$ and $v'(x) = f(x)$ almost everywhere. Applying integration by parts across $[B_1, B_2]$:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)g(x)\,dx = \left[ g(x) \int_{B_1}^x f(t)\,dt \right]_{B_1}^{B_2} - \int_{B_1}^{B_2} g'(x) \left( \int_{B_1}^x f(t)\,dt \right) dx \tag{14}
\end{gather}
$$

Because the evaluation at $x = B_1$ vanishes identically, step 14 simplifies to:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)g(x)\,dx = g(B_2) \int_{B_1}^{B_2} f(t)\,dt - \int_{B_1}^{B_2} g'(x) \left( \int_{B_1}^x f(t)\,dt \right) dx \tag{15}
\end{gather}
$$

Applying the triangle inequality to step 15:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le |g(B_2)| \left| \int_{B_1}^{B_2} f(t)\,dt \right| + \int_{B_1}^{B_2} |g'(x)| \left| \int_{B_1}^x f(t)\,dt \right| dx \tag{16}
\end{gather}
$$

Substituting the uniform bound $|\int_{B_1}^x f(t)\,dt| \le 2M$ from step 7 into step 16:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le 2M |g(B_2)| + 2M \int_{B_1}^{B_2} |g'(x)|\,dx \tag{17}
\end{gather}
$$

Because $g$ is monotonic on $[B_1, B_2]$, the derivative $g'(x)$ does not change sign on $(B_1, B_2)$. Therefore:
$$
\begin{gather}
\int_{B_1}^{B_2} |g'(x)|\,dx = \left| \int_{B_1}^{B_2} g'(x)\,dx \right| = |g(B_2) - g(B_1)| \tag{18}
\end{gather}
$$

Substituting step 18 into step 17:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le 2M |g(B_2)| + 2M |g(B_2) - g(B_1)| \tag{19}
\end{gather}
$$

Applying the triangle inequality $|g(B_2) - g(B_1)| \le |g(B_2)| + |g(B_1)|$ to step 19:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le 2M \big( 2|g(B_2)| + |g(B_1)| \big) \tag{20}
\end{gather}
$$
---
# Step 5
Let $\varepsilon > 0$ be arbitrary.

By hypothesis step 4, $\lim_{x \to \infty} g(x) = 0$. By definition of the limit at infinity, there exists an exhaustion threshold $B_0 \ge a$ such that:
$$
\begin{gather}
x \ge B_0 \implies |g(x)| < \frac{\varepsilon}{2M} \tag{21}
\end{gather}
$$

Let $B_1, B_2$ be arbitrary parameters satisfying $B_2 > B_1 \ge B_0$.

Evaluating the Bonnet bound from step 13 with $B_1 \ge B_0$:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le 2M |g(B_1)| < 2M \cdot \frac{\varepsilon}{2M} = \varepsilon \tag{22}
\end{gather}
$$

(Similarly, using the integration by parts bound from step 20 with $B_1, B_2 \ge B_0$ chosen such that $|g(x)| < \frac{\varepsilon}{6M}$ yields an identical verification: $2M(2 \cdot \frac{\varepsilon}{6M} + \frac{\varepsilon}{6M}) = \varepsilon$).

Because for every $\varepsilon > 0$ there exists an exhaustion threshold $B_0 \ge a$ such that step 22 holds for all $B_2 > B_1 \ge B_0$, the integrand $fg$ satisfies the Cauchy Criterion for improper integrals.

By the Cauchy Criterion for Convergence of Improper Integrals, the improper integral converges to a finite real value:
$$
\begin{gather}
\int_a^\infty f(x)g(x)\,dx = \lim_{B \to \infty} \int_a^B f(x)g(x)\,dx \in \mathbb{R} \tag{23}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
