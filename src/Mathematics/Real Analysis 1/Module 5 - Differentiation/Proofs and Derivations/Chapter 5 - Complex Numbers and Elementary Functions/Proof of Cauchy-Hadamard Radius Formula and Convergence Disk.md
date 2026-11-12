---
dg-publish: true
---
Let $\sum_{n=0}^\infty c_n (z - z_0)^n$ be a formal power series with complex coefficients $c_n \in \mathbb{C}$ and center $z_0 \in \mathbb{C}$. Let $L \in [0, \infty]$ denote the limit superior of the sequence of root moduli:
$$
\begin{gather}
L := \limsup_{n \to \infty} \sqrt[n]{|c_n|} \tag{1}
\end{gather}
$$
Define the radius of convergence $R \in [0, \infty]$ by the reciprocal convention:
$$
\begin{gather}
R := \begin{cases} \infty & \text{if } L = 0 \\[2mm] \dfrac{1}{L} & \text{if } 0 < L < \infty \\[2mm] 0 & \text{if } L = \infty \end{cases} \tag{2}
\end{gather}
$$

The proof establishes the behavior of the series across three mutually exclusive regions of the complex plane: the open disk of convergence $|z - z_0| < R$, compact subsets of this open disk, and the exterior domain $|z - z_0| > R$.

**Interior Convergence ($|z - z_0| < R$):**
Consider an arbitrary point $z \in \mathbb{C}$ such that $|z - z_0| < R$. If $R = 0$, this open disk is empty, so assume $R > 0$. 

Choose a real number $\rho$ strictly intermediate between $|z - z_0|$ and $R$:
$$
\begin{gather}
|z - z_0| < \rho < R \tag{3}
\end{gather}
$$
Taking the reciprocal reverses the strict inequality. Since $R = 1/L$ (with $1/\infty = 0$), step 3 implies:
$$
\begin{gather}
\frac{1}{\rho} > \frac{1}{R} = L = \limsup_{n \to \infty} \sqrt[n]{|c_n|} \tag{4}
\end{gather}
$$
Set $\varepsilon := \frac{1}{\rho} - L > 0$. By the definition of the limit superior as the infimum of the supremum tail bounds, there exists an integer $N \in \mathbb{N}$ such that for all $n \geq N$:
$$
\begin{gather}
\sqrt[n]{|c_n|} \leq L + \varepsilon = \frac{1}{\rho} \tag{5}
\end{gather}
$$
Raising both sides of step 5 to the $n$-th power yields the coefficient bound $|c_n| \leq \rho^{-n}$ for all $n \geq N$. 

Multiplying this bound by $|z - z_0|^n$ provides an estimate for the general term of the series:
$$
\begin{gather}
|c_n (z - z_0)^n| = |c_n| |z - z_0|^n \leq \left( \frac{|z - z_0|}{\rho} \right)^n \tag{6}
\end{gather}
$$
valid for every index $n \geq N$. Define $q := \frac{|z - z_0|}{\rho}$. By step 3, $q$ satisfies $0 \leq q < 1$. 

The geometric series $\sum_{n=0}^\infty q^n$ converges to $\frac{1}{1 - q} < \infty$. By the direct comparison test for real series, step 6 demonstrates that the series of absolute values $\sum_{n=0}^\infty |c_n (z - z_0)^n|$ converges. Consequently, by the Cauchy completeness of $\mathbb{C}$, the power series $\sum_{n=0}^\infty c_n (z - z_0)^n$ converges absolutely at every point $z \in B(z_0, R)$.

**Uniform Convergence on Compact Subsets:**
Let $K \subset B(z_0, R)$ be a compact subset of the open convergence disk. Because $K$ is compact and the distance function $z \mapsto |z - z_0|$ is continuous, the supremum of $|z - z_0|$ on $K$ is attained at some point in $K$. Hence:
$$
\begin{gather}
r_K := \sup_{z \in K} |z - z_0| < R \tag{7}
\end{gather}
$$
Select a radius $\rho_0$ such that $r_K < \rho_0 < R$. Repeating the construction of step 5, there exists an index $N_0 \in \mathbb{N}$ such that $|c_n| \leq \rho_0^{-n}$ for all $n \geq N_0$. 

For every $z \in K$ and every $n \geq N_0$, the terms are uniformly bounded:
$$
\begin{gather}
\sup_{z \in K} |c_n (z - z_0)^n| \leq |c_n| r_K^n \leq \left( \frac{r_K}{\rho_0} \right)^n \tag{8}
\end{gather}
$$
Because $0 \leq \frac{r_K}{\rho_0} < 1$, the terms $M_n := (r_K / \rho_0)^n$ form a convergent numerical geometric series $\sum_{n=0}^\infty M_n < \infty$. 

By the Weierstrass $M$-test, the series $\sum_{n=0}^\infty c_n (z - z_0)^n$ converges uniformly and absolutely on $K$. Since every closed disk $\overline{B}(z_0, r) = \{z \in \mathbb{C} : |z - z_0| \leq r\}$ with $r < R$ is compact, uniform convergence holds on all closed subdisks strictly inside $B(z_0, R)$.

**Exterior Divergence ($|z - z_0| > R$):**
Now consider a point $z \in \mathbb{C}$ such that $|z - z_0| > R$. If $R = \infty$, the exterior is empty, so assume $R < \infty$. 

Choose a real number $\rho$ strictly between $R$ and $|z - z_0|$:
$$
\begin{gather}
R < \rho < |z - z_0| \tag{9}
\end{gather}
$$
From step 9, taking reciprocals yields:
$$
\begin{gather}
\frac{1}{\rho} < \frac{1}{R} = L = \limsup_{n \to \infty} \sqrt[n]{|c_n|} \tag{10}
\end{gather}
$$
By the definition of the limit superior as the supremum of subsequential limits, the sequence $\sqrt[n]{|c_n|}$ must exceed $\frac{1}{\rho}$ infinitely often. That is, there exists a strictly increasing sequence of positive integers $(n_k)_{k=1}^\infty$ such that for all $k \in \mathbb{N}$:
$$
\begin{gather}
\sqrt[n_k]{|c_{n_k}|} > \frac{1}{\rho} \tag{11}
\end{gather}
$$
Raising both sides of step 11 to the power $n_k$ gives $|c_{n_k}| > \rho^{-n_k}$. 

Evaluating the modulus of the corresponding terms of the power series at $z$ yields:
$$
\begin{gather}
|c_{n_k} (z - z_0)^{n_k}| = |c_{n_k}| |z - z_0|^{n_k} > \left( \frac{|z - z_0|}{\rho} \right)^{n_k} \tag{12}
\end{gather}
$$
Because $|z - z_0| > \rho$, the ratio satisfies $\frac{|z - z_0|}{\rho} > 1$. Therefore:
$$
\begin{gather}
\lim_{k \to \infty} \left( \frac{|z - z_0|}{\rho} \right)^{n_k} = \infty \tag{13}
\end{gather}
$$
Combining step 12 and step 13 demonstrates that the sequence of general terms $a_n(z) := c_n (z - z_0)^n$ does not converge to zero as $n \to \infty$; in fact, the subsequence of moduli is unbounded:
$$
\begin{gather}
\limsup_{n \to \infty} |c_n (z - z_0)^n| = \infty \tag{14}
\end{gather}
$$
By the divergence test (the $n$-th term test for series convergence), a necessary condition for the convergence of a series $\sum a_n$ is $\lim_{n \to \infty} a_n = 0$. Because step 14 precludes the terms from tending to zero, the power series $\sum_{n=0}^\infty c_n (z - z_0)^n$ diverges for every $z$ satisfying $|z - z_0| > R$.
$$
\textbf{Q.E.D}
$$