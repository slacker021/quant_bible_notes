---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f: [a, \infty) \to \mathbb{R}$ be a function satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Because the absolute value function $u \mapsto |u|$ is continuous on $\mathbb{R}$, the composition $|f|$ is Riemann integrable on every compact interval $[a, B]$:
$$
\begin{gather}
|f| \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{2}
\end{gather}
$$
Assume that the improper integral of $|f|$ converges to a finite real value:
$$
\begin{gather}
\int_a^\infty |f(x)|\,dx := \lim_{B \to \infty} \int_a^B |f(x)|\,dx < \infty \tag{3}
\end{gather}
$$
---
# Step 1
Because the improper integral $\int_a^\infty |f(x)|\,dx$ converges, by the Cauchy Criterion for Convergence of Improper Integrals, for every $\varepsilon > 0$, there exists an exhaustion threshold $B_0 \ge a$ such that:
$$
\begin{gather}
B_1, B_2 > B_0 \implies \left| \int_{B_1}^{B_2} |f(x)|\,dx \right| < \varepsilon \tag{4}
\end{gather}
$$

Without loss of generality, assume $B_2 \ge B_1 > B_0$. Because $|f(x)| \ge 0$ for all $x \in [B_1, B_2]$, the order-preserving property of the Riemann integral guarantees:
$$
\begin{gather}
\int_{B_1}^{B_2} |f(x)|\,dx \ge \int_{B_1}^{B_2} 0\,dx = 0 \tag{5}
\end{gather}
$$

The absolute value on the integral in step 4 may therefore be evaluated directly:
$$
\begin{gather}
\int_{B_1}^{B_2} |f(x)|\,dx < \varepsilon \quad \text{for all } B_2 \ge B_1 > B_0 \tag{6}
\end{gather}
$$
---
# Step 2
Let $B_2 \ge B_1 > B_0$. By the Absolute Value Inequality for proper Riemann integrals:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| \le \int_{B_1}^{B_2} |f(x)|\,dx \tag{7}
\end{gather}
$$

Chaining the inequality of step 7 with step 6 yields:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| \le \int_{B_1}^{B_2} |f(x)|\,dx < \varepsilon \quad \text{for all } B_2 \ge B_1 > B_0 \tag{8}
\end{gather}
$$

For parameters satisfying $B_1 > B_2 > B_0$, applying the directional inversion identity $\int_{B_1}^{B_2} f(x)\,dx = -\int_{B_2}^{B_1} f(x)\,dx$ gives:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| = \left| -\int_{B_2}^{B_1} f(x)\,dx \right| = \left| \int_{B_2}^{B_1} f(x)\,dx \right| < \varepsilon \tag{9}
\end{gather}
$$

Combining step 8 and step 9 confirms that for all $B_1, B_2 > B_0$:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| < \varepsilon \tag{10}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists an exhaustion threshold $B_0 \ge a$ such that step 10 holds for all $B_1, B_2 > B_0$, the function $f$ satisfies the Cauchy Criterion for improper integrals.

By the Cauchy Criterion for Convergence of Improper Integrals, the improper integral of $f$ converges to a finite real value:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B f(x)\,dx = \int_a^\infty f(x)\,dx \in \mathbb{R} \tag{11}
\end{gather}
$$
---
# Step 3
An independent deduction proceeds via Jordan's non-negative decomposition. Define the positive and negative parts of $f$:
$$
\begin{gather}
f^+(x) := \max\{f(x), 0\} = \frac{|f(x)| + f(x)}{2} \tag{12}
\end{gather}
$$
$$
\begin{gather}
f^-(x) := \max\{-f(x), 0\} = \frac{|f(x)| - f(x)}{2} \tag{13}
\end{gather}
$$

Both $f^+$ and $f^-$ are non-negative and satisfy the pointwise domination:
$$
\begin{gather}
0 \le f^+(x) \le |f(x)|, \qquad 0 \le f^-(x) \le |f(x)| \quad \text{for all } x \in [a, \infty) \tag{14}
\end{gather}
$$

Because $f, |f| \in \mathcal{R}[a, B]$, the algebraic representations in step 12 and step 13 ensure that $f^+, f^- \in \mathcal{R}[a, B]$ for all $B \ge a$.

Because $\int_a^\infty |f(x)|\,dx$ converges, applying the Direct Comparison Test for Improper Integrals to each inequality in step 14 guarantees that both improper integrals converge finitely:
$$
\begin{gather}
\int_a^\infty f^+(x)\,dx < \infty, \qquad \int_a^\infty f^-(x)\,dx < \infty \tag{15}
\end{gather}
$$

Expressing $f$ as the difference:
$$
\begin{gather}
f(x) = f^+(x) - f^-(x) \tag{16}
\end{gather}
$$

By the vector space linearity of convergent improper integrals:
$$
\begin{gather}
\int_a^\infty f(x)\,dx = \int_a^\infty \big( f^+(x) - f^-(x) \big)\,dx = \int_a^\infty f^+(x)\,dx - \int_a^\infty f^-(x)\,dx \tag{17}
\end{gather}
$$

Because both terms on the right-hand side of step 17 are finite real numbers, their difference is a finite real number, confirming that $\int_a^\infty f(x)\,dx$ converges.

---
# Step 4
For every finite parameter $B \ge a$, applying the proper Riemann absolute value inequality on $[a, B]$:
$$
\begin{gather}
\left| \int_a^B f(x)\,dx \right| \le \int_a^B |f(x)|\,dx \tag{18}
\end{gather}
$$

Because the limit $\lim_{B \to \infty} \int_a^B f(x)\,dx = \int_a^\infty f(x)\,dx$ exists in $\mathbb{R}$, and the absolute value function $t \mapsto |t|$ is continuous on $\mathbb{R}$, the limit commutes with the absolute value:
$$
\begin{gather}
\left| \int_a^\infty f(x)\,dx \right| = \left| \lim_{B \to \infty} \int_a^B f(x)\,dx \right| = \lim_{B \to \infty} \left| \int_a^B f(x)\,dx \right| \tag{19}
\end{gather}
$$

Taking the limit as $B \to \infty$ on both sides of step 18, the order-preserving property of functional limits guarantees:
$$
\begin{gather}
\lim_{B \to \infty} \left| \int_a^B f(x)\,dx \right| \le \lim_{B \to \infty} \int_a^B |f(x)|\,dx \tag{20}
\end{gather}
$$

Substituting step 19 and the definition of the absolute improper integral into step 20:
$$
\begin{gather}
\left| \int_a^\infty f(x)\,dx \right| \le \int_a^\infty |f(x)|\,dx \tag{21}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
