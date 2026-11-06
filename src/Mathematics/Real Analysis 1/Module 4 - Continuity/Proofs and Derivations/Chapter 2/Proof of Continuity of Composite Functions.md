---
dg-publish: true
---
Let $X, Y \subseteq \mathbb{R}$, let $f: X \to Y$, let $g: Y \to \mathbb{R}$, and let $a \in X$. 

Suppose that $f$ is continuous at $a$, and that $g$ is continuous at the image point $b = f(a) \in Y$. 

Let an arbitrary error tolerance $\varepsilon > 0$ be given. 

Because $g: Y \to \mathbb{R}$ is continuous at $b \in Y$, there exists a corresponding distance $\eta > 0$ such that for all $y \in Y$:
$$
\begin{gather}
|y - b| < \eta \implies |g(y) - g(b)| < \varepsilon \tag{1}
\end{gather}
$$

Now consider the strictly positive value $\eta > 0$ as an error tolerance for the mapping $f$. 

Because $f: X \to Y$ is continuous at $a \in X$, there exists a distance $\delta > 0$ such that for all $x \in X$:
$$
\begin{gather}
|x - a| < \delta \implies |f(x) - f(a)| < \eta \tag{2}
\end{gather}
$$

Let $x \in X$ satisfy the condition:
$$
\begin{gather}
|x - a| < \delta \tag{3}
\end{gather}
$$

Applying step 2 to step 3 guarantees that:
$$
\begin{gather}
|f(x) - f(a)| = |f(x) - b| < \eta \tag{4}
\end{gather}
$$

Because $f(x) \in Y$, setting $y = f(x)$ allows for the application of step 1 to the bound in step 4:
$$
\begin{gather}
|g(f(x)) - g(b)| = |(g \circ f)(x) - (g \circ f)(a)| < \varepsilon \tag{5}
\end{gather}
$$

Consequently, for every $\varepsilon > 0$, there exists $\delta > 0$ such that for all $x \in X$, $|x - a| < \delta$ guarantees $|(g \circ f)(x) - (g \circ f)(a)| < \varepsilon$. 

This establishes that $(g \circ f)$ is continuous at $a$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
