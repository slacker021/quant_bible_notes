---
dg-publish: true
---
Let $h \in \mathbb{R}_{>0}$ be a fixed strictly positive step size, and let $x \in \mathbb{R}$ be an arbitrary real number.

# Equivalent Reformulation
Dividing the target inequality $(k - 1)h \le x < kh$ by the positive scalar $h > 0$ yields the equivalent condition:
$$
k - 1 \le \frac{x}{h} < k \tag{1}
$$
It therefore suffices to demonstrate the existence and uniqueness of an integer $k \in \mathbb{Z}$ satisfying step 1.

# Existence
Define the subset $E \subset \mathbb{Z}$ consisting of all integers that strictly exceed the ratio $x/h$:
$$
E := \left\{ n \in \mathbb{Z} \ \middle|\ \frac{x}{h} < n \right\} \tag{2}
$$
Because the set of integers $\mathbb{Z}$ is not bounded above in $\mathbb{R}$, the scalar $x/h$ cannot serve as an upper bound for $\mathbb{Z}$. Therefore, there exists at least one integer strictly greater than $x/h$, proving that $E \ne \emptyset$. 

Concurrently, by the defining condition in step 2, every element $n \in E$ satisfies $n > x/h$. Consequently, $E$ is bounded below in $\mathbb{R}$ by the minorant $x/h$.

Because $E$ is a non-empty subset of $\mathbb{Z}$ bounded below, it possesses a unique minimal element:
$$
k := \min E \in \mathbb{Z} \tag{3}
$$
Because $k \in E$, the defining condition of $E$ requires that:
$$
\frac{x}{h} < k \tag{4}
$$
Furthermore, because $k$ is the minimal element of $E$, its immediate predecessor $k - 1$ cannot belong to $E$:
$$
k - 1 \notin E \implies k - 1 \le \frac{x}{h} \tag{5}
$$
Combining step 4 and step 5 yields:
$$
k - 1 \le \frac{x}{h} < k \tag{6}
$$
Multiplying step 6 across by $h > 0$ recovers the target inequality:
$$
(k - 1)h \le x < kh \tag{7}
$$

# Uniqueness
Suppose that $k_1, k_2 \in \mathbb{Z}$ both satisfy step 6 with $k_1 < k_2$. Because $k_1$ and $k_2$ are integers, $k_1 < k_2 \implies k_1 \le k_2 - 1$. 

Combining this with the bracketing bounds requires:
$$
k_2 - 1 \le \frac{x}{h} < k_1 \le k_2 - 1 \implies k_2 - 1 < k_2 - 1 \tag{8}
$$
Step 8 is an impossible contradiction. Therefore, $k_1 = k_2$, confirming that the integer $k \in \mathbb{Z}$ is uniquely determined.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
