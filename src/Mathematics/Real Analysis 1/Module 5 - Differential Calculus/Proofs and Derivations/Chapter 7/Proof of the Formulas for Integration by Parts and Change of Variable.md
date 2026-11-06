---
dg-publish: true
---
### Part 1: Integration by Parts
Let $u, v: I \to \mathbb{R}$ be continuously differentiable on an interval $I \subseteq \mathbb{R}$.

By Theorem 2.1 (The Leibniz Product Rule), the product function $(u v)$ is differentiable on $I$, with:
$$
\begin{gather}
(u(x) v(x))' = u'(x) v(x) + u(x) v'(x) \tag{1}
\end{gather}
$$

Rearranging terms:
$$
\begin{gather}
u(x) v'(x) = (u(x) v(x))' - u'(x) v(x) \tag{2}
\end{gather}
$$

Taking the indefinite integral on both sides:
$$
\begin{gather}
\int u(x) v'(x) \, dx = \int (u(x) v(x))' \, dx - \int u'(x) v(x) \, dx \tag{3}
\end{gather}
$$

By definition of the primitive, $\int (u(x)v(x))' \, dx = u(x)v(x) + C_0$. Absorbing constants into the indefinite integrals yields:
$$
\begin{gather}
\int u(x) v'(x) \, dx = u(x) v(x) - \int u'(x) v(x) \, dx \tag{4}
\end{gather}
$$

In differential notation where $dv = v'(x)dx$ and $du = u'(x)dx$:
$$
\begin{gather}
\int u \, dv = uv - \int v \, du \tag{5}
\end{gather}
$$

### Part 2: Change of Variable (Substitution)
Let $\varphi: J \to I$ be a differentiable function on an interval $J$, and suppose $F: I \to \mathbb{R}$ is a primitive of $f$ on $I$, meaning $F'(x) = f(x)$ for all $x \in I$.

Consider the composite function $\Phi: J \to \mathbb{R}$ defined by:
$$
\begin{gather}
\Phi(t) := (F \circ \varphi)(t) = F(\varphi(t)) \tag{6}
\end{gather}
$$

By Theorem 2.3 (The Chain Rule), $\Phi$ is differentiable on $J$, with derivative:
$$
\begin{gather}
\Phi'(t) = F'(\varphi(t)) \cdot \varphi'(t) \tag{7}
\end{gather}
$$

Because $F'(x) = f(x)$, substituting $x = \varphi(t)$ into equation (7) gives:
$$
\begin{gather}
\Phi'(t) = f(\varphi(t)) \cdot \varphi'(t) \tag{8}
\end{gather}
$$

By Definition 7.1, equation (8) proves that $\Phi(t) = F(\varphi(t))$ is a primitive of the function $t \mapsto f(\varphi(t)) \varphi'(t)$ on $J$. 

Therefore, taking the indefinite integral:
$$
\begin{gather}
\int f(\varphi(t)) \varphi'(t) \, dt = \Phi(t) + C = F(\varphi(t)) + C = \left( \int f(x) \, dx \right)\Bigg|_{x = \varphi(t)} \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
