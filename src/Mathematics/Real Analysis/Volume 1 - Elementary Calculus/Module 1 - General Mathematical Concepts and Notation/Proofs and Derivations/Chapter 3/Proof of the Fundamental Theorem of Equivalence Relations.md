---
dg-publish: true
---
# Forward Direction
Assume that $(X = \emptyset) \lor (Y = \emptyset)$. To establish that $X \times Y = \emptyset$, proceed by contradiction. Assume that: 
$$
\begin{gather}
X \times Y \neq \emptyset \tag{1}
\end{gather}
$$
By the definition of a non-empty set, the assumption in step 1 guarantees the existence of at least one element $z_0 \in X \times Y$. By the definition of the Cartesian product, $z_0$ is an ordered pair $(x_0, y_0)$ satisfying: 
$$
\begin{gather}
x_0 \in X \quad \wedge \quad y_0 \in Y \tag{2}
\end{gather}
$$
The existence of $x_0 \in X$ establishes that $X \neq \emptyset$. Similarly, the existence of $y_0 \in Y$ establishes that $Y \neq \emptyset$. Combining these two deductions yields: 
$$
\begin{gather}
(X \neq \emptyset) \wedge (Y \neq \emptyset) \tag{3}
\end{gather}
$$
By De Morgan's laws of propositional logic, the statement in step 3 is logically equivalent to
$$
\begin{gather}
\neg((X = \emptyset) \lor (Y = \emptyset)) \tag{4}
\end{gather}
$$
Step 4 directly contradicts the initial premise that $(X = \emptyset) \lor (Y = \emptyset)$. Consequently, the hypothesis $X \times Y \neq \emptyset$ must be rejected, confirming that: 
$$
\begin{gather}
(X = \emptyset) \lor (Y = \emptyset) \implies X \times Y = \emptyset \tag{5}
\end{gather}
$$

# Reverse Direction
To establish that $X \times Y = \emptyset \implies (X = \emptyset) \lor (Y = \emptyset)$, proceed by proving the contrapositive:
$$
\begin{gather}
\neg((X = \emptyset) \lor (Y = \emptyset)) \implies X \times Y \neq \emptyset \tag{6}
\end{gather}
$$
Assume the antecedent of the contrapositive:
$$
\begin{gather}
\neg((X = \emptyset) \lor (Y = \emptyset)) \tag{7}
\end{gather}
$$
[[Proof of de Morgan's Laws of Set Complements|Applying De Morgan's laws]] to step 7 demonstrates that:
$$
\begin{gather}
(X \neq \emptyset) \wedge (Y \neq \emptyset) \tag{8}
\end{gather}
$$
Because both $X$ and $Y$ are non-empty sets, there exist witness elements $x_0$ and $y_0$ such that: 
$$
\begin{gather}
x_0 \in X \quad \wedge \quad y_0 \in Y \tag{9}
\end{gather}
$$
By the definition of the Cartesian product, the ordered pair formed by these witness elements satisfies: 
$$
\begin{gather}
(x_0, y_0) \in X \times Y \tag{10}
\end{gather}
$$
Because $X \times Y$ contains at least one element $(x_0, y_0)$, it follows that: 
$$
\begin{gather}
X \times Y \neq \emptyset \tag{11}
\end{gather}
$$
Step 8 through step 11 establish the contrapositive implication. Because an implication is logically equivalent to its contrapositive, it follows that: 
$$
\begin{gather}
X \times Y = \emptyset \implies (X = \emptyset) \lor (Y = \emptyset) \tag{12}
\end{gather}
$$
Combining step 5 and step 12 establishes the full equivalence:
$$
\begin{gather}
X \times Y = \emptyset \iff (X = \emptyset) \lor (Y = \emptyset) \tag{13}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$