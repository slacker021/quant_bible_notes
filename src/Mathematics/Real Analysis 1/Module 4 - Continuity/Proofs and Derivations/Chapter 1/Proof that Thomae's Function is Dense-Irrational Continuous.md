---
dg-publish: true
---
Let Thomae's function $R: (0, 1) \to \mathbb{R}$ be defined by:
$$
\begin{gather}
R(x) := \begin{cases} \frac{1}{q}, & \text{if } x = \frac{p}{q} \in \mathbb{Q} \cap (0, 1) \text{ in lowest terms } (p, q \in \mathbb{N}, \ \gcd(p, q) = 1) \\[2mm] 0, & \text{if } x \in (0, 1) \setminus \mathbb{Q} \end{cases} \tag{1}
\end{gather}
$$

# Proposition 1
Let $a \in \mathbb{Q} \cap (0, 1)$ be an arbitrary rational number within the domain. 

The number $a$ admits a unique representation in lowest terms:
$$
\begin{gather}
a = \frac{p_0}{q_0}, \quad p_0, q_0 \in \mathbb{N}, \quad \gcd(p_0, q_0) = 1 \tag{2}
\end{gather}
$$
Evaluating $R$ at $a$ by step 1 yields the strictly positive value:
$$
\begin{gather}
R(a) = \frac{1}{q_0} > 0 \tag{3}
\end{gather}
$$

Fix the positive error tolerance:
$$
\begin{gather}
\varepsilon_0 := \frac{1}{2q_0} > 0 \tag{4}
\end{gather}
$$

Let $\delta > 0$ be an arbitrary positive distance. Define the constrained radius:
$$
\begin{gather}
\delta' := \min(\delta, a, 1 - a) > 0 \tag{5}
\end{gather}
$$
By step 5, the open interval $(a - \delta', a + \delta')$ is entirely contained within the domain $(0, 1)$. 

By the density of the irrational numbers in $\mathbb{R}$, there exists an irrational number $\xi \in (a - \delta', a + \delta')$. For this element:
$$
\begin{gather}
|\xi - a| < \delta' \le \delta \tag{6}
\end{gather}
$$
Because $\xi \in (0, 1) \setminus \mathbb{Q}$, step 1 gives $R(\xi) = 0$. Evaluating the absolute difference:
$$
\begin{gather}
|R(\xi) - R(a)| = \left|0 - \frac{1}{q_0}\right| = \frac{1}{q_0} > \frac{1}{2q_0} = \varepsilon_0 \tag{7}
\end{gather}
$$

Because for every distance $\delta > 0$ there exists a domain point $\xi$ satisfying $|\xi - a| < \delta$ for which $|R(\xi) - R(a)| \ge \varepsilon_0$, the metric continuity criterion fails. 

Consequently, $R$ is discontinuous at every rational point $a \in \mathbb{Q} \cap (0, 1)$.

---
# Proposition 2
Let $a \in (0, 1) \setminus \mathbb{Q}$ be an arbitrary irrational point within the domain. By step 1, the functional value is:
$$
\begin{gather}
R(a) = 0 \tag{8}
\end{gather}
$$

Let an arbitrary error tolerance $\varepsilon > 0$ be given. 

By the Archimedean property of the real numbers (from the [[Proof of the Principle of Archimedes]]), there exists a natural number $N \in \mathbb{N}$ such that:
$$
\begin{gather}
N > \frac{1}{\varepsilon} \iff \frac{1}{N} < \varepsilon \tag{9}
\end{gather}
$$

Consider the set of all rational numbers in $(0, 1)$ whose irreducible denominators do not exceed $N$:
$$
\begin{gather}
S_N := \left\{ \frac{p}{q} \in (0, 1) \ \middle|\  p, q \in \mathbb{N}, \ \gcd(p, q) = 1, \ q \le N \right\} \tag{10}
\end{gather}
$$

For each denominator $q \in \{1, 2, \dots, N\}$, the requirement that $\frac{p}{q} \in (0, 1)$ restricts the numerator to the finite integer range $1 \le p \le q - 1$. The total number of elements in $S_N$ is bounded above by:
$$
\begin{gather}
|S_N| \le \sum_{q=1}^N (q - 1) = \frac{N(N - 1)}{2} < \infty \tag{11}
\end{gather}
$$
Step 11 demonstrates that $S_N$ is a finite set of real numbers.

Because $a$ is irrational, $a \notin S_N$. Because the set $S_N$ is finite and does not contain $a$, the distance from $a$ to the nearest element of $S_N$ is strictly positive:
$$
\begin{gather}
\delta_1 := \min_{x \in S_N} |x - a| > 0 \tag{12}
\end{gather}
$$

Furthermore, because $a \in (0, 1)$, the distances from $a$ to the domain boundaries are positive:
$$
\begin{gather}
\delta_2 := \min(a, 1 - a) > 0 \tag{13}
\end{gather}
$$

Define the control distance:
$$
\begin{gather}
\delta := \min(\delta_1, \delta_2) > 0 \tag{14}
\end{gather}
$$

Because $\delta \le \delta_2$, the neighborhood $(a - \delta, a + \delta) \subseteq (0, 1)$. Moreover, because $\delta \le \delta_1$, the neighborhood contains no elements of $S_N$:
$$
\begin{gather}
(a - \delta, a + \delta) \cap S_N = \emptyset \tag{15}
\end{gather}
$$

Let $x \in (0, 1)$ satisfy $|x - a| < \delta$. There are two possibilities:
* If $x \in (0, 1) \setminus \mathbb{Q}$, then $R(x) = 0$, so:
$$
\begin{gather}
|R(x) - R(a)| = |0 - 0| = 0 < \varepsilon \tag{16}
\end{gather}
$$
* If $x \in \mathbb{Q} \cap (0, 1)$, then $x = \frac{p}{q}$ in lowest terms. By step 15, $x \notin S_N$. By the definition of $S_N$ in step 10, every rational number in $(0, 1)$ that is not an element of $S_N$ must have a denominator satisfying $q > N$. Consequently:
$$
\begin{gather}
R(x) = \frac{1}{q} < \frac{1}{N} \tag{17}
\end{gather}
$$
Combining step 17 with step 9 yields:
$$
\begin{gather}
|R(x) - R(a)| = \left|\frac{1}{q} - 0\right| = \frac{1}{q} < \frac{1}{N} < \varepsilon \tag{18}
\end{gather}
$$

In both cases, $|R(x) - R(a)| < \varepsilon$ whenever $x \in (0, 1)$ satisfies $|x - a| < \delta$. 

Because $\varepsilon > 0$ was arbitrarily chosen, $R$ is continuous at the irrational point $a$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$