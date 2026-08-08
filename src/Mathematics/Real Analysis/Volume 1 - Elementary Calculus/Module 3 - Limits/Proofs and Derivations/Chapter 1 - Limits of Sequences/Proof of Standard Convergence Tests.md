---
dg-publish: true
---
Let $\sum_{n=1}^\infty a_n$ be an infinite series of real numbers, and let $\alpha := \limsup_{n \to \infty} \sqrt[n]{|a_n|}$ denote the limit superior of the sequence of $n$-th roots of the absolute terms.

**Case 1: Absolute Convergence ($\alpha < 1$)**
Assume $\alpha < 1$. Choose a real constant $q$ such that $\alpha < q < 1$. By the definition of the limit superior as the supremum of subsequential limits, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
\sqrt[n]{|a_n|} \le q \tag{1}
\end{gather}
$$
Raising both sides of step 1 to the $n$-th power preserves the inequality:
$$
\begin{gather}
|a_n| \le q^n \quad \forall n > N \tag{2}
\end{gather}
$$
Because $0 < q < 1$, the geometric series $\sum_{n=1}^\infty q^n$ converges. By the [[Proof of the Standard Comparison Test|Standard Comparison Test]], the upper bound in step 2 implies that the series of absolute values $\sum_{n=1}^\infty |a_n|$ converges. Therefore, the series $\sum_{n=1}^\infty a_n$ converges absolutely.

**Case 2: Divergence ($\alpha > 1$)**
Assume $\alpha > 1$. Because $\alpha = \limsup_{n \to \infty} \sqrt[n]{|a_n|} > 1$ is the largest partial limit of the sequence $\left\{\sqrt[n]{|a_n|}\right\}$, there exists a subsequence $\{a_{n_k}\}$ such that
$$
\begin{gather}
\lim_{k \to \infty} \sqrt[n_k]{|a_{n_k}|} = \alpha > 1 \tag{3}
\end{gather}
$$
Consequently, there exists an integer $K \in \mathbb{N}$ such that for all $k > K$:
$$
\begin{gather}
\sqrt[n_k]{|a_{n_k}|} > 1 \implies |a_{n_k}| > 1 \tag{4}
\end{gather}
$$
Because the terms $|a_{n_k}|$ remain bounded away from zero for infinitely many indices $n_k$, the sequence of terms cannot converge to zero as $n \to \infty$:
$$
\begin{gather}
\lim_{n \to \infty} a_n \neq 0 \tag{5}
\end{gather}
$$
By the [[Proof of the Cauchy Convergence Criterion for a Series|Necessary Condition for Series Convergence]], step 5 guarantees that the series $\sum_{n=1}^\infty a_n$ diverges.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
