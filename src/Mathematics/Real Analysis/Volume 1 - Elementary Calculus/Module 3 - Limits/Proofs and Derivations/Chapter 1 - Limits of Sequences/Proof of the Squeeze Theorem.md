---
dg-publish: true
---
Let $\{a_n\}$, $\{b_n\}$, and $\{x_n\}$ be sequences of real numbers satisfying the inequality:
$$
\begin{gather}
a_n \le x_n \le b_n \quad \forall n > N_0 \tag{1}
\end{gather}
$$
for some index $N_0 \in \mathbb{N}$, and assume that $\{a_n\}$ and $\{b_n\}$ both converge to the identical real limit:
$$
\begin{gather}
\lim_{n \to \infty} a_n = \lim_{n \to \infty} b_n = x \in \mathbb{R} \tag{2}
\end{gather}
$$
Let $\varepsilon > 0$ be arbitrary. Because $\lim_{n \to \infty} a_n = x$, there exists an index $N_1 \in \mathbb{N}$ such that for all $n > N_1$:
$$
\begin{gather}
|a_n - x| < \varepsilon \iff x - \varepsilon < a_n < x + \varepsilon \tag{3}
\end{gather}
$$
Similarly, because $\lim_{n \to \infty} b_n = x$, there exists an index $N_2 \in \mathbb{N}$ such that for all $n > N_2$:
$$
\begin{gather}
|b_n - x| < \varepsilon \iff x - \varepsilon < b_n < x + \varepsilon \tag{4}
\end{gather}
$$
Define the threshold index $N := \max(N_0, N_1, N_2) \in \mathbb{N}$. For every index $n > N$, combining step 1, step 3, and step 4 yields the chain of inequalities:
$$
\begin{gather}
x - \varepsilon < a_n \le x_n \le b_n < x + \varepsilon \tag{5}
\end{gather}
$$
Extracting the outer bounds from step 5 demonstrates that for all $n > N$:
$$
\begin{gather}
x - \varepsilon < x_n < x + \varepsilon \iff |x_n - x| < \varepsilon \tag{6}
\end{gather}
$$
Because $\varepsilon > 0$ was chosen arbitrarily, step 6 proves that the sequence $\{x_n\}$ converges to $x$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
