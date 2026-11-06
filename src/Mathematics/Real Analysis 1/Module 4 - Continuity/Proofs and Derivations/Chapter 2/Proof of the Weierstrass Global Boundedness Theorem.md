---
dg-publish: true
---
Let $K \subset \mathbb{R}$ be a compact subset of the real numbers (that is, $K$ is closed and bounded in $\mathbb{R}$), and let $f: K \to \mathbb{R}$ be continuous on $K$. 

Suppose, for the sake of contradiction, that $f$ is unbounded on $K$. 

This assumption implies that for every positive integer $n \in \mathbb{N}$, there exists a corresponding point $x_n \in K$ such that:
$$
\begin{gather}
|f(x_n)| > n \tag{1}
\end{gather}
$$

Consider the sequence of points $\{x_n\}_{n=1}^\infty \subseteq K$. 

Because $K$ is a bounded subset of $\mathbb{R}$, the sequence $\{x_n\}_{n=1}^\infty$ is bounded in $\mathbb{R}$. 

By the Bolzano–Weierstrass Theorem, every bounded infinite sequence of real numbers possesses a convergent subsequence. Therefore, there exists a subsequence $\{x_{n_k}\}_{k=1}^\infty$ and a limit point $x_0 \in \mathbb{R}$ such that:
$$
\begin{gather}
\lim_{k \to \infty} x_{n_k} = x_0 \tag{2}
\end{gather}
$$

Because $K$ is closed in $\mathbb{R}$, it contains all its accumulation points. Since $\{x_{n_k}\} \subseteq K$, it follows from step 2 that:
$$
\begin{gather}
x_0 \in K \tag{3}
\end{gather}
$$

Because $f$ is continuous on $K$, $f$ is continuous at $x_0 \in K$. 

Applying the Heine sequential criterion for continuity to the convergent subsequence of step 2:
$$
\begin{gather}
\lim_{k \to \infty} f(x_{n_k}) = f(x_0) \tag{4}
\end{gather}
$$

Because $x_0 \in K$, the value $f(x_0)$ is a finite real number. 

Every convergent real sequence is bounded. It follows from step 4 that there exists a positive real constant $C > 0$ such that:
$$
\begin{gather}
\forall k \in \mathbb{N}, \quad |f(x_{n_k})| \le C \tag{5}
\end{gather}
$$

However, by the original construction in step 1, the elements of the subsequence satisfy:
$$
\begin{gather}
|f(x_{n_k})| > n_k \ge k \tag{6}
\end{gather}
$$

Combining the inequality of step 5 and the inequality of step 6:
$$
\begin{gather}
\forall k \in \mathbb{N}, \quad k \le n_k < |f(x_{n_k})| \le C \tag{7}
\end{gather}
$$

The relation of step 7 asserts that the set of natural numbers $\mathbb{N}$ is bounded above by $C$, which violates the Archimedean property of $\mathbb{R}$. 

This contradiction demonstrates that the initial assumption must be false. 

Therefore, $f$ is bounded on $K$, meaning there exists a constant $M > 0$ such that $|f(x)| \le M$ for all $x \in K$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
