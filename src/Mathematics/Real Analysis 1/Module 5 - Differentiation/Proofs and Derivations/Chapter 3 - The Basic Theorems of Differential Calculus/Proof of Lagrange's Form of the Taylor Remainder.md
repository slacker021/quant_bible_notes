---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ have continuous derivatives up to order $n$ on a closed interval with endpoints $x_0$ and $x$, and suppose that the $(n + 1)$-th derivative $f^{(n+1)}$ exists on the open interior between $x_0$ and $x$.

By virtue of [[Proof of Taylor's Formula with General Remainder|Taylor's Formula with General Remainder]], for any auxiliary function $\phi$ continuous on the closed interval and differentiable on its interior with $\phi'(t) \neq 0$, the $n$-th order Taylor remainder satisfies:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!} \frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} f^{(n+1)}(\xi) (x - \xi)^n \tag{1}
\end{gather}
$$
for some intermediate point $\xi$ lying strictly between $x_0$ and $x$.

Define the auxiliary power function $\phi$ by:
$$
\begin{gather}
\phi(t) := (x - t)^{n+1} \tag{2}
\end{gather}
$$

The function $\phi$ satisfies the required hypotheses:
1. Being a polynomial in $t$, $\phi(t)$ is continuous on the closed interval between $x_0$ and $x$;
2. Differentiating step 2 with respect to $t$ via the chain rule gives:
$$
\begin{gather}
\phi'(t) = -(n + 1)(x - t)^n \tag{3}
\end{gather}
$$
Because $t$ lies strictly between $x_0$ and $x$, the difference $x - t \neq 0$, which guarantees that $\phi'(t) \neq 0$ for all $t$ in the open interior.

Evaluating the increment of $\phi$ across the interval:
$$
\begin{gather}
\phi(x) - \phi(x_0) = (x - x)^{n+1} - (x - x_0)^{n+1} = -(x - x_0)^{n+1} \tag{4}
\end{gather}
$$

Forming the ratio of increments using step 3 and step 4:
$$
\begin{gather}
\frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} = \frac{-(x - x_0)^{n+1}}{-(n + 1)(x - \xi)^n} = \frac{(x - x_0)^{n+1}}{(n + 1)(x - \xi)^n} \tag{5}
\end{gather}
$$

Substituting step 5 into the master remainder identity of step 1:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!} \left(\frac{(x - x_0)^{n+1}}{(n + 1)(x - \xi)^n}\right) f^{(n+1)}(\xi) (x - \xi)^n \tag{6}
\end{gather}
$$

Because $\xi$ lies strictly between $x_0$ and $x$, the factor $(x - \xi)^n$ is non-zero and cancels algebraically from step 6:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!(n + 1)} f^{(n+1)}(\xi) (x - x_0)^{n+1} \tag{7}
\end{gather}
$$
Recognizing that $n!(n + 1) = (n + 1)!$, step 7 establishes Lagrange's form of the Taylor remainder:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}(\xi)}{(n + 1)!} (x - x_0)^{n+1} \tag{8}
\end{gather}
$$
where $\xi$ lies strictly between $x_0$ and $x$.

Parametrizing the intermediate point as $\xi = x_0 + \theta(x - x_0)$ with $\theta := \frac{\xi - x_0}{x - x_0} \in (0, 1)$, step 8 assumes the equivalent form:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{(n + 1)!} (x - x_0)^{n+1} \tag{9}
\end{gather}
$$
where $\theta \in (0, 1)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$