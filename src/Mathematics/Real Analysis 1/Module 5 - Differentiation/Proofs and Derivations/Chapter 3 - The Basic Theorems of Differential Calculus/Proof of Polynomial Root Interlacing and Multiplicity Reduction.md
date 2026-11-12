---
dg-publish: true
---
Let $P(x) \in \mathbb{R}[x]$ be a non-constant polynomial with real coefficients, having degree $\deg(P) = d \ge 1$.

# Proposition 1
Let $x_1 < x_2$ be two consecutive real roots of $P(x)$, such that $P(x_1) = 0$, $P(x_2) = 0$, and:
$$
\begin{gather}
P(x) \neq 0, \quad \forall x \in (x_1, x_2) \tag{1}
\end{gather}
$$

Because $P$ is a polynomial, it is infinitely differentiable on $\mathbb{R}$. In particular, $P$ is continuous on $[x_1, x_2]$ and differentiable on $(x_1, x_2)$ with $P(x_1) = P(x_2) = 0$. By virtue of [[Proof of Rolle's Theorem|Rolle's Mean Value Theorem]], there exists at least one intermediate point $\xi \in (x_1, x_2)$ such that:
$$
\begin{gather}
P'(\xi) = 0 \tag{2}
\end{gather}
$$

To establish that the total number of real roots of $P'(x)$ in $(x_1, x_2)$, counted with algebraic multiplicity, is odd, observe that by step 1 and the [[Chapter 2 - Properties of Continuous Functions#The Generalized Darboux Intermediate-Value Property|Intermediate-Value Property]], the continuous function $P(x)$ cannot change sign on $(x_1, x_2)$. Without loss of generality, assume that $P(x) > 0$ for all $x \in (x_1, x_2)$ (if $P(x) < 0$, the identical deduction applies to $-P(x)$).

Let $m_1 \ge 1$ denote the multiplicity of $x_1$ as a root of $P(x)$, and let $m_2 \ge 1$ denote the multiplicity of $x_2$. Factoring the polynomial around $x_1$ and $x_2$ gives:
$$
\begin{gather}
P(x) = (x - x_1)^{m_1} Q_1(x) \tag{3}
\end{gather}
$$
$$
\begin{gather}
P(x) = (x_2 - x)^{m_2} Q_2(x) \tag{4}
\end{gather}
$$
where $Q_1, Q_2$ are polynomials with $Q_1(x_1) \neq 0$ and $Q_2(x_2) \neq 0$. Because $P(x) > 0$ on $(x_1, x_2)$, taking $x \to x_1^+$ in step 3 forces $Q_1(x_1) > 0$. Differentiating step 3 yields:
$$
\begin{gather}
P'(x) = m_1(x - x_1)^{m_1-1} Q_1(x) + (x - x_1)^{m_1} Q'_1(x) = (x - x_1)^{m_1-1} \big(m_1 Q_1(x) + (x - x_1) Q'_1(x)\big) \tag{5}
\end{gather}
$$
Because $m_1 Q_1(x_1) > 0$, by continuity there exists a right-sided neighborhood $(x_1, x_1 + \delta_1)$ on which the bracketed factor remains strictly positive. For all $x \in (x_1, x_1 + \delta_1)$, $(x - x_1)^{m_1-1} > 0$, which implies:
$$
\begin{gather}
P'(x) > 0, \quad \forall x \in (x_1, x_1 + \delta_1) \tag{6}
\end{gather}
$$

Similarly, taking $x \to x_2^-$ in step 4 forces $Q_2(x_2) > 0$. Differentiating step 4 gives:
$$
\begin{gather}
P'(x) = -m_2(x_2 - x)^{m_2-1} Q_2(x) + (x_2 - x)^{m_2} Q'_2(x) = (x_2 - x)^{m_2-1} \big(-m_2 Q_2(x) + (x_2 - x) Q'_2(x)\big) \tag{7}
\end{gather}
$$
Because $-m_2 Q_2(x_2) < 0$, there exists a left-sided neighborhood $(x_2 - \delta_2, x_2)$ on which:
$$
\begin{gather}
P'(x) < 0, \quad \forall x \in (x_2 - \delta_2, x_2) \tag{8}
\end{gather}
$$

Let the real roots of $P'(x)$ lying strictly within $(x_1, x_2)$ be denoted by $\xi_1 < \xi_2 < \dots < \xi_k$, with corresponding multiplicities $\mu_1, \mu_2, \dots, \mu_k \in \mathbb{N}$. Factor $P'(x)$ over the reals as:
$$
\begin{gather}
P'(x) = S(x) \prod_{j=1}^k (x - \xi_j)^{\mu_j} \tag{9}
\end{gather}
$$
where $S(x)$ is a polynomial possessing no roots in $(x_1, x_2)$. By the intermediate-value property, $S(x)$ maintains a constant sign throughout $[x_1, x_2]$. 

For $x \in (x_1, \xi_1)$, each factor $(x - \xi_j)$ is strictly negative, so:
$$
\begin{gather}
\operatorname{sgn}\left(\prod_{j=1}^k (x - \xi_j)^{\mu_j}\right) = \prod_{j=1}^k (-1)^{\mu_j} = (-1)^{\sum_{j=1}^k \mu_j} \tag{10}
\end{gather}
$$
For $x \in (\xi_k, x_2)$, each factor $(x - \xi_j)$ is strictly positive, so:
$$
\begin{gather}
\operatorname{sgn}\left(\prod_{j=1}^k (x - \xi_j)^{\mu_j}\right) = \prod_{j=1}^k (+1)^{\mu_j} = +1 \tag{11}
\end{gather}
$$
From step 6 and step 8, $P'(x)$ changes sign between the left of $(x_1, x_2)$ and the right of $(x_1, x_2)$:
$$
\begin{gather}
\frac{P'(x)|_{x \in (\xi_k, x_2)}}{P'(x)|_{x \in (x_1, \xi_1)}} < 0 \implies \frac{+1}{(-1)^{\sum_{j=1}^k \mu_j}} = -1 \tag{12}
\end{gather}
$$
Step 12 forces:
$$
\begin{gather}
(-1)^{\sum_{j=1}^k \mu_j} = -1 \implies \sum_{j=1}^k \mu_j \equiv 1 \pmod 2 \tag{13}
\end{gather}
$$
Thus, the total multiplicity of the roots of $P'(x)$ in $(x_1, x_2)$ is odd, guaranteeing an odd number (and hence at least one) of roots.

---
# Proposition 2
Let $x_0 \in \mathbb{R}$ be a root of $P(x)$ of multiplicity $m \ge 2$. By definition of polynomial root multiplicity, $P(x)$ admits the unique factorization:
$$
\begin{gather}
P(x) = (x - x_0)^m Q(x) \tag{14}
\end{gather}
$$
where $Q(x) \in \mathbb{R}[x]$ is a polynomial satisfying the non-vanishing condition:
$$
\begin{gather}
Q(x_0) \neq 0 \tag{15}
\end{gather}
$$

Differentiating step 14 using the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]] and the power rule:
$$
\begin{gather}
P'(x) = \frac{d}{dx}\left((x - x_0)^m\right) Q(x) + (x - x_0)^m Q'(x) \tag{16}
\end{gather}
$$
$$
\begin{gather}
P'(x) = m(x - x_0)^{m-1} Q(x) + (x - x_0)^m Q'(x) \tag{17}
\end{gather}
$$

Factoring out the common power $(x - x_0)^{m-1}$ in step 17:
$$
\begin{gather}
P'(x) = (x - x_0)^{m-1} \big(m Q(x) + (x - x_0) Q'(x)\big) \tag{18}
\end{gather}
$$

Define the auxiliary polynomial factor $H(x) \in \mathbb{R}[x]$ by:
$$
\begin{gather}
H(x) := m Q(x) + (x - x_0) Q'(x) \tag{19}
\end{gather}
$$
Evaluating $H(x)$ at the anchor point $x_0$:
$$
\begin{gather}
H(x_0) = m Q(x_0) + (x_0 - x_0) Q'(x_0) = m Q(x_0) \tag{20}
\end{gather}
$$
Because $m \ge 2 \ge 1$ and $Q(x_0) \neq 0$ by step 15, step 20 shows:
$$
\begin{gather}
H(x_0) \neq 0 \tag{21}
\end{gather}
$$

Step 18 and step 21 establish that $(x - x_0)^{m-1}$ is the exact maximal power of $(x - x_0)$ dividing $P'(x)$. Therefore, $x_0$ is a root of $P'(x)$ of multiplicity exactly $(m - 1)$.

---
# Proposition 3
Suppose that all roots of $P(x)$ are real and distinct. Let the degree of $P(x)$ be $\deg(P) = d \ge 1$.

Because all roots are real and distinct, $P(x)$ possesses exactly $d$ distinct real roots, which may be labeled in strictly ascending order:
$$
\begin{gather}
x_1 < x_2 < x_3 < \dots < x_{d-1} < x_d \tag{22}
\end{gather}
$$
Each root $x_k$ has multiplicity $m = 1$.

For each integer $k \in \{1, 2, \dots, d - 1\}$, the pair $x_k$ and $x_{k+1}$ are consecutive real roots of $P(x)$. Applying Proposition 1 to each interval $(x_k, x_{k+1})$ guarantees the existence of at least one real root $\xi_k$ of $P'(x)$ such that:
$$
\begin{gather}
\xi_k \in (x_k, x_{k+1}), \quad \forall k \in \{1, 2, \dots, d - 1\} \tag{23}
\end{gather}
$$

Because the open intervals $(x_k, x_{k+1})$ are mutually disjoint:
$$
\begin{gather}
x_1 < \xi_1 < x_2 < \xi_2 < x_3 < \dots < x_{d-1} < \xi_{d-1} < x_d \tag{24}
\end{gather}
$$
the collection $\{\xi_1, \xi_2, \dots, \xi_{d-1}\}$ forms a set of $(d - 1)$ pairwise distinct real roots of $P'(x)$.

The derivative polynomial $P'(x)$ has degree:
$$
\begin{gather}
\deg(P') = \deg(P) - 1 = d - 1 \tag{25}
\end{gather}
$$
By the Fundamental Theorem of Algebra, a non-zero polynomial of degree $d - 1$ possesses at most $(d - 1)$ complex roots, counted with algebraic multiplicity. 

Because step 24 exhibits $(d - 1)$ distinct real roots, it follows that:
1. All roots of $P'(x)$ are real;
2. Each root $\xi_k$ is simple (multiplicity 1);
3. The roots of $P'(x)$ strictly interlace the roots of $P(x)$ as shown in step 24.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$