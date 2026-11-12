---
dg-publish: true
---
Let $\mathbb{C}$ denote the field of complex numbers. For any $z = x + i y \in \mathbb{C}$ with $x, y \in \mathbb{R}$, the complex conjugate is defined by $\overline{z} := x - i y$, the real part is $\text{Re}(z) := x$, and the modulus is $|z| := \sqrt{x^2 + y^2} = \sqrt{z \overline{z}} \ge 0$. For any $w, z \in \mathbb{C}$ and tuples $u = (u_1, \dots, u_n), v = (v_1, \dots, v_n) \in \mathbb{C}^n$, let the standard inner product on $\mathbb{C}^n$ be given by $\langle u, v \rangle := \sum_{k=1}^n u_k \overline{v_k}$.

---
# Proposition 1
For any $u_1, \dots, u_n, v_1, \dots, v_n \in \mathbb{C}$, the Cauchy-Schwarz inequality holds:
$$
\begin{gather}
\left| \sum_{k=1}^n u_k \overline{v_k} \right|^2 \le \left( \sum_{k=1}^n |u_k|^2 \right) \left( \sum_{k=1}^n |v_k|^2 \right) \tag{1}
\end{gather}
$$
with equality holding if and only if the vectors $u$ and $v$ are linearly dependent over $\mathbb{C}$.

If $v_k = 0$ for all $k \in \{1, \dots, n\}$, then both sides of step 1 vanish identically, establishing the inequality trivially as $0 \le 0$, and the vectors $u$ and $v$ are linearly dependent.

Assume that there exists at least one index $k$ such that $v_k \neq 0$. It follows that:
$$
\begin{gather}
B := \sum_{k=1}^n |v_k|^2 > 0 \tag{2}
\end{gather}
$$
Define the scalar quantities:
$$
\begin{gather}
A := \sum_{k=1}^n |u_k|^2 \ge 0 \quad \text{and} \quad C := \sum_{k=1}^n u_k \overline{v_k} \in \mathbb{C} \tag{3}
\end{gather}
$$
For an arbitrary scalar $\lambda \in \mathbb{C}$, consider the non-negative sum of squared moduli:
$$
\begin{gather}
S(\lambda) := \sum_{k=1}^n |u_k - \lambda v_k|^2 \ge 0 \tag{4}
\end{gather}
$$
Expanding the modulus squared $|u_k - \lambda v_k|^2 = (u_k - \lambda v_k)\overline{(u_k - \lambda v_k)} = (u_k - \lambda v_k)(\overline{u_k} - \overline{\lambda} \overline{v_k})$ yields:
$$
\begin{gather}
|u_k - \lambda v_k|^2 = |u_k|^2 - \overline{\lambda} u_k \overline{v_k} - \lambda \overline{u_k} v_k + |\lambda|^2 |v_k|^2 \tag{5}
\end{gather}
$$
Summing step 5 over $k \in \{1, \dots, n\}$ gives:
$$
\begin{gather}
S(\lambda) = \sum_{k=1}^n |u_k|^2 - \overline{\lambda} \sum_{k=1}^n u_k \overline{v_k} - \lambda \sum_{k=1}^n \overline{u_k} v_k + |\lambda|^2 \sum_{k=1}^n |v_k|^2 \tag{6}
\end{gather}
$$
Notice that $\sum_{k=1}^n \overline{u_k} v_k = \overline{\sum_{k=1}^n u_k \overline{v_k}} = \overline{C}$. Substituting $A, B, C$ into step 6 produces:
$$
\begin{gather}
S(\lambda) = A - \overline{\lambda} C - \lambda \overline{C} + |\lambda|^2 B \ge 0 \tag{7}
\end{gather}
$$
Because step 7 holds for every $\lambda \in \mathbb{C}$, set $\lambda := \frac{C}{B}$, which is well-defined since $B > 0$ by step 2. Evaluating $S(C/B)$ yields:
$$
\begin{gather}
S\left(\frac{C}{B}\right) = A - \frac{\overline{C}}{B} C - \frac{C}{B} \overline{C} + \left|\frac{C}{B}\right|^2 B = A - \frac{|C|^2}{B} - \frac{|C|^2}{B} + \frac{|C|^2}{B} = A - \frac{|C|^2}{B} \tag{8}
\end{gather}
$$
Because $S(\lambda) \ge 0$ for all $\lambda$, the quantity in step 8 must be non-negative:
$$
\begin{gather}
A - \frac{|C|^2}{B} \ge 0 \iff |C|^2 \le A B \tag{9}
\end{gather}
$$
Substituting the definitions of $A, B, C$ from step 3 into step 9 demonstrates that:
$$
\begin{gather}
\left| \sum_{k=1}^n u_k \overline{v_k} \right|^2 \le \left( \sum_{k=1}^n |u_k|^2 \right) \left( \sum_{k=1}^n |v_k|^2 \right) \tag{10}
\end{gather}
$$
Equality holds in step 10 if and only if $S(C/B) = 0$. By step 4, the sum of non-negative terms $\sum_{k=1}^n |u_k - \lambda v_k|^2$ vanishes if and only if every term vanishes:
$$
\begin{gather}
u_k - \lambda v_k = 0 \iff u_k = \lambda v_k \quad \text{for all } k \in \{1, \dots, n\} \tag{11}
\end{gather}
$$
where $\lambda = \frac{C}{B}$, which is precisely the condition that $u$ is a scalar multiple of $v$. Hence, equality holds if and only if $u$ and $v$ are linearly dependent.

---
# Proposition 2
For any two complex numbers $z, w \in \mathbb{C}$, the triangle inequality holds:
$$
\begin{gather}
|z + w| \le |z| + |w| \tag{12}
\end{gather}
$$
and the reverse triangle inequality holds:
$$
\begin{gather}
||z| - |w|| \le |z - w| \tag{13}
\end{gather}
$$

Consider the square of the modulus $|z + w|$:
$$
\begin{gather}
|z + w|^2 = (z + w)\overline{(z + w)} = (z + w)(\overline{z} + \overline{w}) = z \overline{z} + z \overline{w} + w \overline{z} + w \overline{w} \tag{14}
\end{gather}
$$
By definition of the modulus, $z \overline{z} = |z|^2$ and $w \overline{w} = |w|^2$. Moreover, the term $w \overline{z}$ is the complex conjugate of $z \overline{w}$, because $\overline{z \overline{w}} = \overline{z} \overline{\overline{w}} = \overline{z} w = w \overline{z}$. Therefore:
$$
\begin{gather}
z \overline{w} + w \overline{z} = z \overline{w} + \overline{z \overline{w}} = 2 \, \text{Re}(z \overline{w}) \tag{15}
\end{gather}
$$
Substituting step 15 into step 14 produces:
$$
\begin{gather}
|z + w|^2 = |z|^2 + 2 \, \text{Re}(z \overline{w}) + |w|^2 \tag{16}
\end{gather}
$$
For any complex number $\zeta = \xi + i \eta$ with $\xi, \eta \in \mathbb{R}$, the real part satisfies:
$$
\begin{gather}
\text{Re}(\zeta) = \xi \le |\xi| = \sqrt{\xi^2} \le \sqrt{\xi^2 + \eta^2} = |\zeta| \tag{17}
\end{gather}
$$
Applying step 17 to $\zeta = z \overline{w}$ gives:
$$
\begin{gather}
\text{Re}(z \overline{w}) \le |z \overline{w}| = |z| |\overline{w}| = |z| |w| \tag{18}
\end{gather}
$$
Applying the inequality of step 18 to step 16 yields:
$$
\begin{gather}
|z + w|^2 \le |z|^2 + 2 |z| |w| + |w|^2 = (|z| + |w|)^2 \tag{19}
\end{gather}
$$
Taking the principal non-negative square root of both sides of step 19 preserves the inequality, yielding:
$$
\begin{gather}
|z + w| \le |z| + |w| \tag{20}
\end{gather}
$$
which establishes the direct triangle inequality.

To prove the reverse triangle inequality, express $z$ as $z = (z - w) + w$. Applying step 20 gives:
$$
\begin{gather}
|z| = |(z - w) + w| \le |z - w| + |w| \implies |z| - |w| \le |z - w| \tag{21}
\end{gather}
$$
Similarly, express $w$ as $w = (w - z) + z$. Applying step 20 gives:
$$
\begin{gather}
|w| = |(w - z) + z| \le |w - z| + |z| \implies |w| - |z| \le |w - z| \tag{22}
\end{gather}
$$
Because $|w - z| = |-(z - w)| = |-1| |z - w| = |z - w|$, step 22 is equivalent to:
$$
\begin{gather}
-(|z| - |w|) \le |z - w| \tag{23}
\end{gather}
$$
Combining step 21 and step 23 shows that both $|z| - |w|$ and $-(|z| - |w|)$ are bounded from above by $|z - w|$. Thus:
$$
\begin{gather}
||z| - |w|| = \max\{|z| - |w|, \, -(|z| - |w|)\} \le |z - w| \tag{24}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$