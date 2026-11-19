---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f, g: [a, \infty) \to \mathbb{R}$ be functions satisfying:
$$
\begin{gather}
f, g \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Define the respective accumulation functions $F, G: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
F(B) := \int_a^B f(x)\,dx, \qquad G(B) := \int_a^B g(x)\,dx \tag{2}
\end{gather}
$$
---
# Part 1

Assume that $f$ and $g$ satisfy the pointwise domination inequality:
$$
\begin{gather}
0 \le f(x) \le g(x) \quad \text{for all } x \in [a, \infty) \tag{3}
\end{gather}
$$
### Step 1
For every parameter $B \ge a$, by the order-preserving monotonicity of the Riemann integral on the compact interval $[a, B]$:
$$
\begin{gather}
0 \le \int_a^B f(x)\,dx \le \int_a^B g(x)\,dx \tag{4}
\end{gather}
$$

Substituting the definitions from step 2 into step 4 yields:
$$
\begin{gather}
0 \le F(B) \le G(B) \quad \text{for all } B \ge a \tag{5}
\end{gather}
$$

Because $f(x) \ge 0$ and $g(x) \ge 0$ on $[a, \infty)$, the Monotonicity Criterion for Non-Negative Improper Integrals guarantees that both $F$ and $G$ are monotonically non-decreasing functions on $[a, \infty)$.

### Step 2
Suppose that $\int_a^\infty g(x)\,dx$ converges to a finite real value:
$$
\begin{gather}
J := \int_a^\infty g(x)\,dx = \lim_{B \to \infty} G(B) \in \mathbb{R} \tag{6}
\end{gather}
$$

By the Monotonicity Criterion for Non-Negative Improper Integrals, because $g(x) \ge 0$ and $\int_a^\infty g(x)\,dx$ converges, the accumulation function $G(B)$ is bounded from above by its limit:
$$
\begin{gather}
G(B) \le \sup_{B' \ge a} G(B') = J \quad \text{for all } B \ge a \tag{7}
\end{gather}
$$

Combining step 5 and step 7 yields:
$$
\begin{gather}
F(B) \le G(B) \le J \quad \text{for all } B \ge a \tag{8}
\end{gather}
$$

Thus, the accumulation function $F(B)$ is bounded from above on $[a, \infty)$ by the constant $J$.

Because $f(x) \ge 0$ and $F(B)$ is bounded from above, the Monotonicity Criterion for Non-Negative Improper Integrals implies that the improper integral $\int_a^\infty f(x)\,dx$ converges to a finite real value:
$$
\begin{gather}
I := \int_a^\infty f(x)\,dx = \lim_{B \to \infty} F(B) \in \mathbb{R} \tag{9}
\end{gather}
$$

Taking the limit as $B \to \infty$ across the inequality $F(B) \le G(B)$ in step 5, the order-preserving property of functional limits guarantees that:
$$
\begin{gather}
I = \lim_{B \to \infty} F(B) \le \lim_{B \to \infty} G(B) = J \tag{10}
\end{gather}
$$

which confirms the inequality:
$$
\begin{gather}
\int_a^\infty f(x)\,dx \le \int_a^\infty g(x)\,dx \tag{11}
\end{gather}
$$
### Step 3
Suppose that $\int_a^\infty f(x)\,dx$ diverges to $+\infty$:
$$
\begin{gather}
\lim_{B \to \infty} F(B) = +\infty \tag{12}
\end{gather}
$$

Let $E > 0$ be arbitrary. By definition of divergence to infinity, there exists a threshold $B_0 \ge a$ such that:
$$
\begin{gather}
F(B) > E \quad \text{for all } B > B_0 \tag{13}
\end{gather}
$$

Applying the inequality $G(B) \ge F(B)$ from step 5 to step 13 shows that:
$$
\begin{gather}
G(B) \ge F(B) > E \quad \text{for all } B > B_0 \tag{14}
\end{gather}
$$

Because for every $E > 0$ there exists $B_0 \ge a$ such that $G(B) > E$ for all $B > B_0$, the definition of divergence to infinity is satisfied:
$$
\begin{gather}
\lim_{B \to \infty} G(B) = \int_a^\infty g(x)\,dx = +\infty \tag{15}
\end{gather}
$$

This completes the proof of the Direct Comparison Test.

---
# Part 2
Assume that $f(x) > 0$ and $g(x) > 0$ for all $x \in [a, \infty)$, and assume that the asymptotic limit of the ratio exists:
$$
\begin{gather}
L := \lim_{x \to \infty} \frac{f(x)}{g(x)} \in [0, \infty] \tag{16}
\end{gather}
$$

### Step 1
Let $\varepsilon = \frac{L}{2} > 0$. By definition of the limit at infinity in step 16, there exists an exhaustion threshold $x_0 \ge a$ such that:
$$
\begin{gather}
x \ge x_0 \implies \left| \frac{f(x)}{g(x)} - L \right| < \frac{L}{2} \tag{17}
\end{gather}
$$

Expanding the absolute value inequality of step 17:
$$
\begin{gather}
-\frac{L}{2} < \frac{f(x)}{g(x)} - L < \frac{L}{2} \tag{18}
\end{gather}
$$

Adding $L$ across all terms of step 18:
$$
\begin{gather}
\frac{L}{2} < \frac{f(x)}{g(x)} < \frac{3L}{2} \quad \text{for all } x \ge x_0 \tag{19}
\end{gather}
$$

Because $g(x) > 0$ on $[a, \infty)$, multiplying step 19 by $g(x)$ preserves the inequalities:
$$
\begin{gather}
\frac{L}{2} g(x) < f(x) < \frac{3L}{2} g(x) \quad \text{for all } x \ge x_0 \tag{20}
\end{gather}
$$

The equivalence of convergence is now deduced:
1. Suppose $\int_a^\infty g(x)\,dx$ converges. By the domain additivity of improper integrals:
$$
\begin{gather}
\int_a^\infty g(x)\,dx = \int_a^{x_0} g(x)\,dx + \int_{x_0}^\infty g(x)\,dx \tag{21}
\end{gather}
$$
Because $g \in \mathcal{R}[a, x_0]$, the proper integral $\int_a^{x_0} g(x)\,dx$ is finite, so $\int_{x_0}^\infty g(x)\,dx$ converges finitely. By the scalar linearity of the improper integral:
$$
\begin{gather}
\int_{x_0}^\infty \frac{3L}{2} g(x)\,dx = \frac{3L}{2} \int_{x_0}^\infty g(x)\,dx < \infty \tag{22}
\end{gather}
$$
Because $0 < f(x) < \frac{3L}{2} g(x)$ for all $x \ge x_0$ by step 20, applying the Direct Comparison Test of Part 1 on $[x_0, \infty)$ guarantees that $\int_{x_0}^\infty f(x)\,dx$ converges. By domain additivity:
$$
\begin{gather}
\int_a^\infty f(x)\,dx = \int_a^{x_0} f(x)\,dx + \int_{x_0}^\infty f(x)\,dx < \infty \tag{23}
\end{gather}
$$
which establishes that $\int_a^\infty f(x)\,dx$ converges.

2. Conversely, suppose $\int_a^\infty f(x)\,dx$ converges. By domain additivity, the tail integral $\int_{x_0}^\infty f(x)\,dx$ converges. From the left inequality in step 20:
$$
\begin{gather}
g(x) < \frac{2}{L} f(x) \quad \text{for all } x \ge x_0 \tag{24}
\end{gather}
$$
By scalar linearity, $\int_{x_0}^\infty \frac{2}{L} f(x)\,dx = \frac{2}{L} \int_{x_0}^\infty f(x)\,dx < \infty$. Applying the Direct Comparison Test of Part 1 on $[x_0, \infty)$ guarantees that $\int_{x_0}^\infty g(x)\,dx$ converges. By domain additivity, $\int_a^\infty g(x)\,dx$ converges.

3. By the law of contraposition, if either integral diverges to $+\infty$, the other must also diverge to $+\infty$. Therefore, $\int_a^\infty f(x)\,dx$ and $\int_a^\infty g(x)\,dx$ share identical convergence status.

### Step 2
Suppose $L = 0$ and $\int_a^\infty g(x)\,dx$ converges. Setting $\varepsilon = 1 > 0$ in the definition of the limit in step 16, there exists $x_0 \ge a$ such that:
$$
\begin{gather}
x \ge x_0 \implies 0 < \frac{f(x)}{g(x)} < 1 \tag{25}
\end{gather}
$$

Multiplying step 25 by $g(x) > 0$ yields:
$$
\begin{gather}
0 < f(x) < g(x) \quad \text{for all } x \ge x_0 \tag{26}
\end{gather}
$$

Because $\int_a^\infty g(x)\,dx$ converges, domain additivity implies that $\int_{x_0}^\infty g(x)\,dx$ converges. Applying the Direct Comparison Test of Part 1 to step 26 on $[x_0, \infty)$ guarantees that $\int_{x_0}^\infty f(x)\,dx$ converges. By domain additivity, $\int_a^\infty f(x)\,dx$ converges.

### Step 3
Suppose $L = \infty$ and $\int_a^\infty g(x)\,dx$ diverges to $+\infty$. Setting $M = 1 > 0$ in the definition of an infinite limit in step 16, there exists $x_0 \ge a$ such that:
$$
\begin{gather}
x \ge x_0 \implies \frac{f(x)}{g(x)} > 1 \tag{27}
\end{gather}
$$

Multiplying step 27 by $g(x) > 0$ yields:
$$
\begin{gather}
f(x) > g(x) > 0 \quad \text{for all } x \ge x_0 \tag{28}
\end{gather}
$$

Because $\int_a^\infty g(x)\,dx$ diverges to $+\infty$, the tail integral $\int_{x_0}^\infty g(x)\,dx$ diverges to $+\infty$. Applying the Direct Comparison Test of Part 1 to step 28 on $[x_0, \infty)$ guarantees that $\int_{x_0}^\infty f(x)\,dx$ diverges to $+\infty$. By domain additivity, $\int_a^\infty f(x)\,dx$ diverges to $+\infty$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
