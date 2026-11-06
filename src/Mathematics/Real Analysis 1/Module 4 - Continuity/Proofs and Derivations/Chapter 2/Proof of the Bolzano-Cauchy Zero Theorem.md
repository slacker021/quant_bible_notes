---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate closed bounded interval with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be continuous on $[a, b]$. 

Suppose that $f(a) \cdot f(b) < 0$. Without loss of generality, assume that:
$$
\begin{gather}
f(a) < 0 \quad \text{and} \quad f(b) > 0 \tag{1}
\end{gather}
$$
(The symmetric case $f(a) > 0$ and $f(b) < 0$ is resolved identically by examining $-f$).

Define the base interval $I_0 := [a_0, b_0]$ where $a_0 := a$ and $b_0 := b$. 

Construct an infinite sequence of nested intervals $\{I_n\}_{n=0}^\infty$, with $I_n = [a_n, b_n]$, via the following recursive bisection algorithm:
1. Suppose the interval $I_k = [a_k, b_k]$ has been defined such that $f(a_k) \le 0$ and $f(b_k) \ge 0$.
2. Compute the midpoint:
$$
\begin{gather}
m_k := \frac{a_k + b_k}{2} \tag{2}
\end{gather}
$$
3. If $f(m_k) = 0$, the search terminates immediately, yielding the root $\xi = m_k \in (a, b)$.
4. If $f(m_k) < 0$, set $a_{k+1} := m_k$ and $b_{k+1} := b_k$.
5. If $f(m_k) > 0$, set $a_{k+1} := a_k$ and $b_{k+1} := m_k$.

If the algorithm terminates at any finite step $k$, a root is obtained. Therefore, assume the process continues indefinitely without finite termination. 

By induction, the sequence of closed intervals satisfies the nesting property:
$$
\begin{gather}
I_0 \supset I_1 \supset I_2 \supset \cdots \supset I_n \supset \cdots \tag{3}
\end{gather}
$$

The length of the $n$-th interval satisfies:
$$
\begin{gather}
b_n - a_n = \frac{b - a}{2^n} \tag{4}
\end{gather}
$$

Taking the limit of step 4 as $n \to \infty$:
$$
\begin{gather}
\lim_{n \to \infty} (b_n - a_n) = \lim_{n \to \infty} \frac{b - a}{2^n} = 0 \tag{5}
\end{gather}
$$

By Cantor's Nested Interval Theorem (the completeness principle of $\mathbb{R}$), the intersection of the nested closed intervals contains exactly one point:
$$
\begin{gather}
\bigcap_{n=0}^\infty [a_n, b_n] = \{\xi\} \tag{6}
\end{gather}
$$
which implies:
$$
\begin{gather}
\lim_{n \to \infty} a_n = \xi \quad \text{and} \quad \lim_{n \to \infty} b_n = \xi \tag{7}
\end{gather}
$$

Because $a = a_0 \le a_n < b_n \le b_0 = b$ for all $n$, the point $\xi$ belongs to $[a, b]$. Furthermore, because $f(a) < 0$ and $f(b) > 0$, the point $\xi$ cannot equal $a$ or $b$, so $\xi \in (a, b)$.

Because $f$ is continuous on $[a, b]$, it is continuous at $\xi$. Applying the Heine sequential criterion to step 7:
$$
\begin{gather}
\lim_{n \to \infty} f(a_n) = f(\xi) \quad \text{and} \quad \lim_{n \to \infty} f(b_n) = f(\xi) \tag{8}
\end{gather}
$$

By construction, $f(a_n) < 0$ for all $n \in \mathbb{N}$. Taking the limit as $n \to \infty$ and applying the preservation of inequalities under limits:
$$
\begin{gather}
f(\xi) = \lim_{n \to \infty} f(a_n) \le 0 \tag{9}
\end{gather}
$$

Concurrently, by construction $f(b_n) > 0$ for all $n \in \mathbb{N}$. Taking the limit as $n \to \infty$:
$$
\begin{gather}
f(\xi) = \lim_{n \to \infty} f(b_n) \ge 0 \tag{10}
\end{gather}
$$

Combining the inequality of step 9 and the inequality of step 10:
$$
\begin{gather}
0 \le f(\xi) \le 0 \implies f(\xi) = 0 \tag{11}
\end{gather}
$$

This proves the existence of a point $\xi \in (a, b)$ satisfying $f(\xi) = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
