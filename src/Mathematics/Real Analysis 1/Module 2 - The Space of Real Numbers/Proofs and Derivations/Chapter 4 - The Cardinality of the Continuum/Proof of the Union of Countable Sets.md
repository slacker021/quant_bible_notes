---
dg-publish: true
---
Let $\{A_i\}_{i \in \mathcal{I}}$ be a non-empty finite or countable family of sets, where each set $A_i$ is at most countable. If every set $A_i = \emptyset$, then the union $U := \bigcup_{i \in \mathcal{I}} A_i = \emptyset$, which is finite and therefore at most countable. Furthermore, omitting any empty sets from the family leaves the union unchanged. It therefore suffices to assume that each $A_i$ is non-empty.

Consider first a countably infinite family of non-empty sets $\{A_i\}_{i \in \mathbb{N}}$, where each $A_i$ is either finite or countably infinite. The elements of each set $A_i$ can be indexed as an infinite sequence $a_{i,1}, a_{i,2}, a_{i,3}, \dots$ (if a particular set $A_i$ is finite with $m_i$ elements, the sequence is extended by repeating the terminal element: $a_{i,j} := a_{i,m_i}$ for all $j > m_i$). The elements of the union $U := \bigcup_{i=1}^\infty A_i$ can then be arranged into an infinite two-dimensional array in which the row index $i \in \mathbb{N}$ identifies the set $A_i$ and the column index $j \in \mathbb{N}$ identifies the position within that sequence:
$$
\begin{gather}
A_1 : \quad a_{1,1}, \quad a_{1,2}, \quad a_{1,3}, \quad a_{1,4}, \quad \dots \\[2mm]
A_2 : \quad a_{2,1}, \quad a_{2,2}, \quad a_{2,3}, \quad a_{2,4}, \quad \dots \\[2mm]
A_3 : \quad a_{3,1}, \quad a_{3,2}, \quad a_{3,3}, \quad a_{3,4}, \quad \dots \\[2mm]
\vdots \tag{1}
\end{gather}
$$
To enumerate all entries of the array in step 1 sequentially, Cantor's zig-zag (or pairing) enumeration is applied by traversing the grid along its finite anti-diagonals. For each entry $a_{i,j}$, the sum of its indices is a natural number $k := i + j \ge 2$. For any fixed sum $k \in \{2, 3, 4, \dots\}$, there are exactly $k - 1$ ordered pairs $(i, j) \in \mathbb{N} \times \mathbb{N}$ satisfying $i + j = k$, which are ordered by decreasing row index $i = k - 1, k - 2, \dots, 1$:
- $k = 2$: $a_{1,1}$
- $k = 3$: $a_{2,1}, \ a_{1,2}$
- $k = 4$: $a_{3,1}, \ a_{2,2}, \ a_{1,3}$
- $k = 5$: $a_{4,1}, \ a_{3,2}, \ a_{2,3}, \ a_{1,4}$

Concatenating these finite anti-diagonals for $k = 2, 3, 4, \dots$ produces a single linear sequence $y_1, y_2, y_3, \dots$ containing every element of the array:
$$
\begin{gather}
(y_n)_{n \in \mathbb{N}} = \left(a_{1,1}, \ a_{2,1}, \ a_{1,2}, \ a_{3,1}, \ a_{2,2}, \ a_{1,3}, \ a_{4,1}, \ \dots\right) \tag{2}
\end{gather}
$$
Explicitly, because the anti-diagonals prior to $k = i + j$ contain $1 + 2 + \dots + (i + j - 2) = \frac{(i + j - 2)(i + j - 1)}{2}$ entries, each pair $(i, j) \in \mathbb{N} \times \mathbb{N}$ appears at the unique position $n = \pi(i, j) := \frac{(i + j - 2)(i + j - 1)}{2} + j \in \mathbb{N}$. Thus, the mapping $\phi: \mathbb{N} \to U$ defined by $\phi(n) := y_n$ is surjective onto $U$.

Because the sets $A_i$ need not be mutually disjoint (and finite sets $A_i$ possess repeated tail entries), an element of $U$ may appear multiple times in the sequence of step 2. To eliminate duplicates, associate to each element $u \in U$ the minimal index at which $u$ first appears in the sequence $(y_n)_{n \in \mathbb{N}}$:
$$
\begin{gather}
\iota(u) := \min \{ n \in \mathbb{N} \mid \phi(n) = u \} \tag{3}
\end{gather}
$$
which is well-defined by the surjectivity of $\phi$ and the [[Proof of the Properties of Natural Numbers|Well-Ordering Principle of the Natural Numbers]]. If $\iota(u_1) = \iota(u_2) = n$, then $u_1 = \phi(n) = u_2$, establishing that $\iota: U \to \mathbb{N}$ is an injective mapping that places $U$ in bijective correspondence with the subset $S := \iota(U) \subset \mathbb{N}$. By the [[Proof of the Subsets of Countable Sets|Proposition on Subsets of Countable Sets]], $S \subset \mathbb{N}$ is at most countable, and therefore $U$ is at most countable.

Finally, if the family is finite, say $\{A_1, A_2, \dots, A_m\}$, defining $A_i := A_m$ for all $i > m$ reduces the finite union $\bigcup_{i=1}^m A_i = \bigcup_{i=1}^\infty A_i$ directly to the countable family case established above. Furthermore, if at least one set $A_{i_0}$ in the family is countably infinite, then the inclusion $A_{i_0} \subset U$ dictates that $U$ cannot be finite; because $U$ is at most countable and infinite, $U$ is a countable set.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
