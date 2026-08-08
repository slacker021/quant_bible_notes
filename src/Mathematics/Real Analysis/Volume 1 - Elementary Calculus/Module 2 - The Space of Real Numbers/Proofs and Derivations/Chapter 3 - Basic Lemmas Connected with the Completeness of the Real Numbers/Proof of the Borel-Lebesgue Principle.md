---
dg-publish: true
---
Let $\mathcal{S}$ be a system of open intervals covering the closed and bounded interval $I_1 := [a, b]$:
$$
\begin{gather}
I_1 = [a, b] \subseteq \bigcup_{U \in \mathcal{S}} U \tag{1}
\end{gather}
$$
Suppose, for the sake of contradiction, that the interval $I_1$ cannot be covered by any finite subsystem of intervals from $\mathcal{S}$. Bisect $I_1$ at its midpoint $m_1 := \frac{a + b}{2}$ into two closed subintervals $[a, m_1]$ and $[m_1, b]$. At least one of these two closed halves cannot be covered by a finite subsystem of $\mathcal{S}$; otherwise, the union of the two finite subcovers would form a finite subcover of $I_1$, contradicting the assumption. Denote such a half by $I_2 = [a_2, b_2]$.

Repeating this bisection procedure inductively generates a sequence of nested closed intervals:
$$
\begin{gather}
I_1 \supseteq I_2 \supseteq \dots \supseteq I_n \supseteq I_{n+1} \supseteq \dots \tag{2}
\end{gather}
$$
none of which admits a finite subcover from $\mathcal{S}$. At each step, the length of the interval is halved, so that for every $n \in \mathbb{N}$:
$$
\begin{gather}
|I_n| = b_n - a_n = |I_1| \cdot 2^{-(n-1)} = \frac{b - a}{2^{n-1}} \tag{3}
\end{gather}
$$
By [[Proof of Bernoulli's Inequality]], $2^{n-1} = (1 + 1)^{n-1} \ge n$, which together with the corollaries to Archimedes' Principle (see [[Proof of Archimedean Corollaries]]) ensures that for any $\varepsilon > 0$, there exists $n \in \mathbb{N}$ such that $|I_n| \le \frac{b - a}{n} < \varepsilon$. Consequently, by the Cauchy-Cantor Principle (see [[Proof of the Cauchy-Cantor Principle]]), there exists a unique common point $c \in \mathbb{R}$ belonging to every interval $I_n$:
$$
\begin{gather}
c \in \bigcap_{n=1}^\infty I_n \tag{4}
\end{gather}
$$
Because $c \in I_1 = [a, b]$ and $\mathcal{S}$ covers $[a, b]$, there exists at least one open interval $U = (\alpha, \beta) \in \mathcal{S}$ such that $c \in U$, meaning $\alpha < c < \beta$. Define the positive distance from $c$ to the boundary of $U$:
$$
\begin{gather}
\varepsilon := \min\{c - \alpha, \beta - c\} > 0 \tag{5}
\end{gather}
$$
Select an index $n \in \mathbb{N}$ large enough that $|I_n| = b_n - a_n < \varepsilon$. Because both $c \in [a_n, b_n]$ and any point $x \in I_n = [a_n, b_n]$ lie in $I_n$, the distance between $x$ and $c$ satisfies $|x - c| \le b_n - a_n = |I_n| < \varepsilon$, which yields:
$$
\begin{gather}
\alpha \le c - \varepsilon < a_n \le x \le b_n < c + \varepsilon \le \beta \implies I_n \subseteq (\alpha, \beta) = U \tag{6}
\end{gather}
$$
Step 6 demonstrates that the interval $I_n$ is covered by the single open interval $U \in \mathcal{S}$, which constitutes a finite subcover of cardinality one. This directly contradicts the construction of the sequence $\{I_n\}$, in which no interval $I_n$ can be covered by finitely many intervals from $\mathcal{S}$. Therefore, the initial assumption is false, and $[a, b]$ admits a finite subcover.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
