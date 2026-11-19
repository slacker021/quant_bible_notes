---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be a function that is Riemann integrable on $[a, b]$, denoted $f \in \mathcal{R}[a, b]$, with Riemann integral $I \in \mathbb{R}$.

Suppose, for the sake of contradiction, that $f$ is not bounded on $[a, b]$. 

By the definition of the Riemann integral as the limit of Riemann sums as the partition mesh fineness tends to zero, for every $\varepsilon > 0$, there exists a corresponding gauge fineness $\delta > 0$ such that for every marked partition $(P, \xi)$ of $[a, b]$ satisfying $\lambda(P) < \delta$, the Riemann sum satisfies:
$$
\begin{gather}
\left| \sigma(f; P, \xi) - I \right| < \varepsilon \tag{1}
\end{gather}
$$

Setting the error tolerance specifically to $\varepsilon = 1$, step 1 guarantees the existence of a threshold $\delta > 0$ such that for any marked partition $(P, \xi)$ with $\lambda(P) < \delta$:
$$
\begin{gather}
\left| \sum_{i=1}^n f(\xi_i) \Delta x_i - I \right| < 1 \tag{2}
\end{gather}
$$

Fix an arbitrary partition $P = \{x_0, x_1, \dots, x_n\}$ of $[a, b]$ with mesh fineness satisfying $\lambda(P) < \delta$. For instance, one may choose the uniform partition with nodes $x_i = a + i \frac{b - a}{n}$ where the integer $n$ is chosen large enough so that $\frac{b - a}{n} < \delta$.

Because the interval $[a, b]$ is the finite union of the $n$ compact subintervals:
$$
\begin{gather}
[a, b] = \bigcup_{i=1}^n [x_{i-1}, x_i] \tag{3}
\end{gather}
$$
if $f$ were bounded on each individual subinterval $[x_{i-1}, x_i]$ by some constant $M_i < \infty$, the global bound:
$$
\begin{gather}
\sup_{x \in [a, b]} |f(x)| \le \max_{1 \le i \le n} M_i < \infty \tag{4}
\end{gather}
$$
would hold, contradicting the initial hypothesis of unboundedness. Consequently, there exists at least one index $k \in \{1, \dots, n\}$ such that $f$ is unbounded on the subinterval $[x_{k-1}, x_k]$.

For every index $i \neq k$, select an arbitrary sample tag $\xi_i \in [x_{i-1}, x_i]$. Having fixed these $n - 1$ sample tags, the partial contribution of all subintervals other than the $k$-th subinterval to the Riemann sum is a fixed real number:
$$
\begin{gather}
S^* := \sum_{\substack{i=1 \\ i \neq k}}^n f(\xi_i) \Delta x_i \tag{5}
\end{gather}
$$

For any chosen sample point $\xi_k \in [x_{k-1}, x_k]$, the full Riemann sum associated with the marked partition $(P, \xi)$ decomposes as:
$$
\begin{gather}
\sigma(f; P, \xi) = f(\xi_k) \Delta x_k + S^* \tag{6}
\end{gather}
$$

Subtracting the integral $I$ from step 6 and applying the reverse triangle inequality yields:
$$
\begin{gather}
|\sigma(f; P, \xi) - I| = \left| f(\xi_k) \Delta x_k + (S^* - I) \right| \ge |f(\xi_k)| \Delta x_k - |S^* - I| \tag{7}
\end{gather}
$$

Because $f$ is unbounded on $[x_{k-1}, x_k]$, the set of values $\{|f(x)| : x \in [x_{k-1}, x_k]\}$ is not bounded above in $\mathbb{R}$. Furthermore, since $a < b$ and the partition nodes are strictly ordered, the subinterval length is strictly positive: $\Delta x_k = x_k - x_{k-1} > 0$.

Therefore, by the definition of an unbounded set of real numbers, there exists a point $\xi_k \in [x_{k-1}, x_k]$ such that:
$$
\begin{gather}
|f(\xi_k)| > \frac{|S^* - I| + 2}{\Delta x_k} \tag{8}
\end{gather}
$$

Multiplying step 8 by $\Delta x_k > 0$ yields:
$$
\begin{gather}
|f(\xi_k)| \Delta x_k > |S^* - I| + 2 \tag{9}
\end{gather}
$$

Subtracting $|S^* - I|$ from both sides of step 9:
$$
\begin{gather}
|f(\xi_k)| \Delta x_k - |S^* - I| > 2 \tag{10}
\end{gather}
$$

Combining the reverse triangle inequality of step 7 with the strict lower bound of step 10 establishes:
$$
\begin{gather}
|\sigma(f; P, \xi) - I| > 2 \tag{11}
\end{gather}
$$

However, the marked partition $(P, \xi)$ has mesh fineness $\lambda(P) < \delta$, so by step 2, the Riemann sum must satisfy:
$$
\begin{gather}
|\sigma(f; P, \xi) - I| < 1 \tag{12}
\end{gather}
$$

The simultaneous validity of step 11 and step 12 leads to:
$$
\begin{gather}
2 < |\sigma(f; P, \xi) - I| < 1 \tag{13}
\end{gather}
$$
which asserts $2 < 1$. This is a strict arithmetic contradiction.

It follows that the assumption that $f$ is unbounded on $[a, b]$ is untenable. Hence, $f$ is bounded on $[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
