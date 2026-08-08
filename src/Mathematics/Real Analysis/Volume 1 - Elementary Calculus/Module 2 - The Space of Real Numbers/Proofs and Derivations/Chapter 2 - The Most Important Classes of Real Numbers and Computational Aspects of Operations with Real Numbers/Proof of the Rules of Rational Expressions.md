---
dg-publish: true
---
Let $a, b \in \mathbb{R}_{>0}$ be strictly positive real numbers, and let $m, n \in \mathbb{N}$.

--------------------------------------------------------------------------------
# Proposition 1
### Existence of the Positive Root
Define the candidate set $E \subset \mathbb{R}$ by:
$$
E := \{ t \in \mathbb{R} \mid t > 0 \wedge t^n < a \} \tag{1}
$$
To verify that $E$ is non-empty, define $t_0 := \frac{a}{1 + a}$. Because $a > 0$, $0 < t_0 < 1$ and $t_0 < a$. Induction demonstrates that $t_0^n \le t_0 < a$, confirming that $t_0 \in E$, so $E \ne \emptyset$.

To verify that $E$ is bounded above, define $M := 1 + a > 1$. By Bernoulli's Inequality, $(1 + a)^n \ge 1 + na > a$. By the monotonicity of powers on $\mathbb{R}_{>0}$, any $t \ge 1 + a$ satisfies $t^n \ge (1 + a)^n > a$, which implies $t \notin E$. Consequently, $1 + a$ is an upper bound for $E$.

By the Least Upper Bound Principle, $E$ admits a unique supremum:
$$
s := \sup E \tag{2}
$$
Because $t_0 \in E$, $s \ge t_0 > 0$. For any scalars $0 < u < v$, factoring the difference of $n$-th powers yields:
$$
v^n - u^n = (v - u)\sum_{j=0}^{n-1} v^{n-1-j} u^j < (v - u) n v^{n-1} \tag{3}
$$
Evaluate the relation between $s^n$ and $a$ via trichotomy:
* Case 1: Assume $s^n < a$. Set $\Delta := a - s^n > 0$. Choose $\varepsilon$ such that:
$$
0 < \varepsilon < \min \left\{ 1, \, \frac{\Delta}{n(s + 1)^{n-1}} \right\} \tag{4}
$$
Applying step 3 with $v = s + \varepsilon$ and $u = s$ yields:
$$
(s + \varepsilon)^n - s^n < \varepsilon n (s + \varepsilon)^{n-1} \le \varepsilon n (s + 1)^{n-1} < \Delta = a - s^n \tag{5}
$$
Step 5 implies that $(s + \varepsilon)^n < a$, which requires $(s + \varepsilon) \in E$. This contradicts the fact that $s = \sup E$.
* Case 2: Assume $s^n > a$. Set $\Delta := s^n - a > 0$. Choose $\varepsilon$ such that:
$$
0 < \varepsilon < \min \left\{ \frac{s}{2}, \, \frac{\Delta}{n s^{n-1}} \right\} \tag{6}
$$
Applying step 3 with $v = s$ and $u = s - \varepsilon$ yields:
$$
s^n - (s - \varepsilon)^n < \varepsilon n s^{n-1} < \Delta = s^n - a \tag{7}
$$
Step 7 implies that $(s - \varepsilon)^n > a$. For every $t \in E$, $t^n < a < (s - \varepsilon)^n \implies t < s - \varepsilon$. Thus, $s - \varepsilon$ is an upper bound for $E$ strictly smaller than $s$, contradicting $s = \sup E$.

Therefore, by trichotomy, $s^n = a$.

### Uniqueness
If $0 < s_1 < s_2$, the compatibility axioms of an ordered field require $s_1^n < s_2^n$. Thus, there exists a unique positive root, denoted by $\sqrt[n]{a} =: a^{1/n}$.

--------------------------------------------------------------------------------

# Proposition 2
### Product and Iterated Radicals
Set $x := a^{1/n}$ and $y := b^{1/n}$, so that $x^n = a$ and $y^n = b$. By the commutativity and associativity of multiplication:
$$
(x y)^n = x^n y^n = a b \tag{8}
$$
By the uniqueness of the positive $n$-th root of $ab$, step 8 requires:
$$
\sqrt[n]{ab} = xy = a^{1/n} b^{1/n} = \sqrt[n]{a} \cdot \sqrt[n]{b} \tag{9}
$$
Similarly, define $z := (a^{1/m})^{1/n}$. Raising $z$ to the power $nm$:
$$
z^{nm} = (z^n)^m = (a^{1/m})^m = a \tag{10}
$$
By uniqueness of the $(nm)$-th root, $\sqrt[n]{\sqrt[m]{a}} = \sqrt[nm]{a}$.

### Rational Exponent Power Laws
For $m \in \mathbb{Z}$ and $n \in \mathbb{N}$, define $a^{m/n} := (a^{1/n})^m$. For any $k \in \mathbb{N}$:
$$
a^{(km)/(kn)} = \left( (a^{1/(kn)})^k \right)^m = (a^{1/n})^m = a^{m/n} \tag{11}
$$
which establishes that rational powers are independent of the fraction representation.

Let $r_1 = m_1/k$ and $r_2 = m_2/k$ with common denominator $k \in \mathbb{N}$. Setting $c := a^{1/k}$:
$$
a^{r_1} \cdot a^{r_2} = c^{m_1} \cdot c^{m_2} = c^{m_1 + m_2} = a^{(m_1 + m_2)/k} = a^{r_1 + r_2} \tag{12}
$$
Furthermore, for $r_1 = m_1/n_1$ and $r_2 = m_2/n_2$:
$$
(a^{r_1})^{r_2} = \left( (a^{m_1/n_1})^{m_2} \right)^{1/n_2} = (a^{m_1 m_2})^{1/(n_1 n_2)} = a^{r_1 r_2} \tag{13}
$$
and:
$$
(ab)^{r_1} = ((ab)^{1/n_1})^{m_1} = (a^{1/n_1} b^{1/n_1})^{m_1} = a^{r_1} b^{r_1} \tag{14}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
