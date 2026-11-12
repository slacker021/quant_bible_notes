---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $x_0 \in E \cap E'$ be an accumulation point of $E$, and let $f: E \to \mathbb{R}$ be a real-valued mapping.

**Necessity ($\implies$ Differentiability Implies the Existence of a Continuous Auxiliary Factor):**
Assume that $f$ is differentiable at the point $x_0$. 

By the definition of the derivative, the limit of the difference quotient as $x$ approaches $x_0$ through $E \setminus \{x_0\}$ exists and defines the finite derivative value $f'(x_0) \in \mathbb{R}$:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{1}
\end{gather}
$$

Define the auxiliary function $\phi: E \to \mathbb{R}$ piecewise by:
$$
\begin{gather}
\phi(x) := \begin{cases} \dfrac{f(x) - f(x_0)}{x - x_0} & \text{if } x \in E \setminus \{x_0\} \\[3mm] f'(x_0) & \text{if } x = x_0 \end{cases} \tag{2}
\end{gather}
$$

To verify that the factorization identity $f(x) - f(x_0) = \phi(x)(x - x_0)$ holds throughout $E$, consider two exhaustive cases:
1. If $x \in E \setminus \{x_0\}$, multiplying both sides of the upper branch of step 2 by $(x - x_0) \neq 0$ yields:
$$
\begin{gather}
f(x) - f(x_0) = \phi(x)(x - x_0) \tag{3}
\end{gather}
$$
2. If $x = x_0$, evaluating the left-hand side yields $f(x_0) - f(x_0) = 0$, while the right-hand side produces $\phi(x_0)(x_0 - x_0) = f'(x_0) \cdot 0 = 0$.

Thus, the factorization $f(x) - f(x_0) = \phi(x)(x - x_0)$ holds identically for every $x \in E$.

To prove that $\phi$ is continuous at $x_0$, evaluate its limit as $x \to x_0$ through the domain $E$. For all points $x \in E \setminus \{x_0\}$, step 2 gives $\phi(x) = \frac{f(x) - f(x_0)}{x - x_0}$. Taking the limit and invoking step 1 gives:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \phi(x) = \lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{4}
\end{gather}
$$

Because $\phi(x_0) = f'(x_0)$ by definition in step 2, combining this value with step 4 yields:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \phi(x) = \phi(x_0) \tag{5}
\end{gather}
$$
demonstrating that $\phi$ is continuous at $x_0$.

**Sufficiency ($\impliedby$ Existence of a Continuous Auxiliary Factor Implies Differentiability):**
Conversely, assume that there exists an auxiliary function $\phi: E \to \mathbb{R}$ that is continuous at $x_0$ and satisfies:
$$
\begin{gather}
f(x) - f(x_0) = \phi(x)(x - x_0), \quad \forall x \in E \tag{6}
\end{gather}
$$

For any displacement point $x \in E \setminus \{x_0\}$, dividing step 6 by the non-zero quantity $(x - x_0)$ produces:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} = \phi(x) \tag{7}
\end{gather}
$$

Because $\phi$ is continuous at $x_0$, its limit as $x \to x_0$ through $E \setminus \{x_0\}$ exists and equals $\phi(x_0)$:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \phi(x) = \phi(x_0) \tag{8}
\end{gather}
$$

Taking the limit of both sides of step 7 as $x \to x_0$ and substituting step 8 gives:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{E \ni x \to x_0} \phi(x) = \phi(x_0) \tag{9}
\end{gather}
$$

Because the limit of the difference quotient exists as a finite real quantity, $f$ is differentiable at $x_0$, with derivative given by:
$$
\begin{gather}
f'(x_0) = \phi(x_0) \tag{10}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
