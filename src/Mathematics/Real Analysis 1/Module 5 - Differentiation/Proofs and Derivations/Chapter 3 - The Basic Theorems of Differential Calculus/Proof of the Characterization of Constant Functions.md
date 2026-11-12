---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be a connected non-degenerate interval, and let $f: I \to \mathbb{R}$ be a function differentiable at every point of $I$.

**Necessity ($\implies$):**
Assume that $f$ is identically constant on $I$, meaning there exists a scalar $C \in \mathbb{R}$ such that:
$$
\begin{gather}
f(x) = C, \quad \forall x \in I \tag{1}
\end{gather}
$$

Let $x_0 \in I$ be an arbitrary point. For any point $x \in I \setminus \{x_0\}$, the functional values satisfy $f(x) = C$ and $f(x_0) = C$. The difference quotient is therefore identically zero:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} = \frac{C - C}{x - x_0} = \frac{0}{x - x_0} = 0, \quad \forall x \in I \setminus \{x_0\} \tag{2}
\end{gather}
$$

Taking the limit of step 2 as $x \to x_0$ through $I \setminus \{x_0\}$ yields:
$$
\begin{gather}
f'(x_0) = \lim_{I \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{I \ni x \to x_0} 0 = 0 \tag{3}
\end{gather}
$$
Because $x_0 \in I$ was arbitrary, $f'(x) = 0$ for all $x \in I$.

**Sufficiency ($\impliedby$):**
Assume that the derivative vanishes identically across the interval:
$$
\begin{gather}
f'(x) = 0, \quad \forall x \in I \tag{4}
\end{gather}
$$

Fix an anchor point $x_0 \in I$, and let $x \in I$ be an arbitrary point. If $x = x_0$, then $f(x) = f(x_0)$ holds trivially. Suppose now that $x \neq x_0$. Two directional possibilities arise:
1. If $x_0 < x$, the connectedness of the interval $I$ guarantees that the closed interval $[x_0, x]$ is a subset of $I$:
$$
\begin{gather}
[x_0, x] \subseteq I \tag{5}
\end{gather}
$$
Because $f$ is differentiable on $I$, $f$ is continuous on $[x_0, x]$ and differentiable on $(x_0, x)$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on $[x_0, x]$, there exists an intermediate point $\xi \in (x_0, x)$ such that:
$$
\begin{gather}
f(x) - f(x_0) = f'(\xi)(x - x_0) \tag{6}
\end{gather}
$$
Because $\xi \in (x_0, x) \subset I$, step 4 establishes that $f'(\xi) = 0$. Substituting this into step 6 gives:
$$
\begin{gather}
f(x) - f(x_0) = 0 \cdot (x - x_0) = 0 \implies f(x) = f(x_0) \tag{7}
\end{gather}
$$

2. If $x < x_0$, the closed interval $[x, x_0]$ is similarly contained in $I$. Applying Lagrange's theorem on $[x, x_0]$ yields an intermediate point $\eta \in (x, x_0)$ such that:
$$
\begin{gather}
f(x_0) - f(x) = f'(\eta)(x_0 - x) \tag{8}
\end{gather}
$$
Because $\eta \in I$, $f'(\eta) = 0$, whence:
$$
\begin{gather}
f(x_0) - f(x) = 0 \implies f(x) = f(x_0) \tag{9}
\end{gather}
$$

In all cases, $f(x) = f(x_0)$. Setting $C := f(x_0) \in \mathbb{R}$, it follows that $f(x) = C$ for all $x \in I$. Thus, $f$ is identically constant on $I$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$