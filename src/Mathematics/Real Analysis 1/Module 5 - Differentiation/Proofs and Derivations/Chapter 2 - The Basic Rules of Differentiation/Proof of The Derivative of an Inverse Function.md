---
dg-publish: true
---
Let $X, Y \subset \mathbb{R}$ be open intervals, and let $f: X \to Y$ and $g := f^{-1}: Y \to X$ be mutually inverse continuous bijections. Let $x_0 \in X$, and define $y_0 := f(x_0) \in Y$, so that $g(y_0) = x_0$. Assume that $f$ is differentiable at $x_0$ with non-vanishing derivative $f'(x_0) \neq 0$.

Because $f$ is differentiable at $x_0$, the limit of the difference quotient of $f$ exists as a finite non-zero value:
$$
\begin{gather}
\lim_{X \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \neq 0 \tag{1}
\end{gather}
$$

Let $y \in Y \setminus \{y_0\}$ be an arbitrary point distinct from $y_0$. Define the point $x \in X$ by:
$$
\begin{gather}
x := g(y) = f^{-1}(y) \tag{2}
\end{gather}
$$

Because $g$ is a bijective mapping, the condition $y \neq y_0$ guarantees that $x = g(y) \neq g(y_0) = x_0$. Furthermore, evaluating $f$ at $x$ yields $f(x) = f(g(y)) = y$ and $f(x_0) = y_0$. 

Forming the difference quotient of the inverse function $g$ at $y_0$ produces:
$$
\begin{gather}
\frac{g(y) - g(y_0)}{y - y_0} = \frac{x - x_0}{f(x) - f(x_0)} \tag{3}
\end{gather}
$$

Because $x \neq x_0$ and $f(x) \neq f(x_0)$, the algebraic identity for reciprocals permits rewriting step 3 as:
$$
\begin{gather}
\frac{g(y) - g(y_0)}{y - y_0} = \frac{1}{\dfrac{f(x) - f(x_0)}{x - x_0}} = \frac{1}{\dfrac{f(g(y)) - f(g(y_0))}{g(y) - g(y_0)}} \tag{4}
\end{gather}
$$

Because $g = f^{-1}$ is continuous at $y_0$, taking the limit as $y \to y_0$ through $Y \setminus \{y_0\}$ forces:
$$
\begin{gather}
\lim_{Y \ni y \to y_0} g(y) = g(y_0) = x_0 \tag{5}
\end{gather}
$$
with $g(y) \neq x_0$ for all $y \neq y_0$.

By the limit composition theorem for deleted neighborhoods, step 1 and step 5 guarantee that:
$$
\begin{gather}
\lim_{Y \ni y \to y_0} \frac{f(g(y)) - f(g(y_0))}{g(y) - g(y_0)} = \lim_{X \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{6}
\end{gather}
$$

Because $f'(x_0) \neq 0$, applying the reciprocal limit rule to step 4 in conjunction with step 6 yields:
$$
\begin{gather}
\lim_{Y \ni y \to y_0} \frac{g(y) - g(y_0)}{y - y_0} = \frac{1}{\lim\limits_{Y \ni y \to y_0} \dfrac{f(g(y)) - f(g(y_0))}{g(y) - g(y_0)}} = \frac{1}{f'(x_0)} \tag{7}
\end{gather}
$$

Because this limit exists as a finite real quantity, the inverse mapping $f^{-1}$ is differentiable at $y_0$, and its derivative satisfies:
$$
\begin{gather}
(f^{-1})'(y_0) = \frac{1}{f'(x_0)} = \frac{1}{f'(f^{-1}(y_0))} \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
