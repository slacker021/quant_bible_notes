---
dg-publish: true
---
Let $\mathbb{N}$ denote the set of natural numbers. An integer $p \in \mathbb{N} \setminus \{1\}$ is prime if its only divisors in $\mathbb{N}$ are $1$ and $p$.

--------------------------------------------------------------------------------
# Lemma 1
Let $m, a, b \in \mathbb{Z}$ with $m \ne 0$. If $m \mid (a \cdot b)$ and $\gcd(m, a) = 1$, then $m \mid b$.

By Bézout's Identity, because $\gcd(m, a) = 1$, there exist integers $u, v \in \mathbb{Z}$ such that:
$$
u m + v a = 1 \tag{1}
$$
Multiplying step 1 across by $b$ yields:
$$
u m b + v a b = b \tag{2}
$$
Because $m \mid (a \cdot b)$, there exists an integer $k \in \mathbb{Z}$ such that $a b = k m$. Substituting this expression into step 2:
$$
u m b + v (k m) = b \implies m(u b + v k) = b \tag{3}
$$
Because $u, b, v, k \in \mathbb{Z}$, the quantity $u b + v k$ is an integer. Consequently, step 3 demonstrates that $m \mid b$.

--------------------------------------------------------------------------------
# Lemma 2
Let $p \in \mathbb{N}$ be a prime number, and let $a_1, a_2, \dots, a_r \in \mathbb{Z}$. If $p \mid \prod_{j=1}^r a_j$, then $p \mid a_i$ for at least one index $i \in \{1, \dots, r\}$.

Proceed by mathematical induction on the number of factors $r \ge 2$.

### Base Step ($r = 2$)
Assume that $p \mid (a_1 a_2)$. If $p \mid a_1$, the claim holds. Suppose instead that $p \nmid a_1$. Because $p$ is prime, its only positive divisors are $1$ and $p$. Because $p \nmid a_1$, it follows that $\gcd(p, a_1) = 1$. Applying Lemma 1 with $m = p$, $a = a_1$, and $b = a_2$ establishes that $p \mid a_2$.

### Inductive Step
Assume as the inductive hypothesis that the claim holds for any product of $k$ factors ($k \ge 2$). Consider a product of $k + 1$ factors such that $p \mid (a_1 a_2 \cdots a_k a_{k+1})$. Regrouping the product:
$$
p \mid \left( \left(\prod_{j=1}^k a_j\right) \cdot a_{k+1} \right) \tag{4}
$$
Applying the base step ($r = 2$) to step 4 demonstrates that either $p \mid a_{k+1}$ or $p \mid \prod_{j=1}^k a_j$. If $p \mid a_{k+1}$, the condition is satisfied. If $p \mid \prod_{j=1}^k a_j$, the inductive hypothesis ensures that $p \mid a_i$ for some $i \in \{1, \dots, k\}$. 

By the Principle of Mathematical Induction, Lemma 2 holds for all $r \ge 2$.

--------------------------------------------------------------------------------
# Theorem 
### Existence of Prime Factorization
Let $E \subseteq \mathbb{N}$ be the set of natural numbers defined by:
$$
E := \{ n \in \mathbb{N} \mid n = 1 \lor (\forall m \in \mathbb{N}, \, 2 \le m \le n \implies m \text{ is a product of primes}) \} \tag{5}
$$
Clearly $1 \in E$. Since $2$ is prime, $2$ is a product of a single prime factor, so $2 \in E$. 

Assume as the inductive hypothesis that $n \in E$ for some $n \ge 2$. Consider the integer $n + 1$:
* If $n + 1$ is prime, it is trivially a product of a single prime factor.
* If $n + 1$ is composite, there exist integers $a, b \in \mathbb{N}$ such that $n + 1 = a \cdot b$ with $2 \le a \le n$ and $2 \le b \le n$. Because $n \in E$, both $a$ and $b$ admit representations as products of primes: $a = \prod_{i=1}^s p_i$ and $b = \prod_{j=1}^t q_j$. Consequently:
$$
n + 1 = \left(\prod_{i=1}^s p_i\right)\left(\prod_{j=1}^t q_j\right) \tag{6}
$$
which is a product of primes.

In both cases, $n + 1$ is a product of primes, which implies that $(n + 1) \in E$. By the Principle of Mathematical Induction, $E = \mathbb{N}$, establishing that every integer $n > 1$ admits a prime factorization.

### Uniqueness of Prime Factorization
Suppose an integer $n > 1$ admits two prime factorizations:
$$
n = \prod_{i=1}^k p_i = \prod_{j=1}^l q_j \tag{7}
$$
where $p_1 \le p_2 \le \dots \le p_k$ and $q_1 \le q_2 \le \dots \le q_l$ are prime numbers. 

Because $p_1$ divides the left-hand side of step 7, $p_1 \mid \prod_{j=1}^l q_j$. By Lemma 2, $p_1 \mid q_m$ for some index $m \in \{1, \dots, l\}$. Because $q_m$ is prime and $p_1 > 1$, its only divisors are $1$ and $q_m$, forcing $p_1 = q_m \ge q_1$.

By symmetric reasoning, $q_1 \mid \prod_{i=1}^k p_i$, so $q_1 = p_r \ge p_1$ for some $r \in \{1, \dots, k\}$. Combining $p_1 \ge q_1$ and $q_1 \ge p_1$ via antisymmetry yields:
$$
p_1 = q_1 \tag{8}
$$
Dividing both sides of step 7 by $p_1 = q_1$:
$$
\prod_{i=2}^k p_i = \prod_{j=2}^l q_j \tag{9}
$$
Repeating this cancellation process inductively pairs each prime factor $p_r$ with $q_r$ such that $p_r = q_r$. 

If $k \ne l$, assuming without loss of generality that $k < l$, cancelling all $k$ factors would leave:
$$
1 = \prod_{j=k+1}^l q_j \tag{10}
$$
Because every prime satisfies $q_j \ge 2$, the right-hand product in step 10 is at least $2$, producing the contradiction $1 \ge 2$. 

Therefore, $k = l$ and $p_i = q_i$ for all $i \in \{1, \dots, k\}$, proving that the prime factorization is unique up to the ordering of the factors.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
