---
dg-publish: true
---
Let $x, y, z, w \in \mathbb{R}$ be elements of the ordered field $(\mathbb{R}, +, \cdot, \le)$. The compatibility axioms establish that
$$
\forall x, y, z \in \mathbb{R}, \quad (x \le y) \implies (x + z \le y + z) \tag{1}
$$
$$
\forall x, y \in \mathbb{R}, \quad (0 \le x) \wedge (0 \le y) \implies (0 \le x \cdot y) \tag{2}
$$
Strict inequality $x < y$ is defined as $(x \le y) \wedge (x \ne y)$.

--------------------------------------------------------------------------------
# Proposition 1
Assume that $x < y$. By definition of strict inequality, $x \le y$ and $x \ne y$. Applying the additive compatibility axiom in step 1 to the weak inequality $x \le y$ ensures that $x + z \le y + z$. 

It remains to demonstrate that $x + z \ne y + z$. Assume for the purpose of contradiction that $x + z = y + z$. Adding the additive inverse $-z$ to both sides and invoking the associativity and identity axioms: 
$$
(x + z) + (-z) = (y + z) + (-z) \implies x + 0 = y + 0 \implies x = y \tag{3}
$$
Step 3 directly contradicts the initial condition that $x \ne y$. Therefore, $x + z \ne y + z$, which together with $x + z \le y + z$ establishes that $x + z < y + z$.

--------------------------------------------------------------------------------
# Proposition 2
Assume that $0 < x$. Applying Proposition 1 by adding the unique additive inverse $-x$ to both sides of the strict inequality:
$$
0 + (-x) < x + (-x) \tag{4}
$$
By the additive identity axiom, the left-hand side evaluates to $-x$. By the additive inverse axiom, the right-hand side evaluates to $0$. Substituting these values into step 4 produces $-x < 0$.

--------------------------------------------------------------------------------
# Proposition 3
Assume that $x \le y$ and $z \le w$. Adding $z$ to both sides of the inequality $x \le y$ via step 1 gives $x + z \le y + z$. Similarly, adding $y$ to both sides of the inequality $z \le w$ gives $z + y \le w + y$. By the commutativity of addition, this second inequality is rewritten as $y + z \le y + w$. Combining both results produces the chain: 
$$
x + z \le y + z \le y + w \tag{5}
$$
Applying the Transitivity Axiom of the order relation to step 5 yields $x + z \le y + w$.

--------------------------------------------------------------------------------
# Proposition 4
Assume that $x \le y$ and $z < w$. By step 1, adding $z$ to both sides of $x \le y$ produces $x + z \le y + z$. Concurrently, Proposition 1 allows $y$ to be added to both sides of the strict inequality $z < w$, yielding $z + y < w + y$, which by commutativity states that $y + z < y + w$. Combining these simultaneous conditions:
$$
(x + z \le y + z) \wedge (y + z < y + w) \tag{6}
$$
By the transitivity of strict inequalities, step 6 implies that $x + z < y + w$.

--------------------------------------------------------------------------------
# Proposition 5
Assume that $0 < x$ and $0 < y$. By definition of strict inequality, these assumptions imply that $0 \le x$ and $0 \le y$, while $x \ne 0$ and $y \ne 0$. Applying the multiplicative compatibility axiom in step 2 guarantees that $0 \le xy$. 

It remains to verify that $xy \ne 0$. A product of two real numbers equals zero if and only if at least one factor is zero. Because both $x \ne 0$ and $y \ne 0$, it follows that $xy \ne 0$. Because $0 \le xy$ and $xy \ne 0$, one concludes by definition that $0 < xy$.

--------------------------------------------------------------------------------
# Proposition 6
Assume that $x < 0$ and $y < 0$. By Proposition 2, inverting the sign of these negative quantities establishes that their additive inverses are strictly positive: $0 < -x$ and $0 < -y$. Applying Proposition 5 to these positive quantities demonstrates that their product is strictly positive:
$$
0 < (-x)(-y) \tag{7}
$$
The product of two additive inverses satisfies $(-x)(-y) = xy$. Substituting this identity into step 7 immediately yields $0 < xy$.

--------------------------------------------------------------------------------
# Proposition 7
Assume that $x < 0$ and $0 < y$. By Proposition 2, $x < 0$ implies that $0 < -x$. Because $-x$ and $y$ are both strictly positive elements, Proposition 5 dictates that their product is strictly positive: 
$$
0 < (-x)y \tag{8}
$$
Because $(-x)y = -(xy)$, substituting this into step 8 gives $0 < -(xy)$. Applying Proposition 2 to this positive quantity inverts the sign again, showing that $-(-(xy)) < 0$. Because $-(-(xy)) = xy$, it follows that $xy < 0$.

--------------------------------------------------------------------------------
# Proposition 8
Assume that $x < y$ and $0 < z$. Adding $-x$ to both sides of the inequality $x < y$ via Proposition 1 yields $0 < y - x$. Because both $y - x$ and $z$ are strictly positive elements, Proposition 5 guarantees that their product is strictly positive: 
$$
0 < (y - x)z \tag{9}
$$
Distributing $z$ across the difference produces $0 < yz - xz$. Adding the term $xz$ to both sides of this strict inequality via Proposition 1 yields $xz < yz$.

--------------------------------------------------------------------------------
# Proposition 9
Assume that $x < y$ and $z < 0$. Adding $-x$ to both sides of $x < y$ yields $0 < y - x$. Because $y - x$ is strictly positive and $z$ is strictly negative, Proposition 7 requires their product to be strictly negative: 
$$
(y - x)z < 0 \tag{10}
$$
Applying the distributive law transforms step 10 into $yz - xz < 0$. Adding $xz$ to both sides via Proposition 1 establishes the reversed inequality $yz < xz$.

--------------------------------------------------------------------------------
# Proposition 10
Let $x \in \mathbb{R} \setminus \{0\}$. By the Law of Trichotomy, either $0 < x$ or $x < 0$.
* Case 1: If $0 < x$, applying Proposition 5 with $y = x$ demonstrates that $0 < x \cdot x = x^2$.
* Case 2: If $x < 0$, applying Proposition 6 with $y = x$ demonstrates that $0 < x \cdot x = x^2$.

In both cases, $x^2 > 0$ holds for all $x \ne 0$.

--------------------------------------------------------------------------------
# Proposition 11
By the non-triviality condition of the multiplicative identity, $1 \in \mathbb{R} \setminus \{0\}$, meaning $1 \ne 0$. Because $1 = 1^2$, applying Proposition 10 with $x = 1$ immediately yields: 
$$
0 < 1 \tag{11}
$$

--------------------------------------------------------------------------------
# Proposition 12
Assume that $0 < x$. The reciprocal $x^{-1}$ cannot equal zero, because if $x^{-1} = 0$, then $x \cdot x^{-1} = x \cdot 0 = 0$, which contradicts the defining identity $x \cdot x^{-1} = 1$ since $1 \ne 0$. By the Law of Trichotomy, either $0 < x^{-1}$ or $x^{-1} < 0$. 

Assume for the purpose of contradiction that $x^{-1} < 0$. Because $0 < x$ and $x^{-1} < 0$, Proposition 7 dictates that their product must be strictly negative:
$$
x \cdot x^{-1} < 0 \implies 1 < 0 \tag{12}
$$
Step 12 directly contradicts Proposition 11, which proved that $0 < 1$. Therefore, $x^{-1} < 0$ is impossible, leaving $0 < x^{-1}$ as the only valid relation.

--------------------------------------------------------------------------------
# Proposition 13
Assume that $0 < x$ and $x < y$. By transitivity of strict inequalities, $0 < y$. Applying Proposition 12 to both positive numbers establishes that their reciprocals are strictly positive: $0 < x^{-1}$ and $0 < y^{-1}$. Applying Proposition 5 to these two positive reciprocals ensures that their product is strictly positive:
$$
0 < x^{-1} \cdot y^{-1} \tag{13}
$$
Because $x^{-1} \cdot y^{-1} > 0$, Proposition 8 allows the inequality $x < y$ to be multiplied by this product without reversing the inequality:
$$
x \cdot (x^{-1} \cdot y^{-1}) < y \cdot (x^{-1} \cdot y^{-1}) \tag{14}
$$
Utilizing the associativity and commutativity of multiplication, the left-hand side simplifies to: 
$$
(x \cdot x^{-1}) \cdot y^{-1} = 1 \cdot y^{-1} = y^{-1} \tag{15}
$$
The right-hand side simplifies to: 
$$
(y \cdot y^{-1}) \cdot x^{-1} = 1 \cdot x^{-1} = x^{-1} \tag{16}
$$
Substituting step 15 and step 16 into step 14 yields $y^{-1} < x^{-1}$. Combined with $0 < y^{-1}$, one concludes that $0 < y^{-1} < x^{-1}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
