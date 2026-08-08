---
dg-publish: true
---
Let $X$ and $Y$ be sets such that $X \times Y \neq \emptyset$, and let $A$ and $B$ be arbitrary non-empty sets.

# Forward Direction
Assume that $(A \subseteq X) \wedge (B \subseteq Y)$, and let $(a, b) \in A \times B$ be an arbitrary element. By the definition of the Cartesian product: 
$$
\begin{gather}
(a, b) \in A \times B \implies (a \in A) \wedge (b \in B) \tag{1}
\end{gather}
$$
Applying the subset assumptions to step 1 yields: 
$$
\begin{gather}
a \in A \wedge A \subseteq X \implies a \in X \tag{2}
\end{gather}
$$
$$
\begin{gather}
b \in B \wedge B \subseteq Y \implies b \in Y \tag{3}
\end{gather}
$$
Combining step 2 and step 3 gives: 
$$
\begin{gather}
(a \in X) \wedge (b \in Y) \tag{4}
\end{gather}
$$
By the definition of the Cartesian product $X \times Y$, step 4 implies that: 
$$
\begin{gather}
(a, b) \in X \times Y \tag{5}
\end{gather}
$$
Because the choice of element $(a, b)$ was arbitrary, step 1 through step 5 establish that: 
$$
\begin{gather}
(A \subseteq X) \wedge (B \subseteq Y) \implies A \times B \subseteq X \times Y \tag{6}
\end{gather}
$$

# Reverse Direction
Assume that $A \times B \subseteq X \times Y$, with $A \neq \emptyset$ and $B \neq \emptyset$. 

To establish that $A \subseteq X$, let $a \in A$ be an arbitrary element. Because $B \neq \emptyset$, there exists at least one witness element $b_0 \in B$. By the definition of the Cartesian product: 
$$
\begin{gather}
a \in A \wedge b_0 \in B \implies (a, b_0) \in A \times B \tag{7}
\end{gather}
$$
Applying the premise $A \times B \subseteq X \times Y$ to step 7 demonstrates that: 
$$
\begin{gather}
(a, b_0) \in X \times Y \tag{8}
\end{gather}
$$
By the definition of the Cartesian product, step 8 requires that: 
$$
\begin{gather}
a \in X \tag{9}
\end{gather}
$$
Because the choice of element $a \in A$ was arbitrary, step 7 through step 9 establish that: 
$$
\begin{gather}
A \subseteq X \tag{10}
\end{gather}
$$

To establish that $B \subseteq Y$, let $b \in B$ be an arbitrary element. Because $A \neq \emptyset$, there exists at least one witness element $a_0 \in A$. By the definition of the Cartesian product: 
$$
\begin{gather}
a_0 \in A \wedge b \in B \implies (a_0, b) \in A \times B \tag{11}
\end{gather}
$$
Applying the premise $A \times B \subseteq X \times Y$ to step 11 demonstrates that: 
$$
\begin{gather}
(a_0, b) \in X \times Y \tag{12}
\end{gather}
$$
By the definition of the Cartesian product, step 12 requires that: 
$$
\begin{gather}
b \in Y \tag{13}
\end{gather}
$$
Because the choice of element $b \in B$ was arbitrary, step 11 through step 13 establish that: 
$$
\begin{gather}
B \subseteq Y \tag{14}
\end{gather}
$$
Combining step 10 and step 14 yields: 
$$
\begin{gather}
A \times B \subseteq X \times Y \implies (A \subseteq X) \wedge (B \subseteq Y) \tag{15}
\end{gather}
$$
Combining step 6 and step 15 establishes the full equivalence:
$$
\begin{gather}
A \times B \subseteq X \times Y \iff (A \subseteq X) \wedge (B \subseteq Y) \tag{16}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
