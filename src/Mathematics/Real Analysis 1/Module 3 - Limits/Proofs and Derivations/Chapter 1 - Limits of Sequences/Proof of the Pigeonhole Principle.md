---
dg-publish: true
---
Let $n \in \mathbb{N}$ be a natural number, and suppose that $m \in \mathbb{N}$ objects satisfying $m \ge n + 1$ are distributed among $n$ distinct boxes labeled $1, 2, \dots, n$.

For each box index $i \in \{1, 2, \dots, n\}$, let $k_i \in \mathbb{N} \cup \{0\}$ denote the number of objects placed into the $i$-th box. Because every object is placed into exactly one box, the sum of the occupancies equals the total number of objects:
$$
\begin{gather}
\sum_{i=1}^n k_i = m \ge n + 1 \tag{1}
\end{gather}
$$
Assume, for the sake of contradiction, that no box contains two or more objects. Under this assumption, every box contains at most one object:
$$
\begin{gather}
k_i \le 1 \quad \forall i \in \{1, 2, \dots, n\} \tag{2}
\end{gather}
$$
Summing the inequalities in step 2 across all $n$ boxes via the [[Proof of Consequences of Order with Addition and Multiplication|additive compatibility axioms]] of $\mathbb{R}$ yields an upper bound on $m$:
$$
\begin{gather}
m = \sum_{i=1}^n k_i \le \sum_{i=1}^n 1 = n \tag{3}
\end{gather}
$$
Combining step 1 and step 3 by transitivity requires that: 
$$
\begin{gather}
n + 1 \le m \le n \implies n + 1 \le n \tag{4}
\end{gather}
$$
Adding $-n$ to both sides of step 4 via additive compatibility yields $1 \le 0$. By the [[Proof of Consequences of Order with Addition and Multiplication|order properties of real numbers]], $0 < 1$ holds universally, so $1 \le 0$ violates the Law of Trichotomy.

Therefore, the assumption that every box contains at most one object is false, and at least one box must contain at least two objects.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
