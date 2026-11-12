---
dg-publish: true
---
Let $\sum_{n=0}^\infty c_n (z - z_0)^n$ be a formal complex power series with coefficients $c_n \in \mathbb{C}$ centered at $z_0 \in \mathbb{C}$. Without loss of generality, let $z_0 = 0$, so the power series takes the form $\sum_{n=0}^\infty c_n z^n$.

---
# Proposition 1
Suppose that the sequence of terms $(c_n z_0^{*n})_{n=0}^\infty$ is bounded for some nonzero complex number $z_0^* \in \mathbb{C} \setminus \{0\}$, meaning there exists a constant $M \in (0, \infty)$ such that:
$$
\begin{gather}
|c_n (z_0^*)^n| \le M \quad \text{for all } n \in \mathbb{N} \cup \{0\} \tag{1}
\end{gather}
$$
Then for every complex number $z \in \mathbb{C}$ satisfying $|z| < |z_0^*|$, the power series $\sum_{n=0}^\infty c_n z^n$ converges absolutely.

Let $z \in \mathbb{C}$ satisfy $|z| < |z_0^*|$. Because $z_0^* \neq 0$, the ratio:
$$
\begin{gather}
r := \frac{|z|}{|z_0^*|} \tag{2}
\end{gather}
$$
is well-defined and satisfies $0 \le r < 1$.

Express the $n$-th term $c_n z^n$ by factoring out $(z_0^*)^n$:
$$
\begin{gather}
c_n z^n = c_n (z_0^*)^n \left(\frac{z}{z_0^*}\right)^n \tag{3}
\end{gather}
$$
Taking the absolute value of both sides of step 3:
$$
\begin{gather}
|c_n z^n| = |c_n (z_0^*)^n| \left|\frac{z}{z_0^*}\right|^n = |c_n (z_0^*)^n| r^n \tag{4}
\end{gather}
$$
By the boundedness hypothesis of step 1, substituting $|c_n (z_0^*)^n| \le M$ into step 4 yields:
$$
\begin{gather}
|c_n z^n| \le M r^n \quad \text{for all } n \in \mathbb{N} \cup \{0\} \tag{5}
\end{gather}
$$
Consider the geometric series $\sum_{n=0}^\infty M r^n = M \sum_{n=0}^\infty r^n$. Because $0 \le r < 1$, the geometric series converges to a finite real sum:
$$
\begin{gather}
\sum_{n=0}^\infty M r^n = \frac{M}{1 - r} < \infty \tag{6}
\end{gather}
$$
By the direct comparison test for series of non-negative real numbers, the convergence of the dominating geometric series of step 6 implies that:
$$
\begin{gather}
\sum_{n=0}^\infty |c_n z^n| \le \sum_{n=0}^\infty M r^n = \frac{M}{1 - r} < \infty \tag{7}
\end{gather}
$$
Hence, the power series $\sum_{n=0}^\infty c_n z^n$ converges absolutely for every $z$ with $|z| < |z_0^*|$. By [[Proof of Algebraic and Metric Completeness of C|the metric completeness of the complex plane]], absolute convergence implies convergence in $\mathbb{C}$.

---
# Proposition 2
Let $R_0 \in [0, |z_0^*|)$. The power series $\sum_{n=0}^\infty c_n z^n$ converges uniformly on the closed disk $\overline{B}(0, R_0) = \{z \in \mathbb{C} : |z| \le R_0\}$. Furthermore, if the power series diverges at some point $z_1 \in \mathbb{C}$, then it diverges for all $z \in \mathbb{C}$ satisfying $|z| > |z_1|$.

Let $R_0$ satisfy $0 \le R_0 < |z_0^*|$. For every $z \in \overline{B}(0, R_0)$, $|z| \le R_0$. Setting $\rho := \frac{R_0}{|z_0^*|} < 1$, step 5 implies that for all $z \in \overline{B}(0, R_0)$:
$$
\begin{gather}
|c_n z^n| = |c_n (z_0^*)^n| \left|\frac{z}{z_0^*}\right|^n \le M \left(\frac{R_0}{|z_0^*|}\right)^n = M \rho^n \tag{8}
\end{gather}
$$
Define $M_n := M \rho^n$. Since $\rho \in [0, 1)$, the series of constants converges:
$$
\begin{gather}
\sum_{n=0}^\infty M_n = \sum_{n=0}^\infty M \rho^n = \frac{M}{1 - \rho} < \infty \tag{9}
\end{gather}
$$
By the Weierstrass $M$-test, the condition $|c_n z^n| \le M_n$ together with the convergence of $\sum_{n=0}^\infty M_n$ proves that the power series $\sum_{n=0}^\infty c_n z^n$ converges absolutely and uniformly on the closed disk $\overline{B}(0, R_0)$.

Finally, suppose by contradiction that the series converges at some point $z \in \mathbb{C}$ with $|z| > |z_1|$ where the series is known to diverge at $z_1$.

If $\sum_{n=0}^\infty c_n z^n$ converges, the sequence of terms $c_n z^n$ must converge to zero as $n \to \infty$, and therefore $(c_n z^n)_{n=0}^\infty$ is bounded.

Applying Proposition 1 with $z_0^* = z$, because $|z_1| < |z|$, the series $\sum_{n=0}^\infty c_n z_1^n$ must converge absolutely. This contradicts the hypothesis that the series diverges at $z_1$.

Therefore, if the power series diverges at $z_1$, it must diverge for all $z \in \mathbb{C}$ satisfying $|z| > |z_1|$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$