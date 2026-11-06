---
dg-publish: true
---
Let $f: E \to Y \subseteq \mathbb{R}$ and $g: Y \to \mathbb{R}$, with $a \in E'$ and $b \in Y'$. Assume that:
$$
\begin{gather}
\lim_{x \to a} f(x) = b \quad \text{and} \quad \lim_{y \to b} g(y) = c \tag{1}
\end{gather}
$$
---
# Proposition 1
Assume Condition 1 holds: $g$ is continuous at $b$, meaning $g(b) = c = \lim_{y \to b} g(y)$.

Let $\varepsilon > 0$ be given. Because $g$ is continuous at $b$, there exists a radius $\eta > 0$ such that for all $y \in Y$:
$$
\begin{gather}
|y - b| < \eta \implies |g(y) - g(b)| = |g(y) - c| < \varepsilon \tag{2}
\end{gather}
$$
Notice that step 2 includes the point $y = b$. 

Because $\lim_{x \to a} f(x) = b$, for the positive tolerance $\eta > 0$, there exists a radius $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
0 < |x - a| < \delta \implies |f(x) - b| < \eta \tag{3}
\end{gather}
$$
Setting $y = f(x)$ in step 3 satisfies the antecedent of step 2 for all $x \in \mathring{U}_\delta(a) \cap E$. Consequently:
$$
\begin{gather}
|g(f(x)) - c| < \varepsilon \quad \forall x \in E, \ 0 < |x - a| < \delta \tag{4}
\end{gather}
$$
Thus, $\lim_{x \to a} g(f(x)) = c$.

---
# Proposition 2
Assume Condition 2 holds: there exists a radius $\delta_0 > 0$ such that $f(x) \neq b$ for all $x \in \mathring{U}_{\delta_0}(a) \cap E$.

Let $\varepsilon > 0$ be given. Because $\lim_{y \to b} g(y) = c$, there exists a radius $\eta > 0$ such that for all $y \in Y$:
$$
\begin{gather}
0 < |y - b| < \eta \implies |g(y) - c| < \varepsilon \tag{5}
\end{gather}
$$
Because $\lim_{x \to a} f(x) = b$, corresponding to $\eta > 0$, there exists a radius $\delta_1 > 0$ such that for all $x \in E$:
$$
\begin{gather}
0 < |x - a| < \delta_1 \implies |f(x) - b| < \eta \tag{6}
\end{gather}
$$
Define $\delta := \min(\delta_0, \delta_1) > 0$. Let $x \in E$ satisfy $0 < |x - a| < \delta$. Because $\delta \le \delta_0$, $f(x) \neq b$, which implies:
$$
\begin{gather}
|f(x) - b| > 0 \tag{7}
\end{gather}
$$
Concurrently, because $\delta \le \delta_1$, $|f(x) - b| < \eta$. Combining step 6 and step 7 gives:
$$
\begin{gather}
0 < |f(x) - b| < \eta \tag{8}
\end{gather}
$$
Setting $y = f(x)$ satisfies the punctured hypothesis of step 5, which immediately demonstrates that:
$$
\begin{gather}
|g(f(x)) - c| < \varepsilon \quad \forall x \in E, \ 0 < |x - a| < \delta \tag{9}
\end{gather}
$$
Thus, $\lim_{x \to a} g(f(x)) = c$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$