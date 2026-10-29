---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $f: X \to \mathbb{R}$.

**Necessity ($\implies$):**
Assume that $f$ possesses a limit over $\mathcal{B}$, denoted $\lim_{\mathcal{B}} f(x) = A \in \mathbb{R}$.

Let $\varepsilon > 0$ be given. By definition of the limit, there exists an element $B \in \mathcal{B}$ such that:
$$
\begin{gather}
|f(x) - A| < \frac{\varepsilon}{2} \quad \forall x \in B \tag{1}
\end{gather}
$$
Let $x_1, x_2 \in B$ be arbitrary points. Applying the Triangle Inequality to step 1 yields:
$$
\begin{gather}
|f(x_1) - f(x_2)| = |(f(x_1) - A) + (A - f(x_2))| \le |f(x_1) - A| + |f(x_2) - A| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{2}
\end{gather}
$$
Taking the supremum over all pairs $x_1, x_2 \in B$ across step 2 gives:
$$
\begin{gather}
\omega(f, B) = \sup_{x_1, x_2 \in B} |f(x_1) - f(x_2)| \le \varepsilon \tag{3}
\end{gather}
$$
Replacing $\varepsilon$ with $\frac{\varepsilon}{2}$ in step 1 yields the strict bound $\omega(f, B) < \varepsilon$.

**Sufficiency ($\impliedby$):**
Conversely, assume that for every $\varepsilon > 0$, there exists an element $B \in \mathcal{B}$ such that $\omega(f, B) < \varepsilon$.

For each natural number $n \in \mathbb{N}$, choose an element $B_n' \in \mathcal{B}$ such that $\omega(f, B_n') < \frac{1}{n}$. Construct a nested sequence of base elements $\{B_n\}_{n=1}^\infty$ by setting $B_1 := B_1'$, and inductively selecting $B_{n+1} \in \mathcal{B}$ such that:
$$
\begin{gather}
B_{n+1} \subseteq B_n \cap B_{n+1}' \tag{4}
\end{gather}
$$
By virtue of step 4, $B_1 \supseteq B_2 \supseteq \dots \supseteq B_n \supseteq \dots$, and for each $n \in \mathbb{N}$:
$$
\begin{gather}
\omega(f, B_n) \le \omega(f, B_n') < \frac{1}{n} \tag{5}
\end{gather}
$$
For each $n \in \mathbb{N}$, choose a point $x_n \in B_n$ (which is non-empty by base axioms). For any indices $m \ge n$, because $B_m \subseteq B_n$, both $x_n$ and $x_m$ belong to $B_n$. By step 5:
$$
\begin{gather}
|f(x_n) - f(x_m)| \le \omega(f, B_n) < \frac{1}{n} \tag{6}
\end{gather}
$$
Step 6 proves that the image sequence $\{f(x_n)\}_{n=1}^\infty$ is a Cauchy sequence of real numbers. By the completeness of $\mathbb{R}$, there exists a real number $A \in \mathbb{R}$ such that:
$$
\begin{gather}
\lim_{n \to \infty} f(x_n) = A \tag{7}
\end{gather}
$$
It remains to show that $\lim_{\mathcal{B}} f(x) = A$. Let $\varepsilon > 0$ be given. Choose $N \in \mathbb{N}$ such that $\frac{1}{N} < \frac{\varepsilon}{2}$ and $|f(x_N) - A| < \frac{\varepsilon}{2}$.

For any point $x \in B_N$, because $x_N \in B_N$, step 5 implies that $|f(x) - f(x_N)| \le \omega(f, B_N) < \frac{1}{N} < \frac{\varepsilon}{2}$. Applying the Triangle Inequality yields:
$$
\begin{gather}
|f(x) - A| \le |f(x) - f(x_N)| + |f(x_N) - A| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \quad \forall x \in B_N \tag{8}
\end{gather}
$$
Because $B_N \in \mathcal{B}$, step 8 proves that $\lim_{\mathcal{B}} f(x) = A$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$