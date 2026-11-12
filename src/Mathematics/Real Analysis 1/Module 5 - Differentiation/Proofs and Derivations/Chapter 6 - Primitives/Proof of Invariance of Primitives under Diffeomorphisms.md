---
dg-publish: true
---
Let $I, J \subseteq \mathbb{R}$ be open intervals, and let $\varphi: J \to I$ be a $C^1$-diffeomorphism between them. By definition of a 1-dimensional $C^1$-diffeomorphism:
1. $\varphi: J \to I$ is a bijection.
2. $\varphi$ is continuously differentiable on $J$, meaning $\varphi' \in C(J)$.
3. The derivative is nowhere zero on $J$:
$$
\begin{gather}
\varphi'(t) \neq 0 \quad \forall t \in J \tag{1}
\end{gather}
$$
4. The inverse mapping $\psi := \varphi^{-1}: I \to J$ is continuously differentiable on $I$, with its derivative given by the inverse function theorem as:
$$
\begin{gather}
\psi'(x) = (\varphi^{-1})'(x) = \frac{1}{\varphi'(\varphi^{-1}(x))} \neq 0 \quad \forall x \in I \tag{2}
\end{gather}
$$

Let $f: I \to \mathbb{R}$ be a function admitting a primitive $F: I \to \mathbb{R}$ on $I$, so that:
$$
\begin{gather}
F'(x) = f(x) \quad \forall x \in I \tag{3}
\end{gather}
$$

---
# Proposition 1 
Define the pullback composition $\Phi: J \to \mathbb{R}$ by:
$$
\begin{gather}
\Phi(t) := (F \circ \varphi)(t) = F(\varphi(t)), \quad \forall t \in J \tag{4}
\end{gather}
$$

Because $\varphi$ is differentiable at each $t \in J$ with image $\varphi(t) \in I$, and $F$ is differentiable at each point of $I$, the composite function $\Phi$ is differentiable at every $t \in J$ by the [[Proof of the Chain Rule for Differentiable Functions|Chain Rule of Differential Calculus]]. 

Evaluating the derivative of $\Phi$ with respect to $t$ yields:
$$
\begin{gather}
\Phi'(t) = \frac{d}{dt}\big(F(\varphi(t))\big) = F'(\varphi(t)) \cdot \varphi'(t) \tag{5}
\end{gather}
$$

Substituting the primitive identity $F' = f$ from step 3 into step 5 gives:
$$
\begin{gather}
\Phi'(t) = f(\varphi(t)) \, \varphi'(t) = \big((f \circ \varphi) \cdot \varphi'\big)(t) \quad \forall t \in J \tag{6}
\end{gather}
$$

Step 6 demonstrates that $\Phi = F \circ \varphi$ is, by definition, an antiderivative of the differential form pullback mapping $(f \circ \varphi) \cdot \varphi'$ on the interval $J$. In the classical notation of indefinite integrals:
$$
\begin{gather}
\int f(\varphi(t)) \varphi'(t) \, dt = F(\varphi(t)) + C \tag{7}
\end{gather}
$$

---
# Proposition 2
Conversely, suppose that $G: J \to \mathbb{R}$ is a primitive of the transformed integrand $(f \circ \varphi) \cdot \varphi'$ on $J$:
$$
\begin{gather}
G'(t) = f(\varphi(t)) \, \varphi'(t) \quad \forall t \in J \tag{8}
\end{gather}
$$

Define the pushforward function $\Psi: I \to \mathbb{R}$ by pre-composing $G$ with the inverse diffeomorphism $\psi = \varphi^{-1}$:
$$
\begin{gather}
\Psi(x) := (G \circ \psi)(x) = G(\varphi^{-1}(x)), \quad \forall x \in I \tag{9}
\end{gather}
$$

Because $\psi$ is differentiable on $I$ and $G$ is differentiable on $J$, the chain rule applies to $\Psi$ at every point $x \in I$:
$$
\begin{gather}
\Psi'(x) = \frac{d}{dx}\big(G(\psi(x))\big) = G'(\psi(x)) \cdot \psi'(x) \tag{10}
\end{gather}
$$

Substituting step 8 evaluated at $t = \psi(x)$ gives:
$$
\begin{gather}
G'(\psi(x)) = f\big(\varphi(\psi(x))\big) \cdot \varphi'(\psi(x)) = f(x) \cdot \varphi'(\psi(x)) \tag{11}
\end{gather}
$$
because $\varphi(\psi(x)) = \varphi(\varphi^{-1}(x)) = x$.

Now substitute step 11 and the inverse derivative formula of step 2 into step 10:
$$
\begin{gather}
\Psi'(x) = \big[ f(x) \cdot \varphi'(\psi(x)) \big] \cdot \left[ \frac{1}{\varphi'(\psi(x))} \right] \tag{12}
\end{gather}
$$

Because $\varphi'(t) \neq 0$ everywhere on $J$, the factor $\varphi'(\psi(x))$ cancels identically:
$$
\begin{gather}
\Psi'(x) = f(x) \quad \forall x \in I \tag{13}
\end{gather}
$$

Step 13 proves that $\Psi = G \circ \varphi^{-1}$ is an antiderivative of $f$ on $I$. 

Furthermore, the pullback mapping $\varphi^*$ induces a bijective linear isometry between the one-dimensional affine spaces of primitives:
$$
\begin{gather}
\varphi^*: \int f(x) \, dx \longrightarrow \int f(\varphi(t))\varphi'(t) \, dt, \quad F \mapsto F \circ \varphi \tag{14}
\end{gather}
$$
If $F_1 - F_2 = C \in \mathbb{R}$, then:
$$
\begin{gather}
(F_1 \circ \varphi)(t) - (F_2 \circ \varphi)(t) = (F_1 - F_2)(\varphi(t)) = C \quad \forall t \in J \tag{15}
\end{gather}
$$
The affine structure and foliation by additive constants is preserved under smooth coordinate transformations.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
