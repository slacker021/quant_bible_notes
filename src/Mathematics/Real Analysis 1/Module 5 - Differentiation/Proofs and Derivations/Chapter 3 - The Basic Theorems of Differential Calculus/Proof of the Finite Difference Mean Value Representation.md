---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a closed interval, let $n \in \mathbb{N}$, and let $f: [a, b] \to \mathbb{R}$ satisfy $f \in C^{n-1}[a, b]$ with $f^{(n)}(x)$ existing on $(a, b)$. For any step size $h \in \mathbb{R} \setminus \{0\}$ such that the points $x_0, x_0 + h, \dots, x_0 + nh$ belong to $[a, b]$, the forward finite difference operator of order $n$ is defined by:
$$
\begin{gather}
\Delta^n f(x_0; h^n) := \sum_{j=0}^n (-1)^{n-j} \binom{n}{j} f(x_0 + jh) \tag{1}
\end{gather}
$$

# Proposition 1
The $n$-th forward finite difference admits the representation:
$$
\begin{gather}
\Delta^n f(x_0; h^n) = f^{(n)}(\xi) h^n \tag{2}
\end{gather}
$$
for some intermediate point $\xi$ in the open interval $\operatorname{conv}^\circ(\{x_0, x_0 + nh\})$.

The claim is proven by mathematical induction on $n \in \mathbb{N}$.

**Base Case: $n = 1$.**
For $n = 1$, the first forward difference is:
$$
\begin{gather}
\Delta^1 f(x_0; h) = f(x_0 + h) - f(x_0) \tag{3}
\end{gather}
$$
Because $f$ is continuous on the closed interval between $x_0$ and $x_0 + h$ and differentiable on its open interior, applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] yields an intermediate point $\xi \in (x_0, x_0 + h)$ (or $(x_0 + h, x_0)$ if $h < 0$) such that:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = f'(\xi) h \tag{4}
\end{gather}
$$
Thus, $\Delta^1 f(x_0; h) = f^{(1)}(\xi) h^1$, establishing the base case.

**Induction Hypothesis:**
Assume that for an integer $m \ge 1$, whenever $g \in C^{m-1}$ has an $m$-th derivative $g^{(m)}$ on the convex hull of its nodes, $\Delta^m g(x_0; h^m) = g^{(m)}(\eta) h^m$ for some intermediate point $\eta$.

**Induction Step:**
Let $f \in C^m[a, b]$ with $f^{(m+1)}$ existing on $(a, b)$. Define the auxiliary function $F: [a, b - mh] \to \mathbb{R}$ by:
$$
\begin{gather}
F(t) := \Delta^m f(t; h^m) = \sum_{j=0}^m (-1)^{m-j} \binom{m}{j} f(t + jh) \tag{5}
\end{gather}
$$
By definition of the finite difference operator:
$$
\begin{gather}
\Delta^{m+1} f(x_0; h^{m+1}) = F(x_0 + h) - F(x_0) \tag{6}
\end{gather}
$$

Because $f \in C^m$, $F$ is continuously differentiable on the closed interval between $x_0$ and $x_0 + h$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] to $F$:
$$
\begin{gather}
F(x_0 + h) - F(x_0) = F'(\xi_1) h \tag{7}
\end{gather}
$$
for some $\xi_1$ lying strictly between $x_0$ and $x_0 + h$.

Differentiating step 5 with respect to $t$ via the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]]:
$$
\begin{gather}
F'(t) = \sum_{j=0}^m (-1)^{m-j} \binom{m}{j} f'(t + jh) = \Delta^m (f')(t; h^m) \tag{8}
\end{gather}
$$
Evaluating step 8 at $t = \xi_1$:
$$
\begin{gather}
F'(\xi_1) = \Delta^m (f')(\xi_1; h^m) \tag{9}
\end{gather}
$$

The derived function $g := f'$ satisfies $g \in C^{m-1}$ with $g^{(m)} = f^{(m+1)}$ existing. Applying the induction hypothesis to $g$ across the nodes $\{\xi_1, \xi_1 + h, \dots, \xi_1 + mh\}$ yields:
$$
\begin{gather}
\Delta^m (f')(\xi_1; h^m) = (f')^{(m)}(\xi) h^m = f^{(m+1)}(\xi) h^m \tag{10}
\end{gather}
$$
where $\xi$ lies strictly in the interior of the convex hull of $\{\xi_1, \xi_1 + mh\}$. 

Because $\xi_1$ lies strictly between $x_0$ and $x_0 + h$:
$$
\begin{gather}
\operatorname{conv}(\{\xi_1, \xi_1 + mh\}) \subset \operatorname{conv}^\circ(\{x_0, x_0 + (m + 1)h\}) \tag{11}
\end{gather}
$$
Substituting step 10 and step 9 into step 7:
$$
\begin{gather}
\Delta^{m+1} f(x_0; h^{m+1}) = \left(f^{(m+1)}(\xi) h^m\right) h = f^{(m+1)}(\xi) h^{m+1} \tag{12}
\end{gather}
$$
with $\xi \in \operatorname{conv}^\circ(\{x_0, x_0 + (m + 1)h\})$. This establishes Proposition 1 for all $n \in \mathbb{N}$.

---
# Proposition 2
If $f^{(n)}(x_0)$ exists at $x_0$, then:
$$
\begin{gather}
f^{(n)}(x_0) = \lim_{h \to 0} \frac{\Delta^n f(x_0; h^n)}{h^n} \tag{13}
\end{gather}
$$

Because $f$ possesses $n$ derivatives at $x_0$, applying [[Proof of the Local Taylor Formula with Peano Remainder|The Local Taylor Formula with Peano Remainder]] yields, for each index $j \in \{0, 1, \dots, n\}$:
$$
\begin{gather}
f(x_0 + jh) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (jh)^k + o(h^n) \quad \text{as } h \to 0 \tag{14}
\end{gather}
$$

Substituting the expansion of step 14 into the definition of $\Delta^n f(x_0; h^n)$ from step 1:
$$
\begin{gather}
\Delta^n f(x_0; h^n) = \sum_{j=0}^n (-1)^{n-j} \binom{n}{j} \left(\sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} j^k h^k + o(h^n)\right) \tag{15}
\end{gather}
$$
Interchanging the finite summations in step 15:
$$
\begin{gather}
\Delta^n f(x_0; h^n) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} h^k \left(\sum_{j=0}^n (-1)^{n-j} \binom{n}{j} j^k\right) + o(h^n) \sum_{j=0}^n (-1)^{n-j} \binom{n}{j} \tag{16}
\end{gather}
$$

From combinatorial analysis, the finite differences of monomials evaluated at zero satisfy:
$$
\begin{gather}
\sum_{j=0}^n (-1)^{n-j} \binom{n}{j} j^k = \begin{cases} 0, & 0 \le k < n \\ n!, & k = n \end{cases} \tag{17}
\end{gather}
$$
Substituting step 17 into step 16 eliminates every term for $0 \le k < n$:
$$
\begin{gather}
\Delta^n f(x_0; h^n) = \frac{f^{(n)}(x_0)}{n!} h^n (n!) + o(h^n) = f^{(n)}(x_0) h^n + o(h^n) \tag{18}
\end{gather}
$$

Dividing step 18 by $h^n \neq 0$:
$$
\begin{gather}
\frac{\Delta^n f(x_0; h^n)}{h^n} = f^{(n)}(x_0) + \frac{o(h^n)}{h^n} = f^{(n)}(x_0) + o(1) \tag{19}
\end{gather}
$$
Taking the limit of step 19 as $h \to 0$ proves the claim:
$$
\begin{gather}
\lim_{h \to 0} \frac{\Delta^n f(x_0; h^n)}{h^n} = f^{(n)}(x_0) \tag{20}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$