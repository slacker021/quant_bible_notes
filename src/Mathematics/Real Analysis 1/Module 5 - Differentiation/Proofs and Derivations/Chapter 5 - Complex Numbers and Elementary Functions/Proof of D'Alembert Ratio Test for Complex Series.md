---
dg-publish: true
---
Let $\sum_{n=1}^\infty a_n$ be an infinite series with non-zero complex terms $a_n \in \mathbb{C} \setminus \{0\}$. Suppose the limit of the moduli of successive term ratios exists in $[0, \infty]$:
$$
\begin{gather}
\ell := \lim_{n \to \infty} \left| \frac{a_{n+1}}{a_n} \right| \tag{1}
\end{gather}
$$

The proof investigates the convergence behavior under the two principal conditions $\ell < 1$ and $\ell > 1$, and establishes the connection to the root test and the Cauchy-Hadamard radius formula.

**Absolute Convergence when $\ell < 1$:**
Assume $\ell < 1$. Because $\ell \in [0, 1)$, one can select a real number $q$ strictly between $\ell$ and $1$:
$$
\begin{gather}
\ell < q < 1 \tag{2}
\end{gather}
$$
Define $\varepsilon := q - \ell > 0$. By the definition of the limit in step 1, there exists an index $N \in \mathbb{N}$ such that for all $n \geq N$:
$$
\begin{gather}
\left| \left| \frac{a_{n+1}}{a_n} \right| - \ell \right| < \varepsilon \tag{3}
\end{gather}
$$
The right-hand inequality in step 3 implies that for every $n \geq N$:
$$
\begin{gather}
\left| \frac{a_{n+1}}{a_n} \right| < \ell + \varepsilon = q \tag{4}
\end{gather}
$$
Multiplying both sides of step 4 by $|a_n| > 0$ yields:
$$
\begin{gather}
|a_{n+1}| < q |a_n|, \quad \forall n \geq N \tag{5}
\end{gather}
$$
Applying step 5 inductively for any integer $k \geq 0$ produces:
$$
\begin{gather}
|a_{N+k}| \leq q^k |a_N| \tag{6}
\end{gather}
$$
Setting $n = N + k$, step 6 can be rewritten as:
$$
\begin{gather}
|a_n| \leq |a_N| q^{n-N} = \left( \frac{|a_N|}{q^N} \right) q^n, \quad \forall n \geq N \tag{7}
\end{gather}
$$
Define the positive constant $C := \frac{|a_N|}{q^N}$. Step 7 asserts that $|a_n| \leq C q^n$ for all $n \geq N$.

Because $0 \leq q < 1$, the geometric series $\sum_{n=N}^\infty C q^n$ converges to the finite sum:
$$
\begin{gather}
\sum_{n=N}^\infty C q^n = C \frac{q^N}{1 - q} < \infty \tag{8}
\end{gather}
$$
By the direct comparison test for real non-negative series, the tail series of absolute values $\sum_{n=N}^\infty |a_n|$ converges. 

Adding the finite sum of the initial $N-1$ terms yields:
$$
\begin{gather}
\sum_{n=1}^\infty |a_n| = \sum_{n=1}^{N-1} |a_n| + \sum_{n=N}^\infty |a_n| < \infty \tag{9}
\end{gather}
$$
By the metric completeness of $\mathbb{C}$, absolute convergence of a complex series implies convergence. Therefore, the series $\sum_{n=1}^\infty a_n$ converges absolutely when $\ell < 1$.

**Divergence when $\ell > 1$:**
Assume $\ell > 1$ (which includes the case $\ell = \infty$). 

Choose a real number $q$ strictly between $1$ and $\ell$:
$$
\begin{gather}
1 < q < \ell \tag{10}
\end{gather}
$$
By the definition of the limit (or divergence to infinity if $\ell = \infty$), there exists an index $N \in \mathbb{N}$ such that for all $n \geq N$:
$$
\begin{gather}
\left| \frac{a_{n+1}}{a_n} \right| > q > 1 \tag{11}
\end{gather}
$$
Multiplying step 11 by $|a_n| > 0$ gives:
$$
\begin{gather}
|a_{n+1}| > |a_n|, \quad \forall n \geq N \tag{12}
\end{gather}
$$
Inductively applying step 12 shows that for all $k \geq 0$:
$$
\begin{gather}
|a_{N+k}| \geq q^k |a_N| > |a_N| > 0 \tag{13}
\end{gather}
$$
Since $q > 1$, as $k \to \infty$, $q^k |a_N| \to \infty$. Thus:
$$
\begin{gather}
\lim_{n \to \infty} |a_n| = \infty \neq 0 \tag{14}
\end{gather}
$$
Because the terms $a_n$ do not converge to zero, by the divergence test, the complex series $\sum_{n=1}^\infty a_n$ diverges.

**Limiting Equivalence to the Cauchy-Hadamard Root Test:**
To relate the ratio test to the radius of convergence of a power series $\sum_{n=0}^\infty c_n (z - z_0)^n$, consider the sequence of coefficients with non-zero terms $c_n \neq 0$. 

A classical theorem on limits of real sequences states that if a sequence of positive numbers $(u_n)_{n=1}^\infty$ satisfies $\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = L$, then:
$$
\begin{gather}
\lim_{n \to \infty} \sqrt[n]{u_n} = L \tag{15}
\end{gather}
$$
To verify step 15, let $\varepsilon > 0$ be arbitrary. Choose $N \in \mathbb{N}$ such that $L - \varepsilon < \frac{u_{k+1}}{u_k} < L + \varepsilon$ for all $k \geq N$. 

Multiplying these inequalities for $k = N, N+1, \dots, n-1$ yields:
$$
\begin{gather}
(L - \varepsilon)^{n-N} < \frac{u_n}{u_N} < (L + \varepsilon)^{n-N} \tag{16}
\end{gather}
$$
Multiplying step 16 by $u_N$ and taking the $n$-th root:
$$
\begin{gather}
\sqrt[n]{u_N} (L - \varepsilon)^{1 - N/n} < \sqrt[n]{u_n} < \sqrt[n]{u_N} (L + \varepsilon)^{1 - N/n} \tag{17}
\end{gather}
$$
Taking the limit as $n \to \infty$ in step 17, since $\lim_{n \to \infty} u_N^{1/n} = 1$ and $\lim_{n \to \infty} (1 - N/n) = 1$:
$$
\begin{gather}
L - \varepsilon \leq \liminf_{n \to \infty} \sqrt[n]{u_n} \leq \limsup_{n \to \infty} \sqrt[n]{u_n} \leq L + \varepsilon \tag{18}
\end{gather}
$$
Letting $\varepsilon \to 0$ establishes step 15.

Applying step 15 to $u_n = |c_n|$, whenever the coefficient ratio limit $\lim_{n \to \infty} \left| \frac{c_{n+1}}{c_n} \right|$ exists, the Cauchy-Hadamard limit superior satisfies:
$$
\begin{gather}
\frac{1}{R} = \limsup_{n \to \infty} \sqrt[n]{|c_n|} = \lim_{n \to \infty} \left| \frac{c_{n+1}}{c_n} \right| \tag{19}
\end{gather}
$$
Taking reciprocals yields the standard ratio formula for the radius of convergence:
$$
\begin{gather}
R = \lim_{n \to \infty} \left| \frac{c_n}{c_{n+1}} \right| \tag{20}
\end{gather}
$$
$$
\textbf{Q.E.D}
$$