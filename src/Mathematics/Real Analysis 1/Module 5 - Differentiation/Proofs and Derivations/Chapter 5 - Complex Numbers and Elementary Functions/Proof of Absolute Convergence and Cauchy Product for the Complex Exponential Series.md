---
dg-publish: true
---
Let the complex exponential mapping $\exp : \mathbb{C} \to \mathbb{C}$ be defined formally by the power series:
$$
\begin{gather}
\exp(z) := \sum_{n=0}^\infty \frac{z^n}{n!} \tag{1}
\end{gather}
$$
where $z^0 := 1$ and $0! := 1$. For any two infinite series of complex numbers $\sum_{n=0}^\infty a_n$ and $\sum_{n=0}^\infty b_n$, their Cauchy product is defined as the series $\sum_{n=0}^\infty c_n$, where:
$$
\begin{gather}
c_n := \sum_{k=0}^n a_k b_{n-k} \tag{2}
\end{gather}
$$

---
# Proposition 1
The power series $\sum_{n=0}^\infty \frac{z^n}{n!}$ converges absolutely for every $z \in \mathbb{C}$, and therefore converges in $(\mathbb{C}, d)$ for all $z \in \mathbb{C}$.

Let $z \in \mathbb{C}$ be arbitrary. If $z = 0$, the series reduces to the single term $\frac{0^0}{0!} = 1$, which converges trivially.

Suppose $z \neq 0$. Consider the series of absolute values $\sum_{n=0}^\infty u_n$, where $u_n := \left|\frac{z^n}{n!}\right| = \frac{|z|^n}{n!}$. For every $n \ge 0$, $u_n > 0$. Consider the ratio of consecutive terms:
$$
\begin{gather}
\frac{u_{n+1}}{u_n} = \frac{\frac{|z|^{n+1}}{(n+1)!}}{\frac{|z|^n}{n!}} = \frac{|z|^{n+1}}{|z|^n} \cdot \frac{n!}{(n+1)!} = \frac{|z|}{n+1} \tag{3}
\end{gather}
$$
Taking the limit as $n \to \infty$ of step 3, since $|z|$ is a fixed non-negative real constant:
$$
\begin{gather}
L := \lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \lim_{n \to \infty} \frac{|z|}{n+1} = 0 \tag{4}
\end{gather}
$$
Because $L = 0 < 1$, by the real d'Alembert ratio test, the real series of non-negative terms $\sum_{n=0}^\infty \frac{|z|^n}{n!}$ converges to a finite real sum:
$$
\begin{gather}
\sum_{n=0}^\infty \frac{|z|^n}{n!} = e^{|z|} < \infty \tag{5}
\end{gather}
$$
Thus, the series $\sum_{n=0}^\infty \frac{z^n}{n!}$ converges absolutely for every $z \in \mathbb{C}$.

Let $S_N := \sum_{n=0}^N \frac{z^n}{n!}$ denote the $N$-th partial sum in $\mathbb{C}$. For any integers $M > N$:
$$
\begin{gather}
|S_M - S_N| = \left| \sum_{n=N+1}^M \frac{z^n}{n!} \right| \le \sum_{n=N+1}^M \left|\frac{z^n}{n!}\right| = \sum_{n=N+1}^M \frac{|z|^n}{n!} \tag{6}
\end{gather}
$$
Because the real series $\sum_{n=0}^\infty \frac{|z|^n}{n!}$ converges, its sequence of partial sums is a Cauchy sequence in $\mathbb{R}$. Therefore, for every $\varepsilon > 0$, there exists $N_0 \in \mathbb{N}$ such that for all $M > N \ge N_0$, the tail sum $\sum_{n=N+1}^M \frac{|z|^n}{n!} < \varepsilon$. By step 6, $|S_M - S_N| < \varepsilon$ for all $M > N \ge N_0$.

Thus, $(S_N)_{N=0}^\infty$ is a Cauchy sequence in $\mathbb{C}$. By [[Proof of Algebraic and Metric Completeness of C|the metric completeness of the complex plane]], $(S_N)_{N=0}^\infty$ converges to a unique limit in $\mathbb{C}$. Hence, absolute convergence implies convergence in $\mathbb{C}$.

---
# Proposition 2
Let $\sum_{n=0}^\infty a_n$ and $\sum_{n=0}^\infty b_n$ be two absolutely convergent series in $\mathbb{C}$ with limits $A$ and $B$, respectively. Then their Cauchy product $\sum_{n=0}^\infty c_n$ converges absolutely to the product $A B$. Consequently, for any $z, w \in \mathbb{C}$:
$$
\begin{gather}
\exp(z) \exp(w) = \exp(z + w) \tag{7}
\end{gather}
$$

Let $A_N := \sum_{n=0}^N a_n$, $B_N := \sum_{n=0}^N b_n$, and $C_N := \sum_{n=0}^N c_n$, where $c_n$ is defined by step 2. By hypothesis, the real series of absolute values converge:
$$
\begin{gather}
\sum_{n=0}^\infty |a_n| = \alpha < \infty \quad \text{and} \quad \sum_{n=0}^\infty |b_n| = \beta < \infty \tag{8}
\end{gather}
$$
Writing out the partial sum $C_N$:
$$
\begin{gather}
C_N = \sum_{n=0}^N \sum_{k=0}^n a_k b_{n-k} = \sum_{\substack{0 \le j, k \le N \\ j + k \le N}} a_j b_k \tag{9}
\end{gather}
$$
The product of the partial sums $A_N B_N$ is the sum over the square index domain:
$$
\begin{gather}
A_N B_N = \left( \sum_{j=0}^N a_j \right) \left( \sum_{k=0}^N b_k \right) = \sum_{0 \le j, k \le N} a_j b_k \tag{10}
\end{gather}
$$
Subtracting $C_N$ from $A_N B_N$ yields:
$$
\begin{gather}
A_N B_N - C_N = \sum_{\substack{0 \le j, k \le N \\ j + k > N}} a_j b_k \tag{11}
\end{gather}
$$
Applying the triangle inequality to step 11:
$$
\begin{gather}
|A_N B_N - C_N| \le \sum_{\substack{0 \le j, k \le N \\ j + k > N}} |a_j| |b_k| \tag{12}
\end{gather}
$$
Notice that the index condition $j + k > N$ with $0 \le j, k \le N$ implies that either $j > \lfloor N/2 \rfloor$ or $k > \lfloor N/2 \rfloor$. Therefore:
$$
\begin{gather}
\sum_{\substack{0 \le j, k \le N \\ j + k > N}} |a_j| |b_k| \le \sum_{j = \lfloor N/2 \rfloor + 1}^N |a_j| \left(\sum_{k=0}^N |b_k|\right) + \sum_{k = \lfloor N/2 \rfloor + 1}^N |b_k| \left(\sum_{j=0}^N |a_j|\right) \tag{13}
\end{gather}
$$
Because $\sum_{k=0}^N |b_k| \le \beta$ and $\sum_{j=0}^N |a_j| \le \alpha$ by step 8, step 13 implies:
$$
\begin{gather}
|A_N B_N - C_N| \le \beta \sum_{j = \lfloor N/2 \rfloor + 1}^\infty |a_j| + \alpha \sum_{k = \lfloor N/2 \rfloor + 1}^\infty |b_k| \tag{14}
\end{gather}
$$
Since $\sum_{n=0}^\infty |a_n|$ and $\sum_{n=0}^\infty |b_n|$ converge, the tails tend to zero as $N \to \infty$:
$$
\begin{gather}
\lim_{N \to \infty} \sum_{j = \lfloor N/2 \rfloor + 1}^\infty |a_j| = 0 \quad \text{and} \quad \lim_{N \to \infty} \sum_{k = \lfloor N/2 \rfloor + 1}^\infty |b_k| = 0 \tag{15}
\end{gather}
$$
Applying the squeeze theorem to step 14 shows:
$$
\begin{gather}
\lim_{N \to \infty} |A_N B_N - C_N| = 0 \implies \lim_{N \to \infty} C_N = \lim_{N \to \infty} A_N B_N = A B \tag{16}
\end{gather}
$$
By identical reasoning applied to $\sum |a_n|$ and $\sum |b_n|$, the Cauchy product of the absolute series $\sum_{n=0}^\infty \sum_{k=0}^n |a_k| |b_{n-k}|$ converges to $\alpha \beta < \infty$, establishing absolute convergence of $\sum c_n$.

Now let $z, w \in \mathbb{C}$ and set $a_k := \frac{z^k}{k!}$ and $b_m := \frac{w^m}{m!}$. By Proposition 1, $\sum_{k=0}^\infty a_k$ and $\sum_{m=0}^\infty b_m$ converge absolutely to $\exp(z)$ and $\exp(w)$, respectively. The general term of their Cauchy product is:
$$
\begin{gather}
c_n = \sum_{k=0}^n a_k b_{n-k} = \sum_{k=0}^n \frac{z^k}{k!} \frac{w^{n-k}}{(n-k)!} = \frac{1}{n!} \sum_{k=0}^n \frac{n!}{k!(n-k)!} z^k w^{n-k} \tag{17}
\end{gather}
$$
Recognizing the binomial coefficient $\binom{n}{k} = \frac{n!}{k!(n-k)!}$, step 17 becomes:
$$
\begin{gather}
c_n = \frac{1}{n!} \sum_{k=0}^n \binom{n}{k} z^k w^{n-k} \tag{18}
\end{gather}
$$
By the binomial theorem in the commutative field $\mathbb{C}$, the sum in step 18 is precisely $(z + w)^n$. Thus:
$$
\begin{gather}
c_n = \frac{(z + w)^n}{n!} \tag{19}
\end{gather}
$$
Summing $c_n$ over $n \ge 0$ yields:
$$
\begin{gather}
\sum_{n=0}^\infty c_n = \sum_{n=0}^\infty \frac{(z + w)^n}{n!} = \exp(z + w) \tag{20}
\end{gather}
$$
By step 16, $\sum_{n=0}^\infty c_n = \left(\sum_{j=0}^\infty a_j\right)\left(\sum_{k=0}^\infty b_k\right) = \exp(z) \exp(w)$. Consequently:
$$
\begin{gather}
\exp(z + w) = \exp(z) \exp(w) \tag{21}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$