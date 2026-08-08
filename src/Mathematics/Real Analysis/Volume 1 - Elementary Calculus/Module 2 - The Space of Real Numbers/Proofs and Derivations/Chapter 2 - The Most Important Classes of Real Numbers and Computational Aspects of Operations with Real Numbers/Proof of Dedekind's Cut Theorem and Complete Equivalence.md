---
dg-publish: true
---
Let $(\mathbb{F}, +, \cdot, \le)$ be a linearly ordered field. The following propositions establish the logical equivalence between the Least Upper Bound Axiom and Dedekind's Cut Principle.

--------------------------------------------------------------------------------
# Proposition 1
Assume that the Least Upper Bound Axiom holds in $\mathbb{F}$. Let $(X, Y)$ be an arbitrary Dedekind cut of $\mathbb{F}$, satisfying: 
$$
X \cup Y = \mathbb{F}, \quad X \cap Y = \emptyset, \quad X \ne \emptyset, \quad Y \ne \emptyset \tag{1}
$$
$$
\forall x \in X, \, \forall y \in Y, \quad x \le y \tag{2}
$$
Let $y_0 \in Y$ be an arbitrary element. By step 2, $x \le y_0$ for all $x \in X$, which establishes that $X$ is a non-empty subset of $\mathbb{F}$ bounded above by $y_0$. 

By the Least Upper Bound Axiom, $X$ possesses a unique supremum in $\mathbb{F}$, denoted by $c := \sup X$. By the defining properties of the supremum: 
$$
\forall x \in X, \quad x \le c \tag{3}
$$
Furthermore, because every $y \in Y$ serves as an upper bound for $X$ by step 2, and $c$ is the least upper bound:
$$
\forall y \in Y, \quad c \le y \tag{4}
$$
Combining step 3 and step 4 establishes that $x \le c \le y$ for all $x \in X$ and all $y \in Y$. Because $X \cup Y = \mathbb{F}$ and $X \cap Y = \emptyset$, the cut element $c$ belongs to exactly one of the two sets:
* If $c \in X$, then step 3 confirms that $c = \max X$.
* If $c \in Y$, then step 4 confirms that $c = \min Y$.

To verify uniqueness, suppose $c_1, c_2 \in \mathbb{F}$ both satisfy $x \le c_i \le y$ for all $x \in X$ and $y \in Y$, with $c_1 < c_2$. The midpoint:
$$
m := \frac{c_1 + c_2}{2} \tag{5}
$$
satisfies $c_1 < m < c_2$. Because $m > c_1 \ge x$ for all $x \in X$, $m \notin X$. Concurrently, because $m < c_2 \le y$ for all $y \in Y$, $m \notin Y$. Consequently, $m \notin X \cup Y = \mathbb{F}$, which contradicts the totality of the field. Therefore, $c_1 = c_2$, establishing the existence of a unique cut element.

--------------------------------------------------------------------------------
# Proposition 2
Assume that Dedekind's Cut Principle holds in $\mathbb{F}$. Let $A \subset \mathbb{F}$ be an arbitrary non-empty subset bounded above by some majorant $b_0 \in \mathbb{F}$. 

Define $Y \subset \mathbb{F}$ as the set of all strict upper bounds of $A$, and define $X$ as its relative complement:
$$
Y := \{ y \in \mathbb{F} \mid \forall a \in A, \, a < y \} \tag{6}
$$
$$
X := \mathbb{F} \setminus Y = \{ x \in \mathbb{F} \mid \exists a \in A \text{ such that } x \le a \} \tag{7}
$$

### Verification of Dedekind Cut Conditions
1. **Non-emptiness:** Because $A \ne \emptyset$, choosing $a_0 \in A$ gives $a_0 \le a_0$, so $a_0 \in X$, proving $X \ne \emptyset$. Because $b_0$ is an upper bound of $A$, $a \le b_0 < b_0 + 1$ for all $a \in A$, ensuring $(b_0 + 1) \in Y$, so $Y \ne \emptyset$.
2. **Disjoint Exhaustive Partition:** By construction, $X \cup Y = \mathbb{F}$ and $X \cap Y = \emptyset$.
3. **Order Separation:** For any $x \in X$ and $y \in Y$, there exists $a \in A$ such that $x \le a$. Because $y \in Y$, $a < y$. By transitivity, $x < y$.

### Supremum Identification
By Dedekind's Cut Principle, there exists a unique element $c \in \mathbb{F}$ such that:
$$
x \le c \le y \quad \forall x \in X, \, \forall y \in Y \tag{8}
$$
Because $A \subseteq X$, step 8 establishes that $a \le c$ for all $a \in A$, confirming that $c$ is an upper bound for $A$. 

Now let $u \in \mathbb{F}$ be an arbitrary upper bound of $A$. For any $\varepsilon > 0$, the element $u + \varepsilon$ satisfies $a \le u < u + \varepsilon$ for all $a \in A$, which implies $(u + \varepsilon) \in Y$. By step 8: 
$$
c \le u + \varepsilon \quad \forall \varepsilon > 0 \tag{9}
$$
If $c > u$, setting $\varepsilon = \frac{c - u}{2} > 0$ would require $c \le u + \frac{c - u}{2} = \frac{c + u}{2} < c$, producing a contradiction. Therefore, $c \le u$, confirming that $c$ is the least upper bound of $A$. Thus, $c = \sup A$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
