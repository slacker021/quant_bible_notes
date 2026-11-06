---
dg-publish: true
---
Let $K \subset \mathbb{R}$ be a compact subset of $\mathbb{R}$, and let $f: K \to \mathbb{R}$ be continuous on $K$. 

Suppose, for the sake of contradiction, that $f$ is not uniformly continuous on $K$. 

Negating the definition of uniform continuity implies that there exists an error tolerance $\varepsilon_0 > 0$ such that for every $\delta > 0$, there exist witness points $x, y \in K$ satisfying:
$$
\begin{gather}
|x - y| < \delta \quad \text{and} \quad |f(x) - f(y)| \ge \varepsilon_0 \tag{1}
\end{gather}
$$

For each positive integer $n \in \mathbb{N}$, choose the parameter value $\delta_n := \frac{1}{n} > 0$. 

By step 1, there exist corresponding pairs of points $x_n, y_n \in K$ such that for all $n \in \mathbb{N}$:
$$
\begin{gather}
|x_n - y_n| < \frac{1}{n} \tag{2}
\end{gather}
$$
and:
$$
\begin{gather}
|f(x_n) - f(y_n)| \ge \varepsilon_0 \tag{3}
\end{gather}
$$

Consider the sequence $\{x_n\}_{n=1}^\infty \subseteq K$. 

Because $K$ is compact, it is sequentially compact. Therefore, there exists a subsequence $\{x_{n_k}\}_{k=1}^\infty$ that converges to a limit point $x_0 \in K$:
$$
\begin{gather}
\lim_{k \to \infty} x_{n_k} = x_0 \tag{4}
\end{gather}
$$

Now consider the corresponding subsequence $\{y_{n_k}\}_{k=1}^\infty \subseteq K$. 

Applying the triangle inequality:
$$
\begin{gather}
|y_{n_k} - x_0| \le |y_{n_k} - x_{n_k}| + |x_{n_k} - x_0| \tag{5}
\end{gather}
$$

Substituting the bound of step 2 into step 5:
$$
\begin{gather}
|y_{n_k} - x_0| < \frac{1}{n_k} + |x_{n_k} - x_0| \tag{6}
\end{gather}
$$

Taking the limit of step 6 as $k \to \infty$, and noting that $\frac{1}{n_k} \le \frac{1}{k} \to 0$ and $|x_{n_k} - x_0| \to 0$:
$$
\begin{gather}
\lim_{k \to \infty} |y_{n_k} - x_0| = 0 \implies \lim_{k \to \infty} y_{n_k} = x_0 \tag{7}
\end{gather}
$$

Thus, both subsequences $\{x_{n_k}\}$ and $\{y_{n_k}\}$ converge to the same point $x_0 \in K$. 

Because $f$ is continuous on $K$, it is continuous at $x_0$. Applying the Heine sequential criterion to step 4 and step 7:
$$
\begin{gather}
\lim_{k \to \infty} f(x_{n_k}) = f(x_0) \quad \text{and} \quad \lim_{k \to \infty} f(y_{n_k}) = f(x_0) \tag{8}
\end{gather}
$$

Applying the algebraic properties of limits to the difference sequence:
$$
\begin{gather}
\lim_{k \to \infty} \big(f(x_{n_k}) - f(y_{n_k})\big) = f(x_0) - f(x_0) = 0 \tag{9}
\end{gather}
$$
which implies:
$$
\begin{gather}
\lim_{k \to \infty} |f(x_{n_k}) - f(y_{n_k})| = 0 \tag{10}
\end{gather}
$$

However, evaluating the inequality of step 3 along the subsequence yields:
$$
\begin{gather}
\forall k \in \mathbb{N}, \quad |f(x_{n_k}) - f(y_{n_k})| \ge \varepsilon_0 > 0 \tag{11}
\end{gather}
$$

Taking the limit of step 11 as $k \to \infty$:
$$
\begin{gather}
\lim_{k \to \infty} |f(x_{n_k}) - f(y_{n_k})| \ge \varepsilon_0 > 0 \tag{12}
\end{gather}
$$

Comparing step 10 and step 12 yields the contradiction $0 \ge \varepsilon_0 > 0$. 

This establishes that $f$ must be uniformly continuous on $K$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
