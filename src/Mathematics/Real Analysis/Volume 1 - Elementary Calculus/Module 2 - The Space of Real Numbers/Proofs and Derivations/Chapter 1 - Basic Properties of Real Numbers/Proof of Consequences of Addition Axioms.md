---
dg-publish: true
---
The following propositions are derived directly from the axioms of addition on the Abelian group $(\mathbb{R}, +)$. 
# Proposition 1
Proof Let $0_{1}, 0_{2} \in \mathbb{R}$ both satisfy the axiom of the additive identity. 1. Because $0_{2}$ is an additive identity element, $$ 0_{1} + 0_{2} = 0_{1} \tag{1} $$ 2. Because $0_{1}$ is an additive identity element, $$ 0_{2} + 0_{1} = 0_{2} \tag{2} $$ 3. By the commutativity of addition, $$ 0_{1} + 0_{2} = 0_{2} + 0_{1} \tag{3} $$ Equating the identities yields$$ 0_{1} = 0_{1} + 0_{2} = 0_{2} + 0_{1} = 0_{2} \tag{4} $$ Therefore, the neutral element is unique.  

---
# Proposition 2: 
Let $x \in \mathbb{R}$, and suppose that $x_{1}, x_{2} \in \mathbb{R}$ both satisfy the condition of being an additive inverse of $x$, that is$$ x + x_{1} = x_{1} + x = 0 \quad \text{and} \quad x + x_{2} = x_{2} + x = 0 \tag{5}$$ Beginning with $x_{1}$ and applying successively the identity axiom, the definition of $x_{2}$ as an inverse, associativity, the definition of $x_{1}$ as an inverse, and the identity axiom: $$ \begin{align} x_{1} &= x_{1} + 0 \\[2mm] &= x_{1} + (x + x_{2}) \\[2mm] &= (x_{1} + x) + x_{2} \\[2mm] &= 0 + x_{2} \\[2mm] &= x_{2} \tag{5} \end{align} $$ Therefore, the additive inverse of $x$ is unique and is denoted unambiguously by $-x$. 

---
# Proposition 3: Solvability of Linear Additive Equations 
Let $a + x = b$. Substitute the candidate value $x = b + (-a)$ into the left-hand side of the equation, where by the commutativity and associativity of addition,  $$ \begin{align} a + (b + (-a)) &= a + ((-a) + b) \\[2mm] &= (a + (-a)) + b \\[2mm] &= 0 + b \\[2mm] &= b \tag{6} \end{align} $$Thus, $x = b + (-a)$ is indeed a solution to the equation. 

Now, let $x \in \mathbb{R}$ be any element satisfying $a + x = b$. Adding the unique negative $(-a)$ to both sides of the equation: $$ \begin{align} a + x = b &\implies (a + x) + (-a) = b + (-a) \\[2mm] &\implies (x + a) + (-a) = b + (-a) \\[2mm] &\implies x + (a + (-a)) = b + (-a) \\[2mm] &\implies x + 0 = b + (-a) \\[2mm] &\implies x = b + (-a) \tag{7} \end{align} $$Because every step in this chain of implications is invertible via the addition of $a$, the solution is unique.
$$
\textbf{Q.E.D}
$$
