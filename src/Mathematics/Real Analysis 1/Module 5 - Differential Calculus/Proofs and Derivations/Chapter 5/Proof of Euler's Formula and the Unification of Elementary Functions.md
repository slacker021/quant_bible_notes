---
dg-publish: true
---
Let $\theta \in \mathbb{R}$. By Definition 5.4, the complex exponential $e^z$ is defined by the power series:
$$
\begin{gather}
e^z = \sum_{n=0}^\infty \frac{z^n}{n!} \tag{1}
\end{gather}
$$

Evaluating equation (1) at the purely imaginary argument $z = i\theta$:
$$
\begin{gather}
e^{i\theta} = \sum_{n=0}^\infty \frac{(i\theta)^n}{n!} \tag{2}
\end{gather}
$$

Evaluate the successive powers of the imaginary unit $i$:
$$
\begin{gather}
i^0 = 1, \quad i^1 = i, \quad i^2 = -1, \quad i^3 = -i, \quad i^4 = 1, \dots \tag{3}
\end{gather}
$$
In general, for any integer $m \ge 0$:
$$
\begin{gather}
i^{2m} = (i^2)^m = (-1)^m \tag{4} \\
i^{2m+1} = i^{2m} \cdot i = (-1)^m i \tag{5}
\end{gather}
$$

Because the series in equation (2) converges absolutely, its terms can be rearranged without altering the sum into even and odd index summations:
$$
\begin{gather}
e^{i\theta} = \sum_{m=0}^\infty \frac{(i\theta)^{2m}}{(2m)!} + \sum_{m=0}^\infty \frac{(i\theta)^{2m+1}}{(2m+1)!} \tag{6}
\end{gather}
$$

Substituting equations (4) and (5) into equation (6):
$$
\begin{gather}
e^{i\theta} = \sum_{m=0}^\infty \frac{(-1)^m \theta^{2m}}{(2m)!} + i \sum_{m=0}^\infty \frac{(-1)^m \theta^{2m+1}}{(2m+1)!} \tag{7}
\end{gather}
$$

Recognizing the series from the canonical Maclaurin expansions established in Chapter 3 (Table 3.1):
$$
\begin{gather}
\cos\theta = \sum_{m=0}^\infty \frac{(-1)^m \theta^{2m}}{(2m)!} \tag{8} \\
\sin\theta = \sum_{m=0}^\infty \frac{(-1)^m \theta^{2m+1}}{(2m+1)!} \tag{9}
\end{gather}
$$

Substituting equations (8) and (9) into equation (7) produces Euler's formula:
$$
\begin{gather}
e^{i\theta} = \cos\theta + i\sin\theta \tag{10}
\end{gather}
$$

Replacing $\theta$ with $-\theta$ in equation (10):
$$
\begin{gather}
e^{-i\theta} = \cos(-\theta) + i\sin(-\theta) = \cos\theta - i\sin\theta \tag{11}
\end{gather}
$$

Adding and subtracting equations (10) and (11) yields:
$$
\begin{gather}
e^{i\theta} + e^{-i\theta} = 2\cos\theta \implies \cos\theta = \frac{e^{i\theta} + e^{-i\theta}}{2} \tag{12} \\
e^{i\theta} - e^{-i\theta} = 2i\sin\theta \implies \sin\theta = \frac{e^{i\theta} - e^{-i\theta}}{2i} \tag{13}
\end{gather}
$$
extending holomorphically to all $z \in \mathbb{C}$ to define $\cos z$ and $\sin z$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
