---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ have continuous derivatives up to order $n$ on a closed interval with endpoints $x_0$ and $x$, and suppose that the $(n + 1)$-th derivative $f^{(n+1)}$ exists on the open interior between $x_0$ and $x$.

By virtue of [[Proof of Taylor's Formula with General Remainder|Taylor's Formula with General Remainder]], for any auxiliary function $\phi$ continuous on the closed interval and differentiable on its interior with $\phi'(t) \neq 0$, the $n$-th order Taylor remainder admits the representation:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!} \frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} f^{(n+1)}(\xi) (x - \xi)^n \tag{1}
\end{gather}
$$
for some intermediate point $\xi$ lying strictly between $x_0$ and $x$.

Define the linear auxiliary scaling function $\phi$ by:
$$
\begin{gather}
\phi(t) := x - t \tag{2}
\end{gather}
$$

The mapping $\phi$ satisfies the required regularity conditions:
1. Being a polynomial of degree 1, $\phi(t)$ is continuous on the closed interval between $x_0$ and $x$;
2. The derivative is constant and non-zero:
$$
\begin{gather}
\phi'(t) = -1 \neq 0, \quad \forall t \tag{3}
\end{gather}
$$

Evaluating the functional increment of $\phi$ across the interval endpoints:
$$
\begin{gather}
\phi(x) - \phi(x_0) = (x - x) - (x - x_0) = -(x - x_0) \tag{4}
\end{gather}
$$

Computing the ratio of increments appearing in step 1 using step 3 and step 4:
$$
\begin{gather}
\frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} = \frac{-(x - x_0)}{-1} = x - x_0 \tag{5}
\end{gather}
$$

Substituting step 5 into step 1 yields Cauchy's form of the Taylor remainder:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!} f^{(n+1)}(\xi) (x - \xi)^n (x - x_0) \tag{6}
\end{gather}
$$
where $\xi$ lies strictly between $x_0$ and $x$.

To express step 6 in the standard dimensionless parametric form, define the parameter:
$$
\begin{gather}
\theta := \frac{\xi - x_0}{x - x_0} \tag{7}
\end{gather}
$$
Because $\xi$ lies strictly between $x_0$ and $x$, the parameter satisfies $\theta \in (0, 1)$, and $\xi$ is given by:
$$
\begin{gather}
\xi = x_0 + \theta(x - x_0) \tag{8}
\end{gather}
$$

Computing the difference $(x - \xi)$ in terms of $\theta$:
$$
\begin{gather}
x - \xi = x - \big(x_0 + \theta(x - x_0)\big) = (x - x_0) - \theta(x - x_0) = (1 - \theta)(x - x_0) \tag{9}
\end{gather}
$$
Raising step 9 to the $n$-th power:
$$
\begin{gather}
(x - \xi)^n = (1 - \theta)^n (x - x_0)^n \tag{10}
\end{gather}
$$

Multiplying step 10 by $(x - x_0)$ yields:
$$
\begin{gather}
(x - \xi)^n (x - x_0) = (1 - \theta)^n (x - x_0)^{n+1} \tag{11}
\end{gather}
$$

Substituting step 8 and step 11 into step 6 produces the parametric Cauchy remainder:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{n!} (1 - \theta)^n (x - x_0)^{n+1} \tag{12}
\end{gather}
$$
where $\theta \in (0, 1)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$