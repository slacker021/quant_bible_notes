---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be a monotonic function on $[a, b]$.

Without loss of generality, assume that $f$ is non-decreasing on $[a, b]$, meaning:
$$
\begin{gather}
x \le y \implies f(x) \le f(y) \tag{1}
\end{gather}
$$
for all $x, y \in [a, b]$. If $f$ is non-increasing, the function $g := -f$ is non-decreasing, and the linearity of Riemann integrability ensures that $f \in \mathcal{R}[a, b]$ if and only if $g \in \mathcal{R}[a, b]$.

Because $f$ is non-decreasing, for every $x \in [a, b]$:
$$
\begin{gather}
f(a) \le f(x) \le f(b) \tag{2}
\end{gather}
$$
which implies that $f$ is bounded on $[a, b]$ with:
$$
\begin{gather}
\sup_{x \in [a, b]} |f(x)| \le \max\big( |f(a)|, |f(b)| \big) < \infty \tag{3}
\end{gather}
$$
---
# Case 1
If $f(a) = f(b)$, the inequality of step 2 implies $f(x) = f(a)$ for all $x \in [a, b]$. The function $f$ is constant, hence continuous on $[a, b]$. By the Integrability of Continuous Functions on Compact Intervals ([[Proof of the Integrability of Continuous Functions on Compact Intervals]]), every continuous function on $[a, b]$ belongs to $\mathcal{R}[a, b]$.

---
# Case 2
Assume $f(a) < f(b)$, so that $f(b) - f(a) > 0$.

Let $\varepsilon > 0$ be arbitrary. Define the gauge fineness threshold:
$$
\begin{gather}
\delta := \frac{\varepsilon}{f(b) - f(a)} > 0 \tag{4}
\end{gather}
$$

Select an arbitrary partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ whose mesh fineness satisfies:
$$
\begin{gather}
\lambda(P) := \max_{1 \le i \le n} \Delta x_i < \delta \tag{5}
\end{gather}
$$

On each subinterval $\Delta_i = [x_{i-1}, x_i]$, because $f$ is non-decreasing, the minimum is attained at the left endpoint and the maximum at the right endpoint:
$$
\begin{gather}
m_i := \inf_{x \in \Delta_i} f(x) = f(x_{i-1}) \quad \text{and} \quad M_i := \sup_{x \in \Delta_i} f(x) = f(x_i) \tag{6}
\end{gather}
$$

The local oscillation of $f$ on $\Delta_i$ is therefore:
$$
\begin{gather}
\omega(f; \Delta_i) = M_i - m_i = f(x_i) - f(x_{i-1}) \ge 0 \tag{7}
\end{gather}
$$

Compute the total Darboux oscillation sum across the partition $P$:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i = \sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) \Delta x_i \tag{8}
\end{gather}
$$

Because $\Delta x_i \le \lambda(P)$ and $f(x_i) - f(x_{i-1}) \ge 0$ for every $i \in \{1, \dots, n\}$:
$$
\begin{gather}
\sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) \Delta x_i \le \sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) \lambda(P) = \lambda(P) \sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) \tag{9}
\end{gather}
$$

The summation in step 9 telescopes:
$$
\begin{gather}
\sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) = \big( f(x_1) - f(x_0) \big) + \big( f(x_2) - f(x_1) \big) + \dots + \big( f(x_n) - f(x_{n-1}) \big) = f(x_n) - f(x_0) \tag{10}
\end{gather}
$$

Because $x_0 = a$ and $x_n = b$, step 10 becomes:
$$
\begin{gather}
\sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) = f(b) - f(a) \tag{11}
\end{gather}
$$

Combining step 8, step 9, and step 11:
$$
\begin{gather}
S(f; P) - s(f; P) \le \lambda(P) \big( f(b) - f(a) \big) \tag{12}
\end{gather}
$$

Substituting the condition $\lambda(P) < \delta$ from step 5 and the definition of $\delta$ from step 4 into step 12:
$$
\begin{gather}
S(f; P) - s(f; P) < \delta \big( f(b) - f(a) \big) = \left( \frac{\varepsilon}{f(b) - f(a)} \right) \big( f(b) - f(a) \big) = \varepsilon \tag{13}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a partition $P$ satisfying $S(f; P) - s(f; P) < \varepsilon$, the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]) establishes that $f \in \mathcal{R}[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
