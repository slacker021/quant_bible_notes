---
dg-publish: true
---
Let $X, Y \subseteq \mathbb{R}$, let $x_0 \in \text{int}(X)$, let $f: X \to Y$, and let $g: Y \to \mathbb{R}$. Let $y_0 = f(x_0) \in \text{int}(Y)$.

Suppose $f$ is differentiable at $x_0$, and $g$ is differentiable at $y_0$.

# Step 1: Application of Carathéodory's Theorem
By Carathéodory’s Criterion for Differentiability, differentiability of $f$ at $x_0$ guarantees the existence of a function $\psi_f: X \to \mathbb{R}$ continuous at $x_0$ such that:
$$
\begin{gather}
f(x) - f(x_0) = \psi_f(x)(x - x_0) \quad \forall x \in X, \quad \text{with } \psi_f(x_0) = f'(x_0) \tag{1}
\end{gather}
$$

Similarly, differentiability of $g$ at $y_0$ guarantees the existence of a function $\psi_g: Y \to \mathbb{R}$ continuous at $y_0$ such that:
$$
\begin{gather}
g(y) - g(y_0) = \psi_g(y)(y - y_0) \quad \forall y \in Y, \quad \text{with } \psi_g(y_0) = g'(y_0) \tag{2}
\end{gather}
$$

# Step 2: Evaluation on the Composite Mapping
For any $x \in X$, let $y = f(x)$ and $y_0 = f(x_0)$. Substituting $y$ and $y_0$ into the equation of step 2:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = g(f(x)) - g(f(x_0)) = \psi_g(f(x)) \big( f(x) - f(x_0) \big) \tag{3}
\end{gather}
$$

Substituting the equation of step 1 into the equation of step 3:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = \psi_g(f(x)) \cdot \psi_f(x)(x - x_0) \tag{4}
\end{gather}
$$

Define the composite slope function $\Psi: X \to \mathbb{R}$ by:
$$
\begin{gather}
\Psi(x) := \psi_g(f(x)) \cdot \psi_f(x) \tag{5}
\end{gather}
$$

The equation of step 4 becomes:
$$
\begin{gather}
(g \circ f)(x) - (g \circ f)(x_0) = \Psi(x)(x - x_0) \quad \forall x \in X \tag{6}
\end{gather}
$$

# Step 3: Continuity of the Composite Slope
Because $f$ is differentiable at $x_0$, by the Differentiability Implies Pointwise Continuity Theorem $f$ is continuous at $x_0$. 
Because $\psi_g$ is continuous at $y_0 = f(x_0)$, by the Continuity of Composite Mappings Theorem (Module 4), the composition $x \mapsto \psi_g(f(x))$ is continuous at $x_0$.

Because $\psi_f$ is also continuous at $x_0$, the product $\Psi(x) = \psi_g(f(x)) \cdot \psi_f(x)$ is continuous at $x_0$ by the product theorem for continuous functions.

Evaluating $\Psi$ at $x_0$:
$$
\begin{gather}
\Psi(x_0) = \psi_g(f(x_0)) \cdot \psi_f(x_0) = \psi_g(y_0) \cdot \psi_f(x_0) = g'(f(x_0)) \cdot f'(x_0) \tag{7}
\end{gather}
$$

By Carathéodory’s Criterion for Differentiability, the equation of step 6 and the continuity of $\Psi$ at $x_0$ rigorously prove that $(g \circ f)$ is differentiable at $x_0$, with derivative:
$$
\begin{gather}
(g \circ f)'(x_0) = \Psi(x_0) = g'(f(x_0)) \cdot f'(x_0) \tag{8}
\end{gather}
$$

# Step 4: Invariance of Differential Operator Composition
The differential of the composition acts on displacement $h$ as:
$$
\begin{gather}
d(g \circ f)(x_0)(h) = \big( g'(f(x_0)) \cdot f'(x_0) \big) h = g'(f(x_0)) \cdot \big( f'(x_0) h \big) \tag{9}
\end{gather}
$$

Because $df(x_0)(h) = f'(x_0) h$ and $dg(y_0)(k) = g'(y_0) k$, the equation of step 9 is precisely the composition of linear maps:
$$
\begin{gather}
d(g \circ f)(x_0) = dg(y_0) \circ df(x_0) \tag{10}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
