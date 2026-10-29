---
dg-publish: true
---
Let $\mathcal{B}_X$ be a filter base in $X$, let $\mathcal{B}_Y$ be a filter base in $Y$, and let $f: X \to Y$ and $g: Y \to \mathbb{R}$.

Assume that for every base element $B_Y \in \mathcal{B}_Y$, there exists a base element $B_X \in \mathcal{B}_X$ such that:
$$
\begin{gather}
f(B_X) \subseteq B_Y \tag{1}
\end{gather}
$$
Assume further that $g$ possesses a finite limit over the base $\mathcal{B}_Y$:
$$
\begin{gather}
\lim_{\mathcal{B}_Y} g(y) = c \in \mathbb{R} \tag{2}
\end{gather}
$$
Let $\varepsilon > 0$ be an arbitrary positive real error tolerance.

By definition of the limit over a base applied to step 2, there exists an element $B_Y^* \in \mathcal{B}_Y$ such that for all $y \in B_Y^*$:
$$
\begin{gather}
|g(y) - c| < \varepsilon \iff g(B_Y^*) \subseteq (c - \varepsilon, c + \varepsilon) \tag{3}
\end{gather}
$$
By virtue of the structural base-mapping hypothesis in step 1, corresponding to this specific base element $B_Y^* \in \mathcal{B}_Y$, there exists an element $B_X^* \in \mathcal{B}_X$ satisfying:
$$
\begin{gather}
f(B_X^*) \subseteq B_Y^* \tag{4}
\end{gather}
$$
Applying the mapping $g$ across the set containment in step 4 and incorporating step 3 yields:
$$
\begin{gather}
(g \circ f)(B_X^*) = g(f(B_X^*)) \subseteq g(B_Y^*) \subseteq (c - \varepsilon, c + \varepsilon) \tag{5}
\end{gather}
$$
Step 5 demonstrates that for all $x \in B_X^*$:
$$
\begin{gather}
|(g \circ f)(x) - c| < \varepsilon \tag{6}
\end{gather}
$$
Because $B_X^* \in \mathcal{B}_X$ and $\varepsilon > 0$ was chosen arbitrarily, step 6 satisfies the definition of the functional limit over the base $\mathcal{B}_X$, establishing that:
$$
\begin{gather}
\lim_{\mathcal{B}_X} (g \circ f)(x) = c = \lim_{\mathcal{B}_Y} g(y)
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$