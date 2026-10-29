---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $a \in E'$, and let $f, g: E \to \mathbb{R}$. Assume that:
$$\begin{gather} \lim_{x \to a} f(x) = c > 0 \tag{1} \end{gather}$$
and:
$$\begin{gather} \lim_{x \to a} g(x) = 0 \quad \text{with} \quad g(x) > 0 \ \ \forall x \in \mathring{U}_{\delta_0}(a) \cap E \tag{2} \end{gather}$$
for some initial radius $\delta_0 > 0$.

Let $M > 0$ be an arbitrary positive real number.

Instantiating the definition of the functional limit for $f$ with the error tolerance $\varepsilon_1 := \frac{c}{2} > 0$ guarantees the existence of a radius $\delta_1 > 0$ such that for all $x \in E$:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta_1 \implies \vert{}f(x) - c\vert{} < \frac{c}{2} \implies f(x) > c - \frac{c}{2} = \frac{c}{2} > 0 \tag{3} \end{gather}$$
Next, consider the positive quantity $\varepsilon_2 := \frac{c}{2M} > 0$. Because $\lim_{x \to a} g(x) = 0$, there exists a radius $\delta_2 > 0$ such that for all $x \in E$:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta_2 \implies \vert{}g(x)\vert{} < \frac{c}{2M} \tag{4} \end{gather}$$
Define the unified radius:
$$\begin{gather} \delta := \min(\delta_0, \delta_1, \delta_2) > 0 \tag{5} \end{gather}$$
Let $x \in E$ satisfy $0 < \vert{}x - a\vert{} < \delta$. Because $\delta \le \delta_0$, step 2 dictates that $g(x) > 0$, meaning $\vert{}g(x)\vert{} = g(x)$. Because $\delta \le \delta_2$, step 4 establishes that:
$$\begin{gather} 0 < g(x) < \frac{c}{2M} \iff \frac{1}{g(x)} > \frac{2M}{c} > 0 \tag{6} \end{gather}$$
Concurrently, because $\delta \le \delta_1$, step 3 establishes that $f(x) > \frac{c}{2} > 0$. Multiplying the inequalities of step 3 and step 6 preserves the order:
$$\begin{gather} \frac{f(x)}{g(x)} = f(x) \cdot \frac{1}{g(x)} > \frac{c}{2} \cdot \frac{2M}{c} = M \tag{7} \end{gather}$$
Because $M > 0$ was chosen arbitrarily, step 7 proves that for every $M \in \mathbb{R}$, there exists $\delta > 0$ such that $0 < \vert{}x - a\vert{} < \delta \implies \frac{f(x)}{g(x)} > M$. Thus:
$$\begin{gather} \lim_{x \to a} \frac{f(x)}{g(x)} = +\infty \end{gather}$$
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$
