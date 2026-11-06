---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E$. 

Suppose $f$ is continuous at $a$. By the metric formulation of pointwise continuity, for every positive tolerance $\varepsilon > 0$, there exists a corresponding distance $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon \tag{1}
\end{gather}
$$

Fix the specific tolerance choice $\varepsilon_0 = 1 > 0$. By step 1, there exists a distance $\delta_0 > 0$ such that:
$$
\begin{gather}
\forall x \in E \cap (a - \delta_0, a + \delta_0) \implies |f(x) - f(a)| < 1 \tag{2}
\end{gather}
$$

Applying the reverse triangle inequality to the functional difference in step 2:
$$
\begin{gather}
|f(x)| - |f(a)| \le |f(x) - f(a)| < 1 \tag{3}
\end{gather}
$$

Rearranging the inequality of step 3 yields an explicit upper bound for the absolute functional value:
$$
\begin{gather}
|f(x)| < |f(a)| + 1 \tag{4}
\end{gather}
$$

Define the real constant:
$$
\begin{gather}
M := |f(a)| + 1 > 0 \tag{5}
\end{gather}
$$

Because $f(a) \in \mathbb{R}$, the value $M$ defined in step 5 is a strictly positive, finite real number. 

Consequently, for every element $x \in E \cap (a - \delta_0, a + \delta_0)$, the relation $|f(x)| \le M$ holds. 

This proves that $f$ is bounded on the relative neighborhood $U_E(a) := E \cap (a - \delta_0, a + \delta_0)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
