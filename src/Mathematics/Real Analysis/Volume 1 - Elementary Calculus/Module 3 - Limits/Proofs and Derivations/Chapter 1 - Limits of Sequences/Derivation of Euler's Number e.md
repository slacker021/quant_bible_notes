---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be the sequence of real numbers defined by: 
$$
\begin{gather}
x_n := \left(1 + \frac{1}{n}\right)^n \quad \forall n \in \mathbb{N} \tag{1}
\end{gather}
$$
To establish that the limit $\lim_{n \to \infty} x_n =: e$ exists as a finite real number, it suffices to prove that $\{x_n\}$ is strictly increasing and bounded above in $\mathbb{R}$, which guarantees convergence by the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]].

For $n = 1$, $x_1 = \left(1 + \frac{1}{1}\right)^1 = 2$. For any integer $n \ge 2$, applying the [[Proof of the Binomial Theorem|Binomial Theorem]] to expand step 1 yields: 
$$
\begin{gather}
x_n = \sum_{k=0}^n \binom{n}{k} \left(\frac{1}{n}\right)^k = 1 + n\left(\frac{1}{n}\right) + \sum_{k=2}^n \frac{n(n-1)\cdots(n-k+1)}{k! \, n^k} \tag{2}
\end{gather}
$$
Dividing each of the $k$ factors in the numerator of the $k$-th summand by $n$ transforms step 2 into: 
$$
\begin{gather}
x_n = 2 + \sum_{k=2}^n \frac{1}{k!} \left(1 - \frac{1}{n}\right) \left(1 - \frac{2}{n}\right) \cdots \left(1 - \frac{k-1}{n}\right) \tag{3}
\end{gather}
$$
Similarly, expanding the subsequent term $x_{n+1}$ gives: 
$$
\begin{gather}
x_{n+1} = 2 + \sum_{k=2}^{n+1} \frac{1}{k!} \left(1 - \frac{1}{n+1}\right) \left(1 - \frac{2}{n+1}\right) \cdots \left(1 - \frac{k-1}{n+1}\right) \tag{4}
\end{gather}
$$
Comparing step 3 and step 4 term by term reveals that for each index $k \in \{2, \dots, n\}$ and each $j \in \{1, \dots, k - 1\}$, the inequality $\frac{j}{n} > \frac{j}{n+1}$ implies: 
$$
\begin{gather}
0 < 1 - \frac{j}{n} < 1 - \frac{j}{n+1} \tag{5}
\end{gather}
$$
Consequently, each of the first $n$ summands of $x_n$ is strictly less than the corresponding summand of $x_{n+1}$. Furthermore, $x_{n+1}$ contains an additional strictly positive summand corresponding to $k = n + 1$. Because $x_1 = 2 < 2.25 = x_2$ holds for the base case, it follows that $x_n < x_{n+1}$ for all $n \in \mathbb{N}$, proving that $\{x_n\}$ is strictly increasing.

To establish that $\{x_n\}$ is bounded above, observe from step 3 that for all $n \ge 2$ and all $j \in \{1, \dots, k - 1\}$, each factor satisfies $0 < 1 - \frac{j}{n} < 1$. Replacing each such factor with $1$ yields the strict inequality: 
$$
\begin{gather}
x_n < 2 + \sum_{k=2}^n \frac{1}{k!} \tag{6}
\end{gather}
$$
For every integer $k \ge 2$, the factorial $k! = 1 \cdot 2 \cdot 3 \cdots k$ is the product of $k - 1$ factors each greater than or equal to $2$. Consequently, $k! \ge 2^{k-1}$, which implies $\frac{1}{k!} \le \frac{1}{2^{k-1}}$. Substituting this bound into step 6 gives: 
$$
\begin{gather}
x_n < 2 + \sum_{k=2}^n \frac{1}{2^{k-1}} \tag{7}
\end{gather}
$$
Evaluating the finite geometric series in step 7 produces: 
$$
\begin{gather}
\sum_{k=2}^n \frac{1}{2^{k-1}} = \frac{1}{2} + \frac{1}{4} + \dots + \frac{1}{2^{n-1}} = 1 - \frac{1}{2^{n-1}} < 1 \tag{8}
\end{gather}
$$
Combining step 7 and step 8 shows that for all $n \in \mathbb{N}$ (including $x_1 = 2$): 
$$
\begin{gather}
2 \le x_n < 2 + 1 = 3 \tag{9}
\end{gather}
$$
Because $\{x_n\}$ is strictly increasing and bounded above by $3$, the Weierstrass Theorem on Monotonic Sequences guarantees that $\{x_n\}$ converges to a finite real limit $e := \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n$ satisfying $2 < e \le 3$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
