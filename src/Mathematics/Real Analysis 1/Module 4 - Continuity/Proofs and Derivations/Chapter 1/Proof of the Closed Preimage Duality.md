---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ and let $f: E \to \mathbb{R}$.

Recall that a subset $K \subseteq E$ is relatively closed in $E$ if and only if there exists a closed set $F_0 \subseteq \mathbb{R}$ such that $K = F_0 \cap E$. This topological condition is equivalent to the statement that the relative complement $E \setminus K$ is relatively open in $E$:
$$
\begin{gather}
K = F_0 \cap E \iff E \setminus K = (\mathbb{R} \setminus F_0) \cap E \tag{1}
\end{gather}
$$
where $\mathbb{R} \setminus F_0$ is an open subset of $\mathbb{R}$.

Furthermore, for any target subset $S \subseteq \mathbb{R}$, the complete preimage commutes with set complementation:
$$
\begin{gather}
f^{-1}(\mathbb{R} \setminus S) = \{x \in E \mid f(x) \in \mathbb{R} \setminus S\} = \{x \in E \mid f(x) \notin S\} = E \setminus f^{-1}(S) \tag{2}
\end{gather}
$$

**Necessity ($\implies$ Continuity implies Closed Preimages):**
Assume that the function $f$ is continuous on $E$.

Let $F \subseteq \mathbb{R}$ be an arbitrary closed subset of the codomain. The complement $G := \mathbb{R} \setminus F$ is an open subset of $\mathbb{R}$. 

By the [[Proof of the Global Open Preimage Characterization]], the complete preimage of every open set in $\mathbb{R}$ is relatively open in $E$. Consequently, the preimage:
$$
\begin{gather}
f^{-1}(G) = f^{-1}(\mathbb{R} \setminus F) \tag{3}
\end{gather}
$$
is relatively open in $E$. 

Applying the complementation identity of step 2 to step 3 yields:
$$
\begin{gather}
E \setminus f^{-1}(F) \text{ is relatively open in } E \tag{4}
\end{gather}
$$

By virtue of step 1, the complement in $E$ of a relatively open set is relatively closed. Therefore:
$$
\begin{gather}
f^{-1}(F) = E \setminus \big(E \setminus f^{-1}(F)\big) \text{ is relatively closed in } E \tag{5}
\end{gather}
$$

**Sufficiency ($\impliedby$ Closed Preimages implies Continuity):**
Conversely, assume that for every closed subset $F \subseteq \mathbb{R}$, the complete preimage $f^{-1}(F)$ is relatively closed in $E$.

To verify that $f$ is continuous on $E$, by the [[Proof of the Global Open Preimage Characterization]] it suffices to demonstrate that the complete preimage $f^{-1}(G)$ is relatively open in $E$ for every open set $G \subseteq \mathbb{R}$.

Let $G \subseteq \mathbb{R}$ be an arbitrary open set. The complement $F := \mathbb{R} \setminus G$ is closed in $\mathbb{R}$. By the operating hypothesis:
$$
\begin{gather}
f^{-1}(F) = f^{-1}(\mathbb{R} \setminus G) \text{ is relatively closed in } E \tag{6}
\end{gather}
$$

Applying the complementation rule of step 2 transforms step 6 into:
$$
\begin{gather}
E \setminus f^{-1}(G) \text{ is relatively closed in } E \tag{7}
\end{gather}
$$

Applying the equivalence of step 1 once again demonstrates that the relative complement in $E$ of a relatively closed set is relatively open:
$$
\begin{gather}
f^{-1}(G) = E \setminus \big(E \setminus f^{-1}(G)\big) \text{ is relatively open in } E \tag{8}
\end{gather}
$$

Because $G \subseteq \mathbb{R}$ was an arbitrary open set, the Global Open Preimage Characterization guarantees that $f$ is continuous on $E$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$