---
dg-publish: true
---
# Proposition 
Let $\{a_n\}_{n=1}^\infty$ be a monotonically nonincreasing sequence of non-negative real numbers ($a_1 \ge a_2 \ge \dots \ge a_n \ge \dots \ge 0$). Denote the $n$-th partial sum of the parent series $\sum_{n=1}^\infty a_n$ by $S_n := \sum_{j=1}^n a_j$, and the $k$-th partial sum of the condensed series $\sum_{k=0}^\infty 2^k a_{2^k}$ by $T_k := \sum_{j=0}^k 2^j a_{2^j}$.

Because $a_n \ge 0$ and $2^j a_{2^j} \ge 0$ for all indices, both sequences of partial sums $\{S_n\}$ and $\{T_k\}$ are monotonically nondecreasing. By the convergence criterion for series with non-negative terms, each series converges if and only if its sequence of partial sums is bounded above in $\mathbb{R}$.

**Sufficiency:**
Assume that the condensed series $\sum_{k=0}^\infty 2^k a_{2^k}$ converges, so that its sequence of partial sums is bounded above: there exists a real constant $M > 0$ such that $T_k \le M$ for all $k \in \mathbb{N} \cup \{0\}$.

For any integer $n \in \mathbb{N}$, choose $k \in \mathbb{N}$ sufficiently large that $n \le 2^{k+1} - 1$. Because $a_j \ge 0$, the monotonicity of $\{S_n\}$ implies that $S_n \le S_{2^{k+1}-1}$. Partitioning the partial sum $S_{2^{k+1}-1}$ into dyadic blocks of length $2^m$ for $m \in \{0, 1, \dots, k\}$ yields: 
$$
\begin{gather}
S_{2^{k+1}-1} = a_1 + (a_2 + a_3) + (a_4 + a_5 + a_6 + a_7) + \dots + \sum_{j=2^k}^{2^{k+1}-1} a_j \tag{1}
\end{gather}
$$
Because $\{a_n\}$ is nonincreasing, each term in the $m$-th dyadic block satisfies $a_j \le a_{2^m}$ for all $j \ge 2^m$. Bounding each block by its leading term:
$$
\begin{gather}
\sum_{j=2^m}^{2^{m+1}-1} a_j \le \sum_{j=2^m}^{2^{m+1}-1} a_{2^m} = 2^m a_{2^m} \tag{2}
\end{gather}
$$
Substituting the upper bounds of step 2 into step 1 yields: 
$$
\begin{gather}
S_n \le S_{2^{k+1}-1} \le a_1 + 2 a_2 + 4 a_4 + \dots + 2^k a_{2^k} = T_k \le M \tag{3}
\end{gather}
$$
Because $S_n \le M$ holds for all $n \in \mathbb{N}$, the sequence of partial sums $\{S_n\}$ is bounded above in $\mathbb{R}$. Therefore, the series $\sum_{n=1}^\infty a_n$ converges.

**Necessity:**
Conversely, assume that the parent series $\sum_{n=1}^\infty a_n$ converges, so that its sequence of partial sums is bounded above: there exists a real constant $L > 0$ such that $S_n \le L$ for all $n \in \mathbb{N}$.

For any $k \in \mathbb{N}$, partition the partial sum $S_{2^k}$ into dyadic blocks terminating at powers of $2$:
$$
\begin{gather}
S_{2^k} = a_1 + a_2 + (a_3 + a_4) + (a_5 + a_6 + a_7 + a_8) + \dots + \sum_{j=2^{m-1}+1}^{2^m} a_j + \dots + \sum_{j=2^{k-1}+1}^{2^k} a_j \tag{4}
\end{gather}
$$
Because $\{a_n\}$ is nonincreasing, each of the $2^{m-1}$ terms in the $m$-th block satisfies $a_j \ge a_{2^m}$ for all $j \le 2^m$. Consequently:
$$
\begin{gather}
\sum_{j=2^{m-1}+1}^{2^m} a_j \ge \sum_{j=2^{m-1}+1}^{2^m} a_{2^m} = 2^{m-1} a_{2^m} = \frac{1}{2} \cdot 2^m a_{2^m} \tag{5}
\end{gather}
$$
Substituting the lower bounds of step 5 into step 4 gives: 
$$
\begin{gather}
S_{2^k} \ge a_1 + a_2 + \frac{1}{2}(4 a_4 + 8 a_8 + \dots + 2^k a_{2^k}) = \frac{1}{2} a_1 + \frac{1}{2} \sum_{j=0}^k 2^j a_{2^j} = \frac{1}{2} a_1 + \frac{1}{2} T_k \tag{6}
\end{gather}
$$
Rearranging step 6 to isolate $T_k$ and utilizing the uniform bound $S_{2^k} \le L$ produces: 
$$
\begin{gather}
T_k \le 2 S_{2^k} - a_1 \le 2L - a_1 \quad \forall k \in \mathbb{N} \tag{7}
\end{gather}
$$
Thus, $\{T_k\}$ is bounded above in $\mathbb{R}$, which proves that the condensed series $\sum_{k=0}^\infty 2^k a_{2^k}$ converges.

---
# Corollary 
Consider the Dirichlet $p$-series $\sum_{n=1}^\infty \frac{1}{n^p}$ for an arbitrary parameter $p \in \mathbb{R}$.

If $p \le 0$, then $\frac{1}{n^p} = n^{-p} \ge 1$ for all $n \in \mathbb{N}$. Because the individual terms fail to approach zero ($\lim_{n \to \infty} \frac{1}{n^p} \neq 0$), the series diverges by the Divergence Test.

Suppose $p > 0$. For all $n \in \mathbb{N}$, the strict inequality $n < n + 1$ implies $0 < n^p < (n + 1)^p$, which gives: 
$$
\begin{gather}
\frac{1}{n^p} > \frac{1}{(n + 1)^p} > 0 \tag{8}
\end{gather}
$$
Because the terms $a_n := \frac{1}{n^p}$ form a strictly decreasing sequence of positive real numbers, Proposition 1 applies. Constructing the condensed series yields: 
$$
\begin{gather}
\sum_{k=0}^\infty 2^k a_{2^k} = \sum_{k=0}^\infty 2^k \left(\frac{1}{(2^k)^p}\right) = \sum_{k=0}^\infty 2^k \cdot 2^{-kp} = \sum_{k=0}^\infty \left(2^{1-p}\right)^k \tag{9}
\end{gather}
$$
Step 9 is a geometric series with common ratio $r := 2^{1-p} > 0$. By the geometric series convergence theorem, $\sum_{k=0}^\infty r^k$ converges if and only if $r < 1$:
$$
\begin{gather}
2^{1-p} < 1 = 2^0 \iff 1 - p < 0 \iff p > 1 \tag{10}
\end{gather}
$$
By Proposition 1, the Dirichlet $p$-series $\sum_{n=1}^\infty \frac{1}{n^p}$ converges if $p > 1$ and diverges if $p \le 1$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
