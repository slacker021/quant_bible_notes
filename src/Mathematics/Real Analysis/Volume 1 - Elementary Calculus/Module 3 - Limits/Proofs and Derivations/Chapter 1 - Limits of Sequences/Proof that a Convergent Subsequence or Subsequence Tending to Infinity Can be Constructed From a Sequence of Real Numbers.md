---
dg-publish: true
---
Let $\{x_n\}$ be an arbitrary sequence of real numbers. By the law of the excluded middle, the sequence $\{x_n\}$ is either bounded or unbounded. The proof is partitioned into these two exhaustive cases.

### Case 1
Suppose $\{x_n\}$ is bounded. By the [[Proof of the Bolzano-Weierstrass Lemma|Bolzano-Weierstrass Lemma]], every bounded sequence of real numbers contains a convergent subsequence $\{x_{n_k}\}$, which immediately satisfies the lemma.

### Case 2
Suppose $\{x_n\}$ is unbounded. By definition of boundedness, a sequence that is not bounded must fail to be bounded above, fail to be bounded below, or both:
- **Sub-Case 2a ($\{x_n\}$ is unbounded above):** By the logical negation of being bounded above, for every real number $M \in \mathbb{R}$, there exists at least one index $n \in \mathbb{N}$ such that $x_n > M$. Construct a subsequence $\{x_{n_k}\}$ tending to $+\infty$ inductively as follows:
  1. For $k = 1$, setting $M_0 := 1$ guarantees the existence of an index $n_1 \in \mathbb{N}$ such that $x_{n_1} > 1$.
  2. Suppose $n_1 < n_2 < \dots < n_k$ have been chosen such that $x_{n_j} > j$ for all $1 \le j \le k$. Define the finite real number:
$$
\begin{gather}
M_k := \max\left(x_1, x_2, \dots, x_{n_k}, \, k + 1\right) \tag{1}
\end{gather}
$$
  Because $\{x_n\}$ is unbounded above, $M_k$ is not an upper bound for $\{x_n\}$, so there exists an index $n_{k+1} \in \mathbb{N}$ such that $x_{n_{k+1}} > M_k$. By definition of $M_k$ in step 1, $x_j \le M_k$ for all $1 \le j \le n_k$, which forces $n_{k+1} > n_k$ and simultaneously guarantees
$$
\begin{gather}
x_{n_{k+1}} > M_k \ge k + 1 \tag{2}
\end{gather}
$$
  This inductive construction produces a subsequence $\{x_{n_k}\}$ satisfying $x_{n_k} > k$ (and hence $|x_{n_k}| > k$) for all $k \in \mathbb{N}$. For any $c \in \mathbb{R}$, choosing $K \in \mathbb{N}$ via the [[Proof of the Principle of Archimedes|Principle of Archimedes]] such that $K > |c|$ ensures that $x_{n_k} > k > K > |c| \ge c$ for all $k > K$. Thus, $x_{n_k} \to +\infty$ (and $x_{n_k} \to \infty$).

- **Sub-Case 2b ($\{x_n\}$ is unbounded below):** By symmetric reasoning, for every real number $m \in \mathbb{R}$, there exists at least one index $n \in \mathbb{N}$ such that $x_n < m$. Choose $n_1 \in \mathbb{N}$ such that $x_{n_1} < -1$, and given $n_1 < \dots < n_k$, define:
$$
\begin{gather}
m_k := \min\left(x_1, x_2, \dots, x_{n_k}, \, -(k + 1)\right) \tag{3}
\end{gather}
$$
  Because $\{x_n\}$ is unbounded below, there exists an index $n_{k+1} \in \mathbb{N}$ such that $x_{n_{k+1}} < m_k$. Since $x_j \ge m_k$ for all $1 \le j \le n_k$, it follows that $n_{k+1} > n_k$ and $x_{n_{k+1}} < -(k + 1)$. Consequently, $x_{n_k} < -k$ and $|x_{n_k}| = -x_{n_k} > k$ for all $k \in \mathbb{N}$, proving that $x_{n_k} \to -\infty$ (and $x_{n_k} \to \infty$).

In all cases, $\{x_n\}$ contains either a convergent subsequence or a subsequence tending to infinity.
$$
\begin{gather}
\textbf{Q.E.D}
\end{gather}
$$
