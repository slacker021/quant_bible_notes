---
dg-publish: true
---
Let $(\mathbb{R}, +, \cdot, \le)$ and $(\mathbb{R}', +', \cdot', \le')$ be two complete linearly ordered fields with respective additive identities $0, 0'$ and multiplicative identities $1, 1'$.

# Construction of the Canonical Rational Isomorphism
Let $\mathbb{N} \subset \mathbb{R}$ and $\mathbb{N}' \subset \mathbb{R}'$ denote the minimal inductive subsets containing $1$ and $1'$, respectively. Define the mapping $f_{\mathbb{Z}}: \mathbb{Z} \to \mathbb{Z}'$ by setting $f_{\mathbb{Z}}(0) := 0'$, and for any $n \in \mathbb{N}$:
$$
f_{\mathbb{Z}}(n) := \sum_{k=1}^n 1' =: n' \quad \wedge \quad f_{\mathbb{Z}}(-n) := -n' \tag{1}
$$
By mathematical induction, $f_{\mathbb{Z}}$ is a strictly order-preserving ring isomorphism from $\mathbb{Z}$ onto $\mathbb{Z}'$. Extending this mapping to the rational subfield $\mathbb{Q} \subset \mathbb{R}$ by setting:
$$
f_{\mathbb{Q}}\left(\frac{m}{n}\right) := f_{\mathbb{Z}}(m) \cdot' (f_{\mathbb{Z}}(n))^{-1} = \frac{m'}{n'} \quad (m \in \mathbb{Z}, \, n \in \mathbb{N}) \tag{2}
$$
yields a well-defined, bijective, strictly order-preserving field isomorphism $f_{\mathbb{Q}}: \mathbb{Q} \to \mathbb{Q}'$.

# Extension to the Real Continuum
For any real scalar $x \in \mathbb{R}$, define the set of rational lower bounds:
$$
L_x := \{ r \in \mathbb{Q} \mid r \le x \} \tag{3}
$$
By the density of $\mathbb{Q}$ in $\mathbb{R}$, $L_x$ is non-empty, bounded above by any integer $M > x$, and satisfies $x = \sup L_x$. Consider the image of $L_x$ under $f_{\mathbb{Q}}$ within $\mathbb{R}'$:
$$
f_{\mathbb{Q}}(L_x) := \{ f_{\mathbb{Q}}(r) \in \mathbb{Q}' \mid r \in L_x \} \subset \mathbb{R}' \tag{4}
$$
Because $f_{\mathbb{Q}}$ is an order-preserving isomorphism on $\mathbb{Q}$, every element of $f_{\mathbb{Q}}(L_x)$ is bounded above in $\mathbb{R}'$ by $f_{\mathbb{Q}}(M) = M'$. By the Least Upper Bound Axiom in $\mathbb{R}'$, the supremum of this image set exists. Define the mapping $f: \mathbb{R} \to \mathbb{R}'$ by:
$$
f(x) := \sup' f_{\mathbb{Q}}(L_x) \tag{5}
$$
For any $q \in \mathbb{Q}$, the rational set $L_q$ achieves its maximum at $q$, which ensures $f(q) = f_{\mathbb{Q}}(q)$. Thus, $f$ extends $f_{\mathbb{Q}}$.

# Monotonicity and Bijectivity
Let $x, y \in \mathbb{R}$ with $x < y$. By the density of $\mathbb{Q}$ in $\mathbb{R}$, there exist rational scalars $r_1, r_2 \in \mathbb{Q}$ such that $x < r_1 < r_2 < y$. For every $r \in L_x$, the relation $r \le x < r_1$ requires $f_{\mathbb{Q}}(r) \le' f_{\mathbb{Q}}(r_1)$. Concurrently, $r_2 \in L_y$, which establishes that: 
$$
f(x) = \sup' f_{\mathbb{Q}}(L_x) \le' f_{\mathbb{Q}}(r_1) <' f_{\mathbb{Q}}(r_2) \le' \sup' f_{\mathbb{Q}}(L_y) = f(y) \tag{6}
$$
Thus, $x < y \implies f(x) <' f(y)$, which proves that $f$ is strictly increasing and injective.

To establish surjectivity, let $y' \in \mathbb{R}'$ be an arbitrary element. Define the set $S := \{ r \in \mathbb{Q} \mid f_{\mathbb{Q}}(r) \le' y' \}$. By the Archimedean property of $\mathbb{R}'$ and the isomorphism of $f_{\mathbb{Q}}$, $S$ is a non-empty subset of $\mathbb{R}$ bounded above. Setting $x := \sup S \in \mathbb{R}$ yields $f(x) = y'$, confirming that $f$ is surjective.

# Preservation of Arithmetic Operations
By the density of $\mathbb{Q}$, the Minkowski sum of lower bounds satisfies $\sup(L_x + L_y) = x + y$. Applying the supremum property of Minkowski sums in $\mathbb{R}'$:
$$
\begin{align}
f(x + y) &= \sup' f_{\mathbb{Q}}(L_{x+y}) = \sup' f_{\mathbb{Q}}(L_x + L_y) \\[2mm]
&= \sup' \big( f_{\mathbb{Q}}(L_x) +' f_{\mathbb{Q}}(L_y) \big) = \sup' f_{\mathbb{Q}}(L_x) +' \sup' f_{\mathbb{Q}}(L_y) \\[2mm]
&= f(x) +' f(y) \tag{7}
\end{align}
$$
Similarly, for positive elements $x, y > 0$, taking positive rational lower bounds yields $f(x \cdot y) = f(x) \cdot' f(y)$, which extends to all of $\mathbb{R}$ via sign symmetry.

# Uniqueness
Any order-preserving field isomorphism $g: \mathbb{R} \to \mathbb{R}'$ must map $1 \mapsto 1'$, forcing $g|_{\mathbb{Q}} = f_{\mathbb{Q}}$. Because $g$ preserves the order structure, it preserves suprema:
$$
g(x) = g(\sup L_x) = \sup' g(L_x) = \sup' f_{\mathbb{Q}}(L_x) = f(x) \tag{8}
$$
Therefore, the ordered field isomorphism between $\mathbb{R}$ and $\mathbb{R}'$ is unique.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
