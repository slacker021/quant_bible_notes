---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $g \in \mathcal{R}[a, b]$.

Define the integral accumulation function $G: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
G(x) := \int_a^x g(t)\,dt \tag{1}
\end{gather}
$$

Evaluating at the lower boundary point gives:
$$
\begin{gather}
G(a) = \int_a^a g(t)\,dt = 0 \tag{2}
\end{gather}
$$

By the Necessity of Boundedness for Riemann Integrability ([[Proof of the Necessity of Boundedness for Riemann Integrability]]), $g$ is bounded on $[a, b]$. Therefore, there exists a constant $K > 0$ such that:
$$
\begin{gather}
\sup_{t \in [a, b]} |g(t)| \le K \tag{3}
\end{gather}
$$

For any $u, v \in [a, b]$ with $u \le v$, by the Interval Additivity Theorem ([[Proof of Interval Additivity of the Definite Integral]]) and Part 5 of the Monotonicity Theorem ([[Proof of Monotonicity and the Absolute Value Integral Inequality]]):
$$
\begin{gather}
|G(v) - G(u)| = \left| \int_u^v g(t)\,dt \right| \le \int_u^v |g(t)|\,dt \le K(v - u) \tag{4}
\end{gather}
$$
which demonstrates that $G$ is $K$-Lipschitz continuous, and therefore continuous, on $[a, b]$.

Because $[a, b]$ is compact and $G$ is continuous, the Extreme Value Theorem (Weierstrass Theorem) guarantees that $G$ attains its absolute minimum and maximum on $[a, b]$:
$$
\begin{gather}
m_G := \min_{x \in [a, b]} G(x), \qquad M_G := \max_{x \in [a, b]} G(x) \tag{5}
\end{gather}
$$

Because $G(a) = 0$ by step 2, the bounds satisfy:
$$
\begin{gather}
m_G \le 0 \le M_G \tag{6}
\end{gather}
$$

Furthermore, by the Intermediate Value Theorem (Bolzano-Cauchy Theorem), $G$ attains every value in $[m_G, M_G]$.

---
# Abel's Discrete Summation Lemma

Let $n \in \mathbb{N}$, and let $a_1, \dots, a_n$ and $b_1, \dots, b_n$ be sequences of real numbers. Define the partial sums $A_0 := 0$ and $A_k := \sum_{j=1}^k a_j$ for $k \in \{1, \dots, n\}$.

Expressing each term $a_k$ as the difference $a_k = A_k - A_{k-1}$:
$$
\begin{gather}
\sum_{k=1}^n a_k b_k = \sum_{k=1}^n (A_k - A_{k-1})b_k = \sum_{k=1}^n A_k b_k - \sum_{k=1}^n A_{k-1}b_k \tag{7}
\end{gather}
$$

Re-indexing the second sum with index $j = k - 1$ and noting $A_0 = 0$:
$$
\begin{gather}
\sum_{k=1}^n A_{k-1}b_k = \sum_{j=0}^{n-1} A_j b_{j+1} = \sum_{k=1}^{n-1} A_k b_{k+1} \tag{8}
\end{gather}
$$

Subtracting step 8 from the first sum in step 7 yields Abel's summation by parts identity:
$$
\begin{gather}
\sum_{k=1}^n a_k b_k = A_n b_n + \sum_{k=1}^{n-1} A_k (b_k - b_{k+1}) \tag{9}
\end{gather}
$$

Suppose the sequence $(b_k)$ is non-negative and monotonic decreasing:
$$
\begin{gather}
b_1 \ge b_2 \ge \dots \ge b_n \ge 0 \tag{10}
\end{gather}
$$
so that $b_n \ge 0$ and $(b_k - b_{k+1}) \ge 0$ for each $k \in \{1, \dots, n-1\}$.

If there exist constants $m, M \in \mathbb{R}$ such that $m \le A_k \le M$ for all $k \in \{1, \dots, n\}$, bounding each $A_k$ in step 9 from above by $M$ gives:
$$
\begin{gather}
\sum_{k=1}^n a_k b_k \le M b_n + \sum_{k=1}^{n-1} M (b_k - b_{k+1}) = M \left( b_n + \sum_{k=1}^{n-1} (b_k - b_{k+1}) \right) = M b_1 \tag{11}
\end{gather}
$$
and bounding each $A_k$ in step 9 from below by $m$ gives:
$$
\begin{gather}
\sum_{k=1}^n a_k b_k \ge m b_n + \sum_{k=1}^{n-1} m (b_k - b_{k+1}) = m \left( b_n + \sum_{k=1}^{n-1} (b_k - b_{k+1}) \right) = m b_1 \tag{12}
\end{gather}
$$

Combining step 11 and step 12 yields Abel's inequality:
$$
\begin{gather}
m b_1 \le \sum_{k=1}^n a_k b_k \le M b_1 \tag{13}
\end{gather}
$$
---
# Theorem 1
Assume $f: [a, b] \to \mathbb{R}$ is monotonic decreasing and non-negative:
$$
\begin{gather}
f(x_1) \ge f(x_2) \ge 0 \quad \text{for all } a \le x_1 < x_2 \le b \tag{14}
\end{gather}
$$

Because $f$ is monotonic on $[a, b]$, $f \in \mathcal{R}[a, b]$ by the Integrability of Monotone Functions ([[Proof of the Integrability of Monotone Functions]]). By the Integrability of the Product of Integrable Functions ([[Proof of the Integrability of the Product of Integrable Functions]]), the product satisfies $fg \in \mathcal{R}[a, b]$.

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ with $a = x_0 < x_1 < \dots < x_n = b$.

Define the components:
$$
\begin{gather}
a_k := \int_{x_{k-1}}^{x_k} g(t)\,dt = G(x_k) - G(x_{k-1}), \qquad b_k := f(x_{k-1}) \tag{15}
\end{gather}
$$
for each $k \in \{1, \dots, n\}$.

The partial sums of $a_k$ telescope to:
$$
\begin{gather}
A_k = \sum_{j=1}^k a_j = G(x_k) - G(x_0) = G(x_k) - G(a) = G(x_k) \tag{16}
\end{gather}
$$

By step 5, $m_G \le A_k = G(x_k) \le M_G$ for every $k \in \{1, \dots, n\}$.

Because $f$ is non-negative and monotonic decreasing, step 14 implies:
$$
\begin{gather}
f(a) = b_1 \ge b_2 \ge \dots \ge b_n = f(x_{n-1}) \ge f(b) \ge 0 \tag{17}
\end{gather}
$$

Applying Abel's inequality from step 13 to the sequences in step 15:
$$
\begin{gather}
m_G f(a) \le \sum_{k=1}^n f(x_{k-1}) \int_{x_{k-1}}^{x_k} g(t)\,dt \le M_G f(a) \tag{18}
\end{gather}
$$

By the Interval Additivity Theorem, the definite integral of $fg$ decomposes across the partition subintervals:
$$
\begin{gather}
\int_a^b f(t)g(t)\,dt = \sum_{k=1}^n \int_{x_{k-1}}^{x_k} f(t)g(t)\,dt \tag{19}
\end{gather}
$$

Subtracting the sum in step 18 from step 19:
$$
\begin{gather}
\left| \int_a^b f(t)g(t)\,dt - \sum_{k=1}^n f(x_{k-1}) \int_{x_{k-1}}^{x_k} g(t)\,dt \right| = \left| \sum_{k=1}^n \int_{x_{k-1}}^{x_k} \big( f(t) - f(x_{k-1}) \big) g(t)\,dt \right| \tag{20}
\end{gather}
$$

Applying the triangle inequality and the absolute value bound to step 20:
$$
\begin{gather}
\left| \sum_{k=1}^n \int_{x_{k-1}}^{x_k} \big( f(t) - f(x_{k-1}) \big) g(t)\,dt \right| \le \sum_{k=1}^n \int_{x_{k-1}}^{x_k} |f(t) - f(x_{k-1})| |g(t)|\,dt \tag{21}
\end{gather}
$$

Because $f$ is monotonic decreasing, for every $t \in [x_{k-1}, x_k]$:
$$
\begin{gather}
f(x_k) \le f(t) \le f(x_{k-1}) \implies |f(t) - f(x_{k-1})| = f(x_{k-1}) - f(t) \le f(x_{k-1}) - f(x_k) \tag{22}
\end{gather}
$$

Using the uniform bound $|g(t)| \le K$ from step 3 and defining $\Delta x_k := x_k - x_{k-1}$:
$$
\begin{gather}
\sum_{k=1}^n \int_{x_{k-1}}^{x_k} |f(t) - f(x_{k-1})| |g(t)|\,dt \le K \sum_{k=1}^n \big( f(x_{k-1}) - f(x_k) \big) \Delta x_k \tag{23}
\end{gather}
$$

Let $\lambda(P) := \max_{1 \le k \le n} \Delta x_k$ denote the mesh of $P$. Factoring $\lambda(P)$ out of step 23:
$$
\begin{gather}
K \sum_{k=1}^n \big( f(x_{k-1}) - f(x_k) \big) \Delta x_k \le K \lambda(P) \sum_{k=1}^n \big( f(x_{k-1}) - f(x_k) \big) \tag{24}
\end{gather}
$$

The sum in step 24 telescopes:
$$
\begin{gather}
\sum_{k=1}^n \big( f(x_{k-1}) - f(x_k) \big) = f(x_0) - f(x_n) = f(a) - f(b) \tag{25}
\end{gather}
$$

Combining steps 20 through 25 yields:
$$
\begin{gather}
\left| \int_a^b f(t)g(t)\,dt - \sum_{k=1}^n f(x_{k-1}) \int_{x_{k-1}}^{x_k} g(t)\,dt \right| \le K \big( f(a) - f(b) \big) \lambda(P) \tag{26}
\end{gather}
$$

As the mesh $\lambda(P) \to 0$, the upper bound in step 26 converges to zero. Therefore, passing to the limit as $\lambda(P) \to 0$ in the inequality of step 18 preserves the bounds:
$$
\begin{gather}
m_G f(a) \le \int_a^b f(t)g(t)\,dt \le M_G f(a) \tag{27}
\end{gather}
$$

If $f(a) = 0$, the non-negativity and decreasing property from step 14 force $0 \le f(x) \le f(a) = 0$, so $f(x) = 0$ for all $x \in [a, b]$. Then $\int_a^b fg = 0 = f(a) \int_a^\xi g$ for any $\xi \in [a, b]$.

If $f(a) > 0$, dividing step 27 by the positive scalar $f(a) > 0$:
$$
\begin{gather}
m_G \le \frac{1}{f(a)} \int_a^b f(t)g(t)\,dt \le M_G \tag{28}
\end{gather}
$$

Because $G$ is continuous on $[a, b]$ with range $[m_G, M_G]$, the Intermediate Value Theorem ensures that there exists at least one point $\xi \in [a, b]$ such that:
$$
\begin{gather}
G(\xi) = \frac{1}{f(a)} \int_a^b f(t)g(t)\,dt \tag{29}
\end{gather}
$$

Multiplying step 29 by $f(a)$ and substituting $G(\xi) = \int_a^\xi g(x)\,dx$:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx \tag{30}
\end{gather}
$$
which establishes Bonnet's form for non-negative monotonic decreasing functions.

---
# Theorem 2
Assume $f: [a, b] \to \mathbb{R}$ is monotonic increasing and non-negative:
$$
\begin{gather}
0 \le f(x_1) \le f(x_2) \quad \text{for all } a \le x_1 < x_2 \le b \tag{31}
\end{gather}
$$

Define the reflected functions $\tilde{f}, \tilde{g}: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
\tilde{f}(t) := f(a + b - t), \qquad \tilde{g}(t) := g(a + b - t) \tag{32}
\end{gather}
$$

As $t$ increases from $a$ to $b$, the reflected coordinate $x = a + b - t$ decreases from $b$ to $a$. Consequently, $\tilde{f}$ is non-negative and monotonic decreasing on $[a, b]$, with initial value:
$$
\begin{gather}
\tilde{f}(a) = f(a + b - a) = f(b) \tag{33}
\end{gather}
$$

Applying Bonnet's decreasing form from step 30 to $\tilde{f}$ and $\tilde{g}$ guarantees the existence of a point $\eta \in [a, b]$ such that:
$$
\begin{gather}
\int_a^b \tilde{f}(t)\tilde{g}(t)\,dt = \tilde{f}(a) \int_a^\eta \tilde{g}(t)\,dt \tag{34}
\end{gather}
$$

Under the reflection substitution $x = a + b - t$ with $dx = -dt$:
$$
\begin{gather}
\int_a^b \tilde{f}(t)\tilde{g}(t)\,dt = \int_a^b f(a + b - t)g(a + b - t)\,dt = \int_a^b f(x)g(x)\,dx \tag{35}
\end{gather}
$$
and
$$
\begin{gather}
\int_a^\eta \tilde{g}(t)\,dt = \int_a^\eta g(a + b - t)\,dt = -\int_b^{a + b - \eta} g(x)\,dx = \int_{a + b - \eta}^b g(x)\,dx \tag{36}
\end{gather}
$$

Define the point $\xi \in [a, b]$ by:
$$
\begin{gather}
\xi := a + b - \eta \tag{37}
\end{gather}
$$

Because $\eta \in [a, b]$, step 37 satisfies $\xi \in [a, b]$.

Substituting step 33, step 35, step 36, and step 37 into step 34:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(b) \int_\xi^b g(x)\,dx \tag{38}
\end{gather}
$$
which establishes Bonnet's form for non-negative monotonic increasing functions.

### Additional for Theorem 2
Let $f: [a, b] \to \mathbb{R}$ be an arbitrary monotonic function on $[a, b]$ (not necessarily non-negative).

Consider first the case where $f$ is monotonic decreasing on $[a, b]$.

Define the vertically shifted function $h: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
h(x) := f(x) - f(b) \tag{39}
\end{gather}
$$

Because $f$ is monotonic decreasing, $f(x) \ge f(b)$ for all $x \in [a, b]$, which implies:
$$
\begin{gather}
h(x) \ge 0 \quad \text{for all } x \in [a, b] \tag{40}
\end{gather}
$$

Furthermore, $h$ is monotonic decreasing on $[a, b]$, with initial value $h(a) = f(a) - f(b)$ and terminal value $h(b) = 0$.

Because $h$ is non-negative and monotonic decreasing, Bonnet's decreasing form from step 30 applies to the pair $(h, g)$, guaranteeing the existence of a point $\xi \in [a, b]$ such that:
$$
\begin{gather}
\int_a^b h(x)g(x)\,dx = h(a) \int_a^\xi g(x)\,dx \tag{41}
\end{gather}
$$

Substituting $h(x) = f(x) - f(b)$ and $h(a) = f(a) - f(b)$ into step 41:
$$
\begin{gather}
\int_a^b \big( f(x) - f(b) \big) g(x)\,dx = \big( f(a) - f(b) \big) \int_a^\xi g(x)\,dx \tag{42}
\end{gather}
$$

Expanding both sides via the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]):
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx - f(b) \int_a^b g(x)\,dx = f(a) \int_a^\xi g(x)\,dx - f(b) \int_a^\xi g(x)\,dx \tag{43}
\end{gather}
$$

Rearranging step 43 to isolate the integral of $fg$:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \left( \int_a^b g(x)\,dx - \int_a^\xi g(x)\,dx \right) \tag{44}
\end{gather}
$$

By the Interval Additivity Theorem ([[Proof of Interval Additivity of the Definite Integral]]), $\int_a^b g(x)\,dx = \int_a^\xi g(x)\,dx + \int_\xi^b g(x)\,dx$. Therefore:
$$
\begin{gather}
\int_a^b g(x)\,dx - \int_a^\xi g(x)\,dx = \int_\xi^b g(x)\,dx \tag{45}
\end{gather}
$$

Substituting step 45 into step 44 yields:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \int_\xi^b g(x)\,dx \tag{46}
\end{gather}
$$

Consider next the case where $f$ is monotonic increasing on $[a, b]$.

Define the auxiliary function $k: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
k(x) := f(b) - f(x) \tag{47}
\end{gather}
$$

Because $f$ is monotonic increasing, $f(x) \le f(b)$ for all $x \in [a, b]$, which implies:
$$
\begin{gather}
k(x) \ge 0 \quad \text{for all } x \in [a, b] \tag{48}
\end{gather}
$$

As $x$ increases, $-f(x)$ decreases, so $k$ is monotonic decreasing on $[a, b]$, with $k(a) = f(b) - f(a)$ and $k(b) = 0$.

Applying Bonnet's decreasing form from step 30 to $(k, g)$ yields a point $\xi \in [a, b]$ such that:
$$
\begin{gather}
\int_a^b k(x)g(x)\,dx = k(a) \int_a^\xi g(x)\,dx \tag{49}
\end{gather}
$$

Substituting $k(x) = f(b) - f(x)$ and $k(a) = f(b) - f(a)$ into step 49:
$$
\begin{gather}
\int_a^b \big( f(b) - f(x) \big) g(x)\,dx = \big( f(b) - f(a) \big) \int_a^\xi g(x)\,dx \tag{50}
\end{gather}
$$

Expanding via Linearity:
$$
\begin{gather}
f(b) \int_a^b g(x)\,dx - \int_a^b f(x)g(x)\,dx = f(b) \int_a^\xi g(x)\,dx - f(a) \int_a^\xi g(x)\,dx \tag{51}
\end{gather}
$$

Rearranging step 51 to isolate the integral of $fg$:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \left( \int_a^b g(x)\,dx - \int_a^\xi g(x)\,dx \right) \tag{52}
\end{gather}
$$

Substituting the identity of step 45 into step 52:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \int_\xi^b g(x)\,dx \tag{53}
\end{gather}
$$

Because every monotonic function is either decreasing or increasing, step 46 and step 53 establish the Weierstrass / du Bois-Reymond form for general monotonic functions.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
