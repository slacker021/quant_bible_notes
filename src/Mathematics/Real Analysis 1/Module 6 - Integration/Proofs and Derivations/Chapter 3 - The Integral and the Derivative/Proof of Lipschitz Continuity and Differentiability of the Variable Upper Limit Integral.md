---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f \in \mathcal{R}[a, b]$ be a Riemann integrable function, and define the variable upper limit accumulation function $F: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
F(x) := \int_a^x f(t)\,dt \tag{1}
\end{gather}
$$
where $\int_a^a f(t)\,dt := 0$ by the orientation convention of the definite integral.

By the Necessity of Boundedness for Riemann Integrability (Module 6, Chapter 1), every Riemann integrable function on a compact interval is bounded. Therefore, the supremum of the absolute value of $f$ on $[a, b]$ is a finite non-negative real number:
$$
\begin{gather}
M := \sup_{t \in [a, b]} |f(t)| < \infty \tag{2}
\end{gather}
$$
which implies:
$$
\begin{gather}
|f(t)| \le M \quad \text{for all } t \in [a, b] \tag{3}
\end{gather}
$$
---
# Theorem 1
Let $x_1, x_2 \in [a, b]$ be two arbitrary points. 

By the definition of $F$ in step 1:
$$
\begin{gather}
F(x_2) - F(x_1) = \int_a^{x_2} f(t)\,dt - \int_a^{x_1} f(t)\,dt \tag{4}
\end{gather}
$$

By the Generalized Orientation Additivity Formula (Module 6, Chapter 2, [[Proof of the Generalized Orientation Additivity Formula]]):
$$
\begin{gather}
\int_a^{x_2} f(t)\,dt - \int_a^{x_1} f(t)\,dt = \int_a^{x_2} f(t)\,dt + \int_{x_1}^a f(t)\,dt = \int_{x_1}^{x_2} f(t)\,dt \tag{5}
\end{gather}
$$

Substituting step 5 into step 4 yields:
$$
\begin{gather}
F(x_2) - F(x_1) = \int_{x_1}^{x_2} f(t)\,dt \tag{6}
\end{gather}
$$

To establish the Lipschitz bound, three mutually exhaustive cases are examined:

### Case 1
If $x_1 = x_2$, the integral over a degenerate interval satisfies $\int_{x_1}^{x_1} f(t)\,dt = 0$, giving:
$$
\begin{gather}
|F(x_2) - F(x_1)| = |0| = 0 = M \cdot 0 = M |x_2 - x_1| \tag{7}
\end{gather}
$$

### Case 2
Applying the Absolute Value Integral Inequality (Module 6, Chapter 2, [[Proof of Monotonicity and the Absolute Value Integral Inequality]]) to step 6 gives:
$$
\begin{gather}
|F(x_2) - F(x_1)| = \left| \int_{x_1}^{x_2} f(t)\,dt \right| \le \int_{x_1}^{x_2} |f(t)|\,dt \tag{8}
\end{gather}
$$

By step 3, $|f(t)| \le M$ for all $t \in [x_1, x_2]$. Applying Order Monotonicity of the Riemann Integral (Module 6, Chapter 2, [[Proof of Monotonicity and the Absolute Value Integral Inequality]]) to step 8 yields:
$$
\begin{gather}
\int_{x_1}^{x_2} |f(t)|\,dt \le \int_{x_1}^{x_2} M\,dt = M(x_2 - x_1) = M |x_2 - x_1| \tag{9}
\end{gather}
$$

Combining step 8 and step 9 gives:
$$
\begin{gather}
|F(x_2) - F(x_1)| \le M |x_2 - x_1| \tag{10}
\end{gather}
$$

### Case 3
By the orientation convention of the definite integral:
$$
\begin{gather}
\int_{x_1}^{x_2} f(t)\,dt = -\int_{x_2}^{x_1} f(t)\,dt \tag{11}
\end{gather}
$$

Taking the absolute value of step 11 and applying the Absolute Value Integral Inequality on $[x_2, x_1]$:
$$
\begin{gather}
|F(x_2) - F(x_1)| = \left| -\int_{x_2}^{x_1} f(t)\,dt \right| = \left| \int_{x_2}^{x_1} f(t)\,dt \right| \le \int_{x_2}^{x_1} |f(t)|\,dt \tag{12}
\end{gather}
$$

Applying Order Monotonicity with $|f(t)| \le M$ across $[x_2, x_1]$:
$$
\begin{gather}
\int_{x_2}^{x_1} |f(t)|\,dt \le \int_{x_2}^{x_1} M\,dt = M(x_1 - x_2) = M |x_2 - x_1| \tag{13}
\end{gather}
$$

Combining step 12 and step 13 gives:
$$
\begin{gather}
|F(x_2) - F(x_1)| \le M |x_2 - x_1| \tag{14}
\end{gather}
$$

Combining step 7, step 10, and step 14, the inequality:
$$
\begin{gather}
|F(x_2) - F(x_1)| \le M |x_2 - x_1| \tag{15}
\end{gather}
$$
holds for all pairs $x_1, x_2 \in [a, b]$. 

Consequently, $F$ is Lipschitz continuous on $[a, b]$ with Lipschitz constant $M$. Because every Lipschitz continuous function is uniformly continuous (for any $\varepsilon > 0$, setting $\delta = \frac{\varepsilon}{M + 1}$ guarantees $|F(x_2) - F(x_1)| \le M |x_2 - x_1| < \varepsilon$ whenever $|x_2 - x_1| < \delta$), $F$ is uniformly continuous on $[a, b]$, and therefore continuous on $[a, b]$.

---
# Theorem 2
Suppose $f$ is continuous at a designated point $x_0 \in [a, b]$. 

First assume $x_0 \in (a, b)$. Let $h \in \mathbb{R} \setminus \{0\}$ be any non-zero increment such that $x_0 + h \in [a, b]$. 

By step 6, the difference of the accumulation function values across the increment $h$ is:
$$
\begin{gather}
F(x_0 + h) - F(x_0) = \int_{x_0}^{x_0 + h} f(t)\,dt \tag{16}
\end{gather}
$$

The value $f(x_0)$ is a fixed constant independent of the integration variable $t$. By the Linearity of the Riemann Integral (Module 6, Chapter 2, [[Proof of the Linearity of the Riemann Integral]]):
$$
\begin{gather}
\int_{x_0}^{x_0 + h} f(x_0)\,dt = f(x_0) \int_{x_0}^{x_0 + h} 1\,dt = f(x_0) \cdot h \tag{17}
\end{gather}
$$

Dividing step 17 by the non-zero scalar $h$:
$$
\begin{gather}
f(x_0) = \frac{1}{h} \int_{x_0}^{x_0 + h} f(x_0)\,dt \tag{18}
\end{gather}
$$

Forming the difference between the Newton difference quotient of $F$ at $x_0$ and the candidate derivative value $f(x_0)$:
$$
\begin{gather}
\frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) = \frac{1}{h} \int_{x_0}^{x_0 + h} f(t)\,dt - \frac{1}{h} \int_{x_0}^{x_0 + h} f(x_0)\,dt \tag{19}
\end{gather}
$$

By Linearity of the Riemann Integral, combining the two integrals in step 19 yields:
$$
\begin{gather}
\frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) = \frac{1}{h} \int_{x_0}^{x_0 + h} \big( f(t) - f(x_0) \big)\,dt \tag{20}
\end{gather}
$$

Taking the absolute value of both sides of step 20:
$$
\begin{gather}
\left| \frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) \right| = \frac{1}{|h|} \left| \int_{x_0}^{x_0 + h} \big( f(t) - f(x_0) \big)\,dt \right| \tag{21}
\end{gather}
$$

If $h > 0$, applying the Absolute Value Integral Inequality directly gives:
$$
\begin{gather}
\left| \int_{x_0}^{x_0 + h} \big( f(t) - f(x_0) \big)\,dt \right| \le \int_{x_0}^{x_0 + h} |f(t) - f(x_0)|\,dt \tag{22}
\end{gather}
$$

If $h < 0$, applying the orientation convention $\int_{x_0}^{x_0 + h} = -\int_{x_0 + h}^{x_0}$ and the Absolute Value Integral Inequality gives:
$$
\begin{gather}
\left| \int_{x_0}^{x_0 + h} \big( f(t) - f(x_0) \big)\,dt \right| = \left| -\int_{x_0 - |h|}^{x_0} \big( f(t) - f(x_0) \big)\,dt \right| \le \int_{x_0 - |h|}^{x_0} |f(t) - f(x_0)|\,dt \tag{23}
\end{gather}
$$

Unifying step 22 and step 23, the bound holds over the interval with endpoints $x_0$ and $x_0 + h$:
$$
\begin{gather}
\left| \frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) \right| \le \frac{1}{|h|} \int_{\min\{x_0, x_0 + h\}}^{\max\{x_0, x_0 + h\}} |f(t) - f(x_0)|\,dt \tag{24}
\end{gather}
$$

Now let $\varepsilon > 0$ be an arbitrary positive real number.

Because $f$ is continuous at $x_0$, there exists a radius $\delta > 0$ such that for all $t \in [a, b]$:
$$
\begin{gather}
|t - x_0| < \delta \implies |f(t) - f(x_0)| < \varepsilon \tag{25}
\end{gather}
$$

Let $h$ satisfy $0 < |h| < \delta$ with $x_0 + h \in [a, b]$. 

For every point $t$ belonging to the closed interval with endpoints $x_0$ and $x_0 + h$, the distance from $x_0$ satisfies:
$$
\begin{gather}
|t - x_0| \le |h| < \delta \tag{26}
\end{gather}
$$

By step 25 and step 26, the integrand satisfies:
$$
\begin{gather}
|f(t) - f(x_0)| < \varepsilon \quad \text{for all } t \in [\min\{x_0, x_0 + h\}, \max\{x_0, x_0 + h\}] \tag{27}
\end{gather}
$$

Applying Order Monotonicity of the Riemann Integral to step 27 across the interval of length $|h|$:
$$
\begin{gather}
\int_{\min\{x_0, x_0 + h\}}^{\max\{x_0, x_0 + h\}} |f(t) - f(x_0)|\,dt \le \int_{\min\{x_0, x_0 + h\}}^{\max\{x_0, x_0 + h\}} \varepsilon\,dt = \varepsilon \cdot |h| \tag{28}
\end{gather}
$$

Substituting step 28 into step 24:
$$
\begin{gather}
\left| \frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) \right| \le \frac{1}{|h|} \cdot (\varepsilon |h|) = \varepsilon \tag{29}
\end{gather}
$$

Because $\varepsilon > 0$ was chosen arbitrarily, the inequality of step 29 establishes, by the $\varepsilon$-$\delta$ definition of a functional limit, that:
$$
\begin{gather}
\lim_{h \to 0} \frac{F(x_0 + h) - F(x_0)}{h} = f(x_0) \tag{30}
\end{gather}
$$

Therefore, $F$ is differentiable at $x_0$, and its derivative satisfies:
$$
\begin{gather}
F'(x_0) = f(x_0) \tag{31}
\end{gather}
$$

It remains to examine the boundary endpoints:

### Case 1
If $f$ is continuous from the right at $a$, then for every $\varepsilon > 0$, there exists $\delta > 0$ such that for all $t \in [a, a + \delta)$, $|f(t) - f(a)| < \varepsilon$. Restricting the increment to $h \in (0, \delta)$, the identical deduction of steps 16 through 29 holds over the interval $[a, a + h]$. Consequently:
$$
\begin{gather}
F'_+(a) = \lim_{h \to 0^+} \frac{F(a + h) - F(a)}{h} = f(a) \tag{32}
\end{gather}
$$
### Case 2
If $f$ is continuous from the left at $b$, then for every $\varepsilon > 0$, there exists $\delta > 0$ such that for all $t \in (b - \delta, b]$, $|f(t) - f(b)| < \varepsilon$. Restricting the increment to $h \in (-\delta, 0)$, the identical deduction of steps 16 through 29 holds over the interval $[b - |h|, b]$. Consequently:
$$
\begin{gather}
F'_-(b) = \lim_{h \to 0^-} \frac{F(b + h) - F(b)}{h} = f(b) \tag{33}
\end{gather}
$$

This completes the deduction for all points in $[a, b]$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
