---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be a real-valued function differentiable at every point of the closed interval $[a, b]$ with $a < b$. Suppose that the endpoint derivatives are unequal:
$$
\begin{gather}
f'(a) \neq f'(b) \tag{1}
\end{gather}
$$
and let $\gamma \in \mathbb{R}$ be an arbitrary real scalar lying strictly between $f'(a)$ and $f'(b)$.

Without loss of generality, assume that:
$$
\begin{gather}
f'(a) < \gamma < f'(b) \tag{2}
\end{gather}
$$
If instead $f'(a) > \gamma > f'(b)$, the identical reasoning applies to the negated function $\widetilde{f}(x) := -f(x)$ with target value $-\gamma$, since $(-f)'(a) = -f'(a) < -\gamma < -f'(b) = (-f)'(b)$.

Define the auxiliary mapping $g: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := f(x) - \gamma x, \quad \forall x \in [a, b] \tag{3}
\end{gather}
$$

Because $f$ is differentiable on $[a, b]$, it follows from [[Proof that Differentiability Implies Continuity|Differentiability Implies Continuity]] that $f$ is continuous on $[a, b]$. The linear term $x \mapsto \gamma x$ is continuous on $[a, b]$. Consequently, the difference $g$ is continuous on the compact interval $[a, b]$.

By virtue of the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem]], the continuous function $g$ attains its global minimum on $[a, b]$ at some point $\xi \in [a, b]$:
$$
\begin{gather}
g(\xi) = \inf_{x \in [a, b]} g(x) \le g(x), \quad \forall x \in [a, b] \tag{4}
\end{gather}
$$

To determine the location of $\xi$, evaluate the derivative of $g$ at the boundaries using the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]]:
$$
\begin{gather}
g'(x) = f'(x) - \gamma, \quad \forall x \in [a, b] \tag{5}
\end{gather}
$$

**Exclusion of the Left Boundary ($x = a$):**
Evaluating step 5 at $x = a$ and utilizing the ordering of step 2 gives:
$$
\begin{gather}
g'(a) = f'(a) - \gamma < 0 \tag{6}
\end{gather}
$$
By definition of the right-sided derivative:
$$
\begin{gather}
g'_+(a) = \lim_{x \to a^+} \frac{g(x) - g(a)}{x - a} = g'(a) < 0 \tag{7}
\end{gather}
$$
By the sign-preservation property of limits established in [[Chapter 2 - Limits of Functions|Module 3, Chapter 2]], there exists a radius $\delta_1 > 0$ such that for all $x \in (a, a + \delta_1) \cap [a, b]$:
$$
\begin{gather}
\frac{g(x) - g(a)}{x - a} < 0 \tag{8}
\end{gather}
$$
Because $x > a$, the denominator is strictly positive: $x - a > 0$. Multiplying step 8 by $(x - a)$ yields:
$$
\begin{gather}
g(x) - g(a) < 0 \implies g(x) < g(a) \tag{9}
\end{gather}
$$
Step 9 proves that the value $g(a)$ cannot be the global minimum of $g$ on $[a, b]$. Therefore:
$$
\begin{gather}
\xi \neq a \tag{10}
\end{gather}
$$

**Exclusion of the Right Boundary ($x = b$):**
Evaluating step 5 at $x = b$ and utilizing the ordering of step 2 gives:
$$
\begin{gather}
g'(b) = f'(b) - \gamma > 0 \tag{11}
\end{gather}
$$
By definition of the left-sided derivative:
$$
\begin{gather}
g'_-(b) = \lim_{x \to b^-} \frac{g(x) - g(b)}{x - b} = g'(b) > 0 \tag{12}
\end{gather}
$$
By sign-preservation, there exists a radius $\delta_2 > 0$ such that for all $x \in (b - \delta_2, b) \cap [a, b]$:
$$
\begin{gather}
\frac{g(x) - g(b)}{x - b} > 0 \tag{13}
\end{gather}
$$
Because $x < b$, the denominator is strictly negative: $x - b < 0$. Multiplying step 13 by the negative term $(x - b)$ reverses the inequality:
$$
\begin{gather}
g(x) - g(b) < 0 \implies g(x) < g(b) \tag{14}
\end{gather}
$$
Step 14 proves that the value $g(b)$ cannot be the global minimum of $g$ on $[a, b]$. Therefore:
$$
\begin{gather}
\xi \neq b \tag{15}
\end{gather}
$$

Combining step 10 and step 15 establishes that the global minimum is attained strictly at an interior point:
$$
\begin{gather}
\xi \in (a, b) \tag{16}
\end{gather}
$$

Because $\xi$ is an interior extremum of $g$ on $[a, b]$ and $g$ is differentiable at $\xi$, [[Proof of Fermat's Interior Extremum Lemma|Fermat's Interior Extremum Lemma]] forces the derivative to vanish:
$$
\begin{gather}
g'(\xi) = 0 \tag{17}
\end{gather}
$$
Substituting step 5 into step 17 yields:
$$
\begin{gather}
f'(\xi) - \gamma = 0 \implies f'(\xi) = \gamma \tag{18}
\end{gather}
$$
with $\xi \in (a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$