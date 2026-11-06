---
dg-publish: true
---
Let $f \in C^2([x_0 - \delta, x_0 + \delta])$ and let $M_2 := \sup_{t \in [x_0 - \delta, x_0 + \delta]} |f''(t)|$.

Let $x \in [x_0 - \delta, x_0 + \delta]$ with $x \neq x_0$. Define the linearization error function:
$$
\begin{gather}
E(x) := f(x) - L(x) = f(x) - \big( f(x_0) + f'(x_0)(x - x_0) \big) \tag{1}
\end{gather}
$$

Define an auxiliary function $g: [x_0, x] \to \mathbb{R}$ (assuming $x > x_0$ without loss of generality) by:
$$
\begin{gather}
g(t) := f(x) - \big( f(t) + f'(t)(x - t) \big) - K(x - t)^2 \tag{2}
\end{gather}
$$
where the constant $K \in \mathbb{R}$ is chosen such that $g(x_0) = 0$:
$$
\begin{gather}
K := \frac{f(x) - f(x_0) - f'(x_0)(x - x_0)}{(x - x_0)^2} = \frac{E(x)}{(x - x_0)^2} \tag{3}
\end{gather}
$$

Evaluating $g$ at the endpoint $t = x$:
$$
\begin{gather}
g(x) = f(x) - \big( f(x) + f'(x)(0) \big) - K(0)^2 = 0 \tag{4}
\end{gather}
$$

Because $f \in C^2$, $g$ is continuous on $[x_0, x]$ and differentiable on $(x_0, x)$, with $g(x_0) = g(x) = 0$. By Rolle's Theorem (Theorem 3.2 of Chapter 3, proven from the Weierstrass Extreme Value Theorem), there exists an intermediate point $\xi \in (x_0, x)$ such that:
$$
\begin{gather}
g'(\xi) = 0 \tag{5}
\end{gather}
$$

Differentiating $g(t)$ with respect to $t$ using the product rule:
$$
\begin{gather}
g'(t) = -\left( f'(t) + f''(t)(x - t) - f'(t) \right) + 2K(x - t) = -f''(t)(x - t) + 2K(x - t) \tag{6}
\end{gather}
$$

Evaluating equation (6) at $t = \xi$:
$$
\begin{gather}
g'(\xi) = (x - \xi) \big( 2K - f''(\xi) \big) = 0 \tag{7}
\end{gather}
$$

Because $\xi \in (x_0, x)$, $x - \xi \neq 0$. Therefore:
$$
\begin{gather}
2K - f''(\xi) = 0 \implies K = \frac{f''(\xi)}{2} \tag{8}
\end{gather}
$$

Substituting equation (8) into equation (3):
$$
\begin{gather}
E(x) = \frac{f''(\xi)}{2} (x - x_0)^2 \tag{9}
\end{gather}
$$

Taking absolute values on both sides of equation (9):
$$
\begin{gather}
|f(x) - L(x)| = |E(x)| = \frac{|f''(\xi)|}{2} (x - x_0)^2 \le \frac{M_2}{2} (x - x_0)^2 \tag{10}
\end{gather}
$$
Because this bound holds identically for $x < x_0$ by an identical argument on $[x, x_0]$, and holds trivially for $x = x_0$ where both sides vanish, the proof is complete.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
