---
dg-publish: true
---
Let $f: X \to Y$ be a mapping, and let $A$ and $B$ be arbitrary subsets of $X$.

---
# Proposition 1
Assume that $A \subseteq B$, and let $y \in f(A)$ be an arbitrary element. By the definition of the direct image under $f$, there exists at least one element $x \in A$ such that: 
$$
\begin{gather}
f(x) = y \tag{1}
\end{gather}
$$
Because $A \subseteq B$, the condition $x \in A$ requires: 
$$
\begin{gather}
x \in B \tag{2}
\end{gather}
$$
Because $x \in B$ and $y = f(x)$, the definition of the direct image confirms that: 
$$
\begin{gather}
y \in f(B) \tag{3}
\end{gather}
$$
Because $y \in f(A) \implies y \in f(B)$ holds for all $y \in f(A)$, it follows that: 
$$
\begin{gather}
A \subseteq B \implies f(A) \subseteq f(B) \tag{4}
\end{gather}
$$

To demonstrate that $f(A) \subseteq f(B)$ does not imply $A \subseteq B$ in general, consider the constant mapping $f: \{1, 2\} \to \{0\}$ defined by $f(1) = 0$ and $f(2) = 0$. Let $A = \{1\}$ and $B = \{2\}$. Evaluating the direct images yields: 
$$
\begin{gather}
f(A) = \{0\} \quad \wedge \quad f(B) = \{0\} \tag{5}
\end{gather}
$$
Here, $f(A) \subseteq f(B)$ holds trivially, yet $A \not\subseteq B$ because $1 \notin \{2\}$. Therefore, the converse of step 4 fails in general unless $f$ is injective.

---
# Proposition 2
Assume that $A \neq \emptyset$. There exists at least one witness element $x_0 \in A$. Because $f: X \to Y$ is a well-defined mapping, $f(x_0)$ exists and assigns $x_0$ to a unique value $y_0 \in Y$. By the definition of the direct image: 
$$
\begin{gather}
f(A) = \{f(x) \in Y \mid x \in A\} \tag{6}
\end{gather}
$$
The element $y_0 = f(x_0)$ belongs to $f(A)$. Because $f(A)$ contains at least one element $y_0$, it follows that: 
$$
\begin{gather}
A \neq \emptyset \implies f(A) \neq \emptyset \tag{7}
\end{gather}
$$

---
# Proposition 3
Let $y \in f(A \cap B)$ be an arbitrary element. By the definition of the direct image, there exists an element $x \in A \cap B$ such that $f(x) = y$. By the definition of the set intersection: 
$$
\begin{gather}
x \in A \cap B \implies (x \in A) \wedge (x \in B) \tag{8}
\end{gather}
$$
Because $x \in A$ and $y = f(x)$, it follows that $y \in f(A)$. Similarly, because $x \in B$ and $y = f(x)$, it follows that $y \in f(B)$. Combining these two statements gives: 
$$
\begin{gather}
(y \in f(A)) \wedge (y \in f(B)) \tag{9}
\end{gather}
$$
By the definition of the set intersection, step 9 implies that: 
$$
\begin{gather}
y \in f(A) \cap f(B) \tag{10}
\end{gather}
$$
Because the choice of element $y$ was arbitrary, step 8 through step 10 establish that: 
$$
\begin{gather}
f(A \cap B) \subseteq f(A) \cap f(B) \tag{11}
\end{gather}
$$

---
# Proposition 4
### Forward Inclusion
Let $y \in f(A \cup B)$ be an arbitrary element. By the definition of the direct image, there exists an element $x \in A \cup B$ such that $f(x) = y$. By the definition of the set union: 
$$
\begin{gather}
x \in A \cup B \implies (x \in A) \lor (x \in B) \tag{12}
\end{gather}
$$
This disjunction provides two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } x \in A, \text{ then since } y = f(x), y \in f(A). \text{ Consequently, } y \in f(A) \cup f(B). \\[2mm]
\text{Case 2: If } x \in B, \text{ then since } y = f(x), y \in f(B). \text{ Consequently, } y \in f(A) \cup f(B). \tag{13}
\end{gather}
$$
In both cases, $y \in f(A) \cup f(B)$. Because the choice of element $y$ was arbitrary, step 12 and step 13 establish that: 
$$
\begin{gather}
f(A \cup B) \subseteq f(A) \cup f(B) \tag{14}
\end{gather}
$$

### Reverse Inclusion
By the elementary definition of the set union, $A \subseteq A \cup B$ and $B \subseteq A \cup B$. Applying the monotonicity property established in Item 1:
$$
\begin{gather}
A \subseteq A \cup B \implies f(A) \subseteq f(A \cup B) \tag{15}
\end{gather}
$$
$$
\begin{gather}
B \subseteq A \cup B \implies f(B) \subseteq f(A \cup B) \tag{16}
\end{gather}
$$
Combining step 15 and step 16 via the elementary union inclusion property yields: 
$$
\begin{gather}
f(A) \cup f(B) \subseteq f(A \cup B) \tag{17}
\end{gather}
$$
By virtue of mutual inclusion in step 14 and step 17, the Principle of Extensionality confirms that: 
$$
\begin{gather}
f(A \cup B) = f(A) \cup f(B) \tag{18}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
