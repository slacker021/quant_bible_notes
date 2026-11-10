---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be a non-empty subset, let $x_0 \in E \cap E'$ be an accumulation point of $E$, and let $f: E \to \mathbb{R}$ and $g: E \to \mathbb{R}$ be functions that are differentiable at $x_0$. Let $\alpha, \beta \in \mathbb{R}$ be arbitrary real scalars.

Define the linear combination mapping $h: E \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
h(x) := (\alpha f + \beta g)(x) = \alpha f(x) + \beta g(x), \quad \forall x \in E \tag{1}
\end{gather}
$$

Because $f$ and $g$ are differentiable at $x_0$, the respective limits of their difference quotients exist as finite real numbers:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{2}
\end{gather}
$$
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{g(x) - g(x_0)}{x - x_0} = g'(x_0) \tag{3}
\end{gather}
$$

For any point $x \in E \setminus \{x_0\}$, the difference quotient of the linear combination $h$ admits the algebraic decomposition:
$$
\begin{gather}
\frac{h(x) - h(x_0)}{x - x_0} = \frac{(\alpha f(x) + \beta g(x)) - (\alpha f(x_0) + \beta g(x_0))}{x - x_0} \tag{4}
\end{gather}
$$

Regrouping terms in the numerator of step 4 yields:
$$
\begin{gather}
\frac{h(x) - h(x_0)}{x - x_0} = \alpha \frac{f(x) - f(x_0)}{x - x_0} + \beta \frac{g(x) - g(x_0)}{x - x_0} \tag{5}
\end{gather}
$$

By virtue of the linearity of the limit operator under algebraic field operations on $\mathbb{R}$ established in [[Chapter 2 - Limits of Functions|Module 3, Chapter 2]], taking the limit of both sides of step 5 as $x \to x_0$ through $E \setminus \{x_0\}$ gives:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{h(x) - h(x_0)}{x - x_0} = \alpha \left(\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}\right) + \beta \left(\lim_{E \ni x \to x_0} \frac{g(x) - g(x_0)}{x - x_0}\right) \tag{6}
\end{gather}
$$

Substituting the finite derivative limits of step 2 and step 3 into step 6 produces:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{h(x) - h(x_0)}{x - x_0} = \alpha f'(x_0) + \beta g'(x_0) \tag{7}
\end{gather}
$$

Because the limit on the left-hand side of step 7 exists and is finite, the linear combination $(\alpha f + \beta g)$ is differentiable at $x_0$, and its derivative satisfies:
$$
\begin{gather}
(\alpha f + \beta g)'(x_0) = \alpha f'(x_0) + \beta g'(x_0) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
