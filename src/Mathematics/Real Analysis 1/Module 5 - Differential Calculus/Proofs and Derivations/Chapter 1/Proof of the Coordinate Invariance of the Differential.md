---
dg-publish: true
---
Let the initial coordinates be $(x, y)$ connected by $y = f(x)$, where $f$ is differentiable at $x_0$. Let an affine coordinate change be given by:
$$
\begin{gather}
\tilde{x} = \alpha_1 x + \beta_1, \quad \tilde{y} = \alpha_2 y + \beta_2 \quad (\alpha_1 \neq 0, \alpha_2 \neq 0) \tag{1}
\end{gather}
$$

Let $\tilde{x}_0 = \alpha_1 x_0 + \beta_1$ and $\tilde{y}_0 = \alpha_2 f(x_0) + \beta_2$. 

Consider an argument displacement $h$ in the original coordinate system. By the equation of step 1, the corresponding displacement in the transformed coordinate system is:
$$
\begin{gather}
\tilde{h} = \tilde{x} - \tilde{x}_0 = (\alpha_1(x_0 + h) + \beta_1) - (\alpha_1 x_0 + \beta_1) = \alpha_1 h \tag{2}
\end{gather}
$$

Similarly, the coordinate differentials are:
$$
\begin{gather}
d\tilde{x} = \alpha_1 \, dx \tag{3}
\end{gather}
$$

The increment of the transformed coordinate $\tilde{y}$ is:
$$
\begin{gather}
\Delta \tilde{y}(\tilde{x}_0; \tilde{h}) = \tilde{y}(\tilde{x}_0 + \tilde{h}) - \tilde{y}(\tilde{x}_0) = (\alpha_2 f(x_0 + h) + \beta_2) - (\alpha_2 f(x_0) + \beta_2) = \alpha_2 \Delta f(x_0; h) \tag{4}
\end{gather}
$$

Because $f$ is differentiable at $x_0$, $\Delta f(x_0; h) = f'(x_0) h + o(h)$ as $h \to 0$. Substituting this expansion into the equation of step 4 yields:
$$
\begin{gather}
\Delta \tilde{y}(\tilde{x}_0; \tilde{h}) = \alpha_2 \big( f'(x_0) h + o(h) \big) = \alpha_2 f'(x_0) h + o(h) \tag{5}
\end{gather}
$$

Expressing $h$ in terms of $\tilde{h}$ via the equation of step 2, $h = \frac{\tilde{h}}{\alpha_1}$. Since $\alpha_1 \neq 0$, $o(h) = o(\tilde{h})$ as $\tilde{h} \to 0$. Thus:
$$
\begin{gather}
\Delta \tilde{y}(\tilde{x}_0; \tilde{h}) = \left( \frac{\alpha_2}{\alpha_1} f'(x_0) \right) \tilde{h} + o(\tilde{h}) \quad \text{as } \tilde{h} \to 0 \tag{6}
\end{gather}
$$

By the definition of differentiability at a point, $\tilde{y}$ is differentiable with respect to $\tilde{x}$ at $\tilde{x}_0$, with transformed derivative:
$$
\begin{gather}
\frac{d\tilde{y}}{d\tilde{x}}(\tilde{x}_0) = \frac{\alpha_2}{\alpha_1} f'(x_0) \tag{7}
\end{gather}
$$

Evaluating the differential of $\tilde{y}$ acting on the differential vector $d\tilde{x}$:
$$
\begin{gather}
d\tilde{y}(\tilde{x}_0; d\tilde{x}) = \frac{d\tilde{y}}{d\tilde{x}}(\tilde{x}_0) d\tilde{x} = \left( \frac{\alpha_2}{\alpha_1} f'(x_0) \right) (\alpha_1 \, dx) = \alpha_2 f'(x_0) \, dx = \alpha_2 \, dy(x_0; dx) \tag{8}
\end{gather}
$$

The equation of step 8 demonstrates that the differential transforms covariantly with the ordinate scaling $\alpha_2$, independently of the abscissa scaling $\alpha_1$, proving that the differential is an invariant linear geometric object on the tangent space.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
