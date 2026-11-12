---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a function differentiable everywhere on $(a, b)$.

---
# Proposition 1
Assume that $f'(x) > 0$ for all $x \in (a, b)$. Let $x_1, x_2 \in (a, b)$ be two arbitrary points satisfying $x_1 < x_2$.

Because $f$ is differentiable on $(a, b)$, the restriction of $f$ to the closed compact subinterval $[x_1, x_2]$ is continuous on $[x_1, x_2]$ and differentiable on the open subinterval $(x_1, x_2)$. By virtue of [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]], there exists an intermediate point $\xi \in (x_1, x_2)$ such that:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{1}
\end{gather}
$$

Because $x_1 < x_2$, the displacement of the argument is strictly positive:
$$
\begin{gather}
x_2 - x_1 > 0 \tag{2}
\end{gather}
$$
Furthermore, because $\xi \in (x_1, x_2) \subset (a, b)$, the hypothesis entails:
$$
\begin{gather}
f'(\xi) > 0 \tag{3}
\end{gather}
$$
Multiplying the strictly positive real numbers of step 2 and step 3 demonstrates that the right-hand side of step 1 is strictly positive:
$$
\begin{gather}
f(x_2) - f(x_1) > 0 \iff f(x_1) < f(x_2) \tag{4}
\end{gather}
$$
Because the pair $x_1 < x_2$ was chosen arbitrarily in $(a, b)$, step 4 establishes that $f$ is strictly increasing across $(a, b)$.

---
# Proposition 2
First, assume that $f'(x) \ge 0$ for all $x \in (a, b)$. Let $x_1, x_2 \in (a, b)$ be any two points satisfying $x_1 < x_2$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on $[x_1, x_2]$ yields an intermediate point $\xi \in (x_1, x_2)$ satisfying:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{5}
\end{gather}
$$
Because $x_2 - x_1 > 0$ and $f'(\xi) \ge 0$, the product satisfies:
$$
\begin{gather}
f(x_2) - f(x_1) \ge 0 \iff f(x_1) \le f(x_2) \tag{6}
\end{gather}
$$
Thus, $f$ is non-decreasing on $(a, b)$.

Conversely, suppose that $f$ is non-decreasing on $(a, b)$. Let $x_0 \in (a, b)$ be an arbitrary point. For any point $x \in (a, b)$ with $x > x_0$, the non-decreasing property entails:
$$
\begin{gather}
f(x) \ge f(x_0) \implies f(x) - f(x_0) \ge 0 \tag{7}
\end{gather}
$$
Dividing by the strictly positive difference $x - x_0 > 0$ produces:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} \ge 0 \tag{8}
\end{gather}
$$
Because $f$ is differentiable at $x_0$, the limit of the difference quotient exists. By the preservation of non-strict inequalities under functional limits:
$$
\begin{gather}
f'(x_0) = \lim_{x \to x_0^+} \frac{f(x) - f(x_0)}{x - x_0} \ge 0 \tag{9}
\end{gather}
$$
Because $x_0 \in (a, b)$ was arbitrary, $f'(x) \ge 0$ holds for all $x \in (a, b)$.

---
# Proposition 3
Assume that $f'(x) \equiv 0$ for all $x \in (a, b)$. Fix an anchor point $x_0 \in (a, b)$, and let $x \in (a, b)$ be any distinct point. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on the closed interval between $x_0$ and $x$ yields an intermediate point $\xi$ lying strictly between $x_0$ and $x$ such that:
$$
\begin{gather}
f(x) - f(x_0) = f'(\xi)(x - x_0) \tag{10}
\end{gather}
$$
Because $\xi \in (a, b)$, the derivative vanishes: $f'(\xi) = 0$. Step 10 reduces immediately to:
$$
\begin{gather}
f(x) - f(x_0) = 0 \iff f(x) = f(x_0) \tag{11}
\end{gather}
$$
Because $x$ was arbitrary, $f$ is identically constant across $(a, b)$.

Conversely, if $f(x) \equiv C$ for some constant $C \in \mathbb{R}$, the difference quotient at every $x \in (a, b)$ vanishes identically for all $h \neq 0$:
$$
\begin{gather}
\frac{f(x + h) - f(x)}{h} = \frac{C - C}{h} = 0 \tag{12}
\end{gather}
$$
Taking the limit as $h \to 0$ demonstrates that $f'(x) = 0$ for all $x \in (a, b)$.

---
# Proposition 4
Define the auxiliary function $g: (a, b) \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := -f(x), \quad \forall x \in (a, b) \tag{13}
\end{gather}
$$
By virtue of the linearity of differentiation, $g$ is differentiable on $(a, b)$ with derivative:
$$
\begin{gather}
g'(x) = -f'(x) \tag{14}
\end{gather}
$$
The condition $f'(x) \le 0$ holds for all $x \in (a, b)$ if and only if $g'(x) \ge 0$ for all $x \in (a, b)$. By Proposition 2, $g'(x) \ge 0$ is equivalent to $g$ being non-decreasing on $(a, b)$, which holds if and only if $f = -g$ is non-increasing on $(a, b)$.

---
# Proposition 5
Let $g: (a, b) \to \mathbb{R}$ be defined by $g(x) := -f(x)$. The derivative is $g'(x) = -f'(x)$. If $f'(x) < 0$ for all $x \in (a, b)$, then $g'(x) > 0$ for all $x \in (a, b)$. By Proposition 1, $g$ is strictly increasing on $(a, b)$. Consequently, for any $x_1 < x_2$, the relation $g(x_1) < g(x_2)$ holds, which is equivalent to:
$$
\begin{gather}
-f(x_1) < -f(x_2) \iff f(x_1) > f(x_2) \tag{15}
\end{gather}
$$
Therefore, $f$ is strictly decreasing across $(a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
