---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ be the complete ordered field of real numbers, and let $\mathbb{N} \subset \mathbb{Z} \subset \mathbb{R}$ denote the subsets of natural numbers and integers.

--------------------------------------------------------------------------------
# Proposition 1
Let $E \subset \mathbb{N}$ be a non-empty subset of natural numbers that is bounded above in $\mathbb{R}$. 

By the Least Upper Bound Principle, $E$ possesses a unique supremum $s := \sup E \in \mathbb{R}$. Because $s$ is the least upper bound, the strictly smaller scalar $s - 1 < s$ cannot be an upper bound for $E$. Therefore, there exists at least one element $n \in E$ such that:
$$
s - 1 < n \le s \tag{1}
$$
Adding $1$ across the left-hand inequality of step 1 yields:
$$
s < n + 1 \tag{2}
$$
Let $m \in E$ be an arbitrary element. If $m > n$, the discrete spacing property of natural numbers requires that $m \ge n + 1$. Combining this with step 2 gives $m > s$, which contradicts the fact that $s$ is an upper bound for $E$. Consequently, $m \le n$ holds for all $m \in E$. 

Because $n \in E$ and $m \le n$ for all $m \in E$, it follows that $n = \max E$.

--------------------------------------------------------------------------------
# Proposition 2
Assume for the purpose of contradiction that $\mathbb{N}$ is bounded above in $\mathbb{R}$. 

Because $\mathbb{N} \ne \emptyset$, Proposition 1 guarantees that $\mathbb{N}$ possesses a maximal element:
$$
n_0 := \max \mathbb{N} \in \mathbb{N} \tag{3}
$$
Because $\mathbb{N}$ is an inductive set, $n_0 \in \mathbb{N} \implies (n_0 + 1) \in \mathbb{N}$. However, because $0 < 1$, the additive compatibility axiom dictates that:
$$
n_0 < n_0 + 1 \tag{4}
$$
Step 4 directly contradicts the condition that $n_0$ is the maximal element of $\mathbb{N}$. Therefore, $\mathbb{N}$ is not bounded above in $\mathbb{R}$.

--------------------------------------------------------------------------------
# Proposition 3
Let $m, n \in \mathbb{Z}$ satisfy $n < m$. Then $m - n > 0$. Because $\mathbb{Z}$ is closed under subtraction, $m - n$ is a positive integer, meaning $(m - n) \in \mathbb{N}$. Because $1$ is the minimal element of $\mathbb{N}$:
$$
m - n \ge 1 \iff n + 1 \le m \tag{5}
$$
Now let $E \subset \mathbb{Z}$ be a non-empty subset of integers bounded above in $\mathbb{R}$, and let $s := \sup E \in \mathbb{R}$. By the properties of the supremum, there exists an integer $n \in E$ satisfying:
$$
s - 1 < n \le s \implies s < n + 1 \tag{6}
$$
For every integer $m \in E$, $m \le s < n + 1$, which requires $m < n + 1$. Applying step 5 demonstrates that $m \le n$ for all $m \in E$. Thus, $n = \max E$.

--------------------------------------------------------------------------------
# Proposition 4
Let $E \subset \mathbb{Z}$ be a non-empty subset of integers that is bounded below in $\mathbb{R}$ by some minorant $b \in \mathbb{R}$, such that $b \le x$ for all $x \in E$. 

Consider the reflected set of additive inverses:
$$
-E := \{ -x \in \mathbb{Z} \mid x \in E \} \tag{7}
$$
Because $E \ne \emptyset$, $-E \ne \emptyset$. Multiplying $b \le x$ by $-1$ reverses the inequality:
$$
-x \le -b \quad \forall x \in E \tag{8}
$$
Thus, $-E$ is a non-empty subset of $\mathbb{Z}$ bounded above by $-b$. By Proposition 3, $-E$ possesses a unique maximal element:
$$
m^* := \max(-E) \in -E \tag{9}
$$
Define $n^* := -m^*$. Because $m^* \in -E$, $n^* \in E$. By definition of the maximum:
$$
-x \le m^* \quad \forall x \in E \tag{10}
$$
Multiplying step 10 by $-1$ gives:
$$
-m^* \le x \implies n^* \le x \quad \forall x \in E \tag{11}
$$
Therefore, $n^* = \min E$, proving that every non-empty subset of $\mathbb{Z}$ bounded below contains a minimal element.

--------------------------------------------------------------------------------
# Proposition 5
Because $\mathbb{N} \subset \mathbb{Z}$ and $\mathbb{N}$ is unbounded above in $\mathbb{R}$ by Proposition 2, $\mathbb{Z}$ cannot be bounded above in $\mathbb{R}$. 

Assume for the purpose of contradiction that $\mathbb{Z}$ is bounded below in $\mathbb{R}$. By Proposition 4, $\mathbb{Z}$ must contain a minimal element:
$$
k_{\min} := \min \mathbb{Z} \in \mathbb{Z} \tag{12}
$$
Because $\mathbb{Z}$ is closed under subtraction, $k_{\min} - 1 \in \mathbb{Z}$. However:
$$
k_{\min} - 1 < k_{\min} \tag{13}
$$
Step 13 contradicts the minimality of $k_{\min}$. Consequently, $\mathbb{Z}$ is unbounded both above and below in $\mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
