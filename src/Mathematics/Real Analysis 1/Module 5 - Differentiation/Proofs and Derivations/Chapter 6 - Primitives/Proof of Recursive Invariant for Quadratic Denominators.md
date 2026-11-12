---
dg-publish: true
---
Let $n \in \mathbb{N}$ with $n \ge 1$. Consider the parametric family of indefinite integrals defined on $\mathbb{R}$ by:
$$
\begin{gather}
I_n(x) := \int \frac{dx}{(x^2 + 1)^n} \tag{1}
\end{gather}
$$
where each element of the family represents the set of all primitive mappings of the rational function $f_n(x) = (x^2 + 1)^{-n}$ on the real line $\mathbb{R}$.

---
# Proposition 1
Let $n = 1$. The rational function $f_1(x) = \frac{1}{x^2 + 1}$ is continuous and defined everywhere on $\mathbb{R}$. By the standard derivative of the inverse circular function $\arctan(x)$, the derivative satisfies:
$$
\begin{gather}
\frac{d}{dx} \arctan(x) = \frac{1}{x^2 + 1} \tag{2}
\end{gather}
$$
It follows directly from the definition of the indefinite integral as the complete collection of primitives differing by an arbitrary real constant $C \in \mathbb{R}$ that:
$$
\begin{gather}
I_1(x) = \int \frac{dx}{x^2 + 1} = \arctan(x) + C \tag{3}
\end{gather}
$$

---
# Proposition 2
Let $n \ge 1$ be a fixed integer. In the integral $I_n(x)$ defined in step 1, assign the integration by parts decomposition:
$$
\begin{gather}
u(x) := \frac{1}{(x^2 + 1)^n} = (x^2 + 1)^{-n}, \quad dv := dx \tag{4}
\end{gather}
$$
Differentiating $u(x)$ via the chain rule produces the differential:
$$
\begin{gather}
du = -n (x^2 + 1)^{-n-1} \cdot (2x) \, dx = -\frac{2n x}{(x^2 + 1)^{n+1}} \, dx \tag{5}
\end{gather}
$$
Integrating the differential $dv = dx$ yields the primitive factor:
$$
\begin{gather}
v(x) = x \tag{6}
\end{gather}
$$
Applying the integration by parts formula $\int u \, dv = u v - \int v \, du$ to $I_n(x)$ yields:
$$
\begin{gather}
I_n(x) = \frac{x}{(x^2 + 1)^n} - \int x \left( -\frac{2n x}{(x^2 + 1)^{n+1}} \right) dx = \frac{x}{(x^2 + 1)^n} + 2n \int \frac{x^2}{(x^2 + 1)^{n+1}} \, dx \tag{7}
\end{gather}
$$

Decompose the algebraic numerator in the integral on the right-hand side of step 7 by adding and subtracting unity:
$$
\begin{gather}
x^2 = (x^2 + 1) - 1 \tag{8}
\end{gather}
$$
Substituting the algebraic decomposition of step 8 into the integral produces:
$$
\begin{gather}
\int \frac{x^2}{(x^2 + 1)^{n+1}} \, dx = \int \frac{(x^2 + 1) - 1}{(x^2 + 1)^{n+1}} \, dx = \int \frac{dx}{(x^2 + 1)^n} - \int \frac{dx}{(x^2 + 1)^{n+1}} \tag{9}
\end{gather}
$$
By virtue of the definition of the index sequence in step 1, the two integrals on the right-hand side of step 9 correspond precisely to $I_n(x)$ and $I_{n+1}(x)$:
$$
\begin{gather}
\int \frac{x^2}{(x^2 + 1)^{n+1}} \, dx = I_n(x) - I_{n+1}(x) \tag{10}
\end{gather}
$$

Substitute the result of step 10 back into step 7:
$$
\begin{gather}
I_n(x) = \frac{x}{(x^2 + 1)^n} + 2n \big( I_n(x) - I_{n+1}(x) \big) \tag{11}
\end{gather}
$$
Expanding the bracketed term in step 11 yields:
$$
\begin{gather}
I_n(x) = \frac{x}{(x^2 + 1)^n} + 2n I_n(x) - 2n I_{n+1}(x) \tag{12}
\end{gather}
$$
Transposing the term $2n I_{n+1}(x)$ to the left-hand side and isolating it produces:
$$
\begin{gather}
2n I_{n+1}(x) = \frac{x}{(x^2 + 1)^n} + (2n - 1) I_n(x) \tag{13}
\end{gather}
$$
Because $n \ge 1$, the integer coefficient $2n$ is non-zero. Dividing both sides of step 13 by $2n$ gives the recurrence relation:
$$
\begin{gather}
I_{n+1}(x) = \frac{x}{2n(x^2 + 1)^n} + \frac{2n - 1}{2n} I_n(x) \tag{14}
\end{gather}
$$
for all $n \ge 1$.

---
# Proposition 3
Let $a > 0$ and consider the generalized quadratic denominator integral:
$$
\begin{gather}
J_n(x; a) := \int \frac{dx}{(x^2 + a^2)^n} \tag{15}
\end{gather}
$$
Factoring out $a^2$ from the denominator demonstrates:
$$
\begin{gather}
(x^2 + a^2)^n = a^{2n} \left( \left(\frac{x}{a}\right)^2 + 1 \right)^n \tag{16}
\end{gather}
$$
Applying the linear change of variable $t = \frac{x}{a}$, with differential $dx = a \, dt$, the integral transforms into:
$$
\begin{gather}
J_n(x; a) = \int \frac{a \, dt}{a^{2n} (t^2 + 1)^n} = \frac{1}{a^{2n - 1}} \int \frac{dt}{(t^2 + 1)^n} = \frac{1}{a^{2n - 1}} I_n\left(\frac{x}{a}\right) \tag{17}
\end{gather}
$$
Substituting the recurrence relation of step 14 into step 17 yields:
$$
\begin{gather}
J_{n+1}(x; a) = \frac{1}{a^{2n + 1}} I_{n+1}(t) = \frac{1}{a^{2n + 1}} \left[ \frac{t}{2n(t^2 + 1)^n} + \frac{2n - 1}{2n} I_n(t) \right] \tag{18}
\end{gather}
$$
Expressing step 18 back in terms of the original variable $x$ and the integral $J_n(x; a)$ produces:
$$
\begin{gather}
J_{n+1}(x; a) = \frac{x}{2n a^2 (x^2 + a^2)^n} + \frac{2n - 1}{2n a^2} J_n(x; a) \tag{19}
\end{gather}
$$
with base primitive:
$$
\begin{gather}
J_1(x; a) = \frac{1}{a} \arctan\left(\frac{x}{a}\right) + C \tag{20}
\end{gather}
$$
This demonstrates that every rational integral with an irreducible quadratic denominator of arbitrary power $(x^2 + a^2)^n$ can be evaluated recursively in closed form as a sum of rational algebraic functions and an inverse tangent term.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
