---
dg-publish: true
---
Let $q \in \mathbb{N}$ be a fixed natural base with $q > 1$, and let $x \in \mathbb{R}_{>0}$ be an arbitrary strictly positive real number.

# Monotonicity of Integer Powers of the Base
Because $q \ge 2$, setting $h = q - 1 \ge 1 > 0$ in Bernoulli's Inequality establishes that for all $n \in \mathbb{N}$:
$$
q^n = (1 + (q - 1))^n \ge 1 + n(q - 1) > n(q - 1) \tag{1}
$$
Furthermore, for any integers $m, n \in \mathbb{Z}$ with $m < n$, the difference satisfies $n - m \in \mathbb{N}$, which implies $q^{n-m} \ge q^1 > 1$. Multiplying by $q^m > 0$ establishes that:
$$
m < n \implies q^m < q^n \tag{2}
$$
Thus, the mapping $m \mapsto q^m$ is strictly monotonically increasing on $\mathbb{Z}$.

# Existence of the Order Bound
Define the subset $E \subset \mathbb{Z}$ of integer exponents whose powers strictly exceed $x$:
$$
E := \{ m \in \mathbb{Z} \mid x < q^m \} \tag{3}
$$
To verify that $E$ is non-empty, apply the Principle of Archimedes to the positive step size $q - 1 > 0$ and the target value $x > 0$. There exists a natural number $n \in \mathbb{N}$ such that $n(q - 1) > x$. Combining this with step 1 yields:
$$
q^n > n(q - 1) > x \implies n \in E \tag{4}
$$
Thus, $E \ne \emptyset$.

To verify that $E$ is bounded below in $\mathbb{Z}$, apply the Principle of Archimedes to the reciprocal $\frac{1}{x} > 0$. There exists an integer $M \in \mathbb{N}$ such that $q^M > \frac{1}{x}$, which is equivalent to:
$$
q^{-M} < x \tag{5}
$$
Because $m \mapsto q^m$ is strictly increasing, any integer $m \in E$ satisfies $q^{-M} < x < q^m$, which by step 2 requires $-M < m$. Consequently, $-M$ serves as a lower bound for $E$.

Because $E$ is a non-empty subset of integers that is bounded below, it possesses a unique minimal element:
$$
k := \min E \in \mathbb{Z} \tag{6}
$$
Because $k \in E$, the strict inequality $x < q^k$ holds. Concurrently, because $k$ is the minimal element of $E$, its immediate predecessor cannot belong to $E$:
$$
k - 1 \notin E \implies q^{k-1} \le x \tag{7}
$$
Combining step 6 and step 7 yields:
$$
q^{k-1} \le x < q^k \tag{8}
$$
Setting $p := k - 1 \in \mathbb{Z}$ produces the required bracketing relation:
$$
q^p \le x < q^{p+1} \tag{9}
$$

# Uniqueness
Suppose there exist two distinct integers $p_1, p_2 \in \mathbb{Z}$ satisfying step 9 with $p_1 < p_2$. Because $p_1$ and $p_2$ are integers, $p_1 < p_2 \implies p_1 + 1 \le p_2$. Applying the monotonicity established in step 2:
$$
q^{p_1+1} \le q^{p_2} \tag{10}
$$
Combining step 10 with the bounding conditions requires:
$$
x < q^{p_1+1} \le q^{p_2} \le x \implies x < x \tag{11}
$$
Step 11 is an impossible contradiction. Therefore, $p_1 = p_2$, establishing uniqueness.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
