---
dg-publish: true
---
Evaluating the successive derivatives of the basic elementary functions at $x_0 = 0$ yields their canonical Maclaurin polynomials with remainder terms.

### 1. The Exponential Function $f(x) = e^x$
For all $k \in \mathbb{N}$, $f^{(k)}(x) = e^x$, so $f^{(k)}(0) = 1$.
By Taylor's Theorem with the Peano remainder:
$$
\begin{gather}
e^x = \sum_{k=0}^n \frac{f^{(k)}(0)}{k!}x^k + o(x^n) = 1 + x + \frac{x^2}{2!} + \dots + \frac{x^n}{n!} + o(x^n) \quad \text{as } x \to 0 \tag{1}
\end{gather}
$$
Furthermore, using the Lagrange remainder on any compact interval $[-R, R]$, $|R_n(x)| \le \frac{e^R}{(n+1)!}R^{n+1} \to 0$ as $n \to \infty$, proving that the Taylor series converges to $e^x$ on all of $\mathbb{R}$.

### 2. The Sine and Cosine Functions
For $f(x) = \sin x$:
$$
\begin{gather}
f^{(k)}(x) = \sin\left(x + \frac{k\pi}{2}\right) \implies f^{(k)}(0) = \begin{cases} 0, & k = 2m \\ (-1)^m, & k = 2m + 1 \end{cases} \tag{2}
\end{gather}
$$
Because all even derivatives vanish, the Maclaurin polynomial contains only odd powers:
$$
\begin{gather}
\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots + (-1)^m \frac{x^{2m+1}}{(2m+1)!} + o(x^{2m+2}) \quad \text{as } x \to 0 \tag{3}
\end{gather}
$$

For $g(x) = \cos x$:
$$
\begin{gather}
g^{(k)}(x) = \cos\left(x + \frac{k\pi}{2}\right) \implies g^{(k)}(0) = \begin{cases} (-1)^m, & k = 2m \\ 0, & k = 2m + 1 \end{cases} \tag{4}
\end{gather}
$$
Because all odd derivatives vanish, the Maclaurin polynomial contains only even powers:
$$
\begin{gather}
\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots + (-1)^m \frac{x^{2m}}{(2m)!} + o(x^{2m+1}) \quad \text{as } x \to 0 \tag{5}
\end{gather}
$$
Because $|\sin^{(n+1)}(\xi)| \le 1$ and $|\cos^{(n+1)}(\xi)| \le 1$, the Lagrange remainder satisfies $|R_n(x)| \le \frac{|x|^{n+1}}{(n+1)!} \to 0$ for all $x \in \mathbb{R}$.

### 3. The Natural Logarithm $f(x) = \ln(1 + x)$
For $x > -1$, $f'(x) = (1 + x)^{-1}$, and by induction:
$$
\begin{gather}
f^{(k)}(x) = (-1)^{k-1}(k - 1)!(1 + x)^{-k} \implies f^{(k)}(0) = (-1)^{k-1}(k - 1)! \tag{6}
\end{gather}
$$

The coefficient of $x^k$ in the Taylor polynomial is:
$$
\begin{gather}
\frac{f^{(k)}(0)}{k!} = \frac{(-1)^{k-1}(k - 1)!}{k!} = \frac{(-1)^{k-1}}{k} \tag{7}
\end{gather}
$$

Therefore:
$$
\begin{gather}
\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \dots + (-1)^{n-1}\frac{x^n}{n} + o(x^n) \quad \text{as } x \to 0 \tag{8}
\end{gather}
$$

### 4. The Binomial Function $f(x) = (1 + x)^\alpha$ ($\alpha \in \mathbb{R}$)
Differentiating repeatedly:
$$
\begin{gather}
f^{(k)}(x) = \alpha(\alpha - 1)\dots(\alpha - k + 1)(1 + x)^{\alpha - k} \implies f^{(k)}(0) = \alpha(\alpha - 1)\dots(\alpha - k + 1) \tag{9}
\end{gather}
$$

The Taylor polynomial is:
$$
\begin{gather}
(1 + x)^\alpha = 1 + \alpha x + \frac{\alpha(\alpha - 1)}{2!}x^2 + \dots + \frac{\alpha(\alpha - 1)\dots(\alpha - n + 1)}{n!}x^n + o(x^n) \quad \text{as } x \to 0 \tag{10}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
