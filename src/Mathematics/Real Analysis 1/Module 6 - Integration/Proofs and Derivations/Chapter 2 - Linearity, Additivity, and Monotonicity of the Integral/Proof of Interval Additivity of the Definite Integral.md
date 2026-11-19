---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $c \in (a, b)$ be an interior point, and let $f: [a, b] \to \mathbb{R}$ be a real-valued function. Let $f_1 := f|_{[a, c]}$ and $f_2 := f|_{[c, b]}$ denote the restrictions of $f$ to $[a, c]$ and $[c, b]$, respectively.

---
# Part 1

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ satisfying $a = x_0 < x_1 < \dots < x_n = b$.

Form the refinement $P^* := P \cup \{c\}$.

By the Darboux Sum Monotonicity Under Refinement ([[Proof of the Darboux Sum Monotonicity Under Refinement]]), adding partition points increases lower Darboux sums and decreases upper Darboux sums:
$$
\begin{gather}
s(f; P) \le s(f; P^*) \le S(f; P^*) \le S(f; P) \tag{1}
\end{gather}
$$

Subtracting the lower bound from the upper bound in step 1 yields:
$$
\begin{gather}
S(f; P^*) - s(f; P^*) \le S(f; P) - s(f; P) \tag{2}
\end{gather}
$$

Because $c \in P^*$, the point $c$ is a partition point of $P^*$, so $P^*$ can be written as $P^* = \{y_0, y_1, \dots, y_m\}$ with $y_k = c$ for some $k \in \{1, \dots, m-1\}$. 

The partition $P^*$ splits naturally at $c$ into two sub-partitions:
$$
\begin{gather}
P_1 := P^* \cap [a, c] = \{y_0, y_1, \dots, y_k\} \tag{3}
\end{gather}
$$
and
$$
\begin{gather}
P_2 := P^* \cap [c, b] = \{y_k, y_{k+1}, \dots, y_m\} \tag{4}
\end{gather}
$$
where $P_1$ is a partition of $[a, c]$ and $P_2$ is a partition of $[c, b]$.

Let $M_j := \sup_{x \in [y_{j-1}, y_j]} f(x)$ and $m_j := \inf_{x \in [y_{j-1}, y_j]} f(x)$ for each $j \in \{1, \dots, m\}$. The upper Darboux sum of $f$ across $P^*$ splits into two partial sums:
$$
\begin{gather}
S(f; P^*) = \sum_{j=1}^m M_j (y_j - y_{j-1}) = \sum_{j=1}^k M_j (y_j - y_{j-1}) + \sum_{j=k+1}^m M_j (y_j - y_{j-1}) \tag{5}
\end{gather}
$$

Recognizing the sub-partition upper sums on the right-hand side of step 5 gives:
$$
\begin{gather}
S(f; P^*) = S(f_1; P_1) + S(f_2; P_2) \tag{6}
\end{gather}
$$

Similarly, the lower Darboux sum of $f$ across $P^*$ decomposes as:
$$
\begin{gather}
s(f; P^*) = \sum_{j=1}^m m_j (y_j - y_{j-1}) = \sum_{j=1}^k m_j (y_j - y_{j-1}) + \sum_{j=k+1}^m m_j (y_j - y_{j-1}) \tag{7}
\end{gather}
$$
which evaluates to:
$$
\begin{gather}
s(f; P^*) = s(f_1; P_1) + s(f_2; P_2) \tag{8}
\end{gather}
$$

Subtracting step 8 from step 6 produces the fundamental Darboux oscillation decomposition:
$$
\begin{gather}
S(f; P^*) - s(f; P^*) = \big( S(f_1; P_1) - s(f_1; P_1) \big) + \big( S(f_2; P_2) - s(f_2; P_2) \big) \tag{9}
\end{gather}
$$

For any partition, an upper Darboux sum is greater than or equal to the corresponding lower Darboux sum. Therefore, both terms on the right-hand side of step 9 are non-negative:
$$
\begin{gather}
S(f_1; P_1) - s(f_1; P_1) \ge 0, \qquad S(f_2; P_2) - s(f_2; P_2) \ge 0 \tag{10}
\end{gather}
$$
---
# Part 2
To establish necessity, assume $f \in \mathcal{R}[a, b]$.

Let $\varepsilon > 0$ be arbitrary.

By the Riemann Integrability Criterion via Oscillation ([[Proof of the Riemann Integrability Criterion via Oscillation]]), there exists a partition $P$ of $[a, b]$ such that:
$$
\begin{gather}
S(f; P) - s(f; P) < \varepsilon \tag{11}
\end{gather}
$$

Construct the refinement $P^* = P \cup \{c\}$ with its induced sub-partitions $P_1$ of $[a, c]$ and $P_2$ of $[c, b]$ from step 3 and step 4.

Combining step 2, step 9, and step 11:
$$
\begin{gather}
\big( S(f_1; P_1) - s(f_1; P_1) \big) + \big( S(f_2; P_2) - s(f_2; P_2) \big) = S(f; P^*) - s(f; P^*) \le S(f; P) - s(f; P) < \varepsilon \tag{12}
\end{gather}
$$

Because both bracketed terms in step 12 are non-negative by step 10, each individual term is strictly bounded by $\varepsilon$:
$$
\begin{gather}
S(f_1; P_1) - s(f_1; P_1) < \varepsilon \tag{13}
\end{gather}
$$
and
$$
\begin{gather}
S(f_2; P_2) - s(f_2; P_2) < \varepsilon \tag{14}
\end{gather}
$$

By the Riemann Integrability Criterion via Oscillation, step 13 implies that $f_1 \in \mathcal{R}[a, c]$, and step 14 implies that $f_2 \in \mathcal{R}[c, b]$. This establishes necessity.

To establish sufficiency, assume that $f_1 \in \mathcal{R}[a, c]$ and $f_2 \in \mathcal{R}[c, b]$.

Let $\varepsilon > 0$ be arbitrary.

By the Riemann Integrability Criterion via Oscillation applied to $f_1$ on $[a, c]$, there exists a partition $P_1$ of $[a, c]$ such that:
$$
\begin{gather}
S(f_1; P_1) - s(f_1; P_1) < \frac{\varepsilon}{2} \tag{15}
\end{gather}
$$

Similarly, by the Riemann Integrability Criterion via Oscillation applied to $f_2$ on $[c, b]$, there exists a partition $P_2$ of $[c, b]$ such that:
$$
\begin{gather}
S(f_2; P_2) - s(f_2; P_2) < \frac{\varepsilon}{2} \tag{16}
\end{gather}
$$

Define the concatenated partition $P := P_1 \cup P_2$. Because the terminal point of $P_1$ is $c$ and the initial point of $P_2$ is $c$, $P$ is a valid partition of $[a, b]$ containing $c$, so $P = P \cup \{c\} = P^*$.

Applying the identity of step 9 to $P$:
$$
\begin{gather}
S(f; P) - s(f; P) = \big( S(f_1; P_1) - s(f_1; P_1) \big) + \big( S(f_2; P_2) - s(f_2; P_2) \big) \tag{17}
\end{gather}
$$

Substituting the bounds from step 15 and step 16 into step 17:
$$
\begin{gather}
S(f; P) - s(f; P) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{18}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists a partition $P$ of $[a, b]$ satisfying $S(f; P) - s(f; P) < \varepsilon$, the Riemann Integrability Criterion via Oscillation guarantees that $f \in \mathcal{R}[a, b]$. This establishes sufficiency.

Combining necessity and sufficiency yields:
$$
\begin{gather}
f \in \mathcal{R}[a, b] \iff \big( f \in \mathcal{R}[a, c] \quad \text{and} \quad f \in \mathcal{R}[c, b] \big) \tag{19}
\end{gather}
$$
---
# Part 3
Assume $f \in \mathcal{R}[a, b]$.

Let $P_1$ be an arbitrary partition of $[a, c]$ and let $P_2$ be an arbitrary partition of $[c, b]$. The union $P := P_1 \cup P_2$ is a partition of $[a, b]$ containing $c$.

By step 6:
$$
\begin{gather}
S(f; P) = S(f_1; P_1) + S(f_2; P_2) \tag{20}
\end{gather}
$$

For every partition $P_1$ of $[a, c]$ and every partition $P_2$ of $[c, b]$, the upper Darboux sums bound the corresponding definite integrals from above:
$$
\begin{gather}
S(f_1; P_1) \ge \int_a^c f(x)\,dx, \qquad S(f_2; P_2) \ge \int_c^b f(x)\,dx \tag{21}
\end{gather}
$$

Summing the two inequalities in step 21 and substituting step 20:
$$
\begin{gather}
S(f; P) \ge \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{22}
\end{gather}
$$

Taking the infimum over all partitions $P_1$ of $[a, c]$ and $P_2$ of $[c, b]$ independently:
$$
\begin{gather}
\inf_{P_1, P_2} \big( S(f_1; P_1) + S(f_2; P_2) \big) = \inf_{P_1} S(f_1; P_1) + \inf_{P_2} S(f_2; P_2) \tag{23}
\end{gather}
$$

Because $f_1 \in \mathcal{R}[a, c]$ and $f_2 \in \mathcal{R}[c, b]$, the upper Darboux integrals equal the respective Riemann integrals:
$$
\begin{gather}
\inf_{P_1} S(f_1; P_1) = \int_a^c f(x)\,dx, \qquad \inf_{P_2} S(f_2; P_2) = \int_c^b f(x)\,dx \tag{24}
\end{gather}
$$

Furthermore, because every partition of $[a, b]$ containing $c$ is of the form $P_1 \cup P_2$, and the upper Darboux integral is the infimum over all partitions of $[a, b]$:
$$
\begin{gather}
\int_a^b f(x)\,dx = \inf_P S(f; P) = \inf_{P_1, P_2} \big( S(f_1; P_1) + S(f_2; P_2) \big) \tag{25}
\end{gather}
$$

Substituting step 24 into step 25:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{26}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
