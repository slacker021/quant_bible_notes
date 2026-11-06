---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $x_0 \in \text{int}(E)$, and let $f: E \to \mathbb{R}$.

### Direct Implication
Suppose $f$ is differentiable at $x_0$. By Theorem 1.1, the derivative $f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}$ exists in $\mathbb{R}$.

Define the auxiliary function $\psi: E \to \mathbb{R}$ by:
$$
\begin{gather}
\psi(x) := \begin{cases} \frac{f(x) - f(x_0)}{x - x_0}, & x \in E \setminus \{x_0\} \\[2mm] f'(x_0), & x = x_0 \end{cases} \tag{1}
\end{gather}
$$

For every $x \in E \setminus \{x_0\}$, multiplying equation (1) by $(x - x_0)$ yields:
$$
\begin{gather}
f(x) - f(x_0) = \psi(x)(x - x_0) \tag{2}
\end{gather}
$$

For $x = x_0$, equation (2) reduces to $0 = \psi(x_0) \cdot 0 = 0$, which holds identically. 

Furthermore, evaluating the limit of $\psi(x)$ as $x \to x_0$:
$$
\begin{gather}
\lim_{x \to x_0} \psi(x) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) = \psi(x_0) \tag{3}
\end{gather}
$$

Equation (3) proves that $\psi$ is continuous at the point $x_0$.

### Converse Implication
Suppose there exists a function $\psi: E \to \mathbb{R}$ that is continuous at $x_0$ and satisfies:
$$
\begin{gather}
f(x) - f(x_0) = \psi(x)(x - x_0) \quad \forall x \in E \tag{4}
\end{gather}
$$

For any $x \in E \setminus \{x_0\}$, dividing equation (4) by $(x - x_0)$ yields:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} = \psi(x) \tag{5}
\end{gather}
$$

Because $\psi$ is continuous at $x_0$, taking the limit as $x \to x_0$ on both sides of equation (5) yields:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{x \to x_0} \psi(x) = \psi(x_0) \tag{6}
\end{gather}
$$

Because the limit exists and equals the finite real number $\psi(x_0)$, by Theorem 1.1 the function $f$ is differentiable at $x_0$, with derivative $f'(x_0) = \psi(x_0)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
