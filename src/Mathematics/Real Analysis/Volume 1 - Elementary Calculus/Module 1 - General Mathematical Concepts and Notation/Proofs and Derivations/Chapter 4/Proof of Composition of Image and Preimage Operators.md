---
dg-publish: true
---
Let $f: X \to Y$ be a mapping, let $A \subseteq X$, and let $B' \subseteq Y$.

---
# Proposition 1
Let $x \in A$ be an arbitrary element. By the definition of the direct image under $f$: 
$$
\begin{gather}
x \in A \implies f(x) \in f(A) \tag{1}
\end{gather}
$$
The definition of the preimage for any subset $S \subseteq Y$ is: 
$$
\begin{gather}
f^{-1}(S) := \{z \in X \mid f(z) \in S\} \tag{2}
\end{gather}
$$
Instantiating $S = f(A)$ in step 2 yields: 
$$
\begin{gather}
f^{-1}(f(A)) = \{z \in X \mid f(z) \in f(A)\} \tag{3}
\end{gather}
$$
Because $f(x) \in f(A)$ by step 1, the element $x$ satisfies the defining membership condition $f(x) \in f(A)$, which implies: 
$$
\begin{gather}
x \in f^{-1}(f(A)) \tag{4}
\end{gather}
$$
Because $x \in A \implies x \in f^{-1}(f(A))$ holds for all $x \in A$, it follows that: 
$$
\begin{gather}
A \subseteq f^{-1}(f(A)) \tag{5}
\end{gather}
$$

---
# Proposition 2
Let $y \in f(f^{-1}(B'))$ be an arbitrary element. By the definition of the direct image, the condition $y \in f(f^{-1}(B'))$ implies the existence of at least one element $x \in f^{-1}(B')$ such that: 
$$
\begin{gather}
f(x) = y \tag{6}
\end{gather}
$$
By the definition of the preimage, the membership $x \in f^{-1}(B')$ implies: 
$$
\begin{gather}
f(x) \in B' \tag{7}
\end{gather}
$$
Substituting $y = f(x)$ from step 6 into step 7 yields: 
$$
\begin{gather}
y \in B' \tag{8}
\end{gather}
$$
Because $y \in f(f^{-1}(B')) \implies y \in B'$ holds for all $y \in f(f^{-1}(B'))$, it follows that: 
$$
\begin{gather}
f(f^{-1}(B')) \subseteq B' \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
