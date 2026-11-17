---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f: [a, b] \to \mathbb{R}$ be a bounded function, so that $M := \sup_{x \in [a, b]} |f(x)| < \infty$, and let $\overline{I}(f) := \inf_P S(f; P)$ and $\underline{I}(f) := \sup_P s(f; P)$ denote the upper and lower Darboux integrals of $f$ on $[a, b]$, respectively.

If $M = 0$, then $f(x) = 0$ for all $x \in [a, b]$. In this setting, for every partition $P$, $S(f; P) = 0$ and $s(f; P) = 0$, which implies $\overline{I}(f) = 0$ and $\underline{I}(f) = 0$. For every $\varepsilon > 0$, the relations $|S(f; P) - \overline{I}(f)| = 0 < \varepsilon$ and $|s(f; P) - \underline{I}(f)| = 0 < \varepsilon$ hold for every partition $P$ irrespective of the mesh $\lambda(P)$, establishing convergence directly with identical zero limits. Hence, assume without loss of generality that $M > 0$.

---
# Part l
Let $\varepsilon > 0$ be arbitrary.

By the characterization of the infimum $\overline{I}(f) = \inf_P S(f; P)$, the quantity $\overline{I}(f) + \frac{\varepsilon}{2}$ is strictly greater than the infimum. Therefore, there exists a fixed partition $P_0$ of $[a, b]$, say $P_0 = \{y_0, y_1, \dots, y_p\}$ with:
$$
\begin{gather}
a = y_0 < y_1 < \dots < y_{p-1} < y_p = b \tag{1}
\end{gather}
$$
such that:
$$
\begin{gather}
S(f; P_0) < \overline{I}(f) + \frac{\varepsilon}{2} \tag{2}
\end{gather}
$$

The partition $P_0$ contains exactly $p - 1$ interior division points $\{y_1, \dots, y_{p-1}\}$. If $p = 1$, then $P_0 = \{a, b\}$ contains no interior points, meaning that every partition $P$ is already a refinement of $P_0$, whence $S(f; P) \le S(f; P_0) < \overline{I}(f) + \frac{\varepsilon}{2}$ holds for all $P$, and the result follows immediately. Assume therefore that $p \ge 2$, so that $p - 1 \ge 1$.

Define the mesh gauge threshold $\delta > 0$ by:
$$
\begin{gather}
\delta := \frac{\varepsilon}{4 (p - 1) M} > 0 \tag{3}
\end{gather}
$$

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ satisfying $\lambda(P) < \delta$.

Construct the common refinement:
$$
\begin{gather}
P^* := P \cup P_0 \tag{4}
\end{gather}
$$

Because $P_0 \subseteq P^*$, the Darboux Sum Monotonicity Under Refinement ([[Proof of the Darboux Sum Monotonicity Under Refinement]]) ensures that:
$$
\begin{gather}
S(f; P^*) \le S(f; P_0) \tag{5}
\end{gather}
$$

Combining step 5 with step 2:
$$
\begin{gather}
S(f; P^*) < \overline{I}(f) + \frac{\varepsilon}{2} \tag{6}
\end{gather}
$$

To compare $S(f; P)$ and $S(f; P^*)$, partition the index set $\{1, \dots, n\}$ of subintervals of $P$ into two disjoint collections:
$$
\begin{gather}
J_1 := \big\{ i \in \{1, \dots, n\} : (x_{i-1}, x_i) \cap P_0 = \emptyset \big\} \tag{7}
\end{gather}
$$
and
$$
\begin{gather}
J_2 := \big\{ i \in \{1, \dots, n\} : (x_{i-1}, x_i) \cap P_0 \neq \emptyset \big\} \tag{8}
\end{gather}
$$

Because the open subintervals $(x_{i-1}, x_i)$ are pairwise disjoint, each of the $p - 1$ interior points of $P_0$ can belong to at most one open subinterval $(x_{i-1}, x_i)$. Consequently:
$$
\begin{gather}
|J_2| \le p - 1 \tag{9}
\end{gather}
$$

For any index $i \in J_1$, the subinterval $\Delta_i = [x_{i-1}, x_i]$ contains no points of $P_0$ in its interior, so $\Delta_i$ is unbroken in the common refinement $P^*$. The contribution of $\Delta_i$ to $S(f; P)$ and to $S(f; P^*)$ is identical, namely $M_i \Delta x_i$.

For each index $i \in J_2$, the subinterval $\Delta_i = [x_{i-1}, x_i]$ is partitioned in $P^*$ into a finite collection of subsegments $\Delta_{i, 1}^*, \dots, \Delta_{i, k_i}^*$ with lengths $\Delta x_{i, r}^*$ satisfying:
$$
\begin{gather}
\sum_{r=1}^{k_i} \Delta x_{i, r}^* = \Delta x_i \tag{10}
\end{gather}
$$

Let $M_{i, r}^* := \sup_{x \in \Delta_{i, r}^*} f(x)$. Because $-M \le f(x) \le M$ for all $x \in [a, b]$, both $M_i \le M$ and $M_{i, r}^* \ge -M$ hold. Therefore:
$$
\begin{gather}
M_i - M_{i, r}^* \le M - (-M) = 2M \tag{11}
\end{gather}
$$

Using step 10 and step 11, the difference on the $i$-th subinterval is bounded by:
$$
\begin{gather}
M_i \Delta x_i - \sum_{r=1}^{k_i} M_{i, r}^* \Delta x_{i, r}^* = \sum_{r=1}^{k_i} (M_i - M_{i, r}^*) \Delta x_{i, r}^* \le 2M \sum_{r=1}^{k_i} \Delta x_{i, r}^* = 2M \Delta x_i \tag{12}
\end{gather}
$$

Summing the inequality of step 12 across all subintervals in $J_2$, and observing that subintervals in $J_1$ contribute zero difference:
$$
\begin{gather}
S(f; P) - S(f; P^*) = \sum_{i \in J_2} \left( M_i \Delta x_i - \sum_{r=1}^{k_i} M_{i, r}^* \Delta x_{i, r}^* \right) \le 2M \sum_{i \in J_2} \Delta x_i \tag{13}
\end{gather}
$$

Because $\lambda(P) < \delta$, each subinterval length satisfies $\Delta x_i \le \lambda(P) < \delta$. Applying the cardinality bound of step 9:
$$
\begin{gather}
\sum_{i \in J_2} \Delta x_i \le |J_2| \lambda(P) \le (p - 1) \lambda(P) < (p - 1) \delta \tag{14}
\end{gather}
$$

Substituting step 14 and the definition of $\delta$ from step 3 into step 13:
$$
\begin{gather}
S(f; P) - S(f; P^*) < 2M (p - 1) \left( \frac{\varepsilon}{4 (p - 1) M} \right) = \frac{\varepsilon}{2} \tag{15}
\end{gather}
$$

By definition of the upper Darboux integral as an infimum:
$$
\begin{gather}
\overline{I}(f) \le S(f; P) \tag{16}
\end{gather}
$$

Adding step 15 to step 6 yields:
$$
\begin{gather}
S(f; P) = S(f; P^*) + \big( S(f; P) - S(f; P^*) \big) < \left( \overline{I}(f) + \frac{\varepsilon}{2} \right) + \frac{\varepsilon}{2} = \overline{I}(f) + \varepsilon \tag{17}
\end{gather}
$$

Combining step 16 and step 17:
$$
\begin{gather}
\overline{I}(f) \le S(f; P) < \overline{I}(f) + \varepsilon \tag{18}
\end{gather}
$$
which establishes:
$$
\begin{gather}
|S(f; P) - \overline{I}(f)| < \varepsilon \tag{19}
\end{gather}
$$
for every partition $P$ with $\lambda(P) < \delta$. This confirms:
$$
\begin{gather}
\lim_{\lambda(P) \to 0} S(f; P) = \overline{I}(f) \tag{20}
\end{gather}
$$

---
# Part 2
Let $\varepsilon > 0$ be arbitrary.

By the characterization of the supremum $\underline{I}(f) = \sup_P s(f; P)$, the quantity $\underline{I}(f) - \frac{\varepsilon}{2}$ is strictly less than the supremum. Therefore, there exists a fixed partition $P_0 = \{y_0, y_1, \dots, y_p\}$ of $[a, b]$ with $p - 1$ interior points such that:
$$
\begin{gather}
s(f; P_0) > \underline{I}(f) - \frac{\varepsilon}{2} \tag{21}
\end{gather}
$$

With the same gauge threshold $\delta := \frac{\varepsilon}{4 (p - 1) M} > 0$ as in step 3, let $P$ be any partition of $[a, b]$ satisfying $\lambda(P) < \delta$, and form the common refinement $P^* = P \cup P_0$.

By the Darboux Sum Monotonicity Under Refinement ([[Proof of the Darboux Sum Monotonicity Under Refinement]]), because $P_0 \subseteq P^*$:
$$
\begin{gather}
s(f; P^*) \ge s(f; P_0) > \underline{I}(f) - \frac{\varepsilon}{2} \tag{22}
\end{gather}
$$

For subintervals in $J_1$, the contribution to the lower sum is identical in $P$ and $P^*$. For each index $i \in J_2$, let $m_{i, r}^* := \inf_{x \in \Delta_{i, r}^*} f(x)$. Because $m_{i, r}^* \le M$ and $m_i \ge -M$:
$$
\begin{gather}
m_{i, r}^* - m_i \le M - (-M) = 2M \tag{23}
\end{gather}
$$

Hence, the difference on the $i$-th subinterval satisfies:
$$
\begin{gather}
\sum_{r=1}^{k_i} m_{i, r}^* \Delta x_{i, r}^* - m_i \Delta x_i = \sum_{r=1}^{k_i} (m_{i, r}^* - m_i) \Delta x_{i, r}^* \le 2M \Delta x_i \tag{24}
\end{gather}
$$

Summing across all $i \in J_2$ and employing the bound from step 14:
$$
\begin{gather}
s(f; P^*) - s(f; P) \le 2M \sum_{i \in J_2} \Delta x_i < 2M (p - 1) \delta = \frac{\varepsilon}{2} \tag{25}
\end{gather}
$$

From step 22 and step 25:
$$
\begin{gather}
s(f; P) = s(f; P^*) - \big( s(f; P^*) - s(f; P) \big) > \left( \underline{I}(f) - \frac{\varepsilon}{2} \right) - \frac{\varepsilon}{2} = \underline{I}(f) - \varepsilon \tag{26}
\end{gather}
$$

By definition of the lower Darboux integral as a supremum:
$$
\begin{gather}
s(f; P) \le \underline{I}(f) \tag{27}
\end{gather}
$$

Combining step 26 and step 27:
$$
\begin{gather}
\underline{I}(f) - \varepsilon < s(f; P) \le \underline{I}(f) \tag{28}
\end{gather}
$$
which establishes:
$$
\begin{gather}
|s(f; P) - \underline{I}(f)| < \varepsilon \tag{29}
\end{gather}
$$
for every partition $P$ with $\lambda(P) < \delta$. This confirms:
$$
\begin{gather}
\lim_{\lambda(P) \to 0} s(f; P) = \underline{I}(f) \tag{30}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
