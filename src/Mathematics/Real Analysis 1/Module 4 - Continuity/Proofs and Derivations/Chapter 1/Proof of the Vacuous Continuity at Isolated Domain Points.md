---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E \setminus E'$ be an isolated point of $E$.

By definition of an isolated point, $a$ is not an accumulation point of $E$ ($a \notin E'$). Consequently, there exists an open neighborhood $U(a)$ whose punctured intersection with $E$ is empty: $\mathring{U}(a) \cap E = \emptyset$. In metric terms, there exists a strictly positive isolation distance $\delta_0 > 0$ such that the open ball $B_{\delta_0}(a) = (a - \delta_0, a + \delta_0)$ contains no points of $E$ other than $a$:
$$
\begin{gather}
(a - \delta_0, a + \delta_0) \cap E = \{a\} \tag{1}
\end{gather}
$$

Let an arbitrary error tolerance $\varepsilon > 0$ be given. 

Set the control parameter:
$$
\begin{gather}
\delta := \delta_0 > 0 \tag{2}
\end{gather}
$$

Let $x \in E$ satisfy the metric neighborhood condition:
$$
\begin{gather}
|x - a| < \delta \tag{3}
\end{gather}
$$

The inequality of step 3 is equivalent to the statement that $x \in (a - \delta_0, a + \delta_0)$. Because $x \in E$, it follows from step 1 that:
$$
\begin{gather}
x \in (a - \delta_0, a + \delta_0) \cap E = \{a\} \implies x = a \tag{4}
\end{gather}
$$

Evaluating the deviation of functional values at $x = a$ yields:
$$
\begin{gather}
|f(x) - f(a)| = |f(a) - f(a)| = 0 < \varepsilon \tag{5}
\end{gather}
$$

Because the inequality $|f(x) - f(a)| < \varepsilon$ holds for all $x \in E$ satisfying $|x - a| < \delta$, and because $\varepsilon > 0$ was arbitrarily chosen, the metric continuity criterion is satisfied:
$$
\begin{gather}
\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon\big) \tag{6}
\end{gather}
$$

Consequently, $f$ is continuous at the isolated point $a$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$