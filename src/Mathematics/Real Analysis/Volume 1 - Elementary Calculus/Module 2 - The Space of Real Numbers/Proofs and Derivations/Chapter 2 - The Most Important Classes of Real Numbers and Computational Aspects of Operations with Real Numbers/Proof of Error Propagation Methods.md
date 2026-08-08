---
dg-publish: true
---
Let $x, y \in \mathbb{R}$ denote exact quantities and let $\tilde{x}, \tilde{y} \in \mathbb{R}$ denote their respective approximations. Define the signed errors $\alpha := x - \tilde{x}$ and $\beta := y - \tilde{y}$, such that: 
$$
x = \tilde{x} + \alpha \quad \wedge \quad y = \tilde{y} + \beta \tag{1}
$$
$$
|\alpha| = \Delta(\tilde{x}) \quad \wedge \quad |\beta| = \Delta(\tilde{y}) \tag{2}
$$

--------------------------------------------------------------------------------
# Proposition 1
Consider the sum or difference $\tilde{x} \pm \tilde{y}$ approximating $x \pm y$. By definition of the absolute error: 
$$
\Delta(\tilde{x} \pm \tilde{y}) = |(x \pm y) - (\tilde{x} \pm \tilde{y})| \tag{3}
$$
Substituting the representations from step 1 into step 3:
$$
(x \pm y) - (\tilde{x} \pm \tilde{y}) = (x - \tilde{x}) \pm (y - \tilde{y}) = \alpha \pm \beta \tag{4}
$$
Applying the Triangle Inequality to step 4 yields: 
$$
\Delta(\tilde{x} \pm \tilde{y}) = |\alpha \pm \beta| \le |\alpha| + |\beta| = \Delta(\tilde{x}) + \Delta(\tilde{y}) \tag{5}
$$

--------------------------------------------------------------------------------
# Proposition 2
Consider the product $\tilde{x} \cdot \tilde{y}$ approximating $x \cdot y$. By definition of the absolute error: 
$$
\Delta(\tilde{x} \cdot \tilde{y}) = |x y - \tilde{x} \tilde{y}| \tag{6}
$$
Substituting $x = \tilde{x} + \alpha$ and $y = \tilde{y} + \beta$ into step 6 gives: 
$$
x y - \tilde{x} \tilde{y} = (\tilde{x} + \alpha)(\tilde{y} + \beta) - \tilde{x} \tilde{y} = \tilde{x}\beta + \tilde{y}\alpha + \alpha\beta \tag{7}
$$
Applying the [[Proof of the Triangle Inequality|Triangle Inequality]] and the multiplicative property of the absolute value to step 7: 
$$
\begin{align}
\Delta(\tilde{x} \cdot \tilde{y}) &= |\tilde{x}\beta + \tilde{y}\alpha + \alpha\beta| \\[2mm]
&\le |\tilde{x}||\beta| + |\tilde{y}||\alpha| + |\alpha||\beta| \\[2mm]
&= |\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x}) + \Delta(\tilde{x})\Delta(\tilde{y}) \tag{8}
\end{align}
$$

--------------------------------------------------------------------------------
# Proposition 3
Assume that $\tilde{y} \ne 0$ and the relative error satisfies $\delta(\tilde{y}) = \frac{|\beta|}{|\tilde{y}|} < 1$. 

By the Reverse Triangle Inequality: 
$$
\left| 1 + \frac{\beta}{\tilde{y}} \right| \ge 1 - \left| \frac{\beta}{\tilde{y}} \right| = 1 - \delta(\tilde{y}) > 0 \tag{9}
$$
Step 9 guarantees that $y = \tilde{y}\left(1 + \frac{\beta}{\tilde{y}}\right) \ne 0$, ensuring the exact quotient $\frac{x}{y}$ is well-defined, and: 
$$
\left| 1 + \frac{\beta}{\tilde{y}} \right|^{-1} \le \frac{1}{1 - \delta(\tilde{y})} \tag{10}
$$
Evaluating the absolute error of the quotient over a common denominator:
$$
\Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) = \left| \frac{x}{y} - \frac{\tilde{x}}{\tilde{y}} \right| = \left| \frac{x\tilde{y} - y\tilde{x}}{y\tilde{y}} \right| \tag{11}
$$
Substituting $x = \tilde{x} + \alpha$ and $y = \tilde{y} + \beta$:
$$
x\tilde{y} - y\tilde{x} = (\tilde{x} + \alpha)\tilde{y} - (\tilde{y} + \beta)\tilde{x} = \alpha\tilde{y} - \beta\tilde{x} \tag{12}
$$
Substituting step 12 and the factorization $y = \tilde{y}\left(1 + \frac{\beta}{\tilde{y}}\right)$ into step 11 yields: 
$$
\Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) = \frac{|\alpha\tilde{y} - \beta\tilde{x}|}{\tilde{y}^2 \left| 1 + \frac{\beta}{\tilde{y}} \right|} \tag{13}
$$
Applying the Triangle Inequality to the numerator and invoking step 10:
$$
\Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \le \frac{|\tilde{y}||\alpha| + |\tilde{x}||\beta|}{\tilde{y}^2 (1 - \delta(\tilde{y}))} = \frac{|\tilde{y}|\Delta(\tilde{x}) + |\tilde{x}|\Delta(\tilde{y})}{\tilde{y}^2 (1 - \delta(\tilde{y}))} \tag{14}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
