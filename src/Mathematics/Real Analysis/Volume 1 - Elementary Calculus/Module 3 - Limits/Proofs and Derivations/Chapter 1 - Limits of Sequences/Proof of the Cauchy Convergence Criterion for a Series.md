---
dg-publish: true
---
# Theorem 
By definition, the infinite series $\sum_{n=1}^\infty a_n$ converges to a finite real sum if and only if its sequence of partial sums $\{s_n\}$, defined by $s_n := \sum_{k=1}^n a_k$, converges in $\mathbb{R}$.

By the [[Proof of the Cauchy Criterion for Sequences|Cauchy Criterion for Sequences]], $\{s_n\}$ converges if and only if it is a Cauchy sequence: for every $\varepsilon > 0$, there exists an index $N_0 \in \mathbb{N}$ such that $|s_m - s_p| < \varepsilon$ for all $m, p > N_0$.

For any integers $m \ge n \ge 2$, the difference between partial sums evaluates to: 
$$
\begin{gather}
s_m - s_{n-1} = \sum_{k=1}^m a_k - \sum_{k=1}^{n-1} a_k = \sum_{k=n}^m a_k \tag{1}
\end{gather}
$$

**Necessity:**
Assume that the series $\sum_{n=1}^\infty a_n$ converges, so that $\{s_n\}$ is a Cauchy sequence. Given $\varepsilon > 0$, choose an index $N_0 \in \mathbb{N}$ such that $|s_m - s_p| < \varepsilon$ for all $m, p > N_0$, and set $N := N_0 + 1 \in \mathbb{N}$.

For any integers $m, n \in \mathbb{N}$ satisfying $m \ge n > N$, setting $p := n - 1$ ensures that $p \ge N - 1 = N_0$ and $m > N_0$. Applying step 1 yields: 
$$
\begin{gather}
\left| \sum_{k=n}^m a_k \right| = |s_m - s_{n-1}| < \varepsilon \quad \forall m \ge n > N \tag{2}
\end{gather}
$$

**Sufficiency:**
Conversely, assume that for every $\varepsilon > 0$ there exists an index $N \in \mathbb{N}$ such that step 2 holds for all $m \ge n > N$.

Let $m, p \in \mathbb{N}$ satisfy $m, p > N$. If $m = p$, then $|s_m - s_p| = 0 < \varepsilon$. If $m \neq p$, assume without loss of generality that $m > p$, and set $n := p + 1$. Then $m \ge n = p + 1 > N$, so step 1 and step 2 establish that: 
$$
\begin{gather}
|s_m - s_p| = |s_m - s_{n-1}| = \left| \sum_{k=n}^m a_k \right| < \varepsilon \tag{3}
\end{gather}
$$
Thus, $\{s_n\}$ is a Cauchy sequence of real numbers, which guarantees that $\sum_{n=1}^\infty a_n$ converges.

---
# Corollary 
Assume that the series $\sum_{n=1}^\infty a_n$ converges, and let $\varepsilon > 0$ be arbitrary.

By Theorem 1, there exists an index $N \in \mathbb{N}$ such that $\left| \sum_{k=n}^m a_k \right| < \varepsilon$ for all $m \ge n > N$. Specializing this inequality to the case $m = n$ collapses the summation to its single boundary term:
$$
\begin{gather}
\left| \sum_{k=n}^n a_k \right| = |a_n| < \varepsilon \quad \forall n > N \tag{4}
\end{gather}
$$
By definition of the limit of a sequence, step 4 establishes that: 
$$
\begin{gather}
\lim_{n \to \infty} a_n = 0 \tag{5}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
