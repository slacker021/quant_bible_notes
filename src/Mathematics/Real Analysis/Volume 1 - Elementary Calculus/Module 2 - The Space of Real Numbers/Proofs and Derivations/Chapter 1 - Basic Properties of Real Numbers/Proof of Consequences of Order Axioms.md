---
dg-publish: true
---
The axiom of ordering asserts that 
$$
x < y \iff x \leq y \wedge x \neq y \tag{1}
$$
where $x$ and $y$ are real numbers. 

# Proposition 1

### Existence
By the Totality Axiom of ordering, 
$$ \forall x, y \in \mathbb{R}, \quad (x \le y) \lor (y \le x) \tag{2} $$
* If $x = y$, the relation $x = y$ holds. 
* If $x \ne y$, the condition of step 2 requires that either $x \le y$ or $y \le x$. * If $x \le y$, then since $x \ne y$, the definition of strict inequality yields $x < y$. * If $y \le x$, then since $x \ne y$, the definition of strict inequality yields $y < x$ (that is, $x > y$).

Thus, at least one of the relations hold. 

### Mutual Exclusivity
* Suppose $x = y$. Then the condition $x \ne y$ is false, which immediately precludes both $x < y$ and $x > y$ by step 1. 
- Suppose $x < y$. By step 1, $x \ne y$, which excludes $x = y$. If $x > y$ were also true, then $y \le x$. The conjunction $(x \le y) \wedge (y \le x)$ implies $x = y$ by the Antisymmetry Axiom, directly contradicting $x \ne y$. Hence, $x > y$ cannot hold. 
- Suppose $x > y$. By symmetry, identical reasoning shows that neither $x = y$ nor $x < y$ can hold. Therefore, precisely one of the three relations holds.

Therefore, only one of the relations holds. 

---
# Proposition 2
In addition to $x$ and $y$, let $z$ be another real number in the domain of discourse. 

### Assertion 1
Assume that $x < y$ and $y \le z$. 
By the definition of strict inequality, $x < y \implies (x \le y) \wedge (x \ne y)$. By the Transitivity Axiom for the non-strict order relation, $$ (x \le y) \wedge (y \le z) \implies x \le z \tag{3} $$
It remains to verify that $x \ne z$. Assume for the purpose of contradiction that $x = z$. Substituting $x$ for $z$ in the inequality $y \le z$ yields$$ y \le x \tag{4}$$Combined with the initial condition $x \le y$, the Antisymmetry Axiom requires$$ (x \le y) \wedge (y \le x) \implies x = y \tag{5}$$This directly contradicts the initial assumption that $x \ne y$. Therefore, $x \ne z$. Because $x \le z$ and $x \ne z$, it follows by definition that $x < z$.

### Assertion 2
Assume that $x \le y$ and $y < z$. By definition, $y < z \implies (y \le z) \wedge (y \ne z)$. By the Transitivity Axiom,$$ (x \le y) \wedge (y \le z) \implies x \le z \tag{6} $$Assume for the purpose of contradiction that $x = z$. Substituting $z$ for $x$ in the inequality $x \le y$ yields$$ z \le y \tag{7}$$ Combined with $y \le z$, the Antisymmetry Axiom requires$$ (y \le z) \wedge (z \le y) \implies y = z \tag{8}$$ This directly contradicts the initial assumption that $y \ne z$. Therefore, $x \ne z$. Because $x \le z$ and $x \ne z$, it follows by definition that $x < z$.
$$
\textbf{Q.E.D}
$$