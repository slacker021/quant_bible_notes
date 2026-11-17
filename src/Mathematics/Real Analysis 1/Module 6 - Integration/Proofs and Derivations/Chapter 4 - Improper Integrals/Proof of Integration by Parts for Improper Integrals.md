---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $u, v: [a, \infty) \to \mathbb{R}$ be continuously differentiable functions on $[a, \infty)$:
$$
\begin{gather}
u, v \in C^1[a, \infty) \tag{1}
\end{gather}
$$
Assume that the following two hypotheses are satisfied:
1. The asymptotic limit of the product function $uv$ exists as a finite real scalar:
$$
\begin{gather}
L := \lim_{x \to \infty} u(x)v(x) \in \mathbb{R} \tag{2}
\end{gather}
$$
2. The improper integral of $u'v$ over $[a, \infty)$ converges to a finite real value:
$$
\begin{gather}
I_1 := \int_a^\infty u'(x)v(x)\,dx = \lim_{B \to \infty} \int_a^B u'(x)v(x)\,dx \in \mathbb{R} \tag{3}
\end{gather}
$$
---
# Step 1
Let $B \in [a, \infty)$ be an arbitrary exhaustion parameter. Because $u, v \in C^1[a, \infty)$, the functions $u, v, u', v'$ are continuous on the compact interval $[a, B]$. By the algebra of continuous functions, the pointwise products $u v'$ and $u' v$ are continuous on $[a, B]$, ensuring Riemann integrability:
$$
\begin{gather}
u v' \in \mathcal{R}[a, B], \quad u' v \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{4}
\end{gather}
$$
Applying the classical Integration by Parts Formula for proper Riemann integrals established in [[Chapter 3 - The Integral and the Derivative|Chapter 3]]:
$$
\begin{gather}
\int_a^B u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^B - \int_a^B u'(x)v(x)\,dx \tag{5}
\end{gather}
$$
where the boundary evaluation bracket on the compact interval $[a, B]$ is explicitly defined by:
$$
\begin{gather}
\big[ u(x)v(x) \big]_a^B := u(B)v(B) - u(a)v(a) \tag{6}
\end{gather}
$$

---
# Step 2
Define the boundary variation function $\Delta: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
\Delta(B) := \big[ u(x)v(x) \big]_a^B = u(B)v(B) - u(a)v(a) \tag{7}
\end{gather}
$$
By hypothesis (step 2), $\lim_{B \to \infty} u(B)v(B) = L \in \mathbb{R}$. Because $u(a)v(a)$ is a constant scalar independent of $B$, the difference rule for functional limits yields:
$$
\begin{gather}
\lim_{B \to \infty} \Delta(B) = \lim_{B \to \infty} \big( u(B)v(B) - u(a)v(a) \big) = L - u(a)v(a) \tag{8}
\end{gather}
$$
The finite real quantity on the right-hand side of step 8 is denoted by the extended asymptotic boundary evaluation bracket:
$$
\begin{gather}
\big[ u(x)v(x) \big]_a^\infty := \lim_{B \to \infty} \big[ u(x)v(x) \big]_a^B = \lim_{B \to \infty} u(B)v(B) - u(a)v(a) \in \mathbb{R} \tag{9}
\end{gather}
$$
---
# Step 3
By definition of the improper integral of the first kind on $[a, \infty)$:
$$
\begin{gather}
\int_a^\infty u(x)v'(x)\,dx := \lim_{B \to \infty} \int_a^B u(x)v'(x)\,dx \tag{10}
\end{gather}
$$
Substituting the proper integration by parts identity of step 5 into step 10:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B u(x)v'(x)\,dx = \lim_{B \to \infty} \left( \big[ u(x)v(x) \big]_a^B - \int_a^B u'(x)v(x)\,dx \right) \tag{11}
\end{gather}
$$
Because the boundary limit $\lim_{B \to \infty} [u(x)v(x)]_a^B = [u(x)v(x)]_a^\infty$ exists in $\mathbb{R}$ by step 9, and the integral limit $\lim_{B \to \infty} \int_a^B u'(x)v(x)\,dx = I_1$ exists in $\mathbb{R}$ by hypothesis (step 3), the difference rule for functional limits applies to step 11:
$$
\begin{gather}
\lim_{B \to \infty} \left( \big[ u(x)v(x) \big]_a^B - \int_a^B u'(x)v(x)\,dx \right) = \lim_{B \to \infty} \big[ u(x)v(x) \big]_a^B - \lim_{B \to \infty} \int_a^B u'(x)v(x)\,dx \tag{12}
\end{gather}
$$
Evaluating the limits on the right-hand side of step 12 yields:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^\infty - \int_a^\infty u'(x)v(x)\,dx \tag{13}
\end{gather}
$$
Because both $[u(x)v(x)]_a^\infty$ and $\int_a^\infty u'(x)v(x)\,dx$ are finite real numbers, their difference is a finite real number. Therefore, the improper integral $\int_a^\infty u(x)v'(x)\,dx$ converges, and satisfies the formula:
$$
\begin{gather}
\int_a^\infty u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^\infty - \int_a^\infty u'(x)v(x)\,dx \tag{14}
\end{gather}
$$

**Step 4: Symmetric Equivalence of Convergence**

Whenever the asymptotic limit $\lim_{x \to \infty} u(x)v(x) \in \mathbb{R}$ exists, rearranging step 5 as:
$$
\begin{gather}
\int_a^B u'(x)v(x)\,dx = \big[ u(x)v(x) \big]_a^B - \int_a^B u(x)v'(x)\,dx \tag{15}
\end{gather}
$$
demonstrates that $\int_a^\infty u'(x)v(x)\,dx$ converges if and only if $\int_a^\infty u(x)v'(x)\,dx$ converges. Convergence of either integral, in conjunction with the existence of the boundary limit, guarantees the convergence of the other.

---
# Step 4
Let $-\infty < a < b < \infty$, and let $u, v \in C^1[a, b)$. Suppose the one-sided limit $\lim_{x \to b^-} u(x)v(x) \in \mathbb{R}$ exists and $\int_a^b u'(x)v(x)\,dx$ converges. For every $\varepsilon \in (0, b - a)$, proper integration by parts on $[a, b - \varepsilon]$ yields:
$$
\begin{gather}
\int_a^{b - \varepsilon} u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^{b - \varepsilon} - \int_a^{b - \varepsilon} u'(x)v(x)\,dx \tag{16}
\end{gather}
$$
Taking the one-sided limit as $\varepsilon \to 0^+$ on both sides of step 16 yields:
$$
\begin{gather}
\int_a^b u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^{b^-} - \int_a^b u'(x)v(x)\,dx \tag{17}
\end{gather}
$$
where $[u(x)v(x)]_a^{b^-} := \lim_{\varepsilon \to 0^+} u(b - \varepsilon)v(b - \varepsilon) - u(a)v(a) \in \mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
