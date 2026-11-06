---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be a strictly convex, differentiable function on an open interval $I \subseteq \mathbb{R}$.

Its Legendre-Fenchel transform is defined by:
$$
\begin{gather}
f^*(p) := \sup_{x \in I} \big( px - f(x) \big) \tag{1}
\end{gather}
$$

### Step 1: Characterization of the Supremum
Fix $p \in \mathbb{R}$ in the range of $f'$. Define the auxiliary function $\varphi_p(x) := px - f(x)$.

Differentiating with respect to $x$:
$$
\begin{gather}
\varphi_p'(x) = p - f'(x) \tag{2}
\end{gather}
$$

Stationary points satisfy $\varphi_p'(x) = 0 \iff f'(x) = p$.

Because $f$ is strictly convex, by Theorem 4.3 its derivative $f'$ is strictly increasing on $I$. Therefore, the equation $f'(x) = p$ has at most one solution:
$$
\begin{gather}
x(p) = (f')^{-1}(p) \tag{3}
\end{gather}
$$

Evaluating the second derivative:
$$
\begin{gather}
\varphi_p''(x) = -f''(x) < 0 \tag{4}
\end{gather}
$$
which proves that $x(p)$ is a strict global maximum of $\varphi_p$ on $I$. 

Substituting $x(p)$ into the definition of $f^*(p)$:
$$
\begin{gather}
f^*(p) = p \cdot x(p) - f(x(p)) = p \cdot (f')^{-1}(p) - f\big((f')^{-1}(p)\big) \tag{5}
\end{gather}
$$

### Step 2: Young-Fenchel Duality Inequality
By definition of the supremum, for every $x \in I$ and every $p \in \text{dom}(f^*)$:
$$
\begin{gather}
px - f(x) \le \sup_{t \in I}(pt - f(t)) = f^*(p) \tag{6}
\end{gather}
$$

Rearranging terms:
$$
\begin{gather}
px \le f(x) + f^*(p) \tag{7}
\end{gather}
$$
Equality holds if and only if $x = (f')^{-1}(p) \iff p = f'(x)$.

### Step 3: Involution $(f^*)^* = f$
Define the second conjugate $(f^*)^*(x) := \sup_{p \in \text{dom}(f^*)} (xp - f^*(p))$.

From the Young-Fenchel inequality (7), $xp - f^*(p) \le f(x)$ for all $p$. Taking the supremum over $p$:
$$
\begin{gather}
(f^*)^*(x) = \sup_p \big( xp - f^*(p) \big) \le f(x) \tag{8}
\end{gather}
$$

Now choose the specific slope $p_0 := f'(x)$. By Step 1, equality holds in equation (7) at $p_0$:
$$
\begin{gather}
x p_0 - f^*(p_0) = f(x) \tag{9}
\end{gather}
$$

Because the supremum is at least as large as the value at $p_0$:
$$
\begin{gather}
(f^*)^*(x) \ge x p_0 - f^*(p_0) = f(x) \tag{10}
\end{gather}
$$

Combining inequalities (8) and (10):
$$
\begin{gather}
(f^*)^*(x) = f(x) \quad \forall x \in I \tag{11}
\end{gather}
$$
proving the involution property $(f^*)^* = f$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
