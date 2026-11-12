---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a differentiable function on $(a, b)$.

First, assume that $f$ is convex on $(a, b)$. Let $x_0 \in (a, b)$ be an arbitrary anchor point, and let $x \in (a, b)$ be any point.

If $x > x_0$, the restriction of $f$ to $[x_0, x]$ satisfies the hypotheses of [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]]. There exists an intermediate point $\xi \in (x_0, x)$ such that:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} = f'(\xi) \tag{1}
\end{gather}
$$
Because $f$ is convex, [[Proof of First-Order Monotonicity Characterization of Convexity|The First-Order Monotonicity Characterization of Convexity]] guarantees that $f'$ is non-decreasing on $(a, b)$. Because $x_0 < \xi$, the derivative values satisfy:
$$
\begin{gather}
f'(x_0) \le f'(\xi) \tag{2}
\end{gather}
$$
Substituting step 2 into step 1 yields:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} \ge f'(x_0) \tag{3}
\end{gather}
$$
Because $x - x_0 > 0$, multiplying step 3 by $x - x_0$ preserves the inequality:
$$
\begin{gather}
f(x) - f(x_0) \ge f'(x_0)(x - x_0) \iff f(x) \ge f(x_0) + f'(x_0)(x - x_0) \tag{4}
\end{gather}
$$

If $x < x_0$, Lagrange's theorem on $[x, x_0]$ yields an intermediate point $\eta \in (x, x_0)$ such that:
$$
\begin{gather}
\frac{f(x_0) - f(x)}{x_0 - x} = f'(\eta) \tag{5}
\end{gather}
$$
Because $\eta < x_0$ and $f'$ is non-decreasing, $f'(\eta) \le f'(x_0)$. Substituting this bound into step 5 yields:
$$
\begin{gather}
\frac{f(x_0) - f(x)}{x_0 - x} \le f'(x_0) \tag{6}
\end{gather}
$$
Because $x_0 - x > 0$, multiplying step 6 by $x_0 - x$ gives:
$$
\begin{gather}
f(x_0) - f(x) \le f'(x_0)(x_0 - x) = -f'(x_0)(x - x_0) \tag{7}
\end{gather}
$$
Rearranging step 7 recovers the identical inequality:
$$
\begin{gather}
f(x) \ge f(x_0) + f'(x_0)(x - x_0) \tag{8}
\end{gather}
$$
For $x = x_0$, the inequality holds as a trivial identity $f(x_0) \ge f(x_0)$. Thus, step 4 holds for all $x, x_0 \in (a, b)$.

Furthermore, if $f$ is strictly convex, $f'$ is strictly increasing. In this case, $x_0 < \xi$ implies $f'(x_0) < f'(\xi)$, and $\eta < x_0$ implies $f'(\eta) < f'(x_0)$. Thus, the inequalities in step 4 and step 8 are strict for all $x \neq x_0$.

Conversely, assume that for every $x_0 \in (a, b)$ and every $x \in (a, b)$:
$$
\begin{gather}
f(x) \ge f(x_0) + f'(x_0)(x - x_0) \tag{9}
\end{gather}
$$
Let $x_1, x_2 \in (a, b)$ with $x_1 \neq x_2$, let $\lambda \in (0, 1)$, and define the convex combination:
$$
\begin{gather}
x_0 := (1 - \lambda)x_1 + \lambda x_2 \in (a, b) \tag{10}
\end{gather}
$$
Rearranging step 10 shows that:
$$
\begin{gather}
x_1 - x_0 = \lambda(x_1 - x_2) \quad \text{and} \quad x_2 - x_0 = (1 - \lambda)(x_2 - x_1) \tag{11}
\end{gather}
$$
Applying the supporting tangent inequality of step 9 at the anchor point $x_0$ to both $x = x_1$ and $x = x_2$ yields:
$$
\begin{gather}
f(x_1) \ge f(x_0) + f'(x_0)(x_1 - x_0) \tag{12}
\end{gather}
$$
$$
\begin{gather}
f(x_2) \ge f(x_0) + f'(x_0)(x_2 - x_0) \tag{13}
\end{gather}
$$
Multiplying step 12 by $(1 - \lambda) > 0$ and step 13 by $\lambda > 0$, and summing the two resulting inequalities produces:
$$
\begin{gather}
(1 - \lambda)f(x_1) + \lambda f(x_2) \ge \big[(1 - \lambda) + \lambda\big] f(x_0) + f'(x_0)\big[(1 - \lambda)(x_1 - x_0) + \lambda(x_2 - x_0)\big] \tag{14}
\end{gather}
$$
By step 10, the linear bracketed displacement vanishes:
$$
\begin{gather}
(1 - \lambda)(x_1 - x_0) + \lambda(x_2 - x_0) = (1 - \lambda)x_1 + \lambda x_2 - x_0 = x_0 - x_0 = 0 \tag{15}
\end{gather}
$$
Substituting step 15 into step 14 simplifies the bound to:
$$
\begin{gather}
(1 - \lambda)f(x_1) + \lambda f(x_2) \ge f(x_0) = f\big((1 - \lambda)x_1 + \lambda x_2\big) \tag{16}
\end{gather}
$$
Step 16 is the definition of convexity on $(a, b)$. If the inequality in step 9 is strict for all $x \neq x_0$, then step 12 and step 13 are strict, yielding strict inequality in step 16, which proves strict convexity.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
