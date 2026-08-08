---
dg-publish: true
---
Let $a, b, x \in \mathbb{R}$ be elements of the multiplicative group structure of the field $(\mathbb{R}, +, \cdot)$.

--------------------------------------------------------------------------------
# Proposition 1
Let $1_1, 1_2 \in \mathbb{R} \setminus \{0\}$ both satisfy the axiom of the multiplicative identity. 

Because $1_2$ is a multiplicative identity element:
$$
1_1 \cdot 1_2 = 1_1 \tag{1}
$$
Because $1_1$ is a multiplicative identity element:
$$
1_2 \cdot 1_1 = 1_2 \tag{2}
$$
By the commutativity of multiplication: 
$$
1_1 \cdot 1_2 = 1_2 \cdot 1_1 \tag{3}
$$
Combining step 1, step 2, and step 3 yields: 
$$
1_1 = 1_1 \cdot 1_2 = 1_2 \cdot 1_1 = 1_2 \tag{4}
$$
Therefore, the multiplicative identity element is unique and denoted unambiguously by $1$.

--------------------------------------------------------------------------------
# Proposition 2
Let $x \in \mathbb{R} \setminus \{0\}$, and suppose that $x_1, x_2 \in \mathbb{R}$ both satisfy the condition of being a multiplicative inverse of $x$:
$$
x \cdot x_1 = x_1 \cdot x = 1 \quad \wedge \quad x \cdot x_2 = x_2 \cdot x = 1 \tag{5}
$$
Beginning with $x_1$ and successively applying the multiplicative identity axiom, the definition of $x_2$ as an inverse, associativity, the definition of $x_1$ as an inverse, and the multiplicative identity axiom:
$$
\begin{align}
x_1 &= x_1 \cdot 1 \\[2mm]
&= x_1 \cdot (x \cdot x_2) \\[2mm]
&= (x_1 \cdot x) \cdot x_2 \\[2mm]
&= 1 \cdot x_2 \\[2mm]
&= x_2 \tag{6}
\end{align}
$$
Therefore, the multiplicative inverse of $x$ is unique and denoted unambiguously by $x^{-1}$ (or $\frac{1}{x}$).

--------------------------------------------------------------------------------
# Proposition 3
Let $a \in \mathbb{R} \setminus \{0\}$ and $b \in \mathbb{R}$.

### Existence
Substitute the candidate value $x = b \cdot a^{-1}$ into the left-hand side of the linear equation $a \cdot x = b$. Utilizing the commutativity and associativity of multiplication:
$$
\begin{align}
a \cdot (b \cdot a^{-1}) &= a \cdot (a^{-1} \cdot b) \\[2mm]
&= (a \cdot a^{-1}) \cdot b \\[2mm]
&= 1 \cdot b \\[2mm]
&= b \tag{7}
\end{align}
$$
Thus, $x = b \cdot a^{-1} =: \frac{b}{a}$ satisfies the equation, establishing existence.

### Uniqueness
Let $x \in \mathbb{R}$ be an arbitrary element satisfying $a \cdot x = b$. Because $a \neq 0$, the unique reciprocal $a^{-1}$ exists. Multiplying both sides by $a^{-1}$:
$$
\begin{align}
a \cdot x = b &\implies a^{-1} \cdot (a \cdot x) = a^{-1} \cdot b \\[2mm]
&= (a^{-1} \cdot a) \cdot x = b \cdot a^{-1} \\[2mm]
&= 1 \cdot x = b \cdot a^{-1} \\[2mm]
&= x = b \cdot a^{-1} \tag{8}
\end{align}
$$
Because any candidate solution $x$ is uniquely determined as $b \cdot a^{-1}$, the solution is unique.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
