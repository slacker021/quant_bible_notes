---
dg-publish: true
---
Let $\sum_{n=1}^\infty a_n$ be an infinite series of real numbers that is absolutely convergent, meaning that the series of absolute values $\sum_{n=1}^\infty |a_n|$ converges to a finite real sum.

By the [[Proof of the Cauchy Convergence Criterion for a Series|Cauchy Convergence Criterion for a Series]], the series of absolute values $\sum_{n=1}^\infty |a_n|$ converges if and only if for every $\varepsilon > 0$, there exists an index $N \in \mathbb{N}$ such that for all integers $m \ge n > N$:
$$
\begin{gather}
\sum_{k=n}^m |a_k| = \left| \sum_{k=n}^m |a_k| \right| < \varepsilon \tag{1}
\end{gather}
$$
Now consider the original series $\sum_{n=1}^\infty a_n$. For any integers $m \ge n > N$, applying the [[Proof of the Triangle Inequality|Triangle Inequality]] to the tail sum yields:
$$
\begin{gather}
\left| \sum_{k=n}^m a_k \right| \le \sum_{k=n}^m |a_k| \tag{2}
\end{gather}
$$
Combining step 1 and step 2 demonstrates that for all $m \ge n > N$:
$$
\begin{gather}
\left| \sum_{k=n}^m a_k \right| < \varepsilon \tag{3}
\end{gather}
$$
Step 3 establishes that the original series $\sum_{n=1}^\infty a_n$ satisfies the Cauchy Convergence Criterion. Therefore, the series $\sum_{n=1}^\infty a_n$ converges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
