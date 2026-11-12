---
dg-publish: true
---
Let $f \in C^\infty(\mathbb{R})$ be an infinitely differentiable function on $\mathbb{R}$, and let $x \in \mathbb{R} \setminus \{0\}$.

For each integer $n \in \mathbb{N}$, define the auxiliary inverted polynomial-weighted mapping $g_n: \mathbb{R} \setminus \{0\} \to \mathbb{R}$ by:
$$
\begin{gather}
g_n(x) := x^{n-1} f\left(\frac{1}{x}\right) \tag{1}
\end{gather}
$$

The identity to be established is that the $n$-th derivative of $g_n(x)$ satisfies:
$$
\begin{gather}
g_n^{(n)}(x) = \frac{d^n}{dx^n}\left(x^{n-1} f\left(\frac{1}{x}\right)\right) = (-1)^n \frac{1}{x^{n+1}} f^{(n)}\left(\frac{1}{x}\right) \tag{2}
\end{gather}
$$
which, upon multiplying both sides by $(-1)^n$ (noting that $(-1)^{2n} = 1$), is equivalent to:
$$
\begin{gather}
\frac{1}{x^{n+1}} f^{(n)}\left(\frac{1}{x}\right) = (-1)^n \frac{d^n}{dx^n}\left(x^{n-1} f\left(\frac{1}{x}\right)\right) \tag{3}
\end{gather}
$$

The identity in step 2 is established by mathematical induction on $n \in \mathbb{N}$.

**Base Case ($n = 1$):**
For $n = 1$, step 1 gives $g_1(x) = x^0 f(1/x) = f(1/x)$. Differentiating $g_1(x)$ via the [[Proof of The Chain Rule|Chain Rule]] with respect to $x$ yields:
$$
\begin{gather}
g_1'(x) = \frac{d}{dx}\left[f\left(\frac{1}{x}\right)\right] = f'\left(\frac{1}{x}\right) \cdot \frac{d}{dx}\left(\frac{1}{x}\right) = f'\left(\frac{1}{x}\right) \cdot \left(-\frac{1}{x^2}\right) = (-1)^1 \frac{1}{x^2} f'\left(\frac{1}{x}\right) \tag{4}
\end{gather}
$$

Because step 4 matches step 2 for $n = 1$, the base case holds.

**Induction Hypothesis:**
Assume that for an arbitrary integer $m \ge 1$, the formula holds for $n = m$:
$$
\begin{gather}
g_m^{(m)}(x) = \frac{d^m}{dx^m}\left(x^{m-1} f\left(\frac{1}{x}\right)\right) = (-1)^m \frac{1}{x^{m+1}} f^{(m)}\left(\frac{1}{x}\right) \tag{5}
\end{gather}
$$

**Induction Step ($n = m + 1$):**
Consider the function $g_{m+1}(x) = x^m f(1/x)$. Factoring an explicit power of $x$ relates $g_{m+1}$ to $g_m$:
$$
\begin{gather}
g_{m+1}(x) = x \cdot \left(x^{m-1} f\left(\frac{1}{x}\right)\right) = x \cdot g_m(x) \tag{6}
\end{gather}
$$

Differentiating the product $x \cdot g_m(x)$ to order $m + 1$ using the [[Proof of The General Leibniz Rule|General Leibniz Rule]] gives:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = \frac{d^{m+1}}{dx^{m+1}}\big(x \cdot g_m(x)\big) = \sum_{k=0}^{m+1} \binom{m+1}{k} \left(\frac{d^k}{dx^k} x\right) g_m^{(m+1-k)}(x) \tag{7}
\end{gather}
$$

Because the coordinate function $x$ is a first-degree polynomial, its higher derivatives vanish: $\frac{d^k}{dx^k} x = 0$ for all $k \ge 2$. Thus, only the terms corresponding to $k = 0$ and $k = 1$ in step 7 are non-zero:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = \binom{m+1}{0} x \cdot g_m^{(m+1)}(x) + \binom{m+1}{1} 1 \cdot g_m^{(m)}(x) \tag{8}
\end{gather}
$$

Substituting the binomial coefficients $\binom{m+1}{0} = 1$ and $\binom{m+1}{1} = m + 1$ into step 8 yields:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = x \cdot g_m^{(m+1)}(x) + (m + 1) g_m^{(m)}(x) = x \frac{d}{dx}\left[g_m^{(m)}(x)\right] + (m + 1) g_m^{(m)}(x) \tag{9}
\end{gather}
$$

Applying the induction hypothesis from step 5, express $g_m^{(m)}(x)$ as:
$$
\begin{gather}
g_m^{(m)}(x) = (-1)^m x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) \tag{10}
\end{gather}
$$

Differentiating step 10 with respect to $x$ using the product rule and chain rule gives:
$$
\begin{gather}
\frac{d}{dx}\left[g_m^{(m)}(x)\right] = (-1)^m \left[ -(m+1)x^{-(m+2)} f^{(m)}\left(\frac{1}{x}\right) + x^{-(m+1)} f^{(m+1)}\left(\frac{1}{x}\right) \cdot \left(-\frac{1}{x^2}\right) \right] \tag{11}
\end{gather}
$$

Simplifying the algebraic exponents in step 11 yields:
$$
\begin{gather}
\frac{d}{dx}\left[g_m^{(m)}(x)\right] = (-1)^m \left[ -(m+1)x^{-(m+2)} f^{(m)}\left(\frac{1}{x}\right) - x^{-(m+3)} f^{(m+1)}\left(\frac{1}{x}\right) \right] \tag{12}
\end{gather}
$$

Multiplying step 12 by $x$ produces:
$$
\begin{gather}
x \frac{d}{dx}\left[g_m^{(m)}(x)\right] = (-1)^m \left[ -(m+1)x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) - x^{-(m+2)} f^{(m+1)}\left(\frac{1}{x}\right) \right] \tag{13}
\end{gather}
$$

Now substituting step 10 and step 13 into step 9 yields:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = (-1)^m \left[ -(m+1)x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) - x^{-(m+2)} f^{(m+1)}\left(\frac{1}{x}\right) \right] + (m+1) (-1)^m x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) \tag{14}
\end{gather}
$$

Factoring $(-1)^m$, the first and third terms in step 14 cancel identically:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = (-1)^m \left[ -(m+1)x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) + (m+1)x^{-(m+1)} f^{(m)}\left(\frac{1}{x}\right) - x^{-(m+2)} f^{(m+1)}\left(\frac{1}{x}\right) \right] \tag{15}
\end{gather}
$$

Evaluating the cancellation in step 15 leaves:
$$
\begin{gather}
g_{m+1}^{(m+1)}(x) = (-1)^m \left[ -x^{-(m+2)} f^{(m+1)}\left(\frac{1}{x}\right) \right] = (-1)^{m+1} \frac{1}{x^{m+2}} f^{(m+1)}\left(\frac{1}{x}\right) \tag{16}
\end{gather}
$$

Because step 16 matches the induction formula for $n = m + 1$, the induction step is complete.

By mathematical induction, step 2 holds for all $n \in \mathbb{N}$. Multiplying both sides of step 2 by $(-1)^n$ proves step 3.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
