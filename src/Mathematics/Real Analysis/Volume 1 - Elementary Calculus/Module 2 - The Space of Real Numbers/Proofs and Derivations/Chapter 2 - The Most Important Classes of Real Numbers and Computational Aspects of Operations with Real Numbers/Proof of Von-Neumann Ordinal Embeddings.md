---
dg-publish: true
---
Let $x, y$ be von Neumann ordinals in Zermelo-Fraenkel set theory (ZF). The successor of an ordinal $x$ is defined as $x^+ := x \cup \{x\}$, and the strict order relation is defined by set membership: $x < y \iff x \in y$.

--------------------------------------------------------------------------------
# Lemma 1
### Injectivity of Successor Mappings
Assume that:
$$
x^+ = y^+ \iff x \cup \{x\} = y \cup \{y\} \tag{1}
$$
Assume for the purpose of contradiction that $x \ne y$. 

Because $x \in x^+$, step 1 requires that $x \in y \cup \{y\}$, which implies:
$$
(x \in y) \lor (x = y) \tag{2}
$$
Because $x \ne y$, step 2 forces $x \in y$. 

By identical symmetric reasoning, because $y \in y^+ = x^+$, $y \in x \cup \{x\}$. Because $y \ne x$, it follows that $y \in x$.

Combining these results yields the mutual membership cycle:
$$
(x \in y) \wedge (y \in x) \tag{3}
$$
Consider the doubleton set formed by pairing:
$$
S := \{x, y\} \tag{4}
$$
The Axiom of Regularity (Axiom of Foundation) dictates that every non-empty set $A$ contains an element $z \in A$ disjoint from $A$ ($A \cap z = \emptyset$). Evaluating the elements of $S$:
* If $z = x$, then $y \in x$ and $y \in S \implies y \in (S \cap x) \ne \emptyset$.
* If $z = y$, then $x \in y$ and $x \in S \implies x \in (S \cap y) \ne \emptyset$.

Thus, no element of $S$ is disjoint from $S$, which contradicts the Axiom of Regularity. Consequently, the hypothesis $x \ne y$ is false, confirming that:
$$
x^+ = y^+ \implies x = y \tag{5}
$$

--------------------------------------------------------------------------------
# Lemma 2
### Immediate Successor Property
Because $x \in x \cup \{x\} = x^+$, the definition of ordinal ordering confirms that:
$$
x < x^+ \tag{6}
$$
Let $z$ be any ordinal satisfying $z < x^+$. By definition, $z \in x^+ = x \cup \{x\}$, which implies:
$$
(z \in x) \lor (z = x) \iff (z < x) \lor (z = x) \tag{7}
$$
Step 7 demonstrates that no ordinal $z$ can satisfy $x < z < x^+$, proving that $x^+$ is the immediate successor of $x$.

### Well-Ordering Principle
Let $X$ be an arbitrary non-empty set of von Neumann ordinals. 

Applying the Axiom of Regularity directly to $X$ guarantees the existence of an element $x_{\min} \in X$ such that:
$$
X \cap x_{\min} = \emptyset \tag{8}
$$
Assume for the purpose of contradiction that there exists an element $x' \in X$ satisfying $x' < x_{\min}$. By the definition of ordinal ordering, $x' < x_{\min} \iff x' \in x_{\min}$. 

Consequently:
$$
(x' \in X) \wedge (x' \in x_{\min}) \implies x' \in (X \cap x_{\min}) \tag{9}
$$
Step 9 contradicts step 8, which established that $X \cap x_{\min} = \emptyset$. 

Because ordinal comparability ensures that for every $x \in X$, either $x_{\min} \le x$ or $x < x_{\min}$, it follows that:
$$
x_{\min} \le x \quad \forall x \in X \tag{10}
$$
Therefore, $x_{\min} = \min X$, establishing that every non-empty set of ordinals possesses a minimal element under set membership.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
