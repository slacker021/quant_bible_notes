---
dg-publish: true
---
Let $a > 0$ and $b > 0$, and let $p, q \in \mathbb{R} \setminus \{0, 1\}$ satisfy the conjugate exponent relation:
$$
\begin{gather}
\frac{1}{p} + \frac{1}{q} = 1 \tag{1}
\end{gather}
$$

Define the exponent $\alpha := \frac{1}{p} \in \mathbb{R} \setminus \{0, 1\}$. By virtue of step 1:
$$
\begin{gather}
\frac{1}{q} = 1 - \frac{1}{p} = 1 - \alpha \tag{2}
\end{gather}
$$
Now define the variable $x \in (0, \infty)$ by:
$$
\begin{gather}
x := a b^{-1} = \frac{a}{b} \tag{3}
\end{gather}
$$
Notice that $x = 1$ if and only if $a = b$.

Recall [[Proof of the Generalized Power-Bernoulli Differential Inequality|The Generalized Power-Bernoulli Differential Inequality]], which establishes that for the function $\varphi(x) = x^\alpha - \alpha x + \alpha - 1$:
$$
\begin{gather}
x^\alpha - \alpha x + \alpha - 1 \le 0 \quad \text{for } 0 < \alpha < 1 \tag{4}
\end{gather}
$$
and
$$
\begin{gather}
x^\alpha - \alpha x + \alpha - 1 \ge 0 \quad \text{for } \alpha < 0 \ \lor \ \alpha > 1 \tag{5}
\end{gather}
$$
with equality holding in either inequality if and only if $x = 1$.

Substituting $x = \frac{a}{b}$ into the expression $x^\alpha - \alpha x + (\alpha - 1)$ yields:
$$
\begin{gather}
\left(\frac{a}{b}\right)^\alpha - \alpha \left(\frac{a}{b}\right) - (1 - \alpha) \tag{6}
\end{gather}
$$
Multiplying step 6 by the strictly positive quantity $b > 0$ preserves all inequalities and produces:
$$
\begin{gather}
b \left[\left(\frac{a}{b}\right)^\alpha - \alpha \frac{a}{b} - (1 - \alpha)\right] = a^\alpha b^{1 - \alpha} - \alpha a - (1 - \alpha) b \tag{7}
\end{gather}
$$
Substituting $\alpha = \frac{1}{p}$ and $1 - \alpha = \frac{1}{q}$ from step 2 into step 7 transforms the expression into:
$$
\begin{gather}
a^{1/p} b^{1/q} - \frac{a}{p} - \frac{b}{q} \tag{8}
\end{gather}
$$

---
# Proposition 1
Suppose that $p > 1$.

Because $p > 1$, the reciprocal satisfies:
$$
\begin{gather}
0 < \alpha = \frac{1}{p} < 1 \tag{9}
\end{gather}
$$
Applying step 4 to step 8 shows that for all $a, b > 0$:
$$
\begin{gather}
a^{1/p} b^{1/q} - \frac{a}{p} - \frac{b}{q} \le 0 \iff a^{1/p} b^{1/q} \le \frac{a}{p} + \frac{b}{q} \tag{10}
\end{gather}
$$
Because equality in step 4 holds if and only if $x = 1$, equality in step 10 holds if and only if $\frac{a}{b} = 1$, which is equivalent to $a = b$.

---
# Proposition 2
Suppose that $p < 1$ with $p \neq 0$.

If $p \in (0, 1)$, then $\alpha = \frac{1}{p} > 1$. If $p < 0$, then $\alpha = \frac{1}{p} < 0$. In either case:
$$
\begin{gather}
\alpha \in (-\infty, 0) \cup (1, \infty) \tag{11}
\end{gather}
$$
Applying step 5 to step 8 shows that for all $a, b > 0$:
$$
\begin{gather}
a^{1/p} b^{1/q} - \frac{a}{p} - \frac{b}{q} \ge 0 \iff a^{1/p} b^{1/q} \ge \frac{a}{p} + \frac{b}{q} \tag{12}
\end{gather}
$$
Equality holds in step 12 if and only if $x = 1$, which is equivalent to $a = b$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
