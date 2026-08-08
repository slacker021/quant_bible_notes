---
dg-publish: true
---
Let $f: X \to Y$ be a mapping, and let $A'$ and $B'$ be arbitrary subsets of $Y$.

---
# Lemma 1
Assume that $A' \subseteq B'$, and let $x \in f^{-1}(A')$ be an arbitrary element. By the definition of the preimage: 
$$
\begin{gather}
x \in f^{-1}(A') \implies f(x) \in A' \tag{1}
\end{gather}
$$
Because $A' \subseteq B'$, it follows that:
$$
\begin{gather}
f(x) \in A' \implies f(x) \in B' \tag{2}
\end{gather}
$$
By the definition of the preimage, step 2 implies that: 
$$
\begin{gather}
f(x) \in B' \implies x \in f^{-1}(B') \tag{3}
\end{gather}
$$
Because $x \in f^{-1}(A') \implies x \in f^{-1}(B')$ holds for all $x \in f^{-1}(A')$, it follows that: 
$$
\begin{gather}
A' \subseteq B' \implies f^{-1}(A') \subseteq f^{-1}(B') \tag{4}
\end{gather}
$$

---
# Lemma 2
The set identity is verified through a continuous chain of logical equivalences for an arbitrary element $x \in X$:
$$
\begin{aligned}
x \in f^{-1}(A' \cap B') &\iff f(x) \in A' \cap B' \\
&\iff (f(x) \in A') \land (f(x) \in B') \\
&\iff (x \in f^{-1}(A')) \land (x \in f^{-1}(B')) \\
&\iff x \in f^{-1}(A') \cap f^{-1}(B')
\end{aligned} \tag{5}
$$
Because each deduction in step 5 is an unbroken logical equivalence, the Principle of Extensionality confirms that: 
$$
\begin{gather}
f^{-1}(A' \cap B') = f^{-1}(A') \cap f^{-1}(B') \tag{6}
\end{gather}
$$

---
# Lemma 3
Similarly, the set identity is verified through a continuous chain of logical equivalences for an arbitrary element $x \in X$:
$$
\begin{aligned}
x \in f^{-1}(A' \cup B') &\iff f(x) \in A' \cup B' \\
&\iff (f(x) \in A') \lor (f(x) \in B') \\
&\iff (x \in f^{-1}(A')) \lor (x \in f^{-1}(B')) \\
&\iff x \in f^{-1}(A') \cup f^{-1}(B')
\end{aligned} \tag{7}
$$
Because each deduction in step 7 is an unbroken logical equivalence, the Principle of Extensionality confirms that: 
$$
\begin{gather}
f^{-1}(A' \cup B') = f^{-1}(A') \cup f^{-1}(B') \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
