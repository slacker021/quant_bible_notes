---
dg-publish: true
---
Consider the quadratic radical $y = \sqrt{a x^2 + b x + c}$ where $a, b, c \in \mathbb{R}$ and $a x^2 + b x + c > 0$ on an interval.

We prove that in each of the three geometric configurations, the algebraic curve $y^2 = a x^2 + b x + c$ is birationally equivalent to a line, allowing $x$ and $y$ to be expressed as rational functions of a parameter $t$.

### Case 1: First Euler Substitution ($a > 0$)
Let $a > 0$. Set:
$$
\begin{gather}
\sqrt{a x^2 + b x + c} = \sqrt{a} x + t \tag{1}
\end{gather}
$$

Squaring both sides of the equation of step 1:
$$
\begin{gather}
a x^2 + b x + c = (\sqrt{a} x + t)^2 = a x^2 + 2\sqrt{a} x t + t^2 \tag{2}
\end{gather}
$$

Subtracting $a x^2$ from both sides eliminates the quadratic term:
$$
\begin{gather}
b x + c = 2\sqrt{a} x t + t^2 \tag{3}
\end{gather}
$$

Rearranging to solve for $x$:
$$
\begin{gather}
x(b - 2\sqrt{a} t) = t^2 - c \implies x = \frac{t^2 - c}{b - 2\sqrt{a} t} \tag{4}
\end{gather}
$$

Because $x$ is a rational function of $t$, the derivative $\frac{dx}{dt}$ is a rational function of $t$, and:
$$
\begin{gather}
\sqrt{a x^2 + b x + c} = \sqrt{a} \left( \frac{t^2 - c}{b - 2\sqrt{a} t} \right) + t \tag{5}
\end{gather}
$$
is also a rational function of $t$. Thus, the integrand $R(x, \sqrt{ax^2+bx+c})dx$ transforms into a rational fraction of $t$.

### Case 2: Second Euler Substitution ($c > 0$)
Let $c > 0$. Set:
$$
\begin{gather}
\sqrt{a x^2 + b x + c} = x t + \sqrt{c} \tag{6}
\end{gather}
$$

Squaring both sides of the equation of step 6:
$$
\begin{gather}
a x^2 + b x + c = x^2 t^2 + 2\sqrt{c} x t + c \tag{7}
\end{gather}
$$

Subtracting $c$ and dividing by $x \neq 0$:
$$
\begin{gather}
a x + b = x t^2 + 2\sqrt{c} t \tag{8}
\end{gather}
$$

Solving for $x$:
$$
\begin{gather}
x(a - t^2) = 2\sqrt{c} t - b \implies x = \frac{2\sqrt{c} t - b}{a - t^2} \tag{9}
\end{gather}
$$
which expresses $x$, $dx$, and $y = xt + \sqrt{c}$ rationally in terms of $t$.

### Case 3: Third Euler Substitution ($b^2 - 4ac > 0$)
Let $x_1, x_2 \in \mathbb{R}$ be distinct real roots of $a x^2 + b x + c = 0$. Then:
$$
\begin{gather}
a x^2 + b x + c = a(x - x_1)(x - x_2) \tag{10}
\end{gather}
$$

Set:
$$
\begin{gather}
\sqrt{a(x - x_1)(x - x_2)} = (x - x_1) t \tag{11}
\end{gather}
$$

Squaring both sides:
$$
\begin{gather}
a(x - x_1)(x - x_2) = (x - x_1)^2 t^2 \tag{12}
\end{gather}
$$

Dividing by $x - x_1 \neq 0$:
$$
\begin{gather}
a(x - x_2) = (x - x_1) t^2 \tag{13}
\end{gather}
$$

Solving for $x$:
$$
\begin{gather}
a x - a x_2 = x t^2 - x_1 t^2 \implies x(a - t^2) = a x_2 - x_1 t^2 \implies x = \frac{a x_2 - x_1 t^2}{a - t^2} \tag{14}
\end{gather}
$$
which rationalizes $x$, $dx$, and the radical $y = (x - x_1)t$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
