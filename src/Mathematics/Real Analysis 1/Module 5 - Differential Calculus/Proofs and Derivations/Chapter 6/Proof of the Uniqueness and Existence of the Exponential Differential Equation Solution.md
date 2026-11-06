---
dg-publish: true
---
Let $\alpha \in \mathbb{R}$ and $y_0 \in \mathbb{R}$. We consider the initial value problem:
$$
\begin{gather}
f'(x) = \alpha f(x) \quad \forall x \in \mathbb{R}, \quad f(0) = y_0 \tag{1}
\end{gather}
$$

### Part 1: Existence
Define the candidate function $\varphi(x) := y_0 e^{\alpha x}$. 

By the chain rule and the derivative of the exponential function (Chapter 2, Table 2.1):
$$
\begin{gather}
\varphi'(x) = y_0 \frac{d}{dx}\big( e^{\alpha x} \big) = y_0 (\alpha e^{\alpha x}) = \alpha (y_0 e^{\alpha x}) = \alpha \varphi(x) \tag{2}
\end{gather}
$$

Evaluating at $x = 0$:
$$
\begin{gather}
\varphi(0) = y_0 e^0 = y_0 \tag{3}
\end{gather}
$$
Thus, $\varphi(x) = y_0 e^{\alpha x}$ is an analytical solution to problem (1).

### Part 2: Uniqueness
Let $f: \mathbb{R} \to \mathbb{R}$ be an arbitrary differentiable function satisfying problem (1).

Consider the auxiliary function $g: \mathbb{R} \to \mathbb{R}$ defined by:
$$
\begin{gather}
g(x) := f(x) e^{-\alpha x} \tag{4}
\end{gather}
$$

Because both $f(x)$ and $e^{-\alpha x}$ are differentiable across all of $\mathbb{R}$, by Theorem 2.1 (The Leibniz Product Rule) and Theorem 2.3 (The Chain Rule), $g$ is differentiable on $\mathbb{R}$.

Computing the derivative $g'(x)$:
$$
\begin{gather}
g'(x) = f'(x) e^{-\alpha x} + f(x) \frac{d}{dx}\big( e^{-\alpha x} \big) = f'(x) e^{-\alpha x} - \alpha f(x) e^{-\alpha x} \tag{5}
\end{gather}
$$

Factoring out $e^{-\alpha x}$:
$$
\begin{gather}
g'(x) = \big( f'(x) - \alpha f(x) \big) e^{-\alpha x} \tag{6}
\end{gather}
$$

By hypothesis (1), $f'(x) - \alpha f(x) \equiv 0$ for all $x \in \mathbb{R}$. Therefore:
$$
\begin{gather}
g'(x) = 0 \cdot e^{-\alpha x} \equiv 0 \quad \forall x \in \mathbb{R} \tag{7}
\end{gather}
$$

By Theorem 3.5 (The Constancy Criterion, proven from Lagrange's Mean Value Theorem), a function whose derivative vanishes identically on the connected interval $\mathbb{R}$ is constant:
$$
\begin{gather}
g(x) \equiv C \quad \forall x \in \mathbb{R} \tag{8}
\end{gather}
$$

To determine the constant $C$, evaluate $g$ at $x = 0$:
$$
\begin{gather}
C = g(0) = f(0) e^0 = y_0 \cdot 1 = y_0 \tag{9}
\end{gather}
$$

Substituting $C = y_0$ into equation (8):
$$
\begin{gather}
f(x) e^{-\alpha x} = y_0 \implies f(x) = y_0 e^{\alpha x} \tag{10}
\end{gather}
$$

Equation (10) proves that $f(x)$ is identically equal to $y_0 e^{\alpha x}$, establishing uniqueness.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
