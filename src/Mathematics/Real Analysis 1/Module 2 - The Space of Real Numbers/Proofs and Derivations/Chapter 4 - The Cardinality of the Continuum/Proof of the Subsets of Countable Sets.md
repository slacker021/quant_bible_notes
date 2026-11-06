---
dg-publish: true
---
Let $X$ be a countable set and let $A$ be a subset of $X$ ($A \subset X$). If $A = \emptyset$, then $A$ is finite by definition and is therefore at most countable. Assume henceforth that $A$ is non-empty ($A \neq \emptyset$).

Because $X$ is countably infinite, there exists a bijective mapping $f: \mathbb{N} \to X$. This bijection enumerates the elements of $X$ as a sequence of distinct terms $x_1, x_2, \dots, x_n, \dots$, where $x_n := f(n)$ for each $n \in \mathbb{N}$.

Because $A \subset X$ is non-empty and $f$ is surjective onto $X$, the set of indices $I_1 := \{ n \in \mathbb{N} \mid x_n \in A \}$ is a non-empty subset of $\mathbb{N}$. By the [[Proof of the Properties of Natural Numbers|Well-Ordering Principle of the Natural Numbers]], every non-empty subset of $\mathbb{N}$ possesses a unique minimal element. Define $n_1$ to be the smallest natural number such that $x_{n_1} \in A$, and proceed recursively: whenever the set $I_k := \{ n \in \mathbb{N} \mid n > n_{k-1} \text{ and } x_n \in A \}$ is non-empty for $k \ge 2$, define $n_k$ to be its unique minimal element:
$$
\begin{gather}
n_1 := \min \{ n \in \mathbb{N} \mid x_n \in A \} \\[2mm]
n_k := \min \{ n \in \mathbb{N} \mid n > n_{k-1} \text{ and } x_n \in A \} \quad (k \ge 2) \tag{1}
\end{gather}
$$
By step 1, this recursive construction generates a strictly increasing sequence of natural-number indices $n_1 < n_2 < \dots < n_k < \dots$, from which a mapping $g$ into $A$ is defined by setting $g(k) := x_{n_k}$. Observe by mathematical induction on $k$ that $n_k \ge k$ for every index $k$ at which $n_k$ is defined: $n_1 \ge 1$ holds in $\mathbb{N}$, and $n_k > n_{k-1} \ge k - 1$ implies $n_k \ge k$ by the discrete spacing of $\mathbb{N}$. Furthermore, by the minimality of $n_1$ and of each $n_k$ in step 1, no index $m \in \mathbb{N}$ satisfying $m < n_1$ or $n_{j-1} < m < n_j$ can satisfy $x_m \in A$.

There are two mutually exclusive outcomes for this selection process:
1. **The process terminates at some step $k \in \mathbb{N}$:** If the set $I_{k+1} = \{ n \in \mathbb{N} \mid n > n_k \text{ and } x_n \in A \}$ is empty, then no natural number $n > n_k$ satisfies $x_n \in A$. Because no element of $A$ occurs at an index outside $\{n_1, n_2, \dots, n_k\}$ and the original bijection $f$ maps distinct indices to distinct elements, the mapping $g: \{1, 2, \dots, k\} \to A$ given by $g(j) = x_{n_j}$ is a bijection. Thus, $A$ contains exactly $k$ elements and is finite.
2. **The process continues indefinitely:** If $I_k$ is non-empty for every $k \in \mathbb{N}$, the mapping $g: \mathbb{N} \to A$ is defined for all $k \in \mathbb{N}$. For any distinct $i, j \in \mathbb{N}$ with $i < j$, the strict monotonicity of the indices in step 1 ensures $n_i < n_j$; since $f$ is injective, $g(i) = f(n_i) \neq f(n_j) = g(j)$, proving that $g$ is injective. To verify surjectivity, let $a \in A$ be arbitrary. Because $A \subset X$ and $f: \mathbb{N} \to X$ is surjective, there exists $m \in \mathbb{N}$ such that $x_m = a$, meaning $m \in I_1$. The finite set of predecessor indices $\{ j \in I_1 \mid j \le m \}$ contains at most $m$ elements; let $k := |\{ j \in I_1 \mid j \le m \}| \le m$. By the recursive minimality definition in step 1, the construction selects precisely these indices in strictly increasing order, forcing $n_k = m$. Consequently, $g(k) = x_{n_k} = x_m = a$. Thus, $g: \mathbb{N} \to A$ is a bijection, and $A$ is countably infinite.

In either case, the subset $A$ is either finite or countably infinite, establishing that $A$ is at most countable.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
