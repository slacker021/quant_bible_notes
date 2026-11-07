---
dg-publish: true
---
Let $f: \mathbb{R} \to \mathbb{R}$ be twice differentiable on $\mathbb{R}$, with:
$$
\begin{gather}
M_0 := \sup_{x \in \mathbb{R}} |f(x)| < \infty, \quad M_2 := \sup_{x \in \mathbb{R}} |f''(x)| < \infty \tag{1}
\end{gather}
$$

Let $x \in \mathbb{R}$ be an arbitrary point, and let $h > 0$ be an arbitrary positive parameter.

### Step 1: Taylor Expansions Forward and Backward
By the Quantitative Linearization Error Bound Theorem (or Lagrange's remainder for order 2), expanding $f(x + h)$ and $f(x - h)$ around $x$:
$$
\begin{gather}
f(x + h) = f(x) + f'(x)h + \frac{f''(\xi_1)}{2}h^2 \quad \text{for some } \xi_1 \in (x, x + h) \tag{2} \\
f(x - h) = f(x) - f'(x)h + \frac{f''(\xi_2)}{2}h^2 \quad \text{for some } \xi_2 \in (x - h, x) \tag{3}
\end{gather}
$$

Subtracting the equation of step 3 from the equation of step 2:
$$
\begin{gather}
f(x + h) - f(x - h) = 2 f'(x) h + \frac{f''(\xi_1) - f''(\xi_2)}{2}h^2 \tag{4}
\end{gather}
$$

### Step 2: Isolating the First Derivative
Rearranging the equation of step 4 to solve for $f'(x)$:
$$
\begin{gather}
f'(x) = \frac{f(x + h) - f(x - h)}{2h} - \frac{f''(\xi_1) - f''(\xi_2)}{4}h \tag{5}
\end{gather}
$$

Taking absolute values and applying the triangle inequality:
$$
\begin{gather}
|f'(x)| \le \frac{|f(x + h)| + |f(x - h)|}{2h} + \frac{|f''(\xi_1)| + |f''(\xi_2)|}{4}h \tag{6}
\end{gather}
$$

By definition of the suprema $M_0$ and $M_2$:
$$
\begin{gather}
|f(x \pm h)| \le M_0, \quad |f''(\xi_i)| \le M_2 \tag{7}
\end{gather}
$$

Substituting these bounds into the inequality of step 6:
$$
\begin{gather}
|f'(x)| \le \frac{2 M_0}{2h} + \frac{2 M_2}{4}h = \frac{M_0}{h} + \frac{M_2}{2}h \tag{8}
\end{gather}
$$

Because the inequality of step 8 holds for every $x \in \mathbb{R}$, taking the supremum over $x \in \mathbb{R}$:
$$
\begin{gather}
M_1 = \sup_{x \in \mathbb{R}} |f'(x)| \le \frac{M_0}{h} + \frac{M_2}{2}h \quad \forall h > 0 \tag{9}
\end{gather}
$$

### Step 3: Minimization Over the Parameter $h$
The inequality of step 9 holds for *every* choice of $h > 0$. We choose $h$ to minimize the upper bound function:
$$
\begin{gather}
\varphi(h) = \frac{M_0}{h} + \frac{M_2}{2}h \tag{10}
\end{gather}
$$

If $M_2 = 0$, then $f''(x) \equiv 0$, so $f$ is affine. Because $f$ is bounded on $\mathbb{R}$, $f$ must be constant, so $M_1 = 0$, and the inequality holds trivially.

Assume $M_2 > 0$. Differentiating $\varphi(h)$ with respect to $h$:
$$
\begin{gather}
\varphi'(h) = -\frac{M_0}{h^2} + \frac{M_2}{2} = 0 \implies h^2 = \frac{2 M_0}{M_2} \implies h^* = \sqrt{\frac{2 M_0}{M_2}} \tag{11}
\end{gather}
$$

Evaluating $\varphi(h)$ at the optimal parameter $h^*$:
$$
\begin{gather}
\varphi(h^*) = \frac{M_0}{\sqrt{\frac{2 M_0}{M_2}}} + \frac{M_2}{2} \sqrt{\frac{2 M_0}{M_2}} = \sqrt{\frac{M_0 M_2}{2}} + \sqrt{\frac{M_0 M_2}{2}} = 2 \sqrt{\frac{M_0 M_2}{2}} = \sqrt{2 M_0 M_2} \tag{12}
\end{gather}
$$

Substituting the minimum value into the inequality of step 9:
$$
\begin{gather}
M_1 \le \sqrt{2 M_0 M_2} \tag{13}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
