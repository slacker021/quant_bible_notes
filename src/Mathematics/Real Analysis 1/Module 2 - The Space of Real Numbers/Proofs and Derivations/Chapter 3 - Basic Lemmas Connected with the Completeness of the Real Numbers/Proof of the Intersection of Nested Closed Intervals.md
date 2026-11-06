---
dg-publish: true
---
Let $\mathcal{I}$ be a non-empty system of nested closed intervals in $\mathbb{R}$, meaning that for any two intervals $[a_1, b_1], [a_2, b_2] \in \mathcal{I}$, one interval is contained within the other:
$$
\begin{gather}
[a_1, b_1] \subseteq [a_2, b_2] \quad \lor \quad [a_2, b_2] \subseteq [a_1, b_1] \tag{1}
\end{gather}
$$
Define the sets of left and right endpoints of the intervals in $\mathcal{I}$:
$$
\begin{gather}
A := \{a \in \mathbb{R} \mid \exists b \in \mathbb{R}, \, [a, b] \in \mathcal{I}\} \quad \text{and} \quad B := \{b \in \mathbb{R} \mid \exists a \in \mathbb{R}, \, [a, b] \in \mathcal{I}\} \tag{2}
\end{gather}
$$
Because $\mathcal{I}$ is non-empty, both $A$ and $B$ are non-empty subsets of $\mathbb{R}$. For any $a_1 \in A$ and $b_2 \in B$, let $[a_1, b_1], [a_2, b_2] \in \mathcal{I}$ be their corresponding intervals. By step 1, either $[a_1, b_1] \subseteq [a_2, b_2]$ (which implies $a_2 \le a_1 \le b_1 \le b_2$) or $[a_2, b_2] \subseteq [a_1, b_1]$ (which implies $a_1 \le a_2 \le b_2 \le b_1$). In either case:
$$
\begin{gather}
a_1 \le b_2 \quad \forall a_1 \in A, \ \forall b_2 \in B \tag{3}
\end{gather}
$$
Step 3 demonstrates that $A$ is bounded above by every $b \in B$, and $B$ is bounded below by every $a \in A$. By the Least Upper Bound and Greatest Lower Bound Principles (see [[Chapter 1 - Basic Properties of Real Numbers]]), the supremum $\alpha := \sup A$ and the infimum $\beta := \inf B$ exist in $\mathbb{R}$. Furthermore, step 3 implies:
$$
\begin{gather}
a \le \alpha = \sup A \le \inf B = \beta \le b \quad \forall [a, b] \in \mathcal{I} \tag{4}
\end{gather}
$$
Because $\alpha \le \beta$, the closed interval $[\alpha, \beta]$ is well-defined and non-empty. It remains to establish the set equality $[\alpha, \beta] = \bigcap_{I \in \mathcal{I}} I$ via mutual inclusion:
1. **Forward Inclusion ($[\alpha, \beta] \subseteq \bigcap_{I \in \mathcal{I}} I$):** Let $x \in [\alpha, \beta]$, so that $\alpha \le x \le \beta$. For every interval $[a, b] \in \mathcal{I}$, step 4 gives $a \le \alpha \le x \le \beta \le b$, which implies $x \in [a, b]$ for all $[a, b] \in \mathcal{I}$. Thus, $x \in \bigcap_{I \in \mathcal{I}} I$.
2. **Reverse Inclusion ($\bigcap_{I \in \mathcal{I}} I \subseteq [\alpha, \beta]$):** Let $x \in \bigcap_{I \in \mathcal{I}} I$. Then $a \le x \le b$ holds for every $[a, b] \in \mathcal{I}$, which means $x$ is an upper bound for $A$ and a lower bound for $B$. By the definitions of the least upper bound $\alpha = \sup A$ and greatest lower bound $\beta = \inf B$, it follows that $\alpha \le x \le \beta$, so $x \in [\alpha, \beta]$.

Combining both inclusions establishes the identity:
$$
\begin{gather}
[\alpha, \beta] = \bigcap_{I \in \mathcal{I}} I \tag{5}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
