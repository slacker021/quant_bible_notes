---
dg-publish: true
---
Let $x, y, z \in \mathbb{R}$ be elements of the ordered field $(\mathbb{R}, +, \cdot, \le)$. Strict inequality $x < y$ is defined as $(x \le y) \wedge (x \ne y)$.

--------------------------------------------------------------------------------
# Proposition 1
### Existence
By the Totality Axiom of ordering: 
$$
\forall x, y \in \mathbb{R}, \quad (x \le y) \lor (y \le x) \tag{1}
$$
Evaluating the comparability of $x$ and $y$:
* If $x = y$, the relation $x = y$ holds directly.
* If $x \ne y$, the condition of step 1 requires that either $x \le y$ or $y \le x$.
* If $x \le y$, then because $x \ne y$, the definition of strict inequality yields $x < y$.
* If $y \le x$, then because $x \ne y$, the definition of strict inequality yields $y < x$ (that is, $x > y$).

Thus, at least one of the three relations $x < y$, $x = y$, or $x > y$ holds.

### Mutual Exclusivity
* Suppose $x = y$. Then the condition $x \ne y$ is false, which immediately precludes both $x < y$ and $x > y$ by the definition of strict inequality.
* Suppose $x < y$. By definition, $x \ne y$, which excludes $x = y$. If $x > y$ were also true, then $y \le x$. The conjunction $(x \le y) \wedge (y \le x)$ implies $x = y$ by the Antisymmetry Axiom, directly contradicting $x \ne y$. Hence, $x > y$ cannot hold.
* Suppose $x > y$. By symmetry, identical reasoning demonstrates that neither $x = y$ nor $x < y$ can hold.

Therefore, precisely one of the three relations holds.

--------------------------------------------------------------------------------
# Proposition 2
##### Assertion 1
Assume that $x < y$ and $y \le z$. By the definition of strict inequality, $x < y \implies (x \le y) \wedge (x \ne y)$. Applying the Transitivity Axiom for the non-strict order relation:
$$
(x \le y) \wedge (y \le z) \implies x \le z \tag{2}
$$
It remains to verify that $x \ne z$. Assume for the purpose of contradiction that $x = z$. Substituting $x$ for $z$ in the inequality $y \le z$ yields: 
$$
y \le x \tag{3}
$$
Combined with the initial condition $x \le y$, the Antisymmetry Axiom requires: 
$$
(x \le y) \wedge (y \le x) \implies x = y \tag{4}
$$
Step 4 directly contradicts the initial assumption that $x \ne y$. Therefore, $x \ne z$. Because $x \le z$ and $x \ne z$, it follows by definition that $x < z$.

##### Assertion 2
Assume that $x \le y$ and $y < z$. By definition, $y < z \implies (y \le z) \wedge (y \ne z)$. By the Transitivity Axiom: 
$$
(x \le y) \wedge (y \le z) \implies x \le z \tag{5}
$$
Assume for the purpose of contradiction that $x = z$. Substituting $z$ for $x$ in the inequality $x \le y$ yields: 
$$
z \le y \tag{6}
$$
Combined with $y \le z$, the Antisymmetry Axiom requires: 
$$
(y \le z) \wedge (z \le y) \implies y = z \tag{7}
$$
Step 7 directly contradicts the initial assumption that $y \ne z$. Therefore, $x \ne z$. Because $x \le z$ and $x \ne z$, it follows by definition that $x < z$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
