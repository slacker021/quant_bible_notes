---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a continuous function satisfying the midpoint-convexity condition:
$$
\begin{gather}
f\left(\frac{x_1 + x_2}{2}\right) \le \frac{f(x_1) + f(x_2)}{2}, \quad \forall x_1, x_2 \in (a, b) \tag{1}
\end{gather}
$$

To prove that $f$ is convex on $(a, b)$, it must be shown that for any $x_1, x_2 \in (a, b)$ and any $\lambda \in [0, 1]$:
$$
\begin{gather}
f\big((1 - \lambda)x_1 + \lambda x_2\big) \le (1 - \lambda)f(x_1) + \lambda f(x_2) \tag{2}
\end{gather}
$$

Let $D \subset [0, 1]$ denote the set of dyadic rationals in the unit interval:
$$
\begin{gather}
D := \left\{ \frac{m}{2^k} \ \middle|\ k \in \mathbb{N} \cup \{0\}, \ m \in \{0, 1, \dots, 2^k\} \right\} \tag{3}
\end{gather}
$$

**Step 1: Establishing convexity for dyadic coefficients by induction on $k$.**
For $k = 1$, the non-trivial dyadic point is $\lambda = \frac{1}{2}$, for which step 2 coincides identically with the midpoint hypothesis of step 1.

Assume that for some integer $k \ge 1$, step 2 holds for all dyadic numbers of the form $\lambda = \frac{m}{2^k}$ where $m \in \{0, 1, \dots, 2^k\}$. Consider a dyadic fraction at the next refinement level:
$$
\begin{gather}
\lambda = \frac{m}{2^{k+1}}, \quad m \in \{0, 1, \dots, 2^{k+1}\} \tag{4}
\end{gather}
$$
If $m$ is even, $m = 2j$, then $\frac{m}{2^{k+1}} = \frac{j}{2^k}$, which already belongs to the previous refinement level and satisfies step 2 by the induction hypothesis.

If $m$ is odd, write $m = 2j + 1$ with $0 \le j < 2^k$. Then $\lambda$ can be represented as the exact arithmetic mean of two dyadics of order $k$:
$$
\begin{gather}
\lambda = \frac{2j + 1}{2^{k+1}} = \frac{1}{2} \left(\frac{j}{2^k} + \frac{j + 1}{2^k}\right) = \frac{\lambda_1 + \lambda_2}{2} \tag{5}
\end{gather}
$$
where $\lambda_1 := \frac{j}{2^k} \in D$ and $\lambda_2 := \frac{j+1}{2^k} \in D$.

Let $u := (1 - \lambda_1)x_1 + \lambda_1 x_2$ and $v := (1 - \lambda_2)x_1 + \lambda_2 x_2$. The argument corresponding to $\lambda$ is:
$$
\begin{gather}
(1 - \lambda)x_1 + \lambda x_2 = \frac{u + v}{2} \tag{6}
\end{gather}
$$
Applying the midpoint inequality of step 1 to $\frac{u + v}{2}$ gives:
$$
\begin{gather}
f\left(\frac{u + v}{2}\right) \le \frac{f(u) + f(v)}{2} \tag{7}
\end{gather}
$$
By the induction hypothesis, step 2 holds for both $u$ and $v$:
$$
\begin{gather}
f(u) \le (1 - \lambda_1)f(x_1) + \lambda_1 f(x_2) \tag{8}
\end{gather}
$$
$$
\begin{gather}
f(v) \le (1 - \lambda_2)f(x_1) + \lambda_2 f(x_2) \tag{9}
\end{gather}
$$
Substituting step 8 and step 9 into step 7 yields:
$$
\begin{gather}
f\left(\frac{u + v}{2}\right) \le \frac{(1 - \lambda_1) + (1 - \lambda_2)}{2} f(x_1) + \frac{\lambda_1 + \lambda_2}{2} f(x_2) = (1 - \lambda)f(x_1) + \lambda f(x_2) \tag{10}
\end{gather}
$$
By induction, step 2 holds for all $\lambda \in D$.

**Step 2: Extension to arbitrary real $\lambda \in [0, 1]$ via continuity.**
Let $\lambda \in [0, 1]$ be an arbitrary real number. The set of dyadic rationals $D$ is dense in the real interval $[0, 1]$. Consequently, there exists a sequence of dyadic numbers $(\lambda_n)_{n=1}^\infty \subset D$ such that:
$$
\begin{gather}
\lim_{n \to \infty} \lambda_n = \lambda \tag{11}
\end{gather}
$$
For each $n \in \mathbb{N}$, because $\lambda_n \in D$, the dyadic convexity established in Step 1 holds:
$$
\begin{gather}
f\big((1 - \lambda_n)x_1 + \lambda_n x_2\big) \le (1 - \lambda_n)f(x_1) + \lambda_n f(x_2) \tag{12}
\end{gather}
$$

Because $f$ is continuous on $(a, b)$, the composition of $f$ with the linear affine path $t \mapsto (1 - t)x_1 + t x_2$ is continuous on $[0, 1]$. Taking the limit as $n \to \infty$ on both sides of step 12 yields:
$$
\begin{gather}
\lim_{n \to \infty} f\big((1 - \lambda_n)x_1 + \lambda_n x_2\big) = f\left(\lim_{n \to \infty} \big((1 - \lambda_n)x_1 + \lambda_n x_2\big)\right) = f\big((1 - \lambda)x_1 + \lambda x_2\big) \tag{13}
\end{gather}
$$
and
$$
\begin{gather}
\lim_{n \to \infty} \big[(1 - \lambda_n)f(x_1) + \lambda_n f(x_2)\big] = (1 - \lambda)f(x_1) + \lambda f(x_2) \tag{14}
\end{gather}
$$
By the preservation of non-strict inequalities under limits, step 12 implies:
$$
\begin{gather}
f\big((1 - \lambda)x_1 + \lambda x_2\big) \le (1 - \lambda)f(x_1) + \lambda f(x_2) \tag{15}
\end{gather}
$$
Because $x_1, x_2 \in (a, b)$ and $\lambda \in [0, 1]$ were arbitrary, $f$ is convex on $(a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
