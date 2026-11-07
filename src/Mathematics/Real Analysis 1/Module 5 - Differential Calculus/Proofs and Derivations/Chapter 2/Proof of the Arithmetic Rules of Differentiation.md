---
dg-publish: true
---
Let $f, g: E \to \mathbb{R}$ be defined on a neighborhood of $x_0 \in \text{int}(E)$, and suppose both $f$ and $g$ are differentiable at $x_0$. 

By the definition of differentiability at a point, the functional increments satisfy:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = f'(x_0) h + \alpha(h) h \tag{1} \\
g(x_0 + h) - g(x_0) = g'(x_0) h + \beta(h) h \tag{2}
\end{gather}
$$
where $\lim_{h \to 0} \alpha(h) = 0$ and $\lim_{h \to 0} \beta(h) = 0$.

### Part 1: Linearity
Let $c_1, c_2 \in \mathbb{R}$, and consider the linear combination $\Phi(x) := c_1 f(x) + c_2 g(x)$. The increment is:
$$
\begin{gather}
\Phi(x_0 + h) - \Phi(x_0) = c_1 \big( f(x_0 + h) - f(x_0) \big) + c_2 \big( g(x_0 + h) - g(x_0) \big) \tag{3}
\end{gather}
$$

Substituting equations (1) and (2) into equation (3):
$$
\begin{gather}
\Phi(x_0 + h) - \Phi(x_0) = c_1 \big( f'(x_0) h + \alpha(h) h \big) + c_2 \big( g'(x_0) h + \beta(h) h \big) \tag{4}
\end{gather}
$$

Regrouping terms:
$$
\begin{gather}
\Phi(x_0 + h) - \Phi(x_0) = \big( c_1 f'(x_0) + c_2 g'(x_0) \big) h + \big( c_1 \alpha(h) + c_2 \beta(h) \big) h \tag{5}
\end{gather}
$$

By limit algebra, $\lim_{h \to 0} (c_1 \alpha(h) + c_2 \beta(h)) = c_1 \cdot 0 + c_2 \cdot 0 = 0$. By the definition of differentiability at a point, $\Phi$ is differentiable at $x_0$, and:
$$
\begin{gather}
\Phi'(x_0) = c_1 f'(x_0) + c_2 g'(x_0) \tag{6}
\end{gather}
$$

### Part 2: Leibniz Product Rule
Consider the product function $\Pi(x) := f(x) g(x)$. The increment is:
$$
\begin{gather}
\Pi(x_0 + h) - \Pi(x_0) = f(x_0 + h) g(x_0 + h) - f(x_0) g(x_0) \tag{7}
\end{gather}
$$

Adding and subtracting the cross-term $f(x_0) g(x_0 + h)$:
$$
\begin{gather}
\Pi(x_0 + h) - \Pi(x_0) = \big( f(x_0 + h) - f(x_0) \big) g(x_0 + h) + f(x_0) \big( g(x_0 + h) - g(x_0) \big) \tag{8}
\end{gather}
$$

Dividing equation (8) by $h \neq 0$:
$$
\begin{gather}
\frac{\Pi(x_0 + h) - \Pi(x_0)}{h} = \left( \frac{f(x_0 + h) - f(x_0)}{h} \right) g(x_0 + h) + f(x_0) \left( \frac{g(x_0 + h) - g(x_0)}{h} \right) \tag{9}
\end{gather}
$$

Because $g$ is differentiable at $x_0$, by the Differentiability Implies Pointwise Continuity Theorem $g$ is continuous at $x_0$, which guarantees that $\lim_{h \to 0} g(x_0 + h) = g(x_0)$. 

Taking the limit as $h \to 0$ in equation (9):
$$
\begin{gather}
\lim_{h \to 0} \frac{\Pi(x_0 + h) - \Pi(x_0)}{h} = f'(x_0) g(x_0) + f(x_0) g'(x_0) \tag{10}
\end{gather}
$$
which proves the product rule.

### Part 3: Quotient Rule
Suppose $g(x_0) \neq 0$. By continuity of $g$ at $x_0$, there exists a neighborhood $U(x_0)$ on which $g(x) \neq 0$. Consider the reciprocal function $R(x) := \frac{1}{g(x)}$. Its increment is:
$$
\begin{gather}
R(x_0 + h) - R(x_0) = \frac{1}{g(x_0 + h)} - \frac{1}{g(x_0)} = -\frac{g(x_0 + h) - g(x_0)}{g(x_0 + h) g(x_0)} \tag{11}
\end{gather}
$$

Dividing equation (11) by $h \neq 0$:
$$
\begin{gather}
\frac{R(x_0 + h) - R(x_0)}{h} = -\frac{1}{g(x_0 + h) g(x_0)} \cdot \frac{g(x_0 + h) - g(x_0)}{h} \tag{12}
\end{gather}
$$

Taking the limit as $h \to 0$:
$$
\begin{gather}
\lim_{h \to 0} \frac{R(x_0 + h) - R(x_0)}{h} = -\frac{1}{(g(x_0))^2} \cdot g'(x_0) = -\frac{g'(x_0)}{(g(x_0))^2} \tag{13}
\end{gather}
$$

Applying the Leibniz product rule to $\frac{f}{g} = f \cdot \frac{1}{g}$:
$$
\begin{gather}
\left(\frac{f}{g}\right)'(x_0) = f'(x_0) \cdot \frac{1}{g(x_0)} + f(x_0) \left( -\frac{g'(x_0)}{(g(x_0))^2} \right) = \frac{f'(x_0)g(x_0) - f(x_0)g'(x_0)}{(g(x_0))^2} \tag{14}
\end{gather}
$$
Multiplying by the coordinate differential $dx$ immediately yields the corresponding differential statements.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
