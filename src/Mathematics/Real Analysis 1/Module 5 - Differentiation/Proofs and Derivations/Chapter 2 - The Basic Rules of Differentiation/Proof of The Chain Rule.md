---
dg-publish: true
---
Let $X, Y \subseteq \mathbb{R}$, let $f: X \to Y$ and $g: Y \to \mathbb{R}$ be functions, and let $x_0 \in X \cap X'$ be an accumulation point of $X$. Define $y_0 := f(x_0) \in Y \cap Y'$. Assume that $f$ is differentiable at $x_0$ and $g$ is differentiable at $y_0$.

By the [[Proof of The Carathéodory Differentiability Criterion|Carathéodory Differentiability Criterion]], the differentiability of $f$ at $x_0$ is equivalent to the existence of an auxiliary function $\phi: X \to \mathbb{R}$ that is continuous at $x_0$ and satisfies:
$$
\begin{gather}
f(x) - f(x_0) = \phi(x)(x - x_0), \quad \forall x \in X \tag{1}
\end{gather}
$$
with anchor value:
$$
\begin{gather}
\phi(x_0) = f'(x_0) \tag{2}
\end{gather}
$$

Similarly, the differentiability of $g$ at $y_0$ guarantees the existence of an auxiliary function $\psi: Y \to \mathbb{R}$ that is continuous at $y_0$ and satisfies:
$$
\begin{gather}
g(y) - g(y_0) = \psi(y)(y - y_0), \quad \forall y \in Y \tag{3}
\end{gather}
$$
with anchor value:
$$
\begin{gather}
\psi(y_0) = g'(y_0) = g'(f(x_0)) \tag{4}
\end{gather}
$$

For any point $x \in X$, setting $y := f(x) \in Y$ in step 3 yields:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = g(f(x)) - g(f(x_0)) = \psi(f(x))\big(f(x) - f(x_0)\big) \tag{5}
\end{gather}
$$

Substituting the factorization of $f(x) - f(x_0)$ from step 1 into step 5 produces:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = \psi(f(x)) \cdot \phi(x)(x - x_0) \tag{6}
\end{gather}
$$

Define the composite auxiliary factor $\Theta: X \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
\Theta(x) := \psi(f(x)) \cdot \phi(x) = (\psi \circ f)(x) \cdot \phi(x), \quad \forall x \in X \tag{7}
\end{gather}
$$

Step 6 can then be expressed as:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = \Theta(x)(x - x_0), \quad \forall x \in X \tag{8}
\end{gather}
$$

To verify the continuity of $\Theta$ at $x_0$, note that because $f$ is differentiable at $x_0$, the theorem establishing that [[Proof that Differentiability Implies Continuity|differentiability implies continuity]] confirms that $f$ is continuous at $x_0$. 

Because $f$ is continuous at $x_0$ and $\psi$ is continuous at $y_0 = f(x_0)$, the composite mapping $(\psi \circ f): X \to \mathbb{R}$ is continuous at $x_0$ by the [[Proof of Continuity of Composite Functions|continuity of composite functions]]. 

Because $\phi$ is continuous at $x_0$ by step 1, the product $\Theta = (\psi \circ f) \cdot \phi$ is continuous at $x_0$ as the product of two continuous functions:
$$
\begin{gather}
\lim_{X \ni x \to x_0} \Theta(x) = \left(\lim_{X \ni x \to x_0} \psi(f(x))\right) \cdot \left(\lim_{X \ni x \to x_0} \phi(x)\right) = \psi(f(x_0)) \cdot \phi(x_0) = \Theta(x_0) \tag{9}
\end{gather}
$$

Evaluating the anchor value $\Theta(x_0)$ using step 2 and step 4 yields:
$$
\begin{gather}
\Theta(x_0) = \psi(f(x_0)) \cdot \phi(x_0) = \psi(y_0) \cdot \phi(x_0) = g'(f(x_0)) \cdot f'(x_0) \tag{10}
\end{gather}
$$

By virtue of the sufficiency direction of the [[Proof of The Carathéodory Differentiability Criterion|Carathéodory Differentiability Criterion]], the existence of the factor $\Theta(x)$ continuous at $x_0$ satisfying step 8 proves that the composite function $(g \circ f)$ is differentiable at $x_0$, and its derivative is given by:
$$
\begin{gather}
(g \circ f)'(x_0) = \Theta(x_0) = g'(f(x_0)) \cdot f'(x_0) \tag{11}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
