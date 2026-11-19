---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f \in \mathcal{R}[a, b]$, and let the infimum and supremum of $f$ on $[a, b]$ be defined by:
$$
\begin{gather}
m := \inf_{x \in [a, b]} f(x), \qquad M := \sup_{x \in [a, b]} f(x) \tag{1}
\end{gather}
$$
---
# Theorem 1
By definition of the infimum and supremum as the greatest lower bound and least upper bound:
$$
\begin{gather}
m \le f(x) \le M \quad \text{for all } x \in [a, b] \tag{2}
\end{gather}
$$

By Part 4 of the Monotonicity and the Absolute Value Integral Inequality ([[Proof of Monotonicity and the Absolute Value Integral Inequality]]), integrating step 2 across $[a, b]$ gives:
$$
\begin{gather}
m(b - a) \le \int_a^b f(x)\,dx \le M(b - a) \tag{3}
\end{gather}
$$

Because $a < b$, the interval length satisfies:
$$
\begin{gather}
b - a > 0 \tag{4}
\end{gather}
$$

Dividing the compound inequality of step 3 by the strictly positive quantity $(b - a) > 0$:
$$
\begin{gather}
m \le \frac{1}{b - a} \int_a^b f(x)\,dx \le M \tag{5}
\end{gather}
$$

Define the real value $\mu$ by:
$$
\begin{gather}
\mu := \frac{1}{b - a} \int_a^b f(x)\,dx \tag{6}
\end{gather}
$$

By step 5, $\mu$ satisfies:
$$
\begin{gather}
\mu \in [m, M] \tag{7}
\end{gather}
$$

Multiplying step 6 by $(b - a)$ yields:
$$
\begin{gather}
\int_a^b f(x)\,dx = \mu(b - a) \tag{8}
\end{gather}
$$
which establishes the Average Value Form.

---
# Theorem 2
Assume additionally that $f \in C[a, b]$.

Because $[a, b]$ is a compact subset of $\mathbb{R}$ and $f$ is continuous on $[a, b]$, the Extreme Value Theorem (Weierstrass Theorem) ensures that $f$ attains both its absolute minimum and its absolute maximum on $[a, b]$. 

Therefore, there exist points $x_{\min}, x_{\max} \in [a, b]$ such that:
$$
\begin{gather}
f(x_{\min}) = m, \qquad f(x_{\max}) = M \tag{9}
\end{gather}
$$

From step 7 in Part 1, the average value $\mu$ satisfies:
$$
\begin{gather}
m \le \mu \le M \tag{10}
\end{gather}
$$

Consider first the case where $m = M$. In this case, step 2 forces $f(x) = m = M = \mu$ for all $x \in [a, b]$. Every point $\xi \in [a, b]$ satisfies:
$$
\begin{gather}
f(\xi) = \mu \tag{11}
\end{gather}
$$

Consider next the case where $m < M$. Define the closed interval $I_0$ connecting $x_{\min}$ and $x_{\max}$:
$$
\begin{gather}
I_0 := [\min\{x_{\min}, x_{\max}\}, \max\{x_{\min}, x_{\max}\}] \subseteq [a, b] \tag{12}
\end{gather}
$$

Because $f$ is continuous on $[a, b]$, its restriction $f|_{I_0}$ is continuous on $I_0$.

The function $f$ maps the endpoints of $I_0$ to $m$ and $M$ by step 9. By step 10, $\mu$ belongs to the closed interval $[m, M]$ between $f(x_{\min})$ and $f(x_{\max})$.

By the Intermediate Value Theorem (Bolzano-Cauchy Theorem), a continuous function on a closed interval attains every intermediate value between its endpoint values. Therefore, there exists at least one point $\xi \in I_0 \subseteq [a, b]$ such that:
$$
\begin{gather}
f(\xi) = \mu \tag{13}
\end{gather}
$$

Substituting the equality $f(\xi) = \mu$ from step 13 into the identity of step 8:
$$
\begin{gather}
\int_a^b f(x)\,dx = f(\xi)(b - a) \tag{14}
\end{gather}
$$
which establishes the Continuous Form.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
