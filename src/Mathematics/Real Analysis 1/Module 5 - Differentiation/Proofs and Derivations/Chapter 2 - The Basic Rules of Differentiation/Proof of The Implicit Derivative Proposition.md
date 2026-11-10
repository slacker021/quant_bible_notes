---
dg-publish: true
---
Let $U(t_0) \subseteq \mathbb{R}$ be an open neighborhood of a parameter point $t_0 \in \mathbb{R}$, and let $x: U(t_0) \to \mathbb{R}$ and $y: U(t_0) \to \mathbb{R}$ be functions that are differentiable at $t_0$. Define the anchor coordinates $x_0 := x(t_0)$ and $y_0 := y(t_0)$. Assume that the derivative of $x$ does not vanish at $t_0$:
$$
\begin{gather}
x'(t_0) \neq 0 \tag{1}
\end{gather}
$$

By virtue of the [[Proof of The Derivative of an Inverse Function|Derivative of an Inverse Function Theorem]], because $x$ is differentiable at $t_0$ with non-zero derivative $x'(t_0) \neq 0$, there exists an open subinterval $U_0 \subseteq U(t_0)$ containing $t_0$ and an open neighborhood $V(x_0) \subseteq \mathbb{R}$ containing $x_0$ such that the restriction $x: U_0 \to V(x_0)$ is a continuous bijection possessing a continuous inverse mapping $t: V(x_0) \to U_0$. 

The inverse mapping satisfies $t(x_0) = t_0$, is differentiable at $x_0$, and its derivative is given by:
$$
\begin{gather}
t'(x_0) = \frac{1}{x'(t(x_0))} = \frac{1}{x'(t_0)} \tag{2}
\end{gather}
$$

Define the composite single-variable function $y(x): V(x_0) \to \mathbb{R}$ by:
$$
\begin{gather}
y(x) := (y \circ t)(x) = y(t(x)), \quad \forall x \in V(x_0) \tag{3}
\end{gather}
$$

Because $t: V(x_0) \to U_0$ is differentiable at $x_0$ and $y: U_0 \to \mathbb{R}$ is differentiable at the image point $t_0 = t(x_0)$, the [[Proof of The Chain Rule|Chain Rule]] applies directly to the composite mapping $(y \circ t)$ at $x_0$. 

Applying the Chain Rule yields:
$$
\begin{gather}
y'_x(x_0) = \frac{d}{dx}\big[y(t(x))\big]_{x=x_0} = y'_t(t(x_0)) \cdot t'(x_0) = y'_t(t_0) \cdot t'(x_0) \tag{4}
\end{gather}
$$

Substituting the value of the inverse derivative $t'(x_0)$ from step 2 into step 4 produces:
$$
\begin{gather}
y'_x(x_0) = y'_t(t_0) \cdot \left(\frac{1}{x'(t_0)}\right) = \frac{y'_t(t_0)}{x'_t(t_0)} \tag{5}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
