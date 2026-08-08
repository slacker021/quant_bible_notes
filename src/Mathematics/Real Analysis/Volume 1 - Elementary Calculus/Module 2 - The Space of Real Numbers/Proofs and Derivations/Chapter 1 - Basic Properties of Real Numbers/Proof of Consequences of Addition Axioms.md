---
dg-publish: true
---
Let $a, b, x \in \mathbb{R}$ be elements of the additive Abelian group $(\mathbb{R}, +)$.

--------------------------------------------------------------------------------
# Proposition 1
Let $0_1, 0_2 \in \mathbb{R}$ both satisfy the axiom of the additive identity. 

Because $0_2$ is an additive identity element:
$$
0_1 + 0_2 = 0_1 \tag{1}
$$
Because $0_1$ is an additive identity element:
$$
0_2 + 0_1 = 0_2 \tag{2}
$$
By the commutativity of addition: 
$$
0_1 + 0_2 = 0_2 + 0_1 \tag{3}
$$
Combining step 1, step 2, and step 3 yields: 
$$
0_1 = 0_1 + 0_2 = 0_2 + 0_1 = 0_2 \tag{4}
$$
Therefore, the additive identity element is unique and denoted unambiguously by $0$.

--------------------------------------------------------------------------------
# Proposition 2
Let $x \in \mathbb{R}$, and suppose that $x_1, x_2 \in \mathbb{R}$ both satisfy the condition of being an additive inverse of $x$:
$$
x + x_1 = x_1 + x = 0 \quad \wedge \quad x + x_2 = x_2 + x = 0 \tag{5}
$$
Beginning with $x_1$ and successively applying the additive identity axiom, the definition of $x_2$ as an inverse, associativity, the definition of $x_1$ as an inverse, and the additive identity axiom:
$$
\begin{align}
x_1 &= x_1 + 0 \\[2mm]
&= x_1 + (x + x_2) \\[2mm]
&= (x_1 + x) + x_2 \\[2mm]
&= 0 + x_2 \\[2mm]
&= x_2 \tag{6}
\end{align}
$$
Therefore, the additive inverse of $x$ is unique and denoted unambiguously by $-x$.

--------------------------------------------------------------------------------
# Proposition 3
### Existence
Substitute the candidate value $x = b + (-a)$ into the left-hand side of the linear equation $a + x = b$. By the commutativity and associativity of addition: 
$$
\begin{align}
a + (b + (-a)) &= a + ((-a) + b) \\[2mm]
&= (a + (-a)) + b \\[2mm]
&= 0 + b \\[2mm]
&= b \tag{7}
\end{align}
$$
Thus, $x = b + (-a) =: b - a$ satisfies the equation, establishing existence.

### Uniqueness
Let $x \in \mathbb{R}$ be an arbitrary solution satisfying $a + x = b$. Adding the unique additive inverse $(-a)$ to both sides of the equality:
$$
\begin{align}
a + x = b &\implies (a + x) + (-a) = b + (-a) \\[2mm]
&\implies (x + a) + (-a) = b + (-a) \\[2mm]
&\implies x + (a + (-a)) = b + (-a) \\[2mm]
&\implies x + 0 = b + (-a) \\[2mm]
&\implies x = b + (-a) \tag{8}
\end{align}
$$
Because any candidate solution $x$ is uniquely determined as $b + (-a)$, the solution is unique.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
