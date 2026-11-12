---
dg-publish: true
---
Let $\mathbb{C}$ denote the set $\mathbb{R}^2 = \{(x, y) : x, y \in \mathbb{R}\}$ equipped with componentwise addition:
$$
\begin{gather}
(x_1, y_1) + (x_2, y_2) := (x_1 + x_2, y_1 + y_2) \tag{1}
\end{gather}
$$
and multiplication defined by:
$$
\begin{gather}
(x_1, y_1) \cdot (x_2, y_2) := (x_1 x_2 - y_1 y_2, \, x_1 y_2 + x_2 y_1) \tag{2}
\end{gather}
$$
The additive identity is $0_{\mathbb{C}} := (0, 0)$ and the multiplicative identity is $1_{\mathbb{C}} := (1, 0)$. The Euclidean modulus mapping $|\cdot| : \mathbb{C} \to [0, \infty)$ is given by:
$$
\begin{gather}
|z| = |(x, y)| := \sqrt{x^2 + y^2} \tag{3}
\end{gather}
$$
inducing the canonical Euclidean metric $d(z_1, z_2) := |z_1 - z_2|$.

---
# Proposition 1
The algebraic structure $(\mathbb{C}, +, \cdot)$ satisfies all axioms of an algebraic field.

Let $z_1 = (x_1, y_1)$, $z_2 = (x_2, y_2)$, and $z_3 = (x_3, y_3)$ be arbitrary elements of $\mathbb{C}$.

First, the commutativity and associativity of addition follow directly from the corresponding properties of addition in the real field $\mathbb{R}$:
$$
\begin{gather}
z_1 + z_2 = (x_1 + x_2, y_1 + y_2) = (x_2 + x_1, y_2 + y_1) = z_2 + z_1 \tag{4}
\end{gather}
$$
and
$$
\begin{gather}
(z_1 + z_2) + z_3 = ((x_1 + x_2) + x_3, (y_1 + y_2) + y_3) = (x_1 + (x_2 + x_3), y_1 + (y_2 + y_3)) = z_1 + (z_2 + z_3) \tag{5}
\end{gather}
$$
The element $0_{\mathbb{C}} = (0, 0)$ satisfies $z_1 + 0_{\mathbb{C}} = (x_1 + 0, y_1 + 0) = (x_1, y_1) = z_1$. For every $z_1 = (x_1, y_1)$, the unique additive inverse is $-z_1 := (-x_1, -y_1) \in \mathbb{C}$, satisfying $z_1 + (-z_1) = (x_1 - x_1, y_1 - y_1) = (0, 0)$. Thus, $(\mathbb{C}, +)$ is an abelian group.

Next, multiplication is commutative:
$$
\begin{gather}
z_1 \cdot z_2 = (x_1 x_2 - y_1 y_2, \, x_1 y_2 + x_2 y_1) = (x_2 x_1 - y_2 y_1, \, x_2 y_1 + x_1 y_2) = z_2 \cdot z_1 \tag{6}
\end{gather}
$$
Multiplication is associative. Computing $(z_1 \cdot z_2) \cdot z_3$ gives:
$$
\begin{gather}
(x_1 x_2 - y_1 y_2, \, x_1 y_2 + x_2 y_1) \cdot (x_3, y_3) \tag{7}
\end{gather}
$$
Evaluating the first component of step 7 yields:
$$
\begin{gather}
(x_1 x_2 - y_1 y_2) x_3 - (x_1 y_2 + x_2 y_1) y_3 = x_1 x_2 x_3 - y_1 y_2 x_3 - x_1 y_2 y_3 - x_2 y_1 y_3 \tag{8}
\end{gather}
$$
Evaluating the second component of step 7 yields:
$$
\begin{gather}
(x_1 x_2 - y_1 y_2) y_3 + (x_1 y_2 + x_2 y_1) x_3 = x_1 x_2 y_3 - y_1 y_2 y_3 + x_1 y_2 x_3 + x_2 y_1 x_3 \tag{9}
\end{gather}
$$
Similarly, computing $z_1 \cdot (z_2 \cdot z_3)$ produces:
$$
\begin{gather}
(x_1, y_1) \cdot (x_2 x_3 - y_2 y_3, \, x_2 y_3 + x_3 y_2) \tag{10}
\end{gather}
$$
The first component of step 10 is:
$$
\begin{gather}
x_1(x_2 x_3 - y_2 y_3) - y_1(x_2 y_3 + x_3 y_2) = x_1 x_2 x_3 - x_1 y_2 y_3 - y_1 x_2 y_3 - y_1 y_2 x_3 \tag{11}
\end{gather}
$$
which is identical to step 8. The second component of step 10 is:
$$
\begin{gather}
x_1(x_2 y_3 + x_3 y_2) + y_1(x_2 x_3 - y_2 y_3) = x_1 x_2 y_3 + x_1 x_3 y_2 + y_1 x_2 x_3 - y_1 y_2 y_3 \tag{12}
\end{gather}
$$
which is identical to step 9. Hence $(z_1 \cdot z_2) \cdot z_3 = z_1 \cdot (z_2 \cdot z_3)$.

The element $1_{\mathbb{C}} = (1, 0)$ satisfies:
$$
\begin{gather}
z_1 \cdot 1_{\mathbb{C}} = (x_1 \cdot 1 - y_1 \cdot 0, \, x_1 \cdot 0 + y_1 \cdot 1) = (x_1, y_1) = z_1 \tag{13}
\end{gather}
$$
For any nonzero element $z_1 = (x_1, y_1) \neq (0, 0)$, at least one of $x_1, y_1$ is nonzero, implying $x_1^2 + y_1^2 > 0$. Define:
$$
\begin{gather}
z_1^{-1} := \left(\frac{x_1}{x_1^2 + y_1^2}, \, \frac{-y_1}{x_1^2 + y_1^2}\right) \tag{14}
\end{gather}
$$
Multiplying $z_1$ by $z_1^{-1}$ yields:
$$
\begin{gather}
z_1 \cdot z_1^{-1} = \left(x_1 \frac{x_1}{x_1^2 + y_1^2} - y_1 \frac{-y_1}{x_1^2 + y_1^2}, \, x_1 \frac{-y_1}{x_1^2 + y_1^2} + y_1 \frac{x_1}{x_1^2 + y_1^2}\right) = \left(\frac{x_1^2 + y_1^2}{x_1^2 + y_1^2}, \, 0\right) = (1, 0) = 1_{\mathbb{C}} \tag{15}
\end{gather}
$$
Thus every nonzero element has a unique multiplicative inverse in $\mathbb{C}$.

Finally, the distributive law $z_1 \cdot (z_2 + z_3) = z_1 \cdot z_2 + z_1 \cdot z_3$ holds:
$$
\begin{gather}
z_1 \cdot (z_2 + z_3) = (x_1, y_1) \cdot (x_2 + x_3, y_2 + y_3) = (x_1(x_2 + x_3) - y_1(y_2 + y_3), \, x_1(y_2 + y_3) + y_1(x_2 + x_3)) \tag{16}
\end{gather}
$$
Expanding by the distributivity of real numbers:
$$
\begin{gather}
(x_1 x_2 - y_1 y_2 + x_1 x_3 - y_1 y_3, \, x_1 y_2 + x_2 y_1 + x_1 y_3 + x_3 y_1) = z_1 \cdot z_2 + z_1 \cdot z_3 \tag{17}
\end{gather}
$$
Therefore, $(\mathbb{C}, +, \cdot)$ satisfies all field axioms.

---
# Proposition 2
The metric space $(\mathbb{C}, d)$ is complete: every Cauchy sequence in $\mathbb{C}$ converges to a limit in $\mathbb{C}$.

Let $(z_n)_{n=1}^\infty$ be a Cauchy sequence in $(\mathbb{C}, d)$, where $z_n = (x_n, y_n) \in \mathbb{R}^2$ with $x_n = \text{Re}(z_n)$ and $y_n = \text{Im}(z_n)$.

By definition of a Cauchy sequence, for every $\varepsilon > 0$, there exists an integer $N \in \mathbb{N}$ such that for all $n, m \ge N$:
$$
\begin{gather}
|z_n - z_m| = \sqrt{(x_n - x_m)^2 + (y_n - y_m)^2} < \varepsilon \tag{18}
\end{gather}
$$
For every $n, m \in \mathbb{N}$, the inequalities:
$$
\begin{gather}
|x_n - x_m| \le \sqrt{(x_n - x_m)^2 + (y_n - y_m)^2} = |z_n - z_m| \tag{19}
\end{gather}
$$
and
$$
\begin{gather}
|y_n - y_m| \le \sqrt{(x_n - x_m)^2 + (y_n - y_m)^2} = |z_n - z_m| \tag{20}
\end{gather}
$$
hold by the non-negativity of squared real numbers. Consequently, for all $n, m \ge N$:
$$
\begin{gather}
|x_n - x_m| < \varepsilon \quad \text{and} \quad |y_n - y_m| < \varepsilon \tag{21}
\end{gather}
$$
This demonstrates that $(x_n)_{n=1}^\infty$ and $(y_n)_{n=1}^\infty$ are Cauchy sequences in $\mathbb{R}$.

By the metric completeness of the real field $\mathbb{R}$, every Cauchy sequence in $\mathbb{R}$ converges. Thus, there exist real numbers $x^*, y^* \in \mathbb{R}$ such that:
$$
\begin{gather}
\lim_{n \to \infty} x_n = x^* \quad \text{and} \quad \lim_{n \to \infty} y_n = y^* \tag{22}
\end{gather}
$$
Define $z^* := (x^*, y^*) \in \mathbb{C}$. For the given $\varepsilon > 0$, choose $N_1 \in \mathbb{N}$ such that $|x_n - x^*| < \frac{\varepsilon}{\sqrt{2}}$ for all $n \ge N_1$, and choose $N_2 \in \mathbb{N}$ such that $|y_n - y^*| < \frac{\varepsilon}{\sqrt{2}}$ for all $n \ge N_2$. Setting $N_0 := \max\{N_1, N_2\}$, for all $n \ge N_0$:
$$
\begin{gather}
|z_n - z^*| = \sqrt{(x_n - x^*)^2 + (y_n - y^*)^2} < \sqrt{\left(\frac{\varepsilon}{\sqrt{2}}\right)^2 + \left(\frac{\varepsilon}{\sqrt{2}}\right)^2} = \sqrt{\frac{\varepsilon^2}{2} + \frac{\varepsilon^2}{2}} = \varepsilon \tag{23}
\end{gather}
$$
Hence $\lim_{n \to \infty} z_n = z^*$ in $(\mathbb{C}, d)$. Because every Cauchy sequence in $\mathbb{C}$ converges to a limit in $\mathbb{C}$, the metric space $(\mathbb{C}, d)$ is complete.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$