---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a convex function on $(a, b)$.

Recall that for any four points $u < v < w < z$ in $(a, b)$, the chord slope function:
$$
\begin{gather}
S(x, y) := \frac{f(y) - f(x)}{y - x} \tag{1}
\end{gather}
$$
is non-decreasing in each argument independently.

---
# Proposition 1
Let $x \in (a, b)$ be an arbitrary point. For any $h > 0$ such that $x + h \in (a, b)$ and any $k > 0$ such that $x - k \in (a, b)$, the three-point chord ordering with $x - k < x < x + h$ yields:
$$
\begin{gather}
\frac{f(x) - f(x - k)}{k} \le \frac{f(x + h) - f(x)}{h} \tag{2}
\end{gather}
$$
The right difference quotient $\Delta_+(h) := \frac{f(x + h) - f(x)}{h}$ is a non-decreasing function of $h \in (0, b - x)$. Furthermore, by step 2, $\Delta_+(h)$ is bounded from below by the fixed real scalar $\frac{f(x) - f(x - k)}{k}$. By the monotone convergence theorem for functions, the infimum and limit as $h \to 0^+$ exists as a finite real number:
$$
\begin{gather}
f'_+(x) = \lim_{h \to 0^+} \frac{f(x + h) - f(x)}{h} = \inf_{h > 0} \frac{f(x + h) - f(x)}{h} \tag{3}
\end{gather}
$$

Similarly, the left difference quotient $\Delta_-(k) := \frac{f(x) - f(x - k)}{k}$ is a non-decreasing function of $k > 0$ (so it is non-increasing as $k \to 0^+$). By step 2, $\Delta_-(k)$ is bounded from above by $\frac{f(x + h) - f(x)}{h}$. Therefore, the supremum and limit as $k \to 0^+$ exists as a finite real number:
$$
\begin{gather}
f'_-(x) = \lim_{k \to 0^+} \frac{f(x) - f(x - k)}{k} = \sup_{k > 0} \frac{f(x) - f(x - k)}{k} \tag{4}
\end{gather}
$$

Taking the limit in step 2 as $k \to 0^+$ and $h \to 0^+$ preserves the inequality:
$$
\begin{gather}
f'_-(x) \le f'_+(x) \tag{5}
\end{gather}
$$
proving that both unilateral derivatives exist as finite real numbers and satisfy step 5 at every point $x \in (a, b)$.

---
# Proposition 2
Let $x_1, x_2 \in (a, b)$ with $x_1 < x_2$. Choose $h > 0$ and $k > 0$ sufficiently small such that $x_1 - k < x_1 < x_1 + h < x_2 - k < x_2 < x_2 + h$.

The chord slope monotonicity across the ordered sequence $x_1 - k < x_1 < x_1 + h < x_2 < x_2 + h$ entails:
$$
\begin{gather}
\frac{f(x_1) - f(x_1 - k)}{k} \le \frac{f(x_1 + h) - f(x_1)}{h} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x_2) - f(x_2 - k)}{k} \le \frac{f(x_2 + h) - f(x_2)}{h} \tag{6}
\end{gather}
$$
Taking the limits as $k \to 0^+$ and $h \to 0^+$ across each corresponding term in step 6 and applying the unilateral representations of step 3 and step 4 yields:
$$
\begin{gather}
f'_-(x_1) \le f'_+(x_1) \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le f'_-(x_2) \le f'_+(x_2) \tag{7}
\end{gather}
$$
Step 7 proves the fundamental chaining of directional derivative rates between any two distinct points in the interval.

---
# Proposition 3
A function $f$ fails to be differentiable at a point $x \in (a, b)$ if and only if the bilateral derivative limit does not exist, which for convex functions occurs precisely when the unilateral derivatives disagree:
$$
\begin{gather}
f'_-(x) < f'_+(x) \tag{8}
\end{gather}
$$
Define the set of non-differentiable angular singular points:
$$
\begin{gather}
S := \{x \in (a, b) \mid f'_-(x) < f'_+(x)\} \tag{9}
\end{gather}
$$

For each singular point $x \in S$, define the open interval of missing slope values:
$$
\begin{gather}
J_x := \big(f'_-(x), f'_+(x)\big) \subset \mathbb{R} \tag{10}
\end{gather}
$$
Because $f'_-(x) < f'_+(x)$, the interval $J_x$ is non-empty.

Now consider two distinct points $x_1, x_2 \in S$ with $x_1 < x_2$. By Proposition 2:
$$
\begin{gather}
f'_+(x_1) \le f'_-(x_2) \tag{11}
\end{gather}
$$
Step 11 implies that every point $t_1 \in J_{x_1} = (f'_-(x_1), f'_+(x_1))$ and every point $t_2 \in J_{x_2} = (f'_-(x_2), f'_+(x_2))$ satisfy:
$$
\begin{gather}
t_1 < f'_+(x_1) \le f'_-(x_2) < t_2 \implies t_1 < t_2 \tag{12}
\end{gather}
$$
Consequently, the open intervals $J_{x_1}$ and $J_{x_2}$ are completely disjoint:
$$
\begin{gather}
J_{x_1} \cap J_{x_2} = \emptyset, \quad \forall x_1 \neq x_2 \in S \tag{13}
\end{gather}
$$

The collection $\{J_x\}_{x \in S}$ forms a family of pairwise disjoint non-empty open subintervals of $\mathbb{R}$. By the density of the rational numbers $\mathbb{Q}$ in $\mathbb{R}$, each non-empty open interval $J_x$ contains at least one rational number $q_x \in \mathbb{Q} \cap J_x$.

Because the intervals are pairwise disjoint, the mapping $x \mapsto q_x$ is an injection from $S$ into $\mathbb{Q}$:
$$
\begin{gather}
x_1 \neq x_2 \implies q_{x_1} \neq q_{x_2} \tag{14}
\end{gather}
$$
Because $\mathbb{Q}$ is countable, the existence of an injective mapping from $S$ into $\mathbb{Q}$ demonstrates that the set of singular points $S$ is at most countable.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
