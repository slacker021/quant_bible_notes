---
dg-publish: true
---
Let $\sum_{n=1}^\infty a_n$ be an infinite series whose terms satisfy $a_n \ge 0$ for all $n \in \mathbb{N}$, and let $\{s_n\}_{n=1}^\infty$ denote its sequence of partial sums:
$$
\begin{gather}
s_n := \sum_{k=1}^n a_k \tag{1}
\end{gather}
$$
For every index $n \in \mathbb{N}$, evaluating the difference between consecutive partial sums yields:
$$
\begin{gather}
s_{n+1} - s_n = a_{n+1} \ge 0 \implies s_n \le s_{n+1} \tag{2}
\end{gather}
$$
Step 2 establishes that the sequence of partial sums $\{s_n\}$ is nondecreasing.

By definition, the series $\sum_{n=1}^\infty a_n$ converges if and only if its sequence of partial sums $\{s_n\}$ converges to a finite limit in $\mathbb{R}$. Applying the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Monotone Convergence Theorem]] to the nondecreasing sequence $\{s_n\}$ confirms that $\{s_n\}$ converges if and only if $\{s_n\}$ is bounded above in $\mathbb{R}$, in which case:
$$
\begin{gather}
\sum_{n=1}^\infty a_n = \lim_{n \to \infty} s_n = \sup_{n \in \mathbb{N}} s_n < +\infty \tag{3}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
