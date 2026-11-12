---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ have $x_0$ as an accumulation point, and suppose there exists a polynomial $P(x) = \sum_{k=0}^n c_k (x - x_0)^k$ of degree at most $n$ such that:
$$
\begin{gather}
f(x) - P(x) = o\big((x - x_0)^n\big) \quad \text{as } E \ni x \to x_0 \tag{1}
\end{gather}
$$

**Part 1: Uniqueness of the Asymptotic Polynomial.**
Suppose there exists another polynomial $Q(x) = \sum_{k=0}^n d_k (x - x_0)^k$ of degree at most $n$ satisfying the identical asymptotic approximation property:
$$
\begin{gather}
f(x) - Q(x) = o\big((x - x_0)^n\big) \quad \text{as } E \ni x \to x_0 \tag{2}
\end{gather}
$$

Define the difference polynomial $R(x) := P(x) - Q(x)$. Subtracting step 2 from step 1:
$$
\begin{gather}
R(x) = P(x) - Q(x) = \big(f(x) - Q(x)\big) - \big(f(x) - P(x)\big) \tag{3}
\end{gather}
$$
By the algebra of Landau symbols:
$$
\begin{gather}
R(x) = o\big((x - x_0)^n\big) - o\big((x - x_0)^n\big) = o\big((x - x_0)^n\big) \quad \text{as } x \to x_0 \tag{4}
\end{gather}
$$

Expressing the polynomial $R(x)$ in terms of the coefficient differences $a_k := c_k - d_k$:
$$
\begin{gather}
R(x) = \sum_{k=0}^n a_k (x - x_0)^k \tag{5}
\end{gather}
$$

To prove that $a_k = 0$ for all $k \in \{0, 1, \dots, n\}$, assume for the sake of contradiction that at least one coefficient is non-zero. Let $m \in \{0, 1, \dots, n\}$ denote the smallest index such that $a_m \neq 0$:
$$
\begin{gather}
a_0 = a_1 = \dots = a_{m-1} = 0 \quad \text{and} \quad a_m \neq 0 \tag{6}
\end{gather}
$$

Factoring $(x - x_0)^m$ out of step 5 gives:
$$
\begin{gather}
R(x) = \sum_{k=m}^n a_k (x - x_0)^k = (x - x_0)^m \left(a_m + \sum_{k=m+1}^n a_k (x - x_0)^{k-m}\right) \tag{7}
\end{gather}
$$
Dividing step 7 by $(x - x_0)^m$ for $x \neq x_0$:
$$
\begin{gather}
\frac{R(x)}{(x - x_0)^m} = a_m + \sum_{k=m+1}^n a_k (x - x_0)^{k-m} \tag{8}
\end{gather}
$$

Taking the limit of step 8 as $x \to x_0$:
$$
\begin{gather}
\lim_{x \to x_0} \frac{R(x)}{(x - x_0)^m} = a_m + 0 = a_m \tag{9}
\end{gather}
$$

On the other hand, step 4 implies that $\lim_{x \to x_0} \frac{R(x)}{(x - x_0)^n} = 0$. Because $m \le n$, the difference exponent $(n - m)$ is non-negative:
$$
\begin{gather}
\frac{R(x)}{(x - x_0)^m} = \frac{R(x)}{(x - x_0)^n} (x - x_0)^{n-m} \tag{10}
\end{gather}
$$
Taking the limit of step 10 as $x \to x_0$:
- If $m < n$:
$$
\begin{gather}
\lim_{x \to x_0} \frac{R(x)}{(x - x_0)^m} = \left(\lim_{x \to x_0} \frac{R(x)}{(x - x_0)^n}\right) \left(\lim_{x \to x_0} (x - x_0)^{n-m}\right) = 0 \times 0 = 0 \tag{11}
\end{gather}
$$
- If $m = n$:
$$
\begin{gather}
\lim_{x \to x_0} \frac{R(x)}{(x - x_0)^m} = \lim_{x \to x_0} \frac{R(x)}{(x - x_0)^n} = 0 \tag{12}
\end{gather}
$$

Comparing step 9 with step 11 and step 12 yields $a_m = 0$, which directly contradicts the definition of $m$ in step 6. Therefore, no non-zero coefficient can exist:
$$
\begin{gather}
a_k = 0 \implies c_k = d_k, \quad \forall k \in \{0, 1, \dots, n\} \tag{13}
\end{gather}
$$
The polynomial $P(x)$ is thus uniquely determined.

**Part 2: Identification with Taylor Coefficients.**
Suppose now that $f$ possesses $n$ derivatives at $x_0$. By virtue of [[Proof of the Local Taylor Formula with Peano Remainder|The Local Taylor Formula with Peano Remainder]], the Taylor polynomial:
$$
\begin{gather}
T_n(x) := \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k \tag{14}
\end{gather}
$$
satisfies the asymptotic property:
$$
\begin{gather}
f(x) - T_n(x) = o\big((x - x_0)^n\big) \quad \text{as } x \to x_0 \tag{15}
\end{gather}
$$

By the uniqueness established in Part 1, any polynomial $P(x) = \sum_{k=0}^n c_k (x - x_0)^k$ satisfying step 1 must coincide identically with $T_n(x)$. Equating corresponding coefficients:
$$
\begin{gather}
c_k = \frac{f^{(k)}(x_0)}{k!}, \quad \forall k \in \{0, 1, \dots, n\} \tag{16}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$