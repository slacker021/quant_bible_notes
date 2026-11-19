---
dg-publish: true
---
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, let $n \in \mathbb{N}_0 = \{0, 1, 2, \dots\}$, let $f \in C^{n+1}[a, b]$, let $x_0 \in [a, b]$ be a fixed expansion basepoint, and let $x \in [a, b]$ be an arbitrary evaluation point.

If $x = x_0$, the difference $x - x_0 = 0$. The polynomial summation reduces to:
$$
\begin{gather}
\sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x_0 - x_0)^k = f(x_0) + \sum_{k=1}^n 0 = f(x_0) \tag{1}
\end{gather}
$$
and the integral over the degenerate interval $[x_0, x_0]$ vanishes:
$$
\begin{gather}
R_n(x_0) = \frac{1}{n!} \int_{x_0}^{x_0} f^{(n+1)}(t)(x_0 - t)^n\,dt = 0 \tag{2}
\end{gather}
$$
so the identity $f(x_0) = f(x_0) + 0$ holds identically.

Assume henceforth that $x \neq x_0$. 

---
# Base Case
For $n = 0$, the regularity hypothesis is $f \in C^1[a, b]$. 

The first derivative $f'$ is continuous on $[a, b]$, and therefore its restriction to the interval connecting $x_0$ and $x$ is continuous and Riemann integrable.

Applying the Newton-Leibniz Formula (Module 6, Chapter 3, [[Proof of the Newton-Leibniz Formula]]) to $f'$ on the interval connecting $x_0$ and $x$:
$$
\begin{gather}
\int_{x_0}^x f'(t)\,dt = f(x) - f(x_0) \tag{3}
\end{gather}
$$

Rearranging step 3 to express $f(x)$:
$$
\begin{gather}
f(x) = f(x_0) + \int_{x_0}^x f'(t)\,dt \tag{4}
\end{gather}
$$

Evaluating the Taylor polynomial sum for $n = 0$:
$$
\begin{gather}
\sum_{k=0}^0 \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k = \frac{f^{(0)}(x_0)}{0!}(x - x_0)^0 = f(x_0) \tag{5}
\end{gather}
$$

Evaluating the candidate integral remainder for $n = 0$:
$$
\begin{gather}
R_0(x) := \frac{1}{0!} \int_{x_0}^x f^{(0+1)}(t)(x - t)^0\,dt = \frac{1}{1} \int_{x_0}^x f'(t) \cdot 1\,dt = \int_{x_0}^x f'(t)\,dt \tag{6}
\end{gather}
$$

Substituting step 5 and step 6 into step 4 yields:
$$
\begin{gather}
f(x) = \sum_{k=0}^0 \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + R_0(x) \tag{7}
\end{gather}
$$
which confirms the base case $n = 0$.

---
# Inductive Step
Assume as the induction hypothesis that for a fixed integer $n \ge 0$, every function $f \in C^{n+1}[a, b]$ satisfies:
$$
\begin{gather}
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + R_n(x) \tag{8}
\end{gather}
$$
with exact remainder:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} \int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt \tag{9}
\end{gather}
$$

Now suppose $f \in C^{n+2}[a, b]$. 

Because $C^{n+2}[a, b] \subset C^{n+1}[a, b]$, the representation of step 8 and step 9 holds for $f$. Examine the integral in the expression for $R_n(x)$:
$$
\begin{gather}
I_n(x) := \int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt \tag{10}
\end{gather}
$$

Define the functional factors on the interval connecting $x_0$ and $x$:
$$
\begin{gather}
u(t) := f^{(n+1)}(t) \tag{11}
\end{gather}
$$
and:
$$
\begin{gather}
v'(t) := (x - t)^n \tag{12}
\end{gather}
$$

Because $f \in C^{n+2}[a, b]$, the function $u$ is continuously differentiable on $[a, b]$, with derivative:
$$
\begin{gather}
u'(t) = f^{(n+2)}(t) \tag{13}
\end{gather}
$$

To determine an antiderivative $v(t)$ for the factor $v'(t) = (x - t)^n$, integrate with respect to $t$:
$$
\begin{gather}
\frac{d}{dt}\left( -\frac{(x - t)^{n+1}}{n + 1} \right) = -\frac{1}{n + 1} \cdot (n + 1)(x - t)^n \cdot \frac{d}{dt}(x - t) = -(x - t)^n(-1) = (x - t)^n \tag{14}
\end{gather}
$$

Therefore, choose the primitive:
$$
\begin{gather}
v(t) := -\frac{(x - t)^{n+1}}{n + 1} \tag{15}
\end{gather}
$$

Both $u$ and $v$ belong to $C^1$ on the interval connecting $x_0$ and $x$. Applying the Theorem on Integration by Parts for Definite Integrals (Module 6, Chapter 3, [[Proof of Integration by Parts for Definite Integrals]]) to $I_n(x)$:
$$
\begin{gather}
\int_{x_0}^x u(t)v'(t)\,dt = \big[ u(t)v(t) \big]_{x_0}^x - \int_{x_0}^x u'(t)v(t)\,dt \tag{16}
\end{gather}
$$

Substituting $u, v, u'$ from steps 11, 13, and 15 into step 16:
$$
\begin{gather}
I_n(x) = \left[ -f^{(n+1)}(t) \frac{(x - t)^{n+1}}{n + 1} \right]_{x_0}^x - \int_{x_0}^x f^{(n+2)}(t)\left( -\frac{(x - t)^{n+1}}{n + 1} \right)\,dt \tag{17}
\end{gather}
$$

Evaluate the boundary term at the upper limit $t = x$:
$$
\begin{gather}
-f^{(n+1)}(x) \frac{(x - x)^{n+1}}{n + 1} = -f^{(n+1)}(x) \frac{0^{n+1}}{n + 1} = 0 \tag{18}
\end{gather}
$$
which holds because the exponent $n + 1 \ge 1$ is strictly positive.

Evaluate the boundary term at the lower limit $t = x_0$:
$$
\begin{gather}
-\left( -f^{(n+1)}(x_0) \frac{(x - x_0)^{n+1}}{n + 1} \right) = \frac{f^{(n+1)}(x_0)}{n + 1}(x - x_0)^{n+1} \tag{19}
\end{gather}
$$

In the integral term on the right-hand side of step 17, extracting the constant scalar factor $\frac{1}{n+1}$ by Linearity of the Riemann Integral (Module 6, Chapter 2, [[Proof of the Linearity of the Riemann Integral]]):
$$
\begin{gather}
-\int_{x_0}^x f^{(n+2)}(t)\left( -\frac{(x - t)^{n+1}}{n + 1} \right)\,dt = \frac{1}{n + 1} \int_{x_0}^x f^{(n+2)}(t)(x - t)^{n+1}\,dt \tag{20}
\end{gather}
$$

Combining step 18, step 19, and step 20 in step 17 yields:
$$
\begin{gather}
I_n(x) = \frac{f^{(n+1)}(x_0)}{n + 1}(x - x_0)^{n+1} + \frac{1}{n + 1} \int_{x_0}^x f^{(n+2)}(t)(x - t)^{n+1}\,dt \tag{21}
\end{gather}
$$

Now substitute step 21 into the expression for $R_n(x)$ from step 9:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} I_n(x) = \frac{1}{n!} \left( \frac{f^{(n+1)}(x_0)}{n + 1}(x - x_0)^{n+1} + \frac{1}{n + 1} \int_{x_0}^x f^{(n+2)}(t)(x - t)^{n+1}\,dt \right) \tag{22}
\end{gather}
$$

Distributing $\frac{1}{n!}$ across the sum in step 22 and applying the factorial recursion $(n + 1) \cdot n! = (n + 1)!$:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}(x_0)}{(n + 1)!}(x - x_0)^{n+1} + \frac{1}{(n + 1)!} \int_{x_0}^x f^{(n+2)}(t)(x - t)^{n+1}\,dt \tag{23}
\end{gather}
$$

Define the remainder of order $n + 1$ by:
$$
\begin{gather}
R_{n+1}(x) := \frac{1}{(n + 1)!} \int_{x_0}^x f^{(n+2)}(t)(x - t)^{n+1}\,dt \tag{24}
\end{gather}
$$

Substituting step 24 into step 23:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}(x_0)}{(n + 1)!}(x - x_0)^{n+1} + R_{n+1}(x) \tag{25}
\end{gather}
$$

Substituting step 25 into the induction hypothesis of step 8:
$$
\begin{gather}
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + \frac{f^{(n+1)}(x_0)}{(n + 1)!}(x - x_0)^{n+1} + R_{n+1}(x) \tag{26}
\end{gather}
$$

Combining the $(n+1)$-th term into the summation in step 26:
$$
\begin{gather}
f(x) = \sum_{k=0}^{n+1} \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + R_{n+1}(x) \tag{27}
\end{gather}
$$

By the Principle of Mathematical Induction, the formula holds for all integers $n \ge 0$.

---
# Conclusion
First consider $x > x_0$, so that the interval of integration is $[x_0, x]$. 

Examine the remainder integral from step 9:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} \int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt \tag{28}
\end{gather}
$$

Define the weight function:
$$
\begin{gather}
g(t) := (x - t)^n \tag{29}
\end{gather}
$$

For all $t \in [x_0, x]$, the difference satisfies $x - t \ge 0$, and therefore:
$$
\begin{gather}
g(t) = (x - t)^n \ge 0 \quad \text{for all } t \in [x_0, x] \tag{30}
\end{gather}
$$
which ensures that $g$ does not change sign on $[x_0, x]$. 

Furthermore, $g$ is a polynomial in $t$ and therefore continuous on $[x_0, x]$, implying $g \in \mathcal{R}[x_0, x]$. By hypothesis, $f \in C^{n+1}[a, b]$, so $f^{(n+1)}$ is continuous on $[x_0, x]$.

Consequently, the hypotheses of the Generalized First Mean-Value Theorem for Integrals (Module 6, Chapter 2, [[Proof of the Generalized First Mean-Value Theorem for Integrals]]) are satisfied by $f^{(n+1)}$ and $g$ on $[x_0, x]$.

By the Generalized First Mean-Value Theorem for Integrals, there exists an intermediate point $\xi \in [x_0, x]$ such that:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}(\xi) \int_{x_0}^x (x - t)^n\,dt \tag{31}
\end{gather}
$$

By step 14, an antiderivative of $(x - t)^n$ with respect to $t$ is $-\frac{(x - t)^{n+1}}{n + 1}$. Applying the Newton-Leibniz Formula to the remaining integral in step 31:
$$
\begin{gather}
\int_{x_0}^x (x - t)^n\,dt = \left[ -\frac{(x - t)^{n+1}}{n + 1} \right]_{x_0}^x = 0 - \left( -\frac{(x - x_0)^{n+1}}{n + 1} \right) = \frac{(x - x_0)^{n+1}}{n + 1} \tag{32}
\end{gather}
$$

Substituting step 32 into step 31:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}(\xi) \frac{(x - x_0)^{n+1}}{n + 1} \tag{33}
\end{gather}
$$

Substituting step 33 into the remainder formula of step 28:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} \cdot f^{(n+1)}(\xi) \frac{(x - x_0)^{n+1}}{n + 1} = \frac{f^{(n+1)}(\xi)}{(n + 1)!}(x - x_0)^{n+1} \tag{34}
\end{gather}
$$

If $x < x_0$, the integration interval is $[x, x_0]$. By the orientation convention:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = -\int_x^{x_0} f^{(n+1)}(t)(x - t)^n\,dt \tag{35}
\end{gather}
$$
On $[x, x_0]$, $x - t \le 0$, so $(x - t)^n = (-1)^n (t - x)^n$. Factoring $(-1)^n$ preserves sign invariance. Applying the Generalized First Mean-Value Theorem on $[x, x_0]$ and re-evaluating the integral yields identical cancellation, producing step 34 for an intermediate node $\xi \in [x, x_0]$.

Parametrizing the intermediate point $\xi$ along the segment connecting $x_0$ and $x$ via:
$$
\begin{gather}
\xi = x_0 + \theta(x - x_0) \quad \text{for some } \theta \in [0, 1] \tag{36}
\end{gather}
$$
the remainder assumes the classical Lagrange form:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{(n + 1)!}(x - x_0)^{n+1} \tag{37}
\end{gather}
$$

**Part 4: Derivation of the Cauchy Remainder Form**

Examine the remainder integral of step 28 written in the product form:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} \int_{x_0}^x H(t) \cdot 1\,dt \tag{38}
\end{gather}
$$
where:
$$
\begin{gather}
H(t) := f^{(n+1)}(t)(x - t)^n \tag{39}
\end{gather}
$$

Because $f^{(n+1)}$ and $t \mapsto (x - t)^n$ are continuous on $[x_0, x]$, their product $H$ is continuous on $[x_0, x]$. The constant function $1$ is strictly positive and continuous on $[x_0, x]$.

Applying the First Mean-Value Theorem for Integrals (Continuous Form, Module 6, Chapter 2, [[Proof of the First Mean-Value Theorem for Integrals]]) to $H$ on the interval connecting $x_0$ and $x$:
$$
\begin{gather}
\int_{x_0}^x H(t)\,dt = H(\xi)(x - x_0) \quad \text{for some } \xi \text{ between } x_0 \text{ and } x \tag{40}
\end{gather}
$$

Substituting the definition of $H$ from step 39 into step 40:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}(\xi)(x - \xi)^n (x - x_0) \tag{41}
\end{gather}
$$

Parametrizing $\xi$ via $\xi = x_0 + \theta(x - x_0)$ with $\theta \in [0, 1]$:
$$
\begin{gather}
x - \xi = x - \big( x_0 + \theta(x - x_0) \big) = (1 - \theta)(x - x_0) \tag{42}
\end{gather}
$$

Substituting step 42 into step 41:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}\big(x_0 + \theta(x - x_0)\big) \big( (1 - \theta)(x - x_0) \big)^n (x - x_0) \tag{43}
\end{gather}
$$

Factoring powers of $(x - x_0)$ in step 43:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}\big(x_0 + \theta(x - x_0)\big) (1 - \theta)^n (x - x_0)^{n+1} \tag{44}
\end{gather}
$$

Substituting step 44 into the remainder formula of step 38:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{n!} (1 - \theta)^n (x - x_0)^{n+1} \tag{45}
\end{gather}
$$
which establishes the classical Cauchy remainder form.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
