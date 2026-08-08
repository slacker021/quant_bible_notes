---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be an arbitrary sequence of real numbers. For each $n \in \mathbb{N}$, define the tail supremum $s_n := \sup_{k \ge n} x_k$ and the tail infimum $i_n := \inf_{k \ge n} x_k$ in the extended real line $\mathbb{R} \cup \{-\infty, +\infty\}$. Denote the superior limit by $L := \limsup_{n \to \infty} x_n = \lim_{n \to \infty} s_n$ and the inferior limit by $l := \liminf_{n \to \infty} x_n = \lim_{n \to \infty} i_n$.

# Proposition 1
First, consider the superior limit $L \in \mathbb{R} \cup \{-\infty, +\infty\}$ across all three possible cases:

**Case 1 ($L \in \mathbb{R}$ is finite):** If $\{x_n\}$ is bounded in $\mathbb{R}$ ($m \le x_n \le M$ for all $n \in \mathbb{N}$), then $m \le i_n \le s_n \le M$ for all $n \in \mathbb{N}$, so both $L$ and $l$ are finite real numbers. Because $\lim_{n \to \infty} s_n = L$, for each $m \in \mathbb{N}$ there exists an index $N_m \in \mathbb{N}$ such that:
$$
\begin{gather}
|s_n - L| < \frac{1}{2m} \iff L - \frac{1}{2m} < s_n < L + \frac{1}{2m} \quad \forall n \ge N_m \tag{1}
\end{gather}
$$
Construct a subsequence $\{x_{n_m}\}$ inductively. For $m = 1$, set $N^{(1)} := N_1$. Because $s_{N^{(1)}} = \sup_{k \ge N^{(1)}} x_k$, the quantity $s_{N^{(1)}} - \frac{1}{2}$ is not an upper bound for $\{x_k \mid k \ge N^{(1)}\}$, so there exists an index $n_1 \ge N^{(1)}$ such that $s_{N^{(1)}} - \frac{1}{2} < x_{n_1} \le s_{N^{(1)}}$.

Having chosen indices $n_1 < n_2 < \dots < n_{m-1}$, set $N^{(m)} := \max(N_m, n_{m-1} + 1)$. Because $s_{N^{(m)}} = \sup_{k \ge N^{(m)}} x_k$, there exists an index $n_m \ge N^{(m)} > n_{m-1}$ such that:
$$
\begin{gather}
s_{N^{(m)}} - \frac{1}{2m} < x_{n_m} \le s_{N^{(m)}} \tag{2}
\end{gather}
$$
Combining step 1 (for $n = N^{(m)} \ge N_m$) and step 2 yields:
$$
\begin{gather}
L - \frac{1}{m} < s_{N^{(m)}} - \frac{1}{2m} < x_{n_m} \le s_{N^{(m)}} < L + \frac{1}{2m} < L + \frac{1}{m} \tag{3}
\end{gather}
$$
Step 3 demonstrates that $|x_{n_m} - L| < \frac{1}{m}$ for all $m \in \mathbb{N}$. By the [[Proof of the Squeeze Theorem|Squeeze Theorem]], $\lim_{m \to \infty} x_{n_m} = L$, proving that $L$ is a partial limit of $\{x_n\}$.

**Case 2 ($L = +\infty$):** By definition, $L = +\infty$ occurs if and only if $\{x_n\}$ is unbounded above. By the [[Proof that a Convergent Subsequence or Subsequence Tending to Infinity Can be Constructed From a Sequence of Real Numbers|Lemma on Subsequences and Infinity]], there exists a subsequence $\{x_{n_k}\}$ tending to $+\infty$. Thus, $L = +\infty$ is a partial limit of $\{x_n\}$.

**Case 3 ($L = -\infty$):** Here $\lim_{n \to \infty} s_n = -\infty$. Because $x_n \le s_n$ holds for all $n \in \mathbb{N}$, it follows that $\lim_{n \to \infty} x_n = -\infty$, meaning every subsequence tends to $-\infty$. Thus, $L = -\infty$ is a partial limit.

By an identical dual construction applied to the tail infima $i_n = \inf_{k \ge n} x_k$ (or by reflecting the sequence to $\{-x_n\}$), the inferior limit $l = \liminf_{n \to \infty} x_n$ is also a partial limit of $\{x_n\}$.

---
# Proposition 2
Let $M \in \mathbb{R} \cup \{-\infty, +\infty\}$ be an arbitrary partial limit of the sequence $\{x_n\}$. By definition of a partial limit, there exists a subsequence $\{x_{n_k}\}_{k=1}^\infty$ such that $\lim_{k \to \infty} x_{n_k} = M$.

By definition of the tail infimum $i_{n_k} = \inf_{j \ge n_k} x_j$ and tail supremum $s_{n_k} = \sup_{j \ge n_k} x_j$, setting $j = n_k$ yields the termwise bounding inequality for every $k \in \mathbb{N}$:
$$
\begin{gather}
i_{n_k} \le x_{n_k} \le s_{n_k} \quad \forall k \in \mathbb{N} \tag{4}
\end{gather}
$$
Because $\{i_{n_k}\}$ and $\{s_{n_k}\}$ are subsequences of the monotonic sequences $\{i_n\}$ and $\{s_n\}$, which converge (or tend in $\mathbb{R} \cup \{-\infty, +\infty\}$) to $l$ and $L$, respectively, it follows that $\lim_{k \to \infty} i_{n_k} = l$ and $\lim_{k \to \infty} s_{n_k} = L$. Passing to the limit as $k \to \infty$ across step 4 via the [[Proof of the Corollary for Limit Inequalities|Corollary for Limit Inequalities]] yields:
$$
\begin{gather}
l = \lim_{k \to \infty} i_{n_k} \le \lim_{k \to \infty} x_{n_k} \le \lim_{k \to \infty} s_{n_k} = L \implies l \le M \le L \tag{5}
\end{gather}
$$
Because $M$ was an arbitrary partial limit of $\{x_n\}$, and both $l$ and $L$ are themselves partial limits of $\{x_n\}$ by Proposition 1, step 5 establishes that the inferior limit $l$ is the smallest of its partial limits, and the superior limit $L$ is the largest of its partial limits.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
