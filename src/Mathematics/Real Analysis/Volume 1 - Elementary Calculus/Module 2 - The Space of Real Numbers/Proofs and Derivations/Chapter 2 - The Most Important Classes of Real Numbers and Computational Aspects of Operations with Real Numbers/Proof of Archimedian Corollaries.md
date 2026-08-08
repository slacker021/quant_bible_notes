---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ be the complete ordered field of real numbers. The following properties follow directly from the Principle of Archimedes.

--------------------------------------------------------------------------------
# Proposition 1
Let $\varepsilon \in \mathbb{R}_{>0}$ be an arbitrary positive real number. Applying the Principle of Archimedes with step size $h = \varepsilon > 0$ and target value $x = 1$ guarantees the existence of a unique integer $n \in \mathbb{Z}$ such that: 
$$
(n - 1)\varepsilon \le 1 < n\varepsilon \tag{1}
$$
Because $1 > 0$ and $\varepsilon > 0$, the strict inequality $n\varepsilon > 1 > 0$ requires that $n > 0$. Since $n \in \mathbb{Z}$ and $n > 0$, it follows that $n \in \mathbb{N}$. 

Dividing the inequality $0 < 1 < n\varepsilon$ by the strictly positive natural number $n$ yields: 
$$
0 < \frac{1}{n} < \varepsilon \tag{2}
$$

--------------------------------------------------------------------------------
# Proposition 2
Let $x \in \mathbb{R}_{\ge 0}$ satisfy $x < \frac{1}{n}$ for all $n \in \mathbb{N}$. 

To establish that $x = 0$, proceed by contradiction. Assume that $x > 0$. Applying Proposition 1 to the positive quantity $\varepsilon = x > 0$ guarantees the existence of a natural number $n_0 \in \mathbb{N}$ such that: 
$$
0 < \frac{1}{n_0} < x \tag{3}
$$
Step 3 directly contradicts the initial hypothesis that $x < \frac{1}{n}$ holds for all $n \in \mathbb{N}$. Therefore, the assumption $x > 0$ is untenable, confirming that $x = 0$.

--------------------------------------------------------------------------------

# Proposition 3
Let $a, b \in \mathbb{R}$ satisfy $a < b$, so that the interval width $b - a > 0$ is strictly positive. 

Applying Proposition 1 to $\varepsilon = b - a > 0$ guarantees the existence of a natural number $n \in \mathbb{N}$ such that: 
$$
0 < \frac{1}{n} < b - a \tag{4}
$$
Next, applying the Principle of Archimedes with positive step size $h = \frac{1}{n} > 0$ to the real scalar $a$ yields a unique integer $m \in \mathbb{Z}$ satisfying: 
$$
\frac{m - 1}{n} \le a < \frac{m}{n} \tag{5}
$$
Define the rational candidate $r := \frac{m}{n} \in \mathbb{Q}$. From the right-hand inequality of step 5, $a < r$. Furthermore, adding $\frac{1}{n}$ to the left-hand inequality of step 5 and incorporating the bound from step 4 gives: 
$$
\frac{m}{n} = \frac{m - 1}{n} + \frac{1}{n} \le a + \frac{1}{n} < a + (b - a) = b \tag{6}
$$
Combining step 5 and step 6 establishes that $a < r < b$, proving that $\mathbb{Q}$ is dense in $\mathbb{R}$.

--------------------------------------------------------------------------------
# Proposition 4
Let $x \in \mathbb{R}$ be an arbitrary real number. Applying the Principle of Archimedes with unit step size $h = 1 > 0$ to $x$ yields a unique integer $m \in \mathbb{Z}$ such that: 
$$
m - 1 \le x < m \tag{7}
$$
Defining $k := m - 1 \in \mathbb{Z}$ transforms step 7 into the unique bracketing relation: 
$$
k \le x < k + 1 \tag{8}
$$
Denoting this unique integer by $\lfloor x \rfloor := k$ (the integer floor of $x$) and defining the fractional part by $\{x\} := x - \lfloor x \rfloor$, subtracting $\lfloor x \rfloor$ across step 8 establishes that: 
$$
0 \le \{x\} < 1 \quad \wedge \quad x = \lfloor x \rfloor + \{x\} \tag{9}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
