---
dg-publish: true
---
Let $\mathbb{R}$ denote the set of all real numbers and $\mathbb{Q}$ denote the set of all rational numbers. By definition, the set of irrational numbers is the complement $\mathbb{R} \setminus \mathbb{Q}$, so the real line partitions into the disjoint union:
$$
\begin{gather}
\mathbb{R} = \mathbb{Q} \cup (\mathbb{R} \setminus \mathbb{Q}) \tag{1}
\end{gather}
$$
First, to prove that $\mathbb{R} \setminus \mathbb{Q}$ is uncountable, assume for the sake of contradiction that $\mathbb{R} \setminus \mathbb{Q}$ is at most countable. By the [[Proof of the Countability of the Rational Numbers|Countability of the Rational Numbers]], the set $\mathbb{Q}$ is countable. Under the assumption that $\mathbb{R} \setminus \mathbb{Q}$ is at most countable, step 1 expresses $\mathbb{R}$ as the union of two at most countable sets:
$$
\begin{gather}
(\mathbb{R} \setminus \mathbb{Q} \text{ is at most countable}) \implies (\mathbb{R} \text{ is countable}) \tag{2}
\end{gather}
$$
By the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]], the deduction in step 2 forces $\mathbb{R}$ to be countable. This directly contradicts the uncountability of the continuum established in the [[Proof of the Uncountability of the Real Numbers|Theorem on the Uncountability of the Real Numbers]]. Therefore, the set of irrational numbers $\mathbb{R} \setminus \mathbb{Q}$ is uncountable.

Second, to prove that $\mathbb{R} \setminus \mathbb{Q}$ possesses the exact cardinality of the continuum $\mathfrak{c}$ (that is, $\mathbb{R} \setminus \mathbb{Q} \sim \mathbb{R}$), an explicit bijection $h: \mathbb{R} \to \mathbb{R} \setminus \mathbb{Q}$ is constructed. Because $\mathbb{Q}$ is countable, its elements can be enumerated as a sequence of distinct terms $\mathbb{Q} = \{q_1, q_2, q_3, \dots\}$. Similarly, select a countably infinite sequence of distinct irrational numbers $S := \{s_1, s_2, s_3, \dots\} \subset \mathbb{R} \setminus \mathbb{Q}$; for example, because $\sqrt{2} \in \mathbb{R} \setminus \mathbb{Q}$ (as established in the [[Proof that the Square Root of 2 is Irrational|Irrationality of the Square Root of Two]]), setting $s_n := n\sqrt{2}$ for each $n \in \mathbb{N}$ yields a sequence of distinct irrational numbers (as $n\sqrt{2} \in \mathbb{Q} \implies \sqrt{2} \in \mathbb{Q}$, a contradiction).

Now define the mapping $h: \mathbb{R} \to \mathbb{R} \setminus \mathbb{Q}$ by shifting $\mathbb{Q}$ and $S$ into the odd- and even-indexed terms of $S$, respectively, while leaving all remaining irrational numbers fixed:
$$
\begin{gather}
h(x) := \begin{cases}
s_{2n - 1} & \text{if } x = q_n \in \mathbb{Q} \ \ (n \in \mathbb{N}) \\[2mm]
s_{2n} & \text{if } x = s_n \in S \ \ (n \in \mathbb{N}) \\[2mm]
x & \text{if } x \in (\mathbb{R} \setminus \mathbb{Q}) \setminus S
\end{cases} \tag{3}
\end{gather}
$$
Because $\mathbb{Q}$, $S$, and $(\mathbb{R} \setminus \mathbb{Q}) \setminus S$ form a partition of $\mathbb{R}$, and their images $\{s_{2n-1} \mid n \in \mathbb{N}\}$, $\{s_{2n} \mid n \in \mathbb{N}\}$, and $(\mathbb{R} \setminus \mathbb{Q}) \setminus S$ form a partition of $\mathbb{R} \setminus \mathbb{Q}$ onto which each branch of step 3 is bijective, $h: \mathbb{R} \to \mathbb{R} \setminus \mathbb{Q}$ is a bijection. Thus, $\mathbb{R} \setminus \mathbb{Q}$ is equipotent to $\mathbb{R}$ and has the cardinality of the continuum $\mathfrak{c}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
