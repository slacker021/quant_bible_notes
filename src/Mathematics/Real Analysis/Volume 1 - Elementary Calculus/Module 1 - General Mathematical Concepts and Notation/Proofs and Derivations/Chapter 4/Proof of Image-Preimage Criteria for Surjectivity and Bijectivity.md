---
dg-publish: true
---
Let $f: X \to Y$ be a mapping.

---
# Proposition 1

### Necessity
Assume that $f: X \to Y$ is surjective, and let $B' \subseteq Y$ be an arbitrary subset. From Proposition 3, the contraction bound $f(f^{-1}(B')) \subseteq B'$ holds for any mapping $f$. To establish the reverse inclusion $B' \subseteq f(f^{-1}(B'))$, let $y \in B'$ be an arbitrary element. 

Because $f$ is surjective, there exists at least one element $x \in X$ such that $f(x) = y$. Because $f(x) = y \in B'$, the definition of the preimage requires:
$$
\begin{gather}
x \in f^{-1}(B') \tag{1}
\end{gather}
$$
Applying the direct image mapping to step 1 gives: 
$$
\begin{gather}
f(x) \in f(f^{-1}(B')) \implies y \in f(f^{-1}(B')) \tag{2}
\end{gather}
$$
Because the choice of element $y \in B'$ was arbitrary, step 1 and step 2 establish that: 
$$
\begin{gather}
B' \subseteq f(f^{-1}(B')) \tag{3}
\end{gather}
$$
By virtue of mutual inclusion, it follows that: 
$$
\begin{gather}
f(f^{-1}(B')) = B' \tag{4}
\end{gather}
$$

### Sufficiency
Assume that $f(f^{-1}(B')) = B'$ holds for every subset $B' \subseteq Y$. Selecting the entire codomain $B' = Y$ yields: 
$$
\begin{gather}
f(f^{-1}(Y)) = Y \tag{5}
\end{gather}
$$
Because $f^{-1}(Y) \subseteq X$, applying the monotonicity of the direct image gives: 
$$
\begin{gather}
f(f^{-1}(Y)) \subseteq f(X) \tag{6}
\end{gather}
$$
Combining step 5 and step 6 with the fundamental codomain containment $f(X) \subseteq Y$ demonstrates that: 
$$
\begin{gather}
Y = f(f^{-1}(Y)) \subseteq f(X) \subseteq Y \implies f(X) = Y \tag{7}
\end{gather}
$$
Because $f(X) = Y$, every element of the codomain possesses at least one antecedent in $X$. Hence, $f$ is surjective.

---
# Proposition 2

### Necessity
Assume that $f: X \to Y$ is bijective. Because $f$ is surjective, Item 1 guarantees that $f(f^{-1}(B')) = B'$ for all $B' \subseteq Y$. 

Now let $A \subseteq X$ be an arbitrary subset. From Proposition 3, the expansion bound $A \subseteq f^{-1}(f(A))$ holds for any mapping $f$. To establish the reverse inclusion $f^{-1}(f(A)) \subseteq A$, let $x \in f^{-1}(f(A))$ be an arbitrary element. By the definition of the preimage:
$$
\begin{gather}
f(x) \in f(A) \tag{8}
\end{gather}
$$
By the definition of the direct image, step 8 implies that:
$$
\begin{gather}
\exists a \in A \text{ such that } f(x) = f(a) \tag{9}
\end{gather}
$$
Because $f$ is injective, step 9 requires:
$$
\begin{gather}
f(x) = f(a) \implies x = a \tag{10}
\end{gather}
$$
Because $a \in A$, it follows that $x \in A$. Therefore:
$$
\begin{gather}
f^{-1}(f(A)) \subseteq A \tag{11}
\end{gather}
$$
Combining both inclusions confirms that:
$$
\begin{gather}
f^{-1}(f(A)) = A \tag{12}
\end{gather}
$$

### Sufficiency
Assume that $f^{-1}(f(A)) = A$ for all $A \subseteq X$ and $f(f^{-1}(B')) = B'$ for all $B' \subseteq Y$. Because $f(f^{-1}(B')) = B'$ holds for all $B' \subseteq Y$, Item 1 confirms that $f$ is surjective.

To establish injectivity, let $x_1, x_2 \in X$ satisfy:
$$
\begin{gather}
f(x_1) = f(x_2) \tag{13}
\end{gather}
$$
Consider the singleton subset $A = \{x_1\} \subseteq X$. Its direct image is:
$$
\begin{gather}
f(A) = \{f(x_1)\} \tag{14}
\end{gather}
$$
Because $f(x_2) = f(x_1)$ by step 13, it follows that:
$$
\begin{gather}
f(x_2) \in f(A) \tag{15}
\end{gather}
$$
By the definition of the preimage, step 15 implies:
$$
\begin{gather}
x_2 \in f^{-1}(f(A)) \tag{16}
\end{gather}
$$
Applying the initial assumption $f^{-1}(f(A)) = A = \{x_1\}$ to step 16 yields:
$$
\begin{gather}
x_2 \in \{x_1\} \implies x_2 = x_1 \tag{17}
\end{gather}
$$
Because $f(x_1) = f(x_2) \implies x_1 = x_2$, $f$ is injective. Because $f$ is simultaneously surjective and injective, $f$ is bijective.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
