---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f: [a, \infty) \to \mathbb{R}$ be a non-negative function satisfying:
$$
\begin{gather}
f(x) \ge 0 \quad \text{for all } x \in [a, \infty) \tag{1}
\end{gather}
$$
Assume that $f$ is Riemann integrable on every compact subinterval $[a, B]$:
$$
\begin{gather}
f \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{2}
\end{gather}
$$
Define the accumulation function $F: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
F(B) := \int_a^B f(x)\,dx \tag{3}
\end{gather}
$$
---
# Step 1
Let $B_1, B_2 \in [a, \infty)$ satisfy $a \le B_1 < B_2$.

By the interval additivity of the Riemann integral, the integral over $[a, B_2]$ decomposes into:
$$
\begin{gather}
F(B_2) = \int_a^{B_2} f(x)\,dx = \int_a^{B_1} f(x)\,dx + \int_{B_1}^{B_2} f(x)\,dx = F(B_1) + \int_{B_1}^{B_2} f(x)\,dx \tag{4}
\end{gather}
$$

Subtracting $F(B_1)$ from both sides of step 4 yields:
$$
\begin{gather}
F(B_2) - F(B_1) = \int_{B_1}^{B_2} f(x)\,dx \tag{5}
\end{gather}
$$

By the non-negativity hypothesis of step 1, $f(x) \ge 0$ for all $x \in [B_1, B_2]$. By the order-preserving (positivity) property of the Riemann integral:
$$
\begin{gather}
\int_{B_1}^{B_2} f(x)\,dx \ge \int_{B_1}^{B_2} 0\,dx = 0 \tag{6}
\end{gather}
$$

Substituting the inequality of step 6 into step 5 yields:
$$
\begin{gather}
F(B_2) - F(B_1) \ge 0 \iff F(B_2) \ge F(B_1) \tag{7}
\end{gather}
$$

Because step 7 holds for every pair of points with $a \le B_1 < B_2$, the accumulation function $F$ is monotonically non-decreasing on $[a, \infty)$.

---
# Step 2
Assume that the improper integral $\int_a^\infty f(x)\,dx$ converges. By definition, this means that the limit of $F(B)$ as $B \to \infty$ exists and is a finite real number:
$$
\begin{gather}
I := \lim_{B \to \infty} F(B) \in \mathbb{R} \tag{8}
\end{gather}
$$

Setting $\varepsilon = 1$ in the definition of the functional limit at infinity, there exists a threshold $B_0 \ge a$ such that:
$$
\begin{gather}
B > B_0 \implies |F(B) - I| < 1 \tag{9}
\end{gather}
$$

The triangle inequality applied to step 9 implies:
$$
\begin{gather}
F(B) < I + 1 \quad \text{for all } B > B_0 \tag{10}
\end{gather}
$$

For parameters $B \in [a, B_0]$, the monotonicity property established in step 7 guarantees:
$$
\begin{gather}
F(B) \le F(B_0) \tag{11}
\end{gather}
$$

Applying step 7 with $B_0 < B_0 + 1$ and using step 10 evaluated at $B = B_0 + 1$:
$$
\begin{gather}
F(B_0) \le F(B_0 + 1) < I + 1 \tag{12}
\end{gather}
$$

Combining step 10, step 11, and step 12 shows that for all $B \in [a, \infty)$:
$$
\begin{gather}
F(B) \le I + 1 \tag{13}
\end{gather}
$$

Hence, the image set $S := \{F(B) : B \ge a\} \subset \mathbb{R}$ is bounded from above by $I + 1$. This completes the proof of necessity.

---
# Step 3
Assume that the accumulation function $F(B)$ is bounded from above on $[a, \infty)$. That is, there exists a constant $K \in \mathbb{R}$ such that:
$$
\begin{gather}
F(B) \le K \quad \text{for all } B \ge a \tag{14}
\end{gather}
$$

Define the image set of accumulation values:
$$
\begin{gather}
S := \{F(B) : B \ge a\} \subset \mathbb{R} \tag{15}
\end{gather}
$$

The set $S$ is non-empty because $F(a) = \int_a^a f(x)\,dx = 0 \in S$. By step 14, $S$ is bounded from above by $K$.

By the Completeness Axiom (Least Upper Bound Property) of the real number system $\mathbb{R}$, every non-empty subset of $\mathbb{R}$ that is bounded from above admits a unique supremum in $\mathbb{R}$:
$$
\begin{gather}
M := \sup S = \sup_{B \ge a} F(B) \in \mathbb{R} \tag{16}
\end{gather}
$$

It will now be demonstrated that $\lim_{B \to \infty} F(B) = M$.

Let $\varepsilon > 0$ be arbitrary. Because $M$ is the least upper bound of $S$, the shifted value $M - \varepsilon$ is strictly less than $M$, and consequently cannot be an upper bound for $S$.

Therefore, there exists an element $F(B_0) \in S$ with $B_0 \ge a$ such that:
$$
\begin{gather}
F(B_0) > M - \varepsilon \tag{17}
\end{gather}
$$

Because $F$ is monotonically non-decreasing by step 7, for every $B \ge B_0$:
$$
\begin{gather}
F(B) \ge F(B_0) > M - \varepsilon \tag{18}
\end{gather}
$$

Simultaneously, because $M$ is an upper bound for the set $S$:
$$
\begin{gather}
F(B) \le M < M + \varepsilon \quad \text{for all } B \ge a \tag{19}
\end{gather}
$$

Combining step 18 and step 19 yields the two-sided inequality for all $B \ge B_0$:
$$
\begin{gather}
M - \varepsilon < F(B) \le M < M + \varepsilon \tag{20}
\end{gather}
$$

Subtracting $M$ across all terms of step 20:
$$
\begin{gather}
-\varepsilon < F(B) - M \le 0 < \varepsilon \implies |F(B) - M| < \varepsilon \tag{21}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a threshold $B_0 \ge a$ such that step 21 holds for all $B \ge B_0$, the definition of functional limits at infinity is satisfied:
$$
\begin{gather}
\lim_{B \to \infty} F(B) = M = \sup_{B \ge a} \int_a^B f(x)\,dx \tag{22}
\end{gather}
$$

This establishes that $\int_a^\infty f(x)\,dx$ converges finitely, with its value given by $\sup_{B \ge a} F(B)$.

---
# Step 4
Suppose that the accumulation function $F(B)$ is not bounded from above on $[a, \infty)$.

By definition of an unbounded set, for every positive real number $E > 0$, there exists an evaluation point $B_0 \ge a$ such that:
$$
\begin{gather}
F(B_0) > E \tag{23}
\end{gather}
$$

Applying the monotonicity relation of step 7, for all $B \ge B_0$:
$$
\begin{gather}
F(B) \ge F(B_0) > E \tag{24}
\end{gather}
$$

Because for every $E > 0$ there exists $B_0 \ge a$ such that $F(B) > E$ for all $B \ge B_0$, the definition of divergence to positive infinity is satisfied:
$$
\begin{gather}
\lim_{B \to \infty} F(B) = \lim_{B \to \infty} \int_a^B f(x)\,dx = +\infty \tag{25}
\end{gather}
$$

Thus, oscillation is impossible for non-negative integrands: the improper integral either converges to a finite positive real number or diverges strictly to $+\infty$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
