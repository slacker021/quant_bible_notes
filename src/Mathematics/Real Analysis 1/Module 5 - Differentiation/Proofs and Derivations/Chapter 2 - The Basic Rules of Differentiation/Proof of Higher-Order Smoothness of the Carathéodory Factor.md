---
dg-publish: true
---
Let $U(x_0) \subseteq \mathbb{R}$ be an open neighborhood of an anchor point $x_0 \in \mathbb{R}$, and let $f: U(x_0) \to \mathbb{R}$ be a function satisfying the Carathéodory factorization:
$$
\begin{gather}
f(x) - f(x_0) = \phi(x)(x - x_0), \quad \forall x \in U(x_0) \tag{1}
\end{gather}
$$
for some auxiliary function $\phi: U(x_0) \to \mathbb{R}$. Assume that $\phi \in C^{n-1}(U(x_0))$ for some integer $n \in \mathbb{N}$.

If $n = 1$, the hypothesis states that $\phi \in C^0(U(x_0))$, so $\phi$ is continuous at $x_0$. By the [[Proof of The Carathéodory Differentiability Criterion|Carathéodory Differentiability Criterion]], $f$ is differentiable at $x_0$ with:
$$
\begin{gather}
f'(x_0) = \phi(x_0) = 1 \cdot \phi^{(0)}(x_0) \tag{2}
\end{gather}
$$
which establishes the base identity for $n = 1$.

Now consider $n \ge 2$. Define the linear polynomial mapping $v: \mathbb{R} \to \mathbb{R}$ by:
$$
\begin{gather}
v(x) := x - x_0 \tag{3}
\end{gather}
$$

The function $v$ is infinitely differentiable on $\mathbb{R}$, with successive derivatives given by:
$$
\begin{gather}
v'(x) = 1, \quad \text{and} \quad v^{(j)}(x) = 0, \quad \forall j \ge 2 \tag{4}
\end{gather}
$$

Rewriting step 1 as $f(x) = f(x_0) + \phi(x)v(x)$, and applying the general Leibniz formula for products to $\phi(x)v(x)$ on $U(x_0)$, the $k$-th derivative of $f$ for any integer $1 \le k \le n - 1$ satisfies:
$$
\begin{gather}
f^{(k)}(x) = \sum_{j=0}^k \binom{k}{j} \phi^{(k-j)}(x) v^{(j)}(x) \tag{5}
\end{gather}
$$

By virtue of step 4, all terms in the summation of step 5 with $j \ge 2$ vanish identically. The summation collapses to the first two terms:
$$
\begin{gather}
f^{(k)}(x) = \binom{k}{0} \phi^{(k)}(x) v(x) + \binom{k}{1} \phi^{(k-1)}(x) v'(x) \tag{6}
\end{gather}
$$

Substituting $v(x) = x - x_0$ and $v'(x) = 1$ into step 6 gives:
$$
\begin{gather}
f^{(k)}(x) = \phi^{(k)}(x)(x - x_0) + k \phi^{(k-1)}(x), \quad \forall x \in U(x_0) \tag{7}
\end{gather}
$$
for every $k \in \{1, 2, \dots, n - 1\}$.

Setting $k = n - 1$ in step 7 yields the explicit expression for the $(n-1)$-th derivative throughout $U(x_0)$:
$$
\begin{gather}
f^{(n-1)}(x) = \phi^{(n-1)}(x)(x - x_0) + (n - 1)\phi^{(n-2)}(x) \tag{8}
\end{gather}
$$

Evaluating step 8 at the anchor point $x = x_0$ gives:
$$
\begin{gather}
f^{(n-1)}(x_0) = \phi^{(n-1)}(x_0)(x_0 - x_0) + (n - 1)\phi^{(n-2)}(x_0) = (n - 1)\phi^{(n-2)}(x_0) \tag{9}
\end{gather}
$$

To determine whether the $n$-th derivative $f^{(n)}(x_0)$ exists, evaluate the limit of the difference quotient of $f^{(n-1)}$ at $x_0$:
$$
\begin{gather}
\frac{f^{(n-1)}(x) - f^{(n-1)}(x_0)}{x - x_0} = \frac{\phi^{(n-1)}(x)(x - x_0) + (n - 1)\big(\phi^{(n-2)}(x) - \phi^{(n-2)}(x_0)\big)}{x - x_0} \tag{10}
\end{gather}
$$
for all $x \in U(x_0) \setminus \{x_0\}$.

Distributing the division across the two terms in step 10 yields:
$$
\begin{gather}
\frac{f^{(n-1)}(x) - f^{(n-1)}(x_0)}{x - x_0} = \phi^{(n-1)}(x) + (n - 1)\left[\frac{\phi^{(n-2)}(x) - \phi^{(n-2)}(x_0)}{x - x_0}\right] \tag{11}
\end{gather}
$$

Because $\phi \in C^{n-1}(U(x_0))$, the derivative $\phi^{(n-1)}$ is continuous on $U(x_0)$, guaranteeing that:
$$
\begin{gather}
\lim_{x \to x_0} \phi^{(n-1)}(x) = \phi^{(n-1)}(x_0) \tag{12}
\end{gather}
$$

Furthermore, because $\phi^{(n-1)}(x_0) = (\phi^{(n-2)})'(x_0)$ exists by definition of the higher derivative, the limit of the bracketed difference quotient in step 11 converges to $\phi^{(n-1)}(x_0)$:
$$
\begin{gather}
\lim_{x \to x_0} \frac{\phi^{(n-2)}(x) - \phi^{(n-2)}(x_0)}{x - x_0} = \phi^{(n-1)}(x_0) \tag{13}
\end{gather}
$$

Taking the limit of both sides of step 11 as $x \to x_0$ and applying step 12 and step 13 produces:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f^{(n-1)}(x) - f^{(n-1)}(x_0)}{x - x_0} = \phi^{(n-1)}(x_0) + (n - 1)\phi^{(n-1)}(x_0) = n \, \phi^{(n-1)}(x_0) \tag{14}
\end{gather}
$$

Because this limit exists as a finite real number, $f$ is $n$-times differentiable at $x_0$, and its $n$-th order derivative satisfies:
$$
\begin{gather}
f^{(n)}(x_0) = n \, \phi^{(n-1)}(x_0) \tag{15}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
