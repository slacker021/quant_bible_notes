---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be a non-empty subset, let $x_0 \in E \cap E'$ be an accumulation point of $E$, and let $f: E \to \mathbb{R}$ and $g: E \to \mathbb{R}$ be functions that are differentiable at $x_0$. Assume that $g(x_0) \neq 0$.

Define the quotient mapping $\left(\frac{f}{g}\right): E \setminus g^{-1}(\{0\}) \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
\left(\frac{f}{g}\right)(x) := \frac{f(x)}{g(x)} \tag{1}
\end{gather}
$$

By virtue of the principle that [[Proof that Differentiability Implies Continuity|differentiability implies continuity]], the differentiability of $g$ at $x_0$ guarantees that $g$ is continuous at $x_0$:
$$
\begin{gather}
\lim_{E \ni x \to x_0} g(x) = g(x_0) \tag{2}
\end{gather}
$$

Because $g(x_0) \neq 0$, the local preservation of sign property for continuous functions implies that there exists an open neighborhood $U(x_0) \subset \mathbb{R}$ such that $g(x) \neq 0$ for all $x \in E \cap U(x_0)$. 

For any point $x \in (E \cap U(x_0)) \setminus \{x_0\}$, the difference quotient of the quotient function is given by:
$$
\begin{gather}
\frac{\left(\frac{f}{g}\right)(x) - \left(\frac{f}{g}\right)(x_0)}{x - x_0} = \frac{\frac{f(x)}{g(x)} - \frac{f(x_0)}{g(x_0)}}{x - x_0} \tag{3}
\end{gather}
$$

Expressing the numerator in step 3 over a common denominator yields:
$$
\begin{gather}
\frac{\frac{f(x)}{g(x)} - \frac{f(x_0)}{g(x_0)}}{x - x_0} = \frac{f(x)g(x_0) - f(x_0)g(x)}{(x - x_0)g(x)g(x_0)} \tag{4}
\end{gather}
$$

Adding and subtracting the intermediate term $f(x_0)g(x_0)$ in the numerator of step 4 produces:
$$
\begin{gather}
f(x)g(x_0) - f(x_0)g(x) = \big(f(x)g(x_0) - f(x_0)g(x_0)\big) - \big(f(x_0)g(x) - f(x_0)g(x_0)\big) \tag{5}
\end{gather}
$$

Factoring common elements across the groupings in step 5 gives:
$$
\begin{gather}
f(x)g(x_0) - f(x_0)g(x) = \big(f(x) - f(x_0)\big)g(x_0) - f(x_0)\big(g(x) - g(x_0)\big) \tag{6}
\end{gather}
$$

Substituting step 6 back into step 4 allows rewriting the quotient as:
$$
\begin{gather}
\frac{\left(\frac{f}{g}\right)(x) - \left(\frac{f}{g}\right)(x_0)}{x - x_0} = \frac{1}{g(x)g(x_0)} \left[ \left(\frac{f(x) - f(x_0)}{x - x_0}\right) g(x_0) - f(x_0) \left(\frac{g(x) - g(x_0)}{x - x_0}\right) \right] \tag{7}
\end{gather}
$$

Because $f$ and $g$ are differentiable at $x_0$, the respective limits of their difference quotients are finite real quantities:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{g(x) - g(x_0)}{x - x_0} = g'(x_0) \tag{9}
\end{gather}
$$

Moreover, by step 2 and the quotient rule for limits, the prefactor satisfies:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{1}{g(x)g(x_0)} = \frac{1}{[g(x_0)]^2} \tag{10}
\end{gather}
$$

Applying the algebraic limit theorems for products and differences to step 7 using step 8, step 9, and step 10 produces:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{\left(\frac{f}{g}\right)(x) - \left(\frac{f}{g}\right)(x_0)}{x - x_0} = \frac{1}{[g(x_0)]^2} \big[ f'(x_0)g(x_0) - f(x_0)g'(x_0) \big] \tag{11}
\end{gather}
$$

Simplifying step 11 yields the final derivative expression:
$$
\begin{gather}
\left(\frac{f}{g}\right)'(x_0) = \frac{f'(x_0)g(x_0) - f(x_0)g'(x_0)}{[g(x_0)]^2} \tag{12}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
