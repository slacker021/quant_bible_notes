---
dg-publish: true
---
Let $X \subset \mathbb{R}$ be a non-empty set of real numbers that is bounded from below. By definition of a lower bound, there exists a real number $m \in \mathbb{R}$ such that $m \le x$ for all $x \in X$. To deduce the existence and uniqueness of the greatest lower bound from the foundational order and completeness principles already established, consider the set $-X$ defined as the reflection of $X$ across the origin:
$$
-X := \{ -x \in \mathbb{R} \mid x \in X \} \tag{1}
$$
Because $X$ is non-empty by hypothesis, there exists at least one element $x_0 \in X$, which ensures that its additive inverse $-x_0$ belongs to $-X$, proving that the reflected set $-X$ is non-empty. Furthermore, because $m$ is a lower bound of $X$, the inequality $m \le x$ holds for every element $x \in X$. Multiplying this relation by the negative unit $-1$ via the compatibility axioms of an ordered field reverses the inequality, yielding
$$
-x \le -m \quad \forall x \in X \tag{2}
$$
Since every element of $-X$ is of the form $-x$ for some $x \in X$, step 2 demonstrates that the real scalar $-m$ serves as an upper bound for the reflected set $-X$. Consequently, $-X$ is a non-empty subset of real numbers that is bounded from above.

The Least Upper Bound Principle guarantees that every non-empty set of real numbers that is bounded from above possesses a unique least upper bound in $\mathbb{R}$. Therefore, the set $-X$ admits a well-defined supremum, which shall be denoted by $s$:
$$
s := \sup(-X) \tag{3}
$$
Now consider the candidate value $i \in \mathbb{R}$ defined as the additive inverse of this supremum:
$$
i := -s = -\sup(-X) \tag{4}
$$
To establish that $i$ is indeed the greatest lower bound of the original set $X$, it must be shown that $i$ is a lower bound of $X$, that $i$ dominates every other lower bound of $X$, and that this bound is unique.

To demonstrate that $i$ is a lower bound of $X$, observe that $s = \sup(-X)$ is, by definition, an upper bound for the reflected set $-X$. As an upper bound, $s$ is greater than or equal to every element in $-X$, which implies that
$$
-x \le s \quad \forall x \in X \tag{5}
$$
Multiplying both sides of the inequality in step 5 by $-1$ inverts the direction of the inequality, producing
$$
-s \le x \quad \forall x \in X \tag{6}
$$
Substituting the identity $i = -s$ into step 6 gives $i \le x$ for all $x \in X$, confirming that $i$ is a valid lower bound of the set $X$.

To show that $i$ is the greatest lower bound, let $i' \in \mathbb{R}$ be an arbitrary lower bound of $X$. By definition, $i'$ satisfies $i' \le x$ for all $x \in X$. Multiplying this inequality by $-1$ produces
$$
-x \le -i' \quad \forall x \in X \tag{7}
$$
Step 7 demonstrates that the number $-i'$ is greater than or equal to every element in $-X$, which means that $-i'$ is an upper bound of $-X$. Because $s = \sup(-X)$ is the least upper bound of $-X$, the scalar $s$ must be less than or equal to every upper bound of $-X$. Consequently, one obtains
$$
s \le -i' \tag{8}
$$
Multiplying step 8 by $-1$ reverses the inequality once more, yielding
$$
i' \le -s \tag{9}
$$
Because $i = -s$, step 9 directly establishes that $i' \le i$. This confirms that no lower bound of $X$ can strictly exceed $i$, proving that $i$ is the greatest lower bound of $X$, denoted $\inf X$.

Finally, to verify uniqueness, suppose that both $i_{1}$ and $i_{2}$ are greatest lower bounds of $X$. Because $i_{1}$ is a greatest lower bound and $i_{2}$ is a lower bound, the maximal property of the infimum requires that $i_{2} \le i_{1}$. Reversing their roles, because $i_{2}$ is a greatest lower bound and $i_{1}$ is a lower bound, it follows identically that $i_{1} \le i_{2}$. Combining these simultaneous inequalities via the Antisymmetry Axiom of the order relation yields
$$
(i_{1} \le i_{2}) \wedge (i_{2} \le i_{1}) \implies i_{1} = i_{2} \tag{10}
$$
Therefore, the greatest lower bound of $X$ is unique, which completes the derivation.
$$
\textbf{Q.E.D}
$$