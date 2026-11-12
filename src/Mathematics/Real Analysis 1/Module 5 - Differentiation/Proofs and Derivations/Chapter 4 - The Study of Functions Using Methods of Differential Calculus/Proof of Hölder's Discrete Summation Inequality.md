---
dg-publish: true
---
Let $n \in \mathbb{N}$, let $x_1, \dots, x_n \ge 0$ and $y_1, \dots, y_n \ge 0$ be non-negative real numbers, and let $p, q \in \mathbb{R} \setminus \{0, 1\}$ be conjugate exponents satisfying:
$$
\begin{gather}
\frac{1}{p} + \frac{1}{q} = 1 \tag{1}
\end{gather}
$$

---
# Proposition 1
Suppose that $p > 1$. Because $\frac{1}{q} = 1 - \frac{1}{p}$, the conjugate exponent also satisfies $q > 1$.

Define the discrete $l^p$ and $l^q$ norms:
$$
\begin{gather}
X := \left(\sum_{i=1}^n x_i^p\right)^{1/p} \quad \text{and} \quad Y := \left(\sum_{i=1}^n y_i^q\right)^{1/q} \tag{2}
\end{gather}
$$
If $X = 0$, then $x_i = 0$ for all $i \in \{1, \dots, n\}$. The sum $\sum_{i=1}^n x_i y_i = 0$ and the product $X Y = 0$, so the inequality holds trivially as an equality $0 \le 0$. An identical conclusion holds if $Y = 0$.

Now assume that $X > 0$ and $Y > 0$. For each index $i \in \{1, \dots, n\}$, define the normalized non-negative terms:
$$
\begin{gather}
a_i := \left(\frac{x_i}{X}\right)^p \quad \text{and} \quad b_i := \left(\frac{y_i}{Y}\right)^q \tag{3}
\end{gather}
$$
By virtue of [[Proof of Young's Conjugate Inequality|Young's Conjugate Inequality]], because $p > 1$ and $q > 1$, every pair $a_i, b_i \ge 0$ satisfies:
$$
\begin{gather}
a_i^{1/p} b_i^{1/q} \le \frac{a_i}{p} + \frac{b_i}{q} \tag{4}
\end{gather}
$$
Substituting step 3 into step 4 yields:
$$
\begin{gather}
\frac{x_i y_i}{X Y} \le \frac{1}{p} \left(\frac{x_i}{X}\right)^p + \frac{1}{q} \left(\frac{y_i}{Y}\right)^q \tag{5}
\end{gather}
$$

Summing the inequality of step 5 across all indices $i \in \{1, \dots, n\}$ gives:
$$
\begin{gather}
\frac{\sum_{i=1}^n x_i y_i}{X Y} \le \frac{1}{p} \sum_{i=1}^n \frac{x_i^p}{X^p} + \frac{1}{q} \sum_{i=1}^n \frac{y_i^q}{Y^q} \tag{6}
\end{gather}
$$
By the definitions of $X$ and $Y$ in step 2:
$$
\begin{gather}
\sum_{i=1}^n \frac{x_i^p}{X^p} = 1 \quad \text{and} \quad \sum_{i=1}^n \frac{y_i^q}{Y^q} = 1 \tag{7}
\end{gather}
$$
Substituting step 7 into the right-hand side of step 6 and applying step 1 yields:
$$
\begin{gather}
\frac{\sum_{i=1}^n x_i y_i}{X Y} \le \frac{1}{p}(1) + \frac{1}{q}(1) = \frac{1}{p} + \frac{1}{q} = 1 \tag{8}
\end{gather}
$$
Multiplying both sides of step 8 by the positive quantity $X Y$ proves Hölder's inequality:
$$
\begin{gather}
\sum_{i=1}^n x_i y_i \le X Y = \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n y_i^q\right)^{1/q} \tag{9}
\end{gather}
$$

Equality in step 4 holds for all $i$ if and only if $a_i = b_i$ for every $i \in \{1, \dots, n\}$. By step 3, this condition is equivalent to:
$$
\begin{gather}
\frac{x_i^p}{X^p} = \frac{y_i^q}{Y^q}, \quad \forall i \in \{1, \dots, n\} \tag{10}
\end{gather}
$$
Step 10 states that the vectors $(x_1^p, \dots, x_n^p)$ and $(y_1^q, \dots, y_n^q)$ are proportional, which is to say, collinear.

---
# Proposition 2
Suppose that $p < 1$ with $p \neq 0$.

Because $\frac{1}{p} + \frac{1}{q} = 1$, the conjugate exponent $q = \frac{p}{p - 1}$ has the opposite sign to $p - 1$, so $p$ and $q$ cannot both be greater than 1. Specifically, when $p \in (0, 1)$, $q < 0$; when $p < 0$, $0 < q < 1$.

Assume that $x_i > 0$ and $y_i > 0$ for all $i \in \{1, \dots, n\}$. Applying [[Proof of Young's Conjugate Inequality|Proposition 2 of Young's Conjugate Inequality]] for $p < 1$ yields the reversed inequality:
$$
\begin{gather}
a_i^{1/p} b_i^{1/q} \ge \frac{a_i}{p} + \frac{b_i}{q} \tag{11}
\end{gather}
$$
with equality if and only if $a_i = b_i$. Setting $a_i = (x_i / X)^p$ and $b_i = (y_i / Y)^q$ in step 11 and repeating the summation of step 6 reverses the inequality sign:
$$
\begin{gather}
\frac{\sum_{i=1}^n x_i y_i}{X Y} \ge \frac{1}{p}(1) + \frac{1}{q}(1) = 1 \tag{12}
\end{gather}
$$
Multiplying by $X Y$ yields:
$$
\begin{gather}
\sum_{i=1}^n x_i y_i \ge \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n y_i^q\right)^{1/q} \tag{13}
\end{gather}
$$
Equality holds if and only if the vectors $(x_1^p, \dots, x_n^p)$ and $(y_1^q, \dots, y_n^q)$ are collinear.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
