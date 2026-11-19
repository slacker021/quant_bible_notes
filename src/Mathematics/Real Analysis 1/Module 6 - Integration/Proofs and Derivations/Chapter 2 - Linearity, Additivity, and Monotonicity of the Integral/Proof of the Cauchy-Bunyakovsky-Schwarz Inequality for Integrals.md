---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ with $a \le b$, and let $f, g \in \mathcal{R}[a, b]$.

---
# Part 1
If $a = b$, both sides of the inequality evaluate to zero by definition of the degenerate integral, satisfying $0 \le 0$.

Assume $a < b$.

Let $\lambda \in \mathbb{R}$ be an arbitrary real parameter.

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), the linear combination $(\lambda f + g)$ belongs to $\mathcal{R}[a, b]$.

By the Integrability of the Product of Integrable Functions ([[Proof of the Integrability of the Product of Integrable Functions]]), the square $(\lambda f + g)^2$ belongs to $\mathcal{R}[a, b]$.

For all $x \in [a, b]$, the algebraic square of a real number is non-negative:
$$
\begin{gather}
\big( \lambda f(x) + g(x) \big)^2 \ge 0 \tag{1}
\end{gather}
$$

By Part 1 of the Monotonicity Theorem ([[Proof of Monotonicity and the Absolute Value Integral Inequality]]), the integral of a non-negative function is non-negative:
$$
\begin{gather}
Q(\lambda) := \int_a^b \big( \lambda f(x) + g(x) \big)^2\,dx \ge 0 \tag{2}
\end{gather}
$$
for all $\lambda \in \mathbb{R}$.

Expanding the integrand of step 2 algebraically:
$$
\begin{gather}
\big( \lambda f(x) + g(x) \big)^2 = \lambda^2 f(x)^2 + 2\lambda f(x)g(x) + g(x)^2 \tag{3}
\end{gather}
$$

Applying the Linearity of the Riemann Integral to step 3 decomposes the integral into a quadratic polynomial in $\lambda$:
$$
\begin{gather}
Q(\lambda) = \lambda^2 \int_a^b f(x)^2\,dx + 2\lambda \int_a^b f(x)g(x)\,dx + \int_a^b g(x)^2\,dx \tag{4}
\end{gather}
$$

Define the real coefficients:
$$
\begin{gather}
A := \int_a^b f(x)^2\,dx, \qquad B := \int_a^b f(x)g(x)\,dx, \qquad C := \int_a^b g(x)^2\,dx \tag{5}
\end{gather}
$$

Because $f(x)^2 \ge 0$ and $g(x)^2 \ge 0$, Part 1 of the Monotonicity Theorem guarantees $A \ge 0$ and $C \ge 0$.

In terms of the coefficients in step 5, step 4 becomes:
$$
\begin{gather}
Q(\lambda) = A\lambda^2 + 2B\lambda + C \ge 0 \quad \text{for all } \lambda \in \mathbb{R} \tag{6}
\end{gather}
$$

Consider first the case where $A = 0$. In this case, step 6 simplifies to:
$$
\begin{gather}
Q(\lambda) = 2B\lambda + C \ge 0 \quad \text{for all } \lambda \in \mathbb{R} \tag{7}
\end{gather}
$$

If $B \ne 0$, choosing the parameter $\lambda_0 := -\frac{C + 1}{2B} \in \mathbb{R}$ evaluates step 7 to:
$$
\begin{gather}
Q(\lambda_0) = 2B\left( -\frac{C + 1}{2B} \right) + C = -(C + 1) + C = -1 < 0 \tag{8}
\end{gather}
$$
which directly contradicts $Q(\lambda) \ge 0$ for all $\lambda \in \mathbb{R}$. Therefore, $A = 0$ implies $B = 0$.

When $A = 0$ and $B = 0$:
$$
\begin{gather}
B^2 = 0 \le 0 \cdot C = AC \tag{9}
\end{gather}
$$
so the inequality $B^2 \le AC$ holds.

Consider next the case where $A > 0$. Completing the square with respect to $\lambda$ in step 6 yields:
$$
\begin{gather}
Q(\lambda) = A\left( \lambda + \frac{B}{A} \right)^2 + C - \frac{B^2}{A} \ge 0 \tag{10}
\end{gather}
$$
for all $\lambda \in \mathbb{R}$.

Evaluating step 10 at the specific point $\lambda^* := -\frac{B}{A} \in \mathbb{R}$:
$$
\begin{gather}
Q(\lambda^*) = A\left( -\frac{B}{A} + \frac{B}{A} \right)^2 + C - \frac{B^2}{A} = C - \frac{B^2}{A} \ge 0 \tag{11}
\end{gather}
$$

Multiplying step 11 by the strictly positive constant $A > 0$:
$$
\begin{gather}
AC - B^2 \ge 0 \implies B^2 \le AC \tag{12}
\end{gather}
$$

Because $B^2 \le AC$ holds both when $A = 0$ (by step 9) and when $A > 0$ (by step 12), substituting the explicit integrals from step 5 yields:
$$
\begin{gather}
\left( \int_a^b f(x)g(x)\,dx \right)^2 \le \left( \int_a^b f(x)^2\,dx \right) \left( \int_a^b g(x)^2\,dx \right) \tag{13}
\end{gather}
$$
---
# Part 2
Let $f, g \in C[a, b]$.

To establish sufficiency, assume $f$ and $g$ are linearly dependent on $[a, b]$. By definition, there exist scalars $\alpha, \beta \in \mathbb{R}$, not both zero, such that:
$$
\begin{gather}
\alpha f(x) + \beta g(x) = 0 \quad \text{for all } x \in [a, b] \tag{14}
\end{gather}
$$

If $\alpha \ne 0$, then $f(x) = k g(x)$ where $k := -\beta/\alpha \in \mathbb{R}$. Substituting $f = k g$ into $B^2$ and $AC$:
$$
\begin{gather}
B^2 = \left( \int_a^b k g(x)^2\,dx \right)^2 = k^2 \left( \int_a^b g(x)^2\,dx \right)^2 \tag{15}
\end{gather}
$$
and
$$
\begin{gather}
AC = \left( \int_a^b k^2 g(x)^2\,dx \right) \left( \int_a^b g(x)^2\,dx \right) = k^2 \left( \int_a^b g(x)^2\,dx \right)^2 \tag{16}
\end{gather}
$$

Because step 15 and step 16 are equal, $B^2 = AC$.

If $\alpha = 0$, then $\beta \ne 0$, forcing $g(x) \equiv 0$ on $[a, b]$. Then $B = 0$ and $C = 0$, giving $B^2 = 0 = AC$. This proves sufficiency.

To establish necessity, assume equality holds in the CBS inequality:
$$
\begin{gather}
B^2 = AC \tag{17}
\end{gather}
$$

If $A = 0$, then $\int_a^b f(x)^2\,dx = 0$. Because $f \in C[a, b]$, the function $f^2$ is continuous and non-negative on $[a, b]$. By Part 2 of the Monotonicity Theorem ([[Proof of Monotonicity and the Absolute Value Integral Inequality]]), if there existed a point $x_0 \in [a, b]$ with $f(x_0)^2 > 0$, then $\int_a^b f^2 > 0$. Because the integral is zero, $f(x)^2 = 0$ for all $x \in [a, b]$, so $f(x) = 0$ identically. Then $1 \cdot f(x) + 0 \cdot g(x) = 0$, with $(\alpha, \beta) = (1, 0) \ne (0, 0)$, establishing that $f$ and $g$ are linearly dependent.

If $A > 0$, evaluate the quadratic polynomial $Q(\lambda)$ at $\lambda^* = -\frac{B}{A}$ using step 11 and step 17:
$$
\begin{gather}
Q(\lambda^*) = C - \frac{B^2}{A} = C - \frac{AC}{A} = C - C = 0 \tag{18}
\end{gather}
$$

By the definition of $Q(\lambda)$ in step 2:
$$
\begin{gather}
\int_a^b \big( \lambda^* f(x) + g(x) \big)^2\,dx = 0 \tag{19}
\end{gather}
$$

Define the auxiliary function $u: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
u(x) := \big( \lambda^* f(x) + g(x) \big)^2 \tag{20}
\end{gather}
$$

Because $f, g \in C[a, b]$, the function $u$ is continuous on $[a, b]$, and $u(x) \ge 0$ for all $x \in [a, b]$.

By Part 2 of the Monotonicity Theorem, because $u \in C[a, b]$, $u(x) \ge 0$, and $\int_a^b u(x)\,dx = 0$, the function $u$ must vanish identically:
$$
\begin{gather}
u(x) = 0 \quad \text{for all } x \in [a, b] \tag{21}
\end{gather}
$$

Taking the square root in step 21:
$$
\begin{gather}
\lambda^* f(x) + g(x) = 0 \quad \text{for all } x \in [a, b] \tag{22}
\end{gather}
$$

Setting $\alpha = \lambda^*$ and $\beta = 1$, the pair $(\alpha, \beta) \ne (0, 0)$ satisfies:
$$
\begin{gather}
\alpha f(x) + \beta g(x) = 0 \quad \text{for all } x \in [a, b] \tag{23}
\end{gather}
$$
which proves that $f$ and $g$ are linearly dependent on $[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
