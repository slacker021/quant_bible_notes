---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be a real-valued function defined on the closed interval $[a, b]$ with $a < b$, satisfying the hypotheses:
1. The function $f$ is continuous on the compact interval $[a, b]$;
2. The function $f$ is differentiable on the open interior interval $(a, b)$.

Define the auxiliary secant-deviation function $F: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
F(x) := f(x) - f(a) - \frac{f(b) - f(a)}{b - a}(x - a), \quad \forall x \in [a, b] \tag{1}
\end{gather}
$$

The properties of $F$ on $[a, b]$ are verified as follows:
- **Continuity:** The mapping $x \mapsto f(x)$ is continuous on $[a, b]$ by hypothesis 1. The affine term $x \mapsto x - a$ is continuous everywhere on $\mathbb{R}$. By the algebraic field properties of continuous functions established in [[Chapter 1 - Continuity of Functions|Module 4, Chapter 1]], the linear combination $F$ is continuous on $[a, b]$.
- **Differentiability:** By hypothesis 2, $f$ is differentiable on $(a, b)$. The affine function $x \mapsto \frac{f(b) - f(a)}{b - a}(x - a)$ has a constant derivative on $\mathbb{R}$. By the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]], $F$ is differentiable on $(a, b)$, and its derivative is given by:
$$
\begin{gather}
F'(x) = f'(x) - \frac{f(b) - f(a)}{b - a}, \quad \forall x \in (a, b) \tag{2}
\end{gather}
$$
- **Boundary Values:** Evaluating $F$ at the left endpoint $x = a$:
$$
\begin{gather}
F(a) = f(a) - f(a) - \frac{f(b) - f(a)}{b - a}(a - a) = 0 - 0 = 0 \tag{3}
\end{gather}
$$
Evaluating $F$ at the right endpoint $x = b$:
$$
\begin{gather}
F(b) = f(b) - f(a) - \frac{f(b) - f(a)}{b - a}(b - a) = (f(b) - f(a)) - (f(b) - f(a)) = 0 \tag{4}
\end{gather}
$$
From step 3 and step 4, $F(a) = F(b) = 0$.

The auxiliary function $F$ satisfies all three hypotheses of [[Proof of Rolle's Theorem|Rolle's Mean Value Theorem]] on $[a, b]$. Consequently, there exists at least one intermediate point $\xi \in (a, b)$ such that:
$$
\begin{gather}
F'(\xi) = 0 \tag{5}
\end{gather}
$$

Substituting the derivative formula of step 2 into step 5 yields:
$$
\begin{gather}
f'(\xi) - \frac{f(b) - f(a)}{b - a} = 0 \tag{6}
\end{gather}
$$

Multiplying step 6 by the non-zero interval width $(b - a)$ produces:
$$
\begin{gather}
f(b) - f(a) = f'(\xi)(b - a) \tag{7}
\end{gather}
$$
where $\xi \in (a, b)$.

Setting $h := b - a > 0$ and parametrizing $\xi$ as $\xi = a + \theta h$ with $\theta := \frac{\xi - a}{b - a}$, the condition $\xi \in (a, b)$ is equivalent to $\theta \in (0, 1)$, yielding the finite-increment identity:
$$
\begin{gather}
\Delta f(a; h) = f'(a + \theta h) h, \quad \theta \in (0, 1) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$