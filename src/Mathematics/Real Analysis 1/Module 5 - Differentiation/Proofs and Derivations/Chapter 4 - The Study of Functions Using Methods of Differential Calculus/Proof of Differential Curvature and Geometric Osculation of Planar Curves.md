---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a twice differentiable function on $(a, b)$.

Consider the planar curve parametrized by the graph of $f$, namely $\mathbf{r}(x) = (x, f(x))$. 

Let $\varphi(x)$ denote the inclination angle formed by the tangent line to the curve with the positive horizontal axis. The slope of the tangent line satisfies:
$$
\begin{gather}
\tan\big(\varphi(x)\big) = f'(x) \tag{1}
\end{gather}
$$
Because the tangent slope is finite, $\varphi(x) \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$, so $\varphi(x) = \arctan\big(f'(x)\big)$.

Differentiating step 1 with respect to the horizontal coordinate $x$ using the chain rule yields:
$$
\begin{gather}
\sec^2\big(\varphi(x)\big) \frac{\mathrm{d}\varphi}{\mathrm{d}x} = f''(x) \tag{2}
\end{gather}
$$
Using the trigonometric identity $\sec^2(\varphi) = 1 + \tan^2(\varphi) = 1 + [f'(x)]^2$, step 2 becomes:
$$
\begin{gather}
\frac{\mathrm{d}\varphi}{\mathrm{d}x} = \frac{f''(x)}{1 + [f'(x)]^2} \tag{3}
\end{gather}
$$

Let $s$ denote the arc length parameter along the curve. The differential increment of arc length satisfies:
$$
\begin{gather}
\mathrm{d}s = \sqrt{(\mathrm{d}x)^2 + (\mathrm{d}y)^2} = \sqrt{1 + \left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2} \, \mathrm{d}x = \sqrt{1 + [f'(x)]^2} \, \mathrm{d}x \tag{4}
\end{gather}
$$
Step 4 gives the rate of change of arc length with respect to $x$:
$$
\begin{gather}
\frac{\mathrm{d}s}{\mathrm{d}x} = \sqrt{1 + [f'(x)]^2} \tag{5}
\end{gather}
$$

The signed geometric curvature $k(x)$ is defined as the instantaneous rate of rotation of the tangent angle with respect to arc length:
$$
\begin{gather}
k(x) := \frac{\mathrm{d}\varphi}{\mathrm{d}s} \tag{6}
\end{gather}
$$
Applying the chain rule for derivatives, step 6 can be written as:
$$
\begin{gather}
k(x) = \frac{\frac{\mathrm{d}\varphi}{\mathrm{d}x}}{\frac{\mathrm{d}s}{\mathrm{d}x}} \tag{7}
\end{gather}
$$
Substituting step 3 and step 5 into step 7 yields:
$$
\begin{gather}
k(x) = \frac{\frac{f''(x)}{1 + [f'(x)]^2}}{\sqrt{1 + [f'(x)]^2}} = \frac{f''(x)}{\left(1 + [f'(x)]^2\right)^{3/2}} \tag{8}
\end{gather}
$$

The radius of curvature $R(x)$ of the osculating circle is defined as the reciprocal of the absolute curvature:
$$
\begin{gather}
R(x) := \frac{1}{|k(x)|} = \frac{\left(1 + [f'(x)]^2\right)^{3/2}}{|f''(x)|} \tag{9}
\end{gather}
$$
provided that $f''(x) \neq 0$.

Because the denominator $\left(1 + [f'(x)]^2\right)^{3/2}$ is strictly positive for all real values of $f'(x)$:
$$
\begin{gather}
\left(1 + [f'(x)]^2\right)^{3/2} \ge 1 > 0 \tag{10}
\end{gather}
$$
the algebraic sign of the signed curvature $k(x)$ is identical to the sign of the second derivative $f''(x)$:
$$
\begin{gather}
\operatorname{sgn}\big(k(x)\big) = \operatorname{sgn}\big(f''(x)\big), \quad \forall x \in (a, b) \tag{11}
\end{gather}
$$
In particular, $k(x) = 0$ if and only if $f''(x) = 0$, which matches the necessary condition for an inflection point established in [[Proof of Necessary Condition for an Inflection Point|The Necessary Condition for an Inflection Point]].
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
