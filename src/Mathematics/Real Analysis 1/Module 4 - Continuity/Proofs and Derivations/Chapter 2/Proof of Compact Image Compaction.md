---
dg-publish: true
---
Let $K \subset \mathbb{R}$ be a compact set (closed and bounded in $\mathbb{R}$), and let $f: K \to \mathbb{R}$ be continuous on $K$. 

By the Heine–Borel Theorem in Euclidean space $\mathbb{R}$, a subset is compact if and only if it is closed and bounded. 

**Boundedness of $f(K)$:**
By the [[Proof of the Weierstrass Global Boundedness Theorem]], there exists a constant $M_0 > 0$ such that for all $x \in K$, $|f(x)| \le M_0$. 

Consequently, the image set $f(K)$ is bounded in $\mathbb{R}$.

**Closedness of $f(K)$:**
To demonstrate that $f(K)$ is closed, let $\{y_n\}_{n=1}^\infty \subseteq f(K)$ be an arbitrary sequence converging to a real limit point $y_0 \in \mathbb{R}$:
$$
\begin{gather}
\lim_{n \to \infty} y_n = y_0 \tag{1}
\end{gather}
$$

Because $y_n \in f(K)$ for each $n \in \mathbb{N}$, there exists an argument $x_n \in K$ such that:
$$
\begin{gather}
f(x_n) = y_n \tag{2}
\end{gather}
$$

Consider the sequence of arguments $\{x_n\}_{n=1}^\infty \subseteq K$. 

Because $K$ is compact, it is sequentially compact: every sequence in $K$ contains a subsequence that converges to a point in $K$. 

Therefore, there exists a subsequence $\{x_{n_k}\}_{k=1}^\infty$ and an element $x_0 \in K$ such that:
$$
\begin{gather}
\lim_{k \to \infty} x_{n_k} = x_0 \tag{3}
\end{gather}
$$

Because $f$ is continuous on $K$, it is continuous at $x_0 \in K$. Applying the Heine sequential criterion to step 3:
$$
\begin{gather}
\lim_{k \to \infty} f(x_{n_k}) = f(x_0) \tag{4}
\end{gather}
$$

However, by step 2, $f(x_{n_k}) = y_{n_k}$. 

Because the parent sequence $\{y_n\}$ converges to $y_0$ by step 1, every subsequence must converge to the same limit:
$$
\begin{gather}
\lim_{k \to \infty} f(x_{n_k}) = \lim_{k \to \infty} y_{n_k} = y_0 \tag{5}
\end{gather}
$$

By the uniqueness of limits in $\mathbb{R}$, comparing step 4 and step 5 yields:
$$
\begin{gather}
f(x_0) = y_0 \tag{6}
\end{gather}
$$

Because $x_0 \in K$, it follows from step 6 that $y_0 \in f(K)$. 

Because $f(K)$ contains all its limit points, $f(K)$ is closed in $\mathbb{R}$. 

Being both closed and bounded, $f(K)$ is compact.

**Special Case: Compact Interval $K = [a, b]$:**
If $K = [a, b]$, then $K$ is simultaneously compact and an interval. 

By the [[Proof of the Image of an Interval under Continuous Mappings]], $f([a, b])$ is an interval. 

By the [[Proof of the Weierstrass Extreme Value Theorem]], $f$ attains its minimum $m = \min f([a, b])$ and maximum $M = \max f([a, b])$ on $[a, b]$. 

The only interval in $\mathbb{R}$ with minimum $m$ and maximum $M$ containing both endpoints is the closed bounded interval $[m, M]$:
$$
\begin{gather}
f([a, b]) = [m, M] \tag{7}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
