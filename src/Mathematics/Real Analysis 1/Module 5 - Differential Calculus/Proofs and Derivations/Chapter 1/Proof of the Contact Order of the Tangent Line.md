---
dg-publish: true
---
Let $f: U(x_0) \to \mathbb{R}$ be defined on a neighborhood $U(x_0)$ of $x_0$, and let $\varphi(x) = c_0 + c_1(x - x_0)$ be an arbitrary affine function.

### Part 1: Contact of Order 0
By the definition of contact of order $n$, $\varphi$ has contact of order 0 with $f$ at $x_0$ if:
$$
\begin{gather}
f(x) - \varphi(x) = o((x - x_0)^0) = o(1) \quad \text{as } x \to x_0 \tag{1}
\end{gather}
$$

The condition of step 1 is equivalent to:
$$
\begin{gather}
\lim_{x \to x_0} \big( f(x) - (c_0 + c_1(x - x_0)) \big) = 0 \tag{2}
\end{gather}
$$

Evaluating the limit:
$$
\begin{gather}
\lim_{x \to x_0} f(x) - c_0 - c_1 \cdot 0 = 0 \implies \lim_{x \to x_0} f(x) = c_0 \tag{3}
\end{gather}
$$

Because $x_0 \in U(x_0)$, evaluating at $x = x_0$ requires $f(x_0) - c_0 = 0 \implies c_0 = f(x_0)$. Substituting $c_0 = f(x_0)$ into the equation of step 3 yields $\lim_{x \to x_0} f(x) = f(x_0)$, which is the definition of continuity of $f$ at $x_0$.

### Part 2: Contact of Order 1
By the definition of contact of order $n$, $\varphi(x)$ has contact of order 1 with $f$ at $x_0$ if:
$$
\begin{gather}
f(x) - \varphi(x) = o(x - x_0) \quad \text{as } x \to x_0 \tag{4}
\end{gather}
$$

Because $o(x - x_0)$ implies $o(1)$, Part 1 mandates that $c_0 = f(x_0)$ and $f$ is continuous at $x_0$. Substituting $c_0 = f(x_0)$ into the condition of step 4 gives:
$$
\begin{gather}
f(x) - f(x_0) - c_1(x - x_0) = o(x - x_0) \quad \text{as } x \to x_0 \tag{5}
\end{gather}
$$

Rearranging the equation of step 5:
$$
\begin{gather}
f(x) - f(x_0) = c_1(x - x_0) + o(x - x_0) \quad \text{as } x \to x_0 \tag{6}
\end{gather}
$$

Comparing the equation of step 6 directly with the definition of differentiability at a point (with increment $h = x - x_0$), the condition of step 6 holds if and only if $f$ is differentiable at $x_0$ and the coefficient $c_1$ equals the derivative:
$$
\begin{gather}
c_1 = f'(x_0) \tag{7}
\end{gather}
$$

Therefore, the unique affine function having contact of order 1 is:
$$
\begin{gather}
\varphi(x) = f(x_0) + f'(x_0)(x - x_0) = T(x) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
