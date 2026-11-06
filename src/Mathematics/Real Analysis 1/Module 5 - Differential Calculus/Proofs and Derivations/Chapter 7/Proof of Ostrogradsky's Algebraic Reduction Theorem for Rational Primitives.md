---
dg-publish: true
---
Let $R(x) = \frac{P(x)}{Q(x)}$ be a proper rational fraction with real coefficients ($\deg P < \deg Q$).

Let $Q(x)$ factor over $\mathbb{C}$ as:
$$
\begin{gather}
Q(x) = a_n \prod_{k=1}^m (x - z_k)^{\alpha_k} \quad (\alpha_k \ge 1) \tag{1}
\end{gather}
$$

Define the greatest common divisor:
$$
\begin{gather}
Q_1(x) := \gcd\big(Q(x), Q'(x)\big) = \prod_{k=1}^m (x - z_k)^{\alpha_k - 1} \tag{2}
\end{gather}
$$
and define the quotient polynomial:
$$
\begin{gather}
Q_2(x) := \frac{Q(x)}{Q_1(x)} = a_n \prod_{k=1}^m (x - z_k) \tag{3}
\end{gather}
$$
Notice that $Q_2(x)$ has purely simple roots (all roots have multiplicity 1).

### Step 1: Decomposition Postulate
We seek an algebraic decomposition of the form:
$$
\begin{gather}
\int \frac{P(x)}{Q(x)} \, dx = \frac{P_1(x)}{Q_1(x)} + \int \frac{P_2(x)}{Q_2(x)} \, dx \tag{4}
\end{gather}
$$
where $P_1(x)$ and $P_2(x)$ are unknown real polynomials with degrees bounded by:
$$
\begin{gather}
\deg P_1 \le \deg Q_1 - 1, \quad \deg P_2 \le \deg Q_2 - 1 \tag{5}
\end{gather}
$$

### Step 2: Differentiating the Integral Identity
Differentiating both sides of equation (4) with respect to $x$:
$$
\begin{gather}
\frac{P(x)}{Q(x)} = \frac{d}{dx}\left( \frac{P_1(x)}{Q_1(x)} \right) + \frac{P_2(x)}{Q_2(x)} = \frac{P_1'(x) Q_1(x) - P_1(x) Q_1'(x)}{(Q_1(x))^2} + \frac{P_2(x)}{Q_2(x)} \tag{6}
\end{gather}
$$

Because $Q(x) = Q_1(x) Q_2(x)$, multiply both sides of equation (6) by $Q(x) = Q_1(x) Q_2(x)$:
$$
\begin{gather}
P(x) = \frac{P_1'(x) Q_1(x) - P_1(x) Q_1'(x)}{Q_1(x)} Q_2(x) + P_2(x) Q_1(x) \tag{7}
\end{gather}
$$

Because $Q_1(x) = \gcd(Q(x), Q'(x))$, the derivative $Q'(x)$ is divisible by $Q_1(x)$. 
Furthermore, differentiating $Q = Q_1 Q_2$ gives $Q' = Q_1' Q_2 + Q_1 Q_2'$. 
Therefore:
$$
\begin{gather}
\frac{Q'(x)}{Q_1(x)} = \frac{Q_1'(x) Q_2(x)}{Q_1(x)} + Q_2'(x) \tag{8}
\end{gather}
$$
which proves that the quotient $\frac{Q_1'(x) Q_2(x)}{Q_1(x)} = \frac{Q'(x)}{Q_1(x)} - Q_2'(x)$ is an algebraic polynomial!

Define the polynomial:
$$
\begin{gather}
T(x) := \frac{Q_1'(x) Q_2(x)}{Q_1(x)} \tag{9}
\end{gather}
$$

Substituting $T(x)$ into equation (7) produces the fundamental polynomial identity:
$$
\begin{gather}
P(x) = P_1'(x) Q_2(x) - P_1(x) T(x) + P_2(x) Q_1(x) \tag{10}
\end{gather}
$$

### Step 3: Existence and Uniqueness of Polynomials $P_1$ and $P_2$
Let $\deg Q_1 = n_1$ and $\deg Q_2 = n_2$, so that $\deg Q = n_1 + n_2$.

The polynomials $P_1(x)$ and $P_2(x)$ have degree at most $n_1 - 1$ and $n_2 - 1$, respectively. 
Representing $P_1(x)$ and $P_2(x)$ by their undetermined coefficients gives $n_1 + n_2 = \deg Q$ unknown real variables.

Equating coefficients of like powers of $x$ on both sides of equation (10) produces a system of $\deg Q$ linear algebraic equations in $\deg Q$ unknowns. 

By the uniqueness of partial fraction expansions, the homogeneous system ($P(x) \equiv 0$) forces $P_1(x) \equiv 0$ and $P_2(x) \equiv 0$. By linear algebra, a square linear system with a trivial kernel has a non-vanishing determinant, guaranteeing a unique solution for the coefficient polynomials $P_1(x)$ and $P_2(x)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
