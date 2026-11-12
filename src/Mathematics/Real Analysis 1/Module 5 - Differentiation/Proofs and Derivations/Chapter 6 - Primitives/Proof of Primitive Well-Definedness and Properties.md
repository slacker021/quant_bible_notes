---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be a non-degenerate interval (open, closed, or semi-infinite), and let $f: I \to \mathbb{R}$ be a real-valued function.

A function $F: I \to \mathbb{R}$ is termed a primitive of $f$ on $I$ if $F$ is differentiable at every point $x \in I$ and its derivative satisfies:
$$
\begin{gather}
F'(x) = f(x) \quad \forall x \in I \tag{1}
\end{gather}
$$
where at any boundary point belonging to $I$, the derivative is understood as the appropriate one-sided derivative.

The indefinite integral of $f$ on $I$, denoted by $\int f(x) \, dx$, is defined as the complete inverse image of the singleton $\{f\}$ under the differential operator $D = \frac{d}{dx}$:
$$
\begin{gather}
\int f(x) \, dx := D^{-1}(\{f\}) = \{ F: I \to \mathbb{R} \mid F \text{ is differentiable on } I \text{ and } F' = f \} \tag{2}
\end{gather}
$$

---
# Proposition 1
Let $F \in \int f(x) \, dx$ be any primitive of $f$ on $I$. Then $F$ is continuous on $I$.

To verify this assertion, fix an arbitrary point $x_0 \in I$. By hypothesis, $F$ is differentiable at $x_0$, meaning the limit of the difference quotient exists in $\mathbb{R}$:
$$
\begin{gather}
\lim_{I \ni x \to x_0} \frac{F(x) - F(x_0)}{x - x_0} = F'(x_0) = f(x_0) \tag{3}
\end{gather}
$$
Consider the displacement $F(x) - F(x_0)$ for $x \in I \setminus \{x_0\}$. Algebraic rewriting yields:
$$
\begin{gather}
F(x) - F(x_0) = \frac{F(x) - F(x_0)}{x - x_0} \cdot (x - x_0) \tag{4}
\end{gather}
$$
Evaluating the limit of both sides of step 4 as $x \to x_0$ through $I$ and invoking the product rule for limits of functions yields:
$$
\begin{gather}
\lim_{I \ni x \to x_0} \big(F(x) - F(x_0)\big) = \left( \lim_{I \ni x \to x_0} \frac{F(x) - F(x_0)}{x - x_0} \right) \cdot \left( \lim_{I \ni x \to x_0} (x - x_0) \right) = f(x_0) \cdot 0 = 0 \tag{5}
\end{gather}
$$
Step 5 demonstrates that:
$$
\begin{gather}
\lim_{I \ni x \to x_0} F(x) = F(x_0) \tag{6}
\end{gather}
$$
Because the limit of $F(x)$ as $x \to x_0$ along $I$ coincides identically with the functional value $F(x_0)$, $F$ is continuous at $x_0$. Since $x_0 \in I$ was chosen arbitrarily, $F \in C(I)$.

---
# Proposition 2
The differential operator $D = \frac{d}{dx}$ and the indefinite integral operator $\int$ satisfy canonical operational identities on their respective domains of definition:

1. Let $F: I \to \mathbb{R}$ be an arbitrary differentiable function on $I$. Applying the integration operator to its differential $dF = F'(x)\,dx$ recovers $F$ modulo an additive constant:
$$
\begin{gather}
\int dF(x) = \int F'(x) \, dx = F(x) + C \tag{7}
\end{gather}
$$
for some $C \in \mathbb{R}$.

2. Let $f: I \to \mathbb{R}$ be a function admitting a primitive on $I$. Differentiating the indefinite integral with respect to the independent variable reproduces the integrand identically:
$$
\begin{gather}
\frac{d}{dx} \left( \int f(x) \, dx \right) = f(x) \tag{8}
\end{gather}
$$
and in terms of differential forms:
$$
\begin{gather}
d \left( \int f(x) \, dx \right) = f(x) \, dx \tag{9}
\end{gather}
$$

To substantiate claim 1, notice that $F$ is, by definition, a primitive of its own derivative $F'$. Since any other primitive differs from $F$ by an additive constant on the interval $I$, the indefinite integral consists precisely of the family $F(x) + C$.

To substantiate claim 2, select any member $\Phi \in \int f(x) \, dx$. By step 2, $\Phi$ satisfies $\Phi'(x) = f(x)$ at every $x \in I$. Therefore, applying the differential operator directly evaluates to $f(x)$ for all representatives within the family, confirming the identity of step 8 and step 9.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
