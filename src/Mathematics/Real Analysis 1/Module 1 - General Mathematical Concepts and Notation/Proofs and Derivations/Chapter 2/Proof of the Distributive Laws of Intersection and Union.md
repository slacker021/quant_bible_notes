---
dg-publish: true
---
Let $M$ be the ambient universal set, and let $A$, $B$, and $C$ be arbitrary subsets of $M$.

---
# Proposition 1

### Forward Inclusion
Let $x \in A \cap (B \cup C)$. By the definition of the set intersection: 
$$
\begin{gather}
x \in A \quad \wedge \quad x \in (B \cup C) \tag{1}
\end{gather}
$$
By the definition of the set union, the condition $x \in B \cup C$ denotes $(x \in B) \lor (x \in C)$. Combining this with $x \in A$ leads to two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } x \in B, \text{ then since } x \in A, x \in A \cap B. \\[2mm]
\text{Case 2: If } x \in C, \text{ then since } x \in A, x \in A \cap C. \tag{2}
\end{gather}
$$
Because an element belonging to a set belongs to any union containing that set, step 2 implies that: 
$$
\begin{gather}
x \in (A \cap B) \cup (A \cap C) \tag{3}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 1 through step 3 establish that:
$$
\begin{gather}
A \cap (B \cup C) \subseteq (A \cap B) \cup (A \cap C) \tag{4}
\end{gather}
$$

### Reverse Inclusion
Let $x \in (A \cap B) \cup (A \cap C)$. By the definition of the set union: 
$$
\begin{gather}
x \in (A \cap B) \quad \lor \quad x \in (A \cap C) \tag{5}
\end{gather}
$$
Evaluating both disjuncts:
$$
\begin{gather}
\text{Case 1: If } x \in A \cap B, \text{ then } x \in A \text{ and } x \in B. \\[2mm]
\text{Case 2: If } x \in A \cap C, \text{ then } x \in A \text{ and } x \in C. \tag{6}
\end{gather}
$$
In both cases, $x \in A$ holds unconditionally. Furthermore, $x$ belongs to at least one of $B$ or $C$, meaning that $x \in B \cup C$. Consequently: 
$$
\begin{gather}
x \in A \quad \wedge \quad x \in (B \cup C) \tag{7}
\end{gather}
$$
By the definition of the set intersection, step 7 gives: 
$$
\begin{gather}
x \in A \cap (B \cup C) \tag{8}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 5 through step 8 establish that: 
$$
\begin{gather}
(A \cap B) \cup (A \cap C) \subseteq A \cap (B \cup C) \tag{9}
\end{gather}
$$
By virtue of mutual inclusion in step 4 and step 9, the Principle of Extensionality confirms that: 
$$
\begin{gather}
A \cap (B \cup C) = (A \cap B) \cup (A \cap C) \tag{10}
\end{gather}
$$

---
# Proposition 2

### Forward Inclusion
Let $x \in A \cup (B \cap C)$. By the definition of the set union: 
$$
\begin{gather}
x \in A \quad \lor \quad x \in (B \cap C) \tag{11}
\end{gather}
$$
This disjunction provides two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } x \in A, \text{ then } x \in A \cup B \text{ and } x \in A \cup C. \\[2mm]
\text{Case 2: If } x \in B \cap C, \text{ then } x \in B \text{ (implying } x \in A \cup B\text{) and } x \in C \text{ (implying } x \in A \cup C\text{)}. \tag{12}
\end{gather}
$$
In both cases, $x$ belongs simultaneously to $A \cup B$ and $A \cup C$. By the definition of the set intersection, step 12 yields: 
$$
\begin{gather}
x \in (A \cup B) \cap (A \cup C) \tag{13}
\end{gather}
$$
Because the choice of element $x$ was arbitrary, step 11 through step 13 establish that: 
$$
\begin{gather}
A \cup (B \cap C) \subseteq (A \cup B) \cap (A \cup C) \tag{14}
\end{gather}
$$

### Reverse Inclusion
Let $x \in (A \cup B) \cap (A \cup C)$. By the definition of the set intersection: 
$$
\begin{gather}
x \in (A \cup B) \quad \wedge \quad x \in (A \cup C) \tag{15}
\end{gather}
$$
To determine the membership of $x$, apply the law of excluded middle to the proposition $x \in A$:
$$
\begin{gather}
\text{Case 1: If } x \in A, \text{ then by the definition of the set union, } x \in A \cup (B \cap C). \\[3.5mm]
\text{Case 2: If } x \notin A, \text{ then because } x \in A \cup B \text{ by step 15, it must be that } x \in B. \\[2mm]
\text{Similarly, because } x \in A \cup C \text{ and } x \notin A, \text{ it must be that } x \in C. \\[2mm]
\text{Therefore, } x \in B \wedge x \in C, \text{ which by definition denotes } x \in B \cap C. \\[2mm]
\text{Consequently, } x \in A \cup (B \cap C). \tag{16}
\end{gather}
$$
In both cases, $x \in A \cup (B \cap C)$. Because the choice of element $x$ was arbitrary, step 15 and step 16 establish that: 
$$
\begin{gather}
(A \cup B) \cap (A \cup C) \subseteq A \cup (B \cap C) \tag{17}
\end{gather}
$$
By virtue of mutual inclusion in step 14 and step 17, the Principle of Extensionality confirms that: 
$$
\begin{gather}
A \cup (B \cap C) = (A \cup B) \cap (A \cup C) \tag{18}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
