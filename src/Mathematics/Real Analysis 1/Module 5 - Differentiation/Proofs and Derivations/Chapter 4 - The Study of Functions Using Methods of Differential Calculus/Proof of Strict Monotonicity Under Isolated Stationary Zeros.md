---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a differentiable function on $(a, b)$. Suppose that $f'(x) \ge 0$ for all $x \in (a, b)$, and let $Z := \{x \in (a, b) \mid f'(x) = 0\}$ denote its stationary zero set. Suppose further that $Z$ contains no non-empty open subinterval $(\alpha, \beta) \subset (a, b)$.

Because $f'(x) \ge 0$ everywhere on $(a, b)$, [[Proof of Differential Criteria for Interval Monotonicity|Proposition 2 of Differential Criteria for Interval Monotonicity]] guarantees that $f$ is non-decreasing on $(a, b)$.

To demonstrate that $f$ is strictly increasing on $(a, b)$, proceed by contradiction. Suppose that $f$ fails to be strictly increasing. Because $f$ is non-decreasing, the failure of strict monotonicity implies the existence of two distinct points $x_1, x_2 \in (a, b)$ with $x_1 < x_2$ such that:
$$
\begin{gather}
f(x_1) = f(x_2) \tag{1}
\end{gather}
$$

Because $f$ is non-decreasing on $(a, b)$, for every intermediate point $x \in [x_1, x_2]$, the functional values satisfy the order relations:
$$
\begin{gather}
f(x_1) \le f(x) \le f(x_2) \tag{2}
\end{gather}
$$
Combining step 1 and step 2 demonstrates that the bounds collapse to an identity:
$$
\begin{gather}
f(x) = f(x_1) = f(x_2), \quad \forall x \in [x_1, x_2] \tag{3}
\end{gather}
$$
Step 3 states that $f$ is identically constant across the non-degenerate closed interval $[x_1, x_2]$.

Differentiating an identically constant function on the open interior $(x_1, x_2)$ yields:
$$
\begin{gather}
f'(x) = 0, \quad \forall x \in (x_1, x_2) \tag{4}
\end{gather}
$$
Step 4 implies that the non-empty open interval $(x_1, x_2)$ is entirely contained within the stationary zero set $Z$:
$$
\begin{gather}
(x_1, x_2) \subseteq Z \tag{5}
\end{gather}
$$
However, step 5 directly contradicts the initial premise that $Z$ contains no non-empty open subinterval $(\alpha, \beta) \subset (a, b)$.

Hence, the assumption that $f(x_1) = f(x_2)$ must be false. For every pair of points $x_1, x_2 \in (a, b)$ with $x_1 < x_2$, the strict inequality $f(x_1) < f(x_2)$ holds, establishing that $f$ is strictly increasing across $(a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
