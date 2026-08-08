---
dg-publish: true
---
Let $X \subset \mathbb{R}$ be a non-empty set of real numbers that is bounded above.
# Existence
Because $X$ is bounded above, there exists at least one majorant $M \in \mathbb{R}$ such that $x \le M$ for all $x \in X$. Define the set $Y \subset \mathbb{R}$ as the collection of all upper bounds of $X$:
$$
Y := \{ y \in \mathbb{R} \mid \forall x \in X, \, x \le y \} \tag{1}
$$
Because $M \in Y$, the set $Y$ is non-empty. Furthermore, by the defining condition of $Y$, every element of $X$ is less than or equal to every element of $Y$:
$$
\forall x \in X, \, \forall y \in Y, \quad x \le y \tag{2}
$$
Because $X$ and $Y$ are non-empty subsets of $\mathbb{R}$ satisfying the separation condition in step 2, the Axiom of Completeness (Dedekind Continuity) guarantees the existence of a real scalar $c \in \mathbb{R}$ such that:
$$
x \le c \le y \quad \forall x \in X, \, \forall y \in Y \tag{3}
$$
Evaluating the properties of this separating element $c$:
1. The inequality $x \le c$ holds for all $x \in X$, which establishes that $c$ is an upper bound of $X$. Consequently, $c \in Y$.
2. The inequality $c \le y$ holds for all $y \in Y$, which establishes that $c$ is less than or equal to every upper bound of $X$.

Equivalently, for any candidate scalar $s' < c$, the condition $c \le y$ for all $y \in Y$ prevents $s'$ from belonging to $Y$. Because $s' \notin Y$, there must exist at least one element $x' \in X$ such that $s' < x'$. 

Therefore, $c$ satisfies the two defining conditions of the least upper bound:
$$
(c = \sup X) \iff (\forall x \in X, \, x \le c) \wedge (\forall s' < c, \, \exists x' \in X \text{ such that } s' < x') \tag{4}
$$
Thus, a least upper bound exists in $\mathbb{R}$.

# Uniqueness
Suppose that $s_1, s_2 \in \mathbb{R}$ are both least upper bounds of $X$. 

Because $s_1$ is a least upper bound and $s_2$ is an upper bound of $X$, the definition of the supremum requires that:
$$
s_1 \le s_2 \tag{5}
$$
Reversing their roles, because $s_2$ is a least upper bound and $s_1$ is an upper bound of $X$, it follows identically that:
$$
s_2 \le s_1 \tag{6}
$$
Combining step 5 and step 6 via the Antisymmetry Axiom of the order relation:
$$
(s_1 \le s_2) \wedge (s_2 \le s_1) \implies s_1 = s_2 \tag{7}
$$
Therefore, the least upper bound of a non-empty set bounded above is unique, denoted $\sup X = \min Y$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
