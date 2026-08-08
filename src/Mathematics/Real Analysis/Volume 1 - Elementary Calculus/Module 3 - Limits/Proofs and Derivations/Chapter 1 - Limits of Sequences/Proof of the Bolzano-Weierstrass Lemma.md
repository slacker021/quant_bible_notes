---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be an arbitrary bounded sequence of real numbers. An index $m \in \mathbb{N}$ is defined to be a peak of the sequence if every subsequent term does not exceed $x_m$:
$$
\begin{gather}
\forall n \in \mathbb{N}, \quad (n > m) \implies (x_m \ge x_n) \tag{1}
\end{gather}
$$
The argument proceeds by evaluating two exhaustive cases based on the cardinality of the set of peaks.

**Case 1 (Infinitely Many Peaks):**
Suppose that $\{x_n\}$ possesses infinitely many peaks. Arrange the infinite set of peak indices in strictly increasing order:
$$
\begin{gather}
m_1 < m_2 < m_3 < \dots < m_k < m_{k+1} < \dots \tag{2}
\end{gather}
$$
For each $k \in \mathbb{N}$, because $m_k$ is a peak and $m_{k+1} > m_k$, condition step 1 dictates that $x_{m_k} \ge x_{m_{k+1}}$. Consequently, the extracted subsequence $\{x_{m_k}\}_{k=1}^\infty$ satisfies: 
$$
\begin{gather}
x_{m_1} \ge x_{m_2} \ge x_{m_3} \ge \dots \ge x_{m_k} \ge x_{m_{k+1}} \ge \dots \tag{3}
\end{gather}
$$
Step 3 demonstrates that $\{x_{m_k}\}$ is a monotonically nonincreasing subsequence. Because the parent sequence $\{x_n\}$ is bounded, $\{x_{m_k}\}$ is bounded below. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], $\{x_{m_k}\}$ converges to a finite real limit.

**Case 2 (Finitely Many Peaks):**
Suppose instead that $\{x_n\}$ possesses only finitely many peaks. Let $N \in \mathbb{N} \cup \{0\}$ denote the largest peak index, setting $N := 0$ if the sequence contains no peaks. Consequently, no index $n > N$ is a peak.

Select the initial index $n_1 := N + 1 > N$. Because $n_1$ is not a peak, the logical negation of step 1 guarantees the existence of an index $n_2 > n_1$ such that $x_{n_2} > x_{n_1}$. Because $n_2 > n_1 > N$, the index $n_2$ is likewise not a peak, ensuring the existence of an index $n_3 > n_2$ such that $x_{n_3} > x_{n_2}$. Proceeding inductively, given an index $n_k > N$, the fact that $n_k$ is not a peak guarantees the existence of an index $n_{k+1} > n_k$ satisfying $x_{n_{k+1}} > x_{n_k}$.

This inductive construction yields a strictly increasing sequence of indices $n_1 < n_2 < n_3 < \dots < n_k < \dots$ whose corresponding subsequence terms satisfy: 
$$
\begin{gather}
x_{n_1} < x_{n_2} < x_{n_3} < \dots < x_{n_k} < x_{n_{k+1}} < \dots \tag{4}
\end{gather}
$$
Step 4 demonstrates that $\{x_{n_k}\}$ is a strictly increasing (and therefore nondecreasing) subsequence. Because the parent sequence $\{x_n\}$ is bounded, $\{x_{n_k}\}$ is bounded above. By the Weierstrass Theorem on Monotonic Sequences, $\{x_{n_k}\}$ converges to a finite real limit.

In both cases, a convergent subsequence can be extracted from the bounded sequence $\{x_n\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
