---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $f, g: X \to \mathbb{R}$. Assume that:
$$
\begin{gather}
\lim_{\mathcal{B}} f(x) = 0 \tag{1}
\end{gather}
$$
and that $g$ is ultimately bounded over $\mathcal{B}$, meaning there exist a real constant $M > 0$ and an element $B_1 \in \mathcal{B}$ such that:
$$
\begin{gather}
|g(x)| \le M \quad \forall x \in B_1 \tag{2}
\end{gather}
$$
Let $\varepsilon > 0$ be an arbitrary positive real number.

Because $M > 0$, the ratio $\frac{\varepsilon}{M} > 0$ is a valid error tolerance. By the definition of the limit applied to step 1, there exists an element $B_2 \in \mathcal{B}$ such that for all $x \in B_2$:
$$
\begin{gather}
|f(x) - 0| = |f(x)| < \frac{\varepsilon}{M} \tag{3}
\end{gather}
$$
By the directedness property of filter bases, there exists an element $B \in \mathcal{B}$ such that $B \subseteq B_1 \cap B_2$, with $B \neq \emptyset$.

For every point $x \in B$, combining the upper bounds of step 2 and step 3 yields:
$$
\begin{gather}
|(f \cdot g)(x) - 0| = |f(x) \cdot g(x)| = |f(x)| \cdot |g(x)| < \frac{\varepsilon}{M} \cdot M = \varepsilon \tag{4}
\end{gather}
$$
Because $\varepsilon > 0$ was chosen arbitrarily, step 4 demonstrates that:
$$
\begin{gather}
\lim_{\mathcal{B}} \big(f(x) \cdot g(x)\big) = 0
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$