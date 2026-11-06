---
dg-publish: true
---
Let $\sum_{n=k}^\infty x_n = X$ and $\sum_{n=k}^\infty y_n = Y$ be two convergent series of real numbers, with sequences of partial sums defined for each integer $N \ge k$ by: 
$$
\begin{gather}
S_{x, N} := \sum_{n=k}^N x_n \quad \text{and} \quad S_{y, N} := \sum_{n=k}^N y_n \tag{1}
\end{gather}
$$
By definition of series convergence, $\lim_{N \to \infty} S_{x, N} = X$ and $\lim_{N \to \infty} S_{y, N} = Y$.

# Proposition 1
Let $c \in \mathbb{R}$ be an arbitrary real constant. For each $N \ge k$, the $N$-th partial sum of the series $\sum_{n=k}^\infty (c \cdot x_n)$ evaluates by the distributive law of $\mathbb{R}$ to: 
$$
\begin{gather}
S_{c, N} := \sum_{n=k}^N (c \cdot x_n) = c \sum_{n=k}^N x_n = c \cdot S_{x, N} \tag{2}
\end{gather}
$$
Passing to the limit as $N \to \infty$ in step 2 and applying the [[Proof of Arithmetic Operations Involving Limits|scalar multiple rule for sequence limits]] yields: 
$$
\begin{gather}
\lim_{N \to \infty} S_{c, N} = \lim_{N \to \infty} (c \cdot S_{x, N}) = c \lim_{N \to \infty} S_{x, N} = c \cdot X \tag{3}
\end{gather}
$$
Thus, the series $\sum_{n=k}^\infty (c \cdot x_n)$ converges to the sum $c X = c \sum_{n=k}^\infty x_n$.

---
# Proposition 2
For each $N \ge k$, the $N$-th partial sum of the combined series $\sum_{n=k}^\infty (x_n \pm y_n)$ evaluates by the associativity and commutativity of addition in $\mathbb{R}$ to: 
$$
\begin{gather}
S_{x \pm y, N} := \sum_{n=k}^N (x_n \pm y_n) = \sum_{n=k}^N x_n \pm \sum_{n=k}^N y_n = S_{x, N} \pm S_{y, N} \tag{4}
\end{gather}
$$
Passing to the limit as $N \to \infty$ in step 4 and applying the [[Proof of Arithmetic Operations Involving Limits|sum and difference rules for sequence limits]] yields: 
$$
\begin{gather}
\lim_{N \to \infty} S_{x \pm y, N} = \lim_{N \to \infty} (S_{x, N} \pm S_{y, N}) = \lim_{N \to \infty} S_{x, N} \pm \lim_{N \to \infty} S_{y, N} = X \pm Y \tag{5}
\end{gather}
$$
Thus, the series $\sum_{n=k}^\infty (x_n \pm y_n)$ converges to the sum $X \pm Y = \sum_{n=k}^\infty x_n \pm \sum_{n=k}^\infty y_n$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
