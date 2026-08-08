---
dg-publish: true
---
Let $\mathbb{R}$ be the ordered field of real numbers, and let $\mathbb{N} \subset \mathbb{R}$ denote the set of natural numbers, defined as the minimal inductive subset containing $1$.

--------------------------------------------------------------------------------
# Proposition 1
### Additive Closure
Fix an arbitrary natural number $m \in \mathbb{N}$, and define the subset $E_+ \subseteq \mathbb{N}$ by:
$$
E_+ := \{ n \in \mathbb{N} \mid (m + n) \in \mathbb{N} \} \tag{1}
$$
Because $\mathbb{N}$ is an inductive set and $m \in \mathbb{N}$, the successor $m + 1 \in \mathbb{N}$, which confirms that $1 \in E_+$. 

Assume as the inductive hypothesis that $n \in E_+$, meaning $(m + n) \in \mathbb{N}$. By the associativity of addition:
$$
m + (n + 1) = (m + n) + 1 \tag{2}
$$
Because $(m + n) \in \mathbb{N}$ and $\mathbb{N}$ is inductive, $((m + n) + 1) \in \mathbb{N}$. Therefore, $(n + 1) \in E_+$. By the Principle of Mathematical Induction, $E_+ = \mathbb{N}$, establishing that $m + n \in \mathbb{N}$ for all $m, n \in \mathbb{N}$.

### Multiplicative Closure
Fix $m \in \mathbb{N}$, and define the subset $E_\cdot \subseteq \mathbb{N}$ by:
$$
E_\cdot := \{ n \in \mathbb{N} \mid (m \cdot n) \in \mathbb{N} \} \tag{3}
$$
Because $m \cdot 1 = m \in \mathbb{N}$, $1 \in E_\cdot$. Assume that $n \in E_\cdot$, so that $m \cdot n \in \mathbb{N}$. By the distributive law:
$$
m \cdot (n + 1) = m \cdot n + m \tag{4}
$$
Because $m \cdot n \in \mathbb{N}$ and $m \in \mathbb{N}$, the additive closure verified in step 2 ensures that $(m \cdot n + m) \in \mathbb{N}$. Hence, $(n + 1) \in E_\cdot$. By the Principle of Mathematical Induction, $E_\cdot = \mathbb{N}$, proving that $m \cdot n \in \mathbb{N}$ for all $m, n \in \mathbb{N}$.

--------------------------------------------------------------------------------
# Proposition 2
Define the subset $E \subseteq \mathbb{N}$ by:
$$
E := \{ n \in \mathbb{N} \mid (n = 1) \lor ((n - 1) \in \mathbb{N}) \} \tag{5}
$$
By construction, $1 \in E$. Assume that $n \in E$. Because $n \in \mathbb{N}$, the identity $(n + 1) - 1 = n$ confirms that the predecessor of $n + 1$ belongs to $\mathbb{N}$. Consequently, $(n + 1) \in E$. 

By the Principle of Mathematical Induction, $E = \mathbb{N}$, proving that for every $n \in \mathbb{N} \setminus \{1\}$, $(n - 1) \in \mathbb{N}$.

--------------------------------------------------------------------------------
# Proposition 3
### Base Step ($n = 1$)
Define the subset $M \subseteq \mathbb{N}$ by:
$$
M := \{ x \in \mathbb{N} \mid (x = 1) \lor (x \ge 2) \} \tag{6}
$$
where $2 := 1 + 1$. By definition, $1 \in M$. If $x \in M$, then either $x = 1$ (so $x + 1 = 2 \in M$) or $x \ge 2$ (so $x + 1 > x \ge 2$, meaning $x + 1 \in M$). By induction, $M = \mathbb{N}$. 

Thus, every $x \in \mathbb{N}$ satisfies $x \ge 1$. For any $x \in \mathbb{N}$ with $x > 1$, $x \ge 2 = 1 + 1$. Because $2 \in \{ x \in \mathbb{N} \mid 1 < x \}$, it follows that $\min \{ x \in \mathbb{N} \mid 1 < x \} = 2$.

### Inductive Step
Define the subset $E \subseteq \mathbb{N}$ by:
$$
E := \{ n \in \mathbb{N} \mid \min \{ x \in \mathbb{N} \mid n < x \} = n + 1 \} \tag{7}
$$
From the base step, $1 \in E$. Assume that $n \in E$. Let $x \in \mathbb{N}$ satisfy $n + 1 < x$. Because $n \ge 1$, $x > 2 > 1$, which ensures $x \ne 1$. By Proposition 2, $y := x - 1 \in \mathbb{N}$. Subtracting $1$ across $n + 1 < x$ gives $n < y$. 

Because $n \in E$, $y \ge n + 1$, which implies:
$$
x - 1 \ge n + 1 \implies x \ge n + 2 \tag{8}
$$
Because $n + 2 \in \{ x \in \mathbb{N} \mid n + 1 < x \}$ and every element $x$ in this set satisfies $x \ge n + 2$, it follows that $\min \{ x \in \mathbb{N} \mid n + 1 < x \} = n + 2$. Thus, $(n + 1) \in E$. 

By the Principle of Mathematical Induction, $E = \mathbb{N}$.

--------------------------------------------------------------------------------
# Proposition 4
Let $m, n \in \mathbb{N}$ satisfy $n < m$. 

Then $m \in \{ x \in \mathbb{N} \mid n < x \}$. By Proposition 3, the minimal element of this set is $n + 1$. Because any element of a set dominates its minimal element:
$$
n + 1 = \min \{ x \in \mathbb{N} \mid n < x \} \le m \tag{9}
$$

--------------------------------------------------------------------------------
# Proposition 5
Assume for the purpose of contradiction that there exists $x \in \mathbb{N}$ such that:
$$
n < x < n + 1 \tag{10}
$$
Applying Proposition 4 to the left-hand inequality $n < x$ demonstrates that $n + 1 \le x$. This directly contradicts the right-hand inequality $x < n + 1$. 

Therefore, no natural number exists strictly between $n$ and $n + 1$, confirming that $n + 1$ is the immediate successor of $n$.

--------------------------------------------------------------------------------
# Proposition 6
Let $n \in \mathbb{N} \setminus \{1\}$. By Proposition 2, $m := n - 1 \in \mathbb{N}$. 

Assume for the purpose of contradiction that there exists $x \in \mathbb{N}$ such that:
$$
n - 1 < x < n \iff m < x < m + 1 \tag{11}
$$
By Proposition 5, no natural number can lie strictly between $m$ and $m + 1$. Therefore, no natural number lies strictly between $n - 1$ and $n$, confirming that $n - 1$ is the immediate predecessor of $n$.

--------------------------------------------------------------------------------
# Proposition 7
Let $S \subseteq \mathbb{N}$ be a non-empty subset of natural numbers. 

If $1 \in S$, then because $1 \le x$ for all $x \in \mathbb{N}$ (by Proposition 3), $1 = \min S$. 

Suppose instead that $1 \notin S$. Define the set of lower bounds of $S$ in $\mathbb{N}$:
$$
B := \{ k \in \mathbb{N} \mid \forall s \in S, \, k < s \} \tag{12}
$$
Because $1 \notin S$ and $1 \le s$ for all $s \in S$, $1 < s$ for all $s \in S$, proving that $1 \in B$. 

The set $B$ cannot be inductive. If $B$ were inductive, then by the Principle of Mathematical Induction, $B = \mathbb{N}$. This would imply that every natural number is strictly smaller than every element of $S$, forcing $S = \emptyset$, which contradicts the hypothesis $S \ne \emptyset$.

Because $B$ is not inductive, there exists an element $k_0 \in B$ such that $k_0 + 1 \notin B$. 

Because $k_0 \in B$, $k_0 < s$ for all $s \in S$. By Proposition 4:
$$
k_0 + 1 \le s \quad \forall s \in S \tag{13}
$$
Concurrently, because $k_0 + 1 \notin B$, there must exist at least one element $s_0 \in S$ such that $k_0 + 1 \ge s_0$. Combining this with step 13 requires that $s_0 = k_0 + 1$. Consequently:
$$
(k_0 + 1 \in S) \wedge (\forall s \in S, \, k_0 + 1 \le s) \tag{14}
$$
Thus, $k_0 + 1 = \min S$. 

Uniqueness follows from the antisymmetry of the order relation.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
