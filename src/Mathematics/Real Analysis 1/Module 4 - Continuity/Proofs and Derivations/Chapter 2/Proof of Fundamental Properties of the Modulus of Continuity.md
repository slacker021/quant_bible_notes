---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, and let $f: E \to \mathbb{R}$. 

Recall the definition of the modulus of continuity for $\delta > 0$:
$$
\begin{gather}
\omega_f(\delta) := \sup \big\{ |f(x_1) - f(x_2)| : x_1, x_2 \in E, \ |x_1 - x_2| \le \delta \big\} \tag{1}
\end{gather}
$$

---
# Proposition 1

Let $0 < \delta_1 \le \delta_2$. Define the sets of pairs:
$$
\begin{gather}
S(\delta) := \big\{ (x_1, x_2) \in E \times E : |x_1 - x_2| \le \delta \big\} \tag{2}
\end{gather}
$$

Because $\delta_1 \le \delta_2$, the condition $|x_1 - x_2| \le \delta_1$ immediately implies $|x_1 - x_2| \le \delta_2$. Therefore:
$$
\begin{gather}
S(\delta_1) \subseteq S(\delta_2) \tag{3}
\end{gather}
$$

Taking the supremum of $|f(x_1) - f(x_2)|$ over both sets in step 3:
$$
\begin{gather}
\omega_f(\delta_1) = \sup_{(x_1, x_2) \in S(\delta_1)} |f(x_1) - f(x_2)| \le \sup_{(x_1, x_2) \in S(\delta_2)} |f(x_1) - f(x_2)| = \omega_f(\delta_2) \tag{4}
\end{gather}
$$

Because $|f(x) - f(x)| = 0$ for any $x \in E$, $\omega_f(\delta) \ge 0$. Thus, $\omega_f$ is non-negative and monotonically non-decreasing.

---
# Proposition 2

Suppose $E = I$ is an interval in $\mathbb{R}$, and let $\delta_1, \delta_2 > 0$. Let $x_1, x_2 \in I$ satisfy $|x_1 - x_2| \le \delta_1 + \delta_2$. 

If $x_1 = x_2$, the inequality $|f(x_1) - f(x_2)| = 0 \le \omega_f(\delta_1) + \omega_f(\delta_2)$ holds immediately because $\omega_f \ge 0$. 

Assume without loss of generality that $x_1 < x_2$. Because $I$ is an interval, $[x_1, x_2] \subseteq I$. Define the intermediate point $x_3 := \min(x_1 + \delta_1, x_2) \in [x_1, x_2] \subseteq I$, which satisfies $0 \le x_3 - x_1 \le \delta_1$ and $0 \le x_2 - x_3 \le \delta_2$. 

Applying the triangle inequality:
$$
\begin{gather}
|f(x_1) - f(x_2)| \le |f(x_1) - f(x_3)| + |f(x_3) - f(x_2)| \tag{5}
\end{gather}
$$

By definition of the modulus of continuity on step 1:
$$
\begin{gather}
|f(x_1) - f(x_3)| \le \omega_f(\delta_1) \quad \text{and} \quad |f(x_3) - f(x_2)| \le \omega_f(\delta_2) \tag{6}
\end{gather}
$$

Substituting step 6 into step 5:
$$
\begin{gather}
|f(x_1) - f(x_2)| \le \omega_f(\delta_1) + \omega_f(\delta_2) \tag{7}
\end{gather}
$$

Taking the supremum over all qualifying pairs $(x_1, x_2) \in S(\delta_1 + \delta_2)$ yields the subadditivity condition:
$$
\begin{gather}
\omega_f(\delta_1 + \delta_2) \le \omega_f(\delta_1) + \omega_f(\delta_2) \tag{8}
\end{gather}
$$

---
# Proposition 3

**Necessity ($\implies$):** Assume $f$ is uniformly continuous on $E$. 

Let an arbitrary tolerance $\varepsilon > 0$ be given. By definition of uniform continuity, there exists $\delta > 0$ such that for all $x_1, x_2 \in E$, $|x_1 - x_2| < \delta$ implies $|f(x_1) - f(x_2)| < \frac{\varepsilon}{2}$. Setting $\delta_0 := \frac{\delta}{2} > 0$, any pair $x_1, x_2 \in E$ satisfying $|x_1 - x_2| \le \delta_0 < \delta$ satisfies $|f(x_1) - f(x_2)| < \frac{\varepsilon}{2}$. 

Taking the supremum over all such pairs yields:
$$
\begin{gather}
\omega_f(\delta_0) \le \frac{\varepsilon}{2} < \varepsilon \tag{9}
\end{gather}
$$

By Proposition 1, for all $0 < \delta < \delta_0$, $0 \le \omega_f(\delta) \le \omega_f(\delta_0) < \varepsilon$. 

Consequently:
$$
\begin{gather}
\lim_{\delta \to 0^+} \omega_f(\delta) = 0 \tag{10}
\end{gather}
$$

**Sufficiency ($\impliedby$):** Conversely, assume that $\lim_{\delta \to 0^+} \omega_f(\delta) = 0$. 

Let an arbitrary tolerance $\varepsilon > 0$ be given. There exists $\delta > 0$ such that $\omega_f(\delta) < \varepsilon$. 

For any elements $x_1, x_2 \in E$ satisfying $|x_1 - x_2| < \delta$, it follows from the definition of the supremum that:
$$
\begin{gather}
|f(x_1) - f(x_2)| \le \omega_f(\delta) < \varepsilon \tag{11}
\end{gather}
$$

This verifies that $f$ is uniformly continuous on $E$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
