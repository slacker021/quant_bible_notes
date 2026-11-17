---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f, g \in \mathcal{R}[a, b]$, and assume that $g$ does not change sign on $[a, b]$, meaning that either $g(x) \ge 0$ for all $x \in [a, b]$, or $g(x) \le 0$ for all $x \in [a, b]$.

Define the infimum and supremum of $f$ on $[a, b]$ by:
$$
\begin{gather}
m := \inf_{x \in [a, b]} f(x), \qquad M := \sup_{x \in [a, b]} f(x) \tag{1}
\end{gather}
$$

By the Integrability of the Product of Integrable Functions ([[Proof of the Integrability of the Product of Integrable Functions]]), the product function satisfies:
$$
\begin{gather}
fg \in \mathcal{R}[a, b] \tag{2}
\end{gather}
$$
---
# Theorem 1
Assume $g(x) \ge 0$ for all $x \in [a, b]$.

By definition of the infimum and supremum in step 1, the function $f$ satisfies:
$$
\begin{gather}
m \le f(x) \le M \quad \text{for all } x \in [a, b] \tag{3}
\end{gather}
$$

Multiplying step 3 by the non-negative real number $g(x) \ge 0$ preserves the direction of the inequalities:
$$
\begin{gather}
m g(x) \le f(x)g(x) \le M g(x) \quad \text{for all } x \in [a, b] \tag{4}
\end{gather}
$$

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), the scalar multiples $m g$ and $M g$ belong to $\mathcal{R}[a, b]$.

Applying Part 3 (Monotonicity) of the Monotonicity and the Absolute Value Integral Inequality ([[Proof of Monotonicity and the Absolute Value Integral Inequality]]) to step 4:
$$
\begin{gather}
\int_a^b m g(x)\,dx \le \int_a^b f(x)g(x)\,dx \le \int_a^b M g(x)\,dx \tag{5}
\end{gather}
$$

Factoring out the constants $m$ and $M$ by the Linearity of the Riemann Integral:
$$
\begin{gather}
m \int_a^b g(x)\,dx \le \int_a^b f(x)g(x)\,dx \le M \int_a^b g(x)\,dx \tag{6}
\end{gather}
$$

Because $g(x) \ge 0$, Part 1 of the Monotonicity Theorem guarantees:
$$
\begin{gather}
\int_a^b g(x)\,dx \ge 0 \tag{7}
\end{gather}
$$

Consider first the subcase where $\int_a^b g(x)\,dx = 0$. Substituting this into step 6 gives:
$$
\begin{gather}
m \cdot 0 \le \int_a^b f(x)g(x)\,dx \le M \cdot 0 \implies 0 \le \int_a^b f(x)g(x)\,dx \le 0 \tag{8}
\end{gather}
$$
which forces:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = 0 \tag{9}
\end{gather}
$$

In this subcase, choosing $\mu = m \in [m, M]$ satisfies:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = 0 = \mu \cdot 0 = \mu \int_a^b g(x)\,dx \tag{10}
\end{gather}
$$
Moreover, if $f \in C[a, b]$, any point $\xi \in [a, b]$ satisfies:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = 0 = f(\xi) \cdot 0 = f(\xi) \int_a^b g(x)\,dx \tag{11}
\end{gather}
$$

Consider next the subcase where $\int_a^b g(x)\,dx > 0$. Dividing the compound inequality of step 6 by the strictly positive integral $\int_a^b g(x)\,dx > 0$:
$$
\begin{gather}
m \le \frac{\int_a^b f(x)g(x)\,dx}{\int_a^b g(x)\,dx} \le M \tag{12}
\end{gather}
$$

Define the real value $\mu$ by:
$$
\begin{gather}
\mu := \frac{\int_a^b f(x)g(x)\,dx}{\int_a^b g(x)\,dx} \tag{13}
\end{gather}
$$

By step 12, $\mu$ satisfies:
$$
\begin{gather}
\mu \in [m, M] \tag{14}
\end{gather}
$$

Multiplying step 13 by $\int_a^b g(x)\,dx$ establishes:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = \mu \int_a^b g(x)\,dx \tag{15}
\end{gather}
$$
which proves the Bounded Form for non-negative weights.

If additionally $f \in C[a, b]$, the Extreme Value Theorem (Weierstrass Theorem) ensures that $f$ attains both $m$ and $M$ on the compact interval $[a, b]$: there exist $x_{\min}, x_{\max} \in [a, b]$ with $f(x_{\min}) = m$ and $f(x_{\max}) = M$.

Because $f$ is continuous on the subinterval joining $x_{\min}$ and $x_{\max}$, and because $\mu \in [m, M]$ by step 14, the Intermediate Value Theorem (Bolzano-Cauchy Theorem) guarantees the existence of a point $\xi \in [a, b]$ such that:
$$
\begin{gather}
f(\xi) = \mu \tag{16}
\end{gather}
$$

Substituting step 16 into step 15 yields:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(\xi) \int_a^b g(x)\,dx \tag{17}
\end{gather}
$$
which proves the Continuous Form for non-negative weights.

---
# Theorem 2
Assume $g(x) \le 0$ for all $x \in [a, b]$.

Define the auxiliary function $\tilde{g}: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
\tilde{g}(x) := -g(x) \tag{18}
\end{gather}
$$

By the Linearity of the Riemann Integral, $\tilde{g} \in \mathcal{R}[a, b]$. Because $g(x) \le 0$, the auxiliary function satisfies:
$$
\begin{gather}
\tilde{g}(x) \ge 0 \quad \text{for all } x \in [a, b] \tag{19}
\end{gather}
$$

Applying Case 1 to the function pair $(f, \tilde{g})$ guarantees the existence of a real number $\mu \in [m, M]$ such that:
$$
\begin{gather}
\int_a^b f(x)\tilde{g}(x)\,dx = \mu \int_a^b \tilde{g}(x)\,dx \tag{20}
\end{gather}
$$

By the Linearity of the Riemann Integral:
$$
\begin{gather}
\int_a^b f(x)\tilde{g}(x)\,dx = \int_a^b f(x)\big( -g(x) \big)\,dx = -\int_a^b f(x)g(x)\,dx \tag{21}
\end{gather}
$$
and
$$
\begin{gather}
\int_a^b \tilde{g}(x)\,dx = \int_a^b \big( -g(x) \big)\,dx = -\int_a^b g(x)\,dx \tag{22}
\end{gather}
$$

Substituting step 21 and step 22 into step 20:
$$
\begin{gather}
-\int_a^b f(x)g(x)\,dx = -\mu \int_a^b g(x)\,dx \tag{23}
\end{gather}
$$

Multiplying step 23 by $-1$:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = \mu \int_a^b g(x)\,dx \tag{24}
\end{gather}
$$
with $\mu \in [m, M]$, establishing the Bounded Form.

If additionally $f \in C[a, b]$, applying Case 1 directly yields an intermediate point $\xi \in [a, b]$ satisfying $f(\xi) = \mu$, so:
$$
\begin{gather}
\int_a^b f(x)g(x)\,dx = f(\xi) \int_a^b g(x)\,dx \tag{25}
\end{gather}
$$
establishing the Continuous Form.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
