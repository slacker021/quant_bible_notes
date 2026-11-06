---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ and let $f: E \to \mathbb{R}$. Suppose $a$ is an interior point of $E$, so there exists a parameter $\eta > 0$ such that:
$$
\begin{gather}
(a - \eta, a + \eta) \subseteq E \tag{1}
\end{gather}
$$

Because the interval of step 1 is a subset of $E$, the point $a$ is an accumulation point of $E$, and is also an accumulation point of both the left-hand trace $E \cap (-\infty, a]$ and the right-hand trace $E \cap [a, +\infty)$.

**Necessity ($\implies$ Two-Sided Continuity implies Directional Continuity):**
Assume that the function $f$ is continuous at $a$. 

By definition of metric pointwise continuity, for every positive tolerance $\varepsilon > 0$, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon \tag{2}
\end{gather}
$$

Let $\varepsilon > 0$ be given, and let $\delta > 0$ be the control distance from step 2. Define the refined distance:
$$
\begin{gather}
\delta_0 := \min(\delta, \eta) > 0 \tag{3}
\end{gather}
$$

For any $x \in E$ satisfying the left-hand directional condition $a - \delta_0 < x \le a$:
$$
\begin{gather}
|x - a| = a - x < \delta_0 \le \delta \tag{4}
\end{gather}
$$
Applying step 2 to step 4 demonstrates that $|f(x) - f(a)| < \varepsilon$. This verifies the left-continuity condition:
$$
\begin{gather}
\lim_{x \to a^-} f(x) = f(a) \tag{5}
\end{gather}
$$

Similarly, for any $x \in E$ satisfying the right-hand directional condition $a \le x < a + \delta_0$:
$$
\begin{gather}
|x - a| = x - a < \delta_0 \le \delta \tag{6}
\end{gather}
$$
Applying step 2 to step 6 establishes that $|f(x) - f(a)| < \varepsilon$. This verifies the right-continuity condition:
$$
\begin{gather}
\lim_{x \to a^+} f(x) = f(a) \tag{7}
\end{gather}
$$

Combining step 5 and step 7 demonstrates that $f$ is simultaneously left-continuous and right-continuous at $a$.

**Sufficiency ($\impliedby$ Directional Continuity implies Two-Sided Continuity):**
Conversely, assume that $f$ is simultaneously left-continuous and right-continuous at $a$:
$$
\begin{gather}
\lim_{x \to a^-} f(x) = f(a) \quad \text{and} \quad \lim_{x \to a^+} f(x) = f(a) \tag{8}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given. 

By the definition of left-continuity at $a$, there exists a distance $\delta_1 > 0$ such that for all $x \in E$:
$$
\begin{gather}
a - \delta_1 < x \le a \implies |f(x) - f(a)| < \varepsilon \tag{9}
\end{gather}
$$

By the definition of right-continuity at $a$, there exists a distance $\delta_2 > 0$ such that for all $x \in E$:
$$
\begin{gather}
a \le x < a + \delta_2 \implies |f(x) - f(a)| < \varepsilon \tag{10}
\end{gather}
$$

Define the unified symmetric distance:
$$
\begin{gather}
\delta := \min(\delta_1, \delta_2, \eta) > 0 \tag{11}
\end{gather}
$$

Let $x \in E$ satisfy the two-sided metric condition:
$$
\begin{gather}
|x - a| < \delta \iff a - \delta < x < a + \delta \tag{12}
\end{gather}
$$

Every element satisfying step 12 belongs to one of two overlapping intervals:
* If $a - \delta < x \le a$, then because $\delta \le \delta_1$ by step 11, the inequality $a - \delta_1 < x \le a$ holds. Applying step 9 guarantees that $|f(x) - f(a)| < \varepsilon$.
* If $a \le x < a + \delta$, then because $\delta \le \delta_2$ by step 11, the inequality $a \le x < a + \delta_2$ holds. Applying step 10 guarantees that $|f(x) - f(a)| < \varepsilon$.

In both cases, $|f(x) - f(a)| < \varepsilon$ whenever $x \in E$ satisfies $|x - a| < \delta$. Because $\varepsilon > 0$ was arbitrary, $f$ is continuous at $a$. 

This equivalence is consistent with the [[Proof of the Equivalence of Two-Sided and One-Sided Limits]] previously established for functional limits.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$