---
dg-publish: true
---
Let $\{x_n\}$ be a sequence of real numbers.

---
# Theorem 1
Assume that $\{x_n\}$ is nondecreasing, meaning $x_n \le x_{n+1}$ for all $n \in \mathbb{N}$.

**Necessity ($\implies$):**
Suppose $\{x_n\}$ converges to a finite limit $A \in \mathbb{R}$. By the [[Proof of the Basic Properties of Limits|Theorem on the Basic Properties of Limits]], every convergent sequence of real numbers is bounded, which guarantees in particular that $\{x_n\}$ is bounded above.

**Sufficiency ($\impliedby$):**
Conversely, suppose that the nondecreasing sequence $\{x_n\}$ is bounded above. Let $E := \{x_n \mid n \in \mathbb{N}\} \subset \mathbb{R}$ denote the range of the sequence. Because $E$ is non-empty and bounded above in $\mathbb{R}$, the [[Proof of Least Upper Bound Principle|Least Upper Bound Principle]] guarantees the existence of the finite supremum:
$$
\begin{gather}
s := \sup_{n \in \mathbb{N}} x_n = \sup E \in \mathbb{R} \tag{1}
\end{gather}
$$
Let $\varepsilon > 0$ be arbitrary. By the defining approximation property of the supremum, $s - \varepsilon$ is not an upper bound for $E$, so there exists at least one index $N \in \mathbb{N}$ such that:
$$
\begin{gather}
s - \varepsilon < x_N \le s \tag{2}
\end{gather}
$$
Because the sequence $\{x_n\}$ is nondecreasing, every index $n > N$ satisfies $x_N \le x_n$. Moreover, because $s$ is an upper bound for $E$, every term satisfies $x_n \le s < s + \varepsilon$. Combining these bounds for all $n > N$ yields:
$$
\begin{gather}
s - \varepsilon < x_N \le x_n \le s < s + \varepsilon \implies |x_n - s| < \varepsilon \tag{3}
\end{gather}
$$
Because $\varepsilon > 0$ was arbitrary, step 3 establishes that $\{x_n\}$ converges and that its limit is:
$$
\begin{gather}
\lim_{n \to \infty} x_n = s = \sup_{n \in \mathbb{N}} x_n \tag{4}
\end{gather}
$$

---
# Theorem 2
Assume that $\{x_n\}$ is nonincreasing, meaning $x_n \ge x_{n+1}$ for all $n \in \mathbb{N}$.

**Necessity ($\implies$):**
If $\{x_n\}$ converges, then by the [[Proof of the Basic Properties of Limits|Theorem on the Basic Properties of Limits]], $\{x_n\}$ is bounded and therefore bounded below.

**Sufficiency ($\impliedby$):**
Suppose that the nonincreasing sequence $\{x_n\}$ is bounded below. By the [[Proof of Greatest Lower Bound Principle|Greatest Lower Bound Principle]], the non-empty set $E := \{x_n \mid n \in \mathbb{N}\}$ possesses a finite infimum:
$$
\begin{gather}
m := \inf_{n \in \mathbb{N}} x_n = \inf E \in \mathbb{R} \tag{5}
\end{gather}
$$
Let $\varepsilon > 0$ be arbitrary. Because $m + \varepsilon$ exceeds the greatest lower bound $m$, there exists an index $N \in \mathbb{N}$ such that:
$$
\begin{gather}
m \le x_N < m + \varepsilon \tag{6}
\end{gather}
$$
Because $\{x_n\}$ is nonincreasing, every index $n > N$ satisfies $x_n \le x_N$, while the lower bound property of $m$ ensures $m - \varepsilon < m \le x_n$. Consequently, for all $n > N$:
$$
\begin{gather}
m - \varepsilon < m \le x_n \le x_N < m + \varepsilon \implies |x_n - m| < \varepsilon \tag{7}
\end{gather}
$$
Because $\varepsilon > 0$ was arbitrary, step 7 proves that $\{x_n\}$ converges and satisfies:
$$
\begin{gather}
\lim_{n \to \infty} x_n = m = \inf_{n \in \mathbb{N}} x_n \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
