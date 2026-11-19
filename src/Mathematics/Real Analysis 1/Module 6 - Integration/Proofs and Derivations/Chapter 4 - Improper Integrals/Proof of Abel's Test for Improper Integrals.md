---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f, g: [a, \infty) \to \mathbb{R}$ be functions satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B], \quad g \in C^1[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Because $g$ is continuous on $[a, B]$, $g \in \mathcal{R}[a, B]$, which implies $fg \in \mathcal{R}[a, B]$ for all $B \ge a$.

Assume that the following two hypotheses are satisfied:
1. The improper integral of $f$ converges to a finite real value:
$$
\begin{gather}
I := \int_a^\infty f(x)\,dx = \lim_{B \to \infty} \int_a^B f(x)\,dx \in \mathbb{R} \tag{2}
\end{gather}
$$
2. The function $g$ is monotonic on $[a, \infty)$ and uniformly bounded:
$$
\begin{gather}
\exists K > 0 \quad \text{such that} \quad |g(x)| \le K \quad \text{for all } x \in [a, \infty) \tag{3}
\end{gather}
$$
---
# Step 1
Because $g: [a, \infty) \to \mathbb{R}$ is monotonic and bounded above and below by $[-K, K]$ on $[a, \infty)$, the Monotone Convergence Theorem for real functions on unbounded intervals guarantees that the limit of $g(x)$ as $x \to \infty$ exists and is a finite real number:
$$
\begin{gather}
L := \lim_{x \to \infty} g(x) \in [-K, K] \tag{4}
\end{gather}
$$
---
# Step 2
Define the perturbation function $h: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
h(x) := g(x) - L \tag{5}
\end{gather}
$$

Because $g$ is monotonic, the translated function $h$ is monotonic on $[a, \infty)$. Applying the limit arithmetic theorems to step 5:
$$
\begin{gather}
\lim_{x \to \infty} h(x) = \lim_{x \to \infty} \big( g(x) - L \big) = L - L = 0 \tag{6}
\end{gather}
$$

Expressing $g(x)$ in terms of the constant limit $L$ and the transient $h(x)$:
$$
\begin{gather}
g(x) = L + h(x) \tag{7}
\end{gather}
$$

For every parameter $B \ge a$, the linearity of the proper Riemann integral allows the product $f(x)g(x)$ to be decomposed as:
$$
\begin{gather}
\int_a^B f(x)g(x)\,dx = \int_a^B f(x)\big( L + h(x) \big)\,dx = L \int_a^B f(x)\,dx + \int_a^B f(x)h(x)\,dx \tag{8}
\end{gather}
$$

---
# Step 3
Consider the second term on the right-hand side of step 8:
$$
\begin{gather}
\int_a^B f(x)h(x)\,dx \tag{9}
\end{gather}
$$

The pair of functions $(f, h)$ satisfies all requirements of Dirichlet's Test for Improper Integrals:
1. Because $g \in C^1[a, B]$, the shifted function $h(x) = g(x) - L$ satisfies $h \in C^1[a, B]$ for all $B \ge a$.
2. By step 6, $h$ is monotonic on $[a, \infty)$ and satisfies $\lim_{x \to \infty} h(x) = 0$.
3. Define the accumulation function $F(u) := \int_a^u f(t)\,dt$ for $u \ge a$. By hypothesis step 2, $\lim_{u \to \infty} F(u) = I \in \mathbb{R}$. Setting $\varepsilon = 1$ in the definition of the limit, there exists a threshold $B_0 \ge a$ such that:
$$
\begin{gather}
u > B_0 \implies |F(u) - I| < 1 \implies |F(u)| < |I| + 1 \tag{10}
\end{gather}
$$
Because $f \in \mathcal{R}[a, B_0]$, the accumulation function $F$ is continuous on the compact interval $[a, B_0]$. By the Extreme Value Theorem, $F$ is bounded on $[a, B_0]$:
$$
\begin{gather}
\exists M_0 > 0 \quad \text{such that} \quad |F(u)| \le M_0 \quad \text{for all } u \in [a, B_0] \tag{11}
\end{gather}
$$
Defining $M := \max\{M_0, |I| + 1\} < \infty$, combining step 10 and step 11 yields:
$$
\begin{gather}
|F(u)| = \left| \int_a^u f(t)\,dt \right| \le M \quad \text{for all } u \ge a \tag{12}
\end{gather}
$$
Thus, the primitive of $f$ is uniformly bounded on $[a, \infty)$.

Because all hypotheses of Dirichlet's Test are fulfilled, the improper integral of $fh$ converges to a finite real value:
$$
\begin{gather}
J := \int_a^\infty f(x)h(x)\,dx = \lim_{B \to \infty} \int_a^B f(x)h(x)\,dx \in \mathbb{R} \tag{13}
\end{gather}
$$
---
# Step 4
Taking the limit as $B \to \infty$ across the decomposition in step 8:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B f(x)g(x)\,dx = \lim_{B \to \infty} \left( L \int_a^B f(x)\,dx + \int_a^B f(x)h(x)\,dx \right) \tag{14}
\end{gather}
$$

By the sum and scalar multiple limit laws for real functions, because both component limits exist finitely by step 2 and step 13:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B f(x)g(x)\,dx = L \lim_{B \to \infty} \int_a^B f(x)\,dx + \lim_{B \to \infty} \int_a^B f(x)h(x)\,dx = L \cdot I + J \tag{15}
\end{gather}
$$

Because $L, I, J \in \mathbb{R}$, the value $L \cdot I + J$ is a finite real number. Therefore, the improper integral $\int_a^\infty f(x)g(x)\,dx$ converges.

---
# Step 5
An independent deduction proceeds by applying the Cauchy Criterion directly to the product $fg$.

Let $B_1, B_2 \in [a, \infty)$ satisfy $a \le B_1 < B_2$. By the Second Mean-Value Theorem for Integrals (Weierstrass / du Bois-Reymond form for general monotonic functions), there exists an intermediate point $\xi \in [B_1, B_2]$ such that:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)g(x)\,dx = g(B_1) \int_{B_1}^\xi f(x)\,dx + g(B_2) \int_\xi^{B_2} f(x)\,dx \tag{16}
\end{gather}
$$

Applying the triangle inequality to step 16:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le |g(B_1)| \left| \int_{B_1}^\xi f(x)\,dx \right| + |g(B_2)| \left| \int_\xi^{B_2} f(x)\,dx \right| \tag{17}
\end{gather}
$$

By hypothesis step 3, $|g(x)| \le K$ for all $x \ge a$. Substituting this uniform bound into step 17:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le K \left( \left| \int_{B_1}^\xi f(x)\,dx \right| + \left| \int_\xi^{B_2} f(x)\,dx \right| \right) \tag{18}
\end{gather}
$$

Let $\varepsilon > 0$ be arbitrary. Because the improper integral $\int_a^\infty f(x)\,dx$ converges by hypothesis step 2, by the Cauchy Criterion for Convergence of Improper Integrals, there exists an exhaustion threshold $B_0 \ge a$ such that:
$$
\begin{gather}
u, v > B_0 \implies \left| \int_u^v f(x)\,dx \right| < \frac{\varepsilon}{2K} \tag{19}
\end{gather}
$$

Let $B_1, B_2$ satisfy $B_2 > B_1 > B_0$. Because $B_0 < B_1 \le \xi \le B_2$, both subintervals $[B_1, \xi]$ and $[\xi, B_2]$ have endpoints strictly exceeding $B_0$. Applying step 19:
$$
\begin{gather}
\left| \int_{B_1}^\xi f(x)\,dx \right| < \frac{\varepsilon}{2K}, \qquad \left| \int_\xi^{B_2} f(x)\,dx \right| < \frac{\varepsilon}{2K} \tag{20}
\end{gather}
$$

Substituting the bounds from step 20 into step 18:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)g(x)\,dx \right| \le K \left( \frac{\varepsilon}{2K} + \frac{\varepsilon}{2K} \right) = K \cdot \frac{\varepsilon}{K} = \varepsilon \tag{21}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists $B_0 \ge a$ such that step 21 holds for all $B_2 > B_1 > B_0$, the product $fg$ satisfies the Cauchy Criterion for improper integrals.

By the Cauchy Criterion for Convergence of Improper Integrals, the improper integral $\int_a^\infty f(x)g(x)\,dx$ converges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
