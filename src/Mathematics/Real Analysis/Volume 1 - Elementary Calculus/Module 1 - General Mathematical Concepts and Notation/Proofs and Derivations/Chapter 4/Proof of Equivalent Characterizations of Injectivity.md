---
dg-publish: true
---
Let $f: X \to Y$ be a mapping.

---
# Theorem 1
Assume that $f: X \to Y$ is injective, and let $A \subseteq X$ be an arbitrary subset. From Proposition 3, the expansion bound $A \subseteq f^{-1}(f(A))$ holds for any mapping $f$. 

To establish the reverse inclusion $f^{-1}(f(A)) \subseteq A$, let $x \in f^{-1}(f(A))$ be an arbitrary element. By the definition of the preimage: 
$$
\begin{gather}
x \in f^{-1}(f(A)) \implies f(x) \in f(A) \tag{1}
\end{gather}
$$
By the definition of the direct image, step 1 implies that: 
$$
\begin{gather}
\exists a \in A \text{ such that } f(x) = f(a) \tag{2}
\end{gather}
$$
Because $f$ is injective, step 2 requires: 
$$
\begin{gather}
f(x) = f(a) \implies x = a \tag{3}
\end{gather}
$$
Because $a \in A$, it follows that $x \in A$. Therefore, $f^{-1}(f(A)) \subseteq A$. Combining both inclusions confirms that: 
$$
\begin{gather}
f^{-1}(f(A)) = A \tag{4}
\end{gather}
$$

---
# Theorem 2
Assume that $f^{-1}(f(S)) = S$ holds for every subset $S \subseteq X$. Let $A, B \subseteq X$ be arbitrary subsets. From Proposition 1, the inclusion $f(A \cap B) \subseteq f(A) \cap f(B)$ holds for any mapping $f$. 

To establish the reverse inclusion $f(A) \cap f(B) \subseteq f(A \cap B)$, let $y \in f(A) \cap f(B)$ be an arbitrary element. By the definition of the [[Chapter 2 - Naive Set Theory|set intersection]]: 
$$
\begin{gather}
y \in f(A) \quad \wedge \quad y \in f(B) \tag{5}
\end{gather}
$$
Because $y \in f(A)$, there exists at least one element $x \in X$ such that $f(x) = y$. Applying the definition of the preimage:
$$
\begin{gather}
f(x) = y \in f(A) \implies x \in f^{-1}(f(A)) \tag{6}
\end{gather}
$$
Applying the premise $f^{-1}(f(A)) = A$ to step 6 confirms that: 
$$
\begin{gather}
x \in A \tag{7}
\end{gather}
$$
Similarly, because $f(x) = y \in f(B)$: 
$$
\begin{gather}
f(x) = y \in f(B) \implies x \in f^{-1}(f(B)) = B \implies x \in B \tag{8}
\end{gather}
$$
Combining step 7 and step 8 gives $x \in A \cap B$. Taking the direct image of this element yields: 
$$
\begin{gather}
y = f(x) \in f(A \cap B) \tag{9}
\end{gather}
$$
Therefore, $f(A) \cap f(B) \subseteq f(A \cap B)$. By virtue of mutual inclusion, it follows that: 
$$
\begin{gather}
f(A \cap B) = f(A) \cap f(B) \tag{10}
\end{gather}
$$

---
# Theorem 3
Assume that $f(A \cap B) = f(A) \cap f(B)$ holds for all subsets $A, B \subseteq X$. Let $A, B \subseteq X$ satisfy $A \cap B = \emptyset$. Applying the assumption directly yields: 
$$
\begin{gather}
f(A) \cap f(B) = f(A \cap B) = f(\emptyset) \tag{11}
\end{gather}
$$
Because the empty set contains no elements, its direct image contains no elements: $f(\emptyset) = \emptyset$. Substituting this into step 11 demonstrates that: 
$$
\begin{gather}
A \cap B = \emptyset \implies f(A) \cap f(B) = \emptyset \tag{12}
\end{gather}
$$

---
# Theorem 4
Assume that $A \cap B = \emptyset \implies f(A) \cap f(B) = \emptyset$ holds for all subsets $A, B \subseteq X$. Let $A, B \subseteq X$ satisfy $B \subseteq A$. 

To establish the forward inclusion $f(A \setminus B) \subseteq f(A) \setminus f(B)$, observe that $(A \setminus B) \cap B = \emptyset$ by the definition of set difference. Applying hypothesis 4 yields: 
$$
\begin{gather}
f(A \setminus B) \cap f(B) = \emptyset \tag{13}
\end{gather}
$$
Because $A \setminus B \subseteq A$, the monotonicity property of direct images establishes that: 
$$
\begin{gather}
f(A \setminus B) \subseteq f(A) \tag{14}
\end{gather}
$$
Because $f(A \setminus B)$ is contained in $f(A)$ and is disjoint from $f(B)$ by step 13, it must be contained in their difference:
$$
\begin{gather}
f(A \setminus B) \subseteq f(A) \setminus f(B) \tag{15}
\end{gather}
$$

To establish the reverse inclusion $f(A) \setminus f(B) \subseteq f(A \setminus B)$, let $y \in f(A) \setminus f(B)$ be an arbitrary element. By the definition of the set difference: 
$$
\begin{gather}
y \in f(A) \quad \wedge \quad y \notin f(B) \tag{16}
\end{gather}
$$
Because $y \in f(A)$, there exists an element $x \in A$ such that $f(x) = y$. If $x \in B$, then $f(x) = y \in f(B)$, which directly contradicts step 16. Therefore, $x \notin B$. Combining $x \in A$ with $x \notin B$ gives: 
$$
\begin{gather}
x \in A \setminus B \tag{17}
\end{gather}
$$
Taking the direct image of $x$ in step 17 yields: 
$$
\begin{gather}
y = f(x) \in f(A \setminus B) \tag{18}
\end{gather}
$$
Therefore, $f(A) \setminus f(B) \subseteq f(A \setminus B)$. By virtue of mutual inclusion in step 15 and step 18, it follows that: 
$$
\begin{gather}
B \subseteq A \implies f(A \setminus B) = f(A) \setminus f(B) \tag{19}
\end{gather}
$$

---
# Theorem 5
Assume that $f(A \setminus B) = f(A) \setminus f(B)$ holds whenever $B \subseteq A \subseteq X$. To establish that $f$ is injective, let $x_1, x_2 \in X$ be distinct elements ($x_1 \neq x_2$). 

Define the subsets $A := \{x_1, x_2\}$ and $B := \{x_2\}$. Because $x_2 \in \{x_1, x_2\}$, it follows that $B \subseteq A \subseteq X$. The set difference evaluates to: 
$$
\begin{gather}
A \setminus B = \{x_1\} \tag{20}
\end{gather}
$$
Applying assumption 5 to these subsets yields: 
$$
\begin{gather}
f(\{x_1\}) = f(A \setminus B) = f(A) \setminus f(B) = f(\{x_1, x_2\}) \setminus f(\{x_2\}) \tag{21}
\end{gather}
$$
Evaluating the direct images gives: 
$$
\begin{gather}
\{f(x_1)\} = \{f(x_1), f(x_2)\} \setminus \{f(x_2)\} \tag{22}
\end{gather}
$$
Because $\{f(x_1)\}$ is a non-empty singleton set, the right-hand side of step 22 cannot be empty. If $f(x_1) = f(x_2)$, the right-hand side simplifies to $\{f(x_2)\} \setminus \{f(x_2)\} = \emptyset$, producing a contradiction ($\{f(x_1)\} = \emptyset$). Therefore, it must be that: 
$$
\begin{gather}
f(x_1) \neq f(x_2) \tag{23}
\end{gather}
$$
Because $x_1 \neq x_2 \implies f(x_1) \neq f(x_2)$, $f$ is injective. 

This closes the circular chain of implications, establishing that theorems 1, 2, 3, 4, and 5 are logically equivalent.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
