---
dg-publish: true
---
Let $I_1 \supseteq I_2 \supseteq \dots \supseteq I_n \supseteq \dots$ be a sequence of nested closed intervals, where $I_n = [a_n, b_n]$ for each $n \in \mathbb{N}$. For any two intervals $I_m = [a_m, b_m]$ and $I_n = [a_n, b_n]$ in the sequence, their endpoints satisfy:
$$
\begin{gather}
a_m \le b_n \quad \forall m, n \in \mathbb{N} \tag{1}
\end{gather}
$$
To verify step 1, suppose to the contrary that $b_n < a_m$ for some indices $m, n \in \mathbb{N}$. Then $a_n \le b_n < a_m \le b_m$, which implies that the intervals $I_n = [a_n, b_n]$ and $I_m = [a_m, b_m]$ are mutually disjoint ($I_m \cap I_n = \emptyset$). However, setting $k := \max\{m, n\}$, the nesting property dictates that $I_k \subseteq I_m$ and $I_k \subseteq I_n$, so $I_k \subseteq I_m \cap I_n$ cannot be empty, yielding a contradiction.

Now define the two non-empty numerical sets consisting of all left endpoints and all right endpoints of the sequence:
$$
\begin{gather}
A := \{a_m \in \mathbb{R} \mid m \in \mathbb{N}\} \quad \text{and} \quad B := \{b_n \in \mathbb{R} \mid n \in \mathbb{N}\} \tag{2}
\end{gather}
$$
By step 1, every element $a_m \in A$ and every element $b_n \in B$ satisfies $a_m \le b_n$. Thus, $A$ and $B$ satisfy the hypotheses of the Axiom of Completeness (see [[Chapter 1 - Basic Properties of Real Numbers]]), which guarantees the existence of at least one real number $c \in \mathbb{R}$ such that:
$$
\begin{gather}
a_m \le c \le b_n \quad \forall m, n \in \mathbb{N} \tag{3}
\end{gather}
$$
In particular, setting $m = n$ in step 3 yields $a_n \le c \le b_n$, meaning $c \in [a_n, b_n] = I_n$ for all $n \in \mathbb{N}$. Consequently, the intersection of the nested sequence is non-empty:
$$
\begin{gather}
c \in \bigcap_{n=1}^\infty I_n \implies \bigcap_{n=1}^\infty I_n \neq \emptyset \tag{4}
\end{gather}
$$
Finally, suppose that for every $\varepsilon > 0$, there exists an interval $I_n$ of length $|I_n| = b_n - a_n < \varepsilon$. Let $c_1, c_2 \in \bigcap_{n=1}^\infty I_n$ be two points belonging to all intervals of the sequence. If $c_1 \ne c_2$ (without loss of generality, suppose $c_1 < c_2$), then for every $n \in \mathbb{N}$:
$$
\begin{gather}
a_n \le c_1 < c_2 \le b_n \implies 0 < c_2 - c_1 \le b_n - a_n = |I_n| \tag{5}
\end{gather}
$$
Choosing $\varepsilon := c_2 - c_1 > 0$, step 5 states that $|I_n| \ge \varepsilon$ for all $n \in \mathbb{N}$, which directly contradicts the hypothesis that there exists an interval $I_n$ with $|I_n| < \varepsilon$. Therefore, $c_1 = c_2$, and the common point $c$ is unique.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
