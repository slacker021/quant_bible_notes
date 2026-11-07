---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be a continuous, strictly monotonic function defined on an interval $I \subseteq \mathbb{R}$. By the Continuous Inverse Function Theorem of Module 4 (Module 4), the direct image $J = f(I)$ is an interval, and the inverse mapping $f^{-1}: J \to I$ exists, is strictly monotonic, and is continuous on $J$.

Let $x_0 \in \text{int}(I)$ and $y_0 = f(x_0) \in \text{int}(J)$. Suppose $f$ is differentiable at $x_0$ with $f'(x_0) \neq 0$.

Let $y \in J \setminus \{y_0\}$. Set $x = f^{-1}(y)$. Because $f^{-1}$ is strictly monotonic, $y \neq y_0 \implies x \neq x_0$. 

Form the difference quotient for the inverse function:
$$
\begin{gather}
\frac{f^{-1}(y) - f^{-1}(y_0)}{y - y_0} = \frac{x - x_0}{f(x) - f(x_0)} = \frac{1}{\frac{f(x) - f(x_0)}{x - x_0}} \tag{1}
\end{gather}
$$

Because $f^{-1}$ is continuous at $y_0$:
$$
\begin{gather}
\lim_{y \to y_0} x = \lim_{y \to y_0} f^{-1}(y) = f^{-1}(y_0) = x_0 \tag{2}
\end{gather}
$$

Because $f$ is differentiable at $x_0$, as $x \to x_0$ the denominator in the equation of step 1 satisfies:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{3}
\end{gather}
$$

By hypothesis, $f'(x_0) \neq 0$. Applying the quotient limit theorem and the limit of a composite mapping (Module 3):
$$
\begin{gather}
\lim_{y \to y_0} \frac{f^{-1}(y) - f^{-1}(y_0)}{y - y_0} = \lim_{x \to x_0} \frac{1}{\frac{f(x) - f(x_0)}{x - x_0}} = \frac{1}{\lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}} = \frac{1}{f'(x_0)} \tag{4}
\end{gather}
$$

Because the limit in the equation of step 4 exists in $\mathbb{R}$, $f^{-1}$ is differentiable at $y_0$, with derivative:
$$
\begin{gather}
(f^{-1})'(y_0) = \frac{1}{f'(x_0)} = \frac{1}{f'(f^{-1}(y_0))} \tag{5}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
