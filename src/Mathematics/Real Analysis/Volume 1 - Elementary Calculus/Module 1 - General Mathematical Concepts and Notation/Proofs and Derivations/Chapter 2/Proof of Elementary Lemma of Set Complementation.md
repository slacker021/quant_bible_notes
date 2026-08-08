---
dg-publish: true
---
Let $M$ be the ambient universal set, and let $A$, $B$, and $S$ be arbitrary subsets of $M$.

---
# Proposition 1

### Necessity
Assume that $(A \subseteq S) \wedge (B \subseteq S)$, and let $x \in A \cup B$. By the definition of the set union: 
$$
\begin{gather}
x \in A \cup B \iff (x \in A) \lor (x \in B) \tag{1}
\end{gather}
$$
This disjunction requires evaluating two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } x \in A, \text{ the premise } A \subseteq S \text{ implies that } x \in S. \\[2mm]
\text{Case 2: If } x \in B, \text{ the premise } B \subseteq S \text{ implies that } x \in S. \tag{2}
\end{gather}
$$
In both cases, $x \in S$. Because the choice of element $x$ was arbitrary, step 1 and step 2 establish that
$$
\begin{gather}
(A \cup B) \subseteq S \tag{3}
\end{gather}
$$

### Sufficiency
Assume that $(A \cup B) \subseteq S$. By the elementary definition of the set union, every constituent set is contained within the union:
$$
\begin{gather}
A \subseteq (A \cup B) \quad \wedge \quad B \subseteq (A \cup B) \tag{4}
\end{gather}
$$
By the transitivity of the subset relation ($X \subseteq Y \wedge Y \subseteq Z \implies X \subseteq Z$), step 4 combined with the initial assumption yields: 
$$
\begin{gather}
A \subseteq S \quad \wedge \quad B \subseteq S \tag{5}
\end{gather}
$$
Combining step 3 and step 5 establishes the full equivalence: 
$$
\begin{gather}
(A \subseteq S) \wedge (B \subseteq S) \iff (A \cup B) \subseteq S \tag{6}
\end{gather}
$$

---
# Proposition 2

### Necessity
Assume that $A \subseteq B$, and let $x \in C_{M}(B)$. By the definition of the set complement: 
$$
\begin{gather}
x \in M \quad \wedge \quad x \notin B \tag{7}
\end{gather}
$$
To establish that $x \notin A$, proceed by contradiction. Assume that: 
$$
\begin{gather}
x \in A \tag{8}
\end{gather}
$$
Because $A \subseteq B$, the condition in step 8 implies that: 
$$
\begin{gather}
x \in B \tag{9}
\end{gather}
$$
Step 9 directly contradicts the established fact in step 7 that $x \notin B$. Consequently, the hypothesis that $x \in A$ must be rejected, confirming that $x \notin A$. Combining $x \in M$ with $x \notin A$ demonstrates that: 
$$
\begin{gather}
x \in C_{M}(A) \tag{10}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 7 through step 10 establish that: 
$$
\begin{gather}
A \subseteq B \implies C_{M}(B) \subseteq C_{M}(A) \tag{11}
\end{gather}
$$

### Sufficiency
Assume that $C_{M}(B) \subseteq C_{M}(A)$, and let $x \in A$. Because $A \subseteq M$, it follows that $x \in M$. To demonstrate that $x \in B$, proceed by contradiction. Assume that: 
$$
\begin{gather}
x \notin B \tag{12}
\end{gather}
$$
Because $x \in M$ and $x \notin B$, the definition of the complement requires that: 
$$
\begin{gather}
x \in C_{M}(B) \tag{13}
\end{gather}
$$
Applying the premise $C_{M}(B) \subseteq C_{M}(A)$ to step 13 indicates that: 
$$
\begin{gather}
x \in C_{M}(A) \tag{14}
\end{gather}
$$
By the definition of the set complement, step 14 implies that $x \notin A$, which directly contradicts the initial premise that $x \in A$. Consequently, the assumption that $x \notin B$ must be rejected, confirming that $x \in B$. Because $x \in A$ implies $x \in B$, it follows that: 
$$
\begin{gather}
C_{M}(B) \subseteq C_{M}(A) \implies A \subseteq B \tag{15}
\end{gather}
$$
Combining step 11 and step 15 establishes the full equivalence: 
$$
\begin{gather}
(A \subseteq B) \iff (C_{M}(B) \subseteq C_{M}(A)) \tag{16}
\end{gather}
$$

---
# Proposition 3

### Forward Inclusion
Let $x \in C_{M}(C_{M}(A))$. By the definition of the set complement: 
$$
\begin{gather}
x \in M \quad \wedge \quad x \notin C_{M}(A) \tag{17}
\end{gather}
$$
By the definition of the complement $C_M(A)$, the condition $x \notin C_M(A)$ denotes: 
$$
\begin{gather}
\neg(x \in M \wedge x \notin A) \tag{18}
\end{gather}
$$
Applying De Morgan's laws of propositional logic to step 18 yields the equivalent disjunction:
$$
\begin{gather}
x \notin M \quad \lor \quad x \in A \tag{19}
\end{gather}
$$
Because step 17 explicitly establishes that $x \in M$, the first disjunct of step 19 is false. Therefore, the second disjunct must be true: 
$$
\begin{gather}
x \in A \tag{20}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 17 through step 20 establish that: 
$$
\begin{gather}
C_{M}(C_{M}(A)) \subseteq A \tag{21}
\end{gather}
$$

### Reverse Inclusion
Let $x \in A$. Because $A \subseteq M$, it follows that $x \in M$. By the law of non-contradiction, the statement $x \in A$ implies that $x \notin A$ is false, which prevents $x$ from satisfying the defining membership condition of $C_M(A)$:
$$
\begin{gather}
x \notin C_{M}(A) \tag{22}
\end{gather}
$$
Combining $x \in M$ with step 22 satisfies the definition of the complement of $C_M(A)$ in $M$:
$$
\begin{gather}
x \in M \quad \wedge \quad x \notin C_{M}(A) \iff x \in C_{M}(C_{M}(A)) \tag{23}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 22 and step 23 establish that:
$$
\begin{gather}
A \subseteq C_{M}(C_{M}(A)) \tag{24}
\end{gather}
$$
By virtue of mutual inclusion in step 21 and step 24, the Principle of Extensionality confirms that: 
$$
\begin{gather}
C_{M}(C_{M}(A)) = A \tag{25}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
