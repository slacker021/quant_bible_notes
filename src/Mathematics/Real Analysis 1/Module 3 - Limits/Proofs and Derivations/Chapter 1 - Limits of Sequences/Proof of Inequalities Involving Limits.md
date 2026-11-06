---
dg-publish: true
---
Let $\{x_n\}$, $\{y_n\}$, and $\{z_n\}$ be sequences of real numbers.

---
# Theorem 1
Suppose that $\lim_{n \to \infty} x_n = A$ and $\lim_{n \to \infty} y_n = B$, where $A < B$. Because $B - A > 0$, define the positive tolerance:
$$
\begin{gather}
\varepsilon := \frac{B - A}{2} > 0 \tag{1}
\end{gather}
$$
By the definition of sequence convergence applied to $\lim_{n \to \infty} x_n = A$ and $\lim_{n \to \infty} y_n = B$, there exist indices $N_1, N_2 \in \mathbb{N}$ such that:
$$
\begin{gather}
\forall n > N_1 \quad \left(|x_n - A| < \varepsilon \implies x_n < A + \frac{B - A}{2} = \frac{A + B}{2}\right) \tag{2}
\end{gather}
$$
and
$$
\begin{gather}
\forall n > N_2 \quad \left(|y_n - B| < \varepsilon \implies y_n > B - \frac{B - A}{2} = \frac{A + B}{2}\right) \tag{3}
\end{gather}
$$
Define the threshold index $N := \max(N_1, N_2) \in \mathbb{N}$. For every index $n > N$, combining step 2 and step 3 yields:
$$
\begin{gather}
x_n < \frac{A + B}{2} < y_n \implies x_n < y_n \tag{4}
\end{gather}
$$
Thus, $x_n < y_n$ holds for all $n > N$.

---
# Theorem 2
Suppose there exists an index $N_0 \in \mathbb{N}$ such that:
$$
\begin{gather}
x_n \le y_n \le z_n \quad \forall n > N_0 \tag{5}
\end{gather}
$$
and assume that $\{x_n\}$ and $\{z_n\}$ both converge to the identical real limit:
$$
\begin{gather}
\lim_{n \to \infty} x_n = \lim_{n \to \infty} z_n = A \in \mathbb{R} \tag{6}
\end{gather}
$$
Let $\varepsilon > 0$ be arbitrary. Because $\lim_{n \to \infty} x_n = A$, there exists an index $N_1 \in \mathbb{N}$ such that for all $n > N_1$:
$$
\begin{gather}
|x_n - A| < \varepsilon \iff A - \varepsilon < x_n < A + \varepsilon \tag{7}
\end{gather}
$$
Similarly, because $\lim_{n \to \infty} z_n = A$, there exists an index $N_2 \in \mathbb{N}$ such that for all $n > N_2$:
$$
\begin{gather}
|z_n - A| < \varepsilon \iff A - \varepsilon < z_n < A + \varepsilon \tag{8}
\end{gather}
$$
Define the threshold index $N := \max(N_0, N_1, N_2) \in \mathbb{N}$. For every index $n > N$, combining step 5, step 7, and step 8 yields the chain of inequalities:
$$
\begin{gather}
A - \varepsilon < x_n \le y_n \le z_n < A + \varepsilon \tag{9}
\end{gather}
$$
Extracting the outer bounds from step 9 demonstrates that for all $n > N$:
$$
\begin{gather}
A - \varepsilon < y_n < A + \varepsilon \iff |y_n - A| < \varepsilon \tag{10}
\end{gather}
$$
Because $\varepsilon > 0$ was chosen arbitrarily, step 10 proves that the intermediate sequence $\{y_n\}$ converges to $A$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
