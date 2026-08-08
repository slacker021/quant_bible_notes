---
dg-publish: true
---
Let $X$ be an arbitrary set.
# Weak Cardinality Dominance
Define the mapping $f: X \to \mathcal{P}(X)$ by assigning to each element $x \in X$ its corresponding singleton set:
$$
\begin{gather}
f(x) := \{x\} \tag{1}
\end{gather}
$$
Let $x_1, x_2 \in X$ and assume that $f(x_1) = f(x_2)$. By the definition of $f$:
$$
\begin{gather}
\{x_1\} = \{x_2\} \tag{2}
\end{gather}
$$
By the Principle of Extensionality, two singleton sets are equal if and only if their constituent elements are equal:
$$
\begin{gather}
x_1 = x_2 \tag{3}
\end{gather}
$$
Thus, $f$ is an injective mapping from $X$ into $\mathcal{P}(X)$, establishing that: 
$$
\begin{gather}
|X| \le |\mathcal{P}(X)| \tag{4}
\end{gather}
$$

# Strict Cardinality Separation
Let $g: X \to \mathcal{P}(X)$ be an arbitrary mapping. To demonstrate that $g$ cannot be surjective, it suffices to construct a subset $D \in \mathcal{P}(X)$ that does not belong to the image $\operatorname{ran}(g)$. 

Construct the diagonal set $D$ consisting of all elements in $X$ that do not belong to the subset assigned to them under $g$:
$$
\begin{gather}
D := \{x \in X \mid x \notin g(x)\} \tag{5}
\end{gather}
$$
Because every element of $D$ belongs to $X$, it follows that $D \subseteq X$, which establishes that $D \in \mathcal{P}(X)$. 

To establish that $D \notin \operatorname{ran}(g)$, proceed by contradiction. Assume that $g$ is surjective. Under this hypothesis, every element in the codomain $\mathcal{P}(X)$ must possess a preimage in $X$. In particular, there must exist some witness element $d \in X$ such that: 
$$
\begin{gather}
g(d) = D \tag{6}
\end{gather}
$$
Evaluating the membership of $d$ relative to the set $D$ produces two exhaustive cases:
$$
\begin{gather}
\text{Case 1: If } d \in D, \text{ the definition of } D \text{ requires that } d \notin g(d). \\[2mm]
\text{Because } g(d) = D, \text{ this implies } d \notin D, \text{ producing a contradiction.} \\[3.5mm]
\text{Case 2: If } d \notin D, \text{ then because } g(d) = D, \text{ it follows that } d \notin g(d). \\[2mm]
\text{By the definition of } D, \text{ the condition } d \notin g(d) \text{ requires that } d \in D, \text{ producing a contradiction.} \tag{7}
\end{gather}
$$
In both cases, a logical contradiction arises ($d \in D \iff d \notin D$). Consequently, the hypothesis that $g(d) = D$ for some $d \in X$ is false. The set $D$ has no preimage under $g$, which proves that no arbitrary mapping $g: X \to \mathcal{P}(X)$ can be surjective. 

Because no bijection between $X$ and $\mathcal{P}(X)$ can exist, it follows that: 
$$
\begin{gather}
|X| \neq |\mathcal{P}(X)| \tag{8}
\end{gather}
$$
Combining step 4 and step 8 confirms Cantor's Theorem:
$$
\begin{gather}
|X| < |\mathcal{P}(X)| \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
