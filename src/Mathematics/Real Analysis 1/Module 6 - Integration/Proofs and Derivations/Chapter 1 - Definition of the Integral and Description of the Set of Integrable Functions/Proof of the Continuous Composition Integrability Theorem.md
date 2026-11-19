---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f \in \mathcal{R}[a, b]$ with range $f([a, b]) \subseteq [c, d] \subset \mathbb{R}$, and let $\phi: [c, d] \to \mathbb{R}$ be a continuous function on $[c, d]$.

Define the composite function $h: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
h(x) := (\phi \circ f)(x) = \phi(f(x)) \tag{1}
\end{gather}
$$

Because $[c, d]$ is compact and $\phi$ is continuous on $[c, d]$, the Extreme Value Theorem (Weierstrass Theorem) ensures that $\phi$ is bounded on $[c, d]$. Therefore, there exists a real constant $K > 0$ such that:
$$
\begin{gather}
\sup_{u \in [c, d]} |\phi(u)| \le K \tag{2}
\end{gather}
$$

Because $f(x) \in [c, d]$ for all $x \in [a, b]$, step 2 guarantees that $|h(x)| = |\phi(f(x))| \le K$ for all $x \in [a, b]$. Consequently, $h$ is bounded on $[a, b]$, and the local oscillation of $h$ on any non-empty subset $E \subseteq [a, b]$ satisfies:
$$
\begin{gather}
\omega(h; E) = \sup_{x \in E} h(x) - \inf_{x \in E} h(x) \le K - (-K) = 2K \tag{3}
\end{gather}
$$

Let $\varepsilon > 0$ be arbitrary.

Because $[c, d]$ is compact and $\phi$ is continuous, the Heine-Cantor Theorem dictates that $\phi$ is uniformly continuous on $[c, d]$. 

Define the error parameter:
$$
\begin{gather}
\varepsilon' := \frac{\varepsilon}{2(b - a)} > 0 \tag{4}
\end{gather}
$$

By definition of uniform continuity, there exists a modulus of continuity $\eta > 0$ such that for all points $u', u'' \in [c, d]$:
$$
\begin{gather}
|u' - u''| < \eta \implies |\phi(u') - \phi(u'')| < \frac{\varepsilon}{2(b - a)} \tag{5}
\end{gather}
$$

Because $f \in \mathcal{R}[a, b]$, by the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]), there exists a partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ such that the Darboux oscillation sum of $f$ satisfies:
$$
\begin{gather}
\sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i < \frac{\eta \varepsilon}{4K} \tag{6}
\end{gather}
$$
where $\Delta_i = [x_{i-1}, x_i]$ and $\Delta x_i = x_i - x_{i-1}$.

Decompose the index set $\{1, \dots, n\}$ of subintervals of $P$ into two disjoint collections based on the oscillation of $f$:
$$
\begin{gather}
A := \big\{ i \in \{1, \dots, n\} : \omega(f; \Delta_i) < \eta \big\} \tag{7}
\end{gather}
$$
and
$$
\begin{gather}
B := \big\{ i \in \{1, \dots, n\} : \omega(f; \Delta_i) \ge \eta \big\} \tag{8}
\end{gather}
$$

For any index $i \in A$ and for any pair of points $x', x'' \in \Delta_i$, the definition of oscillation ensures:
$$
\begin{gather}
|f(x') - f(x'')| \le \omega(f; \Delta_i) < \eta \tag{9}
\end{gather}
$$

Because $f(x'), f(x'') \in [c, d]$, the uniform continuity implication of step 5 applies:
$$
\begin{gather}
|h(x') - h(x'')| = |\phi(f(x')) - \phi(f(x''))| < \frac{\varepsilon}{2(b - a)} \tag{10}
\end{gather}
$$

Taking the supremum over all pairs $x', x'' \in \Delta_i$ in step 10:
$$
\begin{gather}
\omega(h; \Delta_i) = \sup_{x', x'' \in \Delta_i} |h(x') - h(x'')| \le \frac{\varepsilon}{2(b - a)} \tag{11}
\end{gather}
$$
for every $i \in A$.

Summing across all subintervals in $A$:
$$
\begin{gather}
\sum_{i \in A} \omega(h; \Delta_i) \Delta x_i \le \frac{\varepsilon}{2(b - a)} \sum_{i \in A} \Delta x_i \le \frac{\varepsilon}{2(b - a)} \sum_{i=1}^n \Delta x_i = \frac{\varepsilon}{2(b - a)} (b - a) = \frac{\varepsilon}{2} \tag{12}
\end{gather}
$$

For indices in $B$, step 8 states that $\omega(f; \Delta_i) \ge \eta$. Therefore:
$$
\begin{gather}
\eta \sum_{i \in B} \Delta x_i \le \sum_{i \in B} \omega(f; \Delta_i) \Delta x_i \le \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i \tag{13}
\end{gather}
$$

Combining step 13 with the partition selection bound of step 6:
$$
\begin{gather}
\eta \sum_{i \in B} \Delta x_i < \frac{\eta \varepsilon}{4K} \tag{14}
\end{gather}
$$

Dividing step 14 by the strictly positive constant $\eta > 0$ yields a bound on the aggregate length of subintervals in $B$:
$$
\begin{gather}
\sum_{i \in B} \Delta x_i < \frac{\varepsilon}{4K} \tag{15}
\end{gather}
$$

Applying the global bound $\omega(h; \Delta_i) \le 2K$ from step 3 to each subinterval in $B$:
$$
\begin{gather}
\sum_{i \in B} \omega(h; \Delta_i) \Delta x_i \le 2K \sum_{i \in B} \Delta x_i \tag{16}
\end{gather}
$$

Substituting step 15 into step 16:
$$
\begin{gather}
\sum_{i \in B} \omega(h; \Delta_i) \Delta x_i < 2K \left( \frac{\varepsilon}{4K} \right) = \frac{\varepsilon}{2} \tag{17}
\end{gather}
$$

Decomposing the total Darboux oscillation sum of $h$ across $P$:
$$
\begin{gather}
S(h; P) - s(h; P) = \sum_{i=1}^n \omega(h; \Delta_i) \Delta x_i = \sum_{i \in A} \omega(h; \Delta_i) \Delta x_i + \sum_{i \in B} \omega(h; \Delta_i) \Delta x_i \tag{18}
\end{gather}
$$

Substituting the bounds from step 12 and step 17 into step 18:
$$
\begin{gather}
S(h; P) - s(h; P) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{19}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a partition $P$ satisfying $S(h; P) - s(h; P) < \varepsilon$, the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]) establishes that $h = \phi \circ f \in \mathcal{R}[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
