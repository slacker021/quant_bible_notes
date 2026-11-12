---
dg-publish: true
---
Let $f: \mathbb{R} \to \mathbb{R}$ be a convex function defined on the entire real line.

Recall that for any three points $x_1 < x < x_2$, convexity entails the fundamental three-chord slope inequality:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{1}
\end{gather}
$$

---
# Proposition 1
Suppose that $f$ is bounded from above on $\mathbb{R}$. There exists a real constant $M \in \mathbb{R}$ such that $f(x) \le M$ for all $x \in \mathbb{R}$.

Let $x_1, x_2 \in \mathbb{R}$ be any two points with $x_1 < x_2$. For any point $x > x_2$, the chord slope inequality in step 1 yields:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x) - f(x_2)}{x - x_2} \tag{2}
\end{gather}
$$
Because $f(x) \le M$, the numerator on the right-hand side is bounded:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{M - f(x_2)}{x - x_2} \tag{3}
\end{gather}
$$
Taking the limit of step 3 as $x \to +\infty$, the denominator $x - x_2$ tends to $+\infty$ while the numerator remains bounded, whence:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \lim_{x \to +\infty} \frac{M - f(x_2)}{x - x_2} = 0 \tag{4}
\end{gather}
$$
Because $x_2 - x_1 > 0$, step 4 implies $f(x_2) - f(x_1) \le 0$, which means $f(x_2) \le f(x_1)$.

Next, consider points $x < x_1$. By step 1:
$$
\begin{gather}
\frac{f(x_1) - f(x)}{x_1 - x} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{5}
\end{gather}
$$
Using $f(x) \le M$, rewrite the left-hand difference:
$$
\begin{gather}
\frac{f(x_1) - M}{x_1 - x} \le \frac{f(x_1) - f(x)}{x_1 - x} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{6}
\end{gather}
$$
Taking the limit as $x \to -\infty$, the denominator $x_1 - x \to +\infty$, yielding:
$$
\begin{gather}
0 = \lim_{x \to -\infty} \frac{f(x_1) - M}{x_1 - x} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{7}
\end{gather}
$$
Step 7 implies $f(x_2) - f(x_1) \ge 0$, which means $f(x_1) \le f(x_2)$.

Combining step 4 and step 7 demonstrates that for any $x_1 < x_2$:
$$
\begin{gather}
f(x_1) \le f(x_2) \le f(x_1) \implies f(x_1) = f(x_2) \tag{8}
\end{gather}
$$
Thus, $f$ is identically constant on $\mathbb{R}$.

Now suppose that $f$ is bounded from below, so $f(x) \ge m$ for all $x \in \mathbb{R}$. If $f$ is not identically constant, there exist $x_1 < x_2$ such that $f(x_1) \neq f(x_2)$. If $f(x_1) > f(x_2)$, then $\frac{f(x_2) - f(x_1)}{x_2 - x_1} = -c < 0$ with $c > 0$. For any $x > x_2$, step 1 implies $\frac{f(x) - f(x_2)}{x - x_2} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} = -c$ is impossible for all $x$; rather, for $x < x_1$, $\frac{f(x_1) - f(x)}{x_1 - x} \le -c$, which forces $f(x) \to \infty$. But if $f(x_2) > f(x_1)$, then $\frac{f(x_2) - f(x_1)}{x_2 - x_1} = k > 0$. For $x < x_1$, step 1 gives $\frac{f(x_1) - f(x)}{x_1 - x} \le k$, whence $f(x) \ge f(x_1) - k(x_1 - x)$, which goes to $-\infty$ as $x \to -\infty$, contradicting $f(x) \ge m$. Thus, $f$ is identically constant.

---
# Proposition 2
Suppose that:
$$
\begin{gather}
\lim_{x \to -\infty} \frac{f(x)}{x} = \lim_{x \to +\infty} \frac{f(x)}{x} = 0 \tag{9}
\end{gather}
$$

Fix an arbitrary pair of points $x_1 < x_2$ in $\mathbb{R}$. For any $x > x_2$, the chord inequality in step 1 yields:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x) - f(x_2)}{x - x_2} = \frac{f(x)}{x} \frac{x}{x - x_2} - \frac{f(x_2)}{x - x_2} \tag{10}
\end{gather}
$$
Taking the limit as $x \to +\infty$, the term $\frac{f(x)}{x} \to 0$, $\frac{x}{x - x_2} \to 1$, and $\frac{f(x_2)}{x - x_2} \to 0$. Step 10 becomes:
$$
\begin{gather}
\frac{f(x_2) - f(x_1)}{x_2 - x_1} \le 0 \tag{11}
\end{gather}
$$

Similarly, for any $x < x_1$, step 1 gives:
$$
\begin{gather}
\frac{f(x_1) - f(x)}{x_1 - x} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{12}
\end{gather}
$$
Rewriting the left-hand side as:
$$
\begin{gather}
\frac{f(x_1) - f(x)}{x_1 - x} = \frac{f(x) - f(x_1)}{x - x_1} = \frac{f(x)}{x} \frac{x}{x - x_1} - \frac{f(x_1)}{x - x_1} \tag{13}
\end{gather}
$$
Taking the limit as $x \to -\infty$, because $\lim_{x \to -\infty} \frac{f(x)}{x} = 0$, the expression in step 13 converges to 0. Step 12 then yields:
$$
\begin{gather}
0 \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \tag{14}
\end{gather}
$$

Chaining step 11 and step 14 shows that:
$$
\begin{gather}
0 \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le 0 \implies \frac{f(x_2) - f(x_1)}{x_2 - x_1} = 0 \tag{15}
\end{gather}
$$
Thus, $f(x_1) = f(x_2)$ for all $x_1 < x_2$, proving that $f$ is identically constant.

---
# Proposition 3
Let $f$ be convex on $(a, \infty)$. Fix an anchor point $x_0 \in (a, \infty)$. For any $x > x_0$, the slope of the chord connecting $x_0$ to $x$ is:
$$
\begin{gather}
S(x) := \frac{f(x) - f(x_0)}{x - x_0} \tag{16}
\end{gather}
$$
By virtue of the chord inequality in step 1, the slope function $S(x)$ is non-decreasing on $(x_0, \infty)$.

By the fundamental monotone convergence theorem for real functions, any non-decreasing function on a semi-infinite ray $(x_0, \infty)$ converges as $x \to +\infty$ to a finite limit $L = \sup_{x > x_0} S(x)$ or diverges to $+\infty$:
$$
\begin{gather}
\lim_{x \to +\infty} \frac{f(x) - f(x_0)}{x - x_0} = L \in (-\infty, +\infty] \tag{17}
\end{gather}
$$
Because:
$$
\begin{gather}
\frac{f(x)}{x} = \frac{f(x) - f(x_0)}{x - x_0} \cdot \frac{x - x_0}{x} + \frac{f(x_0)}{x} \tag{18}
\end{gather}
$$
and because $\lim_{x \to +\infty} \frac{x - x_0}{x} = 1$ and $\lim_{x \to +\infty} \frac{f(x_0)}{x} = 0$, step 18 converges to identical behavior:
$$
\begin{gather}
\lim_{x \to +\infty} \frac{f(x)}{x} = L \in (-\infty, +\infty] \tag{19}
\end{gather}
$$
Since $S(x)$ is non-decreasing, $L \ge S(x) > -\infty$, so the limit cannot diverge to $-\infty$. It converges to a finite real number or diverges to $+\infty$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
