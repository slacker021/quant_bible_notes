---
dg-publish: true
---
# Proposition 1
Let $X \subseteq \mathbb{R}$ be a non-empty set that is bounded from above. If $X$ possesses a maximum element, that element is the supremum $\sup X$ and the proof is complete. Assume henceforth that $X$ has no maximum element, which implies that no element belonging to $X$ is an upper bound of $X$.

Select an element $a_0 \in X$ (which is not an upper bound of $X$) and an upper bound $b_0$ of $X$, and construct the initial closed interval $I_0 := [a_0, b_0]$. Proceeding recursively for each $n \in \mathbb{N} \cup \{0\}$, bisect the interval $I_n = [a_n, b_n]$ at its midpoint $m_n := \frac{a_n + b_n}{2}$:
* If $m_n$ is an upper bound of $X$, define the next interval as $I_{n+1} := [a_n, m_n]$.
* If $m_n$ is not an upper bound of $X$, define the next interval as $I_{n+1} := [m_n, b_n]$.

This recursive bisection generates a sequence of nested closed intervals $I_n = [a_n, b_n]$:
$$
\begin{gather}
I_0 \supseteq I_1 \supseteq I_2 \supseteq \dots \supseteq I_n \supseteq I_{n+1} \supseteq \dots \tag{1}
\end{gather}
$$
By construction, for every $n \in \mathbb{N} \cup \{0\}$, the right endpoint $b_n$ is an upper bound of $X$, whereas the left endpoint $a_n$ is not an upper bound of $X$.

The length of the $n$-th interval is $|I_n| = b_n - a_n = \frac{b_0 - a_0}{2^n}$. By [[Proof of Bernoulli's Inequality]], $2^n = (1 + 1)^n \ge 1 + n > n$, so $|I_n| < \frac{b_0 - a_0}{n}$. By Archimedes' Principle (see [[Proof of Archimedean Corollaries]]), for any $\varepsilon > 0$, there exists $n \in \mathbb{N}$ such that $|I_n| < \varepsilon$. Invoking the Cauchy-Cantor Principle yields a unique real number $c \in \mathbb{R}$ belonging to every interval $I_n$:
$$
\begin{gather}
c \in \bigcap_{n=0}^\infty I_n \tag{2}
\end{gather}
$$
To verify that $c = \sup X$, it suffices to show that $c$ is an upper bound of $X$ and that no smaller upper bound exists:
1. **The point $c$ is an upper bound of $X$:** Suppose, for the sake of contradiction, that $c$ is not an upper bound of $X$. Then there exists $x \in X$ such that $x > c$. Set $\varepsilon := x - c > 0$, and choose $N \in \mathbb{N}$ such that $|I_N| = b_N - a_N < \varepsilon$. Because $c \in I_N = [a_N, b_N]$, it follows that $b_N - c \le b_N - a_N < x - c$, which implies $b_N < x$. This contradicts the invariant that $b_N$ is an upper bound of $X$. Thus, $c$ is an upper bound of $X$.
2. **The point $c$ is the least upper bound of $X$:** Suppose, for the sake of contradiction, that there exists an upper bound $y$ of $X$ such that $y < c$. Set $\varepsilon := c - y > 0$, and choose $N \in \mathbb{N}$ such that $|I_N| = b_N - a_N < \varepsilon$. Because $c \in I_N = [a_N, b_N]$, it follows that $c - a_N \le b_N - a_N < c - y$, which implies $a_N > y$. Because $y$ is an upper bound of $X$, any number strictly exceeding $y$ is also an upper bound of $X$, forcing $a_N$ to be an upper bound of $X$. This contradicts the invariant that $a_n$ is never an upper bound of $X$.

Therefore, $c = \sup X$, establishing that the Cauchy-Cantor Principle along with the Principle of Archimedes implies the Least Upper Bound Principle.

---
# Proposition 2
To reduce the Bolzano-Weierstrass case to Proposition 1, it suffices to demonstrate that the Bolzano-Weierstrass Principle implies both the Principle of Archimedes and the Cauchy-Cantor Principle.

First, suppose for the sake of contradiction that the set of natural numbers $\mathbb{N}$ is bounded from above in $\mathbb{R}$. Because $\mathbb{N}$ is bounded below by $1$, $\mathbb{N}$ is a bounded infinite subset of $\mathbb{R}$, and by the Bolzano-Weierstrass Principle it possesses a limit point $c \in \mathbb{R}$. By definition of a limit point, the neighborhood $U_{1/2}(c) = (c - 1/2, c + 1/2)$ of length $1$ must contain infinitely many elements of $\mathbb{N}$. However, by Proposition 4 of the Properties of Natural Numbers (see [[Proof of the Properties of Natural Numbers]]), any two distinct natural numbers $m, n \in \mathbb{N}$ satisfy $|m - n| \ge 1$, so an open interval of length $1$ can contain at most one natural number. This contradiction proves that $\mathbb{N}$ is unbounded above in $\mathbb{R}$, establishing the Principle of Archimedes:
$$
\begin{gather}
\forall x \in \mathbb{R}, \quad \exists n \in \mathbb{N} \quad \text{such that} \quad n > x \tag{3}
\end{gather}
$$

Second, let $I_1 \supseteq I_2 \supseteq \dots \supseteq I_n \supseteq \dots$ be a sequence of nested closed intervals $I_n = [a_n, b_n]$, so that $a_1 \le a_2 \le \dots \le a_n \le b_n \le \dots \le b_1$. Consider the set of left endpoints $A := \{a_n \mid n \in \mathbb{N}\}$, which is bounded in $\mathbb{R}$ since $A \subseteq [a_1, b_1]$:
* **Case 1 ($A$ is a finite set):** Because the sequence $\{a_n\}$ is non-decreasing and takes only finitely many values, there exists an index $N \in \mathbb{N}$ and a value $c := a_N$ such that $a_k = c$ for all $k \ge N$. For any $n \in \mathbb{N}$, setting $k := \max\{n, N\}$ yields $a_n \le a_k = c \le b_k \le b_n$, so $c \in [a_n, b_n] = I_n$ for all $n \in \mathbb{N}$.
* **Case 2 ($A$ is an infinite set):** Because $A \subseteq [a_1, b_1]$ is bounded and infinite, the Bolzano-Weierstrass Principle guarantees that $A$ possesses a limit point $c \in \mathbb{R}$.
  * To verify $a_n \le c$ for all $n \in \mathbb{N}$, suppose to the contrary that $c < a_N$ for some $N \in \mathbb{N}$, and set $\varepsilon := a_N - c > 0$. Because $a_k \ge a_N$ for all $k \ge N$, no term $a_k$ with $k \ge N$ can belong to $U_\varepsilon(c) = (c - \varepsilon, a_N)$. Thus, $U_\varepsilon(c) \cap A \subseteq \{a_1, \dots, a_{N-1}\}$ is finite, contradicting that $c$ is a limit point of $A$.
  * To verify $c \le b_m$ for all $m \in \mathbb{N}$, suppose to the contrary that $c > b_M$ for some $M \in \mathbb{N}$, and set $\varepsilon := c - b_M > 0$. Because every left endpoint satisfies $a_k \le b_M$ for all $k \in \mathbb{N}$, the neighborhood $U_\varepsilon(c) = (b_M, c + \varepsilon)$ is disjoint from $A$, again contradicting that $c$ is a limit point of $A$.

Thus, in both cases, $a_n \le c \le b_n$ for all $n \in \mathbb{N}$, meaning $c \in \bigcap_{n=1}^\infty I_n$. Uniqueness when $\inf |I_n| = 0$ follows from $0 \le |c_1 - c_2| \le |I_n|$. Having established both the Principle of Archimedes and the Cauchy-Cantor Principle, Proposition 1 yields the Least Upper Bound Principle.

---
# Proposition 3
Let $X \subseteq \mathbb{R}$ be a non-empty set bounded from above, and let $M$ denote the non-empty set of all upper bounds of $X$. Suppose, for the sake of contradiction, that $X$ has no least upper bound, meaning that $M$ possesses no minimum element and $X$ possesses no maximum element.

Because $M$ has no minimum element, for every upper bound $y \in M$, there exists a strictly smaller upper bound $y' \in M$ such that $y' < y$. Similarly, because $X$ has no maximum element, no element of $X$ belongs to $M$, and for every $x \notin M$, there exists an element $x' \in X$ such that $x < x'$.

Select an element $a \in X$ (so $a \notin M$) and an upper bound $b \in M$. Because $a \in X$, $b \in M$, and $X \cap M = \emptyset$, it follows that $a < b$. For each $y \in M$, define the open interval $U_y := (y', b + 1)$; for each $x \notin M$, define the open interval $V_x := (a - 1, x')$. The combined family of open intervals:
$$
\begin{gather}
\mathcal{C} := \{U_y\}_{y \in M} \cup \{V_x\}_{x \notin M} \tag{4}
\end{gather}
$$
forms an open cover of the closed and bounded interval $[a, b]$: every $y \in [a, b] \cap M$ satisfies $y' < y < b + 1$ (so $y \in U_y$), and every $x \in [a, b] \setminus M$ satisfies $a - 1 < x < x'$ (so $x \in V_x$).

By the Borel-Lebesgue Principle, the open cover $\mathcal{C}$ admits a finite subcover of $[a, b]$ consisting of subfamilies $\{U_{y_1}, \dots, U_{y_k}\}$ and $\{V_{x_1}, \dots, V_{x_m}\}$. Both subfamilies must be non-empty ($k \ge 1$ and $m \ge 1$):
* For any $x \notin M$, the point $x' \in X$ satisfies $x' < b$ (since $b \in M$ and $X \cap M = \emptyset$), so $b \notin V_x$. Thus, covering $b \in [a, b]$ requires at least one interval $U_{y_i}$ ($k \ge 1$).
* For any $y \in M$, the point $y' \in M$ satisfies $a < y'$ (since $a \in X$ and $X \cap M = \emptyset$), so $a \notin U_y$. Thus, covering $a \in [a, b]$ requires at least one interval $V_{x_j}$ ($m \ge 1$).

Because $k \ge 1$ and $m \ge 1$, define:
$$
\begin{gather}
y^* := \min\{y'_1, \dots, y'_k\} \in M \quad \text{and} \quad x^* := \max\{x'_1, \dots, x'_m\} \in X \tag{5}
\end{gather}
$$
The union of the finite subcover is then:
$$
\begin{gather}
\left(\bigcup_{i=1}^k U_{y_i}\right) \cup \left(\bigcup_{j=1}^m V_{x_j}\right) = (y^*, b + 1) \cup (a - 1, x^*) \tag{6}
\end{gather}
$$
Because each $y_i \in [a, b] \cap M$, $y_i \le b$, and therefore $y^* \le y'_1 < y_1 \le b$. Furthermore, because $a \in X$ and each $y'_i$ is an upper bound of $X$ with $X \cap M = \emptyset$, $a < y'_i$ for all $i \in \{1, \dots, k\}$, so $a < y^*$. Thus, $a < y^* < b$, which implies $y^* \in [a, b]$.

Since $[a, b]$ is covered by step 6 and $y^* \notin (y^*, b + 1)$, the point $y^*$ must belong to $(a - 1, x^*)$, which requires $y^* < x^*$. However, because $x^* \in X$ and $y^* \in M$ is an upper bound of $X$, the definition of an upper bound requires $x^* \le y^*$. This contradiction:
$$
\begin{gather}
y^* < x^* \quad \wedge \quad x^* \le y^* \tag{7}
\end{gather}
$$
proves that $X$ must possess a least upper bound, establishing that the Borel-Lebesgue Principle implies the Least Upper Bound Principle.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
