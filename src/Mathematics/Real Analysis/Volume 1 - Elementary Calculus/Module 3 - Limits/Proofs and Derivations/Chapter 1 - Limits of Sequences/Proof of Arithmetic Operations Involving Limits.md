---
dg-publish: true
---
Let $\{x_n\}$ and $\{y_n\}$ be two convergent sequences of real numbers with $\lim_{n \to \infty} x_n = A$ and $\lim_{n \to \infty} y_n = B$.

# Theorem 1
Let $\varepsilon > 0$ be arbitrary. By the definition of convergence applied to the positive tolerance $\frac{\varepsilon}{2} > 0$, there exists an index $N_1 \in \mathbb{N}$ such that $|x_n - A| < \frac{\varepsilon}{2}$ for all $n > N_1$, and there exists an index $N_2 \in \mathbb{N}$ such that $|y_n - B| < \frac{\varepsilon}{2}$ for all $n > N_2$.

Set $N := \max(N_1, N_2) \in \mathbb{N}$. For all $n > N$, applying the [[Proof of the Triangle Inequality|Triangle Inequality]] yields: 
$$
\begin{gather}
|(x_n + y_n) - (A + B)| = |(x_n - A) + (y_n - B)| \le |x_n - A| + |y_n - B| \tag{1}
\end{gather}
$$
Substituting the individual bounds into step 1 gives, for all $n > N$:
$$
\begin{gather}
|(x_n + y_n) - (A + B)| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{2}
\end{gather}
$$
Thus, $\lim_{n \to \infty} (x_n + y_n) = A + B$.

---
# Theorem 2
Because $\{x_n\}$ converges to $A$, the [[Proof of the Basic Properties of Limits|basic properties of limits]] guarantee that $\{x_n\}$ is bounded: there exists a real constant $M > 0$ such that $|x_n| \le M$ for all $n \in \mathbb{N}$.

Let $\varepsilon > 0$ be arbitrary. Adding and subtracting the term $x_n B$ and applying the Triangle Inequality yields: 
$$
\begin{gather}
|x_n y_n - A B| = |x_n(y_n - B) + B(x_n - A)| \le |x_n||y_n - B| + |B||x_n - A| \tag{3}
\end{gather}
$$
Using the bound $|x_n| \le M$, step 3 becomes: 
$$
\begin{gather}
|x_n y_n - A B| \le M |y_n - B| + |B| |x_n - A| \tag{4}
\end{gather}
$$
Choose an index $N_1 \in \mathbb{N}$ such that $|y_n - B| < \frac{\varepsilon}{2M}$ for all $n > N_1$, and choose an index $N_2 \in \mathbb{N}$ such that $|x_n - A| < \frac{\varepsilon}{2(|B| + 1)}$ for all $n > N_2$, where $|B| + 1 > 0$ avoids division by zero. Setting $N := \max(N_1, N_2) \in \mathbb{N}$, it follows from step 4 that for all $n > N$:
$$
\begin{gather}
|x_n y_n - A B| < M \left(\frac{\varepsilon}{2M}\right) + |B| \left(\frac{\varepsilon}{2(|B| + 1)}\right) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{5}
\end{gather}
$$
Thus, $\lim_{n \to \infty} (x_n \cdot y_n) = A \cdot B$.

---
# Theorem 3
Suppose $B \neq 0$ and $y_n \neq 0$ for all $n \in \mathbb{N}$. It suffices to prove that $\lim_{n \to \infty} \frac{1}{y_n} = \frac{1}{B}$, because the full quotient rule follows by combining this result with Theorem 2.

Because $\lim_{n \to \infty} y_n = B \neq 0$, setting $\varepsilon_0 := \frac{|B|}{2} > 0$ in the definition of convergence guarantees the existence of an index $N_1 \in \mathbb{N}$ such that $|y_n - B| < \frac{|B|}{2}$ for all $n > N_1$. Applying the Reverse Triangle Inequality reveals that for all $n > N_1$:
$$
\begin{gather}
|y_n| = |B - (B - y_n)| \ge |B| - |y_n - B| > |B| - \frac{|B|}{2} = \frac{|B|}{2} \implies \frac{1}{|y_n|} < \frac{2}{|B|} \tag{6}
\end{gather}
$$
Now let $\varepsilon > 0$ be arbitrary. There exists an index $N_2 \in \mathbb{N}$ such that $|y_n - B| < \frac{\varepsilon |B|^2}{2}$ for all $n > N_2$. Setting $N := \max(N_1, N_2) \in \mathbb{N}$, it follows from step 6 that for all $n > N$:
$$
\begin{gather}
\left| \frac{1}{y_n} - \frac{1}{B} \right| = \frac{|B - y_n|}{|y_n| |B|} < \frac{2}{|B|^2} |y_n - B| < \frac{2}{|B|^2} \left( \frac{\varepsilon |B|^2}{2} \right) = \varepsilon \tag{7}
\end{gather}
$$
Thus, $\lim_{n \to \infty} \frac{1}{y_n} = \frac{1}{B}$, and applying Theorem 2 establishes that $\lim_{n \to \infty} \frac{x_n}{y_n} = \lim_{n \to \infty} \left(x_n \cdot \frac{1}{y_n}\right) = \frac{A}{B}$.

---
# Theorem 4
Let $c \in \mathbb{R}$ be a real constant. If $c = 0$, then $c x_n = 0$ for all $n \in \mathbb{N}$ and $c A = 0$, so $\lim_{n \to \infty} (0 \cdot x_n) = 0 = 0 \cdot A$ holds trivially by the convergence of constant sequences.

Suppose $c \neq 0$, so that $|c| > 0$, and let $\varepsilon > 0$ be arbitrary. Because $\frac{\varepsilon}{|c|} > 0$ and $\lim_{n \to \infty} x_n = A$, there exists an index $N \in \mathbb{N}$ such that for all $n > N$:
$$
\begin{gather}
|x_n - A| < \frac{\varepsilon}{|c|} \tag{8}
\end{gather}
$$
Multiplying both sides of step 8 by $|c| > 0$ yields, for all $n > N$:
$$
\begin{gather}
|c x_n - c A| = |c||x_n - A| < |c|\left(\frac{\varepsilon}{|c|}\right) = \varepsilon \tag{9}
\end{gather}
$$
Thus, $\lim_{n \to \infty} (c x_n) = c A$.

---
# Theorem 5
First, consider an integer exponent $p \in \mathbb{N}$. If $p = 1$, the claim holds by hypothesis. Suppose $p \ge 2$, and let $\varepsilon > 0$ be arbitrary. Because $\lim_{n \to \infty} x_n = A$, there exists an index $N_1 \in \mathbb{N}$ such that $|x_n - A| < 1$ for all $n > N_1$, which implies: 
$$
\begin{gather}
|x_n| \le |x_n - A| + |A| < 1 + |A| =: M \quad \forall n > N_1 \tag{10}
\end{gather}
$$
For any real numbers $x, y \in \mathbb{R}$ satisfying $|x| \le M$ and $|y| \le M$, factoring $x^p - y^p$ yields: 
$$
\begin{gather}
|x^p - y^p| = |x - y| \left| \sum_{k=0}^{p - 1} x^k y^{p-1-k} \right| \le |x - y| \sum_{k=0}^{p - 1} |x|^k |y|^{p-1-k} \le |x - y| p M^{p-1} \tag{11}
\end{gather}
$$
Setting $x = x_n$, $y = A$, and $M = 1 + |A|$ in step 11 gives, for all $n > N_1$:
$$
\begin{gather}
|x_n^p - A^p| \le |x_n - A| p(1 + |A|)^{p-1} \tag{12}
\end{gather}
$$
Choose an index $N_2 \in \mathbb{N}$ such that for all $n > N_2$:
$$
\begin{gather}
|x_n - A| < \frac{\varepsilon}{p(1 + |A|)^{p-1}} \tag{13}
\end{gather}
$$
Then for all $n > N := \max(N_1, N_2)$, combining step 12 and step 13 demonstrates that $|x_n^p - A^p| < \varepsilon$, proving that $\lim_{n \to \infty} x_n^p = A^p$ for all $p \in \mathbb{N}$.

For a general real exponent $p \in \mathbb{R}$ with $A > 0$ and $x_n > 0$ for all $n \in \mathbb{N}$, note that if $p = 0$, then $x_n^0 = 1 = A^0$. If $p \neq 0$, let $\varepsilon > 0$ be arbitrary. Because $\lim_{n \to \infty} \frac{x_n}{A} = 1$ by Theorem 3, define the sequence $z_n := \frac{x_n}{A} > 0$. By the [[Proof of Corollary of the Weierstrass Theorem|asymptotics of n-th roots]], $\lim_{k \to \infty} 2^{|p|/k} = 1$ and $\lim_{k \to \infty} 2^{-|p|/k} = 1$. Choose $k \in \mathbb{N}$ large enough that: 
$$
\begin{gather}
1 - \frac{\varepsilon}{A^p} < 2^{-\frac{|p|}{k}} < 1 < 2^{\frac{|p|}{k}} < 1 + \frac{\varepsilon}{A^p} \tag{14}
\end{gather}
$$
Because $\lim_{n \to \infty} z_n = 1$ and $2^{-1/k} < 1 < 2^{1/k}$, there exists an index $N \in \mathbb{N}$ such that $2^{-1/k} < z_n < 2^{1/k}$ for all $n > N$. Raising this inequality to the power $p$ and applying step 14 yields, for all $n > N$:
$$
\begin{gather}
1 - \frac{\varepsilon}{A^p} < z_n^p < 1 + \frac{\varepsilon}{A^p} \implies |z_n^p - 1| < \frac{\varepsilon}{A^p} \tag{15}
\end{gather}
$$
Multiplying step 15 by $A^p > 0$ produces $|x_n^p - A^p| < \varepsilon$ for all $n > N$. Thus, $\lim_{n \to \infty} x_n^p = A^p$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
