---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f: [a, b] \to \mathbb{R}$ be a bounded function, so that there exists a constant $M > 0$ satisfying $|f(x)| \le M$ for all $x \in [a, b]$, and assume that the set of discontinuity points of $f$ in $[a, b]$, denoted $D$, is finite:
$$
\begin{gather}
D = \{c_1, c_2, \dots, c_p\} \subset [a, b] \tag{1}
\end{gather}
$$
where $p := |D| \in \mathbb{N}_0$.

If $p = 0$, then $D = \emptyset$, meaning that $f$ has no points of discontinuity on $[a, b]$. In this case, $f \in C[a, b]$, and the Integrability of Continuous Functions on Compact Intervals ([[Proof of the Integrability of Continuous Functions on Compact Intervals]]) immediately guarantees that $f \in \mathcal{R}[a, b]$.

Assume therefore that $p \ge 1$.

Because $|f(x)| \le M$ for all $x \in [a, b]$, for any non-empty subset $E \subseteq [a, b]$ the oscillation of $f$ on $E$ is bounded by:
$$
\begin{gather}
\omega(f; E) = \sup_{x \in E} f(x) - \inf_{x \in E} f(x) \le M - (-M) = 2M \tag{2}
\end{gather}
$$

Let $\varepsilon > 0$ be arbitrary. 

Choose a positive radius $\eta > 0$ satisfying the strict upper bound:
$$
\begin{gather}
\eta < \frac{\varepsilon}{8 p M} \tag{3}
\end{gather}
$$
and, if $p \ge 2$, also choose $\eta$ small enough so that:
$$
\begin{gather}
\eta < \frac{1}{2} \min_{1 \le j < k \le p} |c_j - c_k| \tag{4}
\end{gather}
$$

For each $k \in \{1, \dots, p\}$, define the singular isolating interval:
$$
\begin{gather}
J_k := [c_k - \eta, c_k + \eta] \cap [a, b] \tag{5}
\end{gather}
$$

Because of step 4, the open intervals $(c_k - \eta, c_k + \eta)$ are pairwise disjoint for distinct indices $k \in \{1, \dots, p\}$. The length of each interval $J_k$ is at most $2\eta$:
$$
\begin{gather}
\text{length}(J_k) \le 2\eta \tag{6}
\end{gather}
$$

Summing the lengths across all $p$ singular intervals and using step 3:
$$
\begin{gather}
\sum_{k=1}^p \text{length}(J_k) \le 2 p \eta < 2 p \left( \frac{\varepsilon}{8 p M} \right) = \frac{\varepsilon}{4M} \tag{7}
\end{gather}
$$

Now consider the complement of the interiors of the singular intervals in $[a, b]$:
$$
\begin{gather}
E := [a, b] \setminus \bigcup_{k=1}^p (c_k - \eta, c_k + \eta) \tag{8}
\end{gather}
$$

Because $[a, b]$ is compact and $\bigcup_{k=1}^p (c_k - \eta, c_k + \eta)$ is open in $[a, b]$, the set $E$ is a compact subset of $\mathbb{R}$. The set $E$ decomposes into a finite union of $m$ non-overlapping compact intervals:
$$
\begin{gather}
E = \bigcup_{j=1}^m K_j \tag{9}
\end{gather}
$$
where $m \le p + 1$, and each $K_j = [u_j, v_j]$ contains no discontinuity points of $f$. 

Consequently, $f$ is continuous on each compact interval $K_j$. By the Heine-Cantor Theorem, $f$ is uniformly continuous on each $K_j$. Because there are only finitely many such intervals, there exists a common modulus of continuity $\delta > 0$ such that for every $j \in \{1, \dots, m\}$ and for all $x', x'' \in K_j$:
$$
\begin{gather}
|x' - x''| < \delta \implies |f(x') - f(x'')| < \frac{\varepsilon}{2(b - a)} \tag{10}
\end{gather}
$$

Construct a partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ by taking the union of the endpoints of all singular intervals $J_k$, and further partitioning each continuous interval $K_j$ into subintervals of length strictly less than $\delta$.

By construction, each subinterval $\Delta_i = [x_{i-1}, x_i]$ of $P$ falls into exactly one of two mutually disjoint index sets:
$$
\begin{gather}
\mathcal{I}_1 := \big\{ i \in \{1, \dots, n\} : \Delta_i \subseteq J_k \text{ for some } k \in \{1, \dots, p\} \big\} \tag{11}
\end{gather}
$$
and
$$
\begin{gather}
\mathcal{I}_2 := \big\{ i \in \{1, \dots, n\} : \Delta_i \subseteq K_j \text{ for some } j \in \{1, \dots, m\} \big\} \tag{12}
\end{gather}
$$

The total Darboux oscillation sum across $P$ decomposes into:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i \in \mathcal{I}_1} \omega(f; \Delta_i) \Delta x_i + \sum_{i \in \mathcal{I}_2} \omega(f; \Delta_i) \Delta x_i \tag{13}
\end{gather}
$$

For each $i \in \mathcal{I}_1$, the oscillation is bounded by the global bound from step 2: $\omega(f; \Delta_i) \le 2M$. Because the subintervals for $i \in \mathcal{I}_1$ partition $\bigcup_{k=1}^p J_k$, the sum of their lengths satisfies:
$$
\begin{gather}
\sum_{i \in \mathcal{I}_1} \Delta x_i = \sum_{k=1}^p \text{length}(J_k) < \frac{\varepsilon}{4M} \tag{14}
\end{gather}
$$
where the strict inequality follows from step 7. Therefore:
$$
\begin{gather}
\sum_{i \in \mathcal{I}_1} \omega(f; \Delta_i) \Delta x_i \le 2M \sum_{i \in \mathcal{I}_1} \Delta x_i < 2M \left( \frac{\varepsilon}{4M} \right) = \frac{\varepsilon}{2} \tag{15}
\end{gather}
$$

For each $i \in \mathcal{I}_2$, the subinterval $\Delta_i$ is contained in some $K_j$ and has length $\Delta x_i < \delta$. The uniform continuity condition of step 10 ensures that:
$$
\begin{gather}
\omega(f; \Delta_i) = \sup_{x', x'' \in \Delta_i} |f(x') - f(x'')| \le \frac{\varepsilon}{2(b - a)} \tag{16}
\end{gather}
$$

Summing across all $i \in \mathcal{I}_2$:
$$
\begin{gather}
\sum_{i \in \mathcal{I}_2} \omega(f; \Delta_i) \Delta x_i \le \frac{\varepsilon}{2(b - a)} \sum_{i \in \mathcal{I}_2} \Delta x_i \le \frac{\varepsilon}{2(b - a)} (b - a) = \frac{\varepsilon}{2} \tag{17}
\end{gather}
$$

Substituting the bounds from step 15 and step 17 into the decomposition of step 13:
$$
\begin{gather}
S(f; P) - s(f; P) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{18}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a partition $P$ satisfying $S(f; P) - s(f; P) < \varepsilon$, the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]) establishes that $f \in \mathcal{R}[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
