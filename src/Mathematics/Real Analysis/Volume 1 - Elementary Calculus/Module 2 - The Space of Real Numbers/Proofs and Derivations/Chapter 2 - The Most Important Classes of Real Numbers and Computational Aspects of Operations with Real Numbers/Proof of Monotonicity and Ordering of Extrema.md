---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ be the ordered field of real numbers.

--------------------------------------------------------------------------------
# Proposition 1
Let $A$ and $B$ be non-empty bounded subsets of $\mathbb{R}$ satisfying $A \subseteq B$. 

Denote $M_B := \sup B$ and $m_B := \inf B$. By the definition of the supremum and infimum:
$$
m_B \le b \le M_B \quad \forall b \in B \tag{1}
$$
Because $A \subseteq B$, every element $a \in A$ satisfies $a \in B$. Consequently:
$$
m_B \le a \le M_B \quad \forall a \in A \tag{2}
$$
Step 2 demonstrates that $M_B$ is an upper bound for $A$ and $m_B$ is a lower bound for $A$. Because $\sup A$ is the least upper bound and $\inf A$ is the greatest lower bound:
$$
\sup A \le M_B = \sup B \quad \wedge \quad \inf B = m_B \le \inf A \tag{3}
$$

--------------------------------------------------------------------------------
# Proposition 2
Let $X, Y \subset \mathbb{R}$ be non-empty sets such that:
$$
x \le y \quad \forall x \in X, \, \forall y \in Y \tag{4}
$$
Fix an arbitrary element $y_0 \in Y$. By step 4, $x \le y_0$ holds for all $x \in X$, which establishes that $y_0$ is an upper bound for $X$. Consequently, $\sup X$ exists in $\mathbb{R}$ and satisfies:
$$
\sup X \le y_0 \tag{5}
$$
Because $y_0 \in Y$ was chosen arbitrarily, step 5 holds universally across all elements of $Y$. Thus, the scalar $\sup X$ serves as a lower bound for $Y$. Because $\inf Y$ is the greatest lower bound of $Y$:
$$
\sup X \le \inf Y \tag{6}
$$

--------------------------------------------------------------------------------
# Proposition 3
Assume in addition to the separation condition of Proposition 2 that either $X \cup Y = \mathbb{R}$, or for every $\varepsilon > 0$ there exist witness elements $x \in X$ and $y \in Y$ satisfying $y - x < \varepsilon$. 

From step 6, $\sup X \le \inf Y$ holds unconditionally. To demonstrate equality, proceed by contradiction. Assume that:
$$
\sup X < \inf Y \tag{7}
$$

### Case 1: Partition Exhaustion ($X \cup Y = \mathbb{R}$)
Define the midpoint:
$$
c := \frac{\sup X + \inf Y}{2} \tag{8}
$$
Step 8 satisfies the strict inequalities $\sup X < c < \inf Y$. Because $c > \sup X$, $c$ strictly exceeds every element of $X$, so $c \notin X$. Concurrently, because $c < \inf Y$, $c$ is strictly smaller than every element of $Y$, so $c \notin Y$. Consequently:
$$
c \notin (X \cup Y) = \mathbb{R} \tag{9}
$$
Step 9 contradicts the premise that $X \cup Y = \mathbb{R}$.

### Case 2: Arbitrary Proximity ($\forall \varepsilon > 0, \, \exists x \in X, y \in Y \text{ such that } y - x < \varepsilon$)
Define the positive scalar $\varepsilon_0 := \inf Y - \sup X > 0$. By hypothesis, there exist witness elements $x_0 \in X$ and $y_0 \in Y$ such that:
$$
y_0 - x_0 < \varepsilon_0 \tag{10}
$$
However, by the definitions of the supremum and infimum, $x_0 \le \sup X$ and $\inf Y \le y_0$. Subtracting these inequalities yields:
$$
y_0 - x_0 \ge \inf Y - \sup X = \varepsilon_0 \tag{11}
$$
Step 11 directly contradicts step 10.

In both cases, the assumption $\sup X < \inf Y$ produces an impossible contradiction, forcing:
$$
\sup X = \inf Y \tag{12}
$$

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
