---
dg-publish: true
---
Let $P(z) = a_n z^n + a_{n-1} z^{n-1} + \dots + a_1 z + a_0$ be a non-constant polynomial with complex coefficients ($a_n \neq 0, n \ge 1$).

We must prove that there exists $z_0 \in \mathbb{C}$ such that $P(z_0) = 0$.

### Step 1: Growth at Infinity
For $z \neq 0$, factor out $a_n z^n$:
$$
\begin{gather}
P(z) = a_n z^n \left( 1 + \frac{a_{n-1}}{a_n z} + \dots + \frac{a_0}{a_n z^n} \right) \tag{1}
\end{gather}
$$

Taking moduli and applying the reverse triangle inequality:
$$
\begin{gather}
|P(z)| \ge |a_n| |z|^n \left( 1 - \sum_{k=1}^n \frac{|a_{n-k}|}{|a_n| |z|^k} \right) \tag{2}
\end{gather}
$$

As $|z| \to \infty$, the sum $\sum_{k=1}^n \frac{|a_{n-k}|}{|a_n| |z|^k} \to 0$. Therefore, there exists a radius $R_1 > 0$ such that for all $|z| \ge R_1$:
$$
\begin{gather}
1 - \sum_{k=1}^n \frac{|a_{n-k}|}{|a_n| |z|^k} \ge \frac{1}{2} \implies |P(z)| \ge \frac{1}{2} |a_n| |z|^n \tag{3}
\end{gather}
$$

The equation of step 3 proves that $\lim_{|z| \to \infty} |P(z)| = \infty$.

### Step 2: Attainment of the Minimum Modulus
Because $\lim_{|z| \to \infty} |P(z)| = \infty$, there exists a large radius $R \ge R_1$ such that:
$$
\begin{gather}
|P(z)| > |P(0)| \quad \forall |z| > R \tag{4}
\end{gather}
$$

Consider the closed disk $\bar{B}_R(0) = \{z \in \mathbb{C} : |z| \le R\}$. 

Because $\bar{B}_R(0) \subset \mathbb{R}^2$ is closed and bounded, by the Heine-Borel Theorem (Module 2) it is compact. Because $P(z)$ is a polynomial, the real-valued function $z \mapsto |P(z)|$ is continuous on $\bar{B}_R(0)$.

By the Weierstrass Extreme Value Theorem (the Weierstrass Extreme Value Theorem (Module 4)), the continuous function $|P(z)|$ attains an absolute minimum on the compact disk $\bar{B}_R(0)$ at some point $z_0 \in \bar{B}_R(0)$:
$$
\begin{gather}
|P(z_0)| = \min_{z \in \bar{B}_R(0)} |P(z)| \tag{5}
\end{gather}
$$

Because $0 \in \bar{B}_R(0)$, $|P(z_0)| \le |P(0)|$. By the condition of step 4, for any point outside the disk ($|z| > R$), $|P(z)| > |P(0)| \ge |P(z_0)|$. 

Consequently, $z_0$ is a *global minimum* of $|P(z)|$ across the entire complex plane:
$$
\begin{gather}
|P(z_0)| \le |P(z)| \quad \forall z \in \mathbb{C} \tag{6}
\end{gather}
$$

### Step 3: D'Alembert's Minimum Modulus Lemma
We prove by contradiction that $|P(z_0)| = 0$.

Suppose for contradiction that $P(z_0) = c_0 \neq 0$. 

Expand the polynomial $P(z)$ in powers of $(z - z_0)$ (Taylor expansion for polynomials):
$$
\begin{gather}
P(z) = P(z_0 + (z - z_0)) = c_0 + c_k (z - z_0)^k + c_{k+1}(z - z_0)^{k+1} + \dots + c_n (z - z_0)^n \tag{7}
\end{gather}
$$
where $k \in \{1, \dots, n\}$ is the smallest positive integer such that $c_k \neq 0$.

Factor out $c_0$:
$$
\begin{gather}
P(z) = c_0 \left( 1 + \frac{c_k}{c_0}(z - z_0)^k + (z - z_0)^{k+1} Q(z) \right) \tag{8}
\end{gather}
$$
where $Q(z)$ is a polynomial in $(z - z_0)$.

Write the non-zero complex number $-\frac{c_0}{c_k}$ in polar form:
$$
\begin{gather}
-\frac{c_0}{c_k} = r_0 e^{i\alpha} \quad (r_0 > 0, \ \alpha \in \mathbb{R}) \tag{9}
\end{gather}
$$

Let $z - z_0 = \rho e^{i\alpha/k}$ for a small positive parameter $\rho > 0$. Then:
$$
\begin{gather}
(z - z_0)^k = \rho^k e^{i\alpha} \tag{10}
\end{gather}
$$

Multiplying by $\frac{c_k}{c_0}$:
$$
\begin{gather}
\frac{c_k}{c_0}(z - z_0)^k = \frac{c_k}{c_0} \rho^k e^{i\alpha} = \rho^k \left( \frac{c_k}{c_0} e^{i\alpha} \right) = \rho^k \left( -\frac{1}{r_0} \right) = -\frac{\rho^k}{r_0} \tag{11}
\end{gather}
$$

Substituting the equation of step 11 into the equation of step 8:
$$
\begin{gather}
P(z) = c_0 \left( 1 - \frac{\rho^k}{r_0} + \rho^{k+1} e^{i(k+1)\alpha/k} Q(z) \right) \tag{12}
\end{gather}
$$

Choose $\rho > 0$ sufficiently small such that $\frac{\rho^k}{r_0} < 1$. Taking the modulus:
$$
\begin{gather}
|P(z)| = |c_0| \left| 1 - \frac{\rho^k}{r_0} + \rho^{k+1} e^{i(k+1)\alpha/k} Q(z) \right| \le |c_0| \left( 1 - \frac{\rho^k}{r_0} + \rho^{k+1} |Q(z)| \right) \tag{13}
\end{gather}
$$

Because $Q(z)$ is bounded for small $\rho$, $|Q(z)| \le M$. Factoring out $\rho^k$:
$$
\begin{gather}
|P(z)| \le |c_0| \left( 1 - \rho^k \left( \frac{1}{r_0} - \rho M \right) \right) \tag{14}
\end{gather}
$$

Choosing $\rho \in \left(0, \frac{1}{2 r_0 M}\right)$, the term $\frac{1}{r_0} - \rho M > \frac{1}{2 r_0} > 0$. 

Therefore:
$$
\begin{gather}
|P(z)| \le |c_0| \left( 1 - \frac{\rho^k}{2 r_0} \right) < |c_0| = |P(z_0)| \tag{15}
\end{gather}
$$

The inequality of step 15 directly contradicts the fact (equation 6) that $|P(z_0)|$ is the global minimum of $|P(z)|$ on $\mathbb{C}$. 

This contradiction forces $|P(z_0)| = 0 \implies P(z_0) = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
