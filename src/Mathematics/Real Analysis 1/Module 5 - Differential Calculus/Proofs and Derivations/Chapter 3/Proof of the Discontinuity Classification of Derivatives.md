---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be differentiable on an open interval $I$, and let $x_0 \in I$.

### Part 1: Impossibility of Jump Discontinuities (First Kind)
Suppose for contradiction that $f'$ possesses a jump discontinuity at $x_0$. 

By definition of a jump discontinuity (Definition 1.3 of Module 4), both one-sided limits exist and are finite, but differ:
$$
\begin{gather}
L^- := \lim_{x \to x_0^-} f'(x) \quad \text{and} \quad L^+ := \lim_{x \to x_0^+} f'(x) \quad \text{with } L^- \neq L^+ \tag{1}
\end{gather}
$$

Assume without loss of generality that $L^- < L^+$. Choose any intermediate value $\gamma \in \mathbb{R}$ strictly between the limits:
$$
\begin{gather}
L^- < \gamma < L^+ \tag{2}
\end{gather}
$$

By definition of one-sided limits:
1. There exists $\delta_1 > 0$ such that for all $x \in (x_0 - \delta_1, x_0)$, $f'(x) < \gamma$.
2. There exists $\delta_2 > 0$ such that for all $x \in (x_0, x_0 + \delta_2)$, $f'(x) > \gamma$.

Now, consider any subinterval $[a, b] \subset (x_0 - \delta_1, x_0 + \delta_2)$ containing $x_0$ in its interior ($a < x_0 < b$). 

By construction, $f'(a) < \gamma$ and $f'(b) > \gamma$. By Theorem 3.7 (Darboux's Theorem), there must exist some $c \in (a, b)$ such that $f'(c) = \gamma$.

However, by the choice of $\delta_1$ and $\delta_2$, for every $x \in (x_0 - \delta_1, x_0)$ we have $f'(x) < \gamma$, and for every $x \in (x_0, x_0 + \delta_2)$ we have $f'(x) > \gamma$. The only remaining candidate point in $(a, b)$ is $x_0$ itself. 

Thus, we must have $f'(x_0) = \gamma$ for *every* choice of $\gamma \in (L^-, L^+)$. But $f'(x_0)$ is a single, fixed real number, which cannot simultaneously equal every element of the non-degenerate open interval $(L^-, L^+)$. This contradiction proves that $f'$ cannot have a jump discontinuity.

### Part 2: Impossibility of Removable Discontinuities
Suppose that $\lim_{x \to x_0} f'(x) = L \in \mathbb{R}$ exists. We must show that $f'(x_0) = L$.

Let $h > 0$. By Theorem 3.4 (Lagrange's Mean Value Theorem) applied to $f$ on $[x_0, x_0 + h]$:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} = f'(\xi_h) \tag{3}
\end{gather}
$$
for some $\xi_h \in (x_0, x_0 + h)$.

As $h \to 0^+$, the squeeze theorem forces $\xi_h \to x_0^+$. Because $\lim_{x \to x_0} f'(x) = L$:
$$
\begin{gather}
\lim_{h \to 0^+} f'(\xi_h) = L \tag{4}
\end{gather}
$$

Combining equations (3) and (4) with the definition of the derivative:
$$
\begin{gather}
f'(x_0) = \lim_{h \to 0^+} \frac{f(x_0 + h) - f(x_0)}{h} = \lim_{h \to 0^+} f'(\xi_h) = L \tag{5}
\end{gather}
$$

Therefore, $\lim_{x \to x_0} f'(x) = f'(x_0)$, proving that $f'$ is continuous at $x_0$. Consequently, removable discontinuities are impossible.

Because neither jump nor removable discontinuities can occur, any point of discontinuity of a derivative must be an essential discontinuity (second kind), where at least one of the one-sided limits fails to exist.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
