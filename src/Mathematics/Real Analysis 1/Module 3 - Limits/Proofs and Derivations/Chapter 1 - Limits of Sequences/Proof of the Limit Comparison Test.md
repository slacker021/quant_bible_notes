---
dg-publish: true
---
Let $\sum_{n=1}^\infty x_n$ and $\sum_{n=1}^\infty y_n$ be two series of real numbers with non-negative terms such that $x_n \ge 0$ and $y_n > 0$ for all $n \in \mathbb{N}$. Assume that the limiting ratio of their terms exists as a finite and strictly positive real number:
$$
\begin{gather}
c := \lim_{n \to \infty} \frac{x_n}{y_n}, \quad \text{where } 0 < c < \infty \tag{1}
\end{gather}
$$
Define the positive error tolerance $\varepsilon := \frac{c}{2} > 0$. By definition of sequence convergence applied to step 1, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
\left| \frac{x_n}{y_n} - c \right| < \frac{c}{2} \iff c - \frac{c}{2} < \frac{x_n}{y_n} < c + \frac{c}{2} \iff \frac{c}{2} < \frac{x_n}{y_n} < \frac{3c}{2} \tag{2}
\end{gather}
$$
Because $y_n > 0$ for all $n \in \mathbb{N}$, multiplying step 2 across by $y_n$ preserves the strict order inequalities:
$$
\begin{gather}
\frac{c}{2} y_n < x_n < \frac{3c}{2} y_n \quad \forall n > N \tag{3}
\end{gather}
$$

**Simultaneous Convergence:**
First, assume that the series $\sum_{n=1}^\infty y_n$ converges to a finite sum $Y \in \mathbb{R}$. By the [[Proof of Arithmetic Properties of Series|scalar multiple rule for series]], the scaled series converges:
$$
\begin{gather}
\sum_{n=1}^\infty \frac{3c}{2} y_n = \frac{3c}{2} \sum_{n=1}^\infty y_n = \frac{3c}{2} Y < \infty \tag{4}
\end{gather}
$$
From the upper bound in step 3, $x_n < \frac{3c}{2} y_n$ holds for all $n > N$. By the [[Proof of the Standard Comparison Test|Standard Comparison Test]], the convergence of $\sum_{n=1}^\infty \frac{3c}{2} y_n$ in step 4 implies that $\sum_{n=1}^\infty x_n$ converges.

Conversely, assume that the series $\sum_{n=1}^\infty x_n$ converges to a finite sum $X \in \mathbb{R}$. Multiplying the lower bound $\frac{c}{2} y_n < x_n$ in step 3 by the positive scalar $\frac{2}{c} > 0$ yields
$$
\begin{gather}
y_n < \frac{2}{c} x_n \quad \forall n > N \tag{5}
\end{gather}
$$
Because $\sum_{n=1}^\infty \frac{2}{c} x_n = \frac{2}{c} \sum_{n=1}^\infty x_n = \frac{2}{c} X < \infty$, the Standard Comparison Test applied to step 5 implies that $\sum_{n=1}^\infty y_n$ converges.

Thus, $\sum_{n=1}^\infty x_n$ converges if and only if $\sum_{n=1}^\infty y_n$ converges.

**Simultaneous Divergence:**
Because both series consist of non-negative terms, any divergence must manifest as unbounded growth of the sequence of partial sums toward positive infinity.

Suppose $\sum_{n=1}^\infty y_n$ diverges, so that $\sum_{n=1}^\infty y_n = +\infty$. Because $\frac{c}{2} > 0$, the scaled series also diverges: $\sum_{n=1}^\infty \frac{c}{2} y_n = +\infty$. Because $x_n > \frac{c}{2} y_n$ for all $n > N$ by step 3, the Standard Comparison Test dictates that $\sum_{n=1}^\infty x_n$ diverges.

Conversely, suppose $\sum_{n=1}^\infty x_n$ diverges, so that $\sum_{n=1}^\infty x_n = +\infty$. Rearranging the upper bound of step 3 produces:
$$
\begin{gather}
y_n > \frac{2}{3c} x_n \quad \forall n > N \tag{6}
\end{gather}
$$
Because $\frac{2}{3c} > 0$, the series $\sum_{n=1}^\infty \frac{2}{3c} x_n = +\infty$ diverges. By the Standard Comparison Test applied to step 6, $\sum_{n=1}^\infty y_n$ diverges.

Therefore, the series $\sum_{n=1}^\infty x_n$ and $\sum_{n=1}^\infty y_n$ either both converge simultaneously or both diverge simultaneously.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
