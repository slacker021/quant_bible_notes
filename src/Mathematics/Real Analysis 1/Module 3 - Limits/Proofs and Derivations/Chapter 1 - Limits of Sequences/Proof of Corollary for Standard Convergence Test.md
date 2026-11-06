---
dg-publish: true
---
# Corollary 1
Let $\sum_{n=1}^\infty x_n$ and $\sum_{n=1}^\infty y_n$ be two series such that $\sum_{n=1}^\infty y_n$ converges and there exists an index $N_0 \in \mathbb{N}$ such that $|x_n| \le y_n$ for all $n > N_0$.

Because $y_n \ge |x_n| \ge 0$ for all $n > N_0$, the terms of $\sum_{n=1}^\infty y_n$ are non-negative for all $n > N_0$. Let $Y := \sum_{n=1}^\infty y_n < \infty$ denote its finite sum. For any integer $n > N_0$, consider the partial sums of the series of absolute values:
$$
\begin{gather}
S_{|x|, n} := \sum_{k=1}^n |x_k| = \sum_{k=1}^{N_0} |x_k| + \sum_{k=N_0+1}^n |x_k| \tag{1}
\end{gather}
$$
Because $|x_k| \le y_k$ for each $k > N_0$, step 1 is bounded above by: 
$$
\begin{gather}
S_{|x|, n} \le \sum_{k=1}^{N_0} |x_k| + \sum_{k=N_0+1}^n y_k \le \sum_{k=1}^{N_0} |x_k| + Y =: M < \infty \tag{2}
\end{gather}
$$
Because $|x_k| \ge 0$, the sequence of partial sums $\{S_{|x|, n}\}$ is monotonically nondecreasing. Furthermore, by step 2, it is bounded above by the constant $M \in \mathbb{R}$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], the sequence $\{S_{|x|, n}\}$ converges to a finite limit. Therefore, $\sum_{n=1}^\infty |x_n|$ converges, which proves that the series $\sum_{n=1}^\infty x_n$ converges absolutely.

---
# Corollary 2
Let $\sum_{n=1}^\infty x_n$ be an infinite series of real numbers, and let $\alpha := \limsup_{n \to \infty} \sqrt[n]{|x_n|}$.

First, suppose $\alpha < 1$. Choose a real number $r$ such that $\alpha < r < 1$. By the definition of the limit superior as the largest partial limit, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
\sqrt[n]{|x_n|} \le r \implies |x_n| \le r^n \tag{3}
\end{gather}
$$
Because $0 < r < 1$, the geometric series $\sum_{n=1}^\infty r^n$ converges. By Corollary 1, the bound $|x_n| \le r^n$ ensures that $\sum_{n=1}^\infty |x_n|$ converges, so $\sum_{n=1}^\infty x_n$ converges absolutely.

Next, suppose $\alpha > 1$. By definition of the limit superior, there exists a subsequence $\{x_{n_k}\}$ such that: 
$$
\begin{gather}
\lim_{k \to \infty} \sqrt[n_k]{|x_{n_k}|} = \alpha > 1 \tag{4}
\end{gather}
$$
Consequently, there exists an index $K \in \mathbb{N}$ such that for all $k > K$, $\sqrt[n_k]{|x_{n_k}|} > 1$, which implies $|x_{n_k}| > 1$. Because infinitely many terms of the sequence $\{x_n\}$ have absolute value exceeding $1$, the sequence of terms cannot converge to zero ($\lim_{n \to \infty} x_n \neq 0$). By Corollary 4, the failure of the terms to vanish guarantees that $\sum_{n=1}^\infty x_n$ diverges.

---
# Corollary 3
Let $\sum_{n=1}^\infty x_n$ be an infinite series with $x_n \neq 0$ for all $n > N_0$, and suppose that the limit $\alpha := \lim_{n \to \infty} \left| \frac{x_{n+1}}{x_n} \right|$ exists.

First, suppose $\alpha < 1$. Choose a real constant $r$ such that $\alpha < r < 1$, and set $\varepsilon := r - \alpha > 0$. By definition of the limit, there exists an index $N \ge N_0$ such that for all $n \ge N$:
$$
\begin{gather}
\left| \frac{x_{n+1}}{x_n} \right| < \alpha + \varepsilon = r \implies |x_{n+1}| < r |x_n| \tag{5}
\end{gather}
$$
Applying step 5 recursively for any index $n > N$ yields: 
$$
\begin{gather}
|x_n| < r |x_{n-1}| < r^2 |x_{n-2}| < \dots < r^{n - N} |x_N| = \left( \frac{|x_N|}{r^N} \right) r^n \tag{6}
\end{gather}
$$
Defining the constant $C := \frac{|x_N|}{r^N} > 0$, step 6 provides the upper bound $|x_n| < C r^n$ for all $n > N$. Because $0 < r < 1$, the geometric series $\sum_{n=1}^\infty C r^n = C \sum_{n=1}^\infty r^n$ converges. By Corollary 1, the series $\sum_{n=1}^\infty x_n$ converges absolutely.

Next, suppose $\alpha > 1$. Setting $\varepsilon := \alpha - 1 > 0$, there exists an index $N \ge N_0$ such that for all $n \ge N$:
$$
\begin{gather}
\left| \frac{x_{n+1}}{x_n} \right| > \alpha - \varepsilon = 1 \implies |x_{n+1}| > |x_n| \tag{7}
\end{gather}
$$
Step 7 implies that for all $n > N$, $|x_n| > |x_N| > 0$. Because the sequence of terms does not approach zero, Corollary 4 guarantees that the series $\sum_{n=1}^\infty x_n$ diverges.

---
# Corollary 4
To establish the Divergence Test, consider the contrapositive statement: if the series $\sum_{n=1}^\infty x_n$ converges to a finite sum $s \in \mathbb{R}$, then its sequence of terms must converge to zero ($\lim_{n \to \infty} x_n = 0$).

Assume that $\sum_{n=1}^\infty x_n$ converges. By definition, the sequence of partial sums $s_n := \sum_{k=1}^n x_k$ converges to $s$:
$$
\begin{gather}
\lim_{n \to \infty} s_n = s \quad \text{and} \quad \lim_{n \to \infty} s_{n-1} = s \tag{8}
\end{gather}
$$
For every $n \ge 2$, the $n$-th term of the series can be expressed as the difference of consecutive partial sums:
$$
\begin{gather}
x_n = s_n - s_{n-1} \tag{9}
\end{gather}
$$
Passing to the limit as $n \to \infty$ on both sides of step 9 and applying the [[Proof of Arithmetic Operations Involving Limits|difference rule for sequence limits]] yields: 
$$
\begin{gather}
\lim_{n \to \infty} x_n = \lim_{n \to \infty} (s_n - s_{n-1}) = \lim_{n \to \infty} s_n - \lim_{n \to \infty} s_{n-1} = s - s = 0 \tag{10}
\end{gather}
$$
Because the implication $(\sum_{n=1}^\infty x_n \text{ converges}) \implies (\lim_{n \to \infty} x_n = 0)$ holds universally, its logical contrapositive is necessarily true: if $\lim_{n \to \infty} x_n$ does not exist or if $\lim_{n \to \infty} x_n \neq 0$, the series $\sum_{n=1}^\infty x_n$ diverges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
