---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be a non-empty subset of the real numbers, let $f: E \to \mathbb{R}$ be a real-valued function, and let $x_0 \in E$ be an interior extremum of $f$. Suppose further that $f$ is differentiable at $x_0$.

Because $x_0$ is an interior extremum of $f$ on $E$, there exists an open neighborhood $U(x_0) \subseteq \mathbb{R}$ such that $x_0$ is an extremum of $f$ relative to the trace neighborhood $U_E(x_0) := U(x_0) \cap E$. Furthermore, by the topological classification of interior extrema, $x_0$ is an accumulation point of both directional subsets:
$$
\begin{gather}
E^- := \{x \in E \mid x < x_0\} \quad \text{and} \quad E^+ := \{x \in E \mid x > x_0\} \tag{1}
\end{gather}
$$

Because $f$ is differentiable at $x_0$, the limit of the difference quotient exists as a finite real number:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{2}
\end{gather}
$$

By virtue of the [[Proof of the Two-Sided Derivative Equivalence|Two-Sided Derivative Equivalence]], the bilateral limit in step 2 entails that both one-sided directional limits exist along $E^+$ and $E^-$ and coincide identically with $f'(x_0)$:
$$
\begin{gather}
f'_+(x_0) = \lim_{E^+ \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{3}
\end{gather}
$$
$$
\begin{gather}
f'_-(x_0) = \lim_{E^- \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{4}
\end{gather}
$$

**Case 1: The point $x_0$ is a local maximum.**
Assume that $x_0$ is a local maximum of $f$. Shrinking the neighborhood $U(x_0)$ if necessary, the functional values satisfy:
$$
\begin{gather}
f(x) \le f(x_0), \quad \forall x \in U_E(x_0) \tag{5}
\end{gather}
$$
Step 5 implies that the functional increment is non-positive:
$$
\begin{gather}
f(x) - f(x_0) \le 0, \quad \forall x \in U_E(x_0) \tag{6}
\end{gather}
$$

Now consider points approaching $x_0$ strictly from the right, taking $x \in E^+ \cap U_E(x_0)$. For every such point, the displacement of the argument is strictly positive:
$$
\begin{gather}
x - x_0 > 0 \tag{7}
\end{gather}
$$
Dividing the non-positive numerator of step 6 by the strictly positive denominator of step 7 establishes:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} \le 0, \quad \forall x \in E^+ \cap U_E(x_0) \tag{8}
\end{gather}
$$

By the order properties of functional limits established in [[Chapter 2 - Limits of Functions|Module 3, Chapter 2]], taking the limit in step 8 as $E^+ \ni x \to x_0$ preserves the non-strict inequality:
$$
\begin{gather}
f'_+(x_0) = \lim_{E^+ \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \le 0 \tag{9}
\end{gather}
$$

Next, consider points approaching $x_0$ strictly from the left, taking $x \in E^- \cap U_E(x_0)$. For every such point, the displacement of the argument is strictly negative:
$$
\begin{gather}
x - x_0 < 0 \tag{10}
\end{gather}
$$
Dividing the non-positive numerator of step 6 by the strictly negative denominator of step 10 reverses the inequality sign:
$$
\begin{gather}
\frac{f(x) - f(x_0)}{x - x_0} \ge 0, \quad \forall x \in E^- \cap U_E(x_0) \tag{11}
\end{gather}
$$

Taking the limit in step 11 as $E^- \ni x \to x_0$ preserves the non-strict inequality:
$$
\begin{gather}
f'_-(x_0) = \lim_{E^- \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \ge 0 \tag{12}
\end{gather}
$$

Substituting the directional evaluations of step 9 and step 12 into the bilateral identities of step 3 and step 4 produces the simultaneous bounds:
$$
\begin{gather}
f'(x_0) \le 0 \quad \text{and} \quad f'(x_0) \ge 0 \tag{13}
\end{gather}
$$
The only real scalar satisfying both inequalities of step 13 is zero:
$$
\begin{gather}
f'(x_0) = 0 \tag{14}
\end{gather}
$$

**Case 2: The point $x_0$ is a local minimum.**
Assume that $x_0$ is a local minimum of $f$. Define the auxiliary mapping $g: E \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := -f(x), \quad \forall x \in E \tag{15}
\end{gather}
$$
Because $f(x) \ge f(x_0)$ for all $x \in U_E(x_0)$, multiplying by $-1$ reverses the inequality:
$$
\begin{gather}
g(x) = -f(x) \le -f(x_0) = g(x_0), \quad \forall x \in U_E(x_0) \tag{16}
\end{gather}
$$
Thus, $x_0$ is an interior local maximum for the auxiliary mapping $g$. 

By virtue of the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]], the function $g$ is differentiable at $x_0$ with derivative:
$$
\begin{gather}
g'(x_0) = -f'(x_0) \tag{17}
\end{gather}
$$
Applying the result of Case 1 to the function $g$ establishes that:
$$
\begin{gather}
g'(x_0) = 0 \tag{18}
\end{gather}
$$
Combining step 17 and step 18 yields $-f'(x_0) = 0$, which implies:
$$
\begin{gather}
f'(x_0) = 0 \tag{19}
\end{gather}
$$

Because any interior extremum is either a local maximum or a local minimum, step 14 and step 19 establish that $f'(x_0) = 0$ in all cases.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$