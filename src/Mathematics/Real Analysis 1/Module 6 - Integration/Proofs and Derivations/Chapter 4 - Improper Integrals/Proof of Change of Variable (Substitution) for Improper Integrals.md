---
dg-publish: true
---
Let $-\infty < a < b \le \infty$ and $-\infty < \alpha < \beta \le \infty$. Let $\phi: [\alpha, \beta) \to [a, b)$ be a continuously differentiable function:
$$
\begin{gather}
\phi \in C^1[\alpha, \beta) \tag{1}
\end{gather}
$$
Assume that $\phi$ is a strictly increasing bijection mapping the interval $[\alpha, \beta)$ onto $[a, b)$, satisfying the boundary asymptotic conditions:
$$
\begin{gather}
\phi(\alpha) = a, \qquad \lim_{t \to \beta^-} \phi(t) = b \tag{2}
\end{gather}
$$
Let $f: [a, b) \to \mathbb{R}$ be a continuous function:
$$
\begin{gather}
f \in C[a, b) \tag{3}
\end{gather}
$$
---
# Step 1
Let $Y \in (\alpha, \beta)$ be an arbitrary intermediate parameter. Because $\phi$ is continuous and strictly increasing on $[\alpha, \beta)$, the restriction of $\phi$ to the compact interval $[\alpha, Y]$ defines a strictly increasing homeomorphism mapping $[\alpha, Y]$ onto the compact subinterval $[a, \phi(Y)] \subset [a, b)$.

Designate the corresponding mapped upper coordinate:
$$
\begin{gather}
X := \phi(Y) \in (a, b) \tag{4}
\end{gather}
$$
Because $f$ is continuous on $[a, b)$, its restriction to $[a, X]$ is continuous, which guarantees Riemann integrability: $f \in \mathcal{R}[a, X]$. 

Furthermore, because $\phi \in C^1[\alpha, Y]$, the derivative $\phi'$ is continuous on $[\alpha, Y]$. The composition $t \mapsto f(\phi(t))$ is continuous on $[\alpha, Y]$ as a composition of continuous mappings. By the product property of continuous functions, the transformed integrand $t \mapsto f(\phi(t))\phi'(t)$ is continuous on $[\alpha, Y]$, which guarantees:
$$
\begin{gather}
f\big(\phi(\cdot)\big) \phi'(\cdot) \in \mathcal{R}[\alpha, Y] \tag{5}
\end{gather}
$$
Applying the classical Change of Variable (Substitution) Formula for proper Riemann integrals established in [[Chapter 3 - The Integral and the Derivative|Chapter 3]]:
$$
\begin{gather}
\int_a^{\phi(Y)} f(x)\,dx = \int_\alpha^Y f\big(\phi(t)\big) \phi'(t)\,dt \tag{6}
\end{gather}
$$
---
# Step 2
Define the variable upper limit accumulation functions $F: [a, b) \to \mathbb{R}$ and $G: [\alpha, \beta) \to \mathbb{R}$ by:
$$
\begin{gather}
F(X) := \int_a^X f(x)\,dx \quad \text{for } X \in [a, b) \tag{7}
\end{gather}
$$
$$
\begin{gather}
G(Y) := \int_\alpha^Y f\big(\phi(t)\big) \phi'(t)\,dt \quad \text{for } Y \in [\alpha, \beta) \tag{8}
\end{gather}
$$
Substituting step 7 and step 8 into the identity of step 6 demonstrates that for all $Y \in [\alpha, \beta)$:
$$
\begin{gather}
G(Y) = F\big(\phi(Y)\big) \tag{9}
\end{gather}
$$
Because $\phi: [\alpha, \beta) \to [a, b)$ is a strictly increasing, continuous bijection, by the Inverse Function Theorem for continuous monotonic functions, the inverse mapping $\phi^{-1}: [a, b) \to [\alpha, \beta)$ exists and is also a strictly increasing, continuous bijection. The inverse mapping satisfies the corresponding boundary limits:
$$
\begin{gather}
\phi^{-1}(a) = \alpha, \qquad \lim_{X \to b^-} \phi^{-1}(X) = \beta \tag{10}
\end{gather}
$$
Evaluating step 9 at $Y = \phi^{-1}(X)$ confirms that for every $X \in [a, b)$:
$$
\begin{gather}
F(X) = G\big(\phi^{-1}(X)\big) \tag{11}
\end{gather}
$$
---
# Step 3
Recall the theorem on limits of composite functions: let $h: D \to E$ and $g: E \to \mathbb{R}$. If $\lim_{t \to t_0} h(t) = s_0$, $h(t) \ne s_0$ on a deleted neighborhood of $t_0$, and $\lim_{s \to s_0} g(s) = L \in \mathbb{R}$, then $\lim_{t \to t_0} g(h(t)) = L$.

Assume that the improper integral $\int_a^b f(x)\,dx$ converges to a finite real scalar $L_1 \in \mathbb{R}$:
$$
\begin{gather}
\lim_{X \to b^-} F(X) = \int_a^b f(x)\,dx = L_1 \in \mathbb{R} \tag{12}
\end{gather}
$$
Because $\phi$ is strictly increasing on $[\alpha, \beta)$, for all $Y < \beta$ the strict inequality $\phi(Y) < b$ holds, ensuring that $\phi(Y) \ne b$ on $[\alpha, \beta)$. By hypothesis (step 2), $\lim_{Y \to \beta^-} \phi(Y) = b$. Applying the composite limit theorem to step 9:
$$
\begin{gather}
\lim_{Y \to \beta^-} G(Y) = \lim_{Y \to \beta^-} F\big(\phi(Y)\big) = \lim_{X \to b^-} F(X) = L_1 \tag{13}
\end{gather}
$$
Consequently, the improper integral $\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt$ converges to the identical finite value $L_1$.

Conversely, assume that the improper integral $\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt$ converges to a finite real scalar $L_2 \in \mathbb{R}$:
$$
\begin{gather}
\lim_{Y \to \beta^-} G(Y) = \int_\alpha^\beta f\big(\phi(t)\big) \phi'(t)\,dt = L_2 \in \mathbb{R} \tag{14}
\end{gather}
$$
Because $\phi^{-1}$ is strictly increasing on $[a, b)$, for all $X < b$ the strict inequality $\phi^{-1}(X) < \beta$ holds, ensuring $\phi^{-1}(X) \ne \beta$ on $[a, b)$. By step 10, $\lim_{X \to b^-} \phi^{-1}(X) = \beta$. Applying the composite limit theorem to step 11:
$$
\begin{gather}
\lim_{X \to b^-} F(X) = \lim_{X \to b^-} G\big(\phi^{-1}(X)\big) = \lim_{Y \to \beta^-} G(Y) = L_2 \tag{15}
\end{gather}
$$
Consequently, the improper integral $\int_a^b f(x)\,dx$ converges to the identical finite value $L_2$.

---
# Step 4
Because the mapping $\phi$ is an order-preserving bijection, the behavior of $F(X)$ as $X \to b^-$ mirrors the behavior of $G(Y)$ as $Y \to \beta^-$ in every regard:
- If either accumulation function diverges to $+\infty$ (or $-\infty$), the other accumulation function diverges to $+\infty$ (or $-\infty$).
- If either accumulation function oscillates without limit, the other accumulation function oscillates without limit.

Therefore, the improper integrals $\int_a^b f(x)\,dx$ and $\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt$ share identical convergence status, and whenever either converges, they evaluate to the same value:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_\alpha^\beta f\big(\phi(t)\big) \phi'(t)\,dt \tag{16}
\end{gather}
$$
This relationship holds universally whether the boundary is an infinite endpoint ($b = \infty$) or a finite singular endpoint ($b < \infty$).
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
