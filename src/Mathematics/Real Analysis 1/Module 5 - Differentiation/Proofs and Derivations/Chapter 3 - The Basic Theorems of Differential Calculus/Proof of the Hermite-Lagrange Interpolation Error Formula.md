---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, let $x_1 < x_2 < \dots < x_p$ be $p$ distinct interpolation nodes in $I$, and let $n_1, n_2, \dots, n_p \in \mathbb{N}$ be positive integer multiplicities whose sum is:
$$
\begin{gather}
\sum_{i=1}^p n_i = n \tag{1}
\end{gather}
$$
Let $f \in C^n(I)$, and let $H_{n-1}(x)$ denote the unique Hermite osculating interpolation polynomial of degree at most $n - 1$ satisfying the matching conditions:
$$
\begin{gather}
H_{n-1}^{(k)}(x_i) = f^{(k)}(x_i), \quad \forall k \in \{0, 1, \dots, n_i - 1\}, \quad \forall i \in \{1, 2, \dots, p\} \tag{2}
\end{gather}
$$

Let $x \in I$ be an arbitrary evaluation point. 

**Case 1: $x \in \{x_1, x_2, \dots, x_p\}$.**
If $x$ coincides with one of the interpolation nodes, say $x = x_j$ for some $j \in \{1, 2, \dots, p\}$, then because $n_j \ge 1$:
$$
\begin{gather}
f(x_j) - H_{n-1}(x_j) = 0 \tag{3}
\end{gather}
$$
Furthermore, the nodal product vanishes at $x = x_j$:
$$
\begin{gather}
\prod_{i=1}^p (x_j - x_i)^{n_i} = 0 \tag{4}
\end{gather}
$$
Both sides of the interpolation error formula vanish identically, and the equality holds for any choice of $\xi \in I$.

**Case 2: $x \notin \{x_1, x_2, \dots, x_p\}$.**
Assume that $x$ is distinct from all interpolation nodes. Define the monic nodal polynomial $\omega: \mathbb{R} \to \mathbb{R}$ of degree $n$ by:
$$
\begin{gather}
\omega(t) := \prod_{i=1}^p (t - x_i)^{n_i} \tag{5}
\end{gather}
$$
Because $x \neq x_i$ for all $i \in \{1, 2, \dots, p\}$, evaluating step 5 at $t = x$ yields:
$$
\begin{gather}
\omega(x) \neq 0 \tag{6}
\end{gather}
$$

Being a monic polynomial of degree $n$, the polynomial $\omega(t)$ expands as:
$$
\begin{gather}
\omega(t) = t^n + a_{n-1} t^{n-1} + \dots + a_1 t + a_0 \tag{7}
\end{gather}
$$
Differentiating step 7 exactly $n$ times:
$$
\begin{gather}
\omega^{(n)}(t) = n!, \quad \forall t \in \mathbb{R} \tag{8}
\end{gather}
$$

Let $J \subset I$ denote the smallest closed compact interval containing the set of $(p + 1)$ points $\{x, x_1, x_2, \dots, x_p\}$. Define the auxiliary function $F: J \to \mathbb{R}$ of the variable $t \in J$ by:
$$
\begin{gather}
F(t) := f(t) - H_{n-1}(t) - \frac{f(x) - H_{n-1}(x)}{\omega(x)} \omega(t) \tag{9}
\end{gather}
$$

The zeros of $F(t)$ across $J$ are determined as follows:
- At $t = x$:
$$
\begin{gather}
F(x) = f(x) - H_{n-1}(x) - \frac{f(x) - H_{n-1}(x)}{\omega(x)} \omega(x) = 0 \tag{10}
\end{gather}
$$
- At each interpolation node $x_i$ ($1 \le i \le p$), differentiating step 9 up to order $k \in \{0, 1, \dots, n_i - 1\}$:
$$
\begin{gather}
F^{(k)}(x_i) = f^{(k)}(x_i) - H_{n-1}^{(k)}(x_i) - \frac{f(x) - H_{n-1}(x)}{\omega(x)} \omega^{(k)}(x_i) \tag{11}
\end{gather}
$$
By step 2, $f^{(k)}(x_i) - H_{n-1}^{(k)}(x_i) = 0$. Furthermore, because $x_i$ is a root of $\omega(t)$ of multiplicity $n_i$, all derivatives $\omega^{(k)}(x_i)$ vanish for $0 \le k < n_i$:
$$
\begin{gather}
\omega^{(k)}(x_i) = 0, \quad \forall k \in \{0, 1, \dots, n_i - 1\} \tag{12}
\end{gather}
$$
Substituting these evaluations into step 11 yields:
$$
\begin{gather}
F^{(k)}(x_i) = 0 - 0 = 0, \quad \forall k \in \{0, 1, \dots, n_i - 1\}, \quad \forall i \in \{1, 2, \dots, p\} \tag{13}
\end{gather}
$$

Step 10 and step 13 establish that the function $F(t)$ possesses roots of multiplicity $n_i$ at each $x_i$, yielding $\sum_{i=1}^p n_i = n$ roots, and an additional root at $t = x$. Because $x$ is distinct from all $x_i$, $F(t)$ possesses at least $(n + 1)$ roots (counted with multiplicity) in the interval $J$.

Because $f \in C^n(J)$ and both $H_{n-1}$ and $\omega$ are smooth polynomials, $F \in C^n(J)$. By virtue of [[Proof of the Generalized Multi-Point Rolle Theorem|The Generalized Multi-Point Rolle Theorem]], the $n$-th derivative $F^{(n)}$ must vanish at least once in the open interior of $J$:
$$
\begin{gather}
\exists \xi \in \operatorname{int}(J) \quad \text{such that} \quad F^{(n)}(\xi) = 0 \tag{14}
\end{gather}
$$

Differentiating step 9 exactly $n$ times with respect to $t$:
$$
\begin{gather}
F^{(n)}(t) = f^{(n)}(t) - H_{n-1}^{(n)}(t) - \frac{f(x) - H_{n-1}(x)}{\omega(x)} \omega^{(n)}(t) \tag{15}
\end{gather}
$$
Because $H_{n-1}(t)$ is a polynomial of degree at most $n - 1$, its $n$-th derivative vanishes identically:
$$
\begin{gather}
H_{n-1}^{(n)}(t) \equiv 0 \tag{16}
\end{gather}
$$
Substituting step 16 and step 8 into step 15 evaluated at $t = \xi$:
$$
\begin{gather}
F^{(n)}(\xi) = f^{(n)}(\xi) - 0 - \frac{f(x) - H_{n-1}(x)}{\omega(x)} n! = 0 \tag{17}
\end{gather}
$$

Rearranging step 17:
$$
\begin{gather}
\frac{f(x) - H_{n-1}(x)}{\omega(x)} n! = f^{(n)}(\xi) \tag{18}
\end{gather}
$$
Multiplying step 18 by $\frac{\omega(x)}{n!}$ yields:
$$
\begin{gather}
f(x) - H_{n-1}(x) = \frac{\omega(x)}{n!} f^{(n)}(\xi) = \frac{\prod_{i=1}^p (x - x_i)^{n_i}}{n!} f^{(n)}(\xi) \tag{19}
\end{gather}
$$
where $\xi$ lies in the interior of the smallest interval containing $\{x, x_1, x_2, \dots, x_p\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$