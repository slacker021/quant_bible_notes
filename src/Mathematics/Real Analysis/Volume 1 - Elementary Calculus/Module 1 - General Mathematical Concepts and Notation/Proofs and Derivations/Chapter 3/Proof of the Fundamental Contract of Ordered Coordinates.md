---
dg-publish: true
---
Let $x, y, u,$ and $v$ be arbitrary mathematical objects.
# Sufficiency
Assume that $(x = u) \wedge (y = v)$. Substituting $u$ for $x$ and $v$ for $y$ directly into the Kuratowski definition of the ordered pair $(x, y)$ yields: 
$$
\begin{gather}
(x, y) = \{\{x\}, \{x, y\}\} = \{\{u\}, \{u, v\}\} \tag{1}
\end{gather}
$$
By the definition of the ordered pair $(u, v)$, the right-hand side of step 1 satisfies: 
$$
\begin{gather}
\{\{u\}, \{u, v\}\} = (u, v) \tag{2}
\end{gather}
$$
Therefore: 
$$
\begin{gather}
(x = u) \wedge (y = v) \implies (x, y) = (u, v) \tag{3}
\end{gather}
$$

# Necessity
Assume that $(x, y) = (u, v)$. By the Kuratowski definition of ordered pairs, this equality translates to the set identity:
$$
\begin{gather}
\{\{x\}, \{x, y\}\} = \{\{u\}, \{u, v\}\} \tag{4}
\end{gather}
$$
To establish that $x = u$ and $y = v$, evaluate two exhaustive cases based on whether $x$ equals $y$:

**Case 1: Assume $x = y$.**
If $x = y$, the left-hand set simplifies to: 
$$
\begin{gather}
\{\{x\}, \{x, x\}\} = \{\{x\}, \{x\}\} = \{\{x\}\} \tag{5}
\end{gather}
$$
By step 4, this forces the right-hand set to collapse to the same singleton: 
$$
\begin{gather}
\{\{u\}, \{u, v\}\} = \{\{x\}\} \tag{6}
\end{gather}
$$
By the [[Chapter 2 - Naive Set Theory|Principle of Extensionality]], every element of the set in step 6 must be equal to $\{x\}$. Consequently: 
$$
\begin{gather}
\{u\} = \{x\} \implies u = x \tag{7}
\end{gather}
$$
$$
\begin{gather}
\{u, v\} = \{x\} \implies u = x \quad \wedge \quad v = x \tag{8}
\end{gather}
$$
Combining step 7 and step 8 with the case hypothesis $x = y$ establishes that: 
$$
\begin{gather}
x = u \quad \wedge \quad y = v \tag{9}
\end{gather}
$$

**Case 2: Assume $x \neq y$.**
Because $x \neq y$, the set $\{x\}$ contains exactly one element while $\{x, y\}$ contains exactly two distinct elements. Thus, the collection $\{\{x\}, \{x, y\}\}$ contains two distinct member sets:
$$
\begin{gather}
\{x\} \neq \{x, y\} \tag{10}
\end{gather}
$$
By the set equality in step 4, the right-hand side must also contain two distinct member sets, which requires $\{u\} \neq \{u, v\}$, guaranteeing that $u \neq v$.

By the Principle of Extensionality applied to step 4, the singleton $\{x\}$ on the left-hand side must equal one of the elements on the right-hand side. To prove that $\{x\} = \{u\}$, proceed by contradiction. Assume that: 
$$
\begin{gather}
\{x\} = \{u, v\} \tag{11}
\end{gather}
$$
Step 11 implies that $u = x$ and $v = x$, which forces $u = v$, directly contradicting the established fact that $u \neq v$. Therefore, the hypothesis in step 11 is false, which leaves the unique identification:
$$
\begin{gather}
\{x\} = \{u\} \implies x = u \tag{12}
\end{gather}
$$
Because step 4 is an equality of two-element collections and $\{x\} = \{u\}$, the remaining elements must be equal:
$$
\begin{gather}
\{x, y\} = \{u, v\} \tag{13}
\end{gather}
$$
Substituting $u = x$ from step 12 into step 13 yields: 
$$
\begin{gather}
\{x, y\} = \{x, v\} \tag{14}
\end{gather}
$$
Because $y \in \{x, y\}$, step 14 requires that $y \in \{x, v\}$, which implies that $(y = x) \lor (y = v)$. Because the case hypothesis establishes that $x \neq y$, $y$ cannot equal $x$. Therefore, it must be that: 
$$
\begin{gather}
y = v \tag{15}
\end{gather}
$$
Combining step 12 and step 15 confirms that $x = u$ and $y = v$ in Case 2.

Because both cases hold, step 3 and step 15 establish the complete logical equivalence:
$$
\begin{gather}
(x, y) = (u, v) \iff (x = u) \wedge (y = v) \tag{16}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
