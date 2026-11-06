---
dg-publish: true
---
Let $\mathbb{R}$ be the ordered field of real numbers, and let $\mathbb{N} \subseteq \mathbb{R}$ denote the set of natural numbers, defined as the minimal inductive subset of $\mathbb{R}$ containing $1$:
$$
\mathbb{N} := \bigcap \{ X \subseteq \mathbb{R} \mid 1 \in X \wedge (\forall x \in X, \, x + 1 \in X) \} \tag{1}
$$

Let $E \subseteq \mathbb{N}$ be a subset of the natural numbers satisfying the two foundational inductive hypotheses:
$$
1 \in E \tag{2}
$$
$$
\forall n \in \mathbb{N}, \quad (n \in E) \implies (n + 1 \in E) \tag{3}
$$
By step 2 and step 3, $E$ contains unity and contains the successor of each of its elements. Consequently, $E$ satisfies the defining conditions of an inductive subset of $\mathbb{R}$.

Let $\mathcal{I}_1 := \{ X \subseteq \mathbb{R} \mid 1 \in X \wedge (\forall x \in X, \, x + 1 \in X) \}$ denote the collection of all inductive subsets of $\mathbb{R}$ containing $1$. 

Because $E \in \mathcal{I}_1$, the definition of set intersection dictates that the intersection over the family $\mathcal{I}_1$ is contained within $E$:
$$
\bigcap_{X \in \mathcal{I}_1} X \subseteq E \tag{4}
$$
Substituting the axiomatic definition of $\mathbb{N}$ from step 1 into step 4 yields:
$$
\mathbb{N} \subseteq E \tag{5}
$$
Combining the initial hypothesis $E \subseteq \mathbb{N}$ with the reverse inclusion $\mathbb{N} \subseteq E$ from step 5 establishes, by the Principle of Extensionality:
$$
E = \mathbb{N} \tag{6}
$$
Therefore, any subset of $\mathbb{N}$ containing $1$ and closed under succession is identically equal to $\mathbb{N}$.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
