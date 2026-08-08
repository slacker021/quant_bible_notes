---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be a sequence of real numbers.

# Theorem 1
Let $\{x_n\}$ be an ultimately constant sequence. By definition, there exist a real number $A \in \mathbb{R}$ and an index $N \in \mathbb{N}$ such that $x_n = A$ for all $n > N$. Let $\varepsilon > 0$ be arbitrary. For every index $n > N$, the absolute difference between $x_n$ and $A$ evaluates to: 
$$
\begin{gather}
|x_n - A| = |A - A| = 0 < \varepsilon \quad \forall n > N \tag{1}
\end{gather}
$$
Because $|x_n - A| < \varepsilon$ holds for all $n > N$, the sequence $\{x_n\}$ converges to $A$.

---
# Theorem 2
Let $\{x_n\}$ be a sequence converging to a limit $A \in \mathbb{R}$, and consider an arbitrary neighborhood $V$ of $A$. By definition of a neighborhood in $\mathbb{R}$, $V$ contains an open $\varepsilon$-ball $U_\varepsilon(A) := (A - \varepsilon, A + \varepsilon)$ for some radius $\varepsilon > 0$. By the definition of sequence convergence, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
|x_n - A| < \varepsilon \iff A - \varepsilon < x_n < A + \varepsilon \iff x_n \in (A - \varepsilon, A + \varepsilon) \subset V \tag{2}
\end{gather}
$$
Consequently, for all $n > N$, every term $x_n$ belongs to $V$. Only the initial terms $x_1, x_2, \dots, x_N$ can possibly lie outside $V$. Because $N \in \mathbb{N}$ is finite, at most finitely many terms of the sequence lie outside the neighborhood $V$.

---
# Theorem 3
Assume, for the sake of contradiction, that a sequence $\{x_n\}$ converges simultaneously to two distinct limits $A \in \mathbb{R}$ and $B \in \mathbb{R}$ with $A \neq B$. Define the positive tolerance: 
$$
\begin{gather}
\varepsilon := \frac{|A - B|}{2} > 0 \tag{3}
\end{gather}
$$
By the definition of convergence, there exists an index $N_1 \in \mathbb{N}$ such that $|x_n - A| < \varepsilon$ for all $n > N_1$, and there exists an index $N_2 \in \mathbb{N}$ such that $|x_n - B| < \varepsilon$ for all $n > N_2$. Set $N := \max(N_1, N_2) \in \mathbb{N}$, and select an arbitrary index $n > N$. Applying the [[Proof of the Triangle Inequality|Triangle Inequality]] yields: 
$$
\begin{gather}
|A - B| = |(A - x_n) + (x_n - B)| \le |x_n - A| + |x_n - B| \tag{4}
\end{gather}
$$
Substituting the convergence bounds for $n > N$ into step 4 yields
$$
\begin{gather}
|A - B| < \varepsilon + \varepsilon = 2\varepsilon \tag{5}
\end{gather}
$$
By definition of $\varepsilon$ in step 3, $2\varepsilon = |A - B|$, so step 5 implies $|A - B| < |A - B|$, which is an impossible contradiction. Therefore, the assumption $A \neq B$ is false, and the limit of a convergent sequence is unique.

---
# Theorem 4
Let $\{x_n\}$ be a sequence converging to a finite limit $A \in \mathbb{R}$. Instantiating the definition of convergence with $\varepsilon = 1 > 0$ guarantees the existence of an index $N \in \mathbb{N}$ such that $|x_n - A| < 1$ for all $n > N$. By the Reverse Triangle Inequality, for every $n > N$:
$$
\begin{gather}
|x_n| - |A| \le |x_n - A| < 1 \implies |x_n| < |A| + 1 \quad \forall n > N \tag{6}
\end{gather}
$$
To construct a uniform bound across all indices $n \in \mathbb{N}$, define the positive real constant: 
$$
\begin{gather}
M := \max(|x_1|, |x_2|, \dots, |x_N|, |A| + 1) > 0 \tag{7}
\end{gather}
$$
For $1 \le n \le N$, $|x_n| \le \max(|x_1|, \dots, |x_N|) \le M$. For $n > N$, step 6 demonstrates that $|x_n| < |A| + 1 \le M$. Thus, $|x_n| \le M$ holds for all $n \in \mathbb{N}$, proving that $\{x_n\}$ is bounded.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
