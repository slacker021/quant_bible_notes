---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be defined on an interval $I$, and let $x_0 \in \text{int}(I)$.

### Part 1: The First Derivative Test
Suppose there exists $\delta > 0$ such that $f'(x) \ge 0$ for all $x \in (x_0 - \delta, x_0)$ and $f'(x) \le 0$ for all $x \in (x_0, x_0 + \delta)$.

Let $x \in (x_0 - \delta, x_0)$. By Theorem 3.4 (Lagrange's Mean Value Theorem) applied to $f$ on $[x, x_0]$, there exists $\xi \in (x, x_0)$ such that:
$$
\begin{gather}
f(x_0) - f(x) = f'(\xi)(x_0 - x) \tag{1}
\end{gather}
$$

Because $\xi \in (x_0 - \delta, x_0)$, $f'(\xi) \ge 0$. Because $x < x_0$, $x_0 - x > 0$. Therefore:
$$
\begin{gather}
f(x_0) - f(x) \ge 0 \implies f(x) \le f(x_0) \tag{2}
\end{gather}
$$

Now let $x \in (x_0, x_0 + \delta)$. Applying Lagrange's Mean Value Theorem on $[x_0, x]$, there exists $\eta \in (x_0, x)$ such that:
$$
\begin{gather}
f(x) - f(x_0) = f'(\eta)(x - x_0) \tag{3}
\end{gather}
$$

Because $\eta \in (x_0, x_0 + \delta)$, $f'(\eta) \le 0$. Because $x - x_0 > 0$:
$$
\begin{gather}
f(x) - f(x_0) \le 0 \implies f(x) \le f(x_0) \tag{4}
\end{gather}
$$

Combining inequalities (2) and (4) proves that $f(x) \le f(x_0)$ for all $x \in (x_0 - \delta, x_0 + \delta)$, establishing that $x_0$ is a local maximum. (The proof for local minimum with signs reversed is identical).

### Part 2: The Higher-Order Derivative Test
Suppose $f \in C^n(U(x_0))$ with $f'(x_0) = \dots = f^{(n-1)}(x_0) = 0$ and $f^{(n)}(x_0) \neq 0$.

By Theorem 3.10 (Taylor's Theorem with the Peano Remainder), for $x \in U(x_0)$:
$$
\begin{gather}
f(x) - f(x_0) = \sum_{k=1}^{n-1} \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n + o((x - x_0)^n) \tag{5}
\end{gather}
$$

Because all lower derivatives vanish:
$$
\begin{gather}
f(x) - f(x_0) = \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n + \alpha(x)(x - x_0)^n = \left( \frac{f^{(n)}(x_0)}{n!} + \alpha(x) \right)(x - x_0)^n \tag{6}
\end{gather}
$$
where $\lim_{x \to x_0} \alpha(x) = 0$.

Because $\frac{f^{(n)}(x_0)}{n!} \neq 0$, by sign preservation of limits there exists $\delta > 0$ such that for all $x \in \mathring{U}_\delta(x_0)$:
$$
\begin{gather}
\operatorname{sgn}\left( \frac{f^{(n)}(x_0)}{n!} + \alpha(x) \right) = \operatorname{sgn}\big( f^{(n)}(x_0) \big) \tag{7}
\end{gather}
$$

**Case A ($n$ is even):**
For any $x \neq x_0$, $(x - x_0)^n > 0$. Therefore, for all $x \in \mathring{U}_\delta(x_0)$:
$$
\begin{gather}
\operatorname{sgn}\big( f(x) - f(x_0) \big) = \operatorname{sgn}\big( f^{(n)}(x_0) \big) \tag{8}
\end{gather}
$$
- If $f^{(n)}(x_0) < 0$, then $f(x) - f(x_0) < 0 \implies f(x) < f(x_0)$ (strict local maximum).
- If $f^{(n)}(x_0) > 0$, then $f(x) - f(x_0) > 0 \implies f(x) > f(x_0)$ (strict local minimum).

**Case B ($n$ is odd):**
The term $(x - x_0)^n$ changes sign across $x_0$: it is positive for $x > x_0$ and negative for $x < x_0$. Therefore, $f(x) - f(x_0)$ takes strictly opposite signs on either side of $x_0$. Consequently, $x_0$ cannot be a local extremum.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
