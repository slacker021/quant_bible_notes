---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E \cap E'$. 

The equivalence of the five statements is established by constructing a closed deductive cycle of implications $(1) \implies (2) \implies (4) \implies (5) \implies (3) \implies (1)$.

**Implication (1) $\implies$ (2) (Cauchy Metric Bound implies Topological Neighborhoods):**
Assume statement 1 holds:
$$
\begin{gather}
\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon\big) \tag{1}
\end{gather}
$$

Let $V(f(a))$ be an arbitrary open neighborhood of $f(a)$ in $\mathbb{R}$. Because $V(f(a))$ is open, there exists an error tolerance $\varepsilon > 0$ such that the symmetric metric interval is entirely contained within $V(f(a))$:
$$
\begin{gather}
(f(a) - \varepsilon, f(a) + \varepsilon) \subseteq V(f(a)) \tag{2}
\end{gather}
$$

Applying step 1 to this $\varepsilon > 0$ yields a distance $\delta > 0$ such that for all $x \in E$, $|x - a| < \delta$ guarantees $|f(x) - f(a)| < \varepsilon$. 

Define the open neighborhood of $a$ in $\mathbb{R}$ by:
$$
\begin{gather}
U(a) := (a - \delta, a + \delta) \tag{3}
\end{gather}
$$

For any element $x \in U(a) \cap E$, the condition $|x - a| < \delta$ is satisfied. It follows that $|f(x) - f(a)| < \varepsilon$, which means $f(x) \in (f(a) - \varepsilon, f(a) + \varepsilon)$. Combining this result with step 2 demonstrates that:
$$
\begin{gather}
f(U(a) \cap E) \subseteq (f(a) - \varepsilon, f(a) + \varepsilon) \subseteq V(f(a)) \tag{4}
\end{gather}
$$
which establishes statement 2.

**Implication (2) $\implies$ (4) (Topological Neighborhoods implies Filter Base Limit):**
Assume statement 2 holds: for every open neighborhood $V(f(a))$ of $f(a)$ in $\mathbb{R}$, there exists an open neighborhood $U(a)$ of $a$ in $\mathbb{R}$ such that $f(U(a) \cap E) \subseteq V(f(a))$.

Consider the neighborhood filter base of $a$ restricted to the domain $E$:
$$
\begin{gather}
\mathcal{B}_a := \{U(a) \cap E \mid U(a) \text{ is an open neighborhood of } a \text{ in } \mathbb{R}\} \tag{5}
\end{gather}
$$

By definition, the limit of $f$ over the filter base $\mathcal{B}_a$ equals $f(a)$ if and only if for every open neighborhood $V(f(a))$ of $f(a)$, there exists an element $B \in \mathcal{B}_a$ such that:
$$
\begin{gather}
f(B) \subseteq V(f(a)) \tag{6}
\end{gather}
$$

Let $V(f(a))$ be an arbitrary open neighborhood of $f(a)$. By the hypothesis of statement 2, there exists an open neighborhood $U(a)$ of $a$ satisfying $f(U(a) \cap E) \subseteq V(f(a))$. 

Setting $B := U(a) \cap E$, it can be seen from step 5 that $B \in \mathcal{B}_a$, and step 6 is directly satisfied:
$$
\begin{gather}
\lim_{\mathcal{B}_a} f(x) = f(a) \tag{7}
\end{gather}
$$
which establishes statement 4.

**Implication (4) $\implies$ (5) (Filter Base Limit implies Cauchy Local Oscillation):**
Assume statement 4 holds. For each radius $\delta > 0$, let $U_\delta(a) := (a - \delta, a + \delta)$, and define the domain trace $X_\delta := U_\delta(a) \cap E$. The oscillation of $f$ on $X_\delta$ is:
$$
\begin{gather}
\omega(f; X_\delta) := \sup_{x_1, x_2 \in X_\delta} |f(x_1) - f(x_2)| = \sup_{x \in X_\delta} f(x) - \inf_{x \in X_\delta} f(x) \tag{8}
\end{gather}
$$

If $0 < \delta_1 < \delta_2$, then $X_{\delta_1} \subseteq X_{\delta_2}$, which implies that $\omega(f; X_{\delta_1}) \le \omega(f; X_{\delta_2})$. Because $\omega(f; X_\delta) \ge 0$ is a monotonically non-decreasing function of $\delta$, the one-sided limit as $\delta \to 0^+$ exists and equals its infimum over $\delta > 0$:
$$
\begin{gather}
\omega(f; a) = \lim_{\delta \to 0^+} \omega(f; X_\delta) = \inf_{\delta > 0} \omega(f; X_\delta) \ge 0 \tag{9}
\end{gather}
$$

To prove that this limit is zero, let an arbitrary tolerance $\varepsilon > 0$ be given. Consider the open neighborhood:
$$
\begin{gather}
V(f(a)) := \left(f(a) - \frac{\varepsilon}{3}, \ f(a) + \frac{\varepsilon}{3}\right) \tag{10}
\end{gather}
$$

By statement 4, there exists a base element $B = U(a) \cap E \in \mathcal{B}_a$ such that $f(B) \subseteq V(f(a))$. Because $U(a)$ is an open neighborhood of $a$, there exists a radius $\delta_0 > 0$ such that $U_{\delta_0}(a) \subseteq U(a)$, which guarantees that:
$$
\begin{gather}
X_{\delta_0} = U_{\delta_0}(a) \cap E \subseteq U(a) \cap E = B \tag{11}
\end{gather}
$$

Consequently, $f(X_{\delta_0}) \subseteq f(B) \subseteq V(f(a))$. For any two points $x_1, x_2 \in X_{\delta_0}$, the triangle inequality implies:
$$
\begin{gather}
|f(x_1) - f(x_2)| \le |f(x_1) - f(a)| + |f(a) - f(x_2)| < \frac{\varepsilon}{3} + \frac{\varepsilon}{3} = \frac{2\varepsilon}{3} \tag{12}
\end{gather}
$$

Taking the supremum over all pairs $x_1, x_2 \in X_{\delta_0}$ in step 12 yields:
$$
\begin{gather}
\omega(f; X_{\delta_0}) \le \frac{2\varepsilon}{3} < \varepsilon \tag{13}
\end{gather}
$$

By the monotonicity established in step 9, for all $0 < \delta < \delta_0$:
$$
\begin{gather}
0 \le \omega(f; X_\delta) \le \omega(f; X_{\delta_0}) < \varepsilon \tag{14}
\end{gather}
$$

Because $\varepsilon > 0$ was arbitrary, step 14 forces:
$$
\begin{gather}
\omega(f; a) = \lim_{\delta \to 0^+} \omega(f; U_\delta(a) \cap E) = 0 \tag{15}
\end{gather}
$$
which establishes statement 5.

**Implication (5) $\implies$ (3) (Cauchy Local Oscillation implies Heine Sequential Sampler):**
Assume statement 5 holds: $\omega(f; a) = 0$. 

Let $\{x_n\}_{n=1}^\infty$ be an arbitrary sequence of elements in $E$ that converges to $a$:
$$
\begin{gather}
\lim_{n \to \infty} x_n = a \tag{16}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given. Because $\lim_{\delta \to 0^+} \omega(f; U_\delta(a) \cap E) = 0$, there exists a distance $\delta > 0$ such that:
$$
\begin{gather}
\omega(f; U_\delta(a) \cap E) < \varepsilon \tag{17}
\end{gather}
$$

Because $a \in E$ and $|a - a| = 0 < \delta$, the point $a$ belongs to $U_\delta(a) \cap E$. 

By virtue of the convergence in step 16, there exists a natural threshold $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
|x_n - a| < \delta \implies x_n \in U_\delta(a) \cap E \tag{18}
\end{gather}
$$

Therefore, for all $n > N$, both $x_n$ and $a$ are elements of the set $U_\delta(a) \cap E$. 

Applying the definition of set oscillation together with step 17 yields:
$$
\begin{gather}
|f(x_n) - f(a)| \le \sup_{x_1, x_2 \in U_\delta(a) \cap E} |f(x_1) - f(x_2)| = \omega(f; U_\delta(a) \cap E) < \varepsilon \quad \forall n > N \tag{19}
\end{gather}
$$

Because $\varepsilon > 0$ was chosen arbitrarily, step 19 proves that:
$$
\begin{gather}
\lim_{n \to \infty} f(x_n) = f(a) \tag{20}
\end{gather}
$$
which establishes statement 3.

**Implication (3) $\implies$ (1) (Heine Sequential Sampler implies Cauchy Metric Bound):**
Assume statement 3 holds. The implication to statement 1 is established via proof by contraposition. 

Suppose that statement 1 is false. The logical negation of statement 1 asserts that there exists an error tolerance $\varepsilon_0 > 0$ such that for every distance $\delta > 0$, there exists at least one point $x \in E$ satisfying $|x - a| < \delta$ for which $|f(x) - f(a)| \ge \varepsilon_0$.

For each natural index $n \in \mathbb{N}$, set the candidate radius $\delta_n := \frac{1}{n} > 0$. By the Axiom of Countable Choice, select a corresponding point $x_n \in E$ satisfying:
$$
\begin{gather}
|x_n - a| < \frac{1}{n} \quad \text{and} \quad |f(x_n) - f(a)| \ge \varepsilon_0 \tag{21}
\end{gather}
$$

Because $\lim_{n \to \infty} \frac{1}{n} = 0$, applying the [[Proof of Inequalities Involving Limits|Squeeze Theorem]] to $0 \le |x_n - a| < \frac{1}{n}$ guarantees that:
$$
\begin{gather}
\lim_{n \to \infty} x_n = a \tag{22}
\end{gather}
$$

However, the second inequality of step 21 demonstrates that the terms of the image sequence $\{f(x_n)\}_{n=1}^\infty$ remain permanently separated from $f(a)$ by at least $\varepsilon_0 > 0$. Consequently:
$$
\begin{gather}
\lim_{n \to \infty} f(x_n) \neq f(a) \tag{23}
\end{gather}
$$

Step 22 and step 23 exhibit a sequence $\{x_n\} \subseteq E$ converging to $a$ whose image sequence fails to converge to $f(a)$, directly violating the Heine condition of statement 3. 

By contraposition, statement 3 implies statement 1. 

With all five implications established, the deductive ring $(1) \implies (2) \implies (4) \implies (5) \implies (3) \implies (1)$ is closed, and the five pillars of continuity are logically equivalent.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$