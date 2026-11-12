---
dg-publish: true
---
Let the exponential function $\exp(x) = e^x$ be defined on $\mathbb{R}$. From the [[Proof of the Master Catalog of Elementary Derivatives|Master Catalog of Elementary Derivatives]], the derivative of $e^x$ satisfies $\frac{d}{dx} e^x = e^x$. By the [[Proof of The Chain Rule|Chain Rule]] applied to the linear argument $-x$, the derivative of $e^{-x}$ satisfies $\frac{d}{dx} e^{-x} = -e^{-x}$.

# Proposition 1
Let $x \in \mathbb{R}$. The hyperbolic sine function is defined analytically by:
$$
\begin{gather}
\sinh(x) := \frac{e^x - e^{-x}}{2} \tag{1}
\end{gather}
$$

Differentiating step 1 using the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]] yields:
$$
\begin{gather}
\frac{d}{dx} \sinh(x) = \frac{1}{2} \frac{d}{dx}\big(e^x - e^{-x}\big) = \frac{1}{2} \left(\frac{d}{dx} e^x - \frac{d}{dx} e^{-x}\right) \tag{2}
\end{gather}
$$

Substituting the derivatives of $e^x$ and $e^{-x}$ into step 2 gives:
$$
\begin{gather}
\frac{d}{dx} \sinh(x) = \frac{1}{2}\big(e^x - (-e^{-x})\big) = \frac{e^x + e^{-x}}{2} = \cosh(x) \tag{3}
\end{gather}
$$

---
# Proposition 2
Let $x \in \mathbb{R}$. The hyperbolic cosine function is defined analytically by:
$$
\begin{gather}
\cosh(x) := \frac{e^x + e^{-x}}{2} \tag{4}
\end{gather}
$$

Differentiating step 4 via the linearity of the differential operator produces:
$$
\begin{gather}
\frac{d}{dx} \cosh(x) = \frac{1}{2} \left(\frac{d}{dx} e^x + \frac{d}{dx} e^{-x}\right) = \frac{1}{2}\big(e^x + (-e^{-x})\big) \tag{5}
\end{gather}
$$

Simplifying the algebraic signs in step 5 yields:
$$
\begin{gather}
\frac{d}{dx} \cosh(x) = \frac{e^x - e^{-x}}{2} = \sinh(x) \tag{6}
\end{gather}
$$

---
# Proposition 3
Let $x \in \mathbb{R}$. The hyperbolic tangent function is defined by the quotient:
$$
\begin{gather}
\tanh(x) := \frac{\sinh(x)}{\cosh(x)} \tag{7}
\end{gather}
$$

Because $e^x > 0$ for all $x \in \mathbb{R}$, $\cosh(x) = \frac{e^x + e^{-x}}{2} \ge 1 > 0$, guaranteeing that the denominator never vanishes. Differentiating step 7 using the [[Proof of The Quotient Rule of Differentiation|Quotient Rule]] and applying Proposition 1 and Proposition 2 yields:
$$
\begin{gather}
\frac{d}{dx} \tanh(x) = \frac{\left(\dfrac{d}{dx} \sinh(x)\right)\cosh(x) - \sinh(x)\left(\dfrac{d}{dx} \cosh(x)\right)}{\cosh^2(x)} \tag{8}
\end{gather}
$$

Substituting $\frac{d}{dx}\sinh(x) = \cosh(x)$ and $\frac{d}{dx}\cosh(x) = \sinh(x)$ into step 8 gives:
$$
\begin{gather}
\frac{d}{dx} \tanh(x) = \frac{\cosh(x)\cosh(x) - \sinh(x)\sinh(x)}{\cosh^2(x)} = \frac{\cosh^2(x) - \sinh^2(x)}{\cosh^2(x)} \tag{9}
\end{gather}
$$

By virtue of the fundamental hyperbolic identity $\cosh^2(x) - \sinh^2(x) = 1$, step 9 simplifies directly to:
$$
\begin{gather}
\frac{d}{dx} \tanh(x) = \frac{1}{\cosh^2(x)} = \operatorname{sech}^2(x) \tag{10}
\end{gather}
$$

Alternatively, splitting the fraction in step 9 produces:
$$
\begin{gather}
\frac{d}{dx} \tanh(x) = \frac{\cosh^2(x)}{\cosh^2(x)} - \frac{\sinh^2(x)}{\cosh^2(x)} = 1 - \tanh^2(x) \tag{11}
\end{gather}
$$

---
# Proposition 4
Let $x \in \mathbb{R} \setminus \{0\}$. The hyperbolic cotangent function is defined by the quotient:
$$
\begin{gather}
\coth(x) := \frac{\cosh(x)}{\sinh(x)} \tag{12}
\end{gather}
$$

Because $x \neq 0$, $\sinh(x) \neq 0$. Differentiating step 12 via the quotient rule yields:
$$
\begin{gather}
\frac{d}{dx} \coth(x) = \frac{\left(\dfrac{d}{dx} \cosh(x)\right)\sinh(x) - \cosh(x)\left(\dfrac{d}{dx} \sinh(x)\right)}{\sinh^2(x)} \tag{13}
\end{gather}
$$

Substituting the derivatives from Proposition 1 and Proposition 2 into step 13 produces:
$$
\begin{gather}
\frac{d}{dx} \coth(x) = \frac{\sinh(x)\sinh(x) - \cosh(x)\cosh(x)}{\sinh^2(x)} = -\frac{\cosh^2(x) - \sinh^2(x)}{\sinh^2(x)} \tag{14}
\end{gather}
$$

Applying the identity $\cosh^2(x) - \sinh^2(x) = 1$ to step 14 gives:
$$
\begin{gather}
\frac{d}{dx} \coth(x) = -\frac{1}{\sinh^2(x)} = -\operatorname{csch}^2(x) \tag{15}
\end{gather}
$$

Rewriting step 14 by separating terms yields the equivalent algebraic formulation:
$$
\begin{gather}
\frac{d}{dx} \coth(x) = 1 - \frac{\cosh^2(x)}{\sinh^2(x)} = 1 - \coth^2(x) \tag{16}
\end{gather}
$$

---
# Proposition 5
Let $x \in \mathbb{R}$. The hyperbolic secant function is defined as the reciprocal:
$$
\begin{gather}
\operatorname{sech}(x) := \frac{1}{\cosh(x)} \tag{17}
\end{gather}
$$

Applying the reciprocal differentiation rule derived in the [[Proof of The Quotient Rule of Differentiation|Quotient Rule]] to step 17 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{sech}(x) = -\frac{\dfrac{d}{dx} \cosh(x)}{\cosh^2(x)} \tag{18}
\end{gather}
$$

Substituting $\frac{d}{dx}\cosh(x) = \sinh(x)$ into step 18 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{sech}(x) = -\frac{\sinh(x)}{\cosh^2(x)} = -\frac{1}{\cosh(x)} \cdot \frac{\sinh(x)}{\cosh(x)} = -\operatorname{sech}(x)\tanh(x) \tag{19}
\end{gather}
$$

---
# Proposition 6
Let $x \in \mathbb{R} \setminus \{0\}$. The hyperbolic cosecant function is defined by:
$$
\begin{gather}
\operatorname{csch}(x) := \frac{1}{\sinh(x)} \tag{20}
\end{gather}
$$

Applying the reciprocal rule to step 20 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{csch}(x) = -\frac{\dfrac{d}{dx} \sinh(x)}{\sinh^2(x)} \tag{21}
\end{gather}
$$

Substituting $\frac{d}{dx}\sinh(x) = \cosh(x)$ into step 21 produces:
$$
\begin{gather}
\frac{d}{dx} \operatorname{csch}(x) = -\frac{\cosh(x)}{\sinh^2(x)} = -\frac{1}{\sinh(x)} \cdot \frac{\cosh(x)}{\sinh(x)} = -\operatorname{csch}(x)\coth(x) \tag{22}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
