---
dg-publish: true
---
Let the hyperbolic functions be defined on their maximal real domains. By the [[Proof of Derivatives of the Six Hyperbolic Functions|Derivatives of the Six Hyperbolic Functions]]:
$$
\begin{gather}
\frac{d}{dy}\sinh(y) = \cosh(y), \quad \frac{d}{dy}\cosh(y) = \sinh(y), \quad \frac{d}{dy}\tanh(y) = 1 - \tanh^2(y) \tag{1}
\end{gather}
$$
$$
\begin{gather}
\frac{d}{dy}\coth(y) = 1 - \coth^2(y), \quad \frac{d}{dy}\operatorname{sech}(y) = -\operatorname{sech}(y)\tanh(y), \quad \frac{d}{dy}\operatorname{csch}(y) = -\operatorname{csch}(y)\coth(y) \tag{2}
\end{gather}
$$

The derivatives of the six inverse hyperbolic functions on their open interior domains are established via the [[Proof of The Derivative of an Inverse Function|Derivative of an Inverse Function Theorem]] and the [[Proof of The Chain Rule|Chain Rule]].

# Proposition 1
Let $x \in \mathbb{R}$. The area hyperbolic sine mapping is defined by:
$$
\begin{gather}
y = \operatorname{arsinh}(x) \iff x = \sinh(y), \quad y \in \mathbb{R} \tag{3}
\end{gather}
$$

Because $\cosh(y) \ge 1 > 0$ for all $y \in \mathbb{R}$, applying the Inverse Function Theorem to step 3 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arsinh}(x) = \frac{1}{\dfrac{d}{dy}\sinh(y)} = \frac{1}{\cosh(y)} \tag{4}
\end{gather}
$$

Using the fundamental identity $\cosh^2(y) - \sinh^2(y) = 1$ with $\cosh(y) > 0$ yields:
$$
\begin{gather}
\cosh(y) = \sqrt{1 + \sinh^2(y)} = \sqrt{1 + x^2} \tag{5}
\end{gather}
$$

Substituting step 5 into step 4 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arsinh}(x) = \frac{1}{\sqrt{x^2 + 1}} \tag{6}
\end{gather}
$$

---
# Proposition 2
Let $x \in (1, \infty)$. The area hyperbolic cosine mapping is defined as the principal branch inverse:
$$
\begin{gather}
y = \operatorname{arcosh}(x) \iff x = \cosh(y), \quad y \in (0, \infty) \tag{7}
\end{gather}
$$

For all $y \in (0, \infty)$, the hyperbolic sine is strictly positive: $\sinh(y) > 0$. By the Inverse Function Theorem:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcosh}(x) = \frac{1}{\dfrac{d}{dy}\cosh(y)} = \frac{1}{\sinh(y)} \tag{8}
\end{gather}
$$

From $\cosh^2(y) - \sinh^2(y) = 1$ and $\sinh(y) > 0$, the sine factor evaluates to:
$$
\begin{gather}
\sinh(y) = \sqrt{\cosh^2(y) - 1} = \sqrt{x^2 - 1} \tag{9}
\end{gather}
$$

Substituting step 9 into step 8 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcosh}(x) = \frac{1}{\sqrt{x^2 - 1}} \tag{10}
\end{gather}
$$

---
# Proposition 3
Let $x \in (-1, 1)$. The area hyperbolic tangent mapping is defined by:
$$
\begin{gather}
y = \operatorname{artanh}(x) \iff x = \tanh(y), \quad y \in \mathbb{R} \tag{11}
\end{gather}
$$

By the Inverse Function Theorem applied to $x = \tanh(y)$:
$$
\begin{gather}
\frac{d}{dx} \operatorname{artanh}(x) = \frac{1}{\dfrac{d}{dy}\tanh(y)} = \frac{1}{1 - \tanh^2(y)} \tag{12}
\end{gather}
$$

Substituting $\tanh(y) = x$ into step 12 produces:
$$
\begin{gather}
\frac{d}{dx} \operatorname{artanh}(x) = \frac{1}{1 - x^2} \tag{13}
\end{gather}
$$

---
# Proposition 4
Let $x \in (-\infty, -1) \cup (1, \infty)$. The area hyperbolic cotangent mapping is defined by:
$$
\begin{gather}
y = \operatorname{arcoth}(x) \iff x = \coth(y), \quad y \in \mathbb{R} \setminus \{0\} \tag{14}
\end{gather}
$$

Invoking the Inverse Function Theorem yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcoth}(x) = \frac{1}{\dfrac{d}{dy}\coth(y)} = \frac{1}{1 - \coth^2(y)} \tag{15}
\end{gather}
$$

Substituting $\coth(y) = x$ into step 15 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcoth}(x) = \frac{1}{1 - x^2} = -\frac{1}{x^2 - 1} \tag{16}
\end{gather}
$$

---
# Proposition 5
Let $x \in (0, 1)$. The area hyperbolic secant function satisfies the reciprocal relation:
$$
\begin{gather}
\operatorname{arsech}(x) = \operatorname{arcosh}\left(\frac{1}{x}\right) \tag{17}
\end{gather}
$$

Because $x \in (0, 1)$, the argument $\frac{1}{x}$ satisfies $\frac{1}{x} > 1$, which lies strictly in the domain of differentiability of $\operatorname{arcosh}$ from Proposition 2.

Applying the Chain Rule to step 17 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arsech}(x) = \operatorname{arcosh}'\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) \tag{18}
\end{gather}
$$

Substituting the derivative from step 10 and $\frac{d}{dx}\left(\frac{1}{x}\right) = -\frac{1}{x^2}$ into step 18 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arsech}(x) = \left(\frac{1}{\sqrt{\left(\dfrac{1}{x}\right)^2 - 1}}\right) \left(-\frac{1}{x^2}\right) = -\frac{1}{x^2 \sqrt{\dfrac{1 - x^2}{x^2}}} \tag{19}
\end{gather}
$$

Because $x > 0$, $\sqrt{x^2} = x$. The denominator of step 19 simplifies to:
$$
\begin{gather}
x^2 \sqrt{\frac{1 - x^2}{x^2}} = x^2 \frac{\sqrt{1 - x^2}}{x} = x \sqrt{1 - x^2} \tag{20}
\end{gather}
$$

Substituting step 20 into step 19 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arsech}(x) = -\frac{1}{x\sqrt{1 - x^2}} \tag{21}
\end{gather}
$$

---
# Proposition 6
Let $x \in \mathbb{R} \setminus \{0\}$. The area hyperbolic cosecant function satisfies:
$$
\begin{gather}
\operatorname{arcsch}(x) = \operatorname{arsinh}\left(\frac{1}{x}\right) \tag{22}
\end{gather}
$$

Applying the Chain Rule to step 22 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsch}(x) = \operatorname{arsinh}'\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) \tag{23}
\end{gather}
$$

Substituting the derivative from step 6 and $\frac{d}{dx}\left(\frac{1}{x}\right) = -\frac{1}{x^2}$ into step 23 produces:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsch}(x) = \left(\frac{1}{\sqrt{\left(\dfrac{1}{x}\right)^2 + 1}}\right) \left(-\frac{1}{x^2}\right) = -\frac{1}{x^2 \sqrt{\dfrac{1 + x^2}{x^2}}} \tag{24}
\end{gather}
$$

Because $\sqrt{x^2} = |x|$ for any non-zero real number $x \neq 0$:
$$
\begin{gather}
x^2 \sqrt{\frac{1 + x^2}{x^2}} = x^2 \frac{\sqrt{1 + x^2}}{|x|} = |x| \sqrt{1 + x^2} \tag{25}
\end{gather}
$$

Substituting step 25 into step 24 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsch}(x) = -\frac{1}{|x|\sqrt{1 + x^2}} \tag{26}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
