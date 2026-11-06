---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E$. 

Suppose that $f$ is continuous at $a$ and that $f(a) \ne 0$. 

By definition of metric pointwise continuity, for every positive tolerance $\varepsilon > 0$, there exists a corresponding distance $\delta > 0$ such that:
$$
\begin{gather}
\forall x \in E, \quad |x - a| < \delta \implies |f(x) - f(a)| < \varepsilon \tag{1}
\end{gather}
$$

Because $f(a) \ne 0$, the absolute value $|f(a)|$ is strictly positive. Choose the explicit positive tolerance:
$$
\begin{gather}
\varepsilon_0 := \frac{|f(a)|}{2} > 0 \tag{2}
\end{gather}
$$

By step 1, there exists a distance $\delta_0 > 0$ such that for all $x \in E \cap (a - \delta_0, a + \delta_0)$:
$$
\begin{gather}
|f(x) - f(a)| < \frac{|f(a)|}{2} \tag{3}
\end{gather}
$$

**Case 1 ($f(a) > 0$):**
If $f(a) > 0$, then $|f(a)| = f(a)$, and step 3 expands to:
$$
\begin{gather}
-\frac{f(a)}{2} < f(x) - f(a) < \frac{f(a)}{2} \tag{4}
\end{gather}
$$

Adding $f(a)$ across the inequality of step 4:
$$
\begin{gather}
0 < \frac{f(a)}{2} < f(x) < \frac{3f(a)}{2} \tag{5}
\end{gather}
$$

Step 5 demonstrates that for all $x \in E \cap (a - \delta_0, a + \delta_0)$, $f(x) > 0 = \operatorname{sgn}(f(a))$ and $|f(x)| \ge \frac{f(a)}{2} > 0$.

**Case 2 ($f(a) < 0$):**
If $f(a) < 0$, then $|f(a)| = -f(a)$, and step 3 expands to:
$$
\begin{gather}
\frac{f(a)}{2} < f(x) - f(a) < -\frac{f(a)}{2} \tag{6}
\end{gather}
$$

Adding $f(a)$ across the inequality of step 6:
$$
\begin{gather}
\frac{3f(a)}{2} < f(x) < \frac{f(a)}{2} < 0 \tag{7}
\end{gather}
$$

Step 7 establishes that for all $x \in E \cap (a - \delta_0, a + \delta_0)$, $f(x) < 0 = \operatorname{sgn}(f(a))$ and $|f(x)| \ge \frac{|f(a)|}{2} > 0$.

In both cases, setting $c := \frac{|f(a)|}{2} > 0$ and $U(a) := (a - \delta_0, a + \delta_0)$ proves that:
$$
\begin{gather}
\forall x \in E \cap U(a), \quad \operatorname{sgn}(f(x)) = \operatorname{sgn}(f(a)) \quad \text{and} \quad |f(x)| \ge c > 0 \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
