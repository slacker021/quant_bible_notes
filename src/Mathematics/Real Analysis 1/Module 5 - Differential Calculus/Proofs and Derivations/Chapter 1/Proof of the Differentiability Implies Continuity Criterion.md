---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $x_0 \in \text{int}(E)$, and let $f: E \to \mathbb{R}$ be differentiable at $x_0$.

By the definition of differentiability at a point, the increment of the function admits the representation:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = f'(x_0) h + \alpha(h) h \tag{1}
\end{gather}
$$
where $\lim_{h \to 0} \alpha(h) = 0$.

Taking the functional limit as $h \to 0$ on both sides of equation (1):
$$
\begin{gather}
\lim_{h \to 0} \big( f(x_0 + h) - f(x_0) \big) = \lim_{h \to 0} \big( f'(x_0) h + \alpha(h) h \big) \tag{2}
\end{gather}
$$

By the algebraic limit theorems established in Module 3:
$$
\begin{gather}
\lim_{h \to 0} \big( f'(x_0) h \big) = f'(x_0) \cdot \lim_{h \to 0} h = f'(x_0) \cdot 0 = 0 \tag{3} \\
\lim_{h \to 0} \big( \alpha(h) h \big) = \left( \lim_{h \to 0} \alpha(h) \right) \cdot \left( \lim_{h \to 0} h \right) = 0 \cdot 0 = 0 \tag{4}
\end{gather}
$$

Substituting equations (3) and (4) into equation (2) gives:
$$
\begin{gather}
\lim_{h \to 0} \big( f(x_0 + h) - f(x_0) \big) = 0 \implies \lim_{h \to 0} f(x_0 + h) = f(x_0) \tag{5}
\end{gather}
$$

Setting $x := x_0 + h$, the condition $h \to 0$ is equivalent to $x \to x_0$. Thus:
$$
\begin{gather}
\lim_{x \to x_0} f(x) = f(x_0) \tag{6}
\end{gather}
$$

By the Characterization of Continuity at Accumulation Points Theorem (Module 4), condition (6) is the precise definition of pointwise continuity at $x_0$. Consequently, $f$ is continuous at $x_0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
