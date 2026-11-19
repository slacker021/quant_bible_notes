---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f: [a, b] \to \mathbb{R}$ be a bounded function, and let $P = \{x_0, x_1, \dots, x_n\}$ and $P'$ be partitions of $[a, b]$ such that $P'$ is a refinement of $P$, denoted $P \subseteq P'$.

---
# Case 1
Suppose first that the refinement $P'$ contains exactly one additional node beyond those in $P$, so that:
$$
\begin{gather}
P' = P \cup \{x^*\} \quad \text{with } x^* \notin P \tag{1}
\end{gather}
$$

Because $a = x_0 < x_1 < \dots < x_n = b$, the new node $x^*$ must fall strictly within the interior of one of the constituent subintervals of $P$. Consequently, there exists a unique index $k \in \{1, \dots, n\}$ such that:
$$
\begin{gather}
x_{k-1} < x^* < x_k \tag{2}
\end{gather}
$$

The introduction of $x^*$ divides the subinterval $\Delta_k = [x_{k-1}, x_k]$ into two contiguous subintervals:
$$
\begin{gather}
\Delta_k' := [x_{k-1}, x^*] \quad \text{and} \quad \Delta_k'' := [x^*, x_k] \tag{3}
\end{gather}
$$
having respective lengths:
$$
\begin{gather}
\Delta x_k' := x^* - x_{k-1} > 0 \quad \text{and} \quad \Delta x_k'' := x_k - x^* > 0 \tag{4}
\end{gather}
$$
which satisfy the additive relation:
$$
\begin{gather}
\Delta x_k' + \Delta x_k'' = (x^* - x_{k-1}) + (x_k - x^*) = x_k - x_{k-1} = \Delta x_k \tag{5}
\end{gather}
$$

Define the local extrema of $f$ on these subintervals:
$$
\begin{gather}
M_k := \sup_{x \in \Delta_k} f(x), \quad M_k' := \sup_{x \in \Delta_k'} f(x), \quad M_k'' := \sup_{x \in \Delta_k''} f(x) \tag{6}
\end{gather}
$$
and
$$
\begin{gather}
m_k := \inf_{x \in \Delta_k} f(x), \quad m_k' := \inf_{x \in \Delta_k'} f(x), \quad m_k'' := \inf_{x \in \Delta_k''} f(x) \tag{7}
\end{gather}
$$

Because $\Delta_k' \subseteq \Delta_k$ and $\Delta_k'' \subseteq \Delta_k$, the fundamental properties of the supremum and infimum on subsets ensure:
$$
\begin{gather}
M_k' \le M_k \quad \text{and} \quad M_k'' \le M_k \tag{8}
\end{gather}
$$
and
$$
\begin{gather}
m_k' \ge m_k \quad \text{and} \quad m_k'' \ge m_k \tag{9}
\end{gather}
$$

For all subintervals $\Delta_i = [x_{i-1}, x_i]$ with $i \neq k$, the endpoints and lengths are identical in $P$ and $P'$. Consequently, the terms associated with $i \neq k$ in the Darboux sums are unchanged. 

Evaluating the difference between the upper Darboux sum on $P$ and that on $P'$:
$$
\begin{gather}
S(f; P) - S(f; P') = M_k \Delta x_k - \big( M_k' \Delta x_k' + M_k'' \Delta x_k'' \big) \tag{10}
\end{gather}
$$

Substituting the identity $\Delta x_k = \Delta x_k' + \Delta x_k''$ from step 5 into step 10:
$$
\begin{gather}
S(f; P) - S(f; P') = M_k (\Delta x_k' + \Delta x_k'') - \big( M_k' \Delta x_k' + M_k'' \Delta x_k'' \big) \tag{11}
\end{gather}
$$

Regrouping terms in step 11:
$$
\begin{gather}
S(f; P) - S(f; P') = (M_k - M_k') \Delta x_k' + (M_k - M_k'') \Delta x_k'' \tag{12}
\end{gather}
$$

By step 8, $M_k - M_k' \ge 0$ and $M_k - M_k'' \ge 0$. Because $\Delta x_k' > 0$ and $\Delta x_k'' > 0$, both products in step 12 are non-negative real numbers. Hence:
$$
\begin{gather}
S(f; P) - S(f; P') \ge 0 \implies S(f; P') \le S(f; P) \tag{13}
\end{gather}
$$

Similarly, evaluating the difference between the lower Darboux sum on $P'$ and that on $P$:
$$
\begin{gather}
s(f; P') - s(f; P) = \big( m_k' \Delta x_k' + m_k'' \Delta x_k'' \big) - m_k \Delta x_k \tag{14}
\end{gather}
$$

Substituting $\Delta x_k = \Delta x_k' + \Delta x_k''$ into step 14:
$$
\begin{gather}
s(f; P') - s(f; P) = (m_k' - m_k) \Delta x_k' + (m_k'' - m_k) \Delta x_k'' \tag{15}
\end{gather}
$$

By step 9, $m_k' - m_k \ge 0$ and $m_k'' - m_k \ge 0$. Because the subinterval lengths are strictly positive, step 15 yields:
$$
\begin{gather}
s(f; P') - s(f; P) \ge 0 \implies s(f; P) \le s(f; P') \tag{16}
\end{gather}
$$
---
# Case 2
Now consider the general case where $P'$ contains $p$ additional points beyond $P$, where $p := |P' \setminus P| \in \mathbb{N}_0$.

If $p = 0$, then $P' = P$, so $s(f; P) = s(f; P')$ and $S(f; P') = S(f; P)$, satisfying the inequalities directly with equality.

If $p \ge 1$, enumerate the added partition points in an arbitrary order:
$$
\begin{gather}
P' \setminus P = \{y_1, y_2, \dots, y_p\} \tag{17}
\end{gather}
$$

Construct an ascending chain of partitions:
$$
\begin{gather}
P^{(0)} := P, \quad P^{(j)} := P^{(j-1)} \cup \{y_j\} \quad \text{for } j \in \{1, \dots, p\} \tag{18}
\end{gather}
$$
so that $P^{(p)} = P'$.

At each stage $j \in \{1, \dots, p\}$, the partition $P^{(j)}$ is obtained from $P^{(j-1)}$ by the addition of exactly one point, namely $y_j$. Therefore, applying the single-point refinement results of step 13 and step 16 to each step of the chain:
$$
\begin{gather}
s(f; P^{(j-1)}) \le s(f; P^{(j)}) \quad \text{and} \quad S(f; P^{(j)}) \le S(f; P^{(j-1)}) \tag{19}
\end{gather}
$$
for every $j \in \{1, \dots, p\}$.

Applying transitivity of the order relation on $\mathbb{R}$ across the finite chain of step 19 yields:
$$
\begin{gather}
s(f; P) = s(f; P^{(0)}) \le s(f; P^{(1)}) \le \dots \le s(f; P^{(p)}) = s(f; P') \tag{20}
\end{gather}
$$
and
$$
\begin{gather}
S(f; P') = S(f; P^{(p)}) \le \dots \le S(f; P^{(1)}) \le S(f; P^{(0)}) = S(f; P) \tag{21}
\end{gather}
$$

The relations of step 20 and step 21 establish that $s(f; P) \le s(f; P')$ and $S(f; P') \le S(f; P)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
