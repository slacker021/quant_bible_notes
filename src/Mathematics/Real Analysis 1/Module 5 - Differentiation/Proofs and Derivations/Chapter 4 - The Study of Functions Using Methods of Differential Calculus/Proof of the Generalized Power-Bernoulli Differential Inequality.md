---
dg-publish: true
---
Let $\alpha \in \mathbb{R} \setminus \{0, 1\}$, and consider the auxiliary real-valued function $\varphi: (0, \infty) \to \mathbb{R}$ defined by:
$$
\begin{gather}
\varphi(x) := x^\alpha - \alpha x + \alpha - 1 \tag{1}
\end{gather}
$$

The function $\varphi$ is infinitely differentiable on the open ray $(0, \infty)$. Differentiating step 1 with respect to $x$ yields:
$$
\begin{gather}
\varphi'(x) = \alpha x^{\alpha - 1} - \alpha = \alpha \left(x^{\alpha - 1} - 1\right) \tag{2}
\end{gather}
$$
The value of $\varphi$ at $x = 1$ is:
$$
\begin{gather}
\varphi(1) = 1^\alpha - \alpha(1) + \alpha - 1 = 0 \tag{3}
\end{gather}
$$
Furthermore, evaluating step 2 at $x = 1$ shows that $x = 1$ is a stationary point:
$$
\begin{gather}
\varphi'(1) = \alpha(1 - 1) = 0 \tag{4}
\end{gather}
$$

---
# Proposition 1
Suppose that $0 < \alpha < 1$.

In this regime, the exponent $\alpha - 1$ is strictly negative:
$$
\begin{gather}
\alpha - 1 < 0 \tag{5}
\end{gather}
$$
Because the exponent is negative, the power mapping $x \mapsto x^{\alpha - 1}$ is strictly decreasing on $(0, \infty)$. Evaluating this power mapping relative to $x = 1$ produces:
$$
\begin{gather}
x \in (0, 1) \implies x^{\alpha - 1} > 1^{\alpha - 1} = 1 \implies x^{\alpha - 1} - 1 > 0 \tag{6}
\end{gather}
$$
$$
\begin{gather}
x \in (1, \infty) \implies x^{\alpha - 1} < 1^{\alpha - 1} = 1 \implies x^{\alpha - 1} - 1 < 0 \tag{7}
\end{gather}
$$

Because $\alpha > 0$, multiplying the inequalities of step 6 and step 7 by $\alpha$ reveals the sign of the derivative in step 2:
$$
\begin{gather}
\varphi'(x) > 0, \quad \forall x \in (0, 1) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\varphi'(x) < 0, \quad \forall x \in (1, \infty) \tag{9}
\end{gather}
$$

By virtue of [[Proof of Differential Criteria for Interval Monotonicity|Differential Criteria for Interval Monotonicity]], step 8 implies that $\varphi$ is strictly increasing on $(0, 1]$, and step 9 implies that $\varphi$ is strictly decreasing on $[1, \infty)$.

Consequently, for any $x \in (0, 1)$, strict monotonicity entails:
$$
\begin{gather}
\varphi(x) < \varphi(1) = 0 \tag{10}
\end{gather}
$$
Similarly, for any $x \in (1, \infty)$, strict monotonicity entails:
$$
\begin{gather}
\varphi(x) < \varphi(1) = 0 \tag{11}
\end{gather}
$$
Combining step 10 and step 11 demonstrates that for all $x \in (0, \infty) \setminus \{1\}$:
$$
\begin{gather}
x^\alpha - \alpha x + \alpha - 1 < 0 \tag{12}
\end{gather}
$$

---
# Proposition 2
Suppose that $\alpha < 0$ or $\alpha > 1$.

**Case 1: $\alpha > 1$.**
In this case, $\alpha - 1 > 0$. The mapping $x \mapsto x^{\alpha - 1}$ is strictly increasing on $(0, \infty)$. Therefore:
$$
\begin{gather}
x \in (0, 1) \implies x^{\alpha - 1} < 1 \implies x^{\alpha - 1} - 1 < 0 \tag{13}
\end{gather}
$$
$$
\begin{gather}
x \in (1, \infty) \implies x^{\alpha - 1} > 1 \implies x^{\alpha - 1} - 1 > 0 \tag{14}
\end{gather}
$$
Because $\alpha > 0$, step 2 yields:
$$
\begin{gather}
\varphi'(x) < 0 \text{ on } (0, 1) \quad \text{and} \quad \varphi'(x) > 0 \text{ on } (1, \infty) \tag{15}
\end{gather}
$$
Thus, $\varphi$ is strictly decreasing on $(0, 1]$ and strictly increasing on $[1, \infty)$, achieving its unique strict global minimum at $x = 1$. Consequently:
$$
\begin{gather}
\varphi(x) > \varphi(1) = 0, \quad \forall x \in (0, \infty) \setminus \{1\} \tag{16}
\end{gather}
$$

**Case 2: $\alpha < 0$.**
In this case, $\alpha - 1 < -1 < 0$. The mapping $x \mapsto x^{\alpha - 1}$ is strictly decreasing on $(0, \infty)$. Therefore:
$$
\begin{gather}
x \in (0, 1) \implies x^{\alpha - 1} - 1 > 0 \tag{17}
\end{gather}
$$
$$
\begin{gather}
x \in (1, \infty) \implies x^{\alpha - 1} - 1 < 0 \tag{18}
\end{gather}
$$
Because $\alpha < 0$, multiplying the inequalities of step 17 and step 18 by the negative scalar $\alpha$ reverses the inequality signs:
$$
\begin{gather}
\varphi'(x) = \alpha(x^{\alpha - 1} - 1) < 0 \text{ on } (0, 1) \quad \text{and} \quad \varphi'(x) > 0 \text{ on } (1, \infty) \tag{19}
\end{gather}
$$
Once again, $\varphi$ decreases strictly on $(0, 1]$ and increases strictly on $[1, \infty)$, reaching a unique strict global minimum at $x = 1$:
$$
\begin{gather}
\varphi(x) > \varphi(1) = 0, \quad \forall x \in (0, \infty) \setminus \{1\} \tag{20}
\end{gather}
$$
Step 16 and step 20 establish that for all $\alpha \in (-\infty, 0) \cup (1, \infty)$ and all $x \in (0, \infty) \setminus \{1\}$:
$$
\begin{gather}
x^\alpha - \alpha x + \alpha - 1 > 0 \tag{21}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
