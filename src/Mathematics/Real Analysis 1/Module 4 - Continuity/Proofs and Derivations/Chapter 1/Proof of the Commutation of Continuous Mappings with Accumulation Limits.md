---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E \cap E'$. Because $a \in E'$, every punctured neighborhood of $a$ contains points of $E$.

**Necessity ($\implies$ Continuity implies the Limit Identity):**
Assume that the mapping $f$ is continuous at the point $a$.

By the metric definition of pointwise continuity, for every positive error tolerance $\varepsilon > 0$, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon \tag{1}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given, and let $\delta > 0$ be the distance guaranteed by step 1. 

Consider any point $x \in E$ satisfying the punctured metric inequality:
$$
\begin{gather}
0 < |x - a| < \delta \tag{2}
\end{gather}
$$

Because $0 < |x - a| < \delta$ immediately implies the unpunctured condition $|x - a| < \delta$, it follows directly from step 1 that:
$$
\begin{gather}
|f(x) - f(a)| < \varepsilon \tag{3}
\end{gather}
$$

Because $a \in E'$, the intersection $E \cap ((a - \delta, a + \delta) \setminus \{a\})$ is non-empty for every $\delta > 0$. Hence, the condition of step 3 demonstrates that the functional limit exists and coincides with $f(a)$:
$$
\begin{gather}
\lim_{E \ni x \to a} f(x) = f(a) \tag{4}
\end{gather}
$$

**Sufficiency ($\impliedby$ The Limit Identity implies Continuity):**
Conversely, assume that the functional limit of $f$ exists at the accumulation point $a$ and equals $f(a)$:
$$
\begin{gather}
\lim_{E \ni x \to a} f(x) = f(a) \tag{5}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given. 

By the definition of a functional limit at an accumulation point, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
0 < |x - a| < \delta \implies |f(x) - f(a)| < \varepsilon \tag{6}
\end{gather}
$$

Now let $x \in E$ satisfy the unpunctured metric bound:
$$
\begin{gather}
|x - a| < \delta \tag{7}
\end{gather}
$$

There are two mutually exclusive and exhaustive cases to examine:
* If $x \neq a$, then $0 < |x - a| < \delta$. Applying step 6 yields $|f(x) - f(a)| < \varepsilon$.
* If $x = a$, then $|f(x) - f(a)| = |f(a) - f(a)| = 0 < \varepsilon$.

In both cases, the inequality $|f(x) - f(a)| < \varepsilon$ holds whenever $x \in E$ satisfies $|x - a| < \delta$. 

Because $\varepsilon > 0$ was chosen arbitrarily, the metric continuity condition is satisfied at $a$:
$$
\begin{gather}
\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon\big) \tag{8}
\end{gather}
$$

Consequently, $f$ is continuous at $a$.

**Commutation of Continuous Mappings:**
Because the identity mapping $\operatorname{id}_E: E \to \mathbb{R}$ defined by $\operatorname{id}_E(x) = x$ directly satisfies:
$$
\begin{gather}
\lim_{E \ni x \to a} x = a \tag{9}
\end{gather}
$$
substituting the limit of step 9 directly into the argument of $f(a)$ transforms the equality of step 4 into the operator commutation law:
$$
\begin{gather}
\lim_{E \ni x \to a} f(x) = f\left(\lim_{E \ni x \to a} x\right) \tag{10}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$