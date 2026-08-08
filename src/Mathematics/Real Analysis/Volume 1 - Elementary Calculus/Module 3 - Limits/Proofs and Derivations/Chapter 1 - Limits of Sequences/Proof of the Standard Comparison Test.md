---
dg-publish: true
---
Let $\sum_{n=1}^\infty a_n$ and $\sum_{n=1}^\infty b_n$ be two series with non-negative terms ($a_n \ge 0$ and $b_n \ge 0$ for all $n \in \mathbb{N}$), and suppose there exists an index $N_0 \in \mathbb{N}$ such that $a_n \le b_n$ for all $n > N_0$.

For each $n \in \mathbb{N}$, denote the sequences of partial sums by:
$$
\begin{gather}
S_n := \sum_{k=1}^n a_k \quad \text{and} \quad T_n := \sum_{k=1}^n b_k \tag{1}
\end{gather}
$$
Because $a_n \ge 0$ and $b_n \ge 0$, both $\{S_n\}$ and $\{T_n\}$ are monotonically nondecreasing sequences in $\mathbb{R}$.

# Theorem 1
Assume that the dominant series $\sum_{n=1}^\infty b_n$ converges to the finite sum $T \in \mathbb{R}$.

Because $\{T_n\}$ is nondecreasing and converges to $T$, every partial sum satisfies $T_n \le T$ for all $n \in \mathbb{N}$. For any integer $n > N_0$, partition the partial sum $S_n$ at the threshold index $N_0$:
$$
\begin{gather}
S_n = \sum_{k=1}^{N_0} a_k + \sum_{k=N_0+1}^n a_k \tag{2}
\end{gather}
$$
Because $a_k \le b_k$ for all $k > N_0$, step 2 is bounded above by:
$$
\begin{gather}
S_n \le \sum_{k=1}^{N_0} a_k + \sum_{k=N_0+1}^n b_k \le \sum_{k=1}^{N_0} a_k + T_n \le \sum_{k=1}^{N_0} a_k + T =: M < \infty \tag{3}
\end{gather}
$$
Step 3 demonstrates that the sequence of partial sums $\{S_n\}$ is bounded above in $\mathbb{R}$ by the constant $M$. Because $\{S_n\}$ is monotonically nondecreasing and bounded above, the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]] guarantees that $\{S_n\}$ converges to a finite real limit. Therefore, the series $\sum_{n=1}^\infty a_n$ converges.

---
# Theorem 2
Assume that the lesser series $\sum_{n=1}^\infty a_n$ diverges.

Because $a_n \ge 0$ for all $n \in \mathbb{N}$, the sequence of partial sums $\{S_n\}$ is monotonically nondecreasing. By the convergence criterion for series with non-negative terms, $\{S_n\}$ cannot be bounded above; therefore, it must diverge to positive infinity:
$$
\begin{gather}
\lim_{n \to \infty} S_n = +\infty \tag{4}
\end{gather}
$$
For all $n > N_0$, decomposing $T_n$ yields:
$$
\begin{gather}
T_n = \sum_{k=1}^{N_0} b_k + \sum_{k=N_0+1}^n b_k \ge \sum_{k=1}^{N_0} b_k + \sum_{k=N_0+1}^n a_k = \sum_{k=1}^{N_0} (b_k - a_k) + S_n \tag{5}
\end{gather}
$$
Defining the constant $C := \sum_{k=1}^{N_0} (b_k - a_k) \in \mathbb{R}$, step 5 establishes that $T_n \ge S_n + C$ for all $n > N_0$. Taking the limit as $n \to \infty$ on both sides and using step 4 yields: 
$$
\begin{gather}
\lim_{n \to \infty} T_n \ge \lim_{n \to \infty} (S_n + C) = +\infty \implies \lim_{n \to \infty} T_n = +\infty \tag{6}
\end{gather}
$$
Thus, the sequence of partial sums $\{T_n\}$ diverges, proving that the series $\sum_{n=1}^\infty b_n$ diverges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
