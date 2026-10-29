---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $a \in E'$ be an accumulation point of $E$, and let $f, g: E \to \mathbb{R}$ be two real-valued functions. Assume there exists a positive radius $\delta_0 > 0$ such that:
$$\begin{gather} f(x) = g(x) \quad \forall x \in \mathring{U}_{\delta_0}(a) \cap E \tag{1} \end{gather}$$
where $\mathring{U}_{\delta_0}(a) = (a - \delta_0, a + \delta_0) \setminus \{a\}$.

Assume that the functional limit of $g$ exists as $x$ tends to $a$ within $E$, denoted:
$$\begin{gather} \lim_{E \ni x \to a} g(x) = L \in \mathbb{R} \tag{2} \end{gather}$$
Let $\varepsilon > 0$ be an arbitrary positive real number. By the definition of a functional limit applied to step 2, there exists a distance $\delta_1 > 0$ such that for all $x \in E$:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta_1 \implies \vert{}g(x) - L\vert{} < \varepsilon \tag{3} \end{gather}$$
Define the composite distance parameter:
$$\begin{gather} \delta := \min(\delta_0, \delta_1) > 0 \tag{4} \end{gather}$$
Let $x \in E$ satisfy the constraint $0 < \vert{}x - a\vert{} < \delta$. Because $\delta \le \delta_0$, the point $x$ belongs to the punctured neighborhood $\mathring{U}_{\delta_0}(a) \cap E$. By virtue of step 1, the functional equality holds:
$$\begin{gather} f(x) = g(x) \tag{5} \end{gather}$$
Concurrently, because $\delta \le \delta_1$, the point $x$ satisfies the antecedent of step 3, establishing that:
$$\begin{gather} \vert{}f(x) - L\vert{} = \vert{}g(x) - L\vert{} < \varepsilon \tag{6} \end{gather}$$
Because $\varepsilon > 0$ was chosen arbitrarily, step 6 proves that $\lim_{E \ni x \to a} f(x) = L$. 

By reversing the symmetric roles of $f$ and $g$, the existence of $\lim_{E \ni x \to a} f(x)$ implies that $\lim_{E \ni x \to a} g(x)$ exists and equals the identical value.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$
