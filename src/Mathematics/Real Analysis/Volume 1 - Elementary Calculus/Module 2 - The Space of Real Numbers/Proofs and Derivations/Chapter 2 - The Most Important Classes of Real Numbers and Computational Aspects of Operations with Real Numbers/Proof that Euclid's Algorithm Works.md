---
dg-publish: true
---
Let $m, n \in \mathbb{N}$ with $m \ge n$. The greatest common divisor $\gcd(m, n)$ is the unique maximal element of the set of common divisors $\operatorname{CD}(m, n) := \{ d \in \mathbb{Z} \mid d \mid m \wedge d \mid n \}$.

# Finite Termination of the Algorithm
If $n \mid m$, there exists $q_1 \in \mathbb{N}$ such that $m = q_1 n + 0$. The remainder is zero at the initial step, and $\gcd(m, n) = n = 0 \cdot m + 1 \cdot n$. 

If $n \nmid m$, dividing $m$ by $n$ via the Principle of Archimedes yields a unique quotient $q_1 \in \mathbb{N}$ and positive remainder $r_1 \in \mathbb{N}$ satisfying:
$$
m = q_1 n + r_1 \quad (0 < r_1 < n) \tag{1}
$$
Iterating the division algorithm successively with divisor and remainder pairs generates the recurrence system:
$$
\begin{align}
m &= q_1 n + r_1, \quad &0 < r_1 < n \\[2mm]
n &= q_2 r_1 + r_2, \quad &0 < r_2 < r_1 \\[2mm]
r_1 &= q_3 r_2 + r_3, \quad &0 < r_3 < r_2 \\[2mm]
&\;\;\vdots \\[2mm]
r_{k-2} &= q_k r_{k-1} + r_k, \quad &0 < r_k < r_{k-1} \\[2mm]
r_{k-1} &= q_{k+1} r_k + 0 \tag{2}
\end{align}
$$
The positive remainders form a strictly decreasing sequence of natural numbers:
$$
n > r_1 > r_2 > r_3 > \dots > r_k > 0 \tag{3}
$$
Because every non-empty subset of $\mathbb{N}$ contains a minimal element by the Well-Ordering Principle, an infinite strictly decreasing sequence of natural numbers cannot exist. Thus, the sequence of positive remainders must be finite, terminating in at most $n$ divisions with a remainder of zero: $r_{k+1} = 0$.

# Invariance of Common Divisors and Identification of the GCD
For any integers $a, b \in \mathbb{Z}$, define $\operatorname{CD}(a, b) := \{ d \in \mathbb{Z} \mid d \mid a \wedge d \mid b \}$. From the division identity $a = q b + r$:
* If $d \in \operatorname{CD}(a, b)$, then $d \mid a$ and $d \mid b$, so $d \mid (a - q b) = r$, which implies $d \in \operatorname{CD}(b, r)$.
* Conversely, if $d \in \operatorname{CD}(b, r)$, then $d \mid b$ and $d \mid r$, so $d \mid (q b + r) = a$, which implies $d \in \operatorname{CD}(a, b)$.

Therefore, $\operatorname{CD}(a, b) = \operatorname{CD}(b, r)$. Applying this invariance down the chain of step 2:
$$
\operatorname{CD}(m, n) = \operatorname{CD}(n, r_1) = \operatorname{CD}(r_1, r_2) = \dots = \operatorname{CD}(r_{k-1}, r_k) = \operatorname{CD}(r_k, 0) \tag{4}
$$
Because every integer divides $0$, the set $\operatorname{CD}(r_k, 0)$ consists of all divisors of $r_k$. The largest positive divisor of $r_k$ is $r_k$ itself. Consequently:
$$
\gcd(m, n) = \max \operatorname{CD}(m, n) = \max \operatorname{CD}(r_k, 0) = r_k \tag{5}
$$
Thus, the last non-zero remainder $r_k$ is the greatest common divisor.

### Derivation of Bézout's Identity
Define $r_{-1} := m$ and $r_0 := n$. The division steps in step 2 can be expressed as:
$$
r_{j-2} = q_j r_{j-1} + r_j \iff r_j = r_{j-2} - q_j r_{j-1} \tag{6}
$$
for $j \in \{1, 2, \dots, k\}$. 

For $j = 1$, $r_1 = m - q_1 n$, which is an integer linear combination of $m$ and $n$. Assume as the inductive hypothesis that for all indices $j < i$, each remainder $r_j$ can be expressed as an integer linear combination of $m$ and $n$:
$$
r_j = u_j m + v_j n \quad (u_j, v_j \in \mathbb{Z}) \tag{7}
$$
By step 6, $r_i = r_{i-2} - q_i r_{i-1}$. Substituting the inductive expressions for $r_{i-2}$ and $r_{i-1}$:
$$
r_i = (u_{i-2} m + v_{i-2} n) - q_i (u_{i-1} m + v_{i-1} n) = (u_{i-2} - q_i u_{i-1})m + (v_{i-2} - q_i v_{i-1})n \tag{8}
$$
Setting $u_i := u_{i-2} - q_i u_{i-1} \in \mathbb{Z}$ and $v_i := v_{i-2} - q_i v_{i-1} \in \mathbb{Z}$, the remainder $r_i$ is an integer linear combination of $m$ and $n$.

By induction, this property holds for all remainders up to the last non-zero remainder $r_k = d = \gcd(m, n)$. Hence, there exist integers $u, v \in \mathbb{Z}$ such that:
$$
u m + v n = d \tag{9}
$$
In particular, if $\gcd(m, n) = 1$, then $u m + v n = 1$. Conversely, if there exist integers $u, v \in \mathbb{Z}$ satisfying $u m + v n = 1$, any common divisor $c \in \operatorname{CD}(m, n)$ must divide $u m + v n = 1$, forcing $c \in \{1, -1\}$, which ensures $\gcd(m, n) = 1$.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
