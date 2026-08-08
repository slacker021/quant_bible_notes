---
dg-publish: true
---
Let $E$ be an arbitrary set, and let $\emptyset$ denote the empty set.

---
# Direct Method (Vacuous Truth)
By the Axiom of Extensionality and the formal definition of the empty set, $\emptyset$ contains no elements: 
$$
\begin{gather}
\forall x \, (x \notin \emptyset) \tag{1}
\end{gather}
$$
By the definition of subset inclusion, a set $A$ is a subset of a set $B$, denoted $A \subseteq B$, if and only if every element belonging to $A$ also belongs to $B$:
$$
\begin{gather}
A \subseteq B \iff \forall x \, (x \in A \implies x \in B) \tag{2}
\end{gather}
$$
Assigning $A = \emptyset$ and $B = E$ into step 2 yields the conditional requirement: 
$$
\begin{gather}
\emptyset \subseteq E \iff \forall x \, (x \in \emptyset \implies x \in E) \tag{3}
\end{gather}
$$
Let $x$ be an arbitrary object in the universal domain. In formal classical logic, a conditional statement $P \implies Q$ evaluates to true whenever the antecedent $P$ is false, regardless of the truth value of the consequent $Q$. By step 1, the antecedent $x \in \emptyset$ is false for every object $x$. Consequently, the implication: 
$$
\begin{gather}
x \in \emptyset \implies x \in E \tag{4}
\end{gather}
$$
is vacuously true for all $x$. Because the condition in step 3 is satisfied universally, it follows that: 
$$
\begin{gather}
\emptyset \subseteq E \tag{5}
\end{gather}
$$

---
# Indirect Method (Proof by Contradiction)
Assume the negation of the conclusion:
$$
\begin{gather}
\emptyset \not\subseteq E \tag{6}
\end{gather}
$$
By the logical negation of the subset definition in step 2, step 6 requires the existence of at least one witness object $x_0$ such that: 
$$
\begin{gather}
x_0 \in \emptyset \quad \wedge \quad x_0 \notin E \tag{7}
\end{gather}
$$
However, asserting that $x_0 \in \emptyset$ directly contradicts step 1, which establishes that no object can belong to $\emptyset$:
$$
\begin{gather}
\forall x \, (x \notin \emptyset) \implies x_0 \notin \emptyset \tag{8}
\end{gather}
$$
Because the hypothesis $\emptyset \not\subseteq E$ produces a direct logical contradiction ($x_0 \in \emptyset \wedge x_0 \notin \emptyset$), the hypothesis is false. Therefore, the empty set is a subset of the arbitrary set $E$:
$$
\begin{gather}
\emptyset \subseteq E \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
