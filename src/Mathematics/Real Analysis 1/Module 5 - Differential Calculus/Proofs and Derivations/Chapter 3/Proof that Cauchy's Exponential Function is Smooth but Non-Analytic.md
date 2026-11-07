---
dg-publish: true
---
Define the function $f: \mathbb{R} \to \mathbb{R}$ by:
$$
\begin{gather}
f(x) := \begin{cases} e^{-1/x^2}, & x \neq 0 \\ 0, & x = 0 \end{cases} \tag{1}
\end{gather}
$$

### Step 1: Derivative Representation for $x \neq 0$
We prove by induction that for every $n \in \mathbb{N}$, the $n$-th derivative for $x \neq 0$ has the form:
$$
\begin{gather}
f^{(n)}(x) = P_{3n}\left(\frac{1}{x}\right) e^{-1/x^2} \tag{2}
\end{gather}
$$
where $P_{3n}(t)$ is an algebraic polynomial in $t$ of degree $3n$.

For $n = 1$:
$$
\begin{gather}
f'(x) = e^{-1/x^2} \frac{d}{dx}\left(-\frac{1}{x^2}\right) = \frac{2}{x^3} e^{-1/x^2} = 2\left(\frac{1}{x}\right)^3 e^{-1/x^2} \tag{3}
\end{gather}
$$
Here $P_3(t) = 2t^3$, which is a polynomial of degree 3, establishing the base case.

Assume the equation of step 2 holds for $n = k$: $f^{(k)}(x) = P_{3k}\left(\frac{1}{x}\right) e^{-1/x^2}$. Differentiating with respect to $x$:
$$
\begin{gather}
f^{(k+1)}(x) = P'_{3k}\left(\frac{1}{x}\right)\left(-\frac{1}{x^2}\right) e^{-1/x^2} + P_{3k}\left(\frac{1}{x}\right) \left(\frac{2}{x^3}\right) e^{-1/x^2} \tag{4}
\end{gather}
$$

Setting $t = \frac{1}{x}$:
$$
\begin{gather}
f^{(k+1)}(x) = \big( -t^2 P'_{3k}(t) + 2t^3 P_{3k}(t) \big) e^{-t^2} \tag{5}
\end{gather}
$$
The polynomial $P_{3(k+1)}(t) := 2t^3 P_{3k}(t) - t^2 P'_{3k}(t)$ has degree $3 + 3k = 3(k+1)$, completing the inductive step.

### Step 2: Vanishing of Derivatives at the Origin
We prove by induction on $n \in \mathbb{N} \cup \{0\}$ that $f^{(n)}(0) = 0$.

For $n = 0$, by definition $f(0) = 0$.
Furthermore:
$$
\begin{gather}
\lim_{x \to 0} f(x) = \lim_{x \to 0} e^{-1/x^2} = \lim_{t \to \infty} e^{-t^2} = 0 = f(0) \tag{6}
\end{gather}
$$
so $f$ is continuous at 0.

Assume $f^{(k)}(0) = 0$ for some $k \ge 0$. By the definition of differentiability at a point:
$$
\begin{gather}
f^{(k+1)}(0) = \lim_{x \to 0} \frac{f^{(k)}(x) - f^{(k)}(0)}{x - 0} = \lim_{x \to 0} \frac{1}{x} P_{3k}\left(\frac{1}{x}\right) e^{-1/x^2} \tag{7}
\end{gather}
$$

Setting $t = \frac{1}{x}$, as $x \to 0$ we have $t \to \pm \infty$:
$$
\begin{gather}
f^{(k+1)}(0) = \lim_{|t| \to \infty} t P_{3k}(t) e^{-t^2} = \lim_{|t| \to \infty} \frac{Q_{3k+1}(t)}{e^{t^2}} \tag{8}
\end{gather}
$$
where $Q_{3k+1}(t) = t P_{3k}(t)$ is a polynomial of degree $3k + 1$.

By the growth hierarchy of exponential functions over polynomials (proven in Module 3):
$$
\begin{gather}
\lim_{|t| \to \infty} \frac{t^m}{e^{t^2}} = 0 \quad \forall m \in \mathbb{N} \implies f^{(k+1)}(0) = 0 \tag{9}
\end{gather}
$$

By induction, $f^{(n)}(0) = 0$ for all integers $n \ge 0$.

### Step 3: Failure of Analyticity
The Taylor series of $f$ expanded at $x_0 = 0$ is:
$$
\begin{gather}
T_f(0; x) = \sum_{n=0}^\infty \frac{f^{(n)}(0)}{n!} x^n = \sum_{n=0}^\infty \frac{0}{n!} x^n \equiv 0 \tag{10}
\end{gather}
$$

The Taylor series converges everywhere on $\mathbb{R}$ to the zero function $g(x) \equiv 0$. 

However, for any $x \neq 0$, $f(x) = e^{-1/x^2} > 0 \neq 0$. Therefore:
$$
\begin{gather}
T_f(0; x) = f(x) \iff x = 0 \tag{11}
\end{gather}
$$
The Taylor series represents $f(x)$ only at the single isolated point $x = 0$, proving that $f \in C^\infty(\mathbb{R})$ is not real-analytic in any neighborhood of the origin.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
