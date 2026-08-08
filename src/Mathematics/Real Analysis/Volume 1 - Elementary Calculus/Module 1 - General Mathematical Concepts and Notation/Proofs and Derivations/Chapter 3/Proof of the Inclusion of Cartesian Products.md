---
dg-publish: true
---
Let $X, Y,$ and $Z$ be arbitrary sets.

---
# Method 1: Mutual Subset Inclusion

### Forward Inclusion
Let $(a, b) \in (X \times Y) \cup (Z \times Y)$ be an arbitrary element. By the definition of the [[Chapter 2 - Naive Set Theory|set union]], 
$$
\begin{gather}
(a, b) \in X \times Y \quad \lor \quad (a, b) \in Z \times Y \tag{1}
\end{gather}
$$
Evaluating both disjuncts:
$$
\begin{gather}
\text{Case 1: If } (a, b) \in X \times Y, \text{ then } a \in X \text{ and } b \in Y. \\[2mm]
\text{Since } a \in X, \text{ it follows that } a \in X \cup Z. \text{ Combining } a \in X \cup Z \text{ with } b \in Y \text{ yields:} \\[2mm]
(a, b) \in (X \cup Z) \times Y. \\[3.5mm]
\text{Case 2: If } (a, b) \in Z \times Y, \text{ then } a \in Z \text{ and } b \in Y. \\[2mm]
\text{Since } a \in Z, \text{ it follows that } a \in X \cup Z. \text{ Combining } a \in X \cup Z \text{ with } b \in Y \text{ yields:} \\[2mm]
(a, b) \in (X \cup Z) \times Y. \tag{2}
\end{gather}
$$
Because $(a, b) \in (X \cup Z) \times Y$ holds in both cases, it follows that: 
$$
\begin{gather}
(X \times Y) \cup (Z \times Y) \subseteq (X \cup Z) \times Y \tag{3}
\end{gather}
$$

### Reverse Inclusion
Let $(a, b) \in (X \cup Z) \times Y$ be an arbitrary element. By the definition of the Cartesian product: 
$$
\begin{gather}
a \in (X \cup Z) \quad \wedge \quad b \in Y \tag{4}
\end{gather}
$$
By the definition of the set union, $a \in X \cup Z \iff (a \in X) \lor (a \in Z)$. This disjunction provides two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } a \in X, \text{ then because } b \in Y, \text{ it follows that } (a, b) \in X \times Y. \\[2mm]
\text{Consequently, } (a, b) \in (X \times Y) \cup (Z \times Y). \\[3.5mm]
\text{Case 2: If } a \in Z, \text{ then because } b \in Y, \text{ it follows that } (a, b) \in Z \times Y. \\[2mm]
\text{Consequently, } (a, b) \in (X \times Y) \cup (Z \times Y). \tag{5}
\end{gather}
$$
Because $(a, b) \in (X \times Y) \cup (Z \times Y)$ holds in both cases, it follows that: 
$$
\begin{gather}
(X \cup Z) \times Y \subseteq (X \times Y) \cup (Z \times Y) \tag{6}
\end{gather}
$$
By virtue of mutual inclusion in step 3 and step 6, the Principle of Extensionality confirms that: 
$$
\begin{gather}
(X \times Y) \cup (Z \times Y) = (X \cup Z) \times Y \tag{7}
\end{gather}
$$

---
# Method 2: Predicate Logic Equivalence
The set identity can be verified through a continuous chain of logical equivalences. Let $(a, b)$ be an arbitrary ordered pair:
$$
\begin{aligned}
(a, b) \in (X \cup Z) \times Y &\iff (a \in X \cup Z) \land (b \in Y) \\
&\iff ((a \in X) \lor (a \in Z)) \land (b \in Y) \\
&\iff ((a \in X) \land (b \in Y)) \lor ((a \in Z) \land (b \in Y)) \\
&\iff ((a, b) \in X \times Y) \lor ((a, b) \in Z \times Y) \\
&\iff (a, b) \in (X \times Y) \cup (Z \times Y)
\end{aligned} \tag{8}
$$
Because each deduction in step 8 is a reversible logical equivalence, the Principle of Extensionality confirms the identity:
$$
\begin{gather}
(X \times Y) \cup (Z \times Y) = (X \cup Z) \times Y \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
