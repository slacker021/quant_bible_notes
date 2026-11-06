---
dg-publish: true
---
Let $f: E \to \mathbb{R}$, and let $a \in \mathbb{R}$ be an accumulation point of both $E \cap (-\infty, a)$ and $E \cap (a, +\infty)$. Let $A \in \mathbb{R}$.

**Necessity ($\implies$):**
Assume that the two-sided limit exists and satisfies $\lim_{x \to a} f(x) = A$.

Let $\varepsilon > 0$ be given. By definition of the two-sided limit, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta \implies \vert{}f(x) - A\vert{} < \varepsilon \tag{1} \end{gather}$$
The punctured neighborhood condition $0 < \vert{}x - a\vert{} < \delta$ is equivalent to the disjoint union:
$$\begin{gather} x \in (a - \delta, a) \cup (a, a + \delta) \tag{2} \end{gather}$$
If $x \in E$ satisfies $a - \delta < x < a$, then $x$ satisfies step 2, so by step 1, $\vert{}f(x) - A\vert{} < \varepsilon$. This proves that $\lim_{x \to a^-} f(x) = A$.

Similarly, if $x \in E$ satisfies $a < x < a + \delta$, then $x$ satisfies step 2, so by step 1, $\vert{}f(x) - A\vert{} < \varepsilon$. This proves that $\lim_{x \to a^+} f(x) = A$.

**Sufficiency ($\impliedby$):**
Conversely, assume that both one-sided limits exist and satisfy:
$$\begin{gather} \lim_{x \to a^-} f(x) = A \quad \text{and} \quad \lim_{x \to a^+} f(x) = A \tag{3} \end{gather}$$
Let $\varepsilon > 0$ be given. 

By definition of the left-hand limit, there exists a distance $\delta_1 > 0$ such that for all $x \in E$:
$$\begin{gather} a - \delta_1 < x < a \implies \vert{}f(x) - A\vert{} < \varepsilon \tag{4} \end{gather}$$
By definition of the right-hand limit, there exists a distance $\delta_2 > 0$ such that for all $x \in E$:
$$\begin{gather} a < x < a + \delta_2 \implies \vert{}f(x) - A\vert{} < \varepsilon \tag{5} \end{gather}$$
Define the unified symmetric distance:
$$\begin{gather} \delta := \min(\delta_1, \delta_2) > 0 \tag{6} \end{gather}$$
Let $x \in E$ satisfy $0 < \vert{}x - a\vert{} < \delta$. Then either $a - \delta < x < a$ or $a < x < a + \delta$:
* If $a - \delta < x < a$, then because $\delta \le \delta_1$, step 4 guarantees that $\vert{}f(x) - A\vert{} < \varepsilon$.
* If $a < x < a + \delta$, then because $\delta \le \delta_2$, step 5 guarantees that $\vert{}f(x) - A\vert{} < \varepsilon$.

In both cases, $\vert{}f(x) - A\vert{} < \varepsilon$ holds whenever $0 < \vert{}x - a\vert{} < \delta$. Consequently, $\lim_{x \to a} f(x) = A$.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$
