---
dg-publish: true
---
Let $n \in \mathbb{N}$ with $n \ge 2$, let $x_0 \in \mathbb{R}$, and let $f: U(x_0) \to \mathbb{R}$ possess continuous derivatives up to order $n$ on an open neighborhood $U(x_0) := (x_0 - \delta, x_0 + \delta)$. Suppose that the derivatives vanish up to order $n - 1$ while the $n$-th derivative is non-zero:
$$
\begin{gather}
f'(x_0) = f''(x_0) = \dots = f^{(n-1)}(x_0) = 0 \quad \text{and} \quad f^{(n)}(x_0) \neq 0 \tag{1}
\end{gather}
$$

By virtue of [[Proof of the Local Taylor Formula with Peano Remainder|Taylor's Formula with Peano Remainder]], the increment of $f$ in a neighborhood of $x_0$ can be expanded for any $x \in U(x_0)$ as:
$$
\begin{gather}
f(x) - f(x_0) = \sum_{k=1}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k + o\big((x - x_0)^n\big) \quad \text{as } x \to x_0 \tag{2}
\end{gather}
$$
Substituting the vanishing derivatives from step 1 into step 2 eliminates all polynomial terms of degree $k < n$:
$$
\begin{gather}
f(x) - f(x_0) = \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n + o\big((x - x_0)^n\big) \tag{3}
\end{gather}
$$

Factoring out $(x - x_0)^n$ for $x \neq x_0$ yields:
$$
\begin{gather}
f(x) - f(x_0) = (x - x_0)^n \left[ \frac{f^{(n)}(x_0)}{n!} + \alpha(x) \right] \tag{4}
\end{gather}
$$
where $\alpha(x) := \frac{o((x - x_0)^n)}{(x - x_0)^n}$ satisfies:
$$
\begin{gather}
\lim_{x \to x_0} \alpha(x) = 0 \tag{5}
\end{gather}
$$

Because $f^{(n)}(x_0) \neq 0$, the constant term $C := \frac{f^{(n)}(x_0)}{n!}$ is non-zero. Define $\varepsilon := \frac{|C|}{2} > 0$. By the definition of functional limit in step 5, there exists a sufficiently small radius $\delta_0 \in (0, \delta)$ such that for all $x$ in the punctured neighborhood $\mathring{U}_{\delta_0}(x_0) := (x_0 - \delta_0, x_0 + \delta_0) \setminus \{x_0\}$:
$$
\begin{gather}
|\alpha(x)| < \frac{|C|}{2} \tag{6}
\end{gather}
$$
The bound in step 6 guarantees that the bracketed factor in step 4 maintains the strict algebraic sign of $f^{(n)}(x_0)$ across the entire punctured neighborhood:
$$
\begin{gather}
\operatorname{sgn}\left(\frac{f^{(n)}(x_0)}{n!} + \alpha(x)\right) = \operatorname{sgn}\big(f^{(n)}(x_0)\big), \quad \forall x \in \mathring{U}_{\delta_0}(x_0) \tag{7}
\end{gather}
$$

---
# Proposition 1
Suppose that $n$ is odd.

For any $x > x_0$, the difference $x - x_0$ is strictly positive, whence $(x - x_0)^n > 0$. For any $x < x_0$, the difference $x - x_0$ is strictly negative; because $n$ is odd, $(x - x_0)^n < 0$. 

By virtue of step 7, the bracketed term in step 4 does not change sign across $\mathring{U}_{\delta_0}(x_0)$. Consequently, the algebraic sign of $f(x) - f(x_0)$ is dictated by $(x - x_0)^n$:
$$
\begin{gather}
\operatorname{sgn}\big(f(x) - f(x_0)\big) = \operatorname{sgn}\big((x - x_0)^n\big) \cdot \operatorname{sgn}\big(f^{(n)}(x_0)\big) \tag{8}
\end{gather}
$$
The product in step 8 takes opposite signs on $(x_0 - \delta_0, x_0)$ and $(x_0, x_0 + \delta_0)$. Functional values lie strictly below $f(x_0)$ on one side and strictly above $f(x_0)$ on the other side. Hence, $x_0$ cannot be a local extremum of $f$.

---
# Proposition 2
Suppose that $n$ is even and $f^{(n)}(x_0) > 0$.

Because $n$ is even, $(x - x_0)^n > 0$ for all $x \in \mathring{U}_{\delta_0}(x_0)$. Furthermore, because $f^{(n)}(x_0) > 0$, step 7 implies that:
$$
\begin{gather}
\frac{f^{(n)}(x_0)}{n!} + \alpha(x) > 0, \quad \forall x \in \mathring{U}_{\delta_0}(x_0) \tag{9}
\end{gather}
$$
The product of two strictly positive quantities in step 4 establishes that:
$$
\begin{gather}
f(x) - f(x_0) > 0 \iff f(x) > f(x_0), \quad \forall x \in \mathring{U}_{\delta_0}(x_0) \tag{10}
\end{gather}
$$
Step 10 proves that $x_0$ is a strict local minimum of $f$.

---
# Proposition 3
Suppose that $n$ is even and $f^{(n)}(x_0) < 0$.

Because $n$ is even, $(x - x_0)^n > 0$ for all $x \in \mathring{U}_{\delta_0}(x_0)$. Because $f^{(n)}(x_0) < 0$, step 7 implies that:
$$
\begin{gather}
\frac{f^{(n)}(x_0)}{n!} + \alpha(x) < 0, \quad \forall x \in \mathring{U}_{\delta_0}(x_0) \tag{11}
\end{gather}
$$
The product of a positive number and a negative number in step 4 establishes that:
$$
\begin{gather}
f(x) - f(x_0) < 0 \iff f(x) < f(x_0), \quad \forall x \in \mathring{U}_{\delta_0}(x_0) \tag{12}
\end{gather}
$$
Step 12 proves that $x_0$ is a strict local maximum of $f$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
