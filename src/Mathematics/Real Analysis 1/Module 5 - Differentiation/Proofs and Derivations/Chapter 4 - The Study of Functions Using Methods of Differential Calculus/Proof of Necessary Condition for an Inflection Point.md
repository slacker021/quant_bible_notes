---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a function. Suppose that the point $(x_0, f(x_0))$ is an inflection point of the graph of $f$, and suppose that the second derivative $f''(x_0)$ exists as a finite real number.

Because $(x_0, f(x_0))$ is an inflection point, there exists a punctured neighborhood:
$$
\begin{gather}
\mathring{U}_\delta(x_0) := (x_0 - \delta, x_0) \cup (x_0, x_0 + \delta) \subset (a, b) \tag{1}
\end{gather}
$$
such that $f$ is strictly convex on one side of $x_0$ and strictly concave on the other side of $x_0$.

Without loss of generality, assume that $f$ is strictly convex on the left subinterval $(x_0 - \delta, x_0)$ and strictly concave on the right subinterval $(x_0, x_0 + \delta)$. (The reverse configuration follows identical lines by considering $-f$).

Because $f''(x_0)$ exists, the first derivative $f'$ exists on an open neighborhood containing $x_0$. 

By virtue of [[Proof of First-Order Monotonicity Characterization of Convexity|The First-Order Monotonicity Characterization of Convexity]]:
1. On $(x_0 - \delta, x_0)$, strict convexity of $f$ implies that the derivative $f'$ is strictly increasing.
2. On $(x_0, x_0 + \delta)$, strict concavity of $f$ implies that the derivative $f'$ is strictly decreasing.

Because $f$ is differentiable at $x_0$, the one-sided derivatives satisfy the transition inequalities. For any $x_1 \in (x_0 - \delta, x_0)$ and $x_2 \in (x_0, x_0 + \delta)$, the monotonicity properties yield:
$$
\begin{gather}
f'(x_1) < f'(x_0) \quad \text{and} \quad f'(x_2) < f'(x_0) \tag{2}
\end{gather}
$$
Step 2 establishes that $f'$ possesses an interior local maximum at the point $x_0$.

Because the second derivative $f''(x_0)$ exists, it is the derivative of the function $f'$ at the point $x_0$:
$$
\begin{gather}
f''(x_0) = (f')'(x_0) = \lim_{x \to x_0} \frac{f'(x) - f'(x_0)}{x - x_0} \tag{3}
\end{gather}
$$

Because $x_0$ is an interior local extremum (specifically, a local maximum) of the differentiable function $f'$, [[Proof of Fermat's Interior Extremum Lemma|Fermat's Interior Extremum Lemma]] applies directly to $f'$ at $x_0$. 

Consequently, the derivative of $f'$ at $x_0$ must vanish identically:
$$
\begin{gather}
(f')'(x_0) = 0 \iff f''(x_0) = 0 \tag{4}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
