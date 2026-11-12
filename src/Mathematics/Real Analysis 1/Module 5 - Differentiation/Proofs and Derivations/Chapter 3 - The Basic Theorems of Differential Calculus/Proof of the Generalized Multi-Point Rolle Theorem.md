---
dg-publish: true
---
Let $n \in \mathbb{N}$, and let $f: [a, b] \to \mathbb{R}$ be a function satisfying $f \in C^{n-1}[a, b]$, such that the $n$-th derivative $f^{(n)}(x)$ exists for every point $x \in (a, b)$. Suppose that $f$ vanishes at $(n + 1)$ distinct points in $[a, b]$, arranged in strictly ascending order:
$$
\begin{gather}
a \le x_0 < x_1 < x_2 < \dots < x_{n-1} < x_n \le b \tag{1}
\end{gather}
$$
such that:
$$
\begin{gather}
f(x_k) = 0, \quad \forall k \in \{0, 1, \dots, n\} \tag{2}
\end{gather}
$$

The claim that there exists an intermediate point $\xi \in (x_0, x_n)$ satisfying $f^{(n)}(\xi) = 0$ is proven by mathematical induction on the derivative order $n \in \mathbb{N}$.

**Base Case: $n = 1$.**
For $n = 1$, the hypothesis states that $f \in C^0[a, b]$ and $f'(x)$ exists on $(a, b)$, with $f(x_0) = f(x_1) = 0$ for $x_0 < x_1$. 

Restricting the domain of $f$ to the closed compact subinterval $[x_0, x_1] \subseteq [a, b]$:
1. The function $f$ is continuous on $[x_0, x_1]$;
2. The function $f$ is differentiable on the open interior $(x_0, x_1)$;
3. The boundary values satisfy $f(x_0) = 0 = f(x_1)$.

All hypotheses of [[Proof of Rolle's Theorem|Rolle's Mean Value Theorem]] are satisfied on $[x_0, x_1]$. Consequently, there exists an interior point $\xi \in (x_0, x_1)$ such that:
$$
\begin{gather}
f'(\xi) = 0 \tag{3}
\end{gather}
$$
The base case $n = 1$ is thus established.

**Induction Hypothesis:**
Assume that for some integer $m \ge 1$, whenever a function $g \in C^{m-1}[\alpha, \beta]$ possesses an $m$-th derivative $g^{(m)}$ on $(\alpha, \beta)$ and vanishes at $(m + 1)$ distinct points $\alpha \le y_0 < y_1 < \dots < y_m \le \beta$, there exists a point $\xi \in (y_0, y_m)$ such that $g^{(m)}(\xi) = 0$.

**Induction Step:**
Let $f \in C^m[a, b]$ be a function such that $f^{(m+1)}(x)$ exists on $(a, b)$, and suppose $f$ vanishes at $(m + 2)$ distinct points:
$$
\begin{gather}
a \le x_0 < x_1 < x_2 < \dots < x_m < x_{m+1} \le b \tag{4}
\end{gather}
$$
with $f(x_k) = 0$ for all $k \in \{0, 1, \dots, m+1\}$.

For each integer index $k \in \{0, 1, \dots, m\}$, consider the contiguous closed subinterval:
$$
\begin{gather}
I_k := [x_k, x_{k+1}] \tag{5}
\end{gather}
$$
Because $m \ge 1$, the class inclusion $C^m[a, b] \subseteq C^1[a, b]$ ensures that $f$ is continuously differentiable on $[a, b]$. In particular, on each subinterval $I_k$:
1. The restriction $f|_{I_k}$ is continuous on $[x_k, x_{k+1}]$;
2. The restriction $f|_{I_k}$ is differentiable on $(x_k, x_{k+1})$;
3. The endpoints satisfy $f(x_k) = 0 = f(x_{k+1})$.

Applying [[Proof of Rolle's Theorem|Rolle's Mean Value Theorem]] to each subinterval $I_k$ yields the existence of an intermediate point $\xi_k \in (x_k, x_{k+1})$ such that:
$$
\begin{gather}
f'(\xi_k) = 0, \quad \forall k \in \{0, 1, \dots, m\} \tag{6}
\end{gather}
$$

Because the open intervals $(x_k, x_{k+1})$ are mutually disjoint and ordered sequentially:
$$
\begin{gather}
x_0 < \xi_0 < x_1 < \xi_1 < x_2 < \dots < x_m < \xi_m < x_{m+1} \tag{7}
\end{gather}
$$
the collection of points $\{\xi_0, \xi_1, \dots, \xi_m\}$ forms a set of $(m + 1)$ distinct points strictly contained within $(x_0, x_{m+1})$.

Define the derived mapping $g: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := f'(x), \quad \forall x \in [a, b] \tag{8}
\end{gather}
$$
Because $f \in C^m[a, b]$, the derived function satisfies $g \in C^{m-1}[a, b]$. Furthermore, for every $x \in (a, b)$, the derivative $g^{(m)}(x)$ exists and is related to $f$ by:
$$
\begin{gather}
g^{(m)}(x) = \frac{d^m}{dx^m}\left(f'(x)\right) = f^{(m+1)}(x) \tag{9}
\end{gather}
$$
By step 6, the function $g$ vanishes at the $(m + 1)$ distinct points:
$$
\begin{gather}
g(\xi_k) = 0, \quad \forall k \in \{0, 1, \dots, m\} \tag{10}
\end{gather}
$$

The function $g$ satisfies all requirements of the induction hypothesis on the interval $[\xi_0, \xi_m]$. Consequently, there exists an intermediate point $\xi \in (\xi_0, \xi_m)$ such that:
$$
\begin{gather}
g^{(m)}(\xi) = 0 \tag{11}
\end{gather}
$$

From step 7, the chain of inequalities ensures that:
$$
\begin{gather}
x_0 < \xi_0 < \xi < \xi_m < x_{m+1} \implies \xi \in (x_0, x_{m+1}) \tag{12}
\end{gather}
$$
Substituting step 9 into step 11 establishes:
$$
\begin{gather}
f^{(m+1)}(\xi) = 0 \tag{13}
\end{gather}
$$
with $\xi \in (x_0, x_{m+1})$. 

By the principle of mathematical induction, the statement holds for all natural numbers $n \in \mathbb{N}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$