---
dg-publish: true
---
Let the circular trigonometric functions be defined on their canonical domains, with derivatives established in the [[Proof of the Master Catalog of Elementary Derivatives|Master Catalog of Elementary Derivatives]] and [[Chapter 2 - The Basic Rules of Differentiation|Chapter 2]]:
$$
\begin{gather}
\frac{d}{dy}\sin(y) = \cos(y), \quad \frac{d}{dy}\cos(y) = -\sin(y), \quad \frac{d}{dy}\tan(y) = \sec^2(y) \tag{1}
\end{gather}
$$
$$
\begin{gather}
\frac{d}{dy}\cot(y) = -\csc^2(y), \quad \frac{d}{dy}\sec(y) = \sec(y)\tan(y), \quad \frac{d}{dy}\csc(y) = -\csc(y)\cot(y) \tag{2}
\end{gather}
$$

The derivatives of the six principal inverse circular functions are determined on their open interior domains via the [[Proof of The Derivative of an Inverse Function|Derivative of an Inverse Function Theorem]].

# Proposition 1
Let $x \in (-1, 1)$. The principal arcsine mapping is defined by:
$$
\begin{gather}
y = \arcsin(x) \iff x = \sin(y), \quad y \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \tag{3}
\end{gather}
$$

On the open interval $\left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$, the cosine function is strictly positive: $\cos(y) > 0$. By the Inverse Function Theorem:
$$
\begin{gather}
\frac{d}{dx} \arcsin(x) = \frac{1}{\dfrac{d}{dy}\sin(y)} = \frac{1}{\cos(y)} \tag{4}
\end{gather}
$$

Applying the Pythagorean identity $\cos^2(y) + \sin^2(y) = 1$ with $\cos(y) > 0$ yields:
$$
\begin{gather}
\cos(y) = \sqrt{1 - \sin^2(y)} = \sqrt{1 - x^2} \tag{5}
\end{gather}
$$

Substituting step 5 into step 4 produces:
$$
\begin{gather}
\frac{d}{dx} \arcsin(x) = \frac{1}{\sqrt{1 - x^2}} \tag{6}
\end{gather}
$$

---
# Proposition 2
Let $x \in (-1, 1)$. The principal arccosine mapping is defined by:
$$
\begin{gather}
y = \arccos(x) \iff x = \cos(y), \quad y \in (0, \pi) \tag{7}
\end{gather}
$$

On the open interval $(0, \pi)$, the sine function is strictly positive: $\sin(y) > 0$. Invoking the Inverse Function Theorem gives:
$$
\begin{gather}
\frac{d}{dx} \arccos(x) = \frac{1}{\dfrac{d}{dy}\cos(y)} = \frac{1}{-\sin(y)} = -\frac{1}{\sin(y)} \tag{8}
\end{gather}
$$

From $\cos^2(y) + \sin^2(y) = 1$ and $\sin(y) > 0$, the sine factor evaluates to:
$$
\begin{gather}
\sin(y) = \sqrt{1 - \cos^2(y)} = \sqrt{1 - x^2} \tag{9}
\end{gather}
$$

Substituting step 9 into step 8 yields:
$$
\begin{gather}
\frac{d}{dx} \arccos(x) = -\frac{1}{\sqrt{1 - x^2}} \tag{10}
\end{gather}
$$

---
# Proposition 3
Let $x \in \mathbb{R}$. The principal arctangent mapping is defined by:
$$
\begin{gather}
y = \arctan(x) \iff x = \tan(y), \quad y \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \tag{11}
\end{gather}
$$

Applying the Inverse Function Theorem to $x = \tan(y)$ yields:
$$
\begin{gather}
\frac{d}{dx} \arctan(x) = \frac{1}{\dfrac{d}{dy}\tan(y)} = \frac{1}{\sec^2(y)} \tag{12}
\end{gather}
$$

By virtue of the trigonometric identity $\sec^2(y) = 1 + \tan^2(y)$, step 12 becomes:
$$
\begin{gather}
\frac{d}{dx} \arctan(x) = \frac{1}{1 + \tan^2(y)} = \frac{1}{1 + x^2} \tag{13}
\end{gather}
$$

---
# Proposition 4
Let $x \in \mathbb{R}$. The principal arccotangent mapping is defined by:
$$
\begin{gather}
y = \operatorname{arccot}(x) \iff x = \cot(y), \quad y \in (0, \pi) \tag{14}
\end{gather}
$$

By the Inverse Function Theorem applied to $x = \cot(y)$:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arccot}(x) = \frac{1}{\dfrac{d}{dy}\cot(y)} = \frac{1}{-\csc^2(y)} = -\frac{1}{\csc^2(y)} \tag{15}
\end{gather}
$$

Using the identity $\csc^2(y) = 1 + \cot^2(y)$, step 15 simplifies to:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arccot}(x) = -\frac{1}{1 + \cot^2(y)} = -\frac{1}{1 + x^2} \tag{16}
\end{gather}
$$

---
# Proposition 5
Let $x \in (-\infty, -1) \cup (1, \infty)$. The principal arcsecant function satisfies:
$$
\begin{gather}
\operatorname{arcsec}(x) = \arccos\left(\frac{1}{x}\right) \tag{17}
\end{gather}
$$

Because $|x| > 1$, the reciprocal argument satisfies $\left|\frac{1}{x}\right| < 1$, which lies strictly in the domain of differentiability of the arccosine function established in Proposition 2.

Applying the [[Proof of The Chain Rule|Chain Rule]] to step 17 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsec}(x) = \frac{d}{dx}\left[\arccos\left(\frac{1}{x}\right)\right] = \arccos'\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) \tag{18}
\end{gather}
$$

Substituting the derivative of arccosine from step 10 and the monomial derivative $\frac{d}{dx}\left(\frac{1}{x}\right) = -\frac{1}{x^2}$ into step 18 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsec}(x) = \left(-\frac{1}{\sqrt{1 - \left(\dfrac{1}{x}\right)^2}}\right) \left(-\frac{1}{x^2}\right) = \frac{1}{x^2 \sqrt{\dfrac{x^2 - 1}{x^2}}} \tag{19}
\end{gather}
$$

Using the positive square root identity $\sqrt{x^2} = |x|$, the denominator in step 19 evaluates to:
$$
\begin{gather}
x^2 \sqrt{\frac{x^2 - 1}{x^2}} = x^2 \frac{\sqrt{x^2 - 1}}{|x|} = |x| \sqrt{x^2 - 1} \tag{20}
\end{gather}
$$

Substituting step 20 into step 19 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arcsec}(x) = \frac{1}{|x|\sqrt{x^2 - 1}} \tag{21}
\end{gather}
$$

---
# Proposition 6
Let $x \in (-\infty, -1) \cup (1, \infty)$. The principal arccosecant function satisfies:
$$
\begin{gather}
\operatorname{arccsc}(x) = \arcsin\left(\frac{1}{x}\right) \tag{22}
\end{gather}
$$

Applying the Chain Rule to step 22 with $\left|\frac{1}{x}\right| < 1$ produces:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arccsc}(x) = \arcsin'\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) \tag{23}
\end{gather}
$$

Substituting the derivative of arcsine from step 6 and $\frac{d}{dx}\left(\frac{1}{x}\right) = -\frac{1}{x^2}$ into step 23 yields:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arccsc}(x) = \left(\frac{1}{\sqrt{1 - \left(\dfrac{1}{x}\right)^2}}\right) \left(-\frac{1}{x^2}\right) = -\frac{1}{x^2 \sqrt{\dfrac{x^2 - 1}{x^2}}} \tag{24}
\end{gather}
$$

Applying the reduction $x^2 \sqrt{\frac{x^2 - 1}{x^2}} = |x|\sqrt{x^2 - 1}$ from step 20 to step 24 gives:
$$
\begin{gather}
\frac{d}{dx} \operatorname{arccsc}(x) = -\frac{1}{|x|\sqrt{x^2 - 1}} \tag{25}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
