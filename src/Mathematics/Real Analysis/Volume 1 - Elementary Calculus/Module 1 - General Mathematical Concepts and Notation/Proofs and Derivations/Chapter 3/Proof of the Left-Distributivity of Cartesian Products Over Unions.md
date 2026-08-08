---
dg-publish: true
---
Let $X, Y, X', Y'$ be arbitrary sets. 

---
# Primary Proof
### Necessity
Let $(a, b) \in (X \times Y) \cap (X' \times Y')$ be an arbitrary element. By definition of set intersection: 
$$(a, b) \in (X \times Y) \cap (X' \times Y') \implies (a, b) \in X \times Y \wedge (a, b) \in X' \times Y' \tag{1}$$
By definition of the Cartesian product: 
$$
\begin{gather}
(a, b) \in X \times Y \implies (a \in X) \land (b \in Y) \\
(a, b) \in X' \times Y' \implies (a \in X') \land (b \in Y') \tag{2}
\end{gather}
$$
Combining all four conditions yields: 
$$(a \in X) \land (b \in Y) \land (a \in X') \land (b \in Y') \tag{3}$$
By the associativity and commutativity of logical conjunction ($\land$), regrouping the terms for each coordinate gives:
$$((a \in X) \land (a \in X')) \land ((b \in Y) \land (b \in Y')) \tag{4}$$ By definition of set intersection: 
$$
(a \in X \cap X') \land (b \in Y \cap Y') \tag{5}
$$
By definition of the Cartesian product, this conjunction implies that: 
$$(a, b) \in (X \cap X') \times (Y \cap Y') \tag{6}$$
Therefore: 
$$
(X \times Y) \cap (X' \times Y') \subseteq (X \cap X') \times (Y \cap Y') \tag{7}
$$

### Sufficiency
Let $(a, b) \in (X \cap X') \times (Y \cap Y')$ be an arbitrary element. By definition of the Cartesian product: 
$$(a, b) \in (X \cap X') \times (Y \cap Y') \implies (a \in X \cap X') \land (b \in Y \cap Y') \tag{8}$$
By definition of set intersection: 
$$
\begin{gather}
a \in X \cap X' \implies (a \in X) \land (a \in X') \\
b \in Y \cap Y' \implies (b \in Y) \land (b \in Y') \tag{9}
\end{gather}
$$
Regrouping the logical conjunctions by ordered pair components yields:
$$((a \in X) \land (b \in Y)) \land ((a \in X') \land (b \in Y')) \tag{10}$$
By definition of the Cartesian product:
$$(a, b) \in X \times Y \land (a, b) \in X' \times Y' \tag{11}$$
By definition of set intersection:
$$(a, b) \in (X \times Y) \cap (X' \times Y') \tag{12}$$
Therefore: 
$$(X \cap X') \times (Y \cap Y') \subseteq (X \times Y) \cap (X' \times Y') \tag{13}$$
$$\textbf{Q.E.D}$$

---
# Alternative Proof
The equality can also be proven directly through a continuous chain of logical equivalences:
$$\begin{aligned}
(a, b) \in (X \times Y) \cap (X' \times Y') &\iff ((a, b) \in X \times Y) \land ((a, b) \in X' \times Y') & \text{(Definition of } \cap\text{)} \\ &\iff (a \in X \land b \in Y) \land (a \in X' \land b \in Y') & \text{(Definition of } \times\text{)} \\ &\iff (a \in X \land a \in X') \land (b \in Y \land b \in Y') & \text{(Associativity/Commutativity of } \land\text{)} \\ &\iff (a \in X \cap X') \land (b \in Y \cap Y') & \text{(Definition of } \cap\text{)} \\ &\iff (a, b) \in (X \cap X') \times (Y \cap Y') & \text{(Definition of } \times\text{)} \\
& & \text{(14)}
\end{aligned}$$
Because each step is a logical equivalence, the identity holds directly.
$$\textbf{Q.E.D}$$