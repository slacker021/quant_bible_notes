---
dg-publish: true
---
Let the domain of strictly positive real numbers be denoted by $\mathbb{R}_+ := (0, \infty)$. 

Define the continuous integrand function $g: \mathbb{R}_+ \to \mathbb{R}$ by:
$$
\begin{gather}
g(t) := \frac{1}{t} \tag{1}
\end{gather}
$$

For every $x \in \mathbb{R}_+$, the function $g$ is continuous on the compact interval connecting $1$ and $x$ (that is, $[1, x]$ if $x \ge 1$, or $[x, 1]$ if $0 < x < 1$). By the Integrability of Continuous Functions on Compact Intervals (Module 6, Chapter 1), $g$ is Riemann integrable on this interval.

Define the natural logarithm function $\ln: \mathbb{R}_+ \to \mathbb{R}$ as the variable upper limit integral:
$$
\begin{gather}
\ln x := \int_1^x \frac{dt}{t} \tag{2}
\end{gather}
$$
---
# Theorem 1
Evaluating the function at $x = 1$: by the orientation convention of the definite integral, the integral over an interval of zero length vanishes:
$$
\begin{gather}
\ln 1 = \int_1^1 \frac{dt}{t} = 0 \tag{3}
\end{gather}
$$

Because $g(t) = 1/t$ is continuous at every point $x \in \mathbb{R}_+$, the Theorem on Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral (Module 6, Chapter 3, [[Proof of Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral]]) establishes that $\ln$ is differentiable at every $x \in \mathbb{R}_+$, with first derivative:
$$
\begin{gather}
\frac{d}{dx} \ln x = g(x) = \frac{1}{x} \tag{4}
\end{gather}
$$

Because $x \in \mathbb{R}_+$, the evaluation of the derivative satisfies:
$$
\begin{gather}
\frac{d}{dx} \ln x = \frac{1}{x} > 0 \quad \text{for all } x \in (0, \infty) \tag{5}
\end{gather}
$$

By the Monotonicity Criterion of Differential Calculus (Module 5), a differentiable function with a strictly positive derivative on an open interval is strictly increasing. Therefore, $\ln$ is strictly increasing on $(0, \infty)$:
$$
\begin{gather}
0 < x_1 < x_2 \implies \ln x_1 < \ln x_2 \tag{6}
\end{gather}
$$

The first derivative function $\ln'(x) = x^{-1}$ is differentiable on $(0, \infty)$. Applying the Power Rule of Differentiation (Module 5):
$$
\begin{gather}
\frac{d^2}{dx^2} \ln x = \frac{d}{dx}\left( \frac{1}{x} \right) = -\frac{1}{x^2} \tag{7}
\end{gather}
$$

For every $x \in (0, \infty)$, $x^2 > 0$, and therefore:
$$
\begin{gather}
\frac{d^2}{dx^2} \ln x = -\frac{1}{x^2} < 0 \quad \text{for all } x \in (0, \infty) \tag{8}
\end{gather}
$$

By the Concavity Criterion of Differential Calculus (Module 5), a twice-differentiable function with a strictly negative second derivative on an interval is strictly concave. Therefore, $\ln$ is strictly concave on $(0, \infty)$.

---
# Theorem 2
Let $x, y \in (0, \infty)$ be arbitrary.

By definition of the natural logarithm in step 2:
$$
\begin{gather}
\ln(xy) = \int_1^{xy} \frac{dt}{t} \tag{9}
\end{gather}
$$

By the Generalized Orientation Additivity Formula (Module 6, Chapter 2, [[Proof of the Generalized Orientation Additivity Formula]]), decomposing the path of integration through the intermediate point $x \in (0, \infty)$ yields:
$$
\begin{gather}
\int_1^{xy} \frac{dt}{t} = \int_1^x \frac{dt}{t} + \int_x^{xy} \frac{dt}{t} \tag{10}
\end{gather}
$$

Substituting $\ln x = \int_1^x \frac{dt}{t}$ from step 2 into step 10:
$$
\begin{gather}
\ln(xy) = \ln x + \int_x^{xy} \frac{dt}{t} \tag{11}
\end{gather}
$$

Consider the definite integral:
$$
\begin{gather}
J := \int_x^{xy} \frac{dt}{t} \tag{12}
\end{gather}
$$

Define the coordinate transformation $\phi: [\min\{1, y\}, \max\{1, y\}] \to \mathbb{R}$ by:
$$
\begin{gather}
\phi(u) := xu \tag{13}
\end{gather}
$$

The mapping $\phi$ is continuously differentiable on its domain with derivative:
$$
\begin{gather}
\phi'(u) = x \tag{14}
\end{gather}
$$
and maps the boundary nodes according to:
$$
\begin{gather}
\phi(1) = x, \qquad \phi(y) = xy \tag{15}
\end{gather}
$$

The integrand $g(t) = 1/t$ is continuous on the compact image interval between $x$ and $xy$. 

Applying the Change of Variable Formula for Definite Integrals (Module 6, Chapter 3, [[Proof of the Change of Variable Formula for Definite Integrals]]) with transformation $t = \phi(u)$:
$$
\begin{gather}
\int_x^{xy} \frac{dt}{t} = \int_{\phi(1)}^{\phi(y)} \frac{dt}{t} = \int_1^y \frac{1}{\phi(u)} \phi'(u)\,du \tag{16}
\end{gather}
$$

Substituting $\phi(u) = xu$ from step 13 and $\phi'(u) = x$ from step 14 into step 16:
$$
\begin{gather}
\int_x^{xy} \frac{dt}{t} = \int_1^y \frac{1}{xu} \cdot x\,du \tag{17}
\end{gather}
$$

Because $x > 0$, the algebraic cancellation $\frac{x}{xu} = \frac{1}{u}$ holds identically on the entire domain of integration, reducing step 17 to:
$$
\begin{gather}
\int_x^{xy} \frac{dt}{t} = \int_1^y \frac{1}{u}\,du \tag{18}
\end{gather}
$$

By definition of the logarithm in step 2 with dummy variable $u$:
$$
\begin{gather}
\int_1^y \frac{1}{u}\,du = \ln y \tag{19}
\end{gather}
$$

Substituting step 18 and step 19 into step 11 yields the identity:
$$
\begin{gather}
\ln(xy) = \ln x + \ln y \tag{20}
\end{gather}
$$

Because step 20 holds for all $x, y \in (0, \infty)$, the natural logarithm is a group homomorphism from the multiplicative group $((0, \infty), \cdot)$ to the additive group $(\mathbb{R}, +)$.

---
# Theorem 3
Let $x \in (0, \infty)$. Applying step 20 to the product $x \cdot \frac{1}{x} = 1$:
$$
\begin{gather}
\ln\left( x \cdot \frac{1}{x} \right) = \ln x + \ln\left( \frac{1}{x} \right) \tag{21}
\end{gather}
$$

By step 3, $\ln(1) = 0$. Substituting this into step 21:
$$
\begin{gather}
\ln x + \ln\left( \frac{1}{x} \right) = 0 \tag{22}
\end{gather}
$$

Subtracting $\ln x$ from both sides of step 22 yields the reciprocal identity:
$$
\begin{gather}
\ln\left( \frac{1}{x} \right) = -\ln x \tag{23}
\end{gather}
$$

Now let $x, y \in (0, \infty)$. Expressing the quotient as a product $x/y = x \cdot (1/y)$ and applying step 20 and step 23:
$$
\begin{gather}
\ln\left( \frac{x}{y} \right) = \ln\left( x \cdot \frac{1}{y} \right) = \ln x + \ln\left( \frac{1}{y} \right) = \ln x - \ln y \tag{24}
\end{gather}
$$

Next consider the power identity $\ln(x^r) = r \ln x$. 

### Case 1
Proceed by mathematical induction on $n$. For $n = 1$, $\ln(x^1) = \ln x = 1 \cdot \ln x$, so the base case holds. Assume the formula holds for an integer $n \ge 1$, so that $\ln(x^n) = n \ln x$. By step 20:
$$
\begin{gather}
\ln(x^{n+1}) = \ln(x^n \cdot x) = \ln(x^n) + \ln x = n \ln x + \ln x = (n + 1)\ln x \tag{25}
\end{gather}
$$
By induction, $\ln(x^n) = n \ln x$ for all $n \in \mathbb{N}$.

### Case 2
If $m = 0$, $x^0 = 1$ and $\ln(x^0) = \ln 1 = 0 = 0 \cdot \ln x$. If $m = -n$ with $n \in \mathbb{N}$, then applying step 23 and Case 3A:
$$
\begin{gather}
\ln(x^{-n}) = \ln\left( \frac{1}{x^n} \right) = -\ln(x^n) = -n \ln x = m \ln x \tag{26}
\end{gather}
$$
Thus $\ln(x^m) = m \ln x$ for all $m \in \mathbb{Z}$.

### Case 3
Let $u := x^{p/q} \in (0, \infty)$. Taking the $q$-th power yields $u^q = (x^{p/q})^q = x^p$. 
Applying Case 3A to $u^q$ and Case 3B to $x^p$:
$$
\begin{gather}
\ln(u^q) = q \ln u, \qquad \ln(x^p) = p \ln x \tag{27}
\end{gather}
$$
Equating the two expressions in step 27 gives:
$$
\begin{gather}
q \ln u = p \ln x \implies \ln u = \frac{p}{q} \ln x \tag{28}
\end{gather}
$$
Substituting $u = x^{p/q} = x^r$ into step 28 proves:
$$
\begin{gather}
\ln(x^r) = r \ln x \quad \text{for all } r \in \mathbb{Q} \tag{29}
\end{gather}
$$

### Case 4
For any arbitrary real number $r \in \mathbb{R}$ and $x > 0$, the general power is analytically defined by $x^r := \exp(r \ln x)$ (where $\exp := \ln^{-1}$ as established in Part 5). Applying $\ln$ to both sides and using $\ln(\exp(y)) = y$ yields:
$$
\begin{gather}
\ln(x^r) = \ln\big( \exp(r \ln x) \big) = r \ln x \tag{30}
\end{gather}
$$

---
# Theorem 4
Consider the evaluation of $\ln 2$:
$$
\begin{gather}
\ln 2 = \int_1^2 \frac{dt}{t} \tag{31}
\end{gather}
$$

For all $t \in [1, 2]$, the inequality $t \le 2$ implies:
$$
\begin{gather}
\frac{1}{t} \ge \frac{1}{2} \tag{32}
\end{gather}
$$

Applying Order Monotonicity of the Riemann Integral (Module 6, Chapter 2, [[Proof of Monotonicity and the Absolute Value Integral Inequality]]) to step 32 across $[1, 2]$:
$$
\begin{gather}
\ln 2 = \int_1^2 \frac{dt}{t} \ge \int_1^2 \frac{1}{2}\,dt = \frac{1}{2}(2 - 1) = \frac{1}{2} > 0 \tag{33}
\end{gather}
$$

For any integer $k \in \mathbb{N}$, evaluating $\ln(2^k)$ via step 25 and step 33:
$$
\begin{gather}
\ln(2^k) = k \ln 2 \ge \frac{k}{2} \tag{34}
\end{gather}
$$

Now establish that $\lim_{x \to \infty} \ln x = \infty$.

Let $M > 0$ be an arbitrary positive real bound. By the Archimedean Property of the real numbers, choose a positive integer $K \in \mathbb{N}$ such that $K > 2M$. Define $X_M := 2^K$. 

For all $x > X_M$, the strict monotonicity of $\ln$ established in step 6 and step 34 implies:
$$
\begin{gather}
\ln x > \ln(2^K) \ge \frac{K}{2} > \frac{2M}{2} = M \tag{35}
\end{gather}
$$

Because $M > 0$ was arbitrary, step 35 proves:
$$
\begin{gather}
\lim_{x \to \infty} \ln x = \infty \tag{36}
\end{gather}
$$

Next establish that $\lim_{x \to 0^+} \ln x = -\infty$.

Let $x \to 0^+$. Define the substitution variable $s := 1/x$. As $x \to 0^+$, $s \to \infty$. 

Using the reciprocal identity of step 23:
$$
\begin{gather}
\lim_{x \to 0^+} \ln x = \lim_{s \to \infty} \ln\left( \frac{1}{s} \right) = \lim_{s \to \infty} (-\ln s) = -\lim_{s \to \infty} \ln s \tag{37}
\end{gather}
$$

Substituting the limit of step 36 into step 37:
$$
\begin{gather}
\lim_{x \to 0^+} \ln x = -\infty \tag{38}
\end{gather}
$$

Now establish bijectivity:
1. *Injectivity:* By step 6, $\ln$ is strictly increasing on $(0, \infty)$. For any $x_1, x_2 \in (0, \infty)$ with $x_1 \neq x_2$, either $x_1 < x_2 \implies \ln x_1 < \ln x_2$, or $x_2 < x_1 \implies \ln x_2 < \ln x_1$. In either case, $\ln x_1 \neq \ln x_2$. Thus $\ln$ is strictly injective.
2. *Surjectivity:* By step 4, $\ln$ is differentiable on $(0, \infty)$, which implies that $\ln$ is continuous on $(0, \infty)$. Let $y \in \mathbb{R}$ be an arbitrary real number. 
By step 38, there exists $x_1 \in (0, \infty)$ such that $\ln x_1 < y$. 
By step 36, there exists $x_2 \in (0, \infty)$ such that $\ln x_2 > y$. 

Because $x_1 < x_2$, the function $\ln$ is continuous on the compact interval $[x_1, x_2]$, and $y$ satisfies $\ln x_1 < y < \ln x_2$.

By the Intermediate Value Theorem (Bolzano-Cauchy Theorem, Module 5), there exists a point $x^* \in (x_1, x_2) \subset (0, \infty)$ such that:
$$
\begin{gather}
\ln x^* = y \tag{39}
\end{gather}
$$
Because $y \in \mathbb{R}$ was arbitrary, every real number belongs to the image of $\ln$. Thus $\ln((0, \infty)) = \mathbb{R}$, establishing that $\ln$ is surjective.

Combining injectivity and surjectivity, the mapping $\ln: (0, \infty) \to \mathbb{R}$ is a bijection.

---
# Theorem 5
Because $\ln: (0, \infty) \to \mathbb{R}$ is a strictly increasing, continuous bijection, it possesses a unique global inverse function:
$$
\begin{gather}
\exp := \ln^{-1}: \mathbb{R} \to (0, \infty) \tag{40}
\end{gather}
$$
satisfying:
$$
\begin{gather}
\exp(y) = x \iff \ln x = y \tag{41}
\end{gather}
$$

By the Inverse Function Theorem (Module 5), because $\ln$ is differentiable on $(0, \infty)$ with non-vanishing derivative $\ln'(x) = 1/x \neq 0$ for all $x \in (0, \infty)$, the inverse function $\exp$ is differentiable at every $y \in \mathbb{R}$, and its derivative is given by:
$$
\begin{gather}
\exp'(y) = \frac{1}{\ln'(\exp(y))} \tag{42}
\end{gather}
$$

Substituting $\ln'(t) = 1/t$ with $t = \exp(y)$ into step 42:
$$
\begin{gather}
\exp'(y) = \frac{1}{\frac{1}{\exp(y)}} = \exp(y) \tag{43}
\end{gather}
$$

Relabeling the independent variable as $x$:
$$
\begin{gather}
\frac{d}{dx} \exp(x) = \exp(x) \quad \text{for all } x \in \mathbb{R} \tag{44}
\end{gather}
$$

Because $\ln 1 = 0$ by step 3, evaluating step 41 at $x = 1$ gives:
$$
\begin{gather}
\exp(0) = 1 \tag{45}
\end{gather}
$$

Because $\ln: (0, \infty) \to \mathbb{R}$ is bijective, there exists a unique real number $e \in (0, \infty)$ such that:
$$
\begin{gather}
\ln e = 1 \tag{46}
\end{gather}
$$
which implies by step 41:
$$
\begin{gather}
e = \exp(1) \tag{47}
\end{gather}
$$

For any base $a > 0$ with $a \neq 1$, define the general exponential function $a^x: \mathbb{R} \to (0, \infty)$ by:
$$
\begin{gather}
a^x := \exp(x \ln a) \tag{48}
\end{gather}
$$

The general logarithm to base $a$, denoted $\log_a: (0, \infty) \to \mathbb{R}$, is defined as the inverse of $x \mapsto a^x$. Let $y = \log_a x$. Then:
$$
\begin{gather}
a^y = x \iff \exp(y \ln a) = x \tag{49}
\end{gather}
$$

Applying the natural logarithm $\ln$ to both sides of step 49:
$$
\begin{gather}
\ln\big( \exp(y \ln a) \big) = \ln x \implies y \ln a = \ln x \tag{50}
\end{gather}
$$

Because $a \neq 1$, step 3 and step 6 imply $\ln a \neq 0$. Dividing step 50 by $\ln a$ yields:
$$
\begin{gather}
\log_a x = y = \frac{\ln x}{\ln a} \tag{51}
\end{gather}
$$
which completes the derivation of all structural and analytic properties.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
