---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be an open neighborhood of $x_0 \in \mathbb{R}$, and let $f: E \to \mathbb{R}$ be continuous at $x_0$. 

Consider a general affine polynomial mapping $L: \mathbb{R} \to \mathbb{R}$ defined by:
$$
\begin{gather}
L(x) := c_0 + c_1(x - x_0) \tag{1}
\end{gather}
$$
where $c_0, c_1 \in \mathbb{R}$ are arbitrary real constants.

The condition that $L(x)$ achieves contact of order at least one with $f$ at the anchor point $x_0$ is defined by the asymptotic relation:
$$
\begin{gather}
f(x) - L(x) = o(x - x_0) \quad \text{as } x \to x_0 \tag{2}
\end{gather}
$$
By virtue of the definition of Landau little-$o$ notation, step 2 is equivalent to the limit statement:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f(x) - L(x)}{x - x_0} = 0 \tag{3}
\end{gather}
$$

**Determination and Uniqueness of the Constant Term $c_0$:**
Express the difference $f(x) - L(x)$ for $x \neq x_0$ as the product:
$$
\begin{gather}
f(x) - L(x) = \left( \frac{f(x) - L(x)}{x - x_0} \right) \cdot (x - x_0) \tag{4}
\end{gather}
$$
Taking the limit as $x \to x_0$ across step 4 and applying the product rule for limits in conjunction with step 3 yields:
$$
\begin{gather}
\lim_{x \to x_0} \big(f(x) - L(x)\big) = \left( \lim_{x \to x_0} \frac{f(x) - L(x)}{x - x_0} \right) \cdot \left( \lim_{x \to x_0} (x - x_0) \right) = 0 \cdot 0 = 0 \tag{5}
\end{gather}
$$

Because $f$ is continuous at $x_0$, $\lim_{x \to x_0} f(x) = f(x_0)$. Furthermore, the affine mapping $L$ is a polynomial, and is therefore continuous everywhere on $\mathbb{R}$, with $\lim_{x \to x_0} L(x) = L(x_0) = c_0 + c_1(0) = c_0$. Applying the difference rule for limits to step 5 produces:
$$
\begin{gather}
\lim_{x \to x_0} \big(f(x) - L(x)\big) = f(x_0) - c_0 = 0 \implies c_0 = f(x_0) \tag{6}
\end{gather}
$$
Thus, the zeroth-order coefficient $c_0$ is uniquely determined as $f(x_0)$.

**Determination and Uniqueness of the Slope Coefficient $c_1$:**
Substituting the value $c_0 = f(x_0)$ from step 6 into the definition of $L(x)$ gives $L(x) = f(x_0) + c_1(x - x_0)$. The quotient of step 3 then becomes:
$$
\begin{gather}
\frac{f(x) - L(x)}{x - x_0} = \frac{f(x) - f(x_0) - c_1(x - x_0)}{x - x_0} = \frac{f(x) - f(x_0)}{x - x_0} - c_1 \tag{7}
\end{gather}
$$

Taking the limit as $x \to x_0$ across step 7 yields:
$$
\begin{gather}
\lim_{x \to x_0} \left( \frac{f(x) - f(x_0)}{x - x_0} - c_1 \right) = 0 \tag{8}
\end{gather}
$$
By the linearity of limits, step 8 is equivalent to:
$$
\begin{gather}
c_1 = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} \tag{9}
\end{gather}
$$

By definition, the limit on the right-hand side of step 9 is the derivative $f'(x_0)$. Because step 9 holds if and only if the difference quotient converges to $c_1$, the slope coefficient $c_1$ is uniquely determined as:
$$
\begin{gather}
c_1 = f'(x_0) \tag{10}
\end{gather}
$$

**Sufficiency of the Tangent Function:**
Conversely, assume that $f$ is differentiable at $x_0$, and define the tangent mapping $T: \mathbb{R} \to \mathbb{R}$ by:
$$
\begin{gather}
T(x) := f(x_0) + f'(x_0)(x - x_0) \tag{11}
\end{gather}
$$
Subtracting $T(x)$ from $f(x)$ and dividing by the displacement $x - x_0$ yields:
$$
\begin{gather}
\frac{f(x) - T(x)}{x - x_0} = \frac{f(x) - f(x_0)}{x - x_0} - f'(x_0) \tag{12}
\end{gather}
$$
Evaluating the limit as $x \to x_0$ gives:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f(x) - T(x)}{x - x_0} = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} - f'(x_0) = f'(x_0) - f'(x_0) = 0 \tag{13}
\end{gather}
$$
Step 13 confirms that $f(x) - T(x) = o(x - x_0)$.

If any other affine function $L(x) = c_0 + c_1(x - x_0)$ is chosen with $(c_0, c_1) \neq (f(x_0), f'(x_0))$, then:
1. If $c_0 \neq f(x_0)$, then $\lim_{x \to x_0} (f(x) - L(x)) = f(x_0) - c_0 \neq 0$, in which case the quotient $\frac{f(x) - L(x)}{x - x_0}$ diverges, failing step 3.
2. If $c_0 = f(x_0)$ but $c_1 \neq f'(x_0)$, then by step 7:
$$
\begin{gather}
\lim_{x \to x_0} \frac{f(x) - L(x)}{x - x_0} = f'(x_0) - c_1 \neq 0 \tag{14}
\end{gather}
$$
which fails to vanish.

Thus, $T(x) = f(x_0) + f'(x_0)(x - x_0)$ is the unique affine mapping achieving contact of order at least one with $f$ at $x_0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$