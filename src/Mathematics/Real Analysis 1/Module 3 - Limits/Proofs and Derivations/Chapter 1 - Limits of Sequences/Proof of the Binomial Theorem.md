---
dg-publish: true
---
# Lemma 
For any non-negative integers $n, k \in \mathbb{N} \cup \{0\}$ with $0 \le k \le n$, the binomial coefficient is defined by
$$
\begin{gather}
\binom{n}{k} := \frac{n!}{k!(n - k)!}, \quad \text{where } 0! := 1 \text{ and } m! := \prod_{i=1}^m i \text{ for } m \in \mathbb{N} \tag{1}
\end{gather}
$$
For any $n, k \in \mathbb{N}$ satisfying $1 \le k \le n$, expanding the sum $\binom{n}{k} + \binom{n}{k-1}$ via step 1 yields
$$
\begin{gather}
\binom{n}{k} + \binom{n}{k-1} = \frac{n!}{k!(n-k)!} + \frac{n!}{(k-1)!(n-k+1)!} \tag{2}
\end{gather}
$$
Using the factorial identities $k! = k(k - 1)!$ and $(n - k + 1)! = (n - k + 1)(n - k)!$, both fractions in step 2 can be expressed over the common denominator $k!(n - k + 1)!$:
$$
\begin{gather}
\frac{n!(n-k+1)}{k!(n-k+1)!} + \frac{n! \cdot k}{k!(n-k+1)!} = \frac{n!(n - k + 1 + k)}{k!(n - k + 1)!} \tag{3}
\end{gather}
$$
Simplifying the numerator via $n!(n + 1) = (n + 1)!$ produces Pascal's Rule:
$$
\begin{gather}
\binom{n}{k} + \binom{n}{k-1} = \frac{(n+1)!}{k!((n + 1) - k)!} = \binom{n+1}{k} \tag{4}
\end{gather}
$$

---
# Theorem 
Let $x, y \in \mathbb{R}$ be arbitrary real numbers. The algebraic identity
$$
\begin{gather}
(x + y)^n = \sum_{k=0}^n \binom{n}{k} x^{n-k} y^k \tag{5}
\end{gather}
$$
is established for all $n \in \mathbb{N} \cup \{0\}$ by mathematical induction.

**Base Step:**
For $n = 0$, $(x + y)^0 = 1$ and $\binom{0}{0} x^0 y^0 = 1 \cdot 1 \cdot 1 = 1$, so step 5 holds. For $n = 1$, the left-hand side evaluates to $(x + y)^1 = x + y$, while the right-hand side yields
$$
\begin{gather}
\sum_{k=0}^1 \binom{1}{k} x^{1-k} y^k = \binom{1}{0} x^1 y^0 + \binom{1}{1} x^0 y^1 = x + y \tag{6}
\end{gather}
$$
Thus, the base cases are verified.

**Inductive Step:**
Assume as the inductive hypothesis that step 5 holds for a fixed natural number $n = m \in \mathbb{N}$:
$$
\begin{gather}
(x + y)^m = \sum_{k=0}^m \binom{m}{k} x^{m-k} y^k \tag{7}
\end{gather}
$$
To evaluate $(x + y)^{m+1}$, factor out $(x + y)$ and substitute the inductive hypothesis of step 7:
$$
\begin{gather}
(x + y)^{m+1} = (x + y)(x + y)^m = (x + y) \sum_{k=0}^m \binom{m}{k} x^{m-k} y^k \tag{8}
\end{gather}
$$
Distributing $x$ and $y$ across the summation in step 8 gives
$$
\begin{gather}
(x + y)^{m+1} = \sum_{k=0}^m \binom{m}{k} x^{m-k+1} y^k + \sum_{k=0}^m \binom{m}{k} x^{m-k} y^{k+1} \tag{9}
\end{gather}
$$
Re-indexing the second summation in step 9 by setting $j := k + 1$ (so that $k = j - 1$, with $j$ ranging from $1$ to $m + 1$) yields
$$
\begin{gather}
\sum_{k=0}^m \binom{m}{k} x^{m-k} y^{k+1} = \sum_{j=1}^{m+1} \binom{m}{j-1} x^{m-j+1} y^j \tag{10}
\end{gather}
$$
Relabeling the dummy index $j$ back to $k$ in step 10 and substituting into step 9 produces
$$
\begin{gather}
(x + y)^{m+1} = \sum_{k=0}^m \binom{m}{k} x^{m-k+1} y^k + \sum_{k=1}^{m+1} \binom{m}{k-1} x^{m-k+1} y^k \tag{11}
\end{gather}
$$
Isolating the $k = 0$ term from the first summation and the $k = m + 1$ term from the second summation permits combining the overlapping sums for $1 \le k \le m$:
$$
\begin{gather}
(x + y)^{m+1} = \binom{m}{0} x^{m+1} y^0 + \sum_{k=1}^m \left[ \binom{m}{k} + \binom{m}{k-1} \right] x^{m-k+1} y^k + \binom{m}{m} x^0 y^{m+1} \tag{12}
\end{gather}
$$
Applying Lemma 1 to the bracketed sum in step 12 and using $\binom{m}{0} = 1 = \binom{m+1}{0}$ and $\binom{m}{m} = 1 = \binom{m+1}{m+1}$ transforms step 12 into
$$
\begin{gather}
(x + y)^{m+1} = \binom{m+1}{0} x^{m+1} y^0 + \sum_{k=1}^m \binom{m+1}{k} x^{(m+1)-k} y^k + \binom{m+1}{m+1} x^0 y^{m+1} \tag{13}
\end{gather}
$$
Absorbing the boundary terms into the summation in step 13 yields
$$
\begin{gather}
(x + y)^{m+1} = \sum_{k=0}^{m+1} \binom{m+1}{k} x^{(m+1)-k} y^k \tag{14}
\end{gather}
$$
By the [[Proof that Induction Works|Principle of Mathematical Induction]], the Binomial Theorem holds for all $n \in \mathbb{N} \cup \{0\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
