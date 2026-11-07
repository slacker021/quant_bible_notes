---
dg-publish: true
---
Let $f, g: [a, b] \to \mathbb{R}$ be continuous on $[a, b]$ and differentiable on $(a, b)$, and suppose $g'(x) \neq 0$ for all $x \in (a, b)$.

### Step 1: Non-Vanishing of the Denominator Increment
Suppose for contradiction that $g(b) = g(a)$. 

Because $g$ is continuous on $[a, b]$ and differentiable on $(a, b)$, by Rolle's Theorem there would exist a point $\xi_0 \in (a, b)$ such that:
$$
\begin{gather}
g'(\xi_0) = 0 \tag{1}
\end{gather}
$$
The equation of step 1 directly contradicts the hypothesis that $g'(x) \neq 0$ for all $x \in (a, b)$. Therefore:
$$
\begin{gather}
g(b) \neq g(a) \implies g(b) - g(a) \neq 0 \tag{2}
\end{gather}
$$

### Step 2: Construction of the Auxiliary Function
Define the auxiliary function $\Phi: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
\Phi(x) := f(x) - f(a) - \frac{f(b) - f(a)}{g(b) - g(a)} \big( g(x) - g(a) \big) \tag{3}
\end{gather}
$$

### Step 3: Verification of Rolle's Hypotheses
1. **Continuity and Differentiability**: Because $f$ and $g$ are continuous on $[a, b]$ and differentiable on $(a, b)$, $\Phi$ is continuous on $[a, b]$ and differentiable on $(a, b)$, with derivative:
$$
\begin{gather}
\Phi'(x) = f'(x) - \frac{f(b) - f(a)}{g(b) - g(a)} g'(x) \tag{4}
\end{gather}
$$
2. **Boundary Equality**: Evaluating $\Phi$ at the endpoints:
$$
\begin{gather}
\Phi(a) = f(a) - f(a) - \frac{f(b) - f(a)}{g(b) - g(a)}(g(a) - g(a)) = 0 \tag{5} \\
\Phi(b) = f(b) - f(a) - \frac{f(b) - f(a)}{g(b) - g(a)}(g(b) - g(a)) = f(b) - f(a) - (f(b) - f(a)) = 0 \tag{6}
\end{gather}
$$
Thus $\Phi(a) = \Phi(b) = 0$.

### Step 4: Application of Rolle's Theorem
By Rolle's Theorem, there exists an intermediate point $\xi \in (a, b)$ such that:
$$
\begin{gather}
\Phi'(\xi) = 0 \tag{7}
\end{gather}
$$

Substituting the equation of step 4 into the equation of step 7:
$$
\begin{gather}
f'(\xi) - \frac{f(b) - f(a)}{g(b) - g(a)} g'(\xi) = 0 \tag{8}
\end{gather}
$$

Because $g'(\xi) \neq 0$, dividing the equation of step 8 by $g'(\xi)$ yields:
$$
\begin{gather}
\frac{f(b) - f(a)}{g(b) - g(a)} = \frac{f'(\xi)}{g'(\xi)} \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
