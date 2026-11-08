---
dg-publish: true
---
Define the real functions $f, g: \mathbb{R} \to \mathbb{R}$ by:
$$
\begin{gather}
f(x) := \begin{cases} x \sin\left(\dfrac{1}{x}\right) & \text{if } x \neq 0 \\[3mm] 0 & \text{if } x = 0 \end{cases} \qquad \text{and} \qquad g(x) := \begin{cases} x^2 \sin\left(\dfrac{1}{x}\right) & \text{if } x \neq 0 \\[3mm] 0 & \text{if } x = 0 \end{cases} \tag{1}
\end{gather}
$$

# Proposition 1
First, consider the continuity of $f$ on the punctured domain $\mathbb{R} \setminus \{0\}$. For any point $x \neq 0$, the reciprocal function $x \mapsto \frac{1}{x}$ is continuous. Because the circular trigonometric sine function is continuous everywhere on $\mathbb{R}$, the composite function $x \mapsto \sin(1/x)$ is continuous on $\mathbb{R} \setminus \{0\}$. Furthermore, the identity function $x \mapsto x$ is continuous on $\mathbb{R}$. As the product of two continuous functions, $f$ is continuous at every point $x \in \mathbb{R} \setminus \{0\}$.

Next, consider the continuity of $f$ at the anchor point $x_0 = 0$. For all $x \in \mathbb{R} \setminus \{0\}$, the trigonometric sine is bounded by unity:
$$
\begin{gather}
\left|\sin\left(\frac{1}{x}\right)\right| \le 1 \tag{2}
\end{gather}
$$
Multiplying step 2 by $|x| > 0$ gives:
$$
\begin{gather}
|f(x) - f(0)| = \left|x \sin\left(\frac{1}{x}\right) - 0\right| = |x| \left|\sin\left(\frac{1}{x}\right)\right| \le |x| \tag{3}
\end{gather}
$$
Because $\lim_{x \to 0} |x| = 0$, applying the Squeeze Theorem to step 3 reveals:
$$
\begin{gather}
\lim_{x \to 0} \big(f(x) - f(0)\big) = 0 \iff \lim_{x \to 0} f(x) = f(0) = 0 \tag{4}
\end{gather}
$$
Step 4 confirms that $f$ is continuous at $x = 0$. Thus, $f$ is continuous everywhere on $\mathbb{R}$.

To examine the differentiability of $f$ at the origin, construct the difference quotient for an arbitrary non-zero increment $h \neq 0$:
$$
\begin{gather}
\frac{f(0 + h) - f(0)}{h} = \frac{h \sin\left(\frac{1}{h}\right) - 0}{h} = \sin\left(\frac{1}{h}\right) \tag{5}
\end{gather}
$$

To prove that the limit as $h \to 0$ of step 5 does not exist, consider the two sequences $\{a_n\}_{n=1}^\infty$ and $\{b_n\}_{n=1}^\infty$ defined for each index $n \in \mathbb{N}$ by:
$$
\begin{gather}
a_n := \frac{1}{2\pi n} \qquad \text{and} \qquad b_n := \frac{1}{2\pi n + \frac{\pi}{2}} \tag{6}
\end{gather}
$$
Both sequences consist of non-zero real numbers that converge to zero as $n \to \infty$:
$$
\begin{gather}
\lim_{n \to \infty} a_n = 0 \qquad \text{and} \qquad \lim_{n \to \infty} b_n = 0 \tag{7}
\end{gather}
$$

Evaluating the difference quotient along the sequence $\{a_n\}$ yields:
$$
\begin{gather}
\lim_{n \to \infty} \frac{f(a_n) - f(0)}{a_n} = \lim_{n \to \infty} \sin(2\pi n) = \lim_{n \to \infty} 0 = 0 \tag{8}
\end{gather}
$$
Evaluating the difference quotient along the sequence $\{b_n\}$ yields:
$$
\begin{gather}
\lim_{n \to \infty} \frac{f(b_n) - f(0)}{b_n} = \lim_{n \to \infty} \sin\left(2\pi n + \frac{\pi}{2}\right) = \lim_{n \to \infty} 1 = 1 \tag{9}
\end{gather}
$$

Because the two sequential limits in step 8 and step 9 are distinct ($0 \neq 1$), the Sequential Criterion for Functional Limits establishes that:
$$
\begin{gather}
\lim_{h \to 0} \frac{f(h) - f(0)}{h} \quad \text{does not exist} \tag{10}
\end{gather}
$$
Thus, $f$ is not differentiable at $x = 0$.

---
# Proposition 2
First, consider the differentiability of $g$ at the origin $x_0 = 0$. Constructing the difference quotient for $h \neq 0$ yields:
$$
\begin{gather}
\frac{g(0 + h) - g(0)}{h} = \frac{h^2 \sin\left(\frac{1}{h}\right) - 0}{h} = h \sin\left(\frac{1}{h}\right) \tag{11}
\end{gather}
$$

Applying the boundedness of the sine function gives:
$$
\begin{gather}
\left|\frac{g(h) - g(0)}{h}\right| = \left|h \sin\left(\frac{1}{h}\right)\right| = |h| \left|\sin\left(\frac{1}{h}\right)\right| \le |h| \tag{12}
\end{gather}
$$
Because $\lim_{h \to 0} |h| = 0$, applying the Squeeze Theorem to step 12 establishes:
$$
\begin{gather}
g'(0) = \lim_{h \to 0} \frac{g(h) - g(0)}{h} = 0 \tag{13}
\end{gather}
$$
Thus, $g$ is differentiable at $x = 0$ with derivative $g'(0) = 0$.

Second, consider any non-zero point $x \neq 0$. In an open neighborhood of $x$ avoiding the origin, $g$ is the product of the differentiable monomial $x \mapsto x^2$ and the differentiable composite function $x \mapsto \sin(1/x)$. Computing the derivative via the product rule and chain rule yields:
$$
\begin{gather}
g'(x) = \frac{d}{dx}\big(x^2\big) \sin\left(\frac{1}{x}\right) + x^2 \frac{d}{dx}\left(\sin\left(\frac{1}{x}\right)\right) = 2x \sin\left(\frac{1}{x}\right) + x^2 \cos\left(\frac{1}{x}\right) \left(-\frac{1}{x^2}\right) \tag{14}
\end{gather}
$$
Simplifying step 14 gives:
$$
\begin{gather}
g'(x) = 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) \tag{15}
\end{gather}
$$
Thus, $g$ is differentiable at every point $x \in \mathbb{R}$, and its global derivative is given by:
$$
\begin{gather}
g'(x) = \begin{cases} 2x \sin\left(\dfrac{1}{x}\right) - \cos\left(\dfrac{1}{x}\right) & \text{if } x \neq 0 \\[3mm] 0 & \text{if } x = 0 \end{cases} \tag{16}
\end{gather}
$$

Finally, examine the continuity of $g'$ at the origin $x = 0$. As $x \to 0$, the first term in step 15 satisfies:
$$
\begin{gather}
\left|2x \sin\left(\frac{1}{x}\right)\right| \le 2|x| \implies \lim_{x \to 0} 2x \sin\left(\frac{1}{x}\right) = 0 \tag{17}
\end{gather}
$$

Consider the behavior of the second term $-\cos(1/x)$. Define the two sequences $\{u_n\}_{n=1}^\infty$ and $\{v_n\}_{n=1}^\infty$ by:
$$
\begin{gather}
u_n := \frac{1}{2\pi n} \qquad \text{and} \qquad v_n := \frac{1}{(2n + 1)\pi} \tag{18}
\end{gather}
$$
Both sequences converge to zero as $n \to \infty$. Evaluating the derivative $g'$ along these sequences yields:
$$
\begin{gather}
\lim_{n \to \infty} g'(u_n) = \lim_{n \to \infty} \left( 2u_n \sin(2\pi n) - \cos(2\pi n) \right) = 0 - 1 = -1 \tag{19}
\end{gather}
$$
and
$$
\begin{gather}
\lim_{n \to \infty} g'(v_n) = \lim_{n \to \infty} \left( 2v_n \sin((2n+1)\pi) - \cos((2n+1)\pi) \right) = 0 - (-1) = 1 \tag{20}
\end{gather}
$$

Because the sequential limits in step 19 and step 20 do not match ($-1 \neq 1$), the functional limit:
$$
\begin{gather}
\lim_{x \to 0} g'(x) \quad \text{does not exist} \tag{21}
\end{gather}
$$
Because the limit of $g'(x)$ as $x \to 0$ does not exist, $g'$ is not continuous at $x = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$