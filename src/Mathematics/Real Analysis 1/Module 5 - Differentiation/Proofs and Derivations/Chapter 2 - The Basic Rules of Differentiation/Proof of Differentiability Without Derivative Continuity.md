---
dg-publish: true
---
Let $f: \mathbb{R} \to \mathbb{R}$ be defined by:
$$
\begin{gather}
f(x) := \begin{cases} x^2 \sin\left(\frac{1}{x}\right) & \text{if } x \neq 0 \\[2mm] 0 & \text{if } x = 0 \end{cases} \tag{1}
\end{gather}
$$

**Differentiability on $\mathbb{R} \setminus \{0\}$:**
Let $x \in \mathbb{R} \setminus \{0\}$. In an open neighborhood of $x$ not containing the origin, $f$ is the product of the monomial $u(x) = x^2$ and the composite trigonometric mapping $v(x) = \sin(1/x)$. 

By the [[Proof of The Chain Rule|Chain Rule]], the derivative of $v(x)$ with respect to $x$ is:
$$
\begin{gather}
\frac{d}{dx}\left[\sin\left(\frac{1}{x}\right)\right] = \cos\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) = \cos\left(\frac{1}{x}\right) \cdot \left(-\frac{1}{x^2}\right) = -\frac{1}{x^2}\cos\left(\frac{1}{x}\right) \tag{2}
\end{gather}
$$

Applying the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]] to $f(x) = x^2 \sin(1/x)$ yields:
$$
\begin{gather}
f'(x) = \left(\frac{d}{dx} x^2\right) \sin\left(\frac{1}{x}\right) + x^2 \frac{d}{dx}\left[\sin\left(\frac{1}{x}\right)\right] \tag{3}
\end{gather}
$$

Substituting $\frac{d}{dx}(x^2) = 2x$ and step 2 into step 3 produces:
$$
\begin{gather}
f'(x) = 2x \sin\left(\frac{1}{x}\right) + x^2 \left(-\frac{1}{x^2}\cos\left(\frac{1}{x}\right)\right) = 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) \tag{4}
\end{gather}
$$
which exists as a finite real quantity for all $x \neq 0$.

**Differentiability at the Origin $x = 0$:**
At the anchor point $x_0 = 0$, the derivative cannot be computed using the product rule formula of step 4 because $\frac{1}{x}$ is undefined at $0$. Instead, evaluate the derivative directly from the limit of the difference quotient.

For any non-zero displacement $h \neq 0$, the difference quotient is:
$$
\begin{gather}
\frac{f(0 + h) - f(0)}{h} = \frac{h^2 \sin\left(\frac{1}{h}\right) - 0}{h} = h \sin\left(\frac{1}{h}\right) \tag{5}
\end{gather}
$$

Because the circular sine mapping is bounded on $\mathbb{R}$ with $|\sin(\theta)| \le 1$ for all $\theta \in \mathbb{R}$, taking absolute values in step 5 gives:
$$
\begin{gather}
\left| \frac{f(h) - f(0)}{h} \right| = \left| h \sin\left(\frac{1}{h}\right) \right| = |h| \left|\sin\left(\frac{1}{h}\right)\right| \le |h| \cdot 1 = |h| \tag{6}
\end{gather}
$$

Expressing step 6 as a double inequality yields:
$$
\begin{gather}
-|h| \le \frac{f(h) - f(0)}{h} \le |h| \tag{7}
\end{gather}
$$

Because $\lim_{h \to 0} (-|h|) = 0$ and $\lim_{h \to 0} |h| = 0$, the Squeeze Theorem implies that:
$$
\begin{gather}
f'(0) = \lim_{h \to 0} \frac{f(h) - f(0)}{h} = 0 \tag{8}
\end{gather}
$$

Thus, $f$ is differentiable at $x = 0$ with $f'(0) = 0$. Combining step 4 and step 8 confirms that $f$ is differentiable everywhere on $\mathbb{R}$, with derivative given by:
$$
\begin{gather}
f'(x) = \begin{cases} 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) & \text{if } x \neq 0 \\[2mm] 0 & \text{if } x = 0 \end{cases} \tag{9}
\end{gather}
$$

**Discontinuity of $f'$ at $x = 0$:**
To determine whether $f'$ is continuous at $0$, investigate the limit $\lim_{x \to 0} f'(x)$.

For the first component of $f'(x)$ in step 9, the bounding property $|2x \sin(1/x)| \le 2|x|$ guarantees:
$$
\begin{gather}
\lim_{x \to 0} 2x \sin\left(\frac{1}{x}\right) = 0 \tag{10}
\end{gather}
$$

Now consider the second component $\cos(1/x)$. Define two sequences $(x_n)_{n=1}^\infty$ and $(y_n)_{n=1}^\infty$ in $\mathbb{R} \setminus \{0\}$ by:
$$
\begin{gather}
x_n := \frac{1}{2\pi n}, \quad y_n := \frac{1}{\pi + 2\pi n}, \quad \forall n \in \mathbb{N} \tag{11}
\end{gather}
$$

Both sequences converge to zero as $n \to \infty$: $\lim_{n \to \infty} x_n = 0$ and $\lim_{n \to \infty} y_n = 0$.

Evaluating $f'$ along the sequence $x_n$ using step 9 yields:
$$
\begin{gather}
f'(x_n) = 2\left(\frac{1}{2\pi n}\right) \sin(2\pi n) - \cos(2\pi n) = \frac{1}{\pi n} \cdot 0 - 1 = -1 \tag{12}
\end{gather}
$$
so that $\lim_{n \to \infty} f'(x_n) = -1$.

Evaluating $f'$ along the sequence $y_n$ gives:
$$
\begin{gather}
f'(y_n) = 2\left(\frac{1}{\pi + 2\pi n}\right) \sin(\pi + 2\pi n) - \cos(\pi + 2\pi n) = \frac{2}{\pi(2n+1)} \cdot 0 - (-1) = 1 \tag{13}
\end{gather}
$$
so that $\lim_{n \to \infty} f'(y_n) = 1$.

By the Heine sequential characterization of functional limits, because $\lim_{n \to \infty} f'(x_n) = -1 \neq 1 = \lim_{n \to \infty} f'(y_n)$, the limit $\lim_{x \to 0} f'(x)$ does not exist.

Because $\lim_{x \to 0} f'(x)$ fails to exist, it cannot equal $f'(0) = 0$. Therefore, $f'$ is discontinuous at the origin $x = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
