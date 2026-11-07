---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $F_1, F_2: I \to \mathbb{R}$ be two primitives of the same function $f: I \to \mathbb{R}$.

By the definition of the primitive, for all $x \in I$:
$$
\begin{gather}
F_1'(x) = f(x) \quad \text{and} \quad F_2'(x) = f(x) \tag{1}
\end{gather}
$$

Define the auxiliary difference function $\Phi: I \to \mathbb{R}$ by:
$$
\begin{gather}
\Phi(x) := F_1(x) - F_2(x) \tag{2}
\end{gather}
$$

Because $F_1$ and $F_2$ are differentiable on $I$, by linearity of derivatives $\Phi$ is differentiable on $I$, with:
$$
\begin{gather}
\Phi'(x) = F_1'(x) - F_2'(x) = f(x) - f(x) = 0 \quad \forall x \in I \tag{3}
\end{gather}
$$

Fix an arbitrary reference point $x_0 \in I$. 

For any other point $x \in I$ with $x \neq x_0$, the closed interval with endpoints $x_0$ and $x$ is contained in $I$ because $I$ is an interval. 

By Lagrange's Mean Value Theorem applied to $\Phi$ on this interval, there exists an intermediate point $\xi$ strictly between $x_0$ and $x$ such that:
$$
\begin{gather}
\Phi(x) - \Phi(x_0) = \Phi'(\xi)(x - x_0) \tag{4}
\end{gather}
$$

By equation (3), $\Phi'(\xi) = 0$. Therefore:
$$
\begin{gather}
\Phi(x) - \Phi(x_0) = 0 \cdot (x - x_0) = 0 \implies \Phi(x) = \Phi(x_0) \tag{5}
\end{gather}
$$

Setting $C := \Phi(x_0) = F_1(x_0) - F_2(x_0) \in \mathbb{R}$, equation (5) proves that:
$$
\begin{gather}
F_1(x) - F_2(x) \equiv C \quad \forall x \in I \tag{6}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
