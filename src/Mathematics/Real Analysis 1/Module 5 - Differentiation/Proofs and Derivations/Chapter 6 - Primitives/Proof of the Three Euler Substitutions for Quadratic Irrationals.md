---
dg-publish: true
---
Let $a, b, c \in \mathbb{R}$ with $a \neq 0$ and non-vanishing discriminant $\Delta = b^2 - 4ac \neq 0$. Let $y = \sqrt{a x^2 + b x + c}$ be real-valued on an open interval $J \subset \mathbb{R}$ where $a x^2 + b x + c > 0$. The equation:
$$
\begin{gather}
y^2 = a x^2 + b x + c \tag{1}
\end{gather}
$$
defines an algebraic curve of degree two (a non-degenerate conic section) in the $(x, y)$-plane. 

Because any non-degenerate conic section containing at least one real point is birationally equivalent to the projective line $\mathbb{P}^1(\mathbb{R})$ via stereographic projection or secant pencils, the curve admits a rational parameterization $x = \Phi(t), y = \Psi(t)$ with $\Phi, \Psi \in \mathbb{R}(t)$. Consequently, for any rational function $R(x, y)$, the differential form $R(x, y) \, dx$ transforms into a purely rational differential form $R(\Phi(t), \Psi(t)) \Phi'(t) \, dt \in \mathbb{R}(t) \, dt$.

---
# Proposition 1
Assume $a > 0$. Under this condition, the conic section of step 1 is a hyperbola whose asymptotes have slopes $\pm \sqrt{a}$. Define the auxiliary variable $t$ through the First Euler Substitution:
$$
\begin{gather}
\sqrt{a x^2 + b x + c} = \pm \sqrt{a} x + t \tag{2}
\end{gather}
$$
Squaring both sides of step 2 eliminates the radical:
$$
\begin{gather}
a x^2 + b x + c = \left( \pm \sqrt{a} x + t \right)^2 = a x^2 \pm 2\sqrt{a} x t + t^2 \tag{3}
\end{gather}
$$
Subtracting $a x^2$ from both sides of step 3 produces an equation linear in the variable $x$:
$$
\begin{gather}
b x + c = \pm 2\sqrt{a} x t + t^2 \tag{4}
\end{gather}
$$
Regrouping terms containing $x$ yields:
$$
\begin{gather}
x \big(b \mp 2\sqrt{a} t\big) = t^2 - c \tag{5}
\end{gather}
$$
Isolating $x$ provides the rational parameterization:
$$
\begin{gather}
x = \frac{t^2 - c}{b \mp 2\sqrt{a} t} \tag{6}
\end{gather}
$$
Substituting the rational expression for $x$ back into the substitution of step 2 demonstrates that $y = \sqrt{a x^2 + b x + c}$ is also rational in $t$:
$$
\begin{gather}
y = \pm \sqrt{a} \left(\frac{t^2 - c}{b \mp 2\sqrt{a} t}\right) + t = \frac{\pm \sqrt{a}(t^2 - c) + bt \mp 2\sqrt{a}t^2}{b \mp 2\sqrt{a} t} = \frac{\mp \sqrt{a} t^2 + bt \mp \sqrt{a} c}{b \mp 2\sqrt{a} t} \tag{7}
\end{gather}
$$
Differentiating the rational expression in step 6 with respect to $t$ via the quotient rule yields:
$$
\begin{gather}
\frac{dx}{dt} = \frac{2t (b \mp 2\sqrt{a} t) - (t^2 - c)(\mp 2\sqrt{a})}{(b \mp 2\sqrt{a} t)^2} = \frac{2 b t \mp 4\sqrt{a} t^2 \pm 2\sqrt{a} t^2 \mp 2\sqrt{a} c}{(b \mp 2\sqrt{a} t)^2} = 2 \frac{\mp \sqrt{a} t^2 + bt \mp c\sqrt{a}}{(b \mp 2\sqrt{a} t)^2} \tag{8}
\end{gather}
$$
Consequently, the differential transforms as $dx = \Phi'(t) \, dt$ with $\Phi'(t) \in \mathbb{R}(t)$, rendering $R(x, y) \, dx$ entirely rational in $t$.

---
# Proposition 2
Assume $c > 0$. The curve $y^2 = a x^2 + b x + c$ possesses real intercepts with the vertical axis at $(0, \pm \sqrt{c})$. Define the pencil of lines passing through the point $(0, \pm \sqrt{c})$ with variable slope $t$ via the Second Euler Substitution:
$$
\begin{gather}
\sqrt{a x^2 + b x + c} = x t \pm \sqrt{c} \tag{9}
\end{gather}
$$
Squaring both sides of step 9 eliminates the radical:
$$
\begin{gather}
a x^2 + b x + c = (x t \pm \sqrt{c})^2 = x^2 t^2 \pm 2\sqrt{c} x t + c \tag{10}
\end{gather}
$$
Subtracting the constant term $c$ from both sides produces:
$$
\begin{gather}
a x^2 + b x = x^2 t^2 \pm 2\sqrt{c} x t \tag{11}
\end{gather}
$$
For $x \neq 0$, dividing both sides of step 11 by $x$ reduces the quadratic relation to a linear equation in $x$:
$$
\begin{gather}
a x + b = x t^2 \pm 2\sqrt{c} t \tag{12}
\end{gather}
$$
Regrouping terms yields:
$$
\begin{gather}
x (a - t^2) = \pm 2\sqrt{c} t - b \tag{13}
\end{gather}
$$
Isolating $x$ gives the rational function:
$$
\begin{gather}
x = \frac{\pm 2\sqrt{c} t - b}{a - t^2} \tag{14}
\end{gather}
$$
Substituting step 14 into step 9 demonstrates that $y = \sqrt{a x^2 + b x + c}$ is a rational function of $t$:
$$
\begin{gather}
y = t \left(\frac{\pm 2\sqrt{c} t - b}{a - t^2}\right) \pm \sqrt{c} = \frac{\pm 2\sqrt{c} t^2 - bt \pm a\sqrt{c} \mp \sqrt{c} t^2}{a - t^2} = \frac{\pm \sqrt{c} t^2 - bt \pm a\sqrt{c}}{a - t^2} \tag{15}
\end{gather}
$$
Differentiating step 14 with respect to $t$ gives:
$$
\begin{gather}
\frac{dx}{dt} = \frac{(\pm 2\sqrt{c})(a - t^2) - (\pm 2\sqrt{c} t - b)(-2t)}{(a - t^2)^2} = \frac{\pm 2a\sqrt{c} \mp 2\sqrt{c} t^2 \pm 4\sqrt{c} t^2 - 2bt}{(a - t^2)^2} = 2 \frac{\pm \sqrt{c} t^2 - bt \pm a\sqrt{c}}{(a - t^2)^2} \tag{16}
\end{gather}
$$
This establishes that $x, y$, and $dx$ are completely rational in $t$.

---
# Proposition 3
Assume that the quadratic polynomial $a x^2 + b x + c$ possesses real roots $x_1, x_2 \in \mathbb{R}$ with $x_1 \neq x_2$, so that it factors as $a(x - x_1)(x - x_2)$. This condition encompasses the case where $a < 0$ and the radicand is positive on the interval $(x_1, x_2)$ (or $(x_2, x_1)$).

Define the Third Euler Substitution by setting:
$$
\begin{gather}
\sqrt{a(x - x_1)(x - x_2)} = t (x - x_1) \tag{17}
\end{gather}
$$
Squaring both sides of step 17 yields:
$$
\begin{gather}
a (x - x_1)(x - x_2) = t^2 (x - x_1)^2 \tag{18}
\end{gather}
$$
For $x \neq x_1$, divide both sides of step 18 by the common factor $(x - x_1)$:
$$
\begin{gather}
a (x - x_2) = t^2 (x - x_1) \tag{19}
\end{gather}
$$
Expanding and collecting terms containing $x$ produces:
$$
\begin{gather}
a x - a x_2 = x t^2 - x_1 t^2 \iff x (a - t^2) = a x_2 - x_1 t^2 \tag{20}
\end{gather}
$$
Isolating $x$ establishes the rational representation:
$$
\begin{gather}
x = \frac{a x_2 - x_1 t^2}{a - t^2} \tag{21}
\end{gather}
$$
Subtracting $x_1$ from both sides of step 21 yields:
$$
\begin{gather}
x - x_1 = \frac{a x_2 - x_1 t^2 - x_1(a - t^2)}{a - t^2} = \frac{a(x_2 - x_1)}{a - t^2} \tag{22}
\end{gather}
$$
Substituting step 22 back into the radical expression of step 17 shows:
$$
\begin{gather}
y = t (x - x_1) = \frac{a(x_2 - x_1) t}{a - t^2} \tag{23}
\end{gather}
$$
Differentiating step 21 with respect to $t$ produces:
$$
\begin{gather}
\frac{dx}{dt} = \frac{(-2x_1 t)(a - t^2) - (a x_2 - x_1 t^2)(-2t)}{(a - t^2)^2} = \frac{-2a x_1 t + 2x_1 t^3 + 2a x_2 t - 2x_1 t^3}{(a - t^2)^2} = \frac{2a(x_2 - x_1)t}{(a - t^2)^2} \tag{24}
\end{gather}
$$
Thus, $x, y,$ and $dx$ are represented as rational functions of $t$.

Because every real quadratic polynomial with non-zero discriminant satisfies $a > 0$, $c > 0$, or factors into real linear factors (since if $a < 0$ and $c < 0$, positivity of the radicand requires $b^2 - 4ac > 0$, ensuring real roots), at least one of the three Euler substitutions is always applicable, guaranteeing the rationalization of $\int R(x, \sqrt{a x^2 + b x + c}) \, dx$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
