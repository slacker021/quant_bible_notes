---
dg-publish: true
---
Let $f: X \to Y$ be a mapping, and let $A'$ and $B'$ be arbitrary subsets of $Y$.

---
# Proposition 1
The set identity is verified through a continuous chain of logical equivalences for an arbitrary element $x \in X$:
$$
\begin{aligned}
x \in f^{-1}(A' \setminus B') &\iff f(x) \in A' \setminus B' \\
&\iff (f(x) \in A') \land (f(x) \notin B') \\
&\iff (x \in f^{-1}(A')) \land (x \notin f^{-1}(B')) \\
&\iff x \in f^{-1}(A') \setminus f^{-1}(B')
\end{aligned} \tag{1}
$$
Because each deduction in step 1 is an unbroken logical equivalence, the Principle of Extensionality confirms that: 
$$
\begin{gather}
f^{-1}(A' \setminus B') = f^{-1}(A') \setminus f^{-1}(B') \tag{2}
\end{gather}
$$

---
# Proposition 2

### Method 1: Algebraic Reduction via Set Difference
Because $f: X \to Y$ is a well-defined mapping from domain $X$ into codomain $Y$, every element of $X$ maps into $Y$. Consequently, the preimage of the total codomain is the total domain:
$$
\begin{gather}
f^{-1}(Y) = X \tag{3}
\end{gather}
$$
By the definition of the set complement in $Y$, $C_Y(A') = Y \setminus A'$. Applying the set difference identity established in Item 1 with $Y$ and $A'$:
$$
\begin{aligned}
f^{-1}(C_Y(A')) &= f^{-1}(Y \setminus A') \\
&= f^{-1}(Y) \setminus f^{-1}(A') \\
&= X \setminus f^{-1}(A') \\
&= C_X(f^{-1}(A'))
\end{aligned} \tag{4}
$$
Therefore, $f^{-1}(C_Y(A')) = C_X(f^{-1}(A'))$.

### Method 2: Pointwise Verification
Alternatively, the identity can be verified directly for an arbitrary element $x \in X$:
$$
\begin{aligned}
x \in f^{-1}(C_Y(A')) &\iff f(x) \in C_Y(A') \\
&\iff (f(x) \in Y) \land (f(x) \notin A') \\
&\iff (x \in X) \land (x \notin f^{-1}(A')) \\
&\iff x \in C_X(f^{-1}(A'))
\end{aligned} \tag{5}
$$
Because each deduction in step 5 is an unbroken logical equivalence, the Principle of Extensionality confirms that: 
$$
\begin{gather}
f^{-1}(C_Y(A')) = C_X(f^{-1}(A')) \tag{6}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
