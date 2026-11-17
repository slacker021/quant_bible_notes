---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f, g \in \mathcal{R}[a, b]$.

By the Necessity of Boundedness for Riemann Integrability ([[Proof of the Necessity of Boundedness for Riemann Integrability]]), every Riemann integrable function on a compact interval is bounded. Therefore, there exist positive real constants $M_f > 0$ and $M_g > 0$ such that:
$$
\begin{gather}
\sup_{x \in [a, b]} |f(x)| \le M_f \tag{1}
\end{gather}
$$
and
$$
\begin{gather}
\sup_{x \in [a, b]} |g(x)| \le M_g \tag{2}
\end{gather}
$$

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), the sum $(f + g)$ and difference $(f - g)$ are Riemann integrable on $[a, b]$:
$$
\begin{gather}
(f + g) \in \mathcal{R}[a, b], \qquad (f - g) \in \mathcal{R}[a, b] \tag{3}
\end{gather}
$$

Applying the triangle inequality for real numbers to step 1 and step 2, for all $x \in [a, b]$:
$$
\begin{gather}
|(f + g)(x)| \le |f(x)| + |g(x)| \le M_f + M_g \tag{4}
\end{gather}
$$
and
$$
\begin{gather}
|(f - g)(x)| \le |f(x)| + |g(x)| \le M_f + M_g \tag{5}
\end{gather}
$$

Define the uniform bound $M := M_f + M_g > 0$. By step 4 and step 5, the ranges of $(f + g)$ and $(f - g)$ are both subsets of the compact interval $[-M, M] \subset \mathbb{R}$:
$$
\begin{gather}
(f + g)([a, b]) \subseteq [-M, M], \qquad (f - g)([a, b]) \subseteq [-M, M] \tag{6}
\end{gather}
$$

Define the real squaring function $\phi: [-M, M] \to \mathbb{R}$ by:
$$
\begin{gather}
\phi(t) := t^2 \tag{7}
\end{gather}
$$

Because polynomials are continuous on all of $\mathbb{R}$, $\phi$ is continuous on the compact interval $[-M, M]$. 

By the Continuous Composition Integrability Theorem ([[Proof of the Continuous Composition Integrability Theorem]]), if a function $u \in \mathcal{R}[a, b]$ has its range contained in a compact interval $J$, and $\phi: J \to \mathbb{R}$ is continuous on $J$, then the composite function $(\phi \circ u)$ belongs to $\mathcal{R}[a, b]$.

Applying this theorem to $u = f + g \in \mathcal{R}[a, b]$ with range in $[-M, M]$:
$$
\begin{gather}
(f + g)^2 = \phi \circ (f + g) \in \mathcal{R}[a, b] \tag{8}
\end{gather}
$$

Similarly, applying the theorem to $u = f - g \in \mathcal{R}[a, b]$ with range in $[-M, M]$:
$$
\begin{gather}
(f - g)^2 = \phi \circ (f - g) \in \mathcal{R}[a, b] \tag{9}
\end{gather}
$$

For any real numbers $u, v \in \mathbb{R}$, expanding $(u + v)^2$ and $(u - v)^2$ yields:
$$
\begin{gather}
(u + v)^2 - (u - v)^2 = (u^2 + 2uv + v^2) - (u^2 - 2uv + v^2) = 4uv \tag{10}
\end{gather}
$$

Dividing step 10 by 4 establishes the algebraic polarization identity:
$$
\begin{gather}
uv = \frac{1}{4}(u + v)^2 - \frac{1}{4}(u - v)^2 \tag{11}
\end{gather}
$$

Setting $u = f(x)$ and $v = g(x)$ in step 11 for each $x \in [a, b]$ gives the pointwise functional decomposition:
$$
\begin{gather}
(fg)(x) = f(x)g(x) = \frac{1}{4} \big( f(x) + g(x) \big)^2 - \frac{1}{4} \big( f(x) - g(x) \big)^2 \tag{12}
\end{gather}
$$

By step 8 and step 9, both $(f + g)^2$ and $(f - g)^2$ belong to $\mathcal{R}[a, b]$.

By the Linearity of the Riemann Integral ([[Proof of the Linearity of the Riemann Integral]]), any real linear combination of functions in $\mathcal{R}[a, b]$ belongs to $\mathcal{R}[a, b]$. Specifically, setting $\alpha = \frac{1}{4}$ and $\beta = -\frac{1}{4}$ yields:
$$
\begin{gather}
\frac{1}{4}(f + g)^2 - \frac{1}{4}(f - g)^2 \in \mathcal{R}[a, b] \tag{13}
\end{gather}
$$

By the identity of step 12 and the membership of step 13:
$$
\begin{gather}
fg \in \mathcal{R}[a, b] \tag{14}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
