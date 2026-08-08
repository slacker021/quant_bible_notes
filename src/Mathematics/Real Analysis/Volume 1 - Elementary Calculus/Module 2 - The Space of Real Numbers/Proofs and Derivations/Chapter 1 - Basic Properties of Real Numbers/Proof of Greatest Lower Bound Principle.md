---
dg-publish: true
---
Let $X \subset \mathbb{R}$ be a non-empty set of real numbers that is bounded below.

# Existence
Because $X$ is bounded below, there exists a minorant $m \in \mathbb{R}$ such that: 
$$
m \le x \quad \forall x \in X \tag{1}
$$
Consider the reflected set $-X \subset \mathbb{R}$ defined by: 
$$
-X := \{ -x \in \mathbb{R} \mid x \in X \} \tag{2}
$$
Because $X$ is non-empty, there exists at least one element $x_0 \in X$, which ensures that $-x_0 \in -X$, establishing that $-X$ is non-empty. 

Multiplying the inequality in step 1 by $-1$ reverses the inequality:
$$
-x \le -m \quad \forall x \in X \tag{3}
$$
Because every element of $-X$ is of the form $-x$ for some $x \in X$, step 3 demonstrates that the scalar $-m$ serves as an upper bound for $-X$. Consequently, $-X$ is a non-empty subset of real numbers that is bounded above.

By the Least Upper Bound Principle, the set $-X$ possesses a unique least upper bound in $\mathbb{R}$, denoted by $s$:
$$
s := \sup(-X) \tag{4}
$$
Define the candidate element $i \in \mathbb{R}$ as the negative of this supremum:
$$
i := -s = -\sup(-X) \tag{5}
$$
To demonstrate that $i$ is a lower bound of $X$, observe that $s = \sup(-X)$ is an upper bound for $-X$:
$$
-x \le s \quad \forall x \in X \tag{6}
$$
Multiplying both sides of step 6 by $-1$ inverts the inequality:
$$
-s \le x \quad \forall x \in X \tag{7}
$$
Substituting $i = -s$ into step 7 demonstrates that $i \le x$ for all $x \in X$, confirming that $i$ is a valid lower bound of $X$.

To demonstrate that $i$ is the greatest lower bound, let $i' \in \mathbb{R}$ be an arbitrary lower bound of $X$, such that $i' \le x$ for all $x \in X$. Multiplying this condition by $-1$ yields: 
$$
-x \le -i' \quad \forall x \in X \tag{8}
$$
Step 8 demonstrates that $-i'$ is an upper bound for the reflected set $-X$. Because $s = \sup(-X)$ is the least upper bound of $-X$, the scalar $s$ must be less than or equal to every upper bound of $-X$:
$$
s \le -i' \tag{9}
$$
Multiplying step 9 by $-1$ reverses the inequality:
$$
i' \le -s \tag{10}
$$
Because $i = -s$, step 10 establishes that $i' \le i$. Consequently, no lower bound of $X$ can strictly exceed $i$, confirming that $i = \inf X$.

# Uniqueness
Suppose that $i_1, i_2 \in \mathbb{R}$ are both greatest lower bounds of $X$. 

Because $i_1$ is a greatest lower bound and $i_2$ is a lower bound of $X$, the definition of the infimum requires that:
$$
i_2 \le i_1 \tag{11}
$$
Reversing their roles, because $i_2$ is a greatest lower bound and $i_1$ is a lower bound of $X$, it follows identically that:
$$
i_1 \le i_2 \tag{12}
$$
Combining step 11 and step 12 via the Antisymmetry Axiom of the order relation:
$$
(i_1 \le i_2) \wedge (i_2 \le i_1) \implies i_1 = i_2 \tag{13}
$$
Therefore, the greatest lower bound of a non-empty set bounded below is unique, denoted $\inf X = -\sup(-X)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
