---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $x_0 \in E \cap E'$.

**Necessity ($\implies$ Differentiability implies Existence of Continuous Auxiliary Function):**
Assume that $f$ is differentiable at the point $x_0$. 

By the [[Proof of the Equivalence of Differentiability and Derivative Existence|Equivalence of Differentiability and Derivative Existence]], the derivative $f'(x_0) \in \mathbb{R}$ exists as the finite limit of the difference quotient:
$$
\begin{gather}
f'(x_0) = \lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \tag{1}
\end{gather}
$$

Define the auxiliary function $\psi: E \to \mathbb{R}$ by the formula:
$$
\begin{gather}
\psi(x) := \begin{cases} \dfrac{f(x) - f(x_0)}{x - x_0} & \text{if } x \in E \setminus \{x_0\} \\[3mm] f'(x_0) & \text{if } x = x_0 \end{cases} \tag{2}
\end{gather}
$$

To verify the algebraic factorization, consider two complementary cases for an arbitrary point $x \in E$:
1. If $x \neq x_0$, multiplying both sides of the upper branch of step 2 by the non-zero quantity $(x - x_0)$ yields:
$$
\begin{gather}
f(x) - f(x_0) = \psi(x)(x - x_0) \tag{3}
\end{gather}
$$
2. If $x = x_0$, evaluating both sides yields $f(x_0) - f(x_0) = 0$ on the left and $\psi(x_0)(x_0 - x_0) = f'(x_0) \cdot 0 = 0$ on the right. 

Thus, the factorization $f(x) - f(x_0) = \psi(x)(x - x_0)$ holds identically for all $x \in E$.

To verify the continuity of $\psi$ at $x_0$, evaluate its limit as $x \to x_0$ through the domain $E$. For every $x \in E \setminus \{x_0\}$, step 2 gives $\psi(x) = \frac{f(x) - f(x_0)}{x - x_0}$. Taking the limit and applying step 1 yields:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \psi(x) = \lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{4}
\end{gather}
$$
By step 2, $\psi(x_0) = f'(x_0)$. Combining this equality with step 4 gives:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \psi(x) = \psi(x_0) \tag{5}
\end{gather}
$$
Because the limit of $\psi(x)$ at $x_0$ along $E$ coincides with its functional value, $\psi$ is continuous at $x_0$.

**Sufficiency ($\impliedby$ Existence of Continuous Auxiliary Function implies Differentiability):**
Conversely, suppose there exists a function $\psi: E \to \mathbb{R}$ that is continuous at $x_0$ and satisfies the factorization:
$$
\begin{gather}
f(x) - f(x_0) = \psi(x)(x - x_0) \tag{6}
\end{gather}
$$
for all $x \in E$.

For any point $x \in E \setminus \{x_0\}$, the displacement $x - x_0$ is non-zero. Dividing step 6 by $x - x_0$ isolates the difference quotient:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} = \psi(x) \tag{7}
\end{gather}
$$

Because $x_0$ is an accumulation point of $E$, one can evaluate the limit of both sides of step 7 as $x \to x_0$ through $E$. Since $\psi$ is continuous at $x_0$, the limit of the right-hand side exists and evaluates to $\psi(x_0)$:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{E \ni x \to x_0} \psi(x) = \psi(x_0) \tag{8}
\end{gather}
$$

Because $\psi(x_0)$ is a finite real number, step 8 demonstrates that the derivative of $f$ at $x_0$ exists and is given by:
$$
\begin{gather}
f'(x_0) = \psi(x_0) \tag{9}
\end{gather}
$$
By the Equivalence of Differentiability and Derivative Existence, the existence of the finite limit in step 8 implies that $f$ is differentiable at $x_0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$