---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be differentiable on an open interval $I \subseteq \mathbb{R}$.

### (1) $\iff$ (2): Chord Convexity and Secant Slopes
Let $x_1 < x < x_2$ in $I$. Any intermediate point $x$ can be represented as:
$$
\begin{gather}
x = \alpha_1 x_1 + \alpha_2 x_2, \quad \text{where } \alpha_1 = \frac{x_2 - x}{x_2 - x_1} > 0, \quad \alpha_2 = \frac{x - x_1}{x_2 - x_1} > 0 \tag{1}
\end{gather}
$$

By Definition 4.1, chord convexity holds if and only if:
$$
\begin{gather}
f(x) \le \frac{x_2 - x}{x_2 - x_1} f(x_1) + \frac{x - x_1}{x_2 - x_1} f(x_2) \tag{2}
\end{gather}
$$

Multiplying inequality (2) by $(x_2 - x_1) > 0$ and rearranging terms:
$$
\begin{gather}
(x_2 - x_1) f(x) \le (x_2 - x) f(x_1) + (x - x_1) f(x_2) \tag{3}
\end{gather}
$$

Writing $(x_2 - x_1) = (x_2 - x) + (x - x_1)$ on the left-hand side:
$$
\begin{gather}
(x_2 - x)\big( f(x) - f(x_1) \big) \le (x - x_1)\big( f(x_2) - f(x) \big) \tag{4}
\end{gather}
$$

Dividing inequality (4) by $(x - x_1)(x_2 - x) > 0$ gives:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{5}
\end{gather}
$$
which is the exact assertion that the secant slope function is monotonically non-decreasing.

### (2) $\implies$ (3): Supporting Tangent Lines
From inequality (5), for any $x_1 < x_0 < x_2$:
$$
\begin{gather}
\frac{f(x_1) - f(x_0)}{x_1 - x_0} \le \frac{f(x_2) - f(x_0)}{x_2 - x_0} \tag{6}
\end{gather}
$$

Taking the limit as $x_1 \to x_0^-$:
$$
\begin{gather}
f'(x_0) \le \frac{f(x_2) - f(x_0)}{x_2 - x_0} \implies f(x_2) \ge f(x_0) + f'(x_0)(x_2 - x_0) \tag{7}
\end{gather}
$$

Taking the limit as $x_2 \to x_0^+$:
$$
\begin{gather}
\frac{f(x_1) - f(x_0)}{x_1 - x_0} \le f'(x_0) \implies f(x_1) - f(x_0) \ge f'(x_0)(x_1 - x_0) \tag{8}
\end{gather}
$$
Inequalities (7) and (8) prove that $f(x) \ge f(x_0) + f'(x_0)(x - x_0)$ for all $x \in I$.

### (3) $\implies$ (4): Monotonicity of the Derivative
Let $x_1, x_2 \in I$ with $x_1 < x_2$. Applying the supporting tangent inequality at $x_1$ and $x_2$:
$$
\begin{gather}
f(x_2) \ge f(x_1) + f'(x_1)(x_2 - x_1) \tag{9} \\
f(x_1) \ge f(x_2) + f'(x_2)(x_1 - x_2) = f(x_2) - f'(x_2)(x_2 - x_1) \tag{10}
\end{gather}
$$

Adding inequalities (9) and (10):
$$
\begin{gather}
f(x_1) + f(x_2) \ge f(x_1) + f(x_2) + \big( f'(x_1) - f'(x_2) \big)(x_2 - x_1) \tag{11}
\end{gather}
$$

Subtracting $f(x_1) + f(x_2)$ yields:
$$
\begin{gather}
0 \ge \big( f'(x_1) - f'(x_2) \big)(x_2 - x_1) \implies \big( f'(x_2) - f'(x_1) \big)(x_2 - x_1) \ge 0 \tag{12}
\end{gather}
$$
Because $x_2 - x_1 > 0$, inequality (12) forces $f'(x_2) \ge f'(x_1)$, proving that $f'$ is monotonically non-decreasing.

### (4) $\implies$ (5): Second Derivative Non-Negativity
If $f \in C^2(I)$, the second derivative is the limit of difference quotients of $f'$:
$$
\begin{gather}
f''(x) = \lim_{h \to 0^+} \frac{f'(x + h) - f'(x)}{h} \tag{13}
\end{gather}
$$
Because $f'$ is non-decreasing, $f'(x + h) \ge f'(x)$, so $f''(x) \ge 0$.

### (5) $\implies$ (1): Second Derivative Implies Chord Convexity
Let $f''(x) \ge 0$. By Theorem 3.5 (Monotonicity Criterion), $f'$ is non-decreasing. 
Let $x_1 < x_2$ and $x = \alpha_1 x_1 + \alpha_2 x_2 \in (x_1, x_2)$. 
By Lagrange's Mean Value Theorem (Theorem 3.4):
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} = f'(\xi_1) \quad \text{for } \xi_1 \in (x_1, x) \tag{14} \\
\frac{f(x_2) - f(x)}{x_2 - x} = f'(\xi_2) \quad \text{for } \xi_2 \in (x, x_2) \tag{15}
\end{gather}
$$
Because $\xi_1 < x < \xi_2$ and $f'$ is non-decreasing, $f'(\xi_1) \le f'(\xi_2)$. Therefore:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{16}
\end{gather}
$$
By the equivalence of (1) and (2), this establishes chord convexity.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
