---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $x_0 \in \text{int}(E)$, and let $f: E \to \mathbb{R}$.

# Theorem 1
Suppose there exist two linear mappings $L_1(h) = A_1 h$ and $L_2(h) = A_2 h$ with $A_1, A_2 \in \mathbb{R}$ such that:
$$
\begin{gather}
\Delta f(x_0; h) = A_1 h + o(h) \quad \text{as } h \to 0 \tag{1} \\
\Delta f(x_0; h) = A_2 h + o(h) \quad \text{as } h \to 0 \tag{2}
\end{gather}
$$

Subtracting the equation of step 2 from the equation of step 1 yields:
$$
\begin{gather}
0 = (A_1 - A_2)h + o(h) - o(h) = (A_1 - A_2)h + o(h) \quad \text{as } h \to 0 \tag{3}
\end{gather}
$$

For any $h \neq 0$, dividing the equation of step 3 by $h$ produces:
$$
\begin{gather}
0 = (A_1 - A_2) + \frac{o(h)}{h} \tag{4}
\end{gather}
$$

Taking the limit as $h \to 0$ in the equation of step 4, by definition of the Landau little-$o$ notation $\lim_{h \to 0} \frac{o(h)}{h} = 0$:
$$
\begin{gather}
0 = \lim_{h \to 0} \left( (A_1 - A_2) + \frac{o(h)}{h} \right) = A_1 - A_2 \tag{5}
\end{gather}
$$

The equation of step 5 establishes that $A_1 = A_2$. Consequently, the linear mapping $h \mapsto A h$ is uniquely determined.

---
# Theorem 2
Suppose first that $f$ is differentiable at $x_0$. By the definition of differentiability at a point:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A h + \alpha(h) h, \quad \text{where } \lim_{h \to 0} \alpha(h) = 0 \tag{6}
\end{gather}
$$

For $h \neq 0$, dividing the equation of step 6 by $h$ gives:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} = A + \alpha(h) \tag{7}
\end{gather}
$$

Taking the limit as $h \to 0$ in the equation of step 7:
$$
\begin{gather}
\lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} = \lim_{h \to 0} (A + \alpha(h)) = A + 0 = A \tag{8}
\end{gather}
$$

Conversely, suppose that the limit of the difference quotient exists and equals a finite number $A \in \mathbb{R}$:
$$
\begin{gather}
\lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} = A \tag{9}
\end{gather}
$$

Define the remainder function $\alpha(h)$ for $h \neq 0$ by:
$$
\begin{gather}
\alpha(h) := \frac{f(x_0 + h) - f(x_0)}{h} - A \tag{10}
\end{gather}
$$

By the hypothesis of step 9, $\lim_{h \to 0} \alpha(h) = A - A = 0$. Multiplying the equation of step 10 by $h$ yields:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A h + \alpha(h) h = A h + o(h) \quad \text{as } h \to 0 \tag{11}
\end{gather}
$$

Substituting $x = x_0 + h$, so that $h = x - x_0$, transforms the equation of step 9 into the equivalent coordinate formulation:
$$
\begin{gather}
f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \tag{12}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
