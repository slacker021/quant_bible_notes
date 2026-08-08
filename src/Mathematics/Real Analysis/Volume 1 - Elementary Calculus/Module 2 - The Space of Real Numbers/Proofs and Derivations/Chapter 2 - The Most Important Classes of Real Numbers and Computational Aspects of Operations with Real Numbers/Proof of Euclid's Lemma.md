---
dg-publish: true
---
Let $a, b \in \mathbb{Z}$ and let $p \in \mathbb{N} \setminus \{1\}$ be a prime number. Assume that $p \mid (a \cdot b)$. To establish that $(p \mid a) \lor (p \mid b)$, evaluate two exhaustive cases based on the divisibility of $a$ by $p$:

# Case 1: Assume $p \mid a$
If $p \mid a$, the disjunction $(p \mid a) \lor (p \mid b)$ holds immediately.

# Case 2: Assume $p \nmid a$
Because $p$ is a prime number, its only positive divisors in $\mathbb{N}$ are $1$ and $p$. Because $p$ does not divide $a$, the greatest common divisor of $a$ and $p$ must be unity:
$$
\gcd(a, p) = 1 \tag{1}
$$
By Bézout's Identity, there exist integers $u, v \in \mathbb{Z}$ such that:
$$
u a + v p = 1 \tag{2}
$$
Multiplying step 2 across by the integer $b$ yields:
$$
u a b + v p b = b \tag{3}
$$
Because $p \mid (a \cdot b)$ by hypothesis, there exists an integer $k \in \mathbb{Z}$ such that $a b = k p$. Substituting this equality into step 3:
$$
u (k p) + v p b = b \tag{4}
$$
Factoring the prime scalar $p$ from the left-hand side of step 4:
$$
p (u k + v b) = b \tag{5}
$$
Because $u, k, v, b \in \mathbb{Z}$, the quantity $u k + v b$ is an integer. By the definition of divisibility, step 5 proves that:
$$
p \mid b \tag{6}
$$
Thus, if $p$ does not divide $a$, it must divide $b$, confirming that $p \mid (a \cdot b) \implies (p \mid a) \lor (p \mid b)$.

# Coprime Specialization
Suppose $a$ and $b$ are relatively prime ($\gcd(|a|, |b|) = 1$) and $p \mid (a \cdot b)$. By the first part of this lemma, $p$ divides at least one factor. If $p$ divided both $a$ and $b$, then $p$ would be a common divisor of $a$ and $b$, which requires $p \le \gcd(|a|, |b|) = 1$, contradicting the definition of a prime ($p > 1$). Therefore, $p$ divides exactly one of the two factors.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
