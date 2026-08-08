---
dg-publish: true
---
Let $\mathbb{R}$ be the ordered field of real numbers, and let $\mathbb{Z} = (-\mathbb{N}) \cup \{0\} \cup \mathbb{N}$ denote the set of integers, where $-\mathbb{N} := \{ -k \mid k \in \mathbb{N} \}$.

--------------------------------------------------------------------------------
# Proposition 1
### Inversion and Subtraction Equivalence
For any $z \in \mathbb{Z}$, the additive inverse $-z$ belongs to $\mathbb{Z}$:
* If $z = 0$, then $-0 = 0 \in \mathbb{Z}$.
* If $z \in \mathbb{N}$, then $-z \in -\mathbb{N} \subset \mathbb{Z}$.
* If $z \in -\mathbb{N}$, then $z = -k$ for some $k \in \mathbb{N}$, so $-z = -(-k) = k \in \mathbb{N} \subset \mathbb{Z}$.

Because subtraction is defined as $m - n := m + (-n)$, closure under subtraction follows directly from closure under addition and inversion.

### Closure under Addition
Let $m, n \in \mathbb{Z}$. Evaluate the sign cases for $m$ and $n$:
* Case 1: Assume $m = 0$ or $n = 0$. If $m = 0$, $m + n = 0 + n = n \in \mathbb{Z}$. If $n = 0$, $m + n = m + 0 = m \in \mathbb{Z}$.
* Case 2: Assume $m$ and $n$ share the same sign.
  * If $m, n \in \mathbb{N}$, then $m + n \in \mathbb{N} \subset \mathbb{Z}$ by the additive closure of natural numbers.
  * If $m, n \in -\mathbb{N}$, then $a := -m \in \mathbb{N}$ and $b := -n \in \mathbb{N}$. By additive closure in $\mathbb{N}$, $a + b \in \mathbb{N}$. Therefore, $m + n = -(a + b) \in -\mathbb{N} \subset \mathbb{Z}$.
* Case 3: Assume $m$ and $n$ possess opposite signs. Without loss of generality, let $m \in \mathbb{N}$ and $n \in -\mathbb{N}$, so that $b := -n \in \mathbb{N}$ and $m + n = m - b$. By trichotomy on $\mathbb{N}$:
  * If $m = b$, then $m - b = 0 \in \mathbb{Z}$.
  * If $m > b$, define the set $S := \{ x \in \mathbb{N} \mid b + x \le m \}$. Because $b < m$, the discrete gap property ensures $b + 1 \le m$, so $1 \in S \ne \emptyset$. Furthermore, every $x \in S$ satisfies $x < b + x \le m$, meaning $S$ is bounded above by $m$. By the Well-Ordering Principle, $S$ possesses a maximal element $k := \max S \in \mathbb{N}$. 
  
    If $b + k < m$, then $(b + k) + 1 \le m$, which implies $b + (k + 1) \le m$, requiring $(k + 1) \in S$. This contradicts the maximality of $k$. Therefore, $b + k = m$, which implies $m - b = k \in \mathbb{N} \subset \mathbb{Z}$.
  * If $m < b$, then $b > m$. By the preceding argument, there exists $k \in \mathbb{N}$ such that $b - m = k$. Consequently, $m - b = -(b - m) = -k \in -\mathbb{N} \subset \mathbb{Z}$.

In all cases, $m + n \in \mathbb{Z}$ and $m - n \in \mathbb{Z}$.

--------------------------------------------------------------------------------
# Proposition 2
### Closure under Multiplication
Let $m, n \in \mathbb{Z}$. Evaluate the sign cases for $m$ and $n$:
* Case 1: Assume $m = 0$ or $n = 0$. By the connection axioms, $m \cdot n = 0 \in \mathbb{Z}$.
* Case 2: Assume $m, n \in \mathbb{N}$. By the multiplicative closure of natural numbers, $m \cdot n \in \mathbb{N} \subset \mathbb{Z}$.
* Case 3: Assume $m, n \in -\mathbb{N}$. Then $-m \in \mathbb{N}$ and $-n \in \mathbb{N}$. By the connection axioms and multiplicative closure in $\mathbb{N}$:
$$
m \cdot n = (-m) \cdot (-n) \in \mathbb{N} \subset \mathbb{Z} \tag{1}
$$
* Case 4: Assume $m$ and $n$ possess opposite signs. Without loss of generality, let $m \in \mathbb{N}$ and $n \in -\mathbb{N}$, so that $-n \in \mathbb{N}$. By multiplicative closure in $\mathbb{N}$, $m \cdot (-n) \in \mathbb{N}$. Applying the connection axioms:
$$
m \cdot n = -(m \cdot (-n)) \in -\mathbb{N} \subset \mathbb{Z} \tag{2}
$$

In all cases, $m \cdot n \in \mathbb{Z}$. Therefore, $\mathbb{Z}$ is closed under addition, subtraction, and multiplication.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
