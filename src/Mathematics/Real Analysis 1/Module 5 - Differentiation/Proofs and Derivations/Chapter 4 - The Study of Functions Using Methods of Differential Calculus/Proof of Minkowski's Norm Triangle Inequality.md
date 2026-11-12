---
dg-publish: true
---
Let $n \in \mathbb{N}$, and let $x_1, \dots, x_n \ge 0$ and $y_1, \dots, y_n \ge 0$ be sequences of non-negative real numbers.

---
# Proposition 1
Suppose that $p \ge 1$.

If $p = 1$, the standard triangle inequality for real numbers establishes that for every $i \in \{1, \dots, n\}$, $|x_i + y_i| \le |x_i| + |y_i|$. Because all terms are non-negative, summing from $i = 1$ to $n$ gives:
$$
\begin{gather}
\sum_{i=1}^n (x_i + y_i) = \sum_{i=1}^n x_i + \sum_{i=1}^n y_i \tag{1}
\end{gather}
$$
which holds as an identity.

Now suppose that $p > 1$. Define the conjugate exponent $q := \frac{p}{p - 1} > 1$, which satisfies:
$$
\begin{gather}
\frac{1}{p} + \frac{1}{q} = 1 \iff (p - 1)q = p \tag{2}
\end{gather}
$$
If $\sum_{i=1}^n (x_i + y_i)^p = 0$, then $x_i = y_i = 0$ for all $i$, and the inequality holds trivially. Hence, assume that $\sum_{i=1}^n (x_i + y_i)^p > 0$.

Decompose the $p$-th power sum by splitting the base:
$$
\begin{gather}
\sum_{i=1}^n (x_i + y_i)^p = \sum_{i=1}^n (x_i + y_i)(x_i + y_i)^{p-1} = \sum_{i=1}^n x_i (x_i + y_i)^{p-1} + \sum_{i=1}^n y_i (x_i + y_i)^{p-1} \tag{3}
\end{gather}
$$
Applying [[Proof of Hölder's Discrete Summation Inequality|Hölder's Discrete Summation Inequality]] with exponents $p$ and $q$ to the first sum in step 3 gives:
$$
\begin{gather}
\sum_{i=1}^n x_i (x_i + y_i)^{p-1} \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n (x_i + y_i)^{(p-1)q}\right)^{1/q} \tag{4}
\end{gather}
$$
Using the exponent identity $(p - 1)q = p$ from step 2, step 4 becomes:
$$
\begin{gather}
\sum_{i=1}^n x_i (x_i + y_i)^{p-1} \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q} \tag{5}
\end{gather}
$$
Similarly, applying Hölder's inequality to the second sum in step 3 gives:
$$
\begin{gather}
\sum_{i=1}^n y_i (x_i + y_i)^{p-1} \le \left(\sum_{i=1}^n y_i^p\right)^{1/p} \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q} \tag{6}
\end{gather}
$$

Substituting step 5 and step 6 into step 3 and factoring out the common second term yields:
$$
\begin{gather}
\sum_{i=1}^n (x_i + y_i)^p \le \left[ \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \right] \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q} \tag{7}
\end{gather}
$$
Dividing both sides of step 7 by $\left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q}$ leaves:
$$
\begin{gather}
\left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1 - 1/q} \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \tag{8}
\end{gather}
$$
Because $1 - \frac{1}{q} = \frac{1}{p}$, step 8 becomes Minkowski's inequality:
$$
\begin{gather}
\left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/p} \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \tag{9}
\end{gather}
$$

Equality in step 5 and step 6 holds if and only if both $(x_i)$ and $(y_i)$ are proportional to $(x_i + y_i)^{p-1}$, which occurs if and only if $(x_1, \dots, x_n)$ and $(y_1, \dots, y_n)$ are collinear.

---
# Proposition 2
Suppose that $p < 1$ with $p \neq 0$. Assume that $x_i > 0$ and $y_i > 0$ for all $i \in \{1, \dots, n\}$.

In this setting, the conjugate exponent $q = \frac{p}{p - 1}$ satisfies $q < 0$ when $p \in (0, 1)$, and $0 < q < 1$ when $p < 0$. In either case, applying the reversed Hölder inequality from [[Proof of Hölder's Discrete Summation Inequality|Proposition 2 of Hölder's Discrete Summation Inequality]] to each term in the sum of step 3 reverses the inequality sign:
$$
\begin{gather}
\sum_{i=1}^n x_i (x_i + y_i)^{p-1} \ge \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q} \tag{10}
\end{gather}
$$
and
$$
\begin{gather}
\sum_{i=1}^n y_i (x_i + y_i)^{p-1} \ge \left(\sum_{i=1}^n y_i^p\right)^{1/p} \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q} \tag{11}
\end{gather}
$$
Summing step 10 and step 11 and dividing by $\left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/q}$ produces:
$$
\begin{gather}
\left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/p} \ge \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \tag{12}
\end{gather}
$$
Equality holds if and only if $(x_1, \dots, x_n)$ and $(y_1, \dots, y_n)$ are collinear.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
