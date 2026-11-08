---
dg-publish: true
---
Let the standard elementary functions be defined on their respective maximal domains in $\mathbb{R}$, and let the derivatives be evaluated as limits of the difference quotient as the displacement $h$ approaches zero.

# Theorem 1
Let $n \in \mathbb{N}$ and let $f: \mathbb{R} \to \mathbb{R}$ be the monomial function $f(x) := x^n$.

For any point $x \in \mathbb{R}$ and non-zero increment $h \neq 0$, the binomial expansion of $(x + h)^n$ yields:
$$
\begin{gather}
(x + h)^n = \sum_{k=0}^n \binom{n}{k} x^{n-k} h^k = x^n + n x^{n-1} h + \sum_{k=2}^n \binom{n}{k} x^{n-k} h^k \tag{1}
\end{gather}
$$

Subtracting $x^n$ from step 1 and dividing by $h$ gives:
$$
\begin{gather}
\frac{f(x + h) - f(x)}{h} = \frac{(x + h)^n - x^n}{h} = n x^{n-1} + \sum_{k=2}^n \binom{n}{k} x^{n-k} h^{k-1} \tag{2}
\end{gather}
$$

Factoring an explicit factor of $h$ from the summation in step 2 produces:
$$
\begin{gather}
\frac{f(x + h) - f(x)}{h} = n x^{n-1} + h \sum_{k=2}^n \binom{n}{k} x^{n-k} h^{k-2} \tag{3}
\end{gather}
$$
where the remaining sum is a polynomial in $h$ (which is empty when $n = 1$). Taking the limit as $h \to 0$ across step 3 yields:
$$
\begin{gather}
\frac{d}{dx}\big(x^n\big) = \lim_{h \to 0} \frac{(x + h)^n - x^n}{h} = n x^{n-1} + 0 \cdot \sum_{k=2}^n \binom{n}{k} x^{n-k} 0^{k-2} = n x^{n-1} \tag{4}
\end{gather}
$$

---
# Theorem 2
Let $\alpha \in \mathbb{R}$, and consider the power function $f(x) := x^\alpha$ defined on the open domain $(0, \infty)$.

Let $x \in (0, \infty)$ and let $h \in \mathbb{R}$ be chosen such that $|h| < x$, guaranteeing that $x + h > 0$. Factoring $x^\alpha$ from the difference quotient yields:
$$
\begin{gather}
\frac{f(x + h) - f(x)}{h} = \frac{(x + h)^\alpha - x^\alpha}{h} = \frac{x^\alpha \left[\left(1 + \dfrac{h}{x}\right)^\alpha - 1\right]}{h} = x^{\alpha - 1} \frac{\left(1 + \dfrac{h}{x}\right)^\alpha - 1}{\dfrac{h}{x}} \tag{5}
\end{gather}
$$

Define the change of variable $u := \frac{h}{x}$. As $h \to 0$, it follows that $u \to 0$ with $u \neq 0$. Step 5 is rewritten as:
$$
\begin{gather}
\frac{(x + h)^\alpha - x^\alpha}{h} = x^{\alpha - 1} \frac{(1 + u)^\alpha - 1}{u} \tag{6}
\end{gather}
$$

Expressing the power $(1 + u)^\alpha$ via the natural exponential and logarithm functions gives $(1 + u)^\alpha = \exp\big(\alpha \ln(1 + u)\big)$. Substituting this identity into the quotient of step 6 yields:
$$
\begin{gather}
\frac{(1 + u)^\alpha - 1}{u} = \frac{e^{\alpha \ln(1 + u)} - 1}{\alpha \ln(1 + u)} \cdot \alpha \cdot \frac{\ln(1 + u)}{u} \tag{7}
\end{gather}
$$

Setting $v := \alpha \ln(1 + u)$, the continuity of the logarithm guarantees that $v \to 0$ as $u \to 0$. From the fundamental limits of the natural exponential and logarithmic functions established in [[Chapter 2 - Limits of Functions|Module 3, Chapter 2]]:
$$
\begin{gather}
\lim_{v \to 0} \frac{e^v - 1}{v} = 1 \qquad \text{and} \qquad \lim_{u \to 0} \frac{\ln(1 + u)}{u} = 1 \tag{8}
\end{gather}
$$

Applying the product rule for limits to step 7 using the limits of step 8 gives:
$$
\begin{gather}
\lim_{u \to 0} \frac{(1 + u)^\alpha - 1}{u} = \left(\lim_{v \to 0} \frac{e^v - 1}{v}\right) \cdot \alpha \cdot \left(\lim_{u \to 0} \frac{\ln(1 + u)}{u}\right) = 1 \cdot \alpha \cdot 1 = \alpha \tag{9}
\end{gather}
$$

Substituting step 9 into step 6 confirms that:
$$
\begin{gather}
\frac{d}{dx}\big(x^\alpha\big) = \lim_{h \to 0} \frac{(x + h)^\alpha - x^\alpha}{h} = x^{\alpha - 1} \cdot \alpha = \alpha x^{\alpha - 1} \tag{10}
\end{gather}
$$

---
# Theorem 3
Let $f: \mathbb{R} \to \mathbb{R}$ be the natural exponential function $f(x) := e^x$.

For any point $x \in \mathbb{R}$ and non-zero increment $h \neq 0$, the functional equation of the exponential function $e^{x + h} = e^x e^h$ allows factoring the term $e^x$:
$$
\begin{gather}
\frac{f(x + h) - f(x)}{h} = \frac{e^{x + h} - e^x}{h} = e^x \frac{e^h - 1}{h} \tag{11}
\end{gather}
$$

By virtue of the fundamental limit of the exponential function at the origin:
$$
\begin{gather}
\lim_{h \to 0} \frac{e^h - 1}{h} = 1 \tag{12}
\end{gather}
$$

Evaluating the limit of step 11 as $h \to 0$ and applying step 12 yields:
$$
\begin{gather}
\frac{d}{dx}\big(e^x\big) = \lim_{h \to 0} \left(e^x \frac{e^h - 1}{h}\right) = e^x \lim_{h \to 0} \frac{e^h - 1}{h} = e^x \cdot 1 = e^x \tag{13}
\end{gather}
$$

---
# Theorem 4
Let $f: \mathbb{R} \to \mathbb{R}$ be the circular trigonometric sine function $f(x) := \sin x$.

For any point $x \in \mathbb{R}$ and non-zero increment $h \neq 0$, applying the trigonometric sum-to-product identity:
$$
\begin{gather}
\sin A - \sin B = 2 \sin\left(\frac{A - B}{2}\right) \cos\left(\frac{A + B}{2}\right) \tag{14}
\end{gather}
$$
with $A = x + h$ and $B = x$ yields:
$$
\begin{gather}
\sin(x + h) - \sin x = 2 \sin\left(\frac{h}{2}\right) \cos\left(x + \frac{h}{2}\right) \tag{15}
\end{gather}
$$

Dividing step 15 by $h$ produces:
$$
\begin{gather}
\frac{\sin(x + h) - \sin x}{h} = \frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \cos\left(x + \frac{h}{2}\right) \tag{16}
\end{gather}
$$

Setting $u := \frac{h}{2} \to 0$ as $h \to 0$, the fundamental trigonometric limit gives:
$$
\begin{gather}
\lim_{h \to 0} \frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} = \lim_{u \to 0} \frac{\sin u}{u} = 1 \tag{17}
\end{gather}
$$
Furthermore, because the cosine function is continuous everywhere on $\mathbb{R}$:
$$
\begin{gather}
\lim_{h \to 0} \cos\left(x + \frac{h}{2}\right) = \cos x \tag{18}
\end{gather}
$$

Applying the product rule for limits to step 16 with step 17 and step 18 gives:
$$
\begin{gather}
\frac{d}{dx}(\sin x) = \lim_{h \to 0} \left( \frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \cos\left(x + \frac{h}{2}\right) \right) = 1 \cdot \cos x = \cos x \tag{19}
\end{gather}
$$

---
# Theorem 5
Let $f: \mathbb{R} \to \mathbb{R}$ be the circular trigonometric cosine function $f(x) := \cos x$.

For any point $x \in \mathbb{R}$ and non-zero increment $h \neq 0$, applying the trigonometric sum-to-product identity:
$$
\begin{gather}
\cos A - \cos B = -2 \sin\left(\frac{A - B}{2}\right) \sin\left(\frac{A + B}{2}\right) \tag{20}
\end{gather}
$$
with $A = x + h$ and $B = x$ yields:
$$
\begin{gather}
\cos(x + h) - \cos x = -2 \sin\left(\frac{h}{2}\right) \sin\left(x + \frac{h}{2}\right) \tag{21}
\end{gather}
$$

Dividing step 21 by $h$ gives:
$$
\begin{gather}
\frac{\cos(x + h) - \cos x}{h} = -\frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \sin\left(x + \frac{h}{2}\right) \tag{22}
\end{gather}
$$

By virtue of the fundamental trigonometric limit of step 17 and the continuity of the sine function on $\mathbb{R}$:
$$
\begin{gather}
\lim_{h \to 0} \frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} = 1 \qquad \text{and} \qquad \lim_{h \to 0} \sin\left(x + \frac{h}{2}\right) = \sin x \tag{23}
\end{gather}
$$

Evaluating the limit of step 22 as $h \to 0$ using step 23 yields:
$$
\begin{gather}
\frac{d}{dx}(\cos x) = \lim_{h \to 0} \left( -\frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \sin\left(x + \frac{h}{2}\right) \right) = -1 \cdot \sin x = -\sin x \tag{24}
\end{gather}
$$

---
# Theorem 6
Let $x \in \mathbb{R} \setminus \left\{\frac{\pi}{2} + n\pi \ \middle|\ n \in \mathbb{Z}\right\}$, and let $f(x) := \tan x = \frac{\sin x}{\cos x}$.

For any displacement $h \neq 0$ such that $x + h$ lies within the domain of the tangent function, constructing the difference quotient gives:
$$
\begin{gather}
\frac{\tan(x + h) - \tan x}{h} = \frac{1}{h} \left( \frac{\sin(x + h)}{\cos(x + h)} - \frac{\sin x}{\cos x} \right) = \frac{\sin(x + h)\cos x - \cos(x + h)\sin x}{h \cos(x + h)\cos x} \tag{25}
\end{gather}
$$

Applying the angle subtraction identity for the sine function:
$$
\begin{gather}
\sin(A - B) = \sin A \cos B - \cos A \sin B \tag{26}
\end{gather}
$$
to the numerator of step 25 with $A = x + h$ and $B = x$ reveals:
$$
\begin{gather}
\sin(x + h)\cos x - \cos(x + h)\sin x = \sin\big((x + h) - x\big) = \sin h \tag{27}
\end{gather}
$$

Substituting step 27 into step 25 isolates the fundamental quotient:
$$
\begin{gather}
\frac{\tan(x + h) - \tan x}{h} = \frac{\sin h}{h} \cdot \frac{1}{\cos(x + h)\cos x} \tag{28}
\end{gather}
$$

Because $\cos x \neq 0$ on the domain of the tangent function, the continuity of the cosine function guarantees:
$$
\begin{gather}
\lim_{h \to 0} \cos(x + h) = \cos x \neq 0 \implies \lim_{h \to 0} \frac{1}{\cos(x + h)\cos x} = \frac{1}{\cos^2 x} \tag{29}
\end{gather}
$$

Combining step 29 with the limit $\lim_{h \to 0} \frac{\sin h}{h} = 1$ in step 28 gives:
$$
\begin{gather}
\frac{d}{dx}(\tan x) = \lim_{h \to 0} \left( \frac{\sin h}{h} \cdot \frac{1}{\cos(x + h)\cos x} \right) = 1 \cdot \frac{1}{\cos^2 x} = \sec^2 x \tag{30}
\end{gather}
$$

---
# Theorem 7
Let $x \in \mathbb{R} \setminus \{n\pi \mid n \in \mathbb{Z}\}$, and let $f(x) := \csc x = \frac{1}{\sin x}$.

For a non-zero increment $h \neq 0$ such that $x + h$ lies in the domain of the cosecant function, forming the difference quotient yields:
$$
\begin{gather}
\frac{\csc(x + h) - \csc x}{h} = \frac{1}{h} \left( \frac{1}{\sin(x + h)} - \frac{1}{\sin x} \right) = \frac{\sin x - \sin(x + h)}{h \sin(x + h)\sin x} \tag{31}
\end{gather}
$$

Applying the sum-to-product identity of step 14 to the numerator of step 31 gives:
$$
\begin{gather}
\sin x - \sin(x + h) = -2 \sin\left(\frac{h}{2}\right) \cos\left(x + \frac{h}{2}\right) \tag{32}
\end{gather}
$$

Substituting step 32 into step 31 yields:
$$
\begin{gather}
\frac{\csc(x + h) - \csc x}{h} = -\frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \cdot \frac{\cos\left(x + \frac{h}{2}\right)}{\sin(x + h)\sin x} \tag{33}
\end{gather}
$$

Because $\sin x \neq 0$ on the domain, the continuity of the sine and cosine functions implies:
$$
\begin{gather}
\lim_{h \to 0} \frac{\cos\left(x + \frac{h}{2}\right)}{\sin(x + h)\sin x} = \frac{\cos x}{\sin^2 x} \tag{34}
\end{gather}
$$

Taking the limit of step 33 as $h \to 0$ and applying step 17 alongside step 34 gives:
$$
\begin{gather}
\frac{d}{dx}(\csc x) = -1 \cdot \frac{\cos x}{\sin^2 x} = -\frac{1}{\sin x} \cdot \frac{\cos x}{\sin x} = -\csc x \cot x \tag{35}
\end{gather}
$$

---
# Theorem 8
Let $x \in \mathbb{R} \setminus \left\{\frac{\pi}{2} + n\pi \ \middle|\ n \in \mathbb{Z}\right\}$, and let $f(x) := \sec x = \frac{1}{\cos x}$.

For a non-zero displacement $h \neq 0$ such that $x + h$ lies in the domain of the secant function, the difference quotient is:
$$
\begin{gather}
\frac{\sec(x + h) - \sec x}{h} = \frac{1}{h} \left( \frac{1}{\cos(x + h)} - \frac{1}{\cos x} \right) = \frac{\cos x - \cos(x + h)}{h \cos(x + h)\cos x} \tag{36}
\end{gather}
$$

Applying the sum-to-product identity of step 20 to the numerator of step 36 yields:
$$
\begin{gather}
\cos x - \cos(x + h) = 2 \sin\left(\frac{h}{2}\right) \sin\left(x + \frac{h}{2}\right) \tag{37}
\end{gather}
$$

Substituting step 37 into step 36 gives:
$$
\begin{gather}
\frac{\sec(x + h) - \sec x}{h} = \frac{\sin\left(\frac{h}{2}\right)}{\frac{h}{2}} \cdot \frac{\sin\left(x + \frac{h}{2}\right)}{\cos(x + h)\cos x} \tag{38}
\end{gather}
$$

Because $\cos x \neq 0$ on the domain, the continuity of sine and cosine implies:
$$
\begin{gather}
\lim_{h \to 0} \frac{\sin\left(x + \frac{h}{2}\right)}{\cos(x + h)\cos x} = \frac{\sin x}{\cos^2 x} \tag{39}
\end{gather}
$$

Taking the limit of step 38 as $h \to 0$ and invoking step 17 and step 39 yields:
$$
\begin{gather}
\frac{d}{dx}(\sec x) = 1 \cdot \frac{\sin x}{\cos^2 x} = \frac{1}{\cos x} \cdot \frac{\sin x}{\cos x} = \sec x \tan x \tag{40}
\end{gather}
$$

---
# Theorem 9
Let $x \in \mathbb{R} \setminus \{n\pi \mid n \in \mathbb{Z}\}$, and let $f(x) := \cot x = \frac{\cos x}{\sin x}$.

For a non-zero increment $h \neq 0$ such that $x + h$ lies in the domain of the cotangent function, forming the difference quotient yields:
$$
\begin{gather}
\frac{\cot(x + h) - \cot x}{h} = \frac{1}{h} \left( \frac{\cos(x + h)}{\sin(x + h)} - \frac{\cos x}{\sin x} \right) = \frac{\cos(x + h)\sin x - \sin(x + h)\cos x}{h \sin(x + h)\sin x} \tag{41}
\end{gather}
$$

By virtue of the angle subtraction identity for the sine function in step 26:
$$
\begin{gather}
\cos(x + h)\sin x - \sin(x + h)\cos x = \sin\big(x - (x + h)\big) = \sin(-h) = -\sin h \tag{42}
\end{gather}
$$

Substituting step 42 into step 41 isolates the ratio:
$$
\begin{gather}
\frac{\cot(x + h) - \cot x}{h} = -\frac{\sin h}{h} \cdot \frac{1}{\sin(x + h)\sin x} \tag{43}
\end{gather}
$$

Because $\sin x \neq 0$ on the domain of the cotangent function, the continuity of the sine function gives:
$$
\begin{gather}
\lim_{h \to 0} \frac{1}{\sin(x + h)\sin x} = \frac{1}{\sin^2 x} \tag{44}
\end{gather}
$$

Taking the limit of step 43 as $h \to 0$ and applying step 44 with $\lim_{h \to 0} \frac{\sin h}{h} = 1$ yields:
$$
\begin{gather}
\frac{d}{dx}(\cot x) = -1 \cdot \frac{1}{\sin^2 x} = -\csc^2 x \tag{45}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$