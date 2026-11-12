---
dg-publish: true
---
Let $f, g: [a, b] \to \mathbb{R}$ be two real-valued functions defined on the closed interval $[a, b]$ with $a < b$, satisfying the following hypotheses:
1. Both $f$ and $g$ are continuous on the compact interval $[a, b]$;
2. Both $f$ and $g$ are differentiable on the open interior interval $(a, b)$.

Define the auxiliary scalar function $F: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
F(x) := \big(f(b) - f(a)\big) g(x) - \big(g(b) - g(a)\big) f(x), \quad \forall x \in [a, b] \tag{1}
\end{gather}
$$

The analytical properties of $F$ on $[a, b]$ are established as follows:
- **Continuity:** The functions $f$ and $g$ are continuous on $[a, b]$ by hypothesis 1. Because $(f(b) - f(a))$ and $(g(b) - g(a))$ are constant real scalars, the linear combination $F$ is continuous on $[a, b]$ by virtue of the algebraic continuity theorems established in [[Chapter 1 - Continuity of Functions|Module 4, Chapter 1]].
- **Differentiability:** By hypothesis 2, both $f$ and $g$ are differentiable on $(a, b)$. By the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]], the function $F$ is differentiable on $(a, b)$, and its derivative is given by:
$$
\begin{gather}
F'(x) = \big(f(b) - f(a)\big) g'(x) - \big(g(b) - g(a)\big) f'(x), \quad \forall x \in (a, b) \tag{2}
\end{gather}
$$
- **Boundary Equalities:** Evaluating $F$ at the left endpoint $x = a$:
$$
\begin{gather}
F(a) = \big(f(b) - f(a)\big) g(a) - \big(g(b) - g(a)\big) f(a) \tag{3}
\end{gather}
$$
Expanding the products in step 3:
$$
\begin{gather}
F(a) = f(b) g(a) - f(a) g(a) - g(b) f(a) + g(a) f(a) = f(b) g(a) - g(b) f(a) \tag{4}
\end{gather}
$$
Evaluating $F$ at the right endpoint $x = b$:
$$
\begin{gather}
F(b) = \big(f(b) - f(a)\big) g(b) - \big(g(b) - g(a)\big) f(b) \tag{5}
\end{gather}
$$
Expanding the products in step 5:
$$
\begin{gather}
F(b) = f(b) g(b) - f(a) g(b) - g(b) f(b) + g(a) f(b) = g(a) f(b) - f(a) g(b) \tag{6}
\end{gather}
$$
Comparing step 4 and step 6 confirms that:
$$
\begin{gather}
F(a) = F(b) \tag{7}
\end{gather}
$$

The auxiliary mapping $F$ satisfies all hypotheses of [[Proof of Rolle's Theorem|Rolle's Mean Value Theorem]] on $[a, b]$. Therefore, there exists at least one intermediate point $\xi \in (a, b)$ such that:
$$
\begin{gather}
F'(\xi) = 0 \tag{8}
\end{gather}
$$

Substituting the derivative of step 2 evaluated at $\xi$ into step 8 yields:
$$
\begin{gather}
\big(f(b) - f(a)\big) g'(\xi) - \big(g(b) - g(a)\big) f'(\xi) = 0 \tag{9}
\end{gather}
$$
Rearranging the terms in step 9 establishes the identity:
$$
\begin{gather}
\big(f(b) - f(a)\big) g'(\xi) = \big(g(b) - g(a)\big) f'(\xi) \tag{10}
\end{gather}
$$

Now suppose in addition that $g'(x) \neq 0$ for all $x \in (a, b)$. If the difference $g(b) - g(a)$ were equal to zero, then $g(a) = g(b)$, and applying Rolle's theorem to $g$ on $[a, b]$ would produce a point $\eta \in (a, b)$ satisfying $g'(\eta) = 0$, contradicting the assumption. Therefore:
$$
\begin{gather}
g(b) - g(a) \neq 0 \tag{11}
\end{gather}
$$
Because $g'(\xi) \neq 0$ and $g(b) - g(a) \neq 0$, dividing step 10 by $(g(b) - g(a)) g'(\xi)$ yields the fractional representation:
$$
\begin{gather}
\frac{f(b) - f(a)}{g(b) - g(a)} = \frac{f'(\xi)}{g'(\xi)} \tag{12}
\end{gather}
$$
where $\xi \in (a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$