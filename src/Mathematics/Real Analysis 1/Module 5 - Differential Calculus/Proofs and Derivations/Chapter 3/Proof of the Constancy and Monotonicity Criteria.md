---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be continuous on an interval $I \subseteq \mathbb{R}$ and differentiable on $\text{int}(I)$.

### Part 1: Constancy Criterion
**Direct Implication ($\implies$):**
Suppose $f'(x) = 0$ for all $x \in \text{int}(I)$. Fix an arbitrary reference point $x_0 \in I$. 
For any other point $x \in I$ with $x \neq x_0$, the closed interval with endpoints $x_0$ and $x$ is contained in $I$ because $I$ is an interval. 

Applying Lagrange's Mean Value Theorem on this interval, there exists an intermediate point $\xi$ strictly between $x_0$ and $x$ such that:
$$
\begin{gather}
f(x) - f(x_0) = f'(\xi)(x - x_0) \tag{1}
\end{gather}
$$

Because $\xi \in \text{int}(I)$, the hypothesis gives $f'(\xi) = 0$. Therefore:
$$
\begin{gather}
f(x) - f(x_0) = 0 \cdot (x - x_0) = 0 \implies f(x) = f(x_0) = \text{const} \tag{2}
\end{gather}
$$

**Converse Implication ($\impliedby$):**
If $f(x) = C$ for all $x \in I$, the difference quotient is $\frac{C - C}{h} = 0$, so $f'(x) = \lim_{h \to 0} 0 = 0$.

### Part 2: Monotonicity Criterion
**Direct Implication ($\implies$):**
Suppose $f'(x) \ge 0$ for all $x \in \text{int}(I)$. Let $x_1, x_2 \in I$ with $x_1 < x_2$. Applying Lagrange's Mean Value Theorem on $[x_1, x_2]$:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{3}
\end{gather}
$$
for some $\xi \in (x_1, x_2) \subseteq \text{int}(I)$.

Because $f'(\xi) \ge 0$ and $x_2 - x_1 > 0$, the product satisfies:
$$
\begin{gather}
f(x_2) - f(x_1) \ge 0 \implies f(x_1) \le f(x_2) \tag{4}
\end{gather}
$$
proving that $f$ is non-decreasing on $I$. (The argument for $f' \le 0$ is identical).

**Converse Implication ($\impliedby$):**
Suppose $f$ is non-decreasing on $I$. For any $x_0 \in \text{int}(I)$ and $h > 0$ such that $x_0 + h \in I$:
$$
\begin{gather}
f(x_0 + h) \ge f(x_0) \implies \frac{f(x_0 + h) - f(x_0)}{h} \ge 0 \tag{5}
\end{gather}
$$

Taking the limit as $h \to 0^+$:
$$
\begin{gather}
f'(x_0) = \lim_{h \to 0^+} \frac{f(x_0 + h) - f(x_0)}{h} \ge 0 \tag{6}
\end{gather}
$$

### Part 3: Strict Monotonicity
Suppose $f'(x) > 0$ for all $x \in \text{int}(I)$. For any $x_1 < x_2$ in $I$, by the equation of step 3:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{7}
\end{gather}
$$
Because $f'(\xi) > 0$ and $x_2 - x_1 > 0$, their product is strictly positive: $f(x_2) - f(x_1) > 0 \implies f(x_1) < f(x_2)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
