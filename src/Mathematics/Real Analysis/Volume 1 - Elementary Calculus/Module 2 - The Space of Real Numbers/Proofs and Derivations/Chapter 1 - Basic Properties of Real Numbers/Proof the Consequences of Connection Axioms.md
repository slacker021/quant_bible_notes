---
dg-publish: true
---
# Proof of Consequences of the Connection Axiom
The connection between the operations of addition and multiplication in the field of real numbers is governed by the distributive axiom, which asserts that multiplication distributes over addition:
$$
\forall x, y, z \in \mathbb{R}, \quad (x + y)z = xz + yz \tag{1}
$$
By the commutativity of multiplication, multiplication also distributes from the left, so that $x(y + z) = xy + xz$. From this fundamental link, the elementary sign rules and the interaction of zero with multiplication are derived.

# Proposition 1
By the definition of the additive identity element, zero satisfies the equality $0 + 0 = 0$. Multiplying both sides of this equality by $x$ and applying the distributive axiom from the left yields
$$
x \cdot 0 = x \cdot (0 + 0) = x \cdot 0 + x \cdot 0 \tag{2}
$$
Because $x \cdot 0$ is an element of $\mathbb{R}$, it possesses a unique additive inverse $-(x \cdot 0)$. Adding this inverse to both sides of the equation in step 2 and utilizing the associativity of addition gives
$$
x \cdot 0 + (-(x \cdot 0)) = (x \cdot 0 + x \cdot 0) + (-(x \cdot 0)) = x \cdot 0 + (x \cdot 0 + (-(x \cdot 0))) \tag{3}
$$
The left-hand side reduces directly to $0$ by the definition of the additive inverse, while the right-hand side simplifies to $x \cdot 0 + 0$, which equals $x \cdot 0$ by the identity axiom. Consequently, one obtains $x \cdot 0 = 0$. Finally, by the commutativity of multiplication, $0 \cdot x = x \cdot 0 = 0$. 

---
# Proposition 2
Assume that $x \cdot y = 0$. If $x = 0$, the proposition holds immediately without further deduction. Suppose, therefore, that $x \ne 0$. 

Because $x$ is a non-zero element of $\mathbb{R}$, the multiplicative inverse axiom guarantees the existence of a unique reciprocal $x^{-1} \in \mathbb{R}$ satisfying $x^{-1} \cdot x = 1$. Multiplying both sides of the initial assumption $x \cdot y = 0$ by $x^{-1}$ and invoking Proposition 1 yields
$$
x^{-1} \cdot (x \cdot y) = x^{-1} \cdot 0 = 0 \tag{4}
$$
Applying the associative property of multiplication to the left-hand side transforms the expression into
$$
(x^{-1} \cdot x) \cdot y = 1 \cdot y = y \tag{5}
$$
Equating expressions (6) and (7) demonstrates that $y = 0$. Thus, whenever $x$ is not equal to zero, $y$ is necessarily zero, which proves that the field of real numbers contains no non-trivial zero divisors.

---
# Proposition 3
By the uniqueness of the additive inverse established under the addition axioms, an element $w \in \mathbb{R}$ is the negative of $x$ if and only if $x + w = 0$. It therefore suffices to demonstrate that the product $(-1) \cdot x$ satisfies this condition.

Recalling that $1$ is the multiplicative identity element, $x$ can be expressed as $1 \cdot x$. Adding $(-1) \cdot x$ to $x$ and factoring $x$ to the right via the distributive property gives
$$
x + (-1) \cdot x = 1 \cdot x + (-1) \cdot x = (1 + (-1)) \cdot x \tag{6}
$$
By definition of the additive inverse of the unit, $1 + (-1) = 0$. Substituting this result into equation (9) and applying Proposition 1 produces
$$
(1 + (-1)) \cdot x = 0 \cdot x = 0 \tag{7}
$$
Because $x + (-1) \cdot x = 0$, the product $(-1) \cdot x$ behaves as an additive inverse to $x$. By the uniqueness of the negative, one concludes that $-x = (-1) \cdot x$.

---
# Proposition 4
Applying Proposition 3 directly to the element $-x$ shows that its negative is obtained by scaling by $-1$:
$$
-(-x) = (-1) \cdot (-x) \tag{8}
$$
To evaluate $-(-x)$, observe that the additive inverse relation $-x + x = 0$ demonstrates that $x$ satisfies the defining condition of the negative of $-x$. Because the negative of any real number is unique, the additive inverse of $-x$ is uniquely identified as $x$ itself, establishing the involution property $-(-x) = x$. Substituting this identity into equation (12) yields $(-1)(-x) = x$.

---
# Proposition 5
For arbitrary elements $x, y \in \mathbb{R}$, the product of their additive inverses satisfies
$$
(-x) \cdot y = -(x \cdot y) \quad \text{and} \quad (-x) \cdot (-y) = x \cdot y \tag{9}
$$
In particular, setting $y = x$ yields $(-x) \cdot (-x) = x \cdot x$.

To verify the first equality, substitute $-x = (-1) \cdot x$ into the product and apply the associativity and commutativity of multiplication:
$$
(-x) \cdot y = ((-1) \cdot x) \cdot y = (-1) \cdot (x \cdot y) = -(x \cdot y) \tag{10}
$$
To verify the second equality, express both $-x$ and $-y$ as products with the negative unit via Proposition 3, which yields
$$
(-x) \cdot (-y) = ((-1) \cdot x) \cdot ((-1) \cdot y) \tag{11}
$$
Rearranging the terms on the right-hand side using the commutativity and associativity of multiplication groups the negative units together:
$$
((-1) \cdot x) \cdot ((-1) \cdot y) = [(-1) \cdot (-1)] \cdot (x \cdot y) \tag{12}
$$
Applying Proposition 4 with $x = 1$ demonstrates that $(-1) \cdot (-1) = 1$. Substituting this value into equation (16) and invoking the multiplicative identity axiom produces
$$
1 \cdot (x \cdot y) = x \cdot y \tag{13}
$$
Setting $y = x$ immediately yields $(-x) \cdot (-x) = x \cdot x$, confirming that the product of two additive inverses is identical to the product of the original elements.
$$
\textbf{Q.E.D}
$$

