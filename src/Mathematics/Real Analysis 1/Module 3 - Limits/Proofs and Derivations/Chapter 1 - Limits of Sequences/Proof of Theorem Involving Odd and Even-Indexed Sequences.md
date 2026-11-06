---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be a sequence of real numbers, and let $A \in \mathbb{R}$.

**Necessity ($\implies$):**
Assume that the sequence $\{x_n\}$ converges to $A$: $\lim_{n \to \infty} x_n = A$.

By the [[Proof of the Corollary of Partial Limits Proposition|subsequence convergence theorem]], every subsequence of a convergent sequence converges to the identical limit. Because the even-indexed terms $\{x_{2n}\}_{n=1}^\infty$ and odd-indexed terms $\{x_{2n+1}\}_{n=1}^\infty$ are subsequences of $\{x_n\}$ corresponding to the strictly increasing index progressions $n_k = 2k$ and $n_k = 2k + 1$, respectively, it follows immediately that: 
$$
\begin{gather}
\lim_{n \to \infty} x_{2n} = A \quad \text{and} \quad \lim_{n \to \infty} x_{2n+1} = A \tag{1}
\end{gather}
$$

**Sufficiency ($\impliedby$):**
Conversely, assume that both the even-indexed and odd-indexed subsequences converge to $A$:
$$
\begin{gather}
\lim_{n \to \infty} x_{2n} = A \quad \text{and} \quad \lim_{n \to \infty} x_{2n+1} = A \tag{2}
\end{gather}
$$
Let $\varepsilon > 0$ be arbitrary. By the definition of convergence applied to $\{x_{2n}\}$, there exists an index $N_1 \in \mathbb{N}$ such that: 
$$
\begin{gather}
|x_{2k} - A| < \varepsilon \quad \forall k > N_1 \tag{3}
\end{gather}
$$
Similarly, by the definition of convergence applied to $\{x_{2n+1}\}$, there exists an index $N_2 \in \mathbb{N}$ such that:
$$
\begin{gather}
|x_{2k+1} - A| < \varepsilon \quad \forall k > N_2 \tag{4}
\end{gather}
$$
Define the unified threshold index:
$$
\begin{gather}
N := \max(2N_1, 2N_2 + 1) \in \mathbb{N} \tag{5}
\end{gather}
$$
Let $n \in \mathbb{N}$ satisfy $n > N$. By integer division by $2$, the index $n$ is either even or odd:
- If $n$ is even, $n = 2k$ for some $k \in \mathbb{N}$. Because $2k = n > N \ge 2N_1$, it follows that $k > N_1$. Applying step 3 yields $|x_n - A| = |x_{2k} - A| < \varepsilon$.
- If $n$ is odd, $n = 2k + 1$ for some $k \in \mathbb{N} \cup \{0\}$. Because $2k + 1 = n > N \ge 2N_2 + 1$, it follows that $2k > 2N_2 \implies k > N_2$. Applying step 4 yields $|x_n - A| = |x_{2k+1} - A| < \varepsilon$.

In both cases, $|x_n - A| < \varepsilon$ holds for all $n > N$. Because $\varepsilon > 0$ was arbitrary, $\{x_n\}$ converges and $\lim_{n \to \infty} x_n = A$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
