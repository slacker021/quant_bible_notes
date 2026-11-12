---
dg-publish: true
---
Let $x_0 \in \mathbb{R}$ and $\delta > 0$, let $U(x_0) := (x_0 - \delta, x_0 + \delta)$, and let $f: U(x_0) \to \mathbb{R}$ be continuous on $U(x_0)$ and differentiable on the punctured neighborhood $\mathring{U}(x_0) := U(x_0) \setminus \{x_0\}$. Define the left and right directional punctured components by $\mathring{U}^-(x_0) := (x_0 - \delta, x_0)$ and $\mathring{U}^+(x_0) := (x_0, x_0 + \delta)$.

---
# Proposition 1
Assume that $f'(x) > 0$ for all $x \in \mathring{U}^-(x_0)$ and $f'(x) < 0$ for all $x \in \mathring{U}^+(x_0)$.

Let $x \in \mathring{U}^-(x_0)$ be an arbitrary point, so that $x_0 - \delta < x < x_0$. The restriction of $f$ to the closed interval $[x, x_0]$ is continuous on $[x, x_0]$ and differentiable on $(x, x_0)$. Because $(x, x_0) \subseteq \mathring{U}^-(x_0)$, [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] guarantees the existence of a point $\xi_1 \in (x, x_0)$ such that:
$$
\begin{gather}
f(x_0) - f(x) = f'(\xi_1)(x_0 - x) \tag{1}
\end{gather}
$$
Because $x < x_0$, the displacement $x_0 - x$ is strictly positive. Furthermore, $\xi_1 \in \mathring{U}^-(x_0)$ entails $f'(\xi_1) > 0$. The product of these positive quantities in step 1 yields:
$$
\begin{gather}
f(x_0) - f(x) > 0 \iff f(x) < f(x_0), \quad \forall x \in \mathring{U}^-(x_0) \tag{2}
\end{gather}
$$

Next, let $x \in \mathring{U}^+(x_0)$ be an arbitrary point, so that $x_0 < x < x_0 + \delta$. The restriction of $f$ to the closed interval $[x_0, x]$ is continuous on $[x_0, x]$ and differentiable on $(x_0, x)$. Because $(x_0, x) \subseteq \mathring{U}^+(x_0)$, [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] yields an intermediate point $\xi_2 \in (x_0, x)$ such that:
$$
\begin{gather}
f(x) - f(x_0) = f'(\xi_2)(x - x_0) \tag{3}
\end{gather}
$$
Because $x > x_0$, the displacement $x - x_0$ is strictly positive. However, $\xi_2 \in \mathring{U}^+(x_0)$ implies that $f'(\xi_2) < 0$. The product of a negative number and a positive number in step 3 yields:
$$
\begin{gather}
f(x) - f(x_0) < 0 \iff f(x) < f(x_0), \quad \forall x \in \mathring{U}^+(x_0) \tag{4}
\end{gather}
$$

Combining step 2 and step 4 demonstrates that for all $x \in \mathring{U}(x_0) = \mathring{U}^-(x_0) \cup \mathring{U}^+(x_0)$, the strict inequality $f(x) < f(x_0)$ holds. Thus, $x_0$ is a strict local maximum of $f$.

---
# Proposition 2
Assume that $f'(x) < 0$ for all $x \in \mathring{U}^-(x_0)$ and $f'(x) > 0$ for all $x \in \mathring{U}^+(x_0)$.

Define the auxiliary function $g: U(x_0) \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := -f(x), \quad \forall x \in U(x_0) \tag{5}
\end{gather}
$$
The function $g$ is continuous on $U(x_0)$ and differentiable on $\mathring{U}(x_0)$ with derivative $g'(x) = -f'(x)$.

For all $x \in \mathring{U}^-(x_0)$, the hypothesis $f'(x) < 0$ implies $g'(x) = -f'(x) > 0$. For all $x \in \mathring{U}^+(x_0)$, the hypothesis $f'(x) > 0$ implies $g'(x) = -f'(x) < 0$. Applying Proposition 1 to $g$ establishes that $x_0$ is a strict local maximum of $g$:
$$
\begin{gather}
g(x) < g(x_0), \quad \forall x \in \mathring{U}(x_0) \tag{6}
\end{gather}
$$
Substituting step 5 into step 6 yields:
$$
\begin{gather}
-f(x) < -f(x_0) \iff f(x) > f(x_0), \quad \forall x \in \mathring{U}(x_0) \tag{7}
\end{gather}
$$
Step 7 proves that $x_0$ is a strict local minimum of $f$.

---
# Proposition 3
Assume that $f'(x)$ maintains a constant sign across the entire punctured neighborhood $\mathring{U}(x_0)$.

First, consider the case where $f'(x) > 0$ for all $x \in \mathring{U}(x_0)$. Applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on $[x, x_0]$ for $x \in \mathring{U}^-(x_0)$ yields $f(x_0) - f(x) = f'(\xi_1)(x_0 - x) > 0$, whence:
$$
\begin{gather}
f(x) < f(x_0), \quad \forall x \in \mathring{U}^-(x_0) \tag{8}
\end{gather}
$$
Similarly, applying [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]] on $[x_0, x]$ for $x \in \mathring{U}^+(x_0)$ yields $f(x) - f(x_0) = f'(\xi_2)(x - x_0) > 0$, whence:
$$
\begin{gather}
f(x) > f(x_0), \quad \forall x \in \mathring{U}^+(x_0) \tag{9}
\end{gather}
$$
Step 8 and step 9 together show that $f$ takes values strictly smaller than $f(x_0)$ to the left of $x_0$ and values strictly larger than $f(x_0)$ to the right of $x_0$. Consequently, $f(x_0)$ cannot be an extremum.

Second, consider the case where $f'(x) < 0$ for all $x \in \mathring{U}(x_0)$. Applying the previous argument to $g(x) = -f(x)$ yields $g(x) < g(x_0)$ on $\mathring{U}^-(x_0)$ and $g(x) > g(x_0)$ on $\mathring{U}^+(x_0)$, which translates to:
$$
\begin{gather}
f(x) > f(x_0) \text{ on } \mathring{U}^-(x_0) \quad \text{and} \quad f(x) < f(x_0) \text{ on } \mathring{U}^+(x_0) \tag{10}
\end{gather}
$$
In this case as well, $x_0$ is not a local extremum.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
