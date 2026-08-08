---
dg-publish: true
---
Let $\{x_n\}_{n=1}^\infty$ be a sequence of real numbers.

**Necessity ($\implies$):**
Assume that the sequence $\{x_n\}$ converges to a finite limit $A \in \mathbb{R}$, and let $\varepsilon > 0$ be arbitrary.

By the definition of convergence applied to the positive tolerance $\frac{\varepsilon}{2} > 0$, there exists an index $N \in \mathbb{N}$ such that $|x_n - A| < \frac{\varepsilon}{2}$ for all $n > N$. For any two indices $n > N$ and $m > N$, adding and subtracting $A$ within the absolute difference and applying the [[Proof of the Triangle Inequality|Triangle Inequality]] yields:
$$
\begin{gather}
|x_n - x_m| = |(x_n - A) + (A - x_m)| \le |x_n - A| + |x_m - A| \tag{1}
\end{gather}
$$
Substituting the convergence bounds into step 1 gives: 
$$
\begin{gather}
|x_n - x_m| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \quad \forall n, m > N \tag{2}
\end{gather}
$$
Therefore, $\{x_n\}$ is a Cauchy sequence.

**Sufficiency ($\impliedby$):**
Conversely, assume that $\{x_n\}$ is a Cauchy sequence. First, it is established that $\{x_n\}$ is bounded in $\mathbb{R}$.

Instantiating the Cauchy definition with $\varepsilon = 1 > 0$ guarantees the existence of an index $N_0 \in \mathbb{N}$ such that $|x_n - x_m| < 1$ for all $n, m > N_0$. Fixing $m = N_0 + 1 > N_0$, the Triangle Inequality reveals that for all $n > N_0$:
$$
\begin{gather}
|x_n| = |(x_n - x_{N_0+1}) + x_{N_0+1}| \le |x_n - x_{N_0+1}| + |x_{N_0+1}| < 1 + |x_{N_0+1}| \tag{3}
\end{gather}
$$
Defining the positive real constant: 
$$
\begin{gather}
M := \max(|x_1|, |x_2|, \dots, |x_{N_0}|, |x_{N_0+1}| + 1) > 0 \tag{4}
\end{gather}
$$
it follows from step 3 and step 4 that $|x_n| \le M$ for all $n \in \mathbb{N}$. Thus, $\{x_n\}$ is bounded.

By the [[Proof of the Bolzano-Weierstrass Lemma|Bolzano-Weierstrass Lemma]], the bounded sequence $\{x_n\}$ contains a subsequence $\{x_{n_k}\}_{k=1}^\infty$ that converges to some finite real limit $L \in \mathbb{R}$.

To prove that the parent sequence $\{x_n\}$ converges to $L$, let $\varepsilon > 0$ be arbitrary. Because $\{x_n\}$ is Cauchy, there exists an index $N_1 \in \mathbb{N}$ such that: 
$$
\begin{gather}
|x_n - x_m| < \frac{\varepsilon}{2} \quad \forall n, m > N_1 \tag{5}
\end{gather}
$$
Furthermore, because $\lim_{k \to \infty} x_{n_k} = L$, there exists an index $K \in \mathbb{N}$ such that: 
$$
\begin{gather}
|x_{n_k} - L| < \frac{\varepsilon}{2} \quad \forall k > K \tag{6}
\end{gather}
$$
Choose a fixed index $k > \max(K, N_1)$. Because $n_1 < n_2 < \dots < n_k$ is a strictly increasing sequence of natural numbers, induction establishes that $n_k \ge k > N_1$. For any index $n > N_1$, adding and subtracting the anchor term $x_{n_k}$ and applying the Triangle Inequality yields:
$$
\begin{gather}
|x_n - L| = |(x_n - x_{n_k}) + (x_{n_k} - L)| \le |x_n - x_{n_k}| + |x_{n_k} - L| \tag{7}
\end{gather}
$$
Because both $n > N_1$ and $n_k > N_1$, step 5 implies that $|x_n - x_{n_k}| < \frac{\varepsilon}{2}$. Because $k > K$, step 6 implies that $|x_{n_k} - L| < \frac{\varepsilon}{2}$. Substituting these bounds into step 7 produces:
$$
\begin{gather}
|x_n - L| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \quad \forall n > N_1 \tag{8}
\end{gather}
$$
Therefore, the sequence $\{x_n\}$ converges to $L$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
