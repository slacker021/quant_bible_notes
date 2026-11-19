---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f: [a, b] \to \mathbb{R}$ be a bounded function, and let $\underline{I}(f) := \sup_P s(f; P)$ and $\overline{I}(f) := \inf_P S(f; P)$ denote the lower and upper Darboux integrals of $f$ on $[a, b]$, respectively.

The logical equivalence of the four assertions is established by verifying the circular chain of implications:
$$
\begin{gather}
(1) \implies (3) \implies (2) \implies (4) \implies (1) \tag{1}
\end{gather}
$$
---
# Implication 1 implies 3
Assume that $f \in \mathcal{R}[a, b]$ with Riemann integral $I := \int_a^b f(x) \, dx \in \mathbb{R}$.

Let $\varepsilon > 0$ be arbitrary. By the definition of the Riemann integral, there exists a gauge threshold $\delta > 0$ such that for every marked partition $(P, \xi)$ of $[a, b]$ satisfying $\lambda(P) < \delta$:
$$
\begin{gather}
\left| \sigma(f; P, \xi) - I \right| < \frac{\varepsilon}{4} \tag{2}
\end{gather}
$$

Fix an arbitrary partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ with mesh fineness $\lambda(P) < \delta$.

For each $i \in \{1, \dots, n\}$, let $M_i := \sup_{x \in \Delta_i} f(x)$ and $m_i := \inf_{x \in \Delta_i} f(x)$ on the subinterval $\Delta_i = [x_{i-1}, x_i]$. By the characterization of the supremum and infimum, for each $i \in \{1, \dots, n\}$, there exist sample points $\xi_i', \xi_i'' \in \Delta_i$ such that:
$$
\begin{gather}
f(\xi_i') > M_i - \frac{\varepsilon}{4(b - a)} \quad \text{and} \quad f(\xi_i'') < m_i + \frac{\varepsilon}{4(b - a)} \tag{3}
\end{gather}
$$

Form the tag vectors $\xi' = (\xi_1', \dots, \xi_n')$ and $\xi'' = (\xi_1'', \dots, \xi_n'')$. Because $\lambda(P) < \delta$, step 2 applies to both marked partitions $(P, \xi')$ and $(P, \xi'')$:
$$
\begin{gather}
\left| \sigma(f; P, \xi') - I \right| < \frac{\varepsilon}{4} \quad \text{and} \quad \left| \sigma(f; P, \xi'') - I \right| < \frac{\varepsilon}{4} \tag{4}
\end{gather}
$$

Applying the triangle inequality to step 4:
$$
\begin{gather}
\sigma(f; P, \xi') - \sigma(f; P, \xi'') \le |\sigma(f; P, \xi') - I| + |I - \sigma(f; P, \xi'')| < \frac{\varepsilon}{4} + \frac{\varepsilon}{4} = \frac{\varepsilon}{2} \tag{5}
\end{gather}
$$

Multiplying the first inequality of step 3 by $\Delta x_i > 0$ and summing over $i \in \{1, \dots, n\}$:
$$
\begin{gather}
S(f; P) - \sigma(f; P, \xi') = \sum_{i=1}^n \big( M_i - f(\xi_i') \big) \Delta x_i < \frac{\varepsilon}{4(b - a)} \sum_{i=1}^n \Delta x_i = \frac{\varepsilon}{4(b - a)} (b - a) = \frac{\varepsilon}{4} \tag{6}
\end{gather}
$$

Similarly, multiplying the second inequality of step 3 by $\Delta x_i > 0$ and summing over $i \in \{1, \dots, n\}$:
$$
\begin{gather}
\sigma(f; P, \xi'') - s(f; P) = \sum_{i=1}^n \big( f(\xi_i'') - m_i \big) \Delta x_i < \frac{\varepsilon}{4(b - a)} \sum_{i=1}^n \Delta x_i = \frac{\varepsilon}{4} \tag{7}
\end{gather}
$$

Decomposing the total oscillation across the partition $P$:
$$
\begin{gather}
S(f; P) - s(f; P) = \big( S(f; P) - \sigma(f; P, \xi') \big) + \big( \sigma(f; P, \xi') - \sigma(f; P, \xi'') \big) + \big( \sigma(f; P, \xi'') - s(f; P) \big) \tag{8}
\end{gather}
$$

Substituting the bounds from step 6, step 5, and step 7 into step 8 yields:
$$
\begin{gather}
S(f; P) - s(f; P) < \frac{\varepsilon}{4} + \frac{\varepsilon}{2} + \frac{\varepsilon}{4} = \varepsilon \tag{9}
\end{gather}
$$

Because $S(f; P) - s(f; P) = \sum_{i=1}^n (M_i - m_i) \Delta x_i = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i$, step 9 establishes assertion 3.

---
# Implication 3 implies 2
Assume that assertion 3 holds: for every $\varepsilon > 0$, there exists a partition $P$ of $[a, b]$ such that $S(f; P) - s(f; P) < \varepsilon$.

By the definition of the lower and upper Darboux integrals, for any partition $P$:
$$
\begin{gather}
s(f; P) \le \underline{I}(f) \quad \text{and} \quad \overline{I}(f) \le S(f; P) \tag{10}
\end{gather}
$$

Furthermore, the Arbitrary Partition Darboux Inequality ([[Proof of the Arbitrary Partition Darboux Inequality]]) guarantees that:
$$
\begin{gather}
\underline{I}(f) \le \overline{I}(f) \tag{11}
\end{gather}
$$

Combining step 10 and step 11:
$$
\begin{gather}
0 \le \overline{I}(f) - \underline{I}(f) \le S(f; P) - s(f; P) \tag{12}
\end{gather}
$$

By hypothesis, a partition $P$ exists for which the right-hand side of step 12 is strictly less than $\varepsilon$:
$$
\begin{gather}
0 \le \overline{I}(f) - \underline{I}(f) < \varepsilon \tag{13}
\end{gather}
$$

Because step 13 holds for every real number $\varepsilon > 0$, and $\overline{I}(f) - \underline{I}(f)$ is a non-negative constant, it follows that:
$$
\begin{gather}
\overline{I}(f) - \underline{I}(f) = 0 \implies \underline{I}(f) = \overline{I}(f) \tag{14}
\end{gather}
$$
which establishes assertion 2.

---
# Implication 2 implies 4
Assume that assertion 2 holds: $\underline{I}(f) = \overline{I}(f) =: I$.

By Darboux's Theorem on Limits of Upper and Lower Sums ([[Proof of Darboux's Theorem on Limits of Upper and Lower Sums]]), the upper and lower Darboux sums converge to their respective Darboux integrals as the partition mesh tends to zero:
$$
\begin{gather}
\lim_{\lambda(P) \to 0} S(f; P) = \overline{I}(f) = I \quad \text{and} \quad \lim_{\lambda(P) \to 0} s(f; P) = \underline{I}(f) = I \tag{15}
\end{gather}
$$

Applying the algebraic limit theorem for differences of convergent net functions across step 15:
$$
\begin{gather}
\lim_{\lambda(P) \to 0} \big( S(f; P) - s(f; P) \big) = \lim_{\lambda(P) \to 0} S(f; P) - \lim_{\lambda(P) \to 0} s(f; P) = I - I = 0 \tag{16}
\end{gather}
$$
which establishes assertion 4.

---
# Implication 4 implies 1
Assume that assertion 4 holds: $\lim_{\lambda(P) \to 0} \big( S(f; P) - s(f; P) \big) = 0$.

From the bounding inequality of step 12:
$$
\begin{gather}
0 \le \overline{I}(f) - \underline{I}(f) \le S(f; P) - s(f; P) \tag{17}
\end{gather}
$$
taking the limit as $\lambda(P) \to 0$ and applying the squeeze theorem yields:
$$
\begin{gather}
0 \le \overline{I}(f) - \underline{I}(f) \le \lim_{\lambda(P) \to 0} \big( S(f; P) - s(f; P) \big) = 0 \tag{18}
\end{gather}
$$
which enforces $\underline{I}(f) = \overline{I}(f) =: I$.

Now let $\varepsilon > 0$ be arbitrary. By the definition of the limit in assertion 4, there exists $\delta > 0$ such that for every partition $P$ with $\lambda(P) < \delta$:
$$
\begin{gather}
S(f; P) - s(f; P) < \varepsilon \tag{19}
\end{gather}
$$

Let $(P, \xi)$ be any marked partition of $[a, b]$ satisfying $\lambda(P) < \delta$. On each subinterval $\Delta_i = [x_{i-1}, x_i]$, the sample value satisfies $m_i \le f(\xi_i) \le M_i$. Multiplying by $\Delta x_i > 0$ and summing over $i \in \{1, \dots, n\}$:
$$
\begin{gather}
s(f; P) \le \sigma(f; P, \xi) \le S(f; P) \tag{20}
\end{gather}
$$

Because $s(f; P) \le \underline{I}(f) = I = \overline{I}(f) \le S(f; P)$, the integral $I$ also satisfies:
$$
\begin{gather}
s(f; P) \le I \le S(f; P) \tag{21}
\end{gather}
$$

Both the Riemann sum $\sigma(f; P, \xi)$ and the real number $I$ belong to the closed interval $[s(f; P), S(f; P)]$. The distance between any two points in a compact interval is bounded by the interval length. Hence:
$$
\begin{gather}
|\sigma(f; P, \xi) - I| \le S(f; P) - s(f; P) \tag{22}
\end{gather}
$$

Combining step 22 with step 19:
$$
\begin{gather}
|\sigma(f; P, \xi) - I| < \varepsilon \tag{23}
\end{gather}
$$
for every marked partition $(P, \xi)$ with $\lambda(P) < \delta$.

The inequality of step 23 proves that $f \in \mathcal{R}[a, b]$ with $\int_a^b f(x) \, dx = I$, which establishes assertion 1.

The circular chain of step 1 is complete, confirming that assertions 1, 2, 3, and 4 are logically equivalent.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
