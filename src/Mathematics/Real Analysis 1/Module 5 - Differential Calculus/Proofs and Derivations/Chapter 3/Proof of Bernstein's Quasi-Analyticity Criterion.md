---
dg-publish: true
---
Let $f \in C^\infty([-R, R])$, and suppose there exists a constant $C > 0$ such that:
$$
\begin{gather}
\sup_{x \in [-R, R]} |f^{(n)}(x)| \le C^n n! \quad \forall n \in \mathbb{N} \tag{1}
\end{gather}
$$

Let $x_0 = 0$, and let $x \in [-R, R]$ with $|x| < \frac{1}{C}$.

By Taylor's Theorem with the Lagrange Remainder, for each $n \in \mathbb{N}$, there exists an intermediate point $\xi_n$ strictly between 0 and $x$ such that:
$$
\begin{gather}
f(x) - P_n(0; x) = R_n(0; x) = \frac{f^{(n+1)}(\xi_n)}{(n+1)!} x^{n+1} \tag{2}
\end{gather}
$$

Taking the absolute value on both sides of the equation of step 2:
$$
\begin{gather}
|R_n(0; x)| = \frac{|f^{(n+1)}(\xi_n)|}{(n+1)!} |x|^{n+1} \tag{3}
\end{gather}
$$

Because $\xi_n \in (-|x|, |x|) \subset [-R, R]$, applying the hypothesis of step 1 to order $n+1$:
$$
\begin{gather}
|f^{(n+1)}(\xi_n)| \le C^{n+1} (n+1)! \tag{4}
\end{gather}
$$

Substituting the bound of step 4 into the equation of step 3:
$$
\begin{gather}
|R_n(0; x)| \le \frac{C^{n+1}(n+1)!}{(n+1)!} |x|^{n+1} = (C |x|)^{n+1} \tag{5}
\end{gather}
$$

Because $|x| < \frac{1}{C}$, the quantity $q := C |x| < 1$. 

By the properties of geometric sequences established in Module 3:
$$
\begin{gather}
\lim_{n \to \infty} q^{n+1} = \lim_{n \to \infty} (C |x|)^{n+1} = 0 \tag{6}
\end{gather}
$$

By the squeeze theorem applied to $0 \le |R_n(0; x)| \le q^{n+1}$:
$$
\begin{gather}
\lim_{n \to \infty} R_n(0; x) = 0 \tag{7}
\end{gather}
$$

Consequently:
$$
\begin{gather}
f(x) = \lim_{n \to \infty} P_n(0; x) = \sum_{k=0}^\infty \frac{f^{(k)}(0)}{k!} x^k \quad \forall x \in \left( -\min\left(R, \frac{1}{C}\right), \min\left(R, \frac{1}{C}\right) \right) \tag{8}
\end{gather}
$$
proving that $f$ is real-analytic on this neighborhood.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
