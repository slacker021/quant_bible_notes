---
dg-publish: true
---
Let $\{y_n\}_{n=1}^\infty$ be a sequence of non-negative real numbers that is monotonically nonincreasing ($y_n \ge y_{n+1} \ge 0$ for all $n \in \mathbb{N}$) and satisfies $\lim_{n \to \infty} y_n = 0$. Consider the alternating series $\sum_{n=1}^\infty (-1)^{n+1} y_n$, and let $s_n := \sum_{k=1}^n (-1)^{k+1} y_k$ denote its $n$-th partial sum.

For any index $m \in \mathbb{N}$, the even-indexed partial sum $s_{2m}$ can be grouped as: 
$$
\begin{gather}
s_{2m} = (y_1 - y_2) + (y_3 - y_4) + \dots + (y_{2m-1} - y_{2m}) = \sum_{k=1}^m (y_{2k-1} - y_{2k}) \tag{1}
\end{gather}
$$
Because $\{y_n\}$ is nonincreasing, each difference satisfies $y_{2k-1} - y_{2k} \ge 0$. Consequently, the sequence of even partial sums is monotonically nondecreasing:
$$
\begin{gather}
s_{2m+2} - s_{2m} = y_{2m+1} - y_{2m+2} \ge 0 \implies s_{2m} \le s_{2m+2} \tag{2}
\end{gather}
$$
Concurrently, the odd-indexed partial sum $s_{2m+1}$ can be rewritten as: 
$$
\begin{gather}
s_{2m+1} = y_1 - (y_2 - y_3) - (y_4 - y_5) - \dots - (y_{2m} - y_{2m+1}) = y_1 - \sum_{k=1}^m (y_{2k} - y_{2k+1}) \tag{3}
\end{gather}
$$
Because $y_{2k} - y_{2k+1} \ge 0$, subtracting additional non-negative terms ensures that the sequence of odd partial sums is monotonically nonincreasing:
$$
\begin{gather}
s_{2m+1} - s_{2m-1} = -(y_{2m} - y_{2m+1}) \le 0 \implies s_{2m+1} \le s_{2m-1} \tag{4}
\end{gather}
$$
Furthermore, because $y_{2m+1} \ge 0$, the relationship between consecutive partial sums satisfies: 
$$
\begin{gather}
s_{2m+1} = s_{2m} + y_{2m+1} \ge s_{2m} \tag{5}
\end{gather}
$$
Combining step 2, step 4, and step 5 yields the nested inequality chain valid for all $m \in \mathbb{N}$:
$$
\begin{gather}
s_2 \le s_4 \le \dots \le s_{2m} \le s_{2m+1} \le \dots \le s_5 \le s_3 \le s_1 \tag{6}
\end{gather}
$$
Step 6 establishes that the nondecreasing sequence $\{s_{2m}\}$ is bounded above by $s_1$, and the nonincreasing sequence $\{s_{2m+1}\}$ is bounded below by $s_2$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], both subsequences converge to finite real limits:
$$
\begin{gather}
\lim_{m \to \infty} s_{2m} = L_e \quad \text{and} \quad \lim_{m \to \infty} s_{2m+1} = L_o \tag{7}
\end{gather}
$$
Evaluating the difference between these limits via step 5 and using the hypothesis $\lim_{n \to \infty} y_n = 0$:
$$
\begin{gather}
L_o - L_e = \lim_{m \to \infty} (s_{2m+1} - s_{2m}) = \lim_{m \to \infty} y_{2m+1} = 0 \implies L_o = L_e =: s \tag{8}
\end{gather}
$$
Because the even-indexed and odd-indexed subsequences converge to the identical real limit $s$, the [[Proof of Theorem Involving Odd and Even-Indexed Sequences|parity decomposition theorem]] guarantees that the entire sequence of partial sums converges:
$$
\begin{gather}
\lim_{n \to \infty} s_n = s = \sum_{n=1}^\infty (-1)^{n+1} y_n \tag{9}
\end{gather}
$$
Finally, by virtue of the monotonic nesting in step 6, the limit $s$ lies between any two consecutive partial sums:
$$
\begin{gather}
s_{2m} \le s \le s_{2m+1} \quad \text{and} \quad s_{2m+2} \le s \le s_{2m+1} \tag{10}
\end{gather}
$$
For an even index $n = 2m$, step 10 implies $0 \le s - s_{2m} \le s_{2m+1} - s_{2m} = y_{2m+1}$. For an odd index $n = 2m - 1$, step 10 implies $0 \le s_{2m-1} - s \le s_{2m-1} - s_{2m} = y_{2m}$. In both cases, the remainder $r_n := s - s_n$ satisfies the truncation bound: 
$$
\begin{gather}
|s - s_n| \le y_{n+1} \quad \forall n \in \mathbb{N} \tag{11}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
