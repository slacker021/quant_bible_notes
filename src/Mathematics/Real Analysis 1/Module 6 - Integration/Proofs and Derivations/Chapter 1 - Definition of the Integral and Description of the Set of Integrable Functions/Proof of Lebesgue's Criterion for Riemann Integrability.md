---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be a bounded function. Then there exists $M > 0$ such that $|f(x)| \le M$ for all $x \in [a, b]$, and consequently $\omega(f; [a, b]) \le 2M$. Let $D_f := \{ x \in [a, b] \mid f \text{ is not continuous at } x \}$.

For each $x \in [a, b]$, define the pointwise oscillation of $f$ at $x$ by:
$$
\begin{gather}
\omega_f(x) := \inf_{\delta > 0} \omega\big(f; (x - \delta, x + \delta) \cap [a, b]\big) \tag{1}
\end{gather}
$$

A function $f$ is continuous at $x \in [a, b]$ if and only if $\omega_f(x) = 0$. Therefore, $D_f = \{ x \in [a, b] \mid \omega_f(x) > 0 \}$. For any $\eta > 0$, define the $\eta$-oscillation set:
$$
\begin{gather}
D_{f, \eta} := \{ x \in [a, b] \mid \omega_f(x) \ge \eta \} \tag{2}
\end{gather}
$$
so that $D_f = \bigcup_{k=1}^\infty D_{f, 1/k}$.

---
# Forward Direction
Assume that $f \in \mathcal{R}[a, b]$. It suffices to show that $D_{f, \eta}$ has Lebesgue measure zero for every $\eta > 0$, because a countable union of sets of Lebesgue measure zero has Lebesgue measure zero: if each $D_{f, 1/k}$ is covered by a countable collection of open intervals of total length strictly less than $\frac{\varepsilon}{2^k}$, then the union of all such collections covers $D_f$ with total length strictly less than $\sum_{k=1}^\infty \frac{\varepsilon}{2^k} = \varepsilon$.

Fix $\eta > 0$ and let $\varepsilon > 0$ be arbitrary. By the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]), there exists a partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ such that:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i < \frac{\eta \varepsilon}{2} \tag{3}
\end{gather}
$$
where $\Delta_i = [x_{i-1}, x_i]$ and $\Delta x_i = x_i - x_{i-1}$ for each $i \in \{1, \dots, n\}$.

Decompose $D_{f, \eta}$ into the points lying in the open subintervals $(x_{i-1}, x_i)$ and the points coinciding with the partition nodes $\{x_0, x_1, \dots, x_n\}$. Let $\mathcal{I} := \{ i \in \{1, \dots, n\} \mid D_{f, \eta} \cap (x_{i-1}, x_i) \neq \emptyset \}$. For each $i \in \mathcal{I}$, choose $x \in D_{f, \eta} \cap (x_{i-1}, x_i)$. Because $(x_{i-1}, x_i)$ is open, there exists $\delta > 0$ such that $(x - \delta, x + \delta) \subset (x_{i-1}, x_i) \subset \Delta_i$, which implies:
$$
\begin{gather}
\omega(f; \Delta_i) \ge \omega\big(f; (x - \delta, x + \delta) \cap [a, b]\big) \ge \omega_f(x) \ge \eta \tag{4}
\end{gather}
$$

Summing step 4 over $i \in \mathcal{I}$ and applying step 3 yields:
$$
\begin{gather}
\eta \sum_{i \in \mathcal{I}} \Delta x_i \le \sum_{i \in \mathcal{I}} \omega(f; \Delta_i) \Delta x_i \le \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i < \frac{\eta \varepsilon}{2} \tag{5}
\end{gather}
$$
Dividing step 5 by $\eta > 0$, the open intervals $I_i := (x_{i-1}, x_i)$ for $i \in \mathcal{I}$ satisfy $\sum_{i \in \mathcal{I}} |I_i| < \frac{\varepsilon}{2}$.

For the at most $n + 1$ partition nodes $x_j$ ($j \in \{0, \dots, n\}$), enclose each $x_j$ in the open interval:
$$
\begin{gather}
J_j := \left(x_j - \frac{\varepsilon}{4(n + 1)}, \, x_j + \frac{\varepsilon}{4(n + 1)}\right) \tag{6}
\end{gather}
$$
so that $\sum_{j=0}^n |J_j| = (n + 1) \cdot \frac{\varepsilon}{2(n + 1)} = \frac{\varepsilon}{2}$.

The finite collection $\{I_i\}_{i \in \mathcal{I}} \cup \{J_j\}_{j=0}^n$ of open intervals covers $D_{f, \eta}$, and its total length satisfies:
$$
\begin{gather}
\sum_{i \in \mathcal{I}} |I_i| + \sum_{j=0}^n |J_j| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{7}
\end{gather}
$$
Hence $D_{f, \eta}$ has Lebesgue measure zero for every $\eta > 0$, and therefore $D_f = \bigcup_{k=1}^\infty D_{f, 1/k}$ has Lebesgue measure zero.

---
# Backward Inclusion
Assume that $D_f$ has Lebesgue measure zero, and let $\varepsilon > 0$ be arbitrary. Set:
$$
\begin{gather}
\eta := \frac{\varepsilon}{2(b - a)} > 0 \quad \text{and} \quad \varepsilon' := \frac{\varepsilon}{2(2M + 1)} > 0 \tag{8}
\end{gather}
$$

First, observe that $D_{f, \eta}$ is a closed subset of $[a, b]$ and hence compact. Indeed, for any $x \in [a, b] \setminus D_{f, \eta}$, we have $\omega_f(x) < \eta$, so there exists $\delta > 0$ such that $\omega\big(f; (x - \delta, x + \delta) \cap [a, b]\big) < \eta$. For every $y \in (x - \delta, x + \delta) \cap [a, b]$, $(x - \delta, x + \delta)$ is an open neighborhood of $y$, so $\omega_f(y) \le \omega\big(f; (x - \delta, x + \delta) \cap [a, b]\big) < \eta$, meaning $y \notin D_{f, \eta}$. Thus $[a, b] \setminus D_{f, \eta}$ is open in $[a, b]$.

Because $D_{f, \eta} \subseteq D_f$ and $D_f$ has Lebesgue measure zero, there exists a countable collection of open intervals $\{I_k\}_{k=1}^\infty$ such that $D_{f, \eta} \subseteq \bigcup_{k=1}^\infty I_k$ and $\sum_{k=1}^\infty |I_k| < \varepsilon'$. By the compactness of $D_{f, \eta}$, there exists a finite subcover $\{U_1, \dots, U_m\}$ of $D_{f, \eta}$ from $\{I_k\}_{k=1}^\infty$ satisfying:
$$
\begin{gather}
D_{f, \eta} \subseteq \bigcup_{j=1}^m U_j \quad \text{and} \quad \sum_{j=1}^m |U_j| < \varepsilon' \tag{9}
\end{gather}
$$

Define $K := [a, b] \setminus \bigcup_{j=1}^m U_j$. Since $\bigcup_{j=1}^m U_j$ is open, $K$ is a closed subset of $[a, b]$, hence compact. For every $x \in K$, we have $x \notin D_{f, \eta}$, so $\omega_f(x) < \eta$. Thus for each $x \in K$, there exists $\delta_x > 0$ such that:
$$
\begin{gather}
\omega\big(f; (x - 2\delta_x, x + 2\delta_x) \cap [a, b]\big) < \eta \tag{10}
\end{gather}
$$

The collection $\{(x - \delta_x, x + \delta_x)\}_{x \in K}$ is an open cover of the compact set $K$. By compactness, there exists a finite subcover $\{(x^{(1)} - \delta_1, x^{(1)} + \delta_1), \dots, (x^{(r)} - \delta_r, x^{(r)} + \delta_r)\}$ of $K$. (If $K = \emptyset$, this subcover is empty.)

Form a partition $P = \{t_0, t_1, \dots, t_n\}$ of $[a, b]$ by taking $a$, $b$, and all endpoints of the intervals $U_j$ ($j = 1, \dots, m$) and $(x^{(l)} - \delta_l, x^{(l)} + \delta_l)$ ($l = 1, \dots, r$) that lie in $[a, b]$, arranged in strictly increasing order. Let $\Delta_i = [t_{i-1}, t_i]$ and $\Delta t_i = t_i - t_{i-1}$ for $i \in \{1, \dots, n\}$. Partition the index set $\{1, \dots, n\}$ into:
$$
\begin{gather}
\mathcal{A} := \left\{ i \in \{1, \dots, n\} \;\middle|\; (t_{i-1}, t_i) \cap \bigcup_{j=1}^m U_j \neq \emptyset \right\}, \quad \mathcal{B} := \{1, \dots, n\} \setminus \mathcal{A} \tag{11}
\end{gather}
$$

For each $i \in \mathcal{A}$, no endpoint of any $U_j$ lies in $(t_{i-1}, t_i)$, so $(t_{i-1}, t_i) \subseteq U_j$ for some $j \in \{1, \dots, m\}$. Because the open intervals $(t_{i-1}, t_i)$ are pairwise disjoint and contained in $\bigcup_{j=1}^m U_j$, step 9 gives:
$$
\begin{gather}
\sum_{i \in \mathcal{A}} \Delta t_i \le \sum_{j=1}^m |U_j| < \varepsilon' = \frac{\varepsilon}{2(2M + 1)} \tag{12}
\end{gather}
$$
and on each such $\Delta_i$, $\omega(f; \Delta_i) \le 2M$.

For each $i \in \mathcal{B}$, $(t_{i-1}, t_i) \cap \bigcup_{j=1}^m U_j = \emptyset$, so $(t_{i-1}, t_i) \subseteq K$. In particular, the midpoint $\frac{t_{i-1} + t_i}{2}$ lies in $K$, and hence in $(x^{(l)} - \delta_l, x^{(l)} + \delta_l)$ for some $l \in \{1, \dots, r\}$. Because no endpoint of $(x^{(l)} - \delta_l, x^{(l)} + \delta_l)$ lies in $(t_{i-1}, t_i)$, we have:
$$
\begin{gather}
\Delta_i \subseteq [x^{(l)} - \delta_l, x^{(l)} + \delta_l] \cap [a, b] \subset (x^{(l)} - 2\delta_l, x^{(l)} + 2\delta_l) \cap [a, b] \tag{13}
\end{gather}
$$
which, by step 10, implies $\omega(f; \Delta_i) < \eta = \frac{\varepsilon}{2(b - a)}$.

Combining the bounds over $\mathcal{A}$ and $\mathcal{B}$ using step 12, step 13, and $\sum_{i \in \mathcal{B}} \Delta t_i \le b - a$:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i \in \mathcal{A}} \omega(f; \Delta_i) \Delta t_i + \sum_{i \in \mathcal{B}} \omega(f; \Delta_i) \Delta t_i < 2M \cdot \frac{\varepsilon}{2(2M + 1)} + \frac{\varepsilon}{2(b - a)}(b - a) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{14}
\end{gather}
$$

Because $\varepsilon > 0$ was arbitrary, the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]) implies that $f \in \mathcal{R}[a, b]$.
$$
\textbf{Q.E.D}
$$

