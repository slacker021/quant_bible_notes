---
dg-publish: true
---
Let $M$ be the ambient universal set, and let $A$ and $B$ be arbitrary subsets of $M$.

---
# Proposition 1

### Forward Inclusion
Let $x \in C_{M}(A \cup B)$. By the definition of the set complement: 
$$
\begin{gather}
x \in M \quad \wedge \quad x \notin (A \cup B) \tag{1}
\end{gather}
$$
By the definition of the set union, the statement $x \in A \cup B$ denotes $(x \in A) \lor (x \in B)$. Applying De Morgan's laws of propositional logic to the negation of this disjunction yields:
$$
\begin{gather}
x \notin A \quad \wedge \quad x \notin B \tag{2}
\end{gather}
$$
Because $x \in M$, step 1 and step 2 imply that:
$$
\begin{gather}
(x \in M \wedge x \notin A) \quad \wedge \quad (x \in M \wedge x \notin B) \tag{3}
\end{gather}
$$
Applying the definition of the complement to both conjuncts of step 3 demonstrates that:
$$
\begin{gather}
x \in C_{M}(A) \quad \wedge \quad x \in C_{M}(B) \tag{4}
\end{gather}
$$
By the definition of the set intersection, step 4 gives:
$$
\begin{gather}
x \in C_{M}(A) \cap C_{M}(B) \tag{5}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 1 through step 5 establish that:
$$
\begin{gather}
C_{M}(A \cup B) \subseteq C_{M}(A) \cap C_{M}(B) \tag{6}
\end{gather}
$$

### Reverse Inclusion
Let $x \in C_{M}(A) \cap C_{M}(B)$. By the definition of the set intersection: 
$$
\begin{gather}
x \in C_{M}(A) \quad \wedge \quad x \in C_{M}(B) \tag{7}
\end{gather}
$$
Applying the definition of the complement to both conjuncts of step 7 gives: 
$$
\begin{gather}
(x \in M \wedge x \notin A) \quad \wedge \quad (x \in M \wedge x \notin B) \tag{8}
\end{gather}
$$
Factoring the common membership $x \in M$ from step 8 results in
$$
\begin{gather}
x \in M \quad \wedge \quad (x \notin A \wedge x \notin B) \tag{9}
\end{gather}
$$
By De Morgan's laws of propositional logic, the conjunction $(x \notin A \wedge x \notin B)$ is logically equivalent to $\neg((x \in A) \lor (x \in B))$, which by the definition of the set union denotes: 
$$
\begin{gather}
x \notin (A \cup B) \tag{10}
\end{gather}
$$
Combining $x \in M$ with step 10 demonstrates that: 
$$
\begin{gather}
x \in C_{M}(A \cup B) \tag{11}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 7 through step 11 establish that: 
$$
\begin{gather}
C_{M}(A) \cap C_{M}(B) \subseteq C_{M}(A \cup B) \tag{12}
\end{gather}
$$
By virtue of mutual inclusion in step 6 and step 12, the Principle of Extensionality confirms that: 
$$
\begin{gather}
C_{M}(A \cup B) = C_{M}(A) \cap C_{M}(B) \tag{13}
\end{gather}
$$

---
# Proposition 2

### Forward Inclusion
Let $x \in C_{M}(A \cap B)$. By the definition of the set complement: 
$$
\begin{gather}
x \in M \quad \wedge \quad x \notin (A \cap B) \tag{14}
\end{gather}
$$
By the definition of the set intersection, the statement $x \in A \cap B$ denotes $(x \in A) \wedge (x \in B)$. Negating this conjunction yields the disjunction:
$$
\begin{gather}
x \notin A \quad \lor \quad x \notin B \tag{15}
\end{gather}
$$
Because $x \in M$, step 14 and step 15 can be distributed as: 
$$
\begin{gather}
(x \in M \wedge x \notin A) \quad \lor \quad (x \in M \wedge x \notin B) \tag{16}
\end{gather}
$$
Applying the definition of the set complement to step 16 establishes that: 
$$
\begin{gather}
x \in C_{M}(A) \quad \lor \quad x \in C_{M}(B) \tag{17}
\end{gather}
$$
By the definition of the set union, step 17 implies that: 
$$
\begin{gather}
x \in C_{M}(A) \cup C_{M}(B) \tag{18}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 14 through step 18 establish that: 
$$
\begin{gather}
C_{M}(A \cap B) \subseteq C_{M}(A) \cup C_{M}(B) \tag{19}
\end{gather}
$$

### Reverse Inclusion
Let $x \in C_{M}(A) \cup C_{M}(B)$. By the definition of the set union: 
$$
\begin{gather}
x \in C_{M}(A) \quad \lor \quad x \in C_{M}(B) \tag{20}
\end{gather}
$$
Applying the definition of the set complement to both disjuncts of step 20 gives: 
$$
\begin{gather}
(x \in M \wedge x \notin A) \quad \lor \quad (x \in M \wedge x \notin B) \tag{21}
\end{gather}
$$
Factoring out the condition $x \in M$ yields: 
$$
\begin{gather}
x \in M \quad \wedge \quad (x \notin A \lor x \notin B) \tag{22}
\end{gather}
$$
By De Morgan's laws of propositional logic, the disjunction $(x \notin A \lor x \notin B)$ is logically equivalent to $\neg(x \in A \wedge x \in B)$, which by the definition of the set intersection denotes: 
$$
\begin{gather}
x \notin (A \cap B) \tag{23}
\end{gather}
$$
Combining $x \in M$ with step 23 demonstrates that: 
$$
\begin{gather}
x \in C_{M}(A \cap B) \tag{24}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 20 through step 24 establish that: 
$$
\begin{gather}
C_{M}(A) \cup C_{M}(B) \subseteq C_{M}(A \cap B) \tag{25}
\end{gather}
$$
By virtue of mutual inclusion in step 19 and step 25, the Principle of Extensionality confirms that: 
$$
\begin{gather}
C_{M}(A \cap B) = C_{M}(A) \cup C_{M}(B) \tag{26}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
