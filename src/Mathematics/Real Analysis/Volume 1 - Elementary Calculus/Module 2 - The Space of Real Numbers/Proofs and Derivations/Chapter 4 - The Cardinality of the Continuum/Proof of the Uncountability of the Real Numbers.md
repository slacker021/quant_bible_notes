---
dg-publish: true
---
Assume, for the sake of contradiction, that the open unit interval $(0, 1) \subset \mathbb{R}$ is countable (since $(0, 1)$ contains the infinite subset $\{1/(n + 1) \mid n \in \mathbb{N}\}$, it cannot be finite). Under this assumption, there exists a bijection $f: \mathbb{N} \to (0, 1)$, allowing every real number in $(0, 1)$ to be listed in a sequence $x_1, x_2, x_3, \dots, x_n, \dots$.

By the canonical $q$-ary representation established in Module 1, every real number $x \in (0, 1)$ possesses a unique infinite decimal expansion (base $q = 10$) once representations ending in an infinite tail of nines ($d_k = 9$ for all $k \ge K$) are prohibited. Furthermore, because $x > 0$, no $x \in (0, 1)$ has an expansion consisting entirely of zeros. Writing each term $x_i$ in its unique canonical decimal expansion produces an infinite two-dimensional grid of digits:
$$
\begin{gather}
x_1 = 0.d_{11} d_{12} d_{13} d_{14} \dots \\[2mm]
x_2 = 0.d_{21} d_{22} d_{23} d_{24} \dots \\[2mm]
x_3 = 0.d_{31} d_{32} d_{33} d_{34} \dots \\[2mm]
\vdots \tag{1}
\end{gather}
$$
where $d_{ij} \in \{0, 1, \dots, 9\}$ denotes the $j$-th decimal digit of the $i$-th real number $x_i$ in the enumeration.

A real number $y$ is now constructed digit by digit via its infinite decimal expansion:
$$
\begin{gather}
y := 0.y_1 y_2 y_3 y_4 \dots = \sum_{n=1}^\infty \frac{y_n}{10^n} \tag{2}
\end{gather}
$$
The $n$-th decimal digit $y_n$ is defined by inspecting the $n$-th diagonal digit $d_{nn}$ of the $n$-th number $x_n$ in step 1 according to the rule:
$$
\begin{gather}
y_n := \begin{cases}
1 & \text{if } d_{nn} \neq 1 \\[2mm]
2 & \text{if } d_{nn} = 1
\end{cases} \tag{3}
\end{gather}
$$
Because $y_n \in \{1, 2\}$ for every $n \in \mathbb{N}$, the series in step 2 satisfies $\frac{1}{9} = \sum_{n=1}^\infty 10^{-n} \le y \le \sum_{n=1}^\infty 2 \cdot 10^{-n} = \frac{2}{9}$, ensuring that $y \in (0, 1)$. Moreover, because no digit of $y$ is $0$ or $9$, the expansion $0.y_1 y_2 y_3 \dots$ is the unique canonical decimal representation of $y$.

By the assumption that the sequence $(x_n)_{n \in \mathbb{N}}$ enumerates all of $(0, 1)$, there must exist some index $k \in \mathbb{N}$ such that $y = x_k$. By the uniqueness of canonical decimal expansions, equality $y = x_k$ requires their decimal digits to coincide at every position, and in particular at the $k$-th position ($y_k = d_{kk}$). However, the construction rule in step 3 guarantees that $y_k \neq d_{kk}$ for every $k \in \mathbb{N}$:
$$
\begin{gather}
\forall k \in \mathbb{N}, \quad y_k \neq d_{kk} \implies y \neq x_k \tag{4}
\end{gather}
$$
Step 4 contradicts the assumption that $y$ appears in the enumeration. Therefore, $(0, 1)$ is uncountable. Because $(0, 1) \subset [0, 1] \subset \mathbb{R}$, the [[Proof of the Subsets of Countable Sets|Proposition on Subsets of Countable Sets]] dictates that neither $[0, 1]$ nor $\mathbb{R}$ can be countable, as any subset of a countable set must be at most countable.

Finally, note that $(0, 1)$, $[0, 1]$, and $\mathbb{R}$ are mutually equipotent:
1. Defining $g: [0, 1] \to (0, 1)$ by setting $g(0) := \frac{1}{2}$, $g(1) := \frac{1}{3}$, $g\left(\frac{1}{n}\right) := \frac{1}{n + 2}$ for $n \in \mathbb{N} \setminus \{1\}$, and $g(x) := x$ for all $x \in [0, 1] \setminus \left\{0, 1, \frac{1}{2}, \frac{1}{3}, \dots\right\}$ yields an explicit bijection between $[0, 1]$ and $(0, 1)$.
2. Defining $h: (0, 1) \to \mathbb{R}$ by $h(x) := \frac{2x - 1}{x(1 - x)}$ provides a strictly increasing, surjective bijection from $(0, 1)$ onto $\mathbb{R}$. Indeed, for $y = 0$, $h(1/2) = 0$. For $y \neq 0$, the relation $h(x) = y$ transforms into the polynomial equation $P(x) := y x^2 - (y - 2)x - 1 = 0$. Because $P(0) = -1 < 0$ and $P(1) = 1 > 0$, the [[Intermediate Value Theorem]] guarantees that $P(x) = 0$ has a unique root in $(0, 1)$.

Thus, $(0, 1) \sim [0, 1] \sim \mathbb{R}$, confirming that all three sets are uncountable and share the cardinality of the continuum $\mathfrak{c}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
