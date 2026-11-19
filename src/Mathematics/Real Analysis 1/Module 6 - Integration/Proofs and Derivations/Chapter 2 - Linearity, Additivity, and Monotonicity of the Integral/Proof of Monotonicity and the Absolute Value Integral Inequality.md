---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ with $a \le b$, and let $f, g \in \mathcal{R}[a, b]$.

---
# Theorem 1
If $a = b$, the integral collapses to a degenerate interval, yielding $\int_a^a f(x)\,dx = 0 \ge 0$.

Assume $a < b$ and suppose $f(x) \ge 0$ for all $x \in [a, b]$.

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$, and let $\xi = (\xi_1, \dots, \xi_n)$ be intermediate evaluation nodes with $\xi_i \in [x_{i-1}, x_i]$ for each $i \in \{1, \dots, n\}$. Let $\Delta x_i := x_i - x_{i-1} > 0$.

Because $\xi_i \in [a, b]$, the hypothesis guarantees $f(\xi_i) \ge 0$. The product of non-negative real numbers is non-negative, so $f(\xi_i) \Delta x_i \ge 0$ for each $i$. Summing these terms yields:
$$
\begin{gather}
\sigma(f; P, \xi) = \sum_{i=1}^n f(\xi_i) \Delta x_i \ge 0 \tag{1}
\end{gather}
$$

Because $f \in \mathcal{R}[a, b]$, the definite integral is the limit of the Riemann sums as the mesh $\lambda(P) := \max_{1 \le i \le n} \Delta x_i \to 0$:
$$
\begin{gather}
\int_a^b f(x)\,dx = \lim_{\lambda(P) \to 0} \sigma(f; P, \xi) \tag{2}
\end{gather}
$$

By the order-preservation property of limits of real sequences and nets, because every Riemann sum satisfies $\sigma(f; P, \xi) \ge 0$ in step 1, the limit must also be non-negative:
$$
\begin{gather}
\int_a^b f(x)\,dx \ge 0 \tag{3}
\end{gather}
$$
---
# Theorem 2
Assume $f \in C[a, b]$, $f(x) \ge 0$ for all $x \in [a, b]$, and there exists a point $x_0 \in [a, b]$ such that $f(x_0) > 0$.

Define the positive parameter:
$$
\begin{gather}
\varepsilon_0 := \frac{f(x_0)}{2} > 0 \tag{4}
\end{gather}
$$

Because $f$ is continuous on $[a, b]$, it is continuous at $x_0$. By definition of continuity, there exists a radius $\delta > 0$ such that for all $x \in [a, b]$ satisfying $|x - x_0| < \delta$:
$$
\begin{gather}
|f(x) - f(x_0)| < \varepsilon_0 = \frac{f(x_0)}{2} \tag{5}
\end{gather}
$$

The absolute value inequality of step 5 implies:
$$
\begin{gather}
f(x) > f(x_0) - \frac{f(x_0)}{2} = \frac{f(x_0)}{2} > 0 \tag{6}
\end{gather}
$$
for all $x \in [a, b] \cap (x_0 - \delta, x_0 + \delta)$.

Define the compact subinterval $[u, v] \subset [a, b]$ by:
$$
\begin{gather}
[u, v] := [a, b] \cap [x_0 - \delta/2, x_0 + \delta/2] \tag{7}
\end{gather}
$$

Because $x_0 \in [a, b]$ and $\delta > 0$, the interval $[u, v]$ contains $x_0$ and has strictly positive length:
$$
\begin{gather}
\ell := v - u > 0 \tag{8}
\end{gather}
$$

By step 6, the lower bound $f(x) \ge \frac{f(x_0)}{2}$ holds for all $x \in [u, v]$.

By the Interval Additivity Theorem ([[Proof of Interval Additivity of the Definite Integral]]), the integral across $[a, b]$ decomposes into three sub-integrals:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^u f(x)\,dx + \int_u^v f(x)\,dx + \int_v^b f(x)\,dx \tag{9}
\end{gather}
$$

Because $f(x) \ge 0$ on $[a, u]$ and $[v, b]$, Part 1 ensures:
$$
\begin{gather}
\int_a^u f(x)\,dx \ge 0, \qquad \int_v^b f(x)\,dx \ge 0 \tag{10}
\end{gather}
$$

For the integral over $[u, v]$, the function $h(x) := f(x) - \frac{f(x_0)}{2}$ is continuous and satisfies $h(x) \ge 0$ on $[u, v]$. By Part 1 and the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]):
$$
\begin{gather}
\int_u^v f(x)\,dx - \frac{f(x_0)}{2}(v - u) = \int_u^v \left( f(x) - \frac{f(x_0)}{2} \right) dx \ge 0 \tag{11}
\end{gather}
$$
which yields:
$$
\begin{gather}
\int_u^v f(x)\,dx \ge \frac{f(x_0)}{2}(v - u) = \frac{f(x_0)}{2}\ell > 0 \tag{12}
\end{gather}
$$

Substituting step 10 and step 12 into step 9:
$$
\begin{gather}
\int_a^b f(x)\,dx \ge 0 + \frac{f(x_0)}{2}\ell + 0 = \frac{f(x_0)}{2}\ell > 0 \tag{13}
\end{gather}
$$
which establishes strict positivity.

---
# Theorem 3
Suppose $f, g \in \mathcal{R}[a, b]$ satisfy $f(x) \le g(x)$ for all $x \in [a, b]$.

Define the difference function $h: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
h(x) := g(x) - f(x) \tag{14}
\end{gather}
$$

Because $f(x) \le g(x)$, the difference satisfies $h(x) \ge 0$ for all $x \in [a, b]$.

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), $h \in \mathcal{R}[a, b]$ and:
$$
\begin{gather}
\int_a^b h(x)\,dx = \int_a^b g(x)\,dx - \int_a^b f(x)\,dx \tag{15}
\end{gather}
$$

Applying Part 1 to the non-negative function $h$:
$$
\begin{gather}
\int_a^b h(x)\,dx \ge 0 \tag{16}
\end{gather}
$$

Substituting step 15 into step 16:
$$
\begin{gather}
\int_a^b g(x)\,dx - \int_a^b f(x)\,dx \ge 0 \implies \int_a^b f(x)\,dx \le \int_a^b g(x)\,dx \tag{17}
\end{gather}
$$
---
# Theorem 4
Suppose $m \le f(x) \le M$ for all $x \in [a, b]$.

The constant functions $g_1(x) := m$ and $g_2(x) := M$ are continuous on $[a, b]$, hence belong to $\mathcal{R}[a, b]$. Their integrals evaluate directly to:
$$
\begin{gather}
\int_a^b m\,dx = m(b - a), \qquad \int_a^b M\,dx = M(b - a) \tag{18}
\end{gather}
$$

Because $m \le f(x)$ for all $x \in [a, b]$, applying Part 3 to $g_1$ and $f$ yields:
$$
\begin{gather}
\int_a^b m\,dx \le \int_a^b f(x)\,dx \implies m(b - a) \le \int_a^b f(x)\,dx \tag{19}
\end{gather}
$$

Because $f(x) \le M$ for all $x \in [a, b]$, applying Part 3 to $f$ and $g_2$ yields:
$$
\begin{gather}
\int_a^b f(x)\,dx \le \int_a^b M\,dx \implies \int_a^b f(x)\,dx \le M(b - a) \tag{20}
\end{gather}
$$

Combining step 19 and step 20:
$$
\begin{gather}
m(b - a) \le \int_a^b f(x)\,dx \le M(b - a) \tag{21}
\end{gather}
$$
---
# Theorem 5
Suppose $f \in \mathcal{R}[a, b]$.

By the Necessity of Boundedness for Riemann Integrability ([[Proof of the Necessity of Boundedness for Riemann Integrability]]), $f$ is bounded on $[a, b]$, so there exists a constant $K > 0$ such that $f([a, b]) \subseteq [-K, K]$.

Define the real function $\phi: [-K, K] \to \mathbb{R}$ by:
$$
\begin{gather}
\phi(t) := |t| \tag{22}
\end{gather}
$$

By the reverse triangle inequality, for all $t_1, t_2 \in [-K, K]$:
$$
\begin{gather}
|\phi(t_1) - \phi(t_2)| = ||t_1| - |t_2|| \le |t_1 - t_2| \tag{23}
\end{gather}
$$
which demonstrates that $\phi$ is 1-Lipschitz continuous on $[-K, K]$.

By the Continuous Composition Integrability Theorem ([[Proof of the Continuous Composition Integrability Theorem]]), the composite function $(\phi \circ f)$ belongs to $\mathcal{R}[a, b]$:
$$
\begin{gather}
|f| = \phi \circ f \in \mathcal{R}[a, b] \tag{24}
\end{gather}
$$

By the definition of absolute value, for all $x \in [a, b]$:
$$
\begin{gather}
-|f(x)| \le f(x) \le |f(x)| \tag{25}
\end{gather}
$$

Applying Part 3 to the left-hand inequality of step 25:
$$
\begin{gather}
\int_a^b \big( -|f(x)| \big)\,dx \le \int_a^b f(x)\,dx \tag{26}
\end{gather}
$$

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), $\int_a^b (-|f(x)|)\,dx = -\int_a^b |f(x)|\,dx$. Therefore:
$$
\begin{gather}
-\int_a^b |f(x)|\,dx \le \int_a^b f(x)\,dx \tag{27}
\end{gather}
$$

Applying Part 3 to the right-hand inequality of step 25:
$$
\begin{gather}
\int_a^b f(x)\,dx \le \int_a^b |f(x)|\,dx \tag{28}
\end{gather}
$$

Combining step 27 and step 28:
$$
\begin{gather}
-\int_a^b |f(x)|\,dx \le \int_a^b f(x)\,dx \le \int_a^b |f(x)|\,dx \tag{29}
\end{gather}
$$

For any real numbers $A, B$, the condition $-B \le A \le B$ is logically equivalent to $|A| \le B$. Applying this algebraic equivalence to step 29 yields:
$$
\begin{gather}
\left| \int_a^b f(x)\,dx \right| \le \int_a^b |f(x)|\,dx \tag{30}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
