---
dg-publish: true
---
Let $\sum_{n=0}^\infty c_n (z - z_0)^n$ be a formal power series with complex coefficients $c_n \in \mathbb{C}$ and center $z_0 \in \mathbb{C}$. Let $R \in [0, \infty]$ denote its radius of convergence as determined by the Cauchy-Hadamard formula:
$$
\begin{gather}
\frac{1}{R} = \limsup_{n \to \infty} \sqrt[n]{|c_n|} \tag{1}
\end{gather}
$$
Consider the formally differentiated series obtained by term-by-term differentiation:
$$
\begin{gather}
\sum_{n=1}^\infty n c_n (z - z_0)^{n-1} = \sum_{k=0}^\infty (k+1) c_{k+1} (z - z_0)^k \tag{2}
\end{gather}
$$
Let $R' \in [0, \infty]$ denote the radius of convergence of the series in step 2. By the Cauchy-Hadamard formula applied to the differentiated series, the reciprocal radius satisfies:
$$
\begin{gather}
\frac{1}{R'} = \limsup_{n \to \infty} \sqrt[n]{n |c_n|} \tag{3}
\end{gather}
$$

The invariance assertion $R' = R$ requires showing that the limit superior in step 3 coincides with the limit superior in step 1.

**Evaluation of the Root Factor Limit:**
Consider the sequence of positive real numbers $u_n := \sqrt[n]{n} = n^{1/n}$ for $n \geq 1$. 

For every $n \geq 2$, the binomial theorem applied to $(1 + \lambda_n)^n$ with $\lambda_n := \sqrt[n]{n} - 1 > 0$ yields:
$$
\begin{gather}
n = (1 + \lambda_n)^n = \sum_{j=0}^n \binom{n}{j} \lambda_n^j > \binom{n}{2} \lambda_n^2 = \frac{n(n-1)}{2} \lambda_n^2 \tag{4}
\end{gather}
$$
Dividing step 4 by $\frac{n(n-1)}{2} > 0$ provides a strict upper bound for $\lambda_n^2$:
$$
\begin{gather}
\lambda_n^2 < \frac{2}{n - 1} \implies 0 < \lambda_n < \sqrt{\frac{2}{n - 1}} \tag{5}
\end{gather}
$$
Taking the limit as $n \to \infty$ in step 5, the squeeze theorem yields $\lim_{n \to \infty} \lambda_n = 0$. Consequently:
$$
\begin{gather}
\lim_{n \to \infty} \sqrt[n]{n} = \lim_{n \to \infty} (1 + \lambda_n) = 1 \tag{6}
\end{gather}
$$

**Product Rule for the Limit Superior:**
Let $(a_n)_{n=1}^\infty$ be a sequence of non-negative real numbers, and let $(b_n)_{n=1}^\infty$ be a sequence of positive real numbers that converges to a strictly positive limit $B \in (0, \infty)$:
$$
\begin{gather}
\lim_{n \to \infty} b_n = B \tag{7}
\end{gather}
$$
To establish the identity $\limsup_{n \to \infty} (a_n b_n) = B \limsup_{n \to \infty} a_n$, let $S := \limsup_{n \to \infty} a_n$. 

1. Case $0 < S < \infty$: Let $\varepsilon \in (0, B)$ be arbitrary. By step 7, there exists an index $N_1 \in \mathbb{N}$ such that for all $n \geq N_1$:
$$
\begin{gather}
B - \varepsilon < b_n < B + \varepsilon \tag{8}
\end{gather}
$$
By definition of $S = \limsup_{n \to \infty} a_n$, there exists $N_2 \in \mathbb{N}$ such that for all $n \geq N_2$, $a_n < S + \varepsilon$. Thus, for all $n \geq \max\{N_1, N_2\}$:
$$
\begin{gather}
a_n b_n < (S + \varepsilon)(B + \varepsilon) \tag{9}
\end{gather}
$$
Taking the limit superior of the left side of step 9 yields:
$$
\begin{gather}
\limsup_{n \to \infty} (a_n b_n) \leq (S + \varepsilon)(B + \varepsilon) \tag{10}
\end{gather}
$$
Since $\varepsilon > 0$ is arbitrary, taking $\varepsilon \to 0$ gives $\limsup_{n \to \infty} (a_n b_n) \leq B S$.

Conversely, there exists a subsequence $(a_{n_k})_{k=1}^\infty$ such that $\lim_{k \to \infty} a_{n_k} = S$. Since $\lim_{k \to \infty} b_{n_k} = B$, the product of convergent subsequences satisfies:
$$
\begin{gather}
\lim_{k \to \infty} (a_{n_k} b_{n_k}) = \left(\lim_{k \to \infty} a_{n_k}\right)\left(\lim_{k \to \infty} b_{n_k}\right) = S B \tag{11}
\end{gather}
$$
Because the limit of any subsequence is bounded above by the limit superior of the full sequence, step 11 implies:
$$
\begin{gather}
\limsup_{n \to \infty} (a_n b_n) \geq \lim_{k \to \infty} (a_{n_k} b_{n_k}) = B S \tag{12}
\end{gather}
$$
Combining step 10 and step 12 yields the equality:
$$
\begin{gather}
\limsup_{n \to \infty} (a_n b_n) = B \limsup_{n \to \infty} a_n \tag{13}
\end{gather}
$$
2. Case $S = 0$: For any $\varepsilon > 0$, $a_n < \varepsilon$ for all sufficiently large $n$. Since $b_n < B + 1$, $a_n b_n < \varepsilon (B + 1)$, implying $\limsup_{n \to \infty} (a_n b_n) = 0 = B \cdot 0$.
3. Case $S = \infty$: For any $M > 0$, there exists a subsequence with $a_{n_k} > M$. Since $b_{n_k} > B/2$ for large $k$, $a_{n_k} b_{n_k} > M B / 2$, which implies $\limsup_{n \to \infty} (a_n b_n) = \infty = B \cdot \infty$.

**Application to Cauchy-Hadamard Reciprocal Radius:**
Decompose the $n$-th root in step 3 using the product of terms:
$$
\begin{gather}
\sqrt[n]{n |c_n|} = \sqrt[n]{n} \cdot \sqrt[n]{|c_n|} \tag{14}
\end{gather}
$$
Setting $b_n := \sqrt[n]{n}$ and $a_n := \sqrt[n]{|c_n|}$, step 6 demonstrates that $\lim_{n \to \infty} b_n = 1$. 

Applying the product rule of step 13 with $B = 1$ directly yields:
$$
\begin{gather}
\limsup_{n \to \infty} \sqrt[n]{n |c_n|} = \limsup_{n \to \infty} \left( \sqrt[n]{n} \cdot \sqrt[n]{|c_n|} \right) = 1 \cdot \limsup_{n \to \infty} \sqrt[n]{|c_n|} = \limsup_{n \to \infty} \sqrt[n]{|c_n|} \tag{15}
\end{gather}
$$
By step 1 and step 3, step 15 establishes that:
$$
\begin{gather}
\frac{1}{R'} = \frac{1}{R} \implies R' = R \tag{16}
\end{gather}
$$

**Higher-Order Derivative Invariance:**
By mathematical induction, let $m \in \mathbb{N}$ denote the order of differentiation. The $m$-th derivative series is given by:
$$
\begin{gather}
\sum_{n=m}^\infty n(n-1)\cdots(n-m+1) c_n (z - z_0)^{n-m} \tag{17}
\end{gather}
$$
The $n$-th root of the polynomial coefficient factor satisfies:
$$
\begin{gather}
\lim_{n \to \infty} \sqrt[n]{n(n-1)\cdots(n-m+1)} = \left(\lim_{n \to \infty} \sqrt[n]{n}\right)^m = 1^m = 1 \tag{18}
\end{gather}
$$
Hence, by identical reasoning, every formal derivative of arbitrary order $m \in \mathbb{N}$ preserves the original radius of convergence $R$.
$$
\textbf{Q.E.D}
$$