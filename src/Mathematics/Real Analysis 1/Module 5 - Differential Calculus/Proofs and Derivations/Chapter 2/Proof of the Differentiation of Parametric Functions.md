---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an open interval, and let $\varphi, \psi: I \to \mathbb{R}$ be differentiable functions describing the parametric curve $t \mapsto (\varphi(t), \psi(t))$.

Let $t_0 \in I$ such that $\varphi'(t_0) \neq 0$.

### Step 1: Local Inversion of the Coordinate Function
Because $\varphi$ is differentiable at $t_0$, by the Differentiability Implies Pointwise Continuity Theorem $\varphi$ is continuous on a neighborhood $U(t_0)$. Without loss of generality, assume $\varphi'(t_0) > 0$. By the sign preservation property of derivatives (or continuity of $\varphi'$ if continuous, or strict local monotonicity via Module 4), there exists an open interval $U(t_0) \subseteq I$ on which $\varphi$ is strictly increasing.

By the Differentiation of the Inverse Function Theorem, the inverse function $t = \varphi^{-1}(x)$ exists on $V(x_0) = \varphi(U(t_0))$ where $x_0 = \varphi(t_0)$, and is differentiable at $x_0$ with derivative:
$$
\begin{gather}
(\varphi^{-1})'(x_0) = \frac{1}{\varphi'(t_0)} \tag{1}
\end{gather}
$$

### Step 2: Differentiating the Composite Function
The ordinate $y$ is expressed as a single-variable function of $x$ by:
$$
\begin{gather}
y(x) = (\psi \circ \varphi^{-1})(x) \tag{2}
\end{gather}
$$

Because $\varphi^{-1}$ is differentiable at $x_0$ and $\psi$ is differentiable at $t_0 = \varphi^{-1}(x_0)$, by the Invariant Chain Rule, the composite function $y(x)$ is differentiable at $x_0$. 

Computing the derivative:
$$
\begin{gather}
y'_x(x_0) = \psi'(\varphi^{-1}(x_0)) \cdot (\varphi^{-1})'(x_0) = \psi'(t_0) \cdot \frac{1}{\varphi'(t_0)} = \frac{\psi'(t_0)}{\varphi'(t_0)} \tag{3}
\end{gather}
$$

In kinematic notation where $\dot{x}(t) = \varphi'(t)$ and $\dot{y}(t) = \psi'(t)$:
$$
\begin{gather}
\frac{dy}{dx}(x_0) = \frac{\dot{y}(t_0)}{\dot{x}(t_0)} \tag{4}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
