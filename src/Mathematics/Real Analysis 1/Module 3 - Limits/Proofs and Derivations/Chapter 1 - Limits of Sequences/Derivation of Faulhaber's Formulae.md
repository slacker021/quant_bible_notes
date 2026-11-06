---
dg-publish: true
---
Let $k \in \mathbb{N} \cup \{0\}$ be a non-negative integer, and let $S_{k}(n) := \sum_{i = 1}^n i^k$ denote the sum of the $k$-th powers of the first $n$ positive integers.

By the [[Proof of the Binomial Theorem|Binomial Theorem]], the expression $(x + 1)^{k+1}$ expands for any $x \in \mathbb{R}$ as:
$$
\begin{gather}
(x + 1)^{k+1} = \sum_{j=0}^{k+1} \binom{k+1}{j} x^j = x^{k+1} + \sum_{j=0}^{k} \binom{k+1}{j} x^j \tag{1}
\end{gather}
$$
Subtracting $x^{k+1}$ from both sides of step 1 yields the algebraic identity: 
$$
\begin{gather}
(x + 1)^{k+1} - x^{k+1} = \sum_{j=0}^{k} \binom{k+1}{j} x^j \tag{2}
\end{gather}
$$
Summing both sides of step 2 over the integer index $x$ from $1$ to $n$ gives: 
$$
\begin{gather}
\sum_{x=1}^n \left((x + 1)^{k+1} - x^{k+1}\right) = \sum_{x=1}^n \left( \sum_{j=0}^k \binom{k+1}{j} x^j \right) \tag{3}
\end{gather}
$$
The left-hand side of step 3 is a finite telescoping sum in which all intermediate terms cancel pairwise:
$$
\begin{gather}
(2^{k+1} - 1^{k+1}) + (3^{k+1} - 2^{k+1}) + \dots + \left((n + 1)^{k+1} - n^{k+1}\right) = (n + 1)^{k+1} - 1 \tag{4}
\end{gather}
$$
Interchanging the order of the two finite summations on the right-hand side of step 3 yields:
$$
\begin{gather}
\sum_{j = 0}^k \binom{k+1}{j} \left( \sum_{x=1}^n x^j \right) = \sum_{j = 0}^k \binom{k+1}{j} S_{j}(n) \tag{5}
\end{gather}
$$
Equating step 4 and step 5 produces Pascal's identity for power sums:
$$
\begin{gather}
(n + 1)^{k+1} - 1 = \sum_{j = 0}^k \binom{k+1}{j} S_{j}(n) \tag{6}
\end{gather}
$$
Isolating the term corresponding to $j = k$ and observing that $\binom{k+1}{k} = k + 1$ transforms step 6 into: 
$$
\begin{gather}
(n + 1)^{k+1} - 1 = (k + 1) S_{k}(n) + \sum_{j = 0}^{k-1} \binom{k+1}{j} S_{j}(n) \tag{7}
\end{gather}
$$
Dividing both sides of step 7 by $k + 1$ expresses $S_k(n)$ recursively in terms of lower-order power sums:
$$
\begin{gather}
S_{k}(n) = \frac{1}{k + 1} \left[ (n + 1)^{k+1} - 1 - \sum_{j = 0}^{k-1} \binom{k+1}{j} S_{j}(n) \right] \tag{8}
\end{gather}
$$
To establish that $S_k(n)$ is a univariate polynomial in $n$ of degree $k + 1$ with leading coefficient $a_{k+1} = \frac{1}{k + 1}$ and vanishing constant term $S_k(0) = 0$, proceed by strong mathematical induction on $k \in \mathbb{N} \cup \{0\}$:

For the base step $k = 0$, direct summation yields: 
$$
\begin{gather}
S_0(n) = \sum_{i=1}^n i^0 = \sum_{i=1}^n 1 = n \tag{9}
\end{gather}
$$
which is a polynomial in $n$ of degree $0 + 1 = 1$ with leading coefficient $\frac{1}{0 + 1} = 1$ and zero constant term, verifying the base step.

Assume as the strong inductive hypothesis that for every integer $j \in \{0, 1, \dots, k - 1\}$, the sum $S_j(n)$ is a polynomial in $n$ of degree $j + 1$ with zero constant term. Under this hypothesis, the finite linear combination: 
$$
\begin{gather}
P(n) := \sum_{j=0}^{k-1} \binom{k+1}{j} S_j(n) \tag{10}
\end{gather}
$$
is a polynomial in $n$ of degree at most $(k - 1) + 1 = k$ satisfying $P(0) = 0$. Meanwhile, expanding $(n + 1)^{k+1} - 1$ via the Binomial Theorem yields: 
$$
\begin{gather}
(n + 1)^{k+1} - 1 = n^{k+1} + (k + 1)n^k + \sum_{r=1}^{k-1} \binom{k+1}{r} n^r \tag{11}
\end{gather}
$$
which is a polynomial in $n$ of degree $k + 1$ with leading term $n^{k+1}$ and zero constant term. Subtracting $P(n)$ from $(n + 1)^{k+1} - 1$ in step 8 alters only terms of degree at most $k$, leaving the leading term $n^{k+1}$ unchanged and preserving the property that the constant term vanishes. Dividing by $k + 1$ demonstrates that $S_k(n)$ is a polynomial in $n$ of degree $k + 1$ with leading coefficient: 
$$
\begin{gather}
a_{k+1} = \frac{1}{k + 1} \tag{12}
\end{gather}
$$
By the [[Proof that Induction Works|Principle of Mathematical Induction]], the claim holds for all $k \in \mathbb{N} \cup \{0\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
