---
dg-publish: true
---
By definition, the set of rational numbers $\mathbb{Q}$ consists of all real numbers that can be expressed as a quotient $p/q$, where the numerator $p$ is an integer ($p \in \mathbb{Z}$) and the denominator $q$ is a natural number ($q \in \mathbb{N} := \{1, 2, 3, \dots\}$).

First, observe that the set of integers $\mathbb{Z} = \{0\} \cup \mathbb{N} \cup (-\mathbb{N})$ is countable. Explicitly, the mapping $h: \mathbb{N} \to \mathbb{Z}$ defined by setting $h(1) := 0$, $h(2k) := k$, and $h(2k + 1) := -k$ for each $k \in \mathbb{N}$ enumerates $\mathbb{Z}$ without repetition as $0, 1, -1, 2, -2, \dots$, establishing a bijection between $\mathbb{N}$ and $\mathbb{Z}$.

Next, for each fixed denominator $q \in \mathbb{N}$, define $A_q$ to be the set of all rational numbers expressible with denominator $q$:
$$
\begin{gather}
A_q := \left\{ \frac{p}{q} \ \middle|\ p \in \mathbb{Z} \right\} \tag{1}
\end{gather}
$$
For any fixed $q \in \mathbb{N}$, consider the mapping $f_q: \mathbb{Z} \to A_q$ defined by $f_q(p) := p/q$. By definition of $A_q$ in step 1, $f_q$ is surjective, and because $q \neq 0$, multiplying $p_1 / q = p_2 / q$ by $q$ yields $p_1 = p_2$, confirming that $f_q$ is injective. Thus, $f_q$ is a bijection between $\mathbb{Z}$ and $A_q$. Composing $h: \mathbb{N} \to \mathbb{Z}$ with $f_q: \mathbb{Z} \to A_q$ yields a bijection $f_q \circ h: \mathbb{N} \to A_q$, which proves that each set $A_q$ is countably infinite.

Because every rational number has at least one representation $p/q$ with $p \in \mathbb{Z}$ and $q \in \mathbb{N}$, the entire set of rational numbers is the union of the sets $A_q$ over all denominators $q \in \mathbb{N}$:
$$
\begin{gather}
\mathbb{Q} = \bigcup_{q=1}^\infty A_q \tag{2}
\end{gather}
$$
Although the sets $A_q$ in step 2 are not mutually disjoint (since equivalent fractions such as $\frac{1}{2} \in A_2$ and $\frac{2}{4} \in A_4$ represent the same rational number), step 2 expresses $\mathbb{Q}$ as a countable union of at most countable sets. By the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]], the union $\mathbb{Q}$ is at most countable. 

Furthermore, setting $q = 1$ yields the inclusion $\mathbb{N} \subset \mathbb{Z} = A_1 \subset \mathbb{Q}$. Because $\mathbb{Q}$ contains the infinite subset $\mathbb{N}$, the [[Proof of the Subsets of Countable Sets|Proposition on Subsets of Countable Sets]] dictates that $\mathbb{Q}$ cannot be finite. Because $\mathbb{Q}$ is at most countable and infinite, the set of rational numbers $\mathbb{Q}$ is countably infinite (countable).
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
