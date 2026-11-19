---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $f, g \in \mathcal{R}[a, b]$, and let $\alpha, \beta \in \mathbb{R}$ be arbitrary real scalars.

Let the definite integrals of $f$ and $g$ over $[a, b]$ be denoted by:
$$
\begin{gather}
I(f) := \int_a^b f(x)\,dx, \qquad I(g) := \int_a^b g(x)\,dx \tag{1}
\end{gather}
$$

Define the linear combination function $h: [a, b] \to \mathbb{R}$ pointwise by:
$$
\begin{gather}
h(x) := \alpha f(x) + \beta g(x) \tag{2}
\end{gather}
$$

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ satisfying $a = x_0 < x_1 < \dots < x_n = b$, and let $\xi = (\xi_1, \dots, \xi_n)$ be an arbitrary vector of intermediate sample points with $\xi_i \in [x_{i-1}, x_i]$ for each $i \in \{1, \dots, n\}$. Let $\Delta x_i := x_i - x_{i-1}$ denote the length of the $i$-th subinterval, and let $\lambda(P) := \max_{1 \le i \le n} \Delta x_i$ denote the mesh (fineness) of $P$.

Form the Riemann sum of $h$ associated with the tagged partition $(P, \xi)$:
$$
\begin{gather}
\sigma(h; P, \xi) = \sum_{i=1}^n h(\xi_i) \Delta x_i = \sum_{i=1}^n \big( \alpha f(\xi_i) + \beta g(\xi_i) \big) \Delta x_i \tag{3}
\end{gather}
$$

Distributing $\Delta x_i$ across the sum and applying the linearity of finite summation yields the algebraic identity:
$$
\begin{gather}
\sigma(h; P, \xi) = \alpha \sum_{i=1}^n f(\xi_i) \Delta x_i + \beta \sum_{i=1}^n g(\xi_i) \Delta x_i = \alpha \sigma(f; P, \xi) + \beta \sigma(g; P, \xi) \tag{4}
\end{gather}
$$

Define the candidate real value:
$$
\begin{gather}
I := \alpha I(f) + \beta I(g) \tag{5}
\end{gather}
$$

Subtracting $I$ from the Riemann sum $\sigma(h; P, \xi)$ via step 4 and step 5 gives:
$$
\begin{gather}
\sigma(h; P, \xi) - I = \alpha \big( \sigma(f; P, \xi) - I(f) \big) + \beta \big( \sigma(g; P, \xi) - I(g) \big) \tag{6}
\end{gather}
$$

Applying the triangle inequality for real numbers to step 6:
$$
\begin{gather}
|\sigma(h; P, \xi) - I| \le |\alpha| |\sigma(f; P, \xi) - I(f)| + |\beta| |\sigma(g; P, \xi) - I(g)| \tag{7}
\end{gather}
$$

Let $\varepsilon > 0$ be an arbitrary positive real number.

Define the auxiliary error tolerances:
$$
\begin{gather}
\varepsilon_f := \frac{\varepsilon}{2(|\alpha| + 1)} > 0, \qquad \varepsilon_g := \frac{\varepsilon}{2(|\beta| + 1)} > 0 \tag{8}
\end{gather}
$$

Because $f \in \mathcal{R}[a, b]$ with integral $I(f)$, by the definition of the Riemann integral as a limit of Riemann sums, there exists a gauge $\delta_1 > 0$ such that for every tagged partition $(P, \xi)$ of $[a, b]$ with mesh $\lambda(P) < \delta_1$:
$$
\begin{gather}
|\sigma(f; P, \xi) - I(f)| < \varepsilon_f = \frac{\varepsilon}{2(|\alpha| + 1)} \tag{9}
\end{gather}
$$

Similarly, because $g \in \mathcal{R}[a, b]$ with integral $I(g)$, there exists a gauge $\delta_2 > 0$ such that for every tagged partition $(P, \xi)$ of $[a, b]$ with mesh $\lambda(P) < \delta_2$:
$$
\begin{gather}
|\sigma(g; P, \xi) - I(g)| < \varepsilon_g = \frac{\varepsilon}{2(|\beta| + 1)} \tag{10}
\end{gather}
$$

Define the uniform gauge:
$$
\begin{gather}
\delta := \min\{\delta_1, \delta_2\} > 0 \tag{11}
\end{gather}
$$

Let $(P, \xi)$ be any tagged partition of $[a, b]$ whose mesh satisfies $\lambda(P) < \delta$. Because $\lambda(P) < \delta \le \delta_1$ and $\lambda(P) < \delta \le \delta_2$, the bounds in step 9 and step 10 hold simultaneously.

Substituting step 9 and step 10 into step 7:
$$
\begin{gather}
|\sigma(h; P, \xi) - I| < |\alpha| \left( \frac{\varepsilon}{2(|\alpha| + 1)} \right) + |\beta| \left( \frac{\varepsilon}{2(|\beta| + 1)} \right) \tag{12}
\end{gather}
$$

Because $|\alpha| < |\alpha| + 1$ and $|\beta| < |\beta| + 1$, the fractions satisfy $\frac{|\alpha|}{|\alpha| + 1} < 1$ and $\frac{|\beta|}{|\beta| + 1} < 1$. Therefore:
$$
\begin{gather}
|\sigma(h; P, \xi) - I| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{13}
\end{gather}
$$

Because for every $\varepsilon > 0$ there exists $\delta > 0$ such that for every tagged partition $(P, \xi)$ with $\lambda(P) < \delta$, the inequality $|\sigma(\alpha f + \beta g; P, \xi) - I| < \varepsilon$ holds, the Riemann sum converges to $I$ as $\lambda(P) \to 0$:
$$
\begin{gather}
\lim_{\lambda(P) \to 0} \sigma(\alpha f + \beta g; P, \xi) = \alpha \int_a^b f(x)\,dx + \beta \int_a^b g(x)\,dx \tag{14}
\end{gather}
$$

By definition of Riemann integrability, step 14 establishes that $(\alpha f + \beta g) \in \mathcal{R}[a, b]$ and:
$$
\begin{gather}
\int_a^b \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^b f(x)\,dx + \beta \int_a^b g(x)\,dx \tag{15}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
