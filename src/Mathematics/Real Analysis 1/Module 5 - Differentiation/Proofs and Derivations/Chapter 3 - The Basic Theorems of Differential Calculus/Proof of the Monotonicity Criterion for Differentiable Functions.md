---
dg-publish: true
---
Let $\langle a, b \rangle \subseteq \mathbb{R}$ denote a connected non-degenerate interval (open, closed, or half-open, bounded or unbounded), and let $f: \langle a, b \rangle \to \mathbb{R}$ be a function differentiable at every point of $\langle a, b \rangle$.

# Proposition 1
The function $f$ is non-decreasing on $\langle a, b \rangle$ if and only if $f'(x) \ge 0$ for all $x \in \langle a, b \rangle$.

**Necessity ($\implies$):**
Assume that $f$ is non-decreasing on $\langle a, b \rangle$. Let $x_0 \in \langle a, b \rangle$ be an arbitrary point, and consider any $x \in \langle a, b \rangle \setminus \{x_0\}$.
- If $x > x_0$, then monotonicity implies $f(x) \ge f(x_0)$, so $x - x_0 > 0$ and $f(x) - f(x_0) \ge 0$;
- If $x < x_0$, then monotonicity implies $f(x) \le f(x_0)$, so $x - x_0 < 0$ and $f(x) - f(x_0) \le 0$.

In both cases, the difference quotient is non-negative:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} \ge 0, \quad \forall x \in \langle a, b \rangle \setminus \{x_0\} \tag{1}
\end{gather}
$$

Because $f$ is differentiable at $x_0$, taking the limit in step 1 as $x \to x_0$ through $\langle a, b \rangle$ preserves the non-strict inequality:
$$
\begin{gather}
f'(x_0) = \lim_{\langle a, b \rangle \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \ge 0 \tag{2}
\end{gather}
$$
Because $x_0 \in \langle a, b \rangle$ was arbitrary, $f'(x) \ge 0$ for all $x \in \langle a, b \rangle$.

**Sufficiency ($\impliedby$):**
Assume that $f'(x) \ge 0$ for all $x \in \langle a, b \rangle$. Let $x_1, x_2 \in \langle a, b \rangle$ be arbitrary points with $x_1 < x_2$.

Because $\langle a, b \rangle$ is a connected interval, the closed compact subinterval $[x_1, x_2]$ is entirely contained within $\langle a, b \rangle$:
$$
\begin{gather}
[x_1, x_2] \subseteq \langle a, b \rangle \tag{3}
\end{gather}
$$
The restriction $f|_{[x_1, x_2]}$ is continuous on $[x_1, x_2]$ and differentiable on $(x_1, x_2)$. By virtue of [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]], there exists an intermediate point $\xi \in (x_1, x_2)$ such that:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{4}
\end{gather}
$$

Because $\xi \in (x_1, x_2) \subset \langle a, b \rangle$, the hypothesis guarantees that $f'(\xi) \ge 0$. Furthermore, $x_2 - x_1 > 0$. The product of two non-negative terms is non-negative:
$$
\begin{gather}
f'(\xi)(x_2 - x_1) \ge 0 \implies f(x_2) - f(x_1) \ge 0 \implies f(x_1) \le f(x_2) \tag{5}
\end{gather}
$$
Because $x_1 < x_2$ were arbitrary, $f$ is non-decreasing on $\langle a, b \rangle$.

---
# Proposition 2
The function $f$ is non-increasing on $\langle a, b \rangle$ if and only if $f'(x) \le 0$ for all $x \in \langle a, b \rangle$.

Define the auxiliary mapping $g: \langle a, b \rangle \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := -f(x), \quad \forall x \in \langle a, b \rangle \tag{6}
\end{gather}
$$
By definition, $f$ is non-increasing on $\langle a, b \rangle$ if and only if $g$ is non-decreasing on $\langle a, b \rangle$.

By the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]], $g$ is differentiable on $\langle a, b \rangle$ with derivative:
$$
\begin{gather}
g'(x) = -f'(x), \quad \forall x \in \langle a, b \rangle \tag{7}
\end{gather}
$$

Applying Proposition 1 to $g$, the mapping $g$ is non-decreasing if and only if $g'(x) \ge 0$ for all $x \in \langle a, b \rangle$. Substituting step 7:
$$
\begin{gather}
-f'(x) \ge 0 \iff f'(x) \le 0 \tag{8}
\end{gather}
$$
Thus, $f$ is non-increasing if and only if $f'(x) \le 0$ for all $x \in \langle a, b \rangle$.

---
# Proposition 3
If $f'(x) > 0$ for all $x \in \langle a, b \rangle$, then $f$ is strictly increasing on $\langle a, b \rangle$.

Let $x_1, x_2 \in \langle a, b \rangle$ be arbitrary points with $x_1 < x_2$. As in Proposition 1, $[x_1, x_2] \subseteq \langle a, b \rangle$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on $[x_1, x_2]$ yields an intermediate point $\xi \in (x_1, x_2)$ such that:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{9}
\end{gather}
$$

By hypothesis, $f'(\xi) > 0$. Because $x_2 > x_1$, the displacement satisfies $x_2 - x_1 > 0$. The product of two strictly positive numbers is strictly positive:
$$
\begin{gather}
f'(\xi)(x_2 - x_1) > 0 \implies f(x_2) - f(x_1) > 0 \implies f(x_1) < f(x_2) \tag{10}
\end{gather}
$$
Because $x_1 < x_2$ were arbitrary, $f$ is strictly increasing on $\langle a, b \rangle$.

---
# Proposition 4
If $f'(x) < 0$ for all $x \in \langle a, b \rangle$, then $f$ is strictly decreasing on $\langle a, b \rangle$.

Define $g(x) := -f(x)$. The derivative is $g'(x) = -f'(x)$. By hypothesis, $f'(x) < 0$, which implies:
$$
\begin{gather}
g'(x) = -f'(x) > 0, \quad \forall x \in \langle a, b \rangle \tag{11}
\end{gather}
$$

Applying Proposition 3 to $g$, the mapping $g$ is strictly increasing on $\langle a, b \rangle$. Therefore, for all $x_1 < x_2$:
$$
\begin{gather}
g(x_1) < g(x_2) \implies -f(x_1) < -f(x_2) \implies f(x_1) > f(x_2) \tag{12}
\end{gather}
$$
Thus, $f$ is strictly decreasing on $\langle a, b \rangle$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$