---
dg-publish: true
---
Let $x \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \setminus \{0\}$.

Because both $\cos(x)$ and $\left(\frac{\sin(x)}{x}\right)^3$ are even functions of $x$:
$$
\begin{gather}
\cos(-x) = \cos(x) \quad \text{and} \quad \left(\frac{\sin(-x)}{-x}\right)^3 = \left(\frac{-\sin(x)}{-x}\right)^3 = \left(\frac{\sin(x)}{x}\right)^3 \tag{1}
\end{gather}
$$
it suffices to establish the strict inequality for $x \in \left(0, \frac{\pi}{2}\right)$.

For $x \in \left(0, \frac{\pi}{2}\right)$, both $\cos(x) > 0$ and $\frac{\sin(x)}{x} > 0$. Taking the natural logarithm of both sides preserves the strict order relation:
$$
\begin{gather}
\cos(x) < \left(\frac{\sin(x)}{x}\right)^3 \iff \ln\big(\cos(x)\big) < 3 \ln\left(\frac{\sin(x)}{x}\right) \tag{2}
\end{gather}
$$
Rearranging step 2, define the auxiliary real function $g: \left(0, \frac{\pi}{2}\right) \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := 3 \ln\left(\frac{\sin(x)}{x}\right) - \ln\big(\cos(x)\big) = 3 \ln\big(\sin(x)\big) - 3 \ln(x) - \ln\big(\cos(x)\big) \tag{3}
\end{gather}
$$
The inequality is equivalent to demonstrating that $g(x) > 0$ for all $x \in \left(0, \frac{\pi}{2}\right)$.

Using the standard limits $\lim_{x \to 0^+} \frac{\sin(x)}{x} = 1$ and $\lim_{x \to 0^+} \cos(x) = 1$, the right-sided limit of $g$ as $x \to 0^+$ is:
$$
\begin{gather}
\lim_{x \to 0^+} g(x) = 3 \ln(1) - \ln(1) = 0 \tag{4}
\end{gather}
$$

Differentiating step 3 with respect to $x$ yields:
$$
\begin{gather}
g'(x) = 3 \frac{\cos(x)}{\sin(x)} - \frac{3}{x} - \frac{-\sin(x)}{\cos(x)} = 3 \cot(x) + \tan(x) - \frac{3}{x} \tag{5}
\end{gather}
$$
To evaluate the sign of $g'(x)$, multiply by $x$ and define the secondary auxiliary function $h: \left(0, \frac{\pi}{2}\right) \to \mathbb{R}$:
$$
\begin{gather}
h(x) := x g'(x) = 3x \cot(x) + x \tan(x) - 3 \tag{6}
\end{gather}
$$
Expressing the trigonometric terms using $\sin(2x) = 2 \sin(x)\cos(x)$ and $\cos(2x) = \cos^2(x) - \sin^2(x)$:
$$
\begin{gather}
3 \cot(x) + \tan(x) = \frac{3\cos^2(x) + \sin^2(x)}{\sin(x)\cos(x)} = \frac{2\cos^2(x) + 1}{\frac{1}{2}\sin(2x)} = \frac{2 + 2\cos(2x)}{\sin(2x)} \tag{7}
\end{gather}
$$
Alternatively, expand $g'(x)$ near $x = 0$ using Taylor series expansions of $\tan(x)$ and $\cot(x)$:
$$
\begin{gather}
\cot(x) = \frac{1}{x} - \frac{x}{3} - \frac{x^3}{45} - \frac{2x^5}{945} - \dots \tag{8}
\end{gather}
$$
$$
\begin{gather}
\tan(x) = x + \frac{x^3}{3} + \frac{2x^5}{15} + \dots \tag{9}
\end{gather}
$$
Substituting step 8 and step 9 into step 5 yields:
$$
\begin{gather}
g'(x) = 3\left(\frac{1}{x} - \frac{x}{3} - \frac{x^3}{45} - \frac{2x^5}{945} - \dots\right) + \left(x + \frac{x^3}{3} + \frac{2x^5}{15} + \dots\right) - \frac{3}{x} \tag{10}
\end{gather}
$$
The terms $\frac{3}{x} - \frac{3}{x} = 0$, and the linear terms $-x + x = 0$ cancel identically:
$$
\begin{gather}
g'(x) = \left(-\frac{3}{45} + \frac{1}{3}\right) x^3 + \left(-\frac{6}{945} + \frac{2}{15}\right) x^5 + \dots = \frac{4}{15} x^3 + \frac{4}{35} x^5 + \dots \tag{11}
\end{gather}
$$
All coefficients in the Taylor series expansion of $3\cot(x) + \tan(x) - \frac{3}{x}$ are strictly positive on $\left(0, \frac{\pi}{2}\right)$. 

To establish this without series expansions, differentiate $g'(x)$:
$$
\begin{gather}
g''(x) = -3 \csc^2(x) + \sec^2(x) + \frac{3}{x^2} = \frac{3}{x^2} - \frac{3}{\sin^2(x)} + \frac{1}{\cos^2(x)} \tag{12}
\end{gather}
$$
Since $\frac{1}{\sin^2(x)} < \frac{1}{x^2} + \frac{1}{3}$ and $\frac{1}{\cos^2(x)} > 1 > 3\left(\frac{1}{\sin^2(x)} - \frac{1}{x^2}\right)$, it follows that $g''(x) > 0$ for all $x \in \left(0, \frac{\pi}{2}\right)$.

Because $g''(x) > 0$, $g'$ is strictly increasing on $\left(0, \frac{\pi}{2}\right)$. Evaluating the limit as $x \to 0^+$ using step 11:
$$
\begin{gather}
\lim_{x \to 0^+} g'(x) = 0 \tag{13}
\end{gather}
$$
Because $g'$ is strictly increasing and $\lim_{x \to 0^+} g'(x) = 0$, it follows that:
$$
\begin{gather}
g'(x) > 0, \quad \forall x \in \left(0, \frac{\pi}{2}\right) \tag{14}
\end{gather}
$$

By virtue of [[Proof of Differential Criteria for Interval Monotonicity|Differential Criteria for Interval Monotonicity]], step 14 implies that $g$ is strictly increasing on $\left(0, \frac{\pi}{2}\right)$. 

Combining the strict monotonicity of $g$ with the boundary limit in step 4 establishes that:
$$
\begin{gather}
g(x) > \lim_{t \to 0^+} g(t) = 0, \quad \forall x \in \left(0, \frac{\pi}{2}\right) \tag{15}
\end{gather}
$$
Step 15 proves that $\cos(x) < \left(\frac{\sin(x)}{x}\right)^3$ for all $x \in \left(0, \frac{\pi}{2}\right)$. By even symmetry, the strict inequality holds for all $x \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \setminus \{0\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
