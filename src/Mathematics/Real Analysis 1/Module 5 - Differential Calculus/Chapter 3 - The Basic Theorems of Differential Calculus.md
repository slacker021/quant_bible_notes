---
dg-publish: true
---
# The Basic Theorems of Differential Calculus

While the derivative is defined through a purely local limit at an isolated point $x_0$, the true mathematical power of differential calculus emerges when differentiability holds across an entire interval. Under the governance of domain connectedness and topological compactness, local differential information ($f'(x)$) integrates into global conclusions regarding the growth, constancy, oscillation, and range of the function.

This chapter establishes the core foundational theorems of differential calculus—Fermat's Stationary Point Lemma, Rolle's Theorem, the Finite Increments Theorems of Lagrange and Cauchy, Darboux's Theorem, and Taylor's Theorem—grounded strictly upon the topological machinery of the real continuum developed in Modules 2, 3, and 4.

---

# Local Extrema and Fermat's Stationary Point Lemma

### Definition of Local Extrema
Let $E \subseteq \mathbb{R}$ and let $f: E \to \mathbb{R}$.

$$\begin{gather}
\textbf{Definition: Local Extrema} \\[5mm]
\text{1. The function } f \text{ has a local maximum at } x_0 \in E \text{ if there exists a neighborhood } U(x_0) \text{ such that:} \\[2mm]
f(x) \le f(x_0) \quad \forall x \in U(x_0) \cap E. \\[3mm]
\text{2. The function } f \text{ has a local minimum at } x_0 \in E \text{ if there exists a neighborhood } U(x_0) \text{ such that:} \\[2mm]
f(x) \ge f(x_0) \quad \forall x \in U(x_0) \cap E.
\end{gather}$$
If the strict inequalities $f(x) < f(x_0)$ (resp. $f(x) > f(x_0)$) hold for all $x \in \mathring{U}(x_0) \cap E$, the point $x_0$ is a *strict local extremum*.

### Fermat's Stationary Point Lemma
$$\begin{gather}
\textbf{Theorem: Fermat's Stationary Point Lemma} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(E), \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{If } f \text{ has a local extremum at } x_0 \text{ and } f \text{ is differentiable at } x_0, \text{ then the derivative vanishes:} \\[3.5mm]
f'(x_0) = 0.
\end{gather}$$
(see [[Proof of Fermat's Stationary Point Lemma]])

>[!danger]+ Intuition: The Horizontal Tangent at Extremal Turning Points
>If $f'(x_0) > 0$, the linear approximation $\Delta f \approx f'(x_0)h$ forces $f(x_0 + h) > f(x_0)$ for positive $h$ and $f(x_0 + h) < f(x_0)$ for negative $h$, precluding any maximum or minimum. An interior extremum requires that the linear drift vanishes entirely ($f'(x_0) = 0$), leaving higher-order curvature terms to determine the turning point.

### Taxonomy of Critical Points and the Closed Interval Protocol
A point $c \in \text{int}(E)$ where $f'(c) = 0$ is termed a **stationary point**. 

Fermat's condition is a necessary, but not sufficient, condition for an extremum:
- The function $f(x) = x^3$ has $f'(0) = 0$, yet $x = 0$ is an inflection point, not a local extremum.
- The function $f(x) = |x|$ attains a strict global minimum at $x = 0$, but $f'(0)$ does not exist.

$$\begin{gather}
\textbf{Definition: Critical Numbers} \\[5mm]
\text{Let } f: I \to \mathbb{R}. \text{ A point } c \in \text{int}(I) \text{ is a critical number of } f \text{ if either:} \\[2mm]
f'(c) = 0 \quad (\text{stationary point}), \quad \text{or} \quad f'(c) \text{ does not exist} \quad (\text{singular point}).
\end{gather}$$

By combining Fermat's Stationary Point Lemma with the Weierstrass Extreme Value Theorem (Module 4), the search for global extrema on compact intervals is reduced to a finite algorithmic evaluation:

$$\begin{gather}
\textbf{Theorem: The Closed Interval Method} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be continuous on the compact interval } [a, b], \text{ and differentiable on } (a, b) \setminus \Sigma, \\[2mm]
\text{where } \Sigma \subset (a, b) \text{ is a finite set of singular points. Then } f \text{ attains its absolute maximum and minimum} \\[2mm]
\text{on } [a, b], \text{ and these absolute extrema belong exclusively to the set:} \\[3.5mm]
S = \{a, b\} \cup \{c \in (a, b) : f'(c) = 0\} \cup \Sigma.
\end{gather}$$

---

# Rolle's Theorem

$$\begin{gather}
\textbf{Theorem: Rolle's Theorem} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be continuous on the closed interval } [a, b] \text{ and differentiable on the open interval } (a, b). \\[2mm]
\text{If } f(a) = f(b), \text{ then there exists at least one intermediate point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
f'(\xi) = 0.
\end{gather}$$
(see [[Proof of Rolle's Theorem]])

Every condition in Rolle's Theorem is mathematically essential:
1. **Failure of Boundary Equality**: $f(x) = x$ on $[0, 1]$ has $f'(x) \equiv 1 \neq 0$.
2. **Failure of Interior Differentiability**: $f(x) = 1 - |x|$ on $[-1, 1]$ satisfies $f(-1) = f(1) = 0$, but $f'(x) = \pm 1$ never vanishes because differentiability fails at $x = 0$.
3. **Failure of Compact Boundary Continuity**: $f(x) = x$ for $x \in [0, 1)$ with $f(1) = 0$ satisfies $f(0) = f(1) = 0$, but lacks continuity at $x = 1$; its derivative $f'(x) \equiv 1$ never vanishes.

### Algebraic Corollary: Interlacing of Polynomial Roots
$$\begin{gather}
\textbf{Corollary: Interlacing of Real Roots} \\[5mm]
\text{Let } P(x) \in \mathbb{R}[x] \text{ be a real polynomial. Between any two distinct real roots of } P(x), \\[2mm]
\text{there lies at least one real root of its derivative } P'(x). \\[2mm]
\text{Consequently, if } P(x) \text{ has } k \text{ distinct real roots, } P'(x) \text{ has at least } k - 1 \text{ real roots.}
\end{gather}$$

---

# The Finite Increments Theorems: Lagrange and Cauchy

### Lagrange's Mean Value Theorem
By applying an affine shear transformation to reduce a general secant chord to the horizontal baseline of Rolle's Theorem, one obtains the celebrated **Finite Increments Theorem** of Joseph-Louis Lagrange:

$$\begin{gather}
\textbf{Theorem: Lagrange’s Mean Value Theorem} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be continuous on } [a, b] \text{ and differentiable on } (a, b). \\[2mm]
\text{Then there exists at least one intermediate point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
f(b) - f(a) = f'(\xi)(b - a), \quad \text{or equivalently} \quad \frac{f(b) - f(a)}{b - a} = f'(\xi).
\end{gather}$$
(see [[Proof of the Lagrange Mean Value Theorem]])

```easy-tikz
title $\text{Lagrange Mean Value Theorem: Parallel Tangent and Secant}$
xlabel $x$
ylabel $y$
show x from 0 to 8 and y from 0 to 6
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 1.2*x - 0.12*x^2, from x = 1.0 to 7.0, in teal, very thick
draw a segment from (1.5, 2.53) to (6.5, 3.73), in blue, thick
draw a line from (1.0, 3.43) to (7.0, 4.87), in red, dashed
draw a segment from (1.5, 0.2) to (1.5, 2.53), in gray, dotted
draw a segment from (6.5, 0.2) to (6.5, 3.73), in gray, dotted
draw a segment from (4.0, 0.2) to (4.0, 3.88), in purple, dotted
mark (1.5, 2.53), in blue, large
mark (6.5, 3.73), in blue, large
mark (4.0, 3.88), in red, large
write "$A(a, f(a))$" at (1.45, 2.85), in blue, left
write "$B(b, f(b))$" at (6.55, 3.5), in blue, right
write "$P(\xi, f(\xi))$" at (4.0, 4.2), in red, above
write "$\text{Secant Slope } \frac{f(b)-f(a)}{b-a}$" at (3.2, 2.7), in blue, below
write "$\text{Parallel Tangent Line } y - f(\xi) = f'(\xi)(x - \xi)$" at (4.5, 5.2), in red, right
write "$a$" at (1.5, 0.0), in black, below
write "$\xi$" at (4.0, 0.0), in purple, below
write "$b$" at (6.5, 0.0), in black, below
```

Setting $b = x_0 + h$ and $a = x_0$, the intermediate point can be parameterized as $\xi = x_0 + \theta h$ with $\theta \in (0, 1)$, yielding the **finite increment formula**:
$$\Delta f(x_0; h) = f'(x_0 + \theta h) h \tag{1}$$

### Fundamental Global Consequences
$$\begin{gather}
\textbf{Theorem: The Constancy and Monotonicity Criteria} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be continuous on an interval } I \subseteq \mathbb{R} \text{ and differentiable on } \text{int}(I). \\[3mm]
\begin{align}
\text{1. Constancy:} \quad &f'(x) = 0 \ \forall x \in \text{int}(I) \iff f(x) \equiv C \text{ on } I \text{ for some constant } C \in \mathbb{R}. \\[2mm]
\text{2. Monotonicity:} \quad &f'(x) \ge 0 \ \forall x \in \text{int}(I) \iff f \text{ is non-decreasing on } I. \\[2mm]
&f'(x) \le 0 \ \forall x \in \text{int}(I) \iff f \text{ is non-increasing on } I. \\[2mm]
\text{3. Strict Monotonicity:} \quad &f'(x) > 0 \ \forall x \in \text{int}(I) \implies f \text{ is strictly increasing on } I.
\end{align}
\end{gather}$$
(see [[Proof of the Constancy and Monotonicity Criteria]])

$$\begin{gather}
\textbf{Corollary: Interval Uniqueness of Primitives} \\[5mm]
\text{Let } F_1, F_2: I \to \mathbb{R} \text{ be differentiable functions on an interval } I. \\[2mm]
\text{If } F_1'(x) = F_2'(x) \text{ for all } x \in I, \text{ then there exists a constant } C \in \mathbb{R} \text{ such that:} \\[3.5mm]
F_1(x) = F_2(x) + C \quad \forall x \in I.
\end{gather}$$

Notice that interval connectedness is mandatory: if the domain $E = (0, 1) \cup (2, 3)$ is disconnected, a function whose derivative vanishes identically may take independent constant values on each component.

### Cauchy's Generalized Mean Value Theorem
$$\begin{gather}
\textbf{Theorem: Cauchy’s Generalized Mean Value Theorem} \\[5mm]
\text{Let } f, g: [a, b] \to \mathbb{R} \text{ be continuous on } [a, b] \text{ and differentiable on } (a, b). \\[2mm]
\text{If } g'(x) \neq 0 \text{ for all } x \in (a, b), \text{ then } g(b) \neq g(a), \text{ and there exists } \xi \in (a, b) \text{ such that:} \\[3.5mm]
\frac{f(b) - f(a)}{g(b) - g(a)} = \frac{f'(\xi)}{g'(\xi)}.
\end{gather}$$
(see [[Proof of the Cauchy Generalized Mean Value Theorem]])

Lagrange's Theorem is the special case of Cauchy's Theorem corresponding to the identity function $g(x) = x$. Cauchy's generalized formula is the indispensable analytical engine used to prove L'Hôpital's Rule and to construct the remainder term in Taylor's Theorem.

---

# Darboux's Intermediate Value Theorem for Derivatives

A continuous function satisfies the Intermediate Value Property (Bolzano-Cauchy Theorem, Module 4). Remarkably, Jean-Gaston Darboux discovered that *every derivative* satisfies the intermediate value property, even if the derivative function $f'$ is everywhere discontinuous:

$$\begin{gather}
\textbf{Theorem: Darboux’s Intermediate Value Theorem for Derivatives} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be differentiable on } [a, b]. \\[2mm]
\text{If } \gamma \in \mathbb{R} \text{ lies strictly between } f'(a) \text{ and } f'(b) \text{ (i.e., } f'(a) < \gamma < f'(b) \text{ or } f'(b) < \gamma < f'(a)\text{)}, \\[2mm]
\text{then there exists at least one intermediate point } c \in (a, b) \text{ such that:} \\[3.5mm]
f'(c) = \gamma. \\[3.5mm]
\text{In topological terms: if } I \subseteq \mathbb{R} \text{ is an interval, the direct image } f'(I) \text{ is an interval.}
\end{gather}$$
(see [[Proof of Darboux's Intermediate Value Theorem for Derivatives]])

$$\begin{gather}
\textbf{Theorem: Classification of Discontinuities of Derivatives} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be differentiable on an open interval } I. \\[2mm]
\text{The derivative function } f': I \to \mathbb{R} \text{ cannot possess jump discontinuities (discontinuities of the first kind)} \\[2mm]
\text{or removable discontinuities at any point of } I. \\[2mm]
\text{Every point of discontinuity of } f' \text{ is an essential discontinuity (discontinuity of the second kind).}
\end{gather}$$
(see [[Proof of the Discontinuity Classification of Derivatives]])

>[!example]- Archetype: Differentiable Function with an Everywhere Discontinuous Derivative
>Define the classical oscillatory function:
>$$f(x) = \begin{cases} x^2 \sin(1/x), & x \neq 0 \\ 0, & x = 0 \end{cases} \tag{2}$$
>For $x \neq 0$, the standard product and chain rules yield:
>$$f'(x) = 2x \sin(1/x) - \cos(1/x) \tag{3}$$
>At the origin $x = 0$, evaluating the difference quotient limit directly from the definition of differentiability at a point:
>$$f'(0) = \lim_{h \to 0} \frac{h^2 \sin(1/h) - 0}{h} = \lim_{h \to 0} h \sin(1/h) = 0 \tag{4}$$
>Thus $f'(x)$ exists for all $x \in \mathbb{R}$. However, as $x \to 0$, $2x \sin(1/x) \to 0$ while $-\cos(1/x)$ oscillates densely across $[-1, 1]$. Consequently, $\lim_{x \to 0} f'(x)$ does not exist. The derivative $f'$ is discontinuous at $x = 0$, yet in every neighborhood $(-\delta, \delta)$, $f'((-\delta, \delta))$ maps onto $[-1, 1]$, perfectly satisfying Darboux's theorem.

---

# The Landau-Kolmogorov Derivative Inequality

In approximation theory and functional analysis, bounding intermediate derivatives using lower- and higher-order derivatives is a fundamental technique:

$$\begin{gather}
\textbf{Theorem: The Landau-Kolmogorov Inequality on Finite Increments} \\[5mm]
\text{Let } f: \mathbb{R} \to \mathbb{R} \text{ be twice differentiable on } \mathbb{R}, \text{ and let:} \\[2mm]
M_0 := \sup_{x \in \mathbb{R}} |f(x)| < \infty, \quad M_2 := \sup_{x \in \mathbb{R}} |f''(x)| < \infty. \\[2mm]
\text{Then the first derivative is bounded on all of } \mathbb{R}, \text{ and satisfies the sharp bound:} \\[3.5mm]
M_1 := \sup_{x \in \mathbb{R}} |f'(x)| \le \sqrt{2 M_0 M_2}.
\end{gather}$$
(see [[Proof of the Landau-Kolmogorov Derivative Inequality]])

---

# Taylor's Formula and Higher-Order Local Approximations

Just as the differential provides the unique affine function having contact of order 1 with a curve, **Taylor's formula** generalizes this local linear microscope to osculating polynomials of arbitrary degree $n \in \mathbb{N}$ having contact of order $n$.

### The Taylor Polynomial
Let $f: U(x_0) \to \mathbb{R}$ be $n$ times differentiable at an interior point $x_0 \in \mathbb{R}$.

$$\begin{gather}
\textbf{Definition: The Taylor Polynomial} \\[5mm]
\text{The Taylor polynomial of degree } n \text{ of } f \text{ at the expansion point } x_0 \text{ is the polynomial:} \\[3.5mm]
P_n(x_0; x) := \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k = f(x_0) + f'(x_0)(x - x_0) + \dots + \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n.
\end{gather}$$
By direct differentiation, $P_n^{(k)}(x_0; x_0) = f^{(k)}(x_0)$ for all $k = 0, 1, \dots, n$. When $x_0 = 0$, $P_n(0; x)$ is termed the **Maclaurin polynomial**.

The difference between the function and its Taylor polynomial is the **remainder term**:
$$R_n(x_0; x) := f(x) - P_n(x_0; x) \tag{5}$$

### Taylor's Theorem with Remainder Forms
$$\begin{gather}
\textbf{Theorem: Taylor's Theorem and Its Remainder Forms} \\[5mm]
\text{Let } f: U(x_0) \to \mathbb{R} \text{ be defined on an open neighborhood of } x_0. \\[3mm]
\begin{align}
\text{1. Peano Remainder:} \quad &\text{If } f \text{ is } n \text{ times differentiable at } x_0, \text{ then as } x \to x_0\text{:} \\[2mm]
&f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + o((x - x_0)^n). \\[3mm]
\text{2. Lagrange Remainder:} \quad &\text{If } f \in C^n([a, b]) \text{ and is } (n+1) \text{ times differentiable on } (a, b), \text{ then } \forall x \in [a, b], \\[2mm]
&\exists \xi \in (x_0, x) \text{ such that:} \\[2mm]
&R_n(x_0; x) = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x - x_0)^{n+1}. \\[3mm]
\text{3. Cauchy Remainder:} \quad &\text{Under the same hypotheses as the Lagrange remainder, there exists } \theta \in (0, 1) \text{ such that:} \\[2mm]
&R_n(x_0; x) = \frac{f^{(n+1)}(x_0 + \theta(x - x_0))}{n!} (1 - \theta)^n (x - x_0)^{n+1}.
\end{align}
\end{gather}$$
(see [[Proof of Taylor's Theorem with the Peano Remainder]])
(see [[Proof of Taylor's Theorem with the Lagrange and Cauchy Remainders]])

### Canonical Maclaurin Expansions
Evaluating the derivatives of standard elementary functions at $x_0 = 0$ yields the canonical Maclaurin series with Peano remainder as $x \to 0$:
$$\begin{gather}
\textbf{Table: Fundamental Maclaurin Expansions} \\[2mm]
\begin{array}{|l|l|}
\hline
e^x & 1 + x + \frac{x^2}{2!} + \dots + \frac{x^n}{n!} + o(x^n) \\[1mm]
\sin x & x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots + (-1)^m \frac{x^{2m+1}}{(2m+1)!} + o(x^{2m+2}) \\[1mm]
\cos x & 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots + (-1)^m \frac{x^{2m}}{(2m)!} + o(x^{2m+1}) \\[1mm]
\sinh x & x + \frac{x^3}{3!} + \frac{x^5}{5!} + \dots + \frac{x^{2m+1}}{(2m+1)!} + o(x^{2m+2}) \\[1mm]
\cosh x & 1 + \frac{x^2}{2!} + \frac{x^4}{4!} + \dots + \frac{x^{2m}}{(2m)!} + o(x^{2m+1}) \\[1mm]
\ln(1 + x) & x - \frac{x^2}{2} + \frac{x^3}{3} - \dots + (-1)^{n-1}\frac{x^n}{n} + o(x^n) \\[1mm]
(1 + x)^\alpha & 1 + \alpha x + \frac{\alpha(\alpha - 1)}{2!}x^2 + \dots + \frac{\alpha(\alpha - 1)\dots(\alpha - n + 1)}{n!}x^n + o(x^n) \\
\hline
\end{array}
\end{gather}$$
(see [[Proof of the Maclaurin Expansions of Elementary Functions]])

### Smoothness Versus Analyticity: Cauchy's Flat Function
A function $f$ is real-analytic ($C^\omega$) at $x_0$ if its Taylor series converges to $f(x)$ on a neighborhood of $x_0$. Augustin-Louis Cauchy discovered that smooth functions ($C^\infty$) are not necessarily analytic:

$$\begin{gather}
\textbf{Theorem: Cauchy’s Non-Analytic Smooth Function} \\[5mm]
\text{Define the function } f: \mathbb{R} \to \mathbb{R} \text{ by:} \\[3.5mm]
f(x) := \begin{cases} e^{-1/x^2}, & x \neq 0 \\ 0, & x = 0 \end{cases} \\[3.5mm]
\text{1. } f \in C^\infty(\mathbb{R}), \text{ possessing derivatives of all orders on all of } \mathbb{R}. \\[2mm]
\text{2. At the origin, every derivative vanishes identically: } f^{(n)}(0) = 0 \quad \forall n \in \mathbb{N} \cup \{0\}. \\[2mm]
\text{3. The Taylor series of } f \text{ at } 0 \text{ is identically zero, converging to } f(x) \text{ exclusively at } x = 0.
\end{gather}$$
(see [[Proof that Cauchy's Exponential Function is Smooth but Non-Analytic]])

### Bernstein's Sufficient Criterion for Analyticity
$$\begin{gather}
\textbf{Theorem: Bernstein’s Analyticity Criterion} \\[5mm]
\text{Let } f \in C^\infty([-R, R]). \text{ If there exists a constant } C > 0 \text{ such that:} \\[3.5mm]
\sup_{x \in [-R, R]} |f^{(n)}(x)| \le C^n n! \quad \forall n \in \mathbb{N},
\end{gather}$$
then the Taylor series of $f$ converges to $f(x)$ for all $|x| < \min(R, 1/C)$, proving analyticity.
(see [[Proof of Bernstein's Quasi-Analyticity Criterion]])

>[!example]- Quantitative Application: Bond Duration and Convexity
>In fixed-income portfolio theory, let $P(y) = \sum_{t=1}^T C_t (1 + y)^{-t}$ denote the price of a cash-flow stream viewed as a function of the continuous compounding yield $y$. Expanding $P(y + \Delta y)$ via Taylor's theorem:
>$$\frac{\Delta P}{P} = -D_{\text{mod}} \cdot \Delta y + \frac{1}{2} C_v \cdot (\Delta y)^2 + o((\Delta y)^2) \tag{6}$$
>where $D_{\text{mod}} = -\frac{P'(y)}{P(y)}$ is the modified duration (first Taylor coefficient), and $C_v = \frac{P''(y)}{P(y)}$ is the bond convexity (second Taylor coefficient). The quadratic Taylor polynomial provides the exact institutional risk measure used to hedge interest rate shocks.
