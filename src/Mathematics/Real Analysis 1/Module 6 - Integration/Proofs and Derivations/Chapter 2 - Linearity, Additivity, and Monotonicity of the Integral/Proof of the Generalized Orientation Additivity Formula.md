---
dg-publish: true
---
Let $J \subset \mathbb{R}$ be an interval, and let $f: J \to \mathbb{R}$ be a real function that is Riemann integrable on every compact subinterval of $J$.

Recall the standard boundary and orientation conventions for definite integrals: for any point $u \in J$, the integral over a degenerate single-point interval is defined by:
$$
\begin{gather}
\int_u^u f(x)\,dx := 0 \tag{1}
\end{gather}
$$
and for any pair of points $u, v \in J$ with $u < v$, the integral with inverted orientation is defined by:
$$
\begin{gather}
\int_v^u f(x)\,dx := -\int_u^v f(x)\,dx \tag{2}
\end{gather}
$$

The convention of step 2 is equivalent to the skew-symmetric identity:
$$
\begin{gather}
\int_u^v f(x)\,dx + \int_v^u f(x)\,dx = 0 \tag{3}
\end{gather}
$$
for all $u, v \in J$.

Recall also the classical Interval Additivity Theorem ([[Proof of Interval Additivity of the Definite Integral]]): whenever three points $u, v, w \in J$ satisfy the strict spatial ordering $u < v < w$,
$$
\begin{gather}
\int_u^w f(x)\,dx = \int_u^v f(x)\,dx + \int_v^w f(x)\,dx \tag{4}
\end{gather}
$$

Let $a, b, c \in J$ be three arbitrary points. The objective is to establish that:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{5}
\end{gather}
$$
holds unconditionally across all possible relative orderings and coincidences of the points $a, b, c$.

---
# Case 1
Suppose that at least two of the three points $a, b, c$ coincide.

If $a = b$, the left-hand side of step 5 satisfies $\int_a^a f(x)\,dx = 0$ by step 1. By step 2 and step 3, the right-hand side of step 5 evaluates to:
$$
\begin{gather}
\int_a^c f(x)\,dx + \int_c^a f(x)\,dx = \int_a^c f(x)\,dx - \int_a^c f(x)\,dx = 0 \tag{6}
\end{gather}
$$
which matches the left-hand side.

If $a = c$, then $\int_a^c f(x)\,dx = \int_a^a f(x)\,dx = 0$ by step 1. The right-hand side of step 5 becomes:
$$
\begin{gather}
\int_a^a f(x)\,dx + \int_a^b f(x)\,dx = 0 + \int_a^b f(x)\,dx = \int_a^b f(x)\,dx \tag{7}
\end{gather}
$$
which matches the left-hand side.

If $b = c$, then $\int_c^b f(x)\,dx = \int_b^b f(x)\,dx = 0$ by step 1. The right-hand side of step 5 becomes:
$$
\begin{gather}
\int_a^b f(x)\,dx + \int_b^b f(x)\,dx = \int_a^b f(x)\,dx + 0 = \int_a^b f(x)\,dx \tag{8}
\end{gather}
$$
which matches the left-hand side.

If $a = b = c$, every integral in step 5 evaluates to zero by step 1, satisfying $0 = 0 + 0$.

Therefore, whenever two or more points coincide, step 5 holds.

---
# Case 2
Suppose that the points $a, b, c$ are pairwise distinct: $a \ne b$, $b \ne c$, and $a \ne c$. The three distinct real numbers admit exactly $3! = 6$ possible strict orderings on the real line.

### Permutation 1
In this configuration, $c$ lies strictly between the initial point $a$ and terminal point $b$. The classical Interval Additivity Theorem of step 4 applies directly with $u = a$, $v = c$, and $w = b$:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{9}
\end{gather}
$$
which proves step 5 for this permutation.

### Permutation 2
Applying classical interval additivity to the ordered triple $a < b < c$ yields:
$$
\begin{gather}
\int_a^c f(x)\,dx = \int_a^b f(x)\,dx + \int_b^c f(x)\,dx \tag{10}
\end{gather}
$$

Subtracting $\int_b^c f(x)\,dx$ from both sides of step 10:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx - \int_b^c f(x)\,dx \tag{11}
\end{gather}
$$

Applying the orientation inversion identity of step 2 to the second term gives $-\int_b^c f(x)\,dx = \int_c^b f(x)\,dx$. Substituting this into step 11 yields:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{12}
\end{gather}
$$

### Permutation 3
Applying classical interval additivity to the ordered triple $c < a < b$ yields:
$$
\begin{gather}
\int_c^b f(x)\,dx = \int_c^a f(x)\,dx + \int_a^b f(x)\,dx \tag{13}
\end{gather}
$$

Subtracting $\int_c^a f(x)\,dx$ from both sides of step 13:
$$
\begin{gather}
\int_a^b f(x)\,dx = -\int_c^a f(x)\,dx + \int_c^b f(x)\,dx \tag{14}
\end{gather}
$$

Applying the orientation inversion identity of step 2 to $-\int_c^a f(x)\,dx$ yields $-\int_c^a f(x)\,dx = \int_a^c f(x)\,dx$. Substituting this into step 14 gives:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{15}
\end{gather}
$$

### Permutation 4
Applying classical interval additivity to the ordered triple $b < c < a$ yields:
$$
\begin{gather}
\int_b^a f(x)\,dx = \int_b^c f(x)\,dx + \int_c^a f(x)\,dx \tag{16}
\end{gather}
$$

Multiplying both sides of step 16 by $-1$:
$$
\begin{gather}
-\int_b^a f(x)\,dx = -\int_c^a f(x)\,dx - \int_b^c f(x)\,dx \tag{17}
\end{gather}
$$

Applying the orientation inversion identity of step 2 to each term:
$$
\begin{gather}
-\int_b^a f(x)\,dx = \int_a^b f(x)\,dx, \qquad -\int_c^a f(x)\,dx = \int_a^c f(x)\,dx, \qquad -\int_b^c f(x)\,dx = \int_c^b f(x)\,dx \tag{18}
\end{gather}
$$

Substituting the identities of step 18 into step 17 yields:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{19}
\end{gather}
$$

### Permutation 5
Applying classical interval additivity to the ordered triple $b < a < c$ yields:
$$
\begin{gather}
\int_b^c f(x)\,dx = \int_b^a f(x)\,dx + \int_a^c f(x)\,dx \tag{20}
\end{gather}
$$

Subtracting $\int_b^a f(x)\,dx$ from both sides of step 20:
$$
\begin{gather}
\int_a^c f(x)\,dx = -\int_b^a f(x)\,dx + \int_b^c f(x)\,dx \tag{21}
\end{gather}
$$

By step 2, $-\int_b^a f(x)\,dx = \int_a^b f(x)\,dx$. Substituting this into step 21:
$$
\begin{gather}
\int_a^c f(x)\,dx = \int_a^b f(x)\,dx + \int_b^c f(x)\,dx \tag{22}
\end{gather}
$$

Subtracting $\int_b^c f(x)\,dx$ from both sides of step 22 and applying $-\int_b^c f(x)\,dx = \int_c^b f(x)\,dx$ gives:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{23}
\end{gather}
$$

### Permutation 6
Applying classical interval additivity to the ordered triple $c < b < a$ yields:
$$
\begin{gather}
\int_c^a f(x)\,dx = \int_c^b f(x)\,dx + \int_b^a f(x)\,dx \tag{24}
\end{gather}
$$

Subtracting $\int_c^b f(x)\,dx$ from both sides of step 24:
$$
\begin{gather}
\int_b^a f(x)\,dx = \int_c^a f(x)\,dx - \int_c^b f(x)\,dx \tag{25}
\end{gather}
$$

Multiplying both sides of step 25 by $-1$:
$$
\begin{gather}
-\int_b^a f(x)\,dx = -\int_c^a f(x)\,dx + \int_c^b f(x)\,dx \tag{26}
\end{gather}
$$

Applying the orientation identities $-\int_b^a f(x)\,dx = \int_a^b f(x)\,dx$ and $-\int_c^a f(x)\,dx = \int_a^c f(x)\,dx$ to step 26:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{27}
\end{gather}
$$

Because the identity holds for all cases of coincident points and across all six permutations of mutually distinct points, the generalized additivity formula is unconditionally valid for all points $a, b, c \in J$:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{28}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
