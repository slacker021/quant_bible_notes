---
dg-publish: true
---
The interaction between the order relation $\le$ and the arithmetic operations on $\mathbb{R}$ is governed by the two Compatibility Axioms of an ordered field: $$ \begin{gather} \forall x, y, z \in \mathbb{R}, \quad (x \le y) \implies (x + z \le y + z) \tag{1} \\ \forall x, y \in \mathbb{R}, \quad (0 \le x) \wedge (0 \le y) \implies (0 \le x \cdot y) \tag{2} \end{gather} $$Strict inequality $x < y$ is defined as $(x \le y) \wedge (x \ne y)$. The following propositions detail the algebraic consequences of these compatibility rules. 

---
# Proposition 1
Assume that $x < y$. By definition of strict inequality, $x \le y$ and $x \ne y$. Applying the additive compatibility axiom in step 1 to the weak inequality $x \le y$ ensures that $x + z \le y + z$. 

It remains to demonstrate that $x + z \ne y + z$. Assume for the purpose of contradiction that $x + z = y + z$. Adding the additive inverse $-z$ to both sides and invoking the associativity and identity axioms yields $$ (x + z) + (-z) = (y + z) + (-z) \implies x + 0 = y + 0 \implies x = y \tag{3} $$ This equality directly contradicts the initial condition that $x \ne y$. Therefore, $x + z \ne y + z$, which together with $x + z \le y + z$ establishes that $x + z < y + z$.  

---
# Proposition 2
Assume that $0 < x$. Applying proposition 1 by adding the unique additive inverse $-x$ to both sides of the strict inequality yields $$ 0 + (-x) < x + (-x) \tag{4} $$By the additive identity axiom, the left-hand side evaluates to $-x$. By the additive inverse axiom, the right-hand side evaluates to $0$. Substituting these values into the inequality of step 4 produces $-x < 0$. 

---
# Proposition 3
Assume that $x \le y$ and $z \le w$. Adding $z$ to both sides of the inequality $x \le y$ via compatibility axiom (1) gives $x + z \le y + z$. Similarly, adding $y$ to both sides of the inequality $z \le w$ gives $z + y \le w + y$. By the commutativity of addition, this second inequality is rewritten as $y + z \le y + w$. Combining both results produces the chain $$ x + z \le y + z \le y + w \tag{5} $$ Applying the Transitivity Axiom of the order relation to the chain of step 5 yields $x + z \le y + w$. 

---
# Proposition 4
Assume that $x \le y$ and $z < w$. By the compatibility axiom of step 1, adding $z$ to both sides of $x \le y$ produces $x + z \le y + z$. Concurrently, proposition 1 allows $y$ to be added to both sides of the strict inequality $z < w$, yielding $z + y < w + y$, which by commutativity states that $y + z < y + w$. One now has the simultaneous conditions $x + z \le y + z$ and $y + z < y + w$. By the transitivity of strict inequalities established as a consequence of the order axioms, this conjunction implies $x + z < y + w$. 

---
# Proposition 5
Assume that $0 < x$ and $0 < y$. By definition of strict inequality, these assumptions imply that $0 \le x$ and $0 \le y$, while $x \ne 0$ and $y \ne 0$. Applying the multiplicative compatibility axiom seen in step 2 guarantees that $0 \le xy$. 
It remains to verify that $xy \ne 0$. By proposition 2 of the connection axioms, a product of two real numbers equals zero if and only if at least one factor is zero. Because both $x \ne 0$ and $y \ne 0$, it follows that $xy \ne 0$. Because $0 \le xy$ and $xy \ne 0$, one concludes by definition that $0 < xy$. 

---
# Proposition 6
Assume that $x < 0$ and $y < 0$. By proposition 2, inverting the sign of these negative quantities establishes that their additive inverses are strictly positive, so that $0 < -x$ and $0 < -y$. Applying proposition 5 to these positive quantities demonstrates that their product is strictly positive: $$ 0 < (-x)(-y) \tag{6} $$According to proposition 5 of the connection axioms, the product of two additive inverses satisfies $(-x)(-y) = xy$. Substituting this identity into the inequality of step 6 immediately yields $0 < xy$. 

---
# Proposition 7
 Assume that $x < 0$ and $0 < y$. By proposition 2, $x < 0$ implies that $0 < -x$. Because $-x$ and $y$ are both strictly positive elements, proposition 5 dictates that their product is strictly positive: $$ 0 < (-x)y \tag{7} $$By Proposition 5 of the connection axioms, $(-x)y = -(xy)$. Substituting this into the inequality of step 14 gives $0 < -(xy)$. Applying proposition 2 to this positive quantity inverts the sign again, showing that $-(-(xy)) < 0$. Because $-(-(xy)) = xy$, this concludes that $xy < 0$. 

---
# Proposition 8
Assume that $x < y$ and $0 < z$. Adding $-x$ to both sides of the inequality $x < y$ via proposition 1 yields $0 < y - x$. Because both $y - x$ and $z$ are strictly positive elements, proposition 5 guarantees that their product is strictly positive: $$ 0 < (y - x)z \tag{8} $$Distributing $z$ across the difference produces $0 < yz - xz$. Adding the term $xz$ to both sides of this strict inequality via proposition 1 yields $xz < yz$. 

---
# Proposition 9 
Assume that $x < y$ and $z < 0$. Adding $-x$ to both sides of $x < y$ yields $0 < y - x$. Because $y - x$ is strictly positive and $z$ is strictly negative, proposition 7 requires their product to be strictly negative: $$ (y - x)z < 0 \tag{9} $$Applying the distributive law transforms the inequality of step 9 into $yz - xz < 0$. Adding $xz$ to both sides via proposition 1 establishes the reversed inequality $yz < xz$. 

---
# Proposition 10
The non-triviality axiom of multiplication dictates that $1 \ne 0$. By the Law of Trichotomy established under the order axioms, exactly one of the two relations $0 < 1$ or $1 < 0$ must hold. Assume for the purpose of contradiction that $1 < 0$. Setting $x = 1$ and $y = 1$ in proposition 6 demonstrates that the product of two negative numbers is strictly positive, which implies that $1 \cdot 1 > 0$. However, by the multiplicative identity axiom, $1 \cdot 1 = 1$, which forces the conclusion that $1 > 0$. This directly contradicts the assumption that $1 < 0$. Because $1 < 0$ leads to a contradiction, the only remaining possibility permitted by trichotomy is $0 < 1$. 

---
# Proposition 11

Assume that $0 < x$. The reciprocal $x^{-1}$ cannot equal zero, because if $x^{-1} = 0$, then $x \cdot x^{-1} = x \cdot 0 = 0$, which contradicts the defining identity $x \cdot x^{-1} = 1$ since $1 \ne 0$. By the Law of Trichotomy, either $0 < x^{-1}$ or $x^{-1} < 0$. Assume for the purpose of contradiction that $x^{-1} < 0$. Because $0 < x$ and $x^{-1} < 0$, proposition 7 dictates that their product must be strictly negative, which means that $x \cdot x^{-1} < 0$. However, $x \cdot x^{-1} = 1$, which requires $1 < 0$. This directly contradicts Proposition 10, which proved that $0 < 1$. Therefore, $x^{-1} < 0$ is impossible, leaving $0 < x^{-1}$ as the only valid relation. 

---
# Proposition 12
Assume that $0 < x$ and $x < y$. By transitivity of strict inequalities, $0 < y$. Applying proposition 11 to both positive numbers establishes that their reciprocals are also strictly positive, so that $0 < x^{-1}$ and $0 < y^{-1}$. Applying proposition 5 to these two positive reciprocals ensures that their product is strictly positive: $$ 0 < x^{-1} \cdot y^{-1} \tag{10} $$ Because $x^{-1} \cdot y^{-1}$ is strictly positive, proposition 8 allows the inequality $x < y$ to be multiplied by this product without changing the direction of the inequality: $$ x \cdot (x^{-1} \cdot y^{-1}) < y \cdot (x^{-1} \cdot y^{-1}) \tag{11} $$Utilizing the associativity and commutativity of multiplication, the left-hand side simplifies to $$ (x \cdot x^{-1}) \cdot y^{-1} = 1 \cdot y^{-1} = y^{-1} \tag{12} $$ while the right-hand side simplifies to $$ (y \cdot y^{-1}) \cdot x^{-1} = 1 \cdot x^{-1} = x^{-1} \tag{13} $$ Substituting these simplified expressions into the inequality of step 13 yields $y^{-1} < x^{-1}$. Combined with the positivity condition $0 < y^{-1}$, one concludes that $0 < y^{-1} < x^{-1}$. $$ \textbf{Q.E.D} $$