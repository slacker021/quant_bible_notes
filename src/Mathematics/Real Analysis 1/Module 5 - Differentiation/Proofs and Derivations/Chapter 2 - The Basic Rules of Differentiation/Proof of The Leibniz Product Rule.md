---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be a non-empty subset, let $x_0 \in E \cap E'$ be an accumulation point of $E$, and let $f: E \to \mathbb{R}$ and $g: E \to \mathbb{R}$ be functions that are differentiable at $x_0$.

Define the product mapping $(fg): E \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
(fg)(x) := f(x)g(x), \quad \forall x \in E \tag{1}
\end{gather}
$$

By virtue of the theorem establishing that [[Proof that Differentiability Implies Continuity|differentiability implies continuity]], the differentiability of $g$ at $x_0$ guarantees that $g$ is continuous at $x_0$, which implies:
$$
\begin{gather}
\lim_{E \ni x \to x_0} g(x) = g(x_0) \tag{2}
\end{gather}
$$

For any displacement point $x \in E \setminus \{x_0\}$, the difference quotient of the product mapping takes the form:
$$
\begin{gather}
\frac{(fg)(x) - (fg)(x_0)}{x - x_0} = \frac{f(x)g(x) - f(x_0)g(x_0)}{x - x_0} \tag{3}
\end{gather}
$$

Adding and subtracting the intermediate cross-term $f(x_0)g(x)$ in the numerator of step 3 produces:
$$
\begin{gather}
\frac{(fg)(x) - (fg)(x_0)}{x - x_0} = \frac{f(x)g(x) - f(x_0)g(x) + f(x_0)g(x) - f(x_0)g(x_0)}{x - x_0} \tag{4}
\end{gather}
$$

Factoring the common terms across the two components in step 4 yields the identity:
$$
\begin{gather}
\frac{(fg)(x) - (fg)(x_0)}{x - x_0} = g(x) \left[\frac{f(x) - f(x_0)}{x - x_0}\right] + f(x_0) \left[\frac{g(x) - g(x_0)}{x - x_0}\right] \tag{5}
\end{gather}
$$

Because $f$ and $g$ are differentiable at $x_0$, the respective limits of the bracketed incremental quotients exist:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{6}
\end{gather}
$$
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{g(x) - g(x_0)}{x - x_0} = g'(x_0) \tag{7}
\end{gather}
$$

Applying the sum and product rules for limits of functions to step 5 in conjunction with step 2, step 6, and step 7 yields:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{(fg)(x) - (fg)(x_0)}{x - x_0} = \left(\lim_{E \ni x \to x_0} g(x)\right)\left(\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}\right) + f(x_0)\left(\lim_{E \ni x \to x_0} \frac{g(x) - g(x_0)}{x - x_0}\right) \tag{8}
\end{gather}
$$

Evaluating the limits in step 8 gives:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{(fg)(x) - (fg)(x_0)}{x - x_0} = g(x_0) f'(x_0) + f(x_0) g'(x_0) = f'(x_0)g(x_0) + f(x_0)g'(x_0) \tag{9}
\end{gather}
$$

Because this limit exists as a finite real number, the product function $(fg)$ is differentiable at $x_0$, and its derivative satisfies:
$$
\begin{gather}
(fg)'(x_0) = f'(x_0)g(x_0) + f(x_0)g'(x_0) \tag{10}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
