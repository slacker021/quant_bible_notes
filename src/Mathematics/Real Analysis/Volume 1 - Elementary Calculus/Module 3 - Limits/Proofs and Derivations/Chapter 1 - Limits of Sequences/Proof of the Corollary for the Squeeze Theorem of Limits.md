---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be a sequence of real numbers.

**Forward Direction ($\implies$):**
Assume that $\lim_{n \to \infty} |x_n| = 0$. By definition of the absolute value on $\mathbb{R}$, every term $x_n$ satisfies the double inequality: 
$$
\begin{gather}
-|x_n| \le x_n \le |x_n| \quad \forall n \in \mathbb{N} \tag{1}
\end{gather}
$$
By the [[Proof of Arithmetic Operations Involving Limits|scalar multiple rule for limits]], the limit of the lower bound evaluates to: 
$$
\begin{gather}
\lim_{n \to \infty} (-|x_n|) = -1 \cdot \lim_{n \to \infty} |x_n| = -1 \cdot 0 = 0 \tag{2}
\end{gather}
$$
Because both the lower bounding sequence $\{-|x_n|\}$ and the upper bounding sequence $\{|x_n|\}$ converge to $0$, the [[Proof of Inequalities Involving Limits|Squeeze Theorem]] applied to step 1 establishes that:
$$
\begin{gather}
\lim_{n \to \infty} x_n = 0 \tag{3}
\end{gather}
$$

**Reverse Direction ($\impliedby$):**
Conversely, assume that $\lim_{n \to \infty} x_n = 0$. Let $\varepsilon > 0$ be arbitrary.

By definition of sequence convergence, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
|x_n - 0| < \varepsilon \iff |x_n| < \varepsilon \tag{4}
\end{gather}
$$
Evaluating the distance between $|x_n|$ and $0$ yields: 
$$
\begin{gather}
||x_n| - 0| = ||x_n|| = |x_n| \tag{5}
\end{gather}
$$
Combining step 4 and step 5 demonstrates that for all $n > N$:
$$
\begin{gather}
||x_n| - 0| < \varepsilon \tag{6}
\end{gather}
$$
Because $\varepsilon > 0$ was arbitrary, step 6 proves that $\lim_{n \to \infty} |x_n| = 0$.

Combining both directions establishes the logical equivalence:
$$
\begin{gather}
\lim_{n \to \infty} |x_n| = 0 \iff \lim_{n \to \infty} x_n = 0 \tag{7}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
