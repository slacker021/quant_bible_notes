---
dg-publish: true
---
Let $k \in \mathbb{Z}$ and let $I_k = ((2k-1)\pi, (2k+1)\pi) \subset \mathbb{R}$ be an open interval of length $2\pi$. On the interval $I_k$, consider the map $\phi: I_k \to \mathbb{R}$ defined by:
$$
\begin{gather}
t = \phi(x) := \tan\left(\frac{x}{2}\right) \tag{1}
\end{gather}
$$
Because the half-angle argument satisfies $\frac{x}{2} \in \left(k\pi - \frac{\pi}{2}, k\pi + \frac{\pi}{2}\right)$, the tangent function is strictly increasing, infinitely differentiable, and maps $I_k$ bijectively onto $\mathbb{R}$.

Let $R(u, v)$ be a real rational function of two indeterminates $u, v$, such that $R(\sin x, \cos x)$ is well-defined and continuous on $I_k$ (outside the zero set of its denominator).

---
# Proposition 1
Applying the standard double-angle trigonometric identities expresses $\sin x$ and $\cos x$ in terms of the half-angle $\frac{x}{2}$:
$$
\begin{gather}
\sin x = 2 \sin\left(\frac{x}{2}\right) \cos\left(\frac{x}{2}\right) \tag{2}
\end{gather}
$$
and
$$
\begin{gather}
\cos x = \cos^2\left(\frac{x}{2}\right) - \sin^2\left(\frac{x}{2}\right) \tag{3}
\end{gather}
$$
By virtue of the Pythagorean identity, write unity in the denominator as:
$$
\begin{gather}
1 = \cos^2\left(\frac{x}{2}\right) + \sin^2\left(\frac{x}{2}\right) \tag{4}
\end{gather}
$$
Dividing numerator and denominator of step 2 by $\cos^2\left(\frac{x}{2}\right)$ (which is strictly positive on $I_k$) produces:
$$
\begin{gather}
\sin x = \frac{2 \sin\left(\frac{x}{2}\right) \cos\left(\frac{x}{2}\right)}{\cos^2\left(\frac{x}{2}\right) + \sin^2\left(\frac{x}{2}\right)} = \frac{2 \frac{\sin(x/2)}{\cos(x/2)}}{1 + \frac{\sin^2(x/2)}{\cos^2(x/2)}} = \frac{2 \tan\left(\frac{x}{2}\right)}{1 + \tan^2\left(\frac{x}{2}\right)} \tag{5}
\end{gather}
$$
Substituting $t = \tan(x/2)$ into step 5 establishes the rational algebraic representation of the sine function:
$$
\begin{gather}
\sin x = \frac{2t}{1 + t^2} \tag{6}
\end{gather}
$$

Similarly, dividing the numerator and denominator of step 3 by $\cos^2\left(\frac{x}{2}\right)$ produces:
$$
\begin{gather}
\cos x = \frac{\cos^2\left(\frac{x}{2}\right) - \sin^2\left(\frac{x}{2}\right)}{\cos^2\left(\frac{x}{2}\right) + \sin^2\left(\frac{x}{2}\right)} = \frac{1 - \tan^2\left(\frac{x}{2}\right)}{1 + \tan^2\left(\frac{x}{2}\right)} \tag{7}
\end{gather}
$$
Substituting $t = \tan(x/2)$ into step 7 demonstrates the rational algebraic representation of the cosine function:
$$
\begin{gather}
\cos x = \frac{1 - t^2}{1 + t^2} \tag{8}
\end{gather}
$$

---
# Proposition 2
Invert the substitution $t = \tan(x/2)$ on the principal interval $(-\pi, \pi)$ by:
$$
\begin{gather}
x = 2 \arctan(t) \tag{9}
\end{gather}
$$
(More generally, on $I_k$, the inversion takes the form $x = 2 \arctan(t) + 2k\pi$).

Differentiating both sides of step 9 with respect to the variable $t$ gives the differential relation:
$$
\begin{gather}
\frac{dx}{dt} = \frac{d}{dt}\big(2 \arctan(t)\big) = \frac{2}{1 + t^2} \tag{10}
\end{gather}
$$
Consequently, the differential of the variable $x$ is:
$$
\begin{gather}
dx = \frac{2}{1 + t^2} \, dt \tag{11}
\end{gather}
$$

---
# Proposition 3
Consider the indefinite integral:
$$
\begin{gather}
I = \int R(\sin x, \cos x) \, dx \tag{12}
\end{gather}
$$
Applying the Change of Variables Formula for indefinite integrals under the smooth diffeomorphism $x = \psi(t) = 2 \arctan(t) + 2k\pi$ transforms step 12 into:
$$
\begin{gather}
\int R(\sin x, \cos x) \, dx = \left[ \int R(\sin(\psi(t)), \cos(\psi(t))) \, \psi'(t) \, dt \right]_{t = \tan(x/2)} \tag{13}
\end{gather}
$$
Substituting the rational representations for sine, cosine, and the differential established in Propositions 1 and 2 produces:
$$
\begin{gather}
\int R(\sin x, \cos x) \, dx = \left[ \int R\left(\frac{2t}{1 + t^2}, \frac{1 - t^2}{1 + t^2}\right) \frac{2}{1 + t^2} \, dt \right]_{t = \tan(x/2)} \tag{14}
\end{gather}
$$
Because the composition and product of rational functions is again a rational function, the integrand on the right-hand side of step 14:
$$
\begin{gather}
\widetilde{R}(t) := R\left(\frac{2t}{1 + t^2}, \frac{1 - t^2}{1 + t^2}\right) \frac{2}{1 + t^2} \tag{15}
\end{gather}
$$
is an algebraic rational function of $t$, meaning $\widetilde{R}(t) \in \mathbb{R}(t)$. 

By virtue of the [[Proof of Partial Fraction Decomposition Theorem over the Real Field|Partial Fraction Decomposition Theorem]], every rational function can be integrated explicitly in terms of elementary functions (rational expressions, logarithms, and inverse tangents). Therefore, the Weierstrass substitution transforms any rational trigonometric integral into an algebraically decidable rational integral.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
