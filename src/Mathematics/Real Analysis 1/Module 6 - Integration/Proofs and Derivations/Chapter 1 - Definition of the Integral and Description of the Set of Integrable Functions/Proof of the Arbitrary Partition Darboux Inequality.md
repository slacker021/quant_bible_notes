---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f: [a, b] \to \mathbb{R}$ be a bounded function, and let $P_1$ and $P_2$ be two arbitrary partitions of $[a, b]$.

Define the common refinement of $P_1$ and $P_2$ by:
$$
\begin{gather}
P^* := P_1 \cup P_2 \tag{1}
\end{gather}
$$

Because $P_1 \subset [a, b]$ and $P_2 \subset [a, b]$ are finite sets containing the endpoints $a$ and $b$, their union $P^*$ is a finite subset of $[a, b]$ containing $a$ and $b$. Thus $P^*$ forms a valid partition of $[a, b]$.

By construction:
$$
\begin{gather}
P_1 \subseteq P^* \quad \text{and} \quad P_2 \subseteq P^* \tag{2}
\end{gather}
$$
so that $P^*$ is a simultaneous refinement of both $P_1$ and $P_2$.

By the Darboux Sum Monotonicity Under Refinement ([[Proof of the Darboux Sum Monotonicity Under Refinement]]), refining a partition increases the lower Darboux sum and decreases the upper Darboux sum. Applying this theorem to $P_1 \subseteq P^*$ yields:
$$
\begin{gather}
s(f; P_1) \le s(f; P^*) \tag{3}
\end{gather}
$$
and applying it to $P_2 \subseteq P^*$ yields:
$$
\begin{gather}
S(f; P^*) \le S(f; P_2) \tag{4}
\end{gather}
$$

Now let the common refinement $P^*$ be enumerated as $P^* = \{z_0, z_1, \dots, z_m\}$ where:
$$
\begin{gather}
a = z_0 < z_1 < \dots < z_{m-1} < z_m = b \tag{5}
\end{gather}
$$
having constituent subintervals $\Delta_j^* := [z_{j-1}, z_j]$ and subinterval lengths $\Delta z_j := z_j - z_{j-1} > 0$ for each $j \in \{1, \dots, m\}$.

For each subinterval $\Delta_j^*$, define the local infimum and supremum:
$$
\begin{gather}
m_j^* := \inf_{x \in \Delta_j^*} f(x) \quad \text{and} \quad M_j^* := \sup_{x \in \Delta_j^*} f(x) \tag{6}
\end{gather}
$$

By definition of the infimum and supremum of a non-empty bounded set of real numbers:
$$
\begin{gather}
m_j^* \le M_j^* \tag{7}
\end{gather}
$$
for every $j \in \{1, \dots, m\}$.

Multiplying the inequality of step 7 by the strictly positive length $\Delta z_j > 0$ preserves the order:
$$
\begin{gather}
m_j^* \Delta z_j \le M_j^* \Delta z_j \tag{8}
\end{gather}
$$
for every $j \in \{1, \dots, m\}$.

Summing the inequality of step 8 across all $j \in \{1, \dots, m\}$:
$$
\begin{gather}
\sum_{j=1}^m m_j^* \Delta z_j \le \sum_{j=1}^m M_j^* \Delta z_j \tag{9}
\end{gather}
$$

By the definitions of lower and upper Darboux sums, the left-hand side of step 9 is $s(f; P^*)$ and the right-hand side is $S(f; P^*)$. Hence:
$$
\begin{gather}
s(f; P^*) \le S(f; P^*) \tag{10}
\end{gather}
$$

Chaining together the inequalities established in step 3, step 10, and step 4:
$$
\begin{gather}
s(f; P_1) \le s(f; P^*) \le S(f; P^*) \le S(f; P_2) \tag{11}
\end{gather}
$$

By transitivity of the order relation on the real numbers $\mathbb{R}$, step 11 establishes:
$$
\begin{gather}
s(f; P_1) \le S(f; P_2) \tag{12}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
