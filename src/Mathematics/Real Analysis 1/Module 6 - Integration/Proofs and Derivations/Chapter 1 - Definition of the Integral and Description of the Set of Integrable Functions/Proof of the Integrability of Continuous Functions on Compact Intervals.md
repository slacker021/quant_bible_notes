---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be a continuous function on $[a, b]$, denoted $f \in C[a, b]$.

By the Extreme Value Theorem (Weierstrass Theorem), a continuous function on a compact set is bounded and attains its global infimum and supremum. Consequently, $f$ is bounded on $[a, b]$, meaning:
$$
\begin{gather}
M := \sup_{x \in [a, b]} |f(x)| < \infty \tag{1}
\end{gather}
$$

Furthermore, for any subinterval $\Delta_i = [x_{i-1}, x_i] \subseteq [a, b]$, the restriction $\left. f \right|_{\Delta_i}$ is continuous on the compact interval $\Delta_i$. By the Extreme Value Theorem, there exist points $u_i, v_i \in \Delta_i$ at which the supremum and infimum are attained:
$$
\begin{gather}
M_i := \sup_{x \in \Delta_i} f(x) = f(u_i) \quad \text{and} \quad m_i := \inf_{x \in \Delta_i} f(x) = f(v_i) \tag{2}
\end{gather}
$$

The local oscillation of $f$ on $\Delta_i$ is therefore expressed as:
$$
\begin{gather}
\omega(f; \Delta_i) = M_i - m_i = f(u_i) - f(v_i) \tag{3}
\end{gather}
$$

Let $\varepsilon > 0$ be arbitrary. 

Because $[a, b]$ is compact and $f$ is continuous, the Heine-Cantor Theorem dictates that $f$ is uniformly continuous on $[a, b]$. 

By the definition of uniform continuity, corresponding to the strictly positive quantity:
$$
\begin{gather}
\eta := \frac{\varepsilon}{b - a} > 0 \tag{4}
\end{gather}
$$
there exists a uniform modulus of continuity $\delta > 0$ such that for all points $x', x'' \in [a, b]$:
$$
\begin{gather}
|x' - x''| < \delta \implies |f(x') - f(x'')| < \frac{\varepsilon}{b - a} \tag{5}
\end{gather}
$$

Select an arbitrary partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ whose mesh fineness satisfies:
$$
\begin{gather}
\lambda(P) := \max_{1 \le i \le n} \Delta x_i < \delta \tag{6}
\end{gather}
$$

For each $i \in \{1, \dots, n\}$, both points $u_i$ and $v_i$ belong to the subinterval $\Delta_i = [x_{i-1}, x_i]$. Consequently, their distance is bounded by the subinterval length:
$$
\begin{gather}
|u_i - v_i| \le x_i - x_{i-1} = \Delta x_i \le \lambda(P) < \delta \tag{7}
\end{gather}
$$

Applying the uniform continuity implication of step 5 to the pair $u_i, v_i$ in step 7:
$$
\begin{gather}
|f(u_i) - f(v_i)| < \frac{\varepsilon}{b - a} \tag{8}
\end{gather}
$$

Because $f(u_i) = M_i \ge m_i = f(v_i)$, combining step 3 and step 8 yields the local oscillation bound:
$$
\begin{gather}
\omega(f; \Delta_i) = f(u_i) - f(v_i) < \frac{\varepsilon}{b - a} \tag{9}
\end{gather}
$$
for every $i \in \{1, \dots, n\}$.

Compute the total Darboux oscillation sum across the partition $P$:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i \tag{10}
\end{gather}
$$

Substituting the uniform upper bound from step 9 into step 10:
$$
\begin{gather}
S(f; P) - s(f; P) < \sum_{i=1}^n \left( \frac{\varepsilon}{b - a} \right) \Delta x_i = \frac{\varepsilon}{b - a} \sum_{i=1}^n \Delta x_i \tag{11}
\end{gather}
$$

Because the partition subintervals tile the entire interval $[a, b]$, the sum of their lengths telescopes:
$$
\begin{gather}
\sum_{i=1}^n \Delta x_i = \sum_{i=1}^n (x_i - x_{i-1}) = x_n - x_0 = b - a \tag{12}
\end{gather}
$$

Substituting step 12 into step 11:
$$
\begin{gather}
S(f; P) - s(f; P) < \frac{\varepsilon}{b - a} (b - a) = \varepsilon \tag{13}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a partition $P$ satisfying $S(f; P) - s(f; P) < \varepsilon$, the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]) establishes that $f \in \mathcal{R}[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
