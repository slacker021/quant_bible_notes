---
dg-publish: true
---
Let $r \in \mathbb{R}$ be a real number, and consider the geometric sequence $\{r^n\}_{n=0}^\infty$.

**Case 1 ($0 < r < 1$):**
Because $0 < r < 1$, multiplying by $r^n > 0$ yields $r^{n+1} < r^n$ for all $n \in \mathbb{N} \cup \{0\}$, proving that $\{r^n\}$ is strictly decreasing. Furthermore, $r^n > 0$ holds for all $n$, so the sequence is bounded below by $0$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], $\{r^n\}$ converges to a finite real limit $A := \lim_{n \to \infty} r^n \ge 0$.

By the [[Proof of Arithmetic Operations Involving Limits|scalar multiple rule for limits]], the sequence $\{r^{n+1}\}$ satisfies:
$$
\begin{gather}
\lim_{n \to \infty} r^{n+1} = \lim_{n \to \infty} (r \cdot r^n) = r \lim_{n \to \infty} r^n = r A \tag{1}
\end{gather}
$$
Because $\{r^{n+1}\}$ is a subsequence of $\{r^n\}$, it must converge to the identical limit $A$. Equating both limits in step 1 yields:
$$
\begin{gather}
A = r A \iff A(1 - r) = 0 \tag{2}
\end{gather}
$$
Because $r \neq 1$, step 2 requires that $A = 0$. Thus, $\lim_{n \to \infty} r^n = 0$ for all $0 < r < 1$.

**Case 2 ($r = 0$):**
For $r = 0$, $r^0 = 1$ and $r^n = 0$ for all $n \ge 1$. The sequence is ultimately constant, so by the [[Proof of the Basic Properties of Limits|basic properties of limits]], $\lim_{n \to \infty} r^n = 0$.

**Case 3 ($-1 < r < 0$):**
Here $0 < |r| < 1$. Applying Case 1 to the absolute value sequence yields $\lim_{n \to \infty} |r^n| = \lim_{n \to \infty} |r|^n = 0$. By the [[Proof of the Corollary for the Squeeze Theorem of Limits|Vanishing of Absolute Values Corollary]], $\lim_{n \to \infty} |r^n| = 0 \iff \lim_{n \to \infty} r^n = 0$. Thus, $\lim_{n \to \infty} r^n = 0$ for all $-1 < r < 0$.

**Case 4 ($r = 1$):**
For $r = 1$, $r^n = 1^n = 1$ for all $n \in \mathbb{N} \cup \{0\}$. Because this is a constant sequence, $\lim_{n \to \infty} 1^n = 1$.

**Case 5 ($r > 1$):**
Define the positive constant $h := r - 1 > 0$, so that $r = 1 + h$. By [[Proof of Bernoulli's Inequality|Bernoulli's Inequality]], for all $n \in \mathbb{N}$:
$$
\begin{gather}
r^n = (1 + h)^n \ge 1 + n h \tag{3}
\end{gather}
$$
Let $c \in \mathbb{R}$ be an arbitrary real number. By the [[Proof of Archimedian Corollaries|Principle of Archimedes]], there exists an index $N \in \mathbb{N}$ such that $N > \frac{c - 1}{h}$. For all $n > N$, step 3 yields:
$$
\begin{gather}
r^n \ge 1 + n h > 1 + N h > 1 + \left(\frac{c - 1}{h}\right) h = c \tag{4}
\end{gather}
$$
Step 4 proves that $r^n \to +\infty$ as $n \to \infty$. Thus, the sequence diverges.

**Case 6 ($r \le -1$):**
If $r = -1$, the sequence evaluates to $x_n = (-1)^n$, oscillating between $1$ and $-1$. The even-indexed subsequence satisfies $\lim_{n \to \infty} x_{2n} = \lim_{n \to \infty} 1 = 1$, whereas the odd-indexed subsequence satisfies $\lim_{n \to \infty} x_{2n+1} = \lim_{n \to \infty} (-1) = -1$. Because these two subsequences converge to distinct limits ($1 \neq -1$), the sequence diverges.

If $r < -1$, then $|r| > 1$. By Case 5, $|r^n| = |r|^n \to +\infty$. Because $\{r^n\}$ is unbounded, it cannot converge to any finite real limit by the [[Proof of the Basic Properties of Limits|boundedness property of convergent sequences]].

Combining all cases establishes that $\{r^n\}$ converges if and only if $-1 < r \le 1$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
