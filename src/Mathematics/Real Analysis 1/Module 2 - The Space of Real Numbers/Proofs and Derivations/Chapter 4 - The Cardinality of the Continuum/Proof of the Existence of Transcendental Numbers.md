---
dg-publish: true
---
Let $\mathbb{A} \subset \mathbb{R}$ denote the set of all real algebraic numbers, and let $\mathbb{T} := \mathbb{R} \setminus \mathbb{A}$ denote the set of real transcendental numbers. By definition, $\mathbb{A}$ and $\mathbb{T}$ form a disjoint partition of the real continuum:
$$
\begin{gather}
\mathbb{R} = \mathbb{A} \cup \mathbb{T}, \qquad \mathbb{A} \cap \mathbb{T} = \emptyset \tag{1}
\end{gather}
$$
By the [[Proof of the Countability of the Algebraic Numbers|Proposition on the Countability of the Algebraic Numbers]], the set $\mathbb{A}$ is countable. If $\mathbb{T}$ were at most countable, then step 1 would express $\mathbb{R}$ as the union of two at most countable sets, forcing $\mathbb{R}$ to be countable by the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]]. This directly contradicts the [[Proof of the Uncountability of the Real Numbers|Theorem on the Uncountability of the Real Numbers]]. Thus, $\mathbb{T}$ is uncountable (and in particular non-empty).

Furthermore, because $\mathbb{T}$ is uncountable, it is infinite and therefore contains a countably infinite subset $S = \{t_1, t_2, t_3, \dots\} \subset \mathbb{T}$. Enumerating the countable set of algebraic numbers as $\mathbb{A} = \{a_1, a_2, a_3, \dots\}$ allows the construction of a mapping $h: \mathbb{R} \to \mathbb{T}$ defined by:
$$
\begin{gather}
h(x) := \begin{cases}
t_{2n - 1} & \text{if } x = a_n \in \mathbb{A} \ \ (n \in \mathbb{N}) \\[2mm]
t_{2n} & \text{if } x = t_n \in S \ \ (n \in \mathbb{N}) \\[2mm]
x & \text{if } x \in \mathbb{T} \setminus S
\end{cases} \tag{2}
\end{gather}
$$
Because $\mathbb{A}$, $S$, and $\mathbb{T} \setminus S$ form a partition of $\mathbb{R}$, and their images $\{t_{2n-1} \mid n \in \mathbb{N}\}$, $\{t_{2n} \mid n \in \mathbb{N}\}$, and $\mathbb{T} \setminus S$ form a partition of $\mathbb{T}$ onto which each branch of step 2 is bijective, $h: \mathbb{R} \to \mathbb{T}$ is a bijection. Therefore, the set of real transcendental numbers $\mathbb{T}$ has the cardinality of the continuum $\mathfrak{c}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
