---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $x_0 \in \text{int}(E)$, and let $f: E \to \mathbb{R}$ be differentiable at $x_0$.

Suppose $f$ attains a local maximum at $x_0$. 

By Definition 3.1, there exists a radius $\delta_0 > 0$ such that $(x_0 - \delta_0, x_0 + \delta_0) \subseteq E$ and:
$$
\begin{gather}
f(x) \le f(x_0) \quad \forall x \in (x_0 - \delta_0, x_0 + \delta_0) \tag{1}
\end{gather}
$$

For any increment $h$ satisfying $0 < |h| < \delta_0$, condition (1) implies that:
$$
\begin{gather}
\Delta f(x_0; h) = f(x_0 + h) - f(x_0) \le 0 \tag{2}
\end{gather}
$$

### Case 1: Right-Hand Limit ($h > 0$)
For $0 < h < \delta_0$, dividing the non-positive numerator (2) by the positive denominator $h > 0$ gives:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} \le 0 \tag{3}
\end{gather}
$$

Because $f$ is differentiable at $x_0$, the two-sided limit exists and equals the right-hand limit. By the order preservation property of limits (Theorem 2.1 of Module 3):
$$
\begin{gather}
f'(x_0) = \lim_{h \to 0^+} \frac{f(x_0 + h) - f(x_0)}{h} \le 0 \tag{4}
\end{gather}
$$

### Case 2: Left-Hand Limit ($h < 0$)
For $-\delta_0 < h < 0$, dividing the non-positive numerator (2) by the negative denominator $h < 0$ reverses the inequality:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} \ge 0 \tag{5}
\end{gather}
$$

Taking the left-hand limit as $h \to 0^-$:
$$
\begin{gather}
f'(x_0) = \lim_{h \to 0^-} \frac{f(x_0 + h) - f(x_0)}{h} \ge 0 \tag{6}
\end{gather}
$$

### Conclusion
Combining inequalities (4) and (6):
$$
\begin{gather}
f'(x_0) \le 0 \quad \text{and} \quad f'(x_0) \ge 0 \implies f'(x_0) = 0 \tag{7}
\end{gather}
$$

If $f$ attains a local minimum at $x_0$, the function $-f$ attains a local maximum at $x_0$. Applying the previous result to $-f$ yields $(-f)'(x_0) = -f'(x_0) = 0 \implies f'(x_0) = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
