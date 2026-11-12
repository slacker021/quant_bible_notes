---
dg-publish: true
---
Let $I \subset \mathbb{R}$ be an interval, and let $f: I \to \mathbb{R}$ be a real-valued function. The Legendre transform (also known as the Legendre-Fenchel conjugate) $f^*$ is defined by:
$$
\begin{gather}
f^*(t) := \sup_{x \in I} \big(tx - f(x)\big) \tag{1}
\end{gather}
$$
on the effective dual domain:
$$
\begin{gather}
I^* := \{t \in \mathbb{R} \mid f^*(t) < +\infty\} \tag{2}
\end{gather}
$$

---
# Proposition 1
For each fixed point $x \in I$, the function $\psi_x(t) := tx - f(x)$ is an affine linear function of $t \in \mathbb{R}$.

Affine functions are trivially convex on $\mathbb{R}$. The Legendre transform $f^*(t)$ is defined in step 1 as the pointwise supremum of a family of affine functions $\{\psi_x\}_{x \in I}$.

Let $t_1, t_2 \in I^*$ and let $\lambda \in [0, 1]$. For every $x \in I$, the linearity of $\psi_x$ gives:
$$
\begin{gather}
\psi_x\big((1 - \lambda)t_1 + \lambda t_2\big) = (1 - \lambda)\psi_x(t_1) + \lambda \psi_x(t_2) \tag{3}
\end{gather}
$$
Because $\psi_x(t_1) \le f^*(t_1)$ and $\psi_x(t_2) \le f^*(t_2)$ for all $x \in I$, step 3 yields:
$$
\begin{gather}
\psi_x\big((1 - \lambda)t_1 + \lambda t_2\big) \le (1 - \lambda)f^*(t_1) + \lambda f^*(t_2) \tag{4}
\end{gather}
$$
Taking the supremum over all $x \in I$ on the left-hand side of step 4 preserves the upper bound:
$$
\begin{gather}
f^*\big((1 - \lambda)t_1 + \lambda t_2\big) = \sup_{x \in I} \psi_x\big((1 - \lambda)t_1 + \lambda t_2\big) \le (1 - \lambda)f^*(t_1) + \lambda f^*(t_2) \tag{5}
\end{gather}
$$
Because $t_1, t_2 \in I^*$, the right-hand side of step 5 is finite, which implies $(1 - \lambda)t_1 + \lambda t_2 \in I^*$. Thus, $I^*$ is an interval (or empty if the supremum diverges everywhere), and $f^*$ is convex on $I^*$.

---
# Proposition 2
Let $x \in I$ and $t \in I^*$. By the definition of the supremum in step 1:
$$
\begin{gather}
tx - f(x) \le \sup_{y \in I} \big(ty - f(y)\big) = f^*(t) \tag{6}
\end{gather}
$$
Adding $f(x)$ to both sides of step 6 immediately yields the Fenchel-Young inequality:
$$
\begin{gather}
xt \le f(x) + f^*(t) \tag{7}
\end{gather}
$$

---
# Proposition 3
Assume that $f$ is convex and continuous on $I$. The biconjugate $(f^*)^*$ is defined on $I$ by:
$$
\begin{gather}
(f^*)^*(x) := \sup_{t \in I^*} \big(xt - f^*(t)\big) \tag{8}
\end{gather}
$$

By virtue of the Fenchel-Young inequality in step 7, for any $x \in I$ and any $t \in I^*$:
$$
\begin{gather}
xt - f^*(t) \le f(x) \tag{9}
\end{gather}
$$
Taking the supremum over all $t \in I^*$ in step 9 yields:
$$
\begin{gather}
(f^*)^*(x) \le f(x), \quad \forall x \in I \tag{10}
\end{gather}
$$

To prove the reverse inequality $f(x) \le (f^*)^*(x)$, let $x_0 \in I$. By [[Proof of Supporting Tangent Characterization of Convexity|The Supporting Tangent Characterization of Convexity]] (or the existence of a subgradient for convex continuous functions), there exists a slope $s \in \mathbb{R}$ such that:
$$
\begin{gather}
f(x) \ge f(x_0) + s(x - x_0), \quad \forall x \in I \tag{11}
\end{gather}
$$
Rearranging step 11 yields:
$$
\begin{gather}
sx - f(x) \le sx_0 - f(x_0), \quad \forall x \in I \tag{12}
\end{gather}
$$
Taking the supremum over all $x \in I$ on the left-hand side shows that $s \in I^*$ and:
$$
\begin{gather}
f^*(s) = \sup_{x \in I} \big(sx - f(x)\big) \le sx_0 - f(x_0) \tag{13}
\end{gather}
$$
Rearranging step 13 gives:
$$
\begin{gather}
f(x_0) \le sx_0 - f^*(s) \tag{14}
\end{gather}
$$
Because $s \in I^*$, the right-hand side of step 14 is bounded above by the supremum over all $t \in I^*$:
$$
\begin{gather}
f(x_0) \le \sup_{t \in I^*} \big(tx_0 - f^*(t)\big) = (f^*)^*(x_0) \tag{15}
\end{gather}
$$
Combining step 10 and step 15 establishes that $(f^*)^*(x) = f(x)$ for all $x \in I$, proving that $(f^*)^* \equiv f$.

---
# Proposition 4
Suppose that $f$ is strictly convex and differentiable on the open interval $I = (a, b)$.

For any fixed parameter $t \in \mathbb{R}$, define the auxiliary function $\theta_t: I \to \mathbb{R}$ by:
$$
\begin{gather}
\theta_t(x) := tx - f(x) \tag{16}
\end{gather}
$$
Differentiating step 16 with respect to $x$ yields:
$$
\begin{gather}
\theta_t'(x) = t - f'(x) \tag{17}
\end{gather}
$$
Because $f$ is strictly convex, [[Proof of First-Order Monotonicity Characterization of Convexity|Proposition 2 of First-Order Monotonicity Characterization of Convexity]] guarantees that $f'$ is strictly increasing on $I$. 

Therefore, for any $t \in f'(I)$, the equation:
$$
\begin{gather}
\theta_t'(x) = 0 \iff t = f'(x) \tag{18}
\end{gather}
$$
possesses a unique solution, denoted by $x(t) \in I$.

Furthermore, evaluating the second derivative (or inspecting the derivative's sign) reveals:
$$
\begin{gather}
x < x(t) \implies f'(x) < t \implies \theta_t'(x) > 0 \tag{19}
\end{gather}
$$
$$
\begin{gather}
x > x(t) \implies f'(x) > t \implies \theta_t'(x) < 0 \tag{20}
\end{gather}
$$
By virtue of [[Proof of First-Derivative Sign-Alternation Criterion|First-Derivative Sign-Alternation Criterion]], $\theta_t$ is strictly increasing for $x < x(t)$ and strictly decreasing for $x > x(t)$. Thus, $x(t)$ is the unique strict global maximum of $\theta_t$ on $I$.

The supremum in step 1 is therefore achieved at the stationary point $x(t)$:
$$
\begin{gather}
f^*(t) = \sup_{x \in I} \big(tx - f(x)\big) = tx(t) - f(x(t)) \tag{21}
\end{gather}
$$
where $x(t)$ is the unique point in $I$ satisfying $t = f'(x)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
