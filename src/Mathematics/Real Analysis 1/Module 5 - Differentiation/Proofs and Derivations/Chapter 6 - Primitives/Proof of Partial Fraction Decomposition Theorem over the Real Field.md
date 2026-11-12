---
dg-publish: true
---
Let $\mathbb{R}[x]$ denote the ring of polynomials in the indeterminate $x$ with real coefficients. Let $P(x), Q(x) \in \mathbb{R}[x]$ be polynomials such that $Q(x)$ is monic, non-zero, and $\deg(P) < \deg(Q)$. 

By virtue of the Fundamental Theorem of Algebra and the property of complex conjugate root pairing for real polynomials, the polynomial $Q(x)$ admits a unique factorization into monic irreducible factors over the field of real numbers $\mathbb{R}$:
$$
\begin{gather}
Q(x) = \prod_{j=1}^r (x - a_j)^{m_j} \prod_{k=1}^s (x^2 + p_k x + q_k)^{n_k} \tag{1}
\end{gather}
$$
where $a_1, \dots, a_r \in \mathbb{R}$ are distinct real roots with multiplicities $m_j \in \mathbb{N}_{\ge 1}$, and each quadratic factor $x^2 + p_k x + q_k \in \mathbb{R}[x]$ is irreducible over $\mathbb{R}$ (meaning its discriminant satisfies $\Delta_k = p_k^2 - 4q_k < 0$), distinct from all other quadratic factors, with multiplicity $n_k \in \mathbb{N}_{\ge 1}$.

---
# Proposition 1
Let $Q_1(x), Q_2(x) \in \mathbb{R}[x]$ be two non-zero polynomials that are coprime, so that their greatest common divisor satisfies:
$$
\begin{gather}
\gcd(Q_1(x), Q_2(x)) = 1 \tag{2}
\end{gather}
$$
Let $P(x) \in \mathbb{R}[x]$ be any polynomial satisfying $\deg(P) < \deg(Q_1 Q_2) = \deg(Q_1) + \deg(Q_2)$. 

Because $\mathbb{R}[x]$ is a principal ideal domain and the polynomials $Q_1(x)$ and $Q_2(x)$ are coprime, Bézout's Identity in $\mathbb{R}[x]$ guarantees the existence of two polynomials $A(x), B(x) \in \mathbb{R}[x]$ such that:
$$
\begin{gather}
A(x) Q_1(x) + B(x) Q_2(x) = 1 \tag{3}
\end{gather}
$$
Multiplying both sides of the identity in step 3 by the polynomial $P(x)$ yields:
$$
\begin{gather}
P(x) = P(x) A(x) Q_1(x) + P(x) B(x) Q_2(x) \tag{4}
\end{gather}
$$
Dividing both sides of step 4 by the product $Q_1(x) Q_2(x)$ gives the fractional decomposition:
$$
\begin{gather}
\frac{P(x)}{Q_1(x) Q_2(x)} = \frac{P(x) B(x)}{Q_1(x)} + \frac{P(x) A(x)}{Q_2(x)} \tag{5}
\end{gather}
$$

Now perform polynomial Euclidean division on the numerator polynomials $P(x) B(x)$ and $P(x) A(x)$ by $Q_1(x)$ and $Q_2(x)$, respectively. There exist unique polynomials $S_1(x), P_1(x), S_2(x), P_2(x) \in \mathbb{R}[x]$ such that:
$$
\begin{gather}
P(x) B(x) = S_1(x) Q_1(x) + P_1(x), \quad \text{with } \deg(P_1) < \deg(Q_1) \tag{6}
\end{gather}
$$
and
$$
\begin{gather}
P(x) A(x) = S_2(x) Q_2(x) + P_2(x), \quad \text{with } \deg(P_2) < \deg(Q_2) \tag{7}
\end{gather}
$$
Substituting equations 6 and 7 into the decomposition of step 5 gives:
$$
\begin{gather}
\frac{P(x)}{Q_1(x) Q_2(x)} = S_1(x) + S_2(x) + \frac{P_1(x)}{Q_1(x)} + \frac{P_2(x)}{Q_2(x)} \tag{8}
\end{gather}
$$
Rearranging the terms in step 8 shows that:
$$
\begin{gather}
S_1(x) + S_2(x) = \frac{P(x)}{Q_1(x) Q_2(x)} - \frac{P_1(x)}{Q_1(x)} - \frac{P_2(x)}{Q_2(x)} \tag{9}
\end{gather}
$$
The right-hand side of step 9 is a rational fraction whose numerator has degree strictly less than $\deg(Q_1 Q_2)$:
$$
\begin{gather}
\deg(P) < \deg(Q_1 Q_2), \quad \deg(P_1 Q_2) = \deg(P_1) + \deg(Q_2) < \deg(Q_1) + \deg(Q_2) = \deg(Q_1 Q_2) \tag{10}
\end{gather}
$$
and
$$
\begin{gather}
\deg(P_2 Q_1) = \deg(P_2) + \deg(Q_1) < \deg(Q_2) + \deg(Q_1) = \deg(Q_1 Q_2) \tag{11}
\end{gather}
$$
Consequently, the right-hand side of step 9 tends to 0 as $|x| \to \infty$. But $S_1(x) + S_2(x)$ is a polynomial. The only polynomial that tends to 0 at infinity is the zero polynomial:
$$
\begin{gather}
S_1(x) + S_2(x) \equiv 0 \tag{12}
\end{gather}
$$
Therefore, equation 8 reduces precisely to:
$$
\begin{gather}
\frac{P(x)}{Q_1(x) Q_2(x)} = \frac{P_1(x)}{Q_1(x)} + \frac{P_2(x)}{Q_2(x)} \tag{13}
\end{gather}
$$
with $\deg(P_1) < \deg(Q_1)$ and $\deg(P_2) < \deg(Q_2)$. By induction on the number of pairwise coprime factors, any proper rational fraction $\frac{P(x)}{Q(x)}$ decomposes into a sum of proper rational fractions whose denominators are the primary factors $(x - a_j)^{m_j}$ and $(x^2 + p_k x + q_k)^{n_k}$.

---
# Proposition 2
Let $a \in \mathbb{R}$ and $m \in \mathbb{N}_{\ge 1}$. Let $P_1(x) \in \mathbb{R}[x]$ be a polynomial with $\deg(P_1) < m$. 

Expand $P_1(x)$ as a Taylor polynomial centered at the point $x = a$:
$$
\begin{gather}
P_1(x) = \sum_{\ell=0}^{m-1} c_\ell (x - a)^\ell, \quad \text{where } c_\ell = \frac{P_1^{(\ell)}(a)}{\ell!} \in \mathbb{R} \tag{14}
\end{gather}
$$
Dividing both sides of step 14 by $(x - a)^m$ yields:
$$
\begin{gather}
\frac{P_1(x)}{(x - a)^m} = \sum_{\ell=0}^{m-1} \frac{c_\ell}{(x - a)^{m - \ell}} \tag{15}
\end{gather}
$$
Setting the index transformation $k = m - \ell \in \{1, \dots, m\}$ and defining the real coefficients $A_k := c_{m - k} \in \mathbb{R}$ expresses step 15 as:
$$
\begin{gather}
\frac{P_1(x)}{(x - a)^m} = \sum_{k=1}^m \frac{A_k}{(x - a)^k} \tag{16}
\end{gather}
$$
which gives the decomposition of the linear component into simple partial fractions.

---
# Proposition 3
Let $x^2 + p x + q \in \mathbb{R}[x]$ be an irreducible real quadratic polynomial with $p^2 - 4q < 0$, and let $n \in \mathbb{N}_{\ge 1}$. Let $P_2(x) \in \mathbb{R}[x]$ be a polynomial with $\deg(P_2) < 2n$.

Repeatedly apply Euclidean division of polynomials by the quadratic divisor $D(x) := x^2 + p x + q$. First, dividing $P_2(x)$ by $D(x)^{n-1}$ yields:
$$
\begin{gather}
P_2(x) = Q_{n-1}(x) D(x)^{n-1} + R_{n-1}(x), \quad \text{with } \deg(R_{n-1}) < 2(n-1) \tag{17}
\end{gather}
$$
Because $\deg(P_2) < 2n$, the quotient polynomial $Q_{n-1}(x)$ satisfies $\deg(Q_{n-1}) < 2n - 2(n-1) = 2$, which means $Q_{n-1}(x) = B_n x + C_n$ for unique real constants $B_n, C_n \in \mathbb{R}$.

Proceeding inductively on $R_{n-1}(x)$ by dividing successsively by powers of $D(x)$ produces the unique polynomial expansion:
$$
\begin{gather}
P_2(x) = \sum_{r=1}^n (B_r x + C_r) \big(x^2 + p x + q\big)^{r - 1} \tag{18}
\end{gather}
$$
where each pair $B_r, C_r \in \mathbb{R}$ consists of uniquely determined real coefficients.

Dividing both sides of step 18 by $D(x)^n = (x^2 + p x + q)^n$ demonstrates:
$$
\begin{gather}
\frac{P_2(x)}{(x^2 + p x + q)^n} = \sum_{r=1}^n \frac{B_r x + C_r}{(x^2 + p x + q)^{n - r + 1}} \tag{19}
\end{gather}
$$
Re-indexing the sum by setting $\ell = n - r + 1 \in \{1, \dots, n\}$ establishes that:
$$
\begin{gather}
\frac{P_2(x)}{(x^2 + p x + q)^n} = \sum_{\ell=1}^n \frac{B_\ell' x + C_\ell'}{(x^2 + p x + q)^\ell} \tag{20}
\end{gather}
$$
Combining Propositions 1, 2, and 3 establishes the existence of the decomposition:
$$
\begin{gather}
\frac{P_0(x)}{Q(x)} = \sum_{j=1}^r \sum_{\ell=1}^{m_j} \frac{A_{j,\ell}}{(x - a_j)^\ell} + \sum_{k=1}^s \sum_{r=1}^{n_k} \frac{B_{k,r} x + C_{k,r}}{(x^2 + p_k x + q_k)^r} \tag{21}
\end{gather}
$$

---
# Proposition 4
To establish uniqueness, consider the vector space $V$ of proper rational fractions with fixed denominator $Q(x)$:
$$
\begin{gather}
V = \left\{ \frac{P(x)}{Q(x)} : P \in \mathbb{R}[x], \; \deg(P) < \deg(Q) \right\} \tag{22}
\end{gather}
$$
The dimension of $V$ over $\mathbb{R}$ is precisely:
$$
\begin{gather}
\dim_\mathbb{R}(V) = \deg(Q) = \sum_{j=1}^r m_j + 2 \sum_{k=1}^s n_k \tag{23}
\end{gather}
$$
Consider the linear subspace $W$ formed by all linear combinations of the simple partial fractions:
$$
\begin{gather}
\mathcal{B} = \bigcup_{j=1}^r \left\{ \frac{1}{(x - a_j)^\ell} \right\}_{\ell=1}^{m_j} \cup \bigcup_{k=1}^s \left\{ \frac{x}{(x^2 + p_k x + q_k)^r}, \; \frac{1}{(x^2 + p_k x + q_k)^r} \right\}_{r=1}^{n_k} \tag{24}
\end{gather}
$$
The number of elements in the family $\mathcal{B}$ is:
$$
\begin{gather}
|\mathcal{B}| = \sum_{j=1}^r m_j + 2 \sum_{k=1}^s n_k = \deg(Q) \tag{25}
\end{gather}
$$
Propositions 1, 2, and 3 demonstrate that the span of $\mathcal{B}$ contains all of $V$, which implies $\operatorname{span}(\mathcal{B}) = V$. Because the cardinality $|\mathcal{B}|$ equals the dimension $\dim_\mathbb{R}(V)$, the spanning set $\mathcal{B}$ is automatically a linear basis of $V$. 

Consequently, the coordinates of any proper fraction $\frac{P_0(x)}{Q(x)} \in V$ with respect to the basis $\mathcal{B}$ are uniquely determined real numbers, establishing both existence and uniqueness of the real partial fraction decomposition.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
