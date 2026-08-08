---
dg-publish: true
---
# Additive Abelian Group Structure of $\mathbb{Z}$
To verify that $(\mathbb{Z}, +)$ forms an abelian group, one checks the group axioms inherited from the ambient field $(\mathbb{R}, +, \cdot)$:
1. **Closure:** For all $m, n \in \mathbb{Z}$, the sum $m + n$ belongs to $\mathbb{Z}$. This was established as the [[Proof that Integer Operations Yield Integers|Algebraic Closure of the Integers]]).
2. **Associativity and Commutativity:** Because $\mathbb{Z} \subset \mathbb{R}$, addition in $\mathbb{Z}$ automatically satisfies $(m + n) + k = m + (n + k)$ and $m + n = n + m$ for all $m, n, k \in \mathbb{Z}$ by the field axioms of $\mathbb{R}$.
3. **Identity Element:** By definition of $\mathbb{Z}$, the additive neutral element $0$ belongs to $\mathbb{Z}$ and satisfies $m + 0 = 0 + m = m$ for all $m \in \mathbb{Z}$.
4. **Inverse Elements:** By construction of $\mathbb{Z} = \mathbb{N} \cup \{0\} \cup (-\mathbb{N})$, for every $m \in \mathbb{Z}$, its additive inverse $-m$ also resides in $\mathbb{Z}$ and satisfies $m + (-m) = 0$.

Thus, $(\mathbb{Z}, +)$ is an abelian group.

# Failure of Multiplicative Group Structure on $\mathbb{Z}$ and $\mathbb{Z} \setminus \{0\}$
For $(\mathbb{Z}, \cdot)$ or $(\mathbb{Z} \setminus \{0\}, \cdot)$ to form a group, every element $m$ of the set would need to possess a multiplicative inverse $m^{-1}$ within that same set. In $\mathbb{R}$, the number $0$ has no multiplicative inverse, immediately disqualifying $\mathbb{Z}$.

Now consider $\mathbb{Z} \setminus \{0\}$. For $m = 1$ and $m = -1$, the multiplicative inverses are $1^{-1} = 1 \in \mathbb{Z}$ and $(-1)^{-1} = -1 \in \mathbb{Z}$. Suppose, however, that $m \in \mathbb{Z} \setminus \{0, 1, -1\}$.
1. **Case 1 ($m \in \mathbb{N}$ with $m \ne 1$):** By [[Proof of the Properties of Natural Numbers|Proposition 3 of the Properties of Natural Numbers]], every natural number $m \ne 1$ satisfies $m \ge 2 > 1 > 0$. Because $m \cdot m^{-1} = 1 > 0$, the order axioms of $\mathbb{R}$ dictate that $m^{-1} > 0$, and multiplying the strict inequality $1 < m$ by $m^{-1} > 0$ yields
   $$
   \begin{gather}
   0 < m^{-1} < 1 \tag{1}
   \end{gather}
   $$
   Because every positive integer belongs to $\mathbb{N}$ and satisfies $n \ge 1$, no integer lies in the open interval $]0, 1[$. Consequently, $m^{-1} \notin \mathbb{Z}$.
2. **Case 2 ($m \in -\mathbb{N}$ with $m \ne -1$):** Here, $-m \in \mathbb{N}$ with $-m \ne 1$. By step 1, $0 < (-m)^{-1} < 1$, which implies $-1 < m^{-1} < 0$. Because no integer lies strictly between $-1$ and $0$, it follows that $m^{-1} \notin \mathbb{Z}$.

Therefore, $\mathbb{Z} \setminus \{0\}$ is not closed under multiplicative inversion and does not form a multiplicative group.
$$
\begin{gather}
\textbf{Q.E.D}
\end{gather}
$$
