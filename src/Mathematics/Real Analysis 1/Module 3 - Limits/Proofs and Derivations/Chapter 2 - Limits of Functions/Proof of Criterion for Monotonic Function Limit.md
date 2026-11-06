---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, and let $f: E \to \mathbb{R}$ be a nondecreasing function.

---
# Theorem 1
Assume that $s_0 := \sup E \in E'$, and consider the limit as $E \ni x \to s_0$.

**Case 1 (Bounded Above):**
Assume that $f$ is bounded above on $E$. By the Least Upper Bound Principle of $\mathbb{R}$, the supremum of the functional image exists as a finite real number:
$$
\begin{gather}
M := \sup_{x \in E} f(x) \in \mathbb{R} \tag{1}
\end{gather}
$$
Let $\varepsilon > 0$ be given. Because $M = \sup_{x \in E} f(x)$, the quantity $M - \varepsilon$ is not an upper bound for $f(E)$. Therefore, there exists a point $x_0 \in E$ such that:
$$
\begin{gather}
M - \varepsilon < f(x_0) \le M \tag{2}
\end{gather}
$$
If $x_0 = s_0$, then because $f$ is nondecreasing, $f(x) \le f(s_0) \le M$ for all $x \in E$, and $f(x) \ge f(x_0) > M - \varepsilon$ for all $x \ge x_0$, which immediately satisfies convergence.

If $x_0 < s_0$, define the positive distance $\delta := s_0 - x_0 > 0$. For all $x \in E$ satisfying $s_0 - \delta < x < s_0$:
$$
\begin{gather}
x_0 < x < s_0 \tag{3}
\end{gather}
$$
Because $f$ is nondecreasing on $E$, step 3 implies that $f(x_0) \le f(x)$. Combining this with step 1 and step 2 gives:
$$
\begin{gather}
M - \varepsilon < f(x_0) \le f(x) \le M < M + \varepsilon \tag{4}
\end{gather}
$$
Step 4 proves that $|f(x) - M| < \varepsilon$ for all $x \in E \cap (s_0 - \delta, s_0)$. Thus:
$$
\begin{gather}
\lim_{E \ni x \to \sup E} f(x) = \sup_{x \in E} f(x) \tag{5}
\end{gather}
$$

**Case 2 (Unbounded Above):**
Assume that $f$ is not bounded above on $E$. Let $C \in \mathbb{R}$ be arbitrary. There exists a point $x_0 \in E$ such that $f(x_0) > C$. 

Setting $\delta := s_0 - x_0 > 0$, for all $x \in E$ satisfying $s_0 - \delta < x < s_0$, monotonicity dictates that $f(x) \ge f(x_0) > C$. Consequently:
$$
\begin{gather}
\lim_{E \ni x \to \sup E} f(x) = +\infty \tag{6}
\end{gather}
$$

---
# Theorem 2
Assume that $i_0 := \inf E \in E'$, and consider the limit as $E \ni x \to i_0$.

**Case 1 (Bounded Below):**
Assume that $f$ is bounded below on $E$. By the Greatest Lower Bound Principle of $\mathbb{R}$:
$$
\begin{gather}
m := \inf_{x \in E} f(x) \in \mathbb{R} \tag{7}
\end{gather}
$$
Let $\varepsilon > 0$ be given. There exists a point $x_1 \in E$ such that $m \le f(x_1) < m + \varepsilon$.

Setting $\delta := x_1 - i_0 > 0$, for all $x \in E$ satisfying $i_0 < x < i_0 + \delta$, monotonicity ensures that $m \le f(x) \le f(x_1) < m + \varepsilon$, which establishes:
$$
\begin{gather}
\lim_{E \ni x \to \inf E} f(x) = \inf_{x \in E} f(x) \tag{8}
\end{gather}
$$

**Case 2 (Unbounded Below):**
If $f$ is unbounded below on $E$, for any $C \in \mathbb{R}$ there exists $x_1 \in E$ such that $f(x_1) < C$. Setting $\delta := x_1 - i_0 > 0$, for all $x \in E$ with $i_0 < x < i_0 + \delta$, monotonicity ensures $f(x) \le f(x_1) < C$. Consequently:
$$
\begin{gather}
\lim_{E \ni x \to \inf E} f(x) = -\infty \tag{9}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$