---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a differentiable function on $(a, b)$.

Recall that a function $f$ is convex on $(a, b)$ if and only if for any three points $x_1 < x < x_2$ in $(a, b)$, the chord slope inequality holds:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{1}
\end{gather}
$$
Furthermore, $f$ is strictly convex if and only if both inequalities in step 1 are strict for all $x_1 < x < x_2$.

---
# Proposition 1
First, assume that $f$ is convex on $(a, b)$. Let $x_1, x_2 \in (a, b)$ be any two points with $x_1 < x_2$. For any intermediate point $x \in (x_1, x_2)$, step 1 provides the outer bounds:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{2}
\end{gather}
$$
Taking the limit as $x \to x_1^+$ on the left-hand side of step 2 yields the instantaneous derivative at $x_1$:
$$
\begin{gather}
f'(x_1) = \lim_{x \to x_1^+} \frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{3}
\end{gather}
$$
Similarly, taking the limit as $x \to x_2^-$ on the right-hand side of step 2 yields:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \lim_{x \to x_2^-} \frac{f(x_2) - f(x)}{x_2 - x} = f'(x_2) \tag{4}
\end{gather}
$$
Chaining step 3 and step 4 establishes that:
$$
\begin{gather}
f'(x_1) \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le f'(x_2) \implies f'(x_1) \le f'(x_2) \tag{5}
\end{gather}
$$
Because $x_1 < x_2$ were arbitrary, step 5 proves that $f'$ is non-decreasing on $(a, b)$.

Conversely, assume that $f'$ is non-decreasing on $(a, b)$. Let $x_1 < x < x_2$ be any three points in $(a, b)$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] to $f$ on $[x_1, x]$ and on $[x, x_2]$ yields two intermediate points $\xi_1 \in (x_1, x)$ and $\xi_2 \in (x, x_2)$ such that:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} = f'(\xi_1) \quad \text{and} \quad \frac{f(x_2) - f(x)}{x_2 - x} = f'(\xi_2) \tag{6}
\end{gather}
$$
Because $\xi_1 < x < \xi_2$, the points satisfy $\xi_1 < \xi_2$. Because $f'$ is non-decreasing, the derivative values satisfy:
$$
\begin{gather}
f'(\xi_1) \le f'(\xi_2) \tag{7}
\end{gather}
$$
Substituting step 6 into step 7 yields:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{8}
\end{gather}
$$
Clearing positive denominators in step 8 gives $(f(x) - f(x_1))(x_2 - x) \le (f(x_2) - f(x))(x - x_1)$, which reorganizes algebraically to:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{9}
\end{gather}
$$
Thus, $f$ satisfies the chord slope criterion of convexity across $(a, b)$.

---
# Proposition 2
First, assume that $f$ is strictly convex on $(a, b)$. By Proposition 1, $f'$ is non-decreasing. To show that $f'$ is strictly increasing, suppose by contradiction that there exist $x_1 < x_2$ such that $f'(x_1) = f'(x_2)$. Because $f'$ is non-decreasing, $f'(x)$ must be identically constant on $[x_1, x_2]$:
$$
\begin{gather}
f'(x) = C, \quad \forall x \in [x_1, x_2] \tag{10}
\end{gather}
$$
Integrating or applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] shows that $f(x) = C x + D$ on $[x_1, x_2]$ for some constant $D$. For an affine function, the chord inequality in step 1 holds with exact equality:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} = C = \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{11}
\end{gather}
$$
which directly contradicts the strict convexity of $f$. Hence, $f'(x_1) < f'(x_2)$ for all $x_1 < x_2$.

Conversely, assume that $f'$ is strictly increasing on $(a, b)$. Let $x_1 < x < x_2$. The intermediate points from Lagrange's theorem satisfy $\xi_1 < x < \xi_2$. Because $f'$ is strictly increasing:
$$
\begin{gather}
f'(\xi_1) < f'(\xi_2) \tag{12}
\end{gather}
$$
Substituting step 6 into step 12 yields the strict chord inequality:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} < \frac{f(x_2) - f(x)}{x_2 - x} \tag{13}
\end{gather}
$$
which is equivalent to strict convexity on $(a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
