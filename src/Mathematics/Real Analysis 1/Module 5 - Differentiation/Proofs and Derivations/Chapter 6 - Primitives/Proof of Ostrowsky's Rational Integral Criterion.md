---
dg-publish: true
---
Let $R(x) = \frac{P(x)}{Q(x)}$ be a proper rational function with real coefficients, where $P(x), Q(x) \in \mathbb{R}[x]$ are coprime polynomials and $\deg(P) < \deg(Q)$. Over the field of complex numbers $\mathbb{C}$, the monic denominator polynomial factors completely as:
$$
\begin{gather}
Q(x) = \prod_{j=1}^r (x - \alpha_j)^{m_j} \tag{1}
\end{gather}
$$
where $\alpha_1, \dots, \alpha_r \in \mathbb{C}$ are the distinct poles of $R(x)$ with corresponding algebraic multiplicities $m_j \ge 1$.

For each pole $\alpha_j$, the complex residue of $R(x)$ at $\alpha_j$ is defined by:
$$
\begin{gather}
\operatorname{Res}\big(R(x); \alpha_j\big) := \frac{1}{(m_j - 1)!} \lim_{z \to \alpha_j} \frac{d^{m_j - 1}}{dz^{m_j - 1}} \left[ (z - \alpha_j)^{m_j} R(z) \right] \tag{2}
\end{gather}
$$
which corresponds to the coefficient of $(x - \alpha_j)^{-1}$ in the partial fraction decomposition of $R(x)$ over $\mathbb{C}$.

---
# Proposition 1
Over the algebraically closed field $\mathbb{C}$, the rational function $R(x)$ admits the complex partial fraction expansion:
$$
\begin{gather}
R(x) = \sum_{j=1}^r \sum_{\ell=1}^{m_j} \frac{A_{j,\ell}}{(x - \alpha_j)^\ell} \tag{3}
\end{gather}
$$
where $A_{j,\ell} \in \mathbb{C}$ are uniquely determined constants. For each index $j \in \{1, \dots, r\}$, the coefficient corresponding to $\ell = 1$ is the residue:
$$
\begin{gather}
A_{j,1} = \operatorname{Res}\big(R(x); \alpha_j\big) \tag{4}
\end{gather}
$$
Term-by-term integration of the decomposition of step 3 demonstrates:
$$
\begin{gather}
\int R(x) \, dx = \sum_{j=1}^r A_{j,1} \ln(x - \alpha_j) + \sum_{j=1}^r \sum_{\ell=2}^{m_j} \frac{A_{j,\ell}}{(1 - \ell)(x - \alpha_j)^{\ell - 1}} + C \tag{5}
\end{gather}
$$
Notice that for every $\ell \ge 2$, the term:
$$
\begin{gather}
S(x) := \sum_{j=1}^r \sum_{\ell=2}^{m_j} \frac{A_{j,\ell}}{(1 - \ell)(x - \alpha_j)^{\ell - 1}} \tag{6}
\end{gather}
$$
is an algebraic rational function of $x$. Since $R(x)$ has real coefficients, its non-real poles and residues occur in complex conjugate pairs, ensuring that the purely rational part $S(x)$ is real-valued when restricted to real arguments $x \in \mathbb{R} \setminus \{\alpha_1, \dots, \alpha_r\}$.

---
# Proposition 2
Suppose that the residues of $R(x)$ at all its poles vanish identically:
$$
\begin{gather}
\operatorname{Res}\big(R(x); \alpha_j\big) = A_{j,1} = 0 \quad \forall j \in \{1, \dots, r\} \tag{7}
\end{gather}
$$
Substituting the vanishing condition of step 7 into the primitive formula of step 5 eliminates every logarithmic term:
$$
\begin{gather}
\sum_{j=1}^r A_{j,1} \ln(x - \alpha_j) \equiv 0 \tag{8}
\end{gather}
$$
Step 5 then collapses to:
$$
\begin{gather}
\int R(x) \, dx = S(x) + C \tag{9}
\end{gather}
$$
Because $S(x)$ is a rational function formed exclusively by negative powers of $(x - \alpha_j)$, it follows that $\int R(x) \, dx$ is an algebraic rational function $S(x) \in \mathbb{R}(x)$. This establishes the sufficiency of the residue condition.

---
# Proposition 3
Conversely, suppose that the primitive of $R(x)$ is an algebraic rational function. That is, there exists a rational function $F(x) = \frac{U(x)}{V(x)} \in \mathbb{C}(x)$ such that:
$$
\begin{gather}
F'(x) = R(x) \tag{10}
\end{gather}
$$
Let $\alpha \in \mathbb{C}$ be any pole of $F(x)$ of multiplicity $k \ge 1$. The Laurent series expansion of $F(x)$ centered at $\alpha$ takes the form:
$$
\begin{gather}
F(x) = \sum_{n=-k}^\infty c_n (x - \alpha)^n, \quad \text{with } c_{-k} \neq 0 \tag{11}
\end{gather}
$$
Differentiating the Laurent series term-by-term yields:
$$
\begin{gather}
R(x) = F'(x) = \sum_{n=-k}^\infty n c_n (x - \alpha)^{n-1} \tag{12}
\end{gather}
$$
Inspect the coefficient of $(x - \alpha)^{-1}$ in the series expansion of step 12. The power $(x - \alpha)^{-1}$ corresponds to the index setting $n - 1 = -1$, which implies $n = 0$. 

The coefficient associated with $n = 0$ in the differentiated series is:
$$
\begin{gather}
0 \cdot c_0 = 0 \tag{13}
\end{gather}
$$
Because the residue $\operatorname{Res}(R(x); \alpha)$ is by definition the coefficient of $(x - \alpha)^{-1}$ in the Laurent series of $R(x)$, step 13 establishes that:
$$
\begin{gather}
\operatorname{Res}\big(R(x); \alpha\big) = 0 \tag{14}
\end{gather}
$$
Since this holds for every pole $\alpha \in \{\alpha_1, \dots, \alpha_r\}$, all residues of $R(x)$ must vanish identically.

This establishes the necessity of the condition, completing the proof of Ostrowsky's criterion.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
