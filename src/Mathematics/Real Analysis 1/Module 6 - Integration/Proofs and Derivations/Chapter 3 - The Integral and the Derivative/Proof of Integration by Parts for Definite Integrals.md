---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $u, v \in C^1[a, b]$ be continuously differentiable functions on $[a, b]$.

---
# Part 1
By definition of the function space $C^1[a, b]$, the functions $u$ and $v$ are differentiable on $[a, b]$, and their derivative functions $u'$ and $v'$ are continuous on $[a, b]$:
$$
\begin{gather}
u, v \in C[a, b], \qquad u', v' \in C[a, b] \tag{1}
\end{gather}
$$

By the algebraic properties of continuous functions on topological spaces (Module 5), the product of any two continuous functions is continuous. Therefore:
$$
\begin{gather}
(u \cdot v')(x) := u(x)v'(x) \in C[a, b] \tag{2}
\end{gather}
$$
and:
$$
\begin{gather}
(u' \cdot v)(x) := u'(x)v(x) \in C[a, b] \tag{3}
\end{gather}
$$

By the Integrability of Continuous Functions on Compact Intervals (Module 6, Chapter 1), every continuous real-valued function defined on a compact interval is Riemann integrable. Applying this theorem to step 2 and step 3 yields:
$$
\begin{gather}
u \cdot v' \in \mathcal{R}[a, b], \qquad u' \cdot v \in \mathcal{R}[a, b] \tag{4}
\end{gather}
$$
establishing the Riemann integrability of both functional products.

---
# Part 2
Define the auxiliary product function $w: [a, b] \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
w(x) := u(x)v(x) \quad \text{for all } x \in [a, b] \tag{5}
\end{gather}
$$

Because $u$ and $v$ are differentiable at every point $x \in [a, b]$, the Product Rule of Differentiation (Module 5) ensures that $w$ is differentiable at every point $x \in [a, b]$, and its derivative is given by:
$$
\begin{gather}
w'(x) = (uv)'(x) = u'(x)v(x) + u(x)v'(x) \tag{6}
\end{gather}
$$

By step 2 and step 3, both terms on the right-hand side of step 6 are continuous on $[a, b]$. Because the sum of two continuous functions is continuous, the derivative function satisfies:
$$
\begin{gather}
w' \in C[a, b] \tag{7}
\end{gather}
$$

By the Integrability of Continuous Functions on Compact Intervals, step 7 implies:
$$
\begin{gather}
w' \in \mathcal{R}[a, b] \tag{8}
\end{gather}
$$
---
# Part 3
The function $w$ is continuous on $[a, b]$ and differentiable on $(a, b)$ with $w'(x) = (uv)'(x)$ Riemann integrable on $[a, b]$. 

Applying the Newton-Leibniz Formula (Module 6, Chapter 3, [[Proof of the Newton-Leibniz Formula]]) to the function $w$:
$$
\begin{gather}
\int_a^b w'(x)\,dx = w(b) - w(a) \tag{9}
\end{gather}
$$

Substituting the definition of $w$ from step 5 into the right-hand side of step 9:
$$
\begin{gather}
w(b) - w(a) = u(b)v(b) - u(a)v(a) =: \big[ u(x)v(x) \big]_a^b \tag{10}
\end{gather}
$$

Substituting the product derivative identity of step 6 into the integrand on the left-hand side of step 9:
$$
\begin{gather}
\int_a^b \big( u'(x)v(x) + u(x)v'(x) \big)\,dx = \big[ u(x)v(x) \big]_a^b \tag{11}
\end{gather}
$$

By step 4, both $u'v$ and $uv'$ belong to $\mathcal{R}[a, b]$. By the Linearity of the Riemann Integral (Module 6, Chapter 2, [[Proof of the Linearity of the Riemann Integral]]):
$$
\begin{gather}
\int_a^b \big( u'(x)v(x) + u(x)v'(x) \big)\,dx = \int_a^b u'(x)v(x)\,dx + \int_a^b u(x)v'(x)\,dx \tag{12}
\end{gather}
$$

Equating step 11 and step 12 yields:
$$
\begin{gather}
\int_a^b u'(x)v(x)\,dx + \int_a^b u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^b \tag{13}
\end{gather}
$$

Subtracting the finite real value $\int_a^b u'(x)v(x)\,dx$ from both sides of step 13:
$$
\begin{gather}
\int_a^b u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^b - \int_a^b u'(x)v(x)\,dx \tag{14}
\end{gather}
$$
which establishes the integration by parts formula for definite integrals.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
