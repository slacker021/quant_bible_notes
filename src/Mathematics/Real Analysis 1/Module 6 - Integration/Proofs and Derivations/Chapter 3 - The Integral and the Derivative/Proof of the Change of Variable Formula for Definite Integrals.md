---
dg-publish: true
---
Let $[\alpha, \beta] \subset \mathbb{R}$ be a non-degenerate compact interval with $\alpha < \beta$, and let $\phi: [\alpha, \beta] \to \mathbb{R}$ be a continuously differentiable mapping, that is, $\phi \in C^1[\alpha, \beta]$.

Because $[\alpha, \beta]$ is compact and $\phi$ is continuous, the Extreme Value Theorem (Weierstrass Theorem, Module 5) guarantees that $\phi$ attains its minimum and maximum on $[\alpha, \beta]$. By the Intermediate Value Theorem (Bolzano-Cauchy Theorem, Module 5), the image:
$$
\begin{gather}
K := \phi([\alpha, \beta]) \subset \mathbb{R} \tag{1}
\end{gather}
$$
is a compact closed interval $[m, M]$, where:
$$
\begin{gather}
m := \min_{t \in [\alpha, \beta]} \phi(t), \qquad M := \max_{t \in [\alpha, \beta]} \phi(t) \tag{2}
\end{gather}
$$

Let $J \subset \mathbb{R}$ be an arbitrary compact interval containing the image $K$, so that $K \subseteq J$. Let $f: J \to \mathbb{R}$ be a continuous function, that is, $f \in C(J)$.

Define the boundary endpoints:
$$
\begin{gather}
a := \phi(\alpha), \qquad b := \phi(\beta) \tag{3}
\end{gather}
$$
Notice that $a, b \in K \subseteq J$. The ordering between $a$ and $b$ is unrestricted; $a < b$, $a = b$, or $a > b$ are all permissible.

---
# Part 1
Fix the reference basepoint $a \in J$, and define the accumulation function $F: J \to \mathbb{R}$ by:
$$
\begin{gather}
F(u) := \int_a^u f(x)\,dx \quad \text{for all } u \in J \tag{4}
\end{gather}
$$

Because $f$ is continuous on the compact interval $J$, the Theorem on Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral (Module 6, Chapter 3, [[Proof of Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral]]) establishes that $F$ is differentiable at every point $u \in J$, and its derivative satisfies:
$$
\begin{gather}
F'(u) = f(u) \quad \text{for all } u \in J \tag{5}
\end{gather}
$$

Because $f \in C(J)$, the derivative function $F'$ is continuous on $J$, which implies $F \in C^1(J)$.

Evaluating $F$ at $u = a$ and $u = b$ via step 4:
$$
\begin{gather}
F(a) = \int_a^a f(x)\,dx = 0 \tag{6}
\end{gather}
$$
and:
$$
\begin{gather}
F(b) = \int_a^b f(x)\,dx \tag{7}
\end{gather}
$$
---
# Part 2

Define the composite function $G: [\alpha, \beta] \to \mathbb{R}$ by:
$$
\begin{gather}
G(t) := (F \circ \phi)(t) = F(\phi(t)) \quad \text{for all } t \in [\alpha, \beta] \tag{8}
\end{gather}
$$

Because $\phi$ is differentiable on $[\alpha, \beta]$ with $\phi(t) \in K \subseteq J$, and $F$ is differentiable on $J$, the Chain Rule of Differentiation (Module 5) ensures that the composite function $G$ is differentiable at every point $t \in [\alpha, \beta]$, with derivative:
$$
\begin{gather}
G'(t) = F'(\phi(t)) \cdot \phi'(t) \tag{9}
\end{gather}
$$

Substituting the derivative evaluation $F'(u) = f(u)$ from step 5 with $u = \phi(t)$ into step 9 yields:
$$
\begin{gather}
G'(t) = f(\phi(t))\phi'(t) \quad \text{for all } t \in [\alpha, \beta] \tag{10}
\end{gather}
$$

Now examine the regularity of $G'$:
1. The function $\phi$ is continuous on $[\alpha, \beta]$, and $f$ is continuous on $J$. The composition of continuous functions is continuous, so the mapping $t \mapsto f(\phi(t))$ belongs to $C[\alpha, \beta]$.
2. The derivative function $\phi'$ belongs to $C[\alpha, \beta]$ because $\phi \in C^1[\alpha, \beta]$.
3. The product of two continuous functions is continuous. Therefore, the function:
$$
\begin{gather}
t \mapsto G'(t) = f(\phi(t))\phi'(t) \tag{11}
\end{gather}
$$
is continuous on $[\alpha, \beta]$.

By the Integrability of Continuous Functions on Compact Intervals (Module 6, Chapter 1), step 11 implies:
$$
\begin{gather}
G' \in \mathcal{R}[\alpha, \beta] \tag{12}
\end{gather}
$$
---
# Part 3
Because $G$ is continuous on $[\alpha, \beta]$ and differentiable on $(\alpha, \beta)$ with derivative $G'$ Riemann integrable on $[\alpha, \beta]$, all hypotheses of the Newton-Leibniz Formula (Module 6, Chapter 3, [[Proof of the Newton-Leibniz Formula]]) are satisfied by $G$ on $[\alpha, \beta]$.

Applying the Newton-Leibniz Formula:
$$
\begin{gather}
\int_\alpha^\beta G'(t)\,dt = G(\beta) - G(\alpha) \tag{13}
\end{gather}
$$

Substituting the explicit derivative formula of step 10 into the left-hand side of step 13:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = G(\beta) - G(\alpha) \tag{14}
\end{gather}
$$

Now evaluate the right-hand side of step 14 using the definition of $G$ from step 8 and the boundary values from step 3:
$$
\begin{gather}
G(\beta) = F(\phi(\beta)) = F(b) \tag{15}
\end{gather}
$$
and:
$$
\begin{gather}
G(\alpha) = F(\phi(\alpha)) = F(a) \tag{16}
\end{gather}
$$

Subtracting step 16 from step 15 and using step 6:
$$
\begin{gather}
G(\beta) - G(\alpha) = F(b) - F(a) = F(b) - 0 = F(b) \tag{17}
\end{gather}
$$

Substituting the integral representation of $F(b)$ from step 7 into step 17:
$$
\begin{gather}
G(\beta) - G(\alpha) = \int_a^b f(x)\,dx \tag{18}
\end{gather}
$$

Equating step 14 and step 18:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = \int_a^b f(x)\,dx \tag{19}
\end{gather}
$$

Because $a = \phi(\alpha)$ and $b = \phi(\beta)$ by step 3, step 19 can be expressed in the unified form:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_{\phi(\alpha)}^{\phi(\beta)} f(x)\,dx = \int_\alpha^\beta f(\phi(t))\phi'(t)\,dt \tag{20}
\end{gather}
$$
which establishes the Change of Variable Formula for definite integrals.

---
# Part 4
A remarkable feature of the deduction in Parts 1 through 3 is that no hypothesis of monotonicity, injectivity, or sign constancy was imposed on the transformation mapping $\phi$ or its derivative $\phi'$.

To understand the analytical mechanism that permits non-monotone transformations, suppose $\phi$ reverses direction at an interior stationary node $c \in (\alpha, \beta)$, such that $\phi'(t) > 0$ on $(\alpha, c)$ and $\phi'(t) < 0$ on $(c, \beta)$. Let:
$$
\begin{gather}
\phi(\alpha) = a, \qquad \phi(c) = d, \qquad \phi(\beta) = b \tag{21}
\end{gather}
$$
where $d > \max\{a, b\}$.

By the Interval Additivity of the Definite Integral (Module 6, Chapter 2, [[Proof of Interval Additivity of the Definite Integral]]), splitting the parameter integral at $c$:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = \int_\alpha^c f(\phi(t))\phi'(t)\,dt + \int_c^\beta f(\phi(t))\phi'(t)\,dt \tag{22}
\end{gather}
$$

On $[\alpha, c]$, $\phi$ is strictly increasing, mapping $[\alpha, c]$ monotonically onto $[a, d]$. Applying the monotonic change of variables:
$$
\begin{gather}
\int_\alpha^c f(\phi(t))\phi'(t)\,dt = \int_a^d f(x)\,dx \tag{23}
\end{gather}
$$

On $[c, \beta]$, $\phi$ is strictly decreasing, mapping $[c, \beta]$ monotonically from $d$ down to $b$. Applying the change of variables with boundary limits $\phi(c) = d$ and $\phi(\beta) = b$:
$$
\begin{gather}
\int_c^\beta f(\phi(t))\phi'(t)\,dt = \int_d^b f(x)\,dx \tag{24}
\end{gather}
$$

Substituting step 23 and step 24 into step 22:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = \int_a^d f(x)\,dx + \int_d^b f(x)\,dx \tag{25}
\end{gather}
$$

By the Generalized Orientation Additivity Formula (Module 6, Chapter 2, [[Proof of the Generalized Orientation Additivity Formula]]):
$$
\begin{gather}
\int_a^d f(x)\,dx + \int_d^b f(x)\,dx = \int_a^b f(x)\,dx \tag{26}
\end{gather}
$$
because the redundant path from $b$ to $d$ and back from $d$ to $b$ satisfies:
$$
\begin{gather}
\int_b^d f(x)\,dx + \int_d^b f(x)\,dx = \int_b^d f(x)\,dx - \int_b^d f(x)\,dx = 0 \tag{27}
\end{gather}
$$

The algebraic sign of the differential factor $\phi'(t)\,dt$ automatically inverts along reverse traversals, ensuring that all overlapping coverages cancel out without requiring any geometric partitioning or absolute values.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
