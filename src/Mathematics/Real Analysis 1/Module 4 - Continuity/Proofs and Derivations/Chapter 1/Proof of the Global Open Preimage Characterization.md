---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ and let $f: E \to \mathbb{R}$.

**Necessity ($\implies$ Global Continuity implies Open Preimages):**
Assume that the function $f$ is continuous at every point of the domain $E$.

Let $G \subseteq \mathbb{R}$ be an arbitrary open subset of the codomain. Consider the complete preimage:
$$
\begin{gather}
f^{-1}(G) := \{x \in E \mid f(x) \in G\} \tag{1}
\end{gather}
$$

If $f^{-1}(G) = \emptyset$, then setting $\Omega := \emptyset$ demonstrates that $f^{-1}(G) = \emptyset \cap E$. Because the empty set is open in $\mathbb{R}$, $f^{-1}(G)$ is relatively open in $E$.

Now assume that $f^{-1}(G)$ is non-empty. Let $a \in f^{-1}(G)$ be an arbitrary element. By step 1, $f(a) \in G$. 

Because $G$ is open in $\mathbb{R}$, $G$ serves as an open neighborhood of $f(a)$. Applying the topological neighborhood formulation of pointwise continuity (Pillar 2 of the [[Proof of the Master Equivalence Architecture of Continuity]]) at the point $a \in E$, there exists an open neighborhood $U_a(a)$ of $a$ in $\mathbb{R}$ such that:
$$
\begin{gather}
f(U_a(a) \cap E) \subseteq G \tag{2}
\end{gather}
$$

Taking preimages on both sides of step 2 establishes that:
$$
\begin{gather}
U_a(a) \cap E \subseteq f^{-1}(G) \tag{3}
\end{gather}
$$

Define the ambient set $\Omega \subseteq \mathbb{R}$ as the union of these neighborhoods over all points in the preimage:
$$
\begin{gather}
\Omega := \bigcup_{a \in f^{-1}(G)} U_a(a) \tag{4}
\end{gather}
$$

Because each $U_a(a)$ is an open subset of $\mathbb{R}$, and an arbitrary union of open sets is open, $\Omega$ is an open set in $\mathbb{R}$. 

Intersecting $\Omega$ with the domain $E$ yields:
$$
\begin{gather}
\Omega \cap E = \left(\bigcup_{a \in f^{-1}(G)} U_a(a)\right) \cap E = \bigcup_{a \in f^{-1}(G)} \big(U_a(a) \cap E\big) \tag{5}
\end{gather}
$$

For each $a \in f^{-1}(G)$, because $a \in U_a(a) \cap E$, the inclusion $f^{-1}(G) \subseteq \Omega \cap E$ holds. Conversely, by step 3, each constituent subset satisfies $U_a(a) \cap E \subseteq f^{-1}(G)$, which guarantees that $\bigcup_{a \in f^{-1}(G)} (U_a(a) \cap E) \subseteq f^{-1}(G)$. Combining these inclusions demonstrates that:
$$
\begin{gather}
f^{-1}(G) = \Omega \cap E \tag{6}
\end{gather}
$$

Because $\Omega$ is open in $\mathbb{R}$, step 6 proves that $f^{-1}(G)$ is relatively open in $E$.

**Sufficiency ($\impliedby$ Open Preimages implies Global Continuity):**
Conversely, assume that for every open set $G \subseteq \mathbb{R}$, the preimage $f^{-1}(G)$ is relatively open in $E$:
$$
\begin{gather}
\forall G \subseteq \mathbb{R} \text{ open}, \ \exists \Omega \subseteq \mathbb{R} \text{ open such that } f^{-1}(G) = \Omega \cap E \tag{7}
\end{gather}
$$

Let $a \in E$ be an arbitrary domain point, and let $V(f(a))$ be an arbitrary open neighborhood of $f(a)$ in $\mathbb{R}$. 

Because $V(f(a))$ is open in $\mathbb{R}$, applying step 7 guarantees the existence of an open set $\Omega \subseteq \mathbb{R}$ such that:
$$
\begin{gather}
f^{-1}(V(f(a))) = \Omega \cap E \tag{8}
\end{gather}
$$

Because $f(a) \in V(f(a))$, the point $a$ belongs to $f^{-1}(V(f(a))) = \Omega \cap E$, so $a \in \Omega$. 

Because $\Omega$ is an open subset of $\mathbb{R}$ containing $a$, set the open neighborhood $U(a) := \Omega$. Evaluating the direct image under $f$ gives:
$$
\begin{gather}
f(U(a) \cap E) = f(\Omega \cap E) = f\big(f^{-1}(V(f(a)))\big) \subseteq V(f(a)) \tag{9}
\end{gather}
$$

Step 9 satisfies the topological neighborhood criterion for continuity at $a$. Because $a \in E$ was arbitrary, $f$ is continuous on the entirety of $E$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$