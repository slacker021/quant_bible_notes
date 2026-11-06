---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be continuous on $[a, b]$ and differentiable on $(a, b)$.

### Step 1: Construction of the Auxiliary Shearing Function
Consider the straight line connecting the boundary points $(a, f(a))$ and $(b, f(b))$. The secant line is given by:
$$
\begin{gather}
y = L(x) := f(a) + \frac{f(b) - f(a)}{b - a}(x - a) \tag{1}
\end{gather}
$$

Define the auxiliary vertical difference function $F: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
F(x) := f(x) - L(x) = f(x) - f(a) - \frac{f(b) - f(a)}{b - a}(x - a) \tag{2}
\end{gather}
$$

### Step 2: Verification of Rolle's Hypotheses
1. **Continuity on $[a, b]$**: Because $f$ is continuous on $[a, b]$ and $L(x)$ is a polynomial (affine function), their difference $F$ is continuous on $[a, b]$.
2. **Differentiability on $(a, b)$**: Because $f$ and $L$ are differentiable on $(a, b)$, by linearity $F$ is differentiable on $(a, b)$, with derivative:
$$
\begin{gather}
F'(x) = f'(x) - \frac{f(b) - f(a)}{b - a} \tag{3}
\end{gather}
$$
3. **Boundary Value Equality**: Evaluating $F$ at the endpoints:
$$
\begin{gather}
F(a) = f(a) - f(a) - \frac{f(b) - f(a)}{b - a}(0) = 0 \tag{4} \\
F(b) = f(b) - f(a) - \frac{f(b) - f(a)}{b - a}(b - a) = f(b) - f(a) - (f(b) - f(a)) = 0 \tag{5}
\end{gather}
$$
Thus, $F(a) = F(b) = 0$.

### Step 3: Application of Rolle's Theorem
The auxiliary function $F$ satisfies all hypotheses of Theorem 3.3 (Rolle's Theorem). Consequently, there exists an intermediate point $\xi \in (a, b)$ such that:
$$
\begin{gather}
F'(\xi) = 0 \tag{6}
\end{gather}
$$

Substituting equation (3) into equation (6):
$$
\begin{gather}
f'(\xi) - \frac{f(b) - f(a)}{b - a} = 0 \implies f(b) - f(a) = f'(\xi)(b - a) \tag{7}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
