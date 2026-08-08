---
dg-publish: true
---
Let $x, y \in \mathbb{R}$ be elements of the ordered field of real numbers.

--------------------------------------------------------------------------------
# Proposition 1
### Standard Triangle Inequality
By definition of the absolute value, the relations $-|x| \le x \le |x|$ and $-|y| \le y \le |y|$ hold for all $x, y \in \mathbb{R}$. 

Summing these inequalities via additive compatibility yields:
$$
-(|x| + |y|) \le x + y \le |x| + |y| \tag{1}
$$
For any real numbers $a, c \in \mathbb{R}$ with $c \ge 0$, the double inequality $-c \le a \le c$ is logically equivalent to $|a| \le c$. Instantiating $a = x + y$ and $c = |x| + |y|$ in step 1 yields:
$$
|x + y| \le |x| + |y| \tag{2}
$$

### Equality Condition
Evaluate the cases of equality based on the signs of $x$ and $y$:
* Case 1: If $x \ge 0$ and $y \ge 0$, then $x + y \ge 0$. Consequently, $|x + y| = x + y = |x| + |y|$.
* Case 2: If $x \le 0$ and $y \le 0$, then $x + y \le 0$. Consequently, $|x + y| = -(x + y) = (-x) + (-y) = |x| + |y|$.
* Case 3: If $x$ and $y$ possess opposite signs, assume without loss of generality that $x < 0 < y$. 
  * If $x + y \ge 0$, then $|x + y| = x + y < y = |y| < |x| + |y|$.
  * If $x + y < 0$, then $|x + y| = -(x + y) = -x - y < -x = |x| < |x| + |y|$.

In both sub-cases of Case 3, the inequality is strict. Therefore, $|x + y| = |x| + |y|$ holds if and only if $x \cdot y \ge 0$.

--------------------------------------------------------------------------------
# Proposition 2
### Difference Form
Substituting $-y$ in place of $y$ into Proposition 1:
$$
|x - y| = |x + (-y)| \le |x| + |-y| \tag{3}
$$
Because $|-y| = |y|$, step 3 immediately yields:
$$
|x - y| \le |x| + |y| \tag{4}
$$

--------------------------------------------------------------------------------
# Proposition 3
### Reverse Triangle Inequality
Expressing $x$ as the sum $x = (x - y) + y$ and applying Proposition 1:
$$
|x| = |(x - y) + y| \le |x - y| + |y| \tag{5}
$$
Subtracting $|y|$ from both sides yields:
$$
|x| - |y| \le |x - y| \tag{6}
$$
Similarly, expressing $y$ as $y = (y - x) + x$ and applying Proposition 1:
$$
|y| = |(y - x) + x| \le |y - x| + |x| = |x - y| + |x| \tag{7}
$$
Subtracting $|x|$ from both sides of step 7 and multiplying by $-1$ reverses the inequality:
$$
|y| - |x| \le |x - y| \implies -(|x| - |y|) \le |x - y| \tag{8}
$$
Combining step 6 and step 8 yields the double inequality:
$$
-|x - y| \le |x| - |y| \le |x - y| \tag{9}
$$
Step 9 is logically equivalent to:
$$
\big| |x| - |y| \big| \le |x - y| \tag{10}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
