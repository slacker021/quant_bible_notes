---
dg-publish: true
---
Let $-\infty \le a < b \le \infty$. Let $f, g: (a, b) \to \mathbb{R}$ be differentiable with $g'(x) \neq 0$ on $(a, b)$, and suppose:
$$
\begin{gather}
\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = L \in [-\infty, \infty] \tag{1}
\end{gather}
$$

### Part 1: The Indeterminate Form $0/0$
Suppose $\lim_{x \to a^+} f(x) = 0$ and $\lim_{x \to a^+} g(x) = 0$.

Extend $f$ and $g$ continuously to the left endpoint $a$ by defining $f(a) := 0$ and $g(a) := 0$. 

For any $x \in (a, b)$, the extended functions are continuous on $[a, x]$ and differentiable on $(a, x)$. By Cauchy's Generalized Mean Value Theorem, there exists an intermediate point $\xi_x \in (a, x)$ such that:
$$
\begin{gather}
\frac{f(x)}{g(x)} = \frac{f(x) - f(a)}{g(x) - g(a)} = \frac{f'(\xi_x)}{g'(\xi_x)} \tag{2}
\end{gather}
$$

As $x \to a^+$, the squeeze theorem forces $\xi_x \to a^+$. 

By hypothesis (1):
$$
\begin{gather}
\lim_{x \to a^+} \frac{f(x)}{g(x)} = \lim_{x \to a^+} \frac{f'(\xi_x)}{g'(\xi_x)} = \lim_{\xi \to a^+} \frac{f'(\xi)}{g'(\xi)} = L \tag{3}
\end{gather}
$$

### Part 2: The Indeterminate Form $\infty/\infty$
Suppose $\lim_{x \to a^+} |g(x)| = \infty$.

Assume first that $L \in \mathbb{R}$ is finite. Let $\varepsilon > 0$. By hypothesis (1), there exists $c \in (a, b)$ such that for all $t \in (a, c)$:
$$
\begin{gather}
L - \frac{\varepsilon}{2} < \frac{f'(t)}{g'(t)} < L + \frac{\varepsilon}{2} \tag{4}
\end{gather}
$$

Fix $x \in (a, c)$ and $y \in (x, c)$. Applying Cauchy's Mean Value Theorem on $[x, y]$:
$$
\begin{gather}
\frac{f(x) - f(y)}{g(x) - g(y)} = \frac{f'(\xi)}{g'(\xi)} \quad \text{for some } \xi \in (x, y) \subset (a, c) \tag{5}
\end{gather}
$$

By inequality (4):
$$
\begin{gather}
L - \frac{\varepsilon}{2} < \frac{f(x) - f(y)}{g(x) - g(y)} < L + \frac{\varepsilon}{2} \tag{6}
\end{gather}
$$

Algebraically decompose the ratio $\frac{f(x)}{g(x)}$:
$$
\begin{gather}
\frac{f(x)}{g(x)} = \frac{f(x) - f(y)}{g(x)} + \frac{f(y)}{g(x)} = \frac{f(x) - f(y)}{g(x) - g(y)} \left( 1 - \frac{g(y)}{g(x)} \right) + \frac{f(y)}{g(x)} \tag{7}
\end{gather}
$$

Keeping $y$ fixed, take the limit as $x \to a^+$. Because $\lim_{x \to a^+} |g(x)| = \infty$:
$$
\begin{gather}
\lim_{x \to a^+} \frac{g(y)}{g(x)} = 0 \quad \text{and} \quad \lim_{x \to a^+} \frac{f(y)}{g(x)} = 0 \tag{8}
\end{gather}
$$

Combining equations (6), (7), and (8), for sufficiently small $x - a$:
$$
\begin{gather}
L - \varepsilon < \frac{f(x)}{g(x)} < L + \varepsilon \tag{9}
\end{gather}
$$
Because $\varepsilon > 0$ was arbitrary, $\lim_{x \to a^+} \frac{f(x)}{g(x)} = L$.

(The cases $L = \pm \infty$ follow similarly by bounding the ratio below or above).
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
