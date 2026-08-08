---
dg-publish: true
---
Let $X, Y, X',$ and $Y'$ be arbitrary sets.

---
# Method 1: Mutual Subset Inclusion

### Forward Inclusion
Let $(a, b) \in (X \times Y) \cap (X' \times Y')$ be an arbitrary element. By the definition of the set intersection: 
$$
\begin{gather}
(a, b) \in X \times Y \quad \wedge \quad (a, b) \in X' \times Y' \tag{1}
\end{gather}
$$
Applying the definition of the Cartesian product to both conjuncts of step 1 gives: 
$$
\begin{gather}
(a \in X \wedge b \in Y) \quad \wedge \quad (a \in X' \wedge b \in Y') \tag{2}
\end{gather}
$$
By the associativity and commutativity of logical conjunction ($\wedge$), the terms in step 2 can be regrouped by coordinate:
$$
\begin{gather}
(a \in X \wedge a \in X') \quad \wedge \quad (b \in Y \wedge b \in Y') \tag{3}
\end{gather}
$$
By the definition of the set intersection, step 3 translates to: 
$$
\begin{gather}
a \in (X \cap X') \quad \wedge \quad b \in (Y \cap Y') \tag{4}
\end{gather}
$$
By the definition of the Cartesian product, step 4 implies that: 
$$
\begin{gather}
(a, b) \in (X \cap X') \times (Y \cap Y') \tag{5}
\end{gather}
$$
Because the choice of element $(a, b)$ was arbitrary, step 1 through step 5 establish that: 
$$
\begin{gather}
(X \times Y) \cap (X' \times Y') \subseteq (X \cap X') \times (Y \cap Y') \tag{6}
\end{gather}
$$

### Reverse Inclusion
Let $(a, b) \in (X \cap X') \times (Y \cap Y')$ be an arbitrary element. By the definition of the Cartesian product: 
$$
\begin{gather}
a \in (X \cap X') \quad \wedge \quad b \in (Y \cap Y') \tag{7}
\end{gather}
$$
Applying the definition of the set intersection to both conjuncts of step 7 gives: 
$$
\begin{gather}
(a \in X \wedge a \in X') \quad \wedge \quad (b \in Y \wedge b \in Y') \tag{8}
\end{gather}
$$
Regrouping the conjuncts in step 8 by Cartesian factors yields: 
$$
\begin{gather}
(a \in X \wedge b \in Y) \quad \wedge \quad (a \in X' \wedge b \in Y') \tag{9}
\end{gather}
$$
Applying the definition of the Cartesian product to both components of step 9 establishes that: 
$$
\begin{gather}
(a, b) \in X \times Y \quad \wedge \quad (a, b) \in X' \times Y' \tag{10}
\end{gather}
$$
By the definition of the set intersection, step 10 implies that: 
$$
\begin{gather}
(a, b) \in (X \times Y) \cap (X' \times Y') \tag{11}
\end{gather}
$$
Because the choice of element $(a, b)$ was arbitrary, step 7 through step 11 establish that: 
$$
\begin{gather}
(X \cap X') \times (Y \cap Y') \subseteq (X \times Y) \cap (X' \times Y') \tag{12}
\end{gather}
$$
By virtue of mutual inclusion in step 6 and step 12, the Principle of Extensionality confirms that: 
$$
\begin{gather}
(X \times Y) \cap (X' \times Y') = (X \cap X') \times (Y \cap Y') \tag{13}
\end{gather}
$$

---
# Method 2: Predicate Logic Equivalence
The set identity can be verified through a continuous chain of logical equivalences. Let $(a, b)$ be an arbitrary ordered pair:
$$
\begin{aligned}
(a, b) \in (X \times Y) \cap (X' \times Y') &\iff ((a, b) \in X \times Y) \land ((a, b) \in X' \times Y') \\
&\iff (a \in X \land b \in Y) \land (a \in X' \land b \in Y') \\
&\iff (a \in X \land a \in X') \land (b \in Y \land b \in Y') \\
&\iff (a \in X \cap X') \land (b \in Y \cap Y') \\
&\iff (a, b) \in (X \cap X') \times (Y \cap Y')
\end{aligned} \tag{14}
$$
Because each deduction in step 14 is a reversible logical equivalence, the Principle of Extensionality confirms the identity:
$$
\begin{gather}
(X \times Y) \cap (X' \times Y') = (X \cap X') \times (Y \cap Y') \tag{15}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
