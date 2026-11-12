---
dg-publish: true
---
Let $I, J \subseteq \mathbb{R}$ be non-degenerate intervals, and let $\varphi: J \to I$ be a mapping between them. 

---
# Proposition 1 
Suppose that:
1. $\varphi: J \to I$ is differentiable at every point of $J$.
2. The function $f: I \to \mathbb{R}$ possesses a primitive $F: I \to \mathbb{R}$ on $I$, so that $F'(u) = f(u)$ for all $u \in I$.

Consider the composite function $\Phi: J \to \mathbb{R}$ defined by:
$$
\begin{gather}
\Phi(t) := (F \circ \varphi)(t) = F(\varphi(t)), \quad \forall t \in J \tag{1}
\end{gather}
$$

Because $\varphi$ is differentiable on $J$ with values in $I$, and $F$ is differentiable on $I$, the [[Proof of The Chain Rule|Chain Rule of Differential Calculus]] implies that $\Phi$ is differentiable at every point $t \in J$.

Computing the derivative of $\Phi$ with respect to $t$ gives:
$$
\begin{gather}
\Phi'(t) = \frac{d}{dt}\big(F(\varphi(t))\big) = F'(\varphi(t)) \cdot \varphi'(t) \tag{2}
\end{gather}
$$

Substituting $F'(u) = f(u)$ evaluated at $u = \varphi(t)$ into step 2 yields:
$$
\begin{gather}
\Phi'(t) = f(\varphi(t)) \, \varphi'(t) \quad \forall t \in J \tag{3}
\end{gather}
$$

Step 3 demonstrates that the function $\Phi = F \circ \varphi$ is an antiderivative of the product mapping $(f \circ \varphi) \cdot \varphi'$ on $J$. In indefinite integral notation:
$$
\begin{gather}
\int f(\varphi(t)) \varphi'(t) \, dt = F(\varphi(t)) + C = \left[ \int f(u) \, du \right]_{u = \varphi(t)} \tag{4}
\end{gather}
$$
where $C \in \mathbb{R}$ is an arbitrary additive constant.

---
# Proposition 2
Suppose that:
1. $\varphi: J \to I$ is a bijection that is continuously differentiable on an open interval $J$, with non-vanishing derivative:
$$
\begin{gather}
\varphi'(t) \neq 0 \quad \forall t \in J \tag{5}
\end{gather}
$$
2. By [[Proof of Darboux's Intermediate-Value Theorem for Derivatives|Darboux's Theorem]] and the continuity of $\varphi'$, the condition $\varphi'(t) \neq 0$ implies that $\varphi'(t)$ maintains a strict, constant sign on $J$. Hence $\varphi$ is strictly monotonic, and its inverse mapping $\psi := \varphi^{-1}: I \to J$ is continuously differentiable on $I$, with:
$$
\begin{gather}
\psi'(x) = (\varphi^{-1})'(x) = \frac{1}{\varphi'(\varphi^{-1}(x))} \neq 0 \quad \forall x \in I \tag{6}
\end{gather}
$$
3. The transformed mapping $g: J \to \mathbb{R}$ defined by $g(t) := f(\varphi(t)) \varphi'(t)$ possesses a known primitive $G: J \to \mathbb{R}$ on $J$, satisfying:
$$
\begin{gather}
G'(t) = f(\varphi(t)) \varphi'(t) \quad \forall t \in J \tag{7}
\end{gather}
$$

Define the candidate primitive function $H: I \to \mathbb{R}$ by:
$$
\begin{gather}
H(x) := (G \circ \psi)(x) = G(\varphi^{-1}(x)), \quad \forall x \in I \tag{8}
\end{gather}
$$

Since $\psi$ is differentiable on $I$ and $G$ is differentiable on $J$, the chain rule applies to $H$ at each point $x \in I$:
$$
\begin{gather}
H'(x) = \frac{d}{dx}\big(G(\psi(x))\big) = G'(\psi(x)) \cdot \psi'(x) \tag{9}
\end{gather}
$$

Evaluating $G'$ from step 7 at $t = \psi(x) = \varphi^{-1}(x)$ gives:
$$
\begin{gather}
G'(\psi(x)) = f\big(\varphi(\psi(x))\big) \cdot \varphi'(\psi(x)) = f(x) \cdot \varphi'(\psi(x)) \tag{10}
\end{gather}
$$
because $\varphi(\psi(x)) = x$ for all $x \in I$.

Substituting step 10 and the inverse derivative identity of step 6 into step 9 yields:
$$
\begin{gather}
H'(x) = \big[ f(x) \cdot \varphi'(\psi(x)) \big] \cdot \left[ \frac{1}{\varphi'(\psi(x))} \right] \tag{11}
\end{gather}
$$

Because $\varphi'(t) \neq 0$ everywhere on $J$, the factor $\varphi'(\psi(x))$ cancels identically:
$$
\begin{gather}
H'(x) = f(x) \quad \forall x \in I \tag{12}
\end{gather}
$$

Step 12 proves that $H = G \circ \varphi^{-1}$ is an antiderivative of the original function $f$ on the interval $I$. Expressed in the traditional substitution form:
$$
\begin{gather}
\int f(x) \, dx = \left[ \int f(\varphi(t)) \varphi'(t) \, dt \right]_{t = \varphi^{-1}(x)} \tag{13}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
