---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, let $x_0, x \in I$ be two distinct points, and let $J \subset I$ denote the closed compact interval with endpoints $x_0$ and $x$ (so $J = [x_0, x]$ if $x_0 < x$, and $J = [x, x_0]$ if $x < x_0$). 

Suppose that $f: I \to \mathbb{R}$ satisfies $f \in C^n(J)$ and that the $(n + 1)$-th derivative $f^{(n+1)}(t)$ exists for every point $t \in \operatorname{int}(J)$. Let $\phi: J \to \mathbb{R}$ be a function continuous on $J$ and differentiable on $\operatorname{int}(J)$, satisfying the non-vanishing derivative condition:
$$
\begin{gather}
\phi'(t) \neq 0, \quad \forall t \in \operatorname{int}(J) \tag{1}
\end{gather}
$$

Define the auxiliary displacement function $F: J \to \mathbb{R}$ of the variable $t \in J$ by:
$$
\begin{gather}
F(t) := f(x) - \sum_{k=0}^n \frac{f^{(k)}(t)}{k!} (x - t)^k, \quad \forall t \in J \tag{2}
\end{gather}
$$

Evaluating $F(t)$ at the endpoints of $J$:
- At $t = x$:
$$
\begin{gather}
F(x) = f(x) - \left(f(x) + \sum_{k=1}^n \frac{f^{(k)}(x)}{k!} (x - x)^k\right) = f(x) - f(x) = 0 \tag{3}
\end{gather}
$$
- At $t = x_0$:
$$
\begin{gather}
F(x_0) = f(x) - \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k = f(x) - P_n(x_0; x) = r_n(x_0; x) \tag{4}
\end{gather}
$$
where $r_n(x_0; x)$ is the Taylor remainder of order $n$.

Because $f \in C^n(J)$ and the monomial functions $t \mapsto (x - t)^k$ are smooth, $F(t)$ is continuous on $J$. Furthermore, for all $t \in \operatorname{int}(J)$, the function $F(t)$ is differentiable with respect to $t$. Differentiating step 2 term by term via the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]] and the chain rule:
$$
\begin{gather}
F'(t) = -\frac{d}{dt}\left[f(t)\right] - \sum_{k=1}^n \frac{d}{dt}\left[\frac{f^{(k)}(t)}{k!} (x - t)^k\right] \tag{5}
\end{gather}
$$

Applying the product rule to each term in the summation of step 5:
$$
\begin{gather}
\frac{d}{dt}\left[\frac{f^{(k)}(t)}{k!} (x - t)^k\right] = \frac{f^{(k+1)}(t)}{k!} (x - t)^k - \frac{f^{(k)}(t)}{k!} k (x - t)^{k-1} \tag{6}
\end{gather}
$$
Simplifying $\frac{k}{k!} = \frac{1}{(k - 1)!}$ in step 6:
$$
\begin{gather}
\frac{d}{dt}\left[\frac{f^{(k)}(t)}{k!} (x - t)^k\right] = \frac{f^{(k+1)}(t)}{k!} (x - t)^k - \frac{f^{(k)}(t)}{(k - 1)!} (x - t)^{k-1} \tag{7}
\end{gather}
$$

Substituting step 7 into step 5 yields:
$$
\begin{gather}
F'(t) = -f'(t) - \sum_{k=1}^n \left(\frac{f^{(k+1)}(t)}{k!} (x - t)^k - \frac{f^{(k)}(t)}{(k - 1)!} (x - t)^{k-1}\right) \tag{8}
\end{gather}
$$
The summation in step 8 is a telescoping sum:
$$
\begin{gather}
\sum_{k=1}^n \left(\frac{f^{(k+1)}(t)}{k!} (x - t)^k - \frac{f^{(k)}(t)}{(k - 1)!} (x - t)^{k-1}\right) = \frac{f^{(n+1)}(t)}{n!} (x - t)^n - f'(t) \tag{9}
\end{gather}
$$
Substituting step 9 into step 8, the boundary rate $f'(t)$ cancels completely:
$$
\begin{gather}
F'(t) = -f'(t) - \left(\frac{f^{(n+1)}(t)}{n!} (x - t)^n - f'(t)\right) = -\frac{f^{(n+1)}(t)}{n!} (x - t)^n \tag{10}
\end{gather}
$$

Both $F$ and $\phi$ are continuous on $J$ and differentiable on $\operatorname{int}(J)$, with $\phi'(t) \neq 0$ on $\operatorname{int}(J)$. By virtue of [[Proof of Cauchy's Generalized Finite-Increment Theorem|Cauchy's Generalized Finite-Increment Theorem]], there exists an intermediate point $\xi \in \operatorname{int}(J)$ such that:
$$
\begin{gather}
\frac{F(x) - F(x_0)}{\phi(x) - \phi(x_0)} = \frac{F'(\xi)}{\phi'(\xi)} \tag{11}
\end{gather}
$$

Substituting $F(x) = 0$ from step 3 and $F(x_0) = r_n(x_0; x)$ from step 4 into step 11:
$$
\begin{gather}
\frac{0 - r_n(x_0; x)}{\phi(x) - \phi(x_0)} = \frac{F'(\xi)}{\phi'(\xi)} \implies -\frac{r_n(x_0; x)}{\phi(x) - \phi(x_0)} = \frac{F'(\xi)}{\phi'(\xi)} \tag{12}
\end{gather}
$$

Substituting the derivative evaluation of step 10 into step 12:
$$
\begin{gather}
-\frac{r_n(x_0; x)}{\phi(x) - \phi(x_0)} = \frac{-\dfrac{f^{(n+1)}(\xi)}{n!} (x - \xi)^n}{\phi'(\xi)} \tag{13}
\end{gather}
$$

Multiplying step 13 by $-(\phi(x) - \phi(x_0))$ isolates the remainder:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{n!} \frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} f^{(n+1)}(\xi) (x - \xi)^n \tag{14}
\end{gather}
$$
where $\xi$ lies strictly between $x_0$ and $x$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$