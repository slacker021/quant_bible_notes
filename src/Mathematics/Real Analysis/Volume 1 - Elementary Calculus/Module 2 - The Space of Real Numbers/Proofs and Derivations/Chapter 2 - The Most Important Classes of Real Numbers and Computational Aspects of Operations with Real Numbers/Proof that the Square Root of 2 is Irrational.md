---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ be the complete ordered field of real numbers, and let $\mathbb{R}_{>0} := \{ x \in \mathbb{R} \mid x > 0 \}$.
# Existence and Uniqueness of the Square Root of Two
Define two subsets $X, Y \subset \mathbb{R}_{>0}$ by:
$$
X := \{ x \in \mathbb{R}_{>0} \mid x^2 < 2 \} \quad \wedge \quad Y := \{ y \in \mathbb{R}_{>0} \mid y^2 > 2 \} \tag{1}
$$
Because $1^2 = 1 < 2$ and $2^2 = 4 > 2$, the memberships $1 \in X$ and $2 \in Y$ confirm that both $X$ and $Y$ are non-empty. 

For any $x, y \in \mathbb{R}_{>0}$, the algebraic identity $y^2 - x^2 = (y - x)(y + x)$ with $x + y > 0$ establishes that:
$$
x < y \iff x^2 < y^2 \tag{2}
$$
Consequently, for every $x \in X$ and every $y \in Y$, the chain $x^2 < 2 < y^2$ implies that $x < y$. By the Axiom of Completeness (Dedekind Continuity), there exists an element $s \in \mathbb{R}$ such that:
$$
x \le s \le y \quad \forall x \in X, \, \forall y \in Y \tag{3}
$$
Because $1 \in X$ and $2 \in Y$, step 3 establishes that $1 \le s \le 2$, ensuring $s > 0$. 

Evaluate the relationship between $s^2$ and $2$ via trichotomy:
* Case 1: Assume $s^2 < 2$. Define $\Delta := 2 - s^2 > 0$. Because $s \ge 1$, $3s \ge 3$ and $\Delta \le 1$, which ensures $0 < \frac{\Delta}{3s} < 1$. Consider the perturbed element $s + \frac{\Delta}{3s} > s$. Squaring this quantity and using $\frac{\Delta}{3s} < 1$ and $\frac{1}{3s} \le \frac{1}{3}$:
$$
\left(s + \frac{\Delta}{3s}\right)^2 = s^2 + \frac{2\Delta}{3} + \left(\frac{\Delta}{3s}\right)^2 < s^2 + \frac{2\Delta}{3} + \frac{\Delta}{3s} \le s^2 + \frac{2\Delta}{3} + \frac{\Delta}{3} = s^2 + \Delta = 2 \tag{4}
$$
Step 4 implies that $\left(s + \frac{\Delta}{3s}\right) \in X$. This contradicts step 3 because $s + \frac{\Delta}{3s} > s$, whereas $x \le s$ holds for all $x \in X$.
* Case 2: Assume $s^2 > 2$. Define $\Delta := s^2 - 2 > 0$. Because $1 \le s \le 2$, $0 < \frac{\Delta}{3s} < s$, ensuring $s - \frac{\Delta}{3s} > 0$. Squaring this quantity:
$$
\left(s - \frac{\Delta}{3s}\right)^2 = s^2 - \frac{2\Delta}{3} + \left(\frac{\Delta}{3s}\right)^2 > s^2 - \frac{2\Delta}{3} > s^2 - \Delta = 2 \tag{5}
$$
Step 5 implies that $\left(s - \frac{\Delta}{3s}\right) \in Y$. This contradicts step 3 because $s - \frac{\Delta}{3s} < s$, whereas $s \le y$ holds for all $y \in Y$.

By trichotomy, the only remaining relation is $s^2 = 2$. Uniqueness on $\mathbb{R}_{>0}$ follows directly from step 2, as $0 < s_1 < s_2 \implies s_1^2 < s_2^2$. This unique positive scalar is denoted by $\sqrt{2}$.

# Irrationality of the Square Root of Two
Assume for the purpose of contradiction that $\sqrt{2} \in \mathbb{Q}$. 

Under this assumption, $\sqrt{2}$ admits a representation as a canonical reduced fraction:
$$
\sqrt{2} = \frac{m}{n}, \quad \text{where } m, n \in \mathbb{N} \text{ and } \gcd(m, n) = 1 \tag{6}
$$
Squaring both sides of step 6 yields:
$$
2 = \frac{m^2}{n^2} \implies m^2 = 2 n^2 \tag{7}
$$
Step 7 demonstrates that $2 \mid m^2$. By Euclid's Lemma, because $2$ is a prime number:
$$
2 \mid (m \cdot m) \implies 2 \mid m \tag{8}
$$
Because $2 \mid m$, there exists an integer $k \in \mathbb{N}$ such that $m = 2k$. Substituting this equality into step 7:
$$
(2k)^2 = 2 n^2 \implies 4k^2 = 2 n^2 \implies n^2 = 2 k^2 \tag{9}
$$
Step 9 demonstrates that $2 \mid n^2$. Applying Euclid's Lemma once more:
$$
2 \mid (n \cdot n) \implies 2 \mid n \tag{10}
$$
Step 8 and step 10 establish that $2 \mid m$ and $2 \mid n$. Consequently, $2$ is a common divisor of $m$ and $n$, which implies:
$$
\gcd(m, n) \ge 2 \tag{11}
$$
Step 11 directly contradicts the premise in step 6 that $\gcd(m, n) = 1$. Therefore, the assumption that $\sqrt{2} \in \mathbb{Q}$ is false, confirming that $\sqrt{2} \in \mathbb{R} \setminus \mathbb{Q}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
