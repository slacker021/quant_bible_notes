---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ and $(\mathbb{R}', +', \cdot', \le')$ be complete linearly ordered fields. Let $f: \mathbb{R} \to \mathbb{R}'$ be a non-trivial order-preserving ring homomorphism, such that $f$ is not identically zero and satisfies for all $x, y \in \mathbb{R}$:
$$
f(x + y) = f(x) +' f(y), \quad f(x \cdot y) = f(x) \cdot' f(y), \quad (x \le y \implies f(x) \le' f(y)) \tag{1}
$$

# Preservation of Identity Elements
Because $0 + 0 = 0$ in $\mathbb{R}$, applying the additive homomorphism property gives:
$$
f(0) = f(0 + 0) = f(0) +' f(0) \tag{2}
$$
Adding the additive inverse $-f(0)$ in $\mathbb{R}'$ to both sides of step 2 yields:
$$
f(0) = 0' \tag{3}
$$
Similarly, for any $x \in \mathbb{R}$:
$$
0' = f(0) = f(x + (-x)) = f(x) +' f(-x) \implies f(-x) = -f(x) \tag{4}
$$
Next, because $1 \cdot 1 = 1$ in $\mathbb{R}$:
$$
f(1) = f(1 \cdot 1) = f(1) \cdot' f(1) \implies f(1) \cdot' (f(1) -' 1') = 0' \tag{5}
$$
Because $\mathbb{R}'$ is a field, step 5 requires that either $f(1) = 0'$ or $f(1) = 1'$. If $f(1) = 0'$, then for every $x \in \mathbb{R}$:
$$
f(x) = f(x \cdot 1) = f(x) \cdot' f(1) = f(x) \cdot' 0' = 0' \tag{6}
$$
Step 6 contradicts the premise that $f$ is non-trivial. Therefore:
$$
f(1) = 1' \tag{7}
$$

# Restriction to Integers and Rational Numbers
For any natural number $n \in \mathbb{N}$, mathematical induction utilizing step 1 and step 7 demonstrates that:
$$
f(n) = f\left(\sum_{k=1}^n 1\right) = \sum_{k=1}^n f(1) = \sum_{k=1}^n 1' =: n' \in \mathbb{N}' \tag{8}
$$
Because $1' >' 0'$ in the ordered field $\mathbb{R}'$, step 8 establishes that $f(n) = n' >' 0'$ for all $n \in \mathbb{N}$. Combining this with step 4 demonstrates that $f(-n) = -n'$ for all $-n \in -\mathbb{N}$. Thus, $f$ maps $\mathbb{Z}$ into $\mathbb{Z}'$.

Now consider an arbitrary rational number $r = \frac{m}{n} \in \mathbb{Q}$ with $m \in \mathbb{Z}$ and $n \in \mathbb{N}$. Because $n \ge 1$, $f(n) = n' >' 0'$, which ensures that the reciprocal $(f(n))^{-1}$ exists in $\mathbb{R}'$. Applying the multiplicative homomorphism property to the identity $m = \frac{m}{n} \cdot n$ yields:
$$
f(m) = f\left(\frac{m}{n}\right) \cdot' f(n) \implies f\left(\frac{m}{n}\right) = f(m) \cdot' (f(n))^{-1} = \frac{m'}{n'} \in \mathbb{Q}' \tag{9}
$$
If $r = \frac{m}{n} > 0$ with $n \in \mathbb{N}$, then $m \in \mathbb{N}$, which implies $m' >' 0'$ and $n' >' 0'$, forcing $f(r) = \frac{m'}{n'} >' 0'$. 

Consequently, for any rational numbers $r_1, r_2 \in \mathbb{Q}$ with $r_1 < r_2$, the difference satisfies $r_2 - r_1 > 0$. Applying the homomorphism properties:
$$
f(r_2) -' f(r_1) = f(r_2 - r_1) >' 0' \iff f(r_1) <' f(r_2) \tag{10}
$$
Thus, the restriction $f|_{\mathbb{Q}}: \mathbb{Q} \to \mathbb{Q}'$ is a strictly order-preserving field isomorphism from $\mathbb{Q}$ onto the rational subfield $\mathbb{Q}' \subset \mathbb{R}'$.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
