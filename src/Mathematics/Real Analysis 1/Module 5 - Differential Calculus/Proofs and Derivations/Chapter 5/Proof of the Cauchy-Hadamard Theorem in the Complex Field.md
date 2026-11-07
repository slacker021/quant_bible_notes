---
dg-publish: true
---
Let $\sum_{n=0}^\infty c_n (z - z_0)^n$ be a complex power series with coefficients $c_n \in \mathbb{C}$. 

Define $L := \limsup_{n \to \infty} \sqrt[n]{|c_n|} \in [0, \infty]$. Let $R := \frac{1}{L}$ (with $R = \infty$ if $L = 0$, and $R = 0$ if $L = \infty$).

### Part 1: Absolute Convergence for $|z - z_0| < R$
Assume $R > 0$, and let $z \in \mathbb{C}$ satisfy $|z - z_0| < R$. 

Then there exists a real number $r$ such that:
$$
\begin{gather}
|z - z_0| < r < R \implies \frac{1}{r} > \frac{1}{R} = L \tag{1}
\end{gather}
$$

Set $\varepsilon := \frac{1}{r} - L > 0$. By definition of the limit superior (Module 3):
$$
\begin{gather}
\limsup_{n \to \infty} \sqrt[n]{|c_n|} = L < L + \varepsilon = \frac{1}{r} \tag{2}
\end{gather}
$$

Therefore, there exists an integer $N \in \mathbb{N}$ such that for all $n \ge N$:
$$
\begin{gather}
\sqrt[n]{|c_n|} < \frac{1}{r} \implies |c_n| < \frac{1}{r^n} \tag{3}
\end{gather}
$$

Multiplying the inequality of step 3 by $|z - z_0|^n$:
$$
\begin{gather}
|c_n (z - z_0)^n| = |c_n| |z - z_0|^n < \left( \frac{|z - z_0|}{r} \right)^n \quad \forall n \ge N \tag{4}
\end{gather}
$$

Set $q := \frac{|z - z_0|}{r}$. By the inequality of step 1, $0 \le q < 1$. 

The series $\sum_{n=N}^\infty q^n$ is a convergent geometric series of real numbers. By the Direct Comparison Test for real series (Module 3), the series:
$$
\begin{gather}
\sum_{n=0}^\infty |c_n (z - z_0)^n| \tag{5}
\end{gather}
$$
converges. Because absolute convergence in the complete metric space $\mathbb{C}$ implies convergence (since $|\operatorname{Re}(w)| \le |w|$ and $|\operatorname{Im}(w)| \le |w|$), the complex power series converges absolutely.

### Part 2: Divergence for $|z - z_0| > R$
Assume $R < \infty$, and let $|z - z_0| > R$. 

Then $\frac{1}{|z - z_0|} < \frac{1}{R} = L$. 

By properties of the limit superior, there exists a subsequence of indices $\{n_k\}_{k=1}^\infty$ such that:
$$
\begin{gather}
\sqrt[n_k]{|c_{n_k}|} > \frac{1}{|z - z_0|} \implies |c_{n_k}| |z - z_0|^{n_k} > 1 \quad \forall k \in \mathbb{N} \tag{6}
\end{gather}
$$

Consequently, the terms $a_n = c_n (z - z_0)^n$ do not converge to zero: $\lim_{n \to \infty} a_n \neq 0$. 

By the divergence test for infinite series (Module 3), the series diverges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
