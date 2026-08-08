---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be an arbitrary sequence of real numbers. By the Law of the Excluded Middle, $\{x_n\}$ is either bounded or unbounded in $\mathbb{R}$.

**Case 1 (Bounded Sequences):**
Suppose that $\{x_n\}$ is bounded. By the [[Proof of the Bolzano-Weierstrass Lemma|Bolzano-Weierstrass Lemma]], every bounded sequence of real numbers contains a convergent subsequence $\{x_{n_k}\}_{k=1}^\infty$, which immediately establishes the claim.

**Case 2 (Unbounded Sequences):**
Suppose that $\{x_n\}$ is unbounded. By definition of boundedness, the sequence must fail to be bounded above, fail to be bounded below, or fail both:

**Sub-Case 2a ($\{x_n\}$ is unbounded above):** Because $\{x_n\}$ is not bounded above, for every real constant $M \in \mathbb{R}$, there exists at least one index $n \in \mathbb{N}$ such that $x_n > M$. Construct a subsequence $\{x_{n_k}\}$ tending to $+\infty$ inductively as follows:
1. For $k = 1$, setting $M_0 := 1$ guarantees the existence of an index $n_1 \in \mathbb{N}$ such that $x_{n_1} > 1$.
2. Suppose indices $n_1 < n_2 < \dots < n_k$ have been selected such that $x_{n_j} > j$ for all $1 \le j \le k$. Define the real constant:
$$
\begin{gather}
M_k := \max(x_1, x_2, \dots, x_{n_k}, k + 1) \tag{1}
\end{gather}
$$
Because $\{x_n\}$ is unbounded above, $M_k$ is not an upper bound for $\{x_n\}$. Therefore, there exists an index $n_{k+1} \in \mathbb{N}$ such that $x_{n_{k+1}} > M_k$. By definition of $M_k$ in step 1, $x_j \le M_k$ for all $1 \le j \le n_k$, which forces $n_{k+1} > n_k$ and simultaneously guarantees that
$$
\begin{gather}
x_{n_{k+1}} > M_k \ge k + 1 \tag{2}
\end{gather}
$$
This inductive construction produces a strictly increasing sequence of indices $n_1 < n_2 < \dots < n_k < \dots$ whose corresponding subsequence satisfies $x_{n_k} > k$ for all $k \in \mathbb{N}$. For any arbitrary constant $c \in \mathbb{R}$, choosing an integer $K \in \mathbb{N}$ via the [[Proof of Archimedian Corollaries|Principle of Archimedes]] such that $K > c$ ensures that $x_{n_k} > k > K > c$ for all $k > K$. Thus, $x_{n_k} \to +\infty$ (and consequently $x_{n_k} \to \infty$).

**Sub-Case 2b ($\{x_n\}$ is unbounded below):** By symmetric reasoning, for every real constant $m \in \mathbb{R}$, there exists at least one index $n \in \mathbb{N}$ such that $x_n < m$. Choose $n_1 \in \mathbb{N}$ such that $x_{n_1} < -1$. Given $n_1 < n_2 < \dots < n_k$, define the real constant:
$$
\begin{gather}
m_k := \min(x_1, x_2, \dots, x_{n_k}, -(k + 1)) \tag{3}
\end{gather}
$$
Because $\{x_n\}$ is unbounded below, there exists an index $n_{k+1} \in \mathbb{N}$ such that $x_{n_{k+1}} < m_k$. Because $x_j \ge m_k$ for all $1 \le j \le n_k$, it follows that $n_{k+1} > n_k$ and $x_{n_{k+1}} < -(k + 1)$. This construction produces a subsequence satisfying $x_{n_k} < -k$ and $|x_{n_k}| > k$ for all $k \in \mathbb{N}$, which proves that $x_{n_k} \to -\infty$ (and consequently $x_{n_k} \to \infty$).

In all cases, from any sequence of real numbers one can extract either a convergent subsequence or a subsequence that tends to infinity.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
