---
dg-publish: true
---
The proofs for these propositions merely repeat the [[Proof of Consequences of Addition Axioms|proofs for the consequences of the addition axioms]], except for a change in the symbol and name of the operation. 

# Proposition 1
Let $1_{1}, 1_{2} \in \mathbb{R} \setminus \{0\}$ both satisfy the axiom of the multiplicative identity. Because $1_{1}$ and $1_{2}$ are multiplicative identities: $$ 1_{1} \cdot 1_{2} = 1_{1} \text{ and } 1_{2} \cdot 1_{1} = 1_{2} \tag{1} $$ By the commutativity of multiplication, $$ 1_{1} \cdot 1_{2} = 1_{2} \cdot 1_{1} \tag{2} $$ Equating the expressions yields$$ 1_{1} = 1_{1} \cdot 1_{2} = 1_{2} \cdot 1_{1} = 1_{2} \tag{3} $$ Therefore, the multiplicative identity element is unique and denoted by $1$.
$$
\begin{gather}
1_{1} = 1_{1} \cdot 1_{2} = 1_{2} \cdot 1_{1} = 1_{2} \tag{4}
\end{gather}
$$

---
# Proposition 2
Let $x \in \mathbb{R} \setminus \{0\}$, and suppose that $x_{1}, x_{2} \in \mathbb{R}$ both satisfy the conditions of being a multiplicative inverse of $x$, that is: $$ x \cdot x_{1} = x_{1} \cdot x = 1 \quad \text{and} \quad x \cdot x_{2} = x_{2} \cdot x = 1 \tag{5}$$ Beginning with $x_{1}$ and applying successively the identity axiom, the definition of $x_{2}$ as an inverse, associativity, the definition of $x_{1}$ as an inverse, and the identity axiom: $$ \begin{align} x_{1} &= x_{1} \cdot 1 \\[2mm] &= x_{1} \cdot (x \cdot x_{2}) \\[2mm] &= (x_{1} \cdot x) \cdot x_{2} \\[2mm] &= 1 \cdot x_{2} \\[2mm] &= x_{2} \tag{6} \end{align} $$ Therefore, the reciprocal is unique and is denoted unambiguously by $x^{-1}$ (or $\frac{1}{x}$).

---
# Proposition 3
Let $a \in \mathbb{R}\setminus \{ 0 \}$ and $b \in \mathbb{R}$ such that $a \cdot x = b$, with $x$ being some real number. Substitute the candidate value $x = b \cdot a^{-1}$ into the left-hand side of the equation. Utilizing the commutativity and associativity of multiplication: $$ \begin{align} a \cdot (b \cdot a^{-1}) &= a \cdot (a^{-1} \cdot b) \\[2mm] &= (a \cdot a^{-1}) \cdot b \\[2mm] &= 1 \cdot b \\[2mm] &= b \tag{7} \end{align} $$ Thus, $x = b \cdot a^{-1}$ satisfies the equation. 

Because $a \ne 0$, the inverse $a^{-1}$ exists. Multiplying both sides of the equation by $a^{-1}$: $$ \begin{align} a \cdot x = b &\implies a^{-1} \cdot (a \cdot x) = a^{-1} \cdot b \\[2mm] &\implies (a^{-1} \cdot a) \cdot x = b \cdot a^{-1} \\[2mm] &\implies 1 \cdot x = b \cdot a^{-1} \\[2mm] &\implies x = b \cdot a^{-1} \tag{8} \end{align} $$ Because this implication is reversible via multiplication by $a$, the solution is unique.
$$
\textbf{Q.E.D}
$$