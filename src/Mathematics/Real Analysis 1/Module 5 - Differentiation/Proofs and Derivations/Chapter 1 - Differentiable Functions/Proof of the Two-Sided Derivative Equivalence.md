---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $x_0$ be an interior point of $E$.

Because $x_0 \in \operatorname{int}(E)$, there exists an open radius $r > 0$ such that the open interval $(x_0 - r, x_0 + r)$ is entirely contained within $E$:
$$
\begin{gather}
(x_0 - r, x_0 + r) \subseteq E \tag{1}
\end{gather}
$$
Step 1 ensures that $x_0$ is simultaneously an accumulation point of $E \cap (x_0, \infty)$ from the right and an accumulation point of $E \cap (-\infty, x_0)$ from the left.

Define the difference quotient function $Q: (x_0 - r, x_0 + r) \setminus \{x_0\} \to \mathbb{R}$ by:
$$
\begin{gather}
Q(x) := \frac{f(x) - f(x_0)}{x - x_0} \tag{2}
\end{gather}
$$
By definition, the bilateral derivative and the one-sided derivatives correspond to the functional limits of $Q(x)$:
$$
\begin{gather}
f'(x_0) = \lim_{x \to x_0} Q(x), \qquad f'_+(x_0) = \lim_{x \to x_0^+} Q(x), \qquad f'_-(x_0) = \lim_{x \to x_0^-} Q(x) \tag{3}
\end{gather}
$$

**Necessity ($\implies$ Bilateral Derivative implies Equality of One-Sided Derivatives):**
Assume that the bilateral derivative $f'(x_0)$ exists as a finite real number $L \in \mathbb{R}$.

By the metric definition of a functional limit, for every tolerance $\varepsilon > 0$, there exists a corresponding distance $\delta \in (0, r)$ such that for all $x \in E$:
$$
\begin{gather}
0 < |x - x_0| < \delta \implies |Q(x) - L| < \varepsilon \tag{4}
\end{gather}
$$

Consider any point $x$ lying in the right-sided punctured interval $(x_0, x_0 + \delta)$. For such an $x$, the inequality $0 < x - x_0 < \delta$ holds, which implies that $0 < |x - x_0| < \delta$. Applying step 4 yields:
$$
\begin{gather}
|Q(x) - L| < \varepsilon \tag{5}
\end{gather}
$$
Because step 5 holds for all $x \in (x_0, x_0 + \delta)$, it follows that:
$$
\begin{gather}
f'_+(x_0) = \lim_{x \to x_0^+} Q(x) = L \tag{6}
\end{gather}
$$

Similarly, consider any point $x$ lying in the left-sided punctured interval $(x_0 - \delta, x_0)$. For such an $x$, the inequality $-\delta < x - x_0 < 0$ holds, which implies that $0 < |x - x_0| < \delta$. Applying step 4 yields:
$$
\begin{gather}
|Q(x) - L| < \varepsilon \tag{7}
\end{gather}
$$
Because step 7 holds for all $x \in (x_0 - \delta, x_0)$, it follows that:
$$
\begin{gather}
f'_-(x_0) = \lim_{x \to x_0^-} Q(x) = L \tag{8}
\end{gather}
$$

Combining step 6 and step 8 demonstrates that both one-sided derivatives exist and satisfy:
$$
\begin{gather}
f'_-(x_0) = f'_+(x_0) = L = f'(x_0) \tag{9}
\end{gather}
$$

**Sufficiency ($\impliedby$ Equality of One-Sided Derivatives implies Bilateral Derivative):**
Conversely, assume that both one-sided derivatives exist and are equal to a common real value $L \in \mathbb{R}$:
$$
\begin{gather}
f'_+(x_0) = L \quad \text{and} \quad f'_-(x_0) = L \tag{10}
\end{gather}
$$

Let $\varepsilon > 0$ be an arbitrary error tolerance. 

Because $\lim_{x \to x_0^+} Q(x) = L$, there exists a right-sided radius $\delta_1 \in (0, r)$ such that:
$$
\begin{gather}
x_0 < x < x_0 + \delta_1 \implies |Q(x) - L| < \varepsilon \tag{11}
\end{gather}
$$

Because $\lim_{x \to x_0^-} Q(x) = L$, there exists a left-sided radius $\delta_2 \in (0, r)$ such that:
$$
\begin{gather}
x_0 - \delta_2 < x < x_0 \implies |Q(x) - L| < \varepsilon \tag{12}
\end{gather}
$$

Define the symmetric radius by:
$$
\begin{gather}
\delta := \min(\delta_1, \delta_2) > 0 \tag{13}
\end{gather}
$$

Now let $x \in E$ be any point satisfying the bilateral punctured proximity condition $0 < |x - x_0| < \delta$. This condition partitions into two mutually exclusive spatial cases:
1. If $x > x_0$, then $x_0 < x < x_0 + \delta \le x_0 + \delta_1$. Applying step 11 yields $|Q(x) - L| < \varepsilon$.
2. If $x < x_0$, then $x_0 - \delta_2 \le x_0 - \delta < x < x_0$. Applying step 12 yields $|Q(x) - L| < \varepsilon$.

In both cases, the inequality $|Q(x) - L| < \varepsilon$ is satisfied. Consequently:
$$
\begin{gather}
\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(0 < |x - x_0| < \delta \implies |Q(x) - L| < \varepsilon\big) \tag{14}
\end{gather}
$$

Step 14 establishes that the bilateral limit exists:
$$
\begin{gather}
f'(x_0) = \lim_{x \to x_0} Q(x) = L \tag{15}
\end{gather}
$$
which confirms that $f'(x_0) \in \mathbb{R}$ and $f'(x_0) = f'_+(x_0) = f'_-(x_0)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$