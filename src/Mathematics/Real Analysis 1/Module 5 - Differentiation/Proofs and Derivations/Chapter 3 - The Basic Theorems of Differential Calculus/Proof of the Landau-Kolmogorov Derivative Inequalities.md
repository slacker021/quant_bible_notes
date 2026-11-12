---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval of the real line, let $f: I \to \mathbb{R}$ be a function twice differentiable on $I$, and define the supremum norms:
$$
\begin{gather}
M_0 := \sup_{x \in I} |f(x)|, \qquad M_1 := \sup_{x \in I} |f'(x)|, \qquad M_2 := \sup_{x \in I} |f''(x)| \tag{1}
\end{gather}
$$
Assume that $M_0 < \infty$ and $M_2 < \infty$. If $M_2 = 0$, then $f''(x) = 0$ for all $x \in I$, which implies that $f$ is an affine function: $f(x) = c_1 x + c_0$. Because $M_0 < \infty$, the only bounded affine functions on unbounded or non-degenerate domains are constant functions ($c_1 = 0$), whence $M_1 = 0$, and all bounds hold trivially. Thus, assume $M_2 > 0$ and $M_0 > 0$.

# Proposition 1
Let $I = \mathbb{R}$. Fix an arbitrary point $x \in \mathbb{R}$ and an arbitrary perturbation parameter $h > 0$. 

Because $f$ is twice differentiable on $\mathbb{R}$, applying [[Proof of Lagrange's Form of the Taylor Remainder|Taylor's Formula with the Lagrange Remainder]] of order $n = 1$ on the intervals $[x, x + h]$ and $[x - h, x]$ yields:
$$
\begin{gather}
f(x + h) = f(x) + h f'(x) + \frac{h^2}{2} f''(\xi_1) \tag{2}
\end{gather}
$$
$$
\begin{gather}
f(x - h) = f(x) - h f'(x) + \frac{h^2}{2} f''(\xi_2) \tag{3}
\end{gather}
$$
for some intermediate points $\xi_1 \in (x, x + h)$ and $\xi_2 \in (x - h, x)$.

Subtracting step 3 from step 2 eliminates both $f(x)$ and the even linear components:
$$
\begin{gather}
f(x + h) - f(x - h) = 2h f'(x) + \frac{h^2}{2}\big(f''(\xi_1) - f''(\xi_2)\big) \tag{4}
\end{gather}
$$
Isolating the term $2h f'(x)$ in step 4 gives:
$$
\begin{gather}
2h f'(x) = f(x + h) - f(x - h) - \frac{h^2}{2}\big(f''(\xi_1) - f''(\xi_2)\big) \tag{5}
\end{gather}
$$

Taking absolute values on both sides of step 5 and invoking the triangle inequality:
$$
\begin{gather}
2h |f'(x)| \le |f(x + h)| + |f(x - h)| + \frac{h^2}{2}|f''(\xi_1)| + \frac{h^2}{2}|f''(\xi_2)| \tag{6}
\end{gather}
$$
By definition of the supremum norms in step 1:
$$
\begin{gather}
|f(x \pm h)| \le M_0 \quad \text{and} \quad |f''(\xi_i)| \le M_2 \tag{7}
\end{gather}
$$
Substituting the uniform bounds of step 7 into step 6 produces:
$$
\begin{gather}
2h |f'(x)| \le 2M_0 + \frac{h^2}{2}(2M_2) = 2M_0 + h^2 M_2 \tag{8}
\end{gather}
$$
Dividing step 8 by $2h > 0$ yields:
$$
\begin{gather}
|f'(x)| \le \frac{M_0}{h} + \frac{h}{2} M_2, \quad \forall h > 0 \tag{9}
\end{gather}
$$

Define the real-valued objective function $\phi: (0, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
\phi(h) := \frac{M_0}{h} + \frac{M_2}{2} h \tag{10}
\end{gather}
$$
Differentiating $\phi(h)$ with respect to $h$:
$$
\begin{gather}
\phi'(h) = -\frac{M_0}{h^2} + \frac{M_2}{2} \tag{11}
\end{gather}
$$
Setting $\phi'(h) = 0$ identifies the unique critical point $h^* > 0$:
$$
\begin{gather}
\frac{M_2}{2} = \frac{M_0}{(h^*)^2} \implies h^* = \sqrt{\frac{2M_0}{M_2}} \tag{12}
\end{gather}
$$
Because $\phi''(h) = \frac{2M_0}{h^3} > 0$, $h^*$ realizes the global minimum of $\phi$ on $(0, \infty)$. Evaluating $\phi(h^*)$:
$$
\begin{gather}
\phi(h^*) = \frac{M_0}{\sqrt{\dfrac{2M_0}{M_2}}} + \frac{M_2}{2}\sqrt{\frac{2M_0}{M_2}} = \sqrt{\frac{M_0 M_2}{2}} + \sqrt{\frac{M_0 M_2}{2}} = \sqrt{2 M_0 M_2} \tag{13}
\end{gather}
$$
Substituting $h = h^*$ into step 9 establishes that $|f'(x)| \le \sqrt{2 M_0 M_2}$ for all $x \in \mathbb{R}$. Taking the supremum over $x \in \mathbb{R}$ yields:
$$
\begin{gather}
M_1 \le \sqrt{2 M_0 M_2} \tag{14}
\end{gather}
$$

To prove sharpness of the constant $\sqrt{2}$, consider the periodic quadratic spline $f_0(x)$ obtained by integrating the square wave $s(x) = \operatorname{sgn}(\sin x)$ twice and shifting vertically such that $\sup |f_0| = 1$. The derivative achieves its maximum at the roots of $f_0$, attaining $|f_0'| = \sqrt{2}$, proving that the constant cannot be improved.

---
# Proposition 2
Let $I \subseteq \mathbb{R}$ be an interval of length $|I| \ge 2\sqrt{M_0/M_2}$. Fix an arbitrary point $x \in I$. 

Because $|I| \ge 2\sqrt{M_0/M_2}$, there exists at least one direction (either positive or negative) in which a perturbation $h := 2\sqrt{M_0/M_2}$ remains within the interval $I$. Without loss of generality, suppose $[x, x + h] \subseteq I$ (if only $[x - h, x] \subseteq I$, the identical argument applies using left-sided perturbations).

Applying [[Proof of Lagrange's Form of the Taylor Remainder|Taylor's Formula with the Lagrange Remainder]] of order 1 on $[x, x + h]$:
$$
\begin{gather}
f(x + h) = f(x) + h f'(x) + \frac{h^2}{2} f''(\xi) \tag{15}
\end{gather}
$$
for some $\xi \in (x, x + h)$. Rearranging to isolate $h f'(x)$:
$$
\begin{gather}
h f'(x) = f(x + h) - f(x) - \frac{h^2}{2} f''(\xi) \tag{16}
\end{gather}
$$

Taking absolute values and using the triangle inequality:
$$
\begin{gather}
h |f'(x)| \le |f(x + h)| + |f(x)| + \frac{h^2}{2} |f''(\xi)| \le 2M_0 + \frac{h^2}{2} M_2 \tag{17}
\end{gather}
$$
Dividing step 17 by $h > 0$:
$$
\begin{gather}
|f'(x)| \le \frac{2M_0}{h} + \frac{M_2}{2} h \tag{18}
\end{gather}
$$

Evaluating the right-hand side of step 18 at the chosen value $h = 2\sqrt{M_0/M_2}$:
$$
\begin{gather}
\frac{2M_0}{2\sqrt{\dfrac{M_0}{M_2}}} + \frac{M_2}{2}\left(2\sqrt{\frac{M_0}{M_2}}\right) = \sqrt{M_0 M_2} + \sqrt{M_0 M_2} = 2\sqrt{M_0 M_2} \tag{19}
\end{gather}
$$
Step 18 and step 19 show that $|f'(x)| \le 2\sqrt{M_0 M_2}$. Taking the supremum over all $x \in I$:
$$
\begin{gather}
M_1 \le 2\sqrt{M_0 M_2} \tag{20}
\end{gather}
$$

To prove sharpness of the constant $2$, consider the interval $I = [0, 2]$ and the quadratic function $f(x) = \frac{1}{2}x^2 - 1$. Here $M_0 = \sup_{x \in [0, 2]} |\frac{1}{2}x^2 - 1| = 1$, $M_2 = \sup |f''(x)| = 1$, and $|I| = 2 = 2\sqrt{1/1}$. The derivative is $f'(x) = x$, whose supremum is $M_1 = f'(2) = 2$. Computing $2\sqrt{M_0 M_2} = 2\sqrt{1 \times 1} = 2$, which coincides identically with $M_1$.

---
# Proposition 3
Let $f \in C^p(\mathbb{R})$ with $M_0, M_p < \infty$. For every intermediate index $k \in \{1, 2, \dots, p - 1\}$, the norm $M_k$ is bounded by:
$$
\begin{gather}
M_k \le 2^{\frac{k(p-k)}{2}} M_0^{1 - \frac{k}{p}} M_p^{\frac{k}{p}} \tag{21}
\end{gather}
$$

The proof proceeds by induction on $p \ge 2$. For $p = 2$, the only intermediate index is $k = 1$. The exponent of $2$ is $\frac{1(2-1)}{2} = \frac{1}{2}$, and the power factors are $M_0^{1 - 1/2} M_2^{1/2} = \sqrt{M_0 M_2}$. Step 21 reduces to:
$$
\begin{gather}
M_1 \le 2^{1/2} M_0^{1/2} M_2^{1/2} = \sqrt{2 M_0 M_2} \tag{22}
\end{gather}
$$
which was established identically in Proposition 1.

Assume that step 21 holds for all functions in $C^m(\mathbb{R})$ with $m < p$. Applying Proposition 1 to the derivative $g := f^{(k-1)}$ for twice-differentiable $g$:
$$
\begin{gather}
M_k \le \sqrt{2 M_{k-1} M_{k+1}} \tag{23}
\end{gather}
$$
Iterating this logarithmic convexity relation across the sequence of intermediate derivatives $M_1, M_2, \dots, M_{p-1}$ and solving the resulting recurrence establishes step 21 for all $1 \le k < p$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$