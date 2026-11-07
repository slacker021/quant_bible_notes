---
dg-publish: true
---
### Part 1: Young's Inequality
Let $p, q > 1$ such that $\frac{1}{p} + \frac{1}{q} = 1$. Let $a, b > 0$ (if $a = 0$ or $b = 0$, $0 \le \frac{a^p}{p} + \frac{b^q}{q}$ holds trivially).

Consider the exponential function $f(x) = e^x$. Because $f''(x) = e^x > 0$ on $\mathbb{R}$, $f$ is strictly convex on $\mathbb{R}$.

Set the weights $\alpha_1 = \frac{1}{p}$ and $\alpha_2 = \frac{1}{q}$. Because $\frac{1}{p} + \frac{1}{q} = 1$ and $\alpha_1, \alpha_2 > 0$, applying the definition of convex functions to $x_1 = \ln(a^p)$ and $x_2 = \ln(b^q)$:
$$
\begin{gather}
\exp\left( \frac{1}{p} \ln(a^p) + \frac{1}{q} \ln(b^q) \right) \le \frac{1}{p} \exp(\ln(a^p)) + \frac{1}{q} \exp(\ln(b^q)) \tag{1}
\end{gather}
$$

Simplifying the left-hand side:
$$
\begin{gather}
\frac{1}{p} \ln(a^p) + \frac{1}{q} \ln(b^q) = \frac{p}{p} \ln a + \frac{q}{q} \ln b = \ln a + \ln b = \ln(ab) \tag{2} \\
\exp(\ln(ab)) = ab \tag{3}
\end{gather}
$$

Simplifying the right-hand side:
$$
\begin{gather}
\frac{1}{p} a^p + \frac{1}{q} b^q = \frac{a^p}{p} + \frac{b^q}{q} \tag{4}
\end{gather}
$$

Substituting equations (3) and (4) into inequality (1):
$$
\begin{gather}
ab \le \frac{a^p}{p} + \frac{b^q}{q} \tag{5}
\end{gather}
$$
which proves Young's inequality.

### Part 2: Hölder's Inequality
Let $a = (a_1, \dots, a_n)$ and $b = (b_1, \dots, b_n)$ in $\mathbb{R}^n$. If $\sum_{k=1}^n |a_k|^p = 0$ or $\sum_{k=1}^n |b_k|^q = 0$, then $a$ or $b$ is the zero vector, and $0 \le 0$ holds trivially.

Assume $A := \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} > 0$ and $B := \left( \sum_{k=1}^n |b_k|^q \right)^{1/q} > 0$.

Define the normalized terms for each $k \in \{1, \dots, n\}$:
$$
\begin{gather}
u_k := \frac{|a_k|}{A}, \quad v_k := \frac{|b_k|}{B} \tag{6}
\end{gather}
$$

Applying Young's inequality (5) to $u_k$ and $v_k$:
$$
\begin{gather}
u_k v_k \le \frac{u_k^p}{p} + \frac{v_k^q}{q} \implies \frac{|a_k b_k|}{AB} \le \frac{|a_k|^p}{p A^p} + \frac{|b_k|^q}{q B^q} \tag{7}
\end{gather}
$$

Summing inequality (7) over $k = 1, \dots, n$:
$$
\begin{gather}
\frac{1}{AB} \sum_{k=1}^n |a_k b_k| \le \frac{1}{p A^p} \sum_{k=1}^n |a_k|^p + \frac{1}{q B^q} \sum_{k=1}^n |b_k|^q \tag{8}
\end{gather}
$$

Because $\sum_{k=1}^n |a_k|^p = A^p$ and $\sum_{k=1}^n |b_k|^q = B^q$:
$$
\begin{gather}
\frac{1}{AB} \sum_{k=1}^n |a_k b_k| \le \frac{A^p}{p A^p} + \frac{B^q}{q B^q} = \frac{1}{p} + \frac{1}{q} = 1 \tag{9}
\end{gather}
$$

Multiplying inequality (9) by $AB$:
$$
\begin{gather}
\sum_{k=1}^n |a_k b_k| \le A B = \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} \left( \sum_{k=1}^n |b_k|^q \right)^{1/q} \tag{10}
\end{gather}
$$
which proves Hölder's inequality.

### Part 3: Minkowski's Inequality
For $p = 1$, the standard triangle inequality on $\mathbb{R}$ gives:
$$
\begin{gather}
\sum_{k=1}^n |a_k + b_k| \le \sum_{k=1}^n (|a_k| + |b_k|) = \sum_{k=1}^n |a_k| + \sum_{k=1}^n |b_k| \tag{11}
\end{gather}
$$

Assume $p > 1$, and let $q = \frac{p}{p - 1}$, so that $\frac{1}{p} + \frac{1}{q} = 1$ and $(p - 1)q = p$.

Using the triangle inequality:
$$
\begin{gather}
|a_k + b_k|^p = |a_k + b_k| \cdot |a_k + b_k|^{p-1} \le (|a_k| + |b_k|) |a_k + b_k|^{p-1} = |a_k||a_k + b_k|^{p-1} + |b_k||a_k + b_k|^{p-1} \tag{12}
\end{gather}
$$

Summing over $k = 1, \dots, n$:
$$
\begin{gather}
\sum_{k=1}^n |a_k + b_k|^p \le \sum_{k=1}^n |a_k||a_k + b_k|^{p-1} + \sum_{k=1}^n |b_k||a_k + b_k|^{p-1} \tag{13}
\end{gather}
$$

Applying Hölder's inequality (10) to each sum on the right-hand side:
$$
\begin{gather}
\sum_{k=1}^n |a_k||a_k + b_k|^{p-1} \le \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} \left( \sum_{k=1}^n |a_k + b_k|^{(p-1)q} \right)^{1/q} = \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} \left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/q} \tag{14}
\end{gather}
$$

Similarly:
$$
\begin{gather}
\sum_{k=1}^n |b_k||a_k + b_k|^{p-1} \le \left( \sum_{k=1}^n |b_k|^p \right)^{1/p} \left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/q} \tag{15}
\end{gather}
$$

Substituting bounds (14) and (15) into inequality (13):
$$
\begin{gather}
\sum_{k=1}^n |a_k + b_k|^p \le \left[ \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} + \left( \sum_{k=1}^n |b_k|^p \right)^{1/p} \right] \left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/q} \tag{16}
\end{gather}
$$

If $\sum_{k=1}^n |a_k + b_k|^p = 0$, the inequality holds trivially. If not, dividing inequality (16) by $\left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/q}$, and noting that $1 - \frac{1}{q} = \frac{1}{p}$:
$$
\begin{gather}
\left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/p} \le \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} + \left( \sum_{k=1}^n |b_k|^p \right)^{1/p} \tag{17}
\end{gather}
$$
which completes the proof of Minkowski's inequality.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
