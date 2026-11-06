---
dg-publish: true
---
Let $x, y \in \mathbb{R}$ be arbitrary elements of the field $(\mathbb{R}, +, \cdot)$.

--------------------------------------------------------------------------------
# Proposition 1
By the definition of the additive identity element, zero satisfies the equality $0 + 0 = 0$. Multiplying both sides of this equality by $x$ and applying the distributive axiom yields:
$$
x \cdot 0 = x \cdot (0 + 0) = x \cdot 0 + x \cdot 0 \tag{1}
$$
Because $x \cdot 0 \in \mathbb{R}$, it possesses a unique additive inverse $-(x \cdot 0)$. Adding this inverse to both sides of the equation in step 1 and utilizing the associativity of addition:
$$
x \cdot 0 + (-(x \cdot 0)) = (x \cdot 0 + x \cdot 0) + (-(x \cdot 0)) = x \cdot 0 + (x \cdot 0 + (-(x \cdot 0))) \tag{2}
$$
The left-hand side reduces directly to $0$ by the definition of the additive inverse, while the right-hand side simplifies to $x \cdot 0 + 0$, which equals $x \cdot 0$ by the additive identity axiom. Consequently, one obtains:
$$
x \cdot 0 = 0 \tag{3}
$$
By the commutativity of multiplication, $0 \cdot x = x \cdot 0 = 0$.

--------------------------------------------------------------------------------
# Proposition 2
Assume that $x \cdot y = 0$. If $x = 0$, the disjunction $(x = 0) \lor (y = 0)$ holds immediately. Suppose, therefore, that $x \neq 0$.

Because $x \in \mathbb{R} \setminus \{0\}$, the multiplicative inverse axiom guarantees the existence of a unique reciprocal $x^{-1} \in \mathbb{R}$ satisfying $x^{-1} \cdot x = 1$. Multiplying both sides of the equality $x \cdot y = 0$ by $x^{-1}$ and invoking Proposition 1:
$$
x^{-1} \cdot (x \cdot y) = x^{-1} \cdot 0 = 0 \tag{4}
$$
Applying the associative property of multiplication to the left-hand side transforms the expression into:
$$
(x^{-1} \cdot x) \cdot y = 1 \cdot y = y \tag{5}
$$
Equating the results of step 4 and step 5 demonstrates that $y = 0$. Thus, $(x \cdot y = 0) \implies (x = 0) \lor (y = 0)$.

--------------------------------------------------------------------------------
# Proposition 3
By the uniqueness of the additive inverse, an element $w \in \mathbb{R}$ satisfies $w = -x$ if and only if $x + w = 0$. It therefore suffices to demonstrate that the candidate product $(-1) \cdot x$ satisfies this condition.

Because $1$ is the multiplicative identity element, $x$ can be expressed as $1 \cdot x$. Adding $(-1) \cdot x$ to $x$ and factoring $x$ via the distributive property:
$$
x + (-1) \cdot x = 1 \cdot x + (-1) \cdot x = (1 + (-1)) \cdot x \tag{6}
$$
By definition of the additive inverse of the unit, $1 + (-1) = 0$. Substituting this result into step 6 and applying Proposition 1 produces:
$$
(1 + (-1)) \cdot x = 0 \cdot x = 0 \tag{7}
$$
Because $x + (-1) \cdot x = 0$, the product $(-1) \cdot x$ is the additive inverse of $x$. By the uniqueness of the negative, $-x = (-1) \cdot x$.

--------------------------------------------------------------------------------
# Proposition 4
Applying Proposition 3 directly to the element $-x$ demonstrates that its negative is obtained by scaling by $-1$:
$$
-(-x) = (-1) \cdot (-x) \tag{8}
$$
Observe that the additive inverse relation $-x + x = 0$ demonstrates that $x$ satisfies the defining condition of the additive inverse of $-x$. Because the negative of any real number is unique, the additive inverse of $-x$ is uniquely identified as $x$ itself, establishing the involution property:
$$
-(-x) = x \tag{9}
$$
Equating step 8 and step 9 yields $(-1)(-x) = x$.

--------------------------------------------------------------------------------
# Proposition 5
To verify the first identity, substitute $-x = (-1) \cdot x$ into the product and apply the associativity and commutativity of multiplication:
$$
(-x) \cdot y = ((-1) \cdot x) \cdot y = (-1) \cdot (x \cdot y) = -(x \cdot y) \tag{10}
$$
To verify the second identity, express both $-x$ and $-y$ as products with the negative unit via Proposition 3:
$$
(-x) \cdot (-y) = ((-1) \cdot x) \cdot ((-1) \cdot y) \tag{11}
$$
Rearranging the terms on the right-hand side using the commutativity and associativity of multiplication:
$$
((-1) \cdot x) \cdot ((-1) \cdot y) = [(-1) \cdot (-1)] \cdot (x \cdot y) \tag{12}
$$
Applying Proposition 4 with $x = 1$ demonstrates that $(-1) \cdot (-1) = 1$. Substituting this value into step 12 and invoking the multiplicative identity axiom produces:
$$
1 \cdot (x \cdot y) = x \cdot y \tag{13}
$$
Setting $y = x$ in step 13 immediately yields $(-x) \cdot (-x) = x \cdot x$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
