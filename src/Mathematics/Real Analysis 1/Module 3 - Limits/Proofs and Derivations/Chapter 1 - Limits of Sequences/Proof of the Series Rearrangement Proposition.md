---
dg-publish: true
---
# Proposition 1
Let $\sum_{n=1}^\infty x_n$ be an absolutely convergent series of real numbers with sum $S \in \mathbb{R}$, so that $\sum_{n=1}^\infty |x_n| < \infty$, and let $\sigma: \mathbb{N} \to \mathbb{N}$ be an arbitrary bijection representing a rearrangement of the series indices.

First, consider the case where all terms are non-negative ($x_n \ge 0$ for all $n \in \mathbb{N}$). For each $m \in \mathbb{N}$, define the $m$-th partial sum of the rearranged series:
$$
\begin{gather}
T_m := \sum_{k=1}^m x_{\sigma(k)} \tag{1}
\end{gather}
$$
Define the index $N_m := \max\{\sigma(1), \sigma(2), \dots, \sigma(m)\} \in \mathbb{N}$. Because every term $x_n$ is non-negative, the partial sum $T_m$ is bounded above by the $N_m$-th partial sum of the original series:
$$
\begin{gather}
T_m = \sum_{k=1}^m x_{\sigma(k)} \le \sum_{n=1}^{N_m} x_n \le \sum_{n=1}^\infty x_n = S \tag{2}
\end{gather}
$$
Step 2 establishes that the sequence of partial sums $\{T_m\}$ is monotonically nondecreasing and bounded above by $S$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], the rearranged series converges to a sum $S' \le S$. Reversing the roles of the two series by viewing the original series as a rearrangement of the rearranged series via the inverse bijection $\sigma^{-1}: \mathbb{N} \to \mathbb{N}$ yields $S \le S'$. Consequently, $S' = S$.

Now consider an arbitrary absolutely convergent series $\sum_{n=1}^\infty x_n$. Define the positive and negative components of each term:
$$
\begin{gather}
x_n^+ := \max(x_n, 0) = \frac{|x_n| + x_n}{2} \quad \text{and} \quad x_n^- := \max(-x_n, 0) = \frac{|x_n| - x_n}{2} \tag{3}
\end{gather}
$$
Because $0 \le x_n^+ \le |x_n|$ and $0 \le x_n^- \le |x_n|$, both series $\sum_{n=1}^\infty x_n^+$ and $\sum_{n=1}^\infty x_n^-$ converge by the [[Proof of the Standard Comparison Test|Standard Comparison Test]]. Applying the non-negative rearrangement result to each series independently yields:
$$
\begin{gather}
\sum_{k=1}^\infty x_{\sigma(k)}^+ = \sum_{n=1}^\infty x_n^+ \quad \text{and} \quad \sum_{k=1}^\infty x_{\sigma(k)}^- = \sum_{n=1}^\infty x_n^- \tag{4}
\end{gather}
$$
By the [[Proof of Arithmetic Properties of Series|difference rule for convergent series]], step 4 establishes that: 
$$
\begin{gather}
\sum_{k=1}^\infty x_{\sigma(k)} = \sum_{k=1}^\infty (x_{\sigma(k)}^+ - x_{\sigma(k)}^-) = \sum_{k=1}^\infty x_{\sigma(k)}^+ - \sum_{k=1}^\infty x_{\sigma(k)}^- = \sum_{n=1}^\infty x_n^+ - \sum_{n=1}^\infty x_n^- = S \tag{5}
\end{gather}
$$
Thus, every rearrangement of an absolutely convergent series converges to the identical sum $S$.

---
# Proposition 2
Let $\sum_{n=1}^\infty x_n$ be a conditionally convergent series of real numbers, meaning that $\sum_{n=1}^\infty x_n$ converges to a finite sum, but $\sum_{n=1}^\infty |x_n| = \infty$. Let $M \in \mathbb{R}$ be an arbitrary real number.

Define the sub-series of strictly positive terms $\{p_k\}_{k=1}^\infty$ and negative terms $\{-q_k\}_{k=1}^\infty$ (with $q_k > 0$), taken in their original relative order. If both $\sum p_k$ and $\sum q_k$ were finite, then $\sum |x_n| = \sum p_k + \sum q_k$ would converge, contradicting conditional convergence. If one sum were finite and the other infinite, $\sum x_n = \sum p_k - \sum q_k$ would diverge to $\pm\infty$, contradicting the convergence of $\sum x_n$. Therefore, both sub-series must diverge:
$$
\begin{gather}
\sum_{k=1}^\infty p_k = +\infty \quad \text{and} \quad \sum_{k=1}^\infty q_k = +\infty \tag{6}
\end{gather}
$$
Concurrently, the convergence of $\sum_{n=1}^\infty x_n$ requires by the [[Proof of the Cauchy Convergence Criterion for a Series|Necessary Condition for Series Convergence]] that: 
$$
\begin{gather}
\lim_{k \to \infty} p_k = 0 \quad \text{and} \quad \lim_{k \to \infty} q_k = 0 \tag{7}
\end{gather}
$$
Construct a rearranged series inductively as follows. Sum the positive terms $p_1 + p_2 + \dots + p_{k_1}$ until the partial sum strictly exceeds $M$, which is guaranteed to occur by step 6 since $\sum p_k = +\infty$:
$$
\begin{gather}
\sum_{i=1}^{k_1 - 1} p_i \le M < \sum_{i=1}^{k_1} p_i \tag{8}
\end{gather}
$$
Next, subtract the negative terms $q_1 + q_2 + \dots + q_{m_1}$ until the new partial sum falls strictly below $M$, which is guaranteed to occur since $\sum q_k = +\infty$:
$$
\begin{gather}
\sum_{i=1}^{k_1} p_i - \sum_{j=1}^{m_1 - 1} q_j \ge M > \sum_{i=1}^{k_1} p_i - \sum_{j=1}^{m_1} q_j \tag{9}
\end{gather}
$$
Repeat this alternating procedure indefinitely, choosing the minimal number of positive terms required to exceed $M$, followed by the minimal number of negative terms required to fall below $M$.

At each step, the partial sum of the rearranged series differs from $M$ by at most the last added term:
$$
\begin{gather}
|S_{\text{rearranged}, n} - M| \le \max(p_k, q_m) \tag{10}
\end{gather}
$$
Because $\lim_{k \to \infty} p_k = 0$ and $\lim_{m \to \infty} q_m = 0$ by step 7, passing to the limit as $n \to \infty$ in step 10 proves that the rearranged series converges to $M$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
