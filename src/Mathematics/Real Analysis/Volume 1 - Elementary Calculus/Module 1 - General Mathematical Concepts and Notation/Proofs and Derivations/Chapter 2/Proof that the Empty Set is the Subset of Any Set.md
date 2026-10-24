---
dg-publish: true
---
Let $E$ be an arbitrary set, and let $\emptyset$ denote the empty set. By the Axiom of Extensionality and the definition of the empty set, $\emptyset$ contains no elements:
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

Assigning $A = \emptyset$ and $B = E$ yields the conditional proposition:
$$
\begin{gather}
\emptyset \subseteq E \iff \forall x \, (x \in \emptyset \implies x \in E) \tag{3}
\end{gather}
$$

Consider an arbitrary element $x$ in the universal domain. In classical propositional logic, a conditional statement of the form $P \implies Q$ evaluates to true whenever the antecedent $P$ is false, regardless of the truth value of the consequent $Q$. By the defining property in step 1, the predicate $x \in \emptyset$ is false for every object $x$. Consequently, the implication
$$
\begin{gather}
x \in \emptyset \implies x \in E \tag{4}
\end{gather}
$$
is vacuously true for every object $x$.

To corroborate this deduction via proof by contradiction, assume the negation of the conclusion:
$$
\begin{gather}
\emptyset \not\subseteq E \tag{5}
\end{gather}
$$
By the logical negation of the subset definition in step 2, the condition in step 5 requires the existence of at least one witness $x_0$ satisfying:
$$
\begin{gather}
x_0 \in \emptyset \quad \wedge \quad x_0 \notin E \tag{6}
\end{gather}
$$
However, the statement $x_0 \in \emptyset$ directly contradicts step 1, which asserts that no element belongs to $\emptyset$:
$$
\begin{gather}
\neg \exists x_0 \, (x_0 \in \emptyset) \tag{7}
\end{gather}
$$
Because the hypothesis $\emptyset \not\subseteq E$ entails a direct contradiction, the hypothesis is false. Therefore, the empty set is a subset of the arbitrary set $E$:
$$
\begin{gather}
\emptyset \subseteq E \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$