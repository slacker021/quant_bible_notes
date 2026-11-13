---
dg-publish: true
---
# Differential Topology of the Continuum and Monotonic Deformation
Possessing the ability to compute a derivative at an isolated point does not immediately yield a complete geometric portrait of a function. A strictly positive derivative $f'(x_0) > 0$ guarantees only that $f$ increases locally across an immediate neighborhood of $x_0$; it does not, by itself, preclude the graph from oscillating erratically, plunging steeply elsewhere, or forming pathological singularities. To reconstruct the global architecture of a curve—its intervals of monotonicity, its extremal peaks and valleys, its regions of upward or downward convexity, its asymptotes, and its singular branching behaviors—analysis must synthesize local derivatives into an overarching investigative apparatus. 

### The Monotonicity Spectrum of Differentiable Mappings
Let $E \subset \mathbb{R}$ be an open interval $(a, b)$, where $-\infty \le a < b \le +\infty$, and let $f: (a, b) \to \mathbb{R}$ be a function differentiable everywhere on $(a, b)$. By virtue of [[Chapter 3 - The Basic Theorems of Differential Calculus#Lagrange's Finite-Increment Theorem|Lagrange's Finite-Increment Theorem]], the finite chord increment separating any two distinct points $x_1 < x_2$ in $(a, b)$ satisfies:
$$
\begin{gather}
f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1) \tag{1}
\end{gather}
$$
for some intermediate point $\xi \in (x_1, x_2)$. Because $x_2 - x_1 > 0$, the algebraic sign of the macroscopic displacement $f(x_2) - f(x_1)$ is governed by the sign of the instantaneous derivative $f'(\xi)$.

This identity establishes a fundamental bridge between the differential properties of $f'$ and the order-preserving characteristics of $f$:
$$
\begin{gather}
\textbf{Theorem: Differential Criteria for Interval Monotonicity} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be differentiable on the open interval } (a, b). \\[2mm]
\text{The following implications and equivalences hold across } (a, b): \\[3.5mm]
\begin{align}
1. \quad & (\forall x \in (a, b), \ f'(x) > 0) \implies f \text{ is strictly increasing on } (a, b); \\[2mm]
2. \quad & (\forall x \in (a, b), \ f'(x) \ge 0) \iff f \text{ is non-decreasing on } (a, b); \\[2mm]
3. \quad & (\forall x \in (a, b), \ f'(x) \equiv 0) \iff f \text{ is identically constant on } (a, b); \\[2mm]
4. \quad & (\forall x \in (a, b), \ f'(x) \le 0) \iff f \text{ is non-increasing on } (a, b); \\[2mm]
5. \quad & (\forall x \in (a, b), \ f'(x) < 0) \implies f \text{ is strictly decreasing on } (a, b).
\end{align}
\end{gather}
$$
(see [[Proof of Differential Criteria for Interval Monotonicity]])

>[!info]+ Remark: Asymmetry Between Strict Positivity and Strict Monotonicity
>There is an essential structural asymmetry within the monotonicity theorem: while $f'(x) \ge 0$ is both necessary and sufficient for non-decreasing behavior, the condition $f'(x) > 0$ is sufficient, but strictly *not necessary*, for strict monotonicity. 
>
>Consider the canonical cubic monomial $f(x) = x^3$ on $\mathbb{R}$. For any pair $x_1 < x_2$, the strict inequality $x_1^3 < x_2^3$ holds, demonstrating that $f$ is strictly increasing across the real line. Nevertheless, its derivative $f'(x) = 3x^2$ vanishes at the origin: $f'(0) = 0$. The vanishing of the derivative at isolated points does not disrupt the global strict ordering of functional values.

### Strict Monotonicity Under Isolated Stationary Sets
The observation regarding $f(x) = x^3$ generalizes to a universal principle: a differentiable function remains strictly monotonic even if its derivative vanishes, provided that the set of stationary points contains no interior continuum:
$$
\begin{gather}
\textbf{Proposition: Strict Monotonicity Under Isolated Stationary Zeros} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be differentiable on } (a, b). \text{ Suppose that } f'(x) \ge 0 \\[2mm]
\text{for all } x \in (a, b), \text{ and let } Z := \{x \in (a, b) \mid f'(x) = 0\} \text{ denote its stationary zero set.} \\[2mm]
\text{If } Z \text{ contains no non-empty open subinterval } (\alpha, \beta) \subset (a, b), \\[2mm]
\text{then } f \text{ is strictly increasing on } (a, b).
\end{gather}
$$
(see [[Proof of Strict Monotonicity Under Isolated Stationary Zeros]])

>[!example]- Example: Monotonic Partitioning of a Cubic Polynomial
>Consider the real cubic polynomial $f: \mathbb{R} \to \mathbb{R}$ defined by:
>$$
>\begin{gather}
>f(x) := x^3 - 3x + 2 \tag{2}
>\end{gather}
>$$
>Differentiating step 2 yields the quadratic derivative:
>$$
>\begin{gather}
>f'(x) = 3x^2 - 3 = 3(x - 1)(x + 1) \tag{3}
>\end{gather}
>$$
>The stationary points, where $f'(x) = 0$, occur at $x = -1$ and $x = 1$. Analyzing the sign of the factored expression in step 3 decomposes the real continuum into three distinct monotonicity regimes:
>1. On $(-\infty, -1)$: Both $(x - 1) < 0$ and $(x + 1) < 0$, whence $f'(x) > 0$. The function is strictly increasing.
>2. On $(-1, 1)$: The factor $(x + 1) > 0$ while $(x - 1) < 0$, whence $f'(x) < 0$. The function is strictly decreasing.
>3. On $(1, \infty)$: Both factors are positive, whence $f'(x) > 0$. The function is strictly increasing.
>
>Because $f$ is continuous at the boundary points $x = \pm 1$, these monotonicity assertions extend to the closed intervals: $f$ is strictly increasing on $(-\infty, -1]$, strictly decreasing on $[-1, 1]$, and strictly increasing on $[1, \infty)$.

---
# Extremal Topologies and Higher-Order Classification
In [[Chapter 3 - The Basic Theorems of Differential Calculus#Fermat's Interior Extremum Lemma|Chapter 3]], Fermat's lemma established that if an interior point $x_0 \in (a, b)$ is a local extremum of a differentiable function, the derivative must vanish: $f'(x_0) = 0$. However, as demonstrated by the cubic monomial $f(x) = x^3$, the condition $f'(x_0) = 0$ is merely necessary, not sufficient. Differential calculus must therefore formulate constructive sufficient criteria to identify and classify extrema.

### First-Derivative Sign Alternation
The connection between the derivative's sign and functional monotonicity provides an immediate sufficient criterion for local extrema:
$$
\begin{gather}
\textbf{Theorem: First-Derivative Sign-Alternation Criterion} \\[5mm]
\text{Let } f: U(x_0) \to \mathbb{R} \text{ be continuous on a neighborhood } U(x_0) := (x_0 - \delta, x_0 + \delta) \\[2mm]
\text{and differentiable on the punctured neighborhood } \mathring{U}(x_0) := U(x_0) \setminus \{x_0\}. \\[2mm]
\text{Let } \mathring{U}^-(x_0) := (x_0 - \delta, x_0) \text{ and } \mathring{U}^+(x_0) := (x_0, x_0 + \delta). \text{ Then:} \\[3.5mm]
\begin{align}
1. \quad & \left(\forall x \in \mathring{U}^-(x_0), \ f'(x) > 0\right) \land \left(\forall x \in \mathring{U}^+(x_0), \ f'(x) < 0\right) \\[2mm]
& \implies x_0 \text{ is a strict local maximum of } f; \\[3.5mm]
2. \quad & \left(\forall x \in \mathring{U}^-(x_0), \ f'(x) < 0\right) \land \left(\forall x \in \mathring{U}^+(x_0), \ f'(x) > 0\right) \\[2mm]
& \implies x_0 \text{ is a strict local minimum of } f; \\[3.5mm]
3. \quad & \left(\forall x \in \mathring{U}(x_0), \ f'(x) > 0\right) \lor \left(\forall x \in \mathring{U}(x_0), \ f'(x) < 0\right) \\[2mm]
& \implies x_0 \text{ is not a local extremum of } f.
\end{align}
\end{gather}
$$
(see [[Proof of First-Derivative Sign-Alternation Criterion]])

>[!warning]+ Warning: Non-Necessity of Derivative Sign Stability
>Not every local extremum displays a derivative of constant sign on either side of $x_0$. Consider the pathological mapping $f: \mathbb{R} \to \mathbb{R}$ defined by:
>$$
>\begin{gather}
>f(x) := \begin{cases} 2x^2 + x^2 \sin\left(\frac{1}{x}\right), & x \neq 0 \\ 0, & x = 0 \end{cases} \tag{4}
>\end{gather}
>$$
>Because $-1 \le \sin(1/x) \le 1$, the function satisfies the strict quadratic bounds:
>$$
>\begin{gather}
>x^2 \le f(x) \le 3x^2 \tag{5}
>\end{gather}
>$$
>Step 5 demonstrates that for all $x \neq 0$, $f(x) \ge x^2 > 0 = f(0)$. Consequently, $x_0 = 0$ is an indisputable and strict global minimum. However, differentiating step 4 for $x \neq 0$ yields:
>$$
>\begin{gather}
>f'(x) = 4x + 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) \tag{6}
>\end{gather}
>$$
>As $x \to 0$, the term $\cos(1/x)$ oscillates between $-1$ and $+1$ infinitely often, dominating the vanishing terms $4x + 2x \sin(1/x)$. As a result, $f'(x)$ alternates sign infinitely often in every punctured neighborhood $(-\delta, 0) \cup (0, \delta)$. The first-derivative sign test is inconclusive, even though the extremum exists.

### Higher-Order Taylor Jet Classification
When higher-order derivatives exist at the stationary point, Taylor's formula provides a direct algebraic classification that avoids inspecting one-sided punctured neighborhoods:
$$
\begin{gather}
\textbf{Theorem: Higher-Order Taylor Jet Criterion for Local Extrema} \\[5mm]
\text{Let } n \in \mathbb{N} \text{ with } n \ge 2, \text{ and let } f: U(x_0) \to \mathbb{R} \text{ possess continuous derivatives} \\[2mm]
\text{up to order } n \text{ on a neighborhood } U(x_0). \text{ Suppose that:} \\[3.5mm]
f'(x_0) = f''(x_0) = \dots = f^{(n-1)}(x_0) = 0 \quad \text{and} \quad f^{(n)}(x_0) \neq 0 \\[3.5mm]
\text{Then the following classification holds:} \\[2mm]
\begin{align}
1. \quad & \text{If } n \text{ is odd, } x_0 \text{ is not a local extremum of } f; \\[2mm]
2. \quad & \text{If } n \text{ is even and } f^{(n)}(x_0) > 0, \ x_0 \text{ is a strict local minimum of } f; \\[2mm]
3. \quad & \text{If } n \text{ is even and } f^{(n)}(x_0) < 0, \ x_0 \text{ is a strict local maximum of } f.
\end{align}
\end{gather}
$$
(see [[Proof of Higher-Order Taylor Jet Criterion for Local Extrema]])

### Geometric Optics and Fermat's Principle of Least Time
A classical physical realization of the first-derivative extremum criterion is *Snell*'s law of refraction in geometric optics. According to Fermat's principle, a light ray traveling between two spatial points traverses the path that minimizes the total transit time.

Consider two optical media separated by a planar interface along the horizontal coordinate axis $y = 0$. Let medium 1 occupy the upper half-plane $y > 0$ with light velocity $c_1$, and medium 2 occupy the lower half-plane $y < 0$ with light velocity $c_2$. Suppose light emanates from $A_1 = (0, h_1)$ in medium 1 and arrives at $A_2 = (a, -h_2)$ in medium 2, where $h_1, h_2, a > 0$.

Let the ray cross the boundary interface at an intermediate point $(x, 0)$, where $x \in [0, a]$. The total propagation time is given by:
$$
\begin{gather}
T(x) = \frac{\sqrt{h_1^2 + x^2}}{c_1} + \frac{\sqrt{h_2^2 + (a - x)^2}}{c_2} \tag{7}
\end{gather}
$$

Differentiating step 7 with respect to the interface coordinate $x$ yields:
$$
\begin{gather}
T'(x) = \frac{x}{c_1 \sqrt{h_1^2 + x^2}} - \frac{a - x}{c_2 \sqrt{h_2^2 + (a - x)^2}} \tag{8}
\end{gather}
$$

Defining the angles of incidence $\alpha_1$ and refraction $\alpha_2$ between the ray paths and the surface normal, the geometric ratios in step 8 become:
$$
\begin{gather}
\sin(\alpha_1) = \frac{x}{\sqrt{h_1^2 + x^2}}, \quad \sin(\alpha_2) = \frac{a - x}{\sqrt{h_2^2 + (a - x)^2}} \tag{9}
\end{gather}
$$

Setting $T'(x) = 0$ in step 8 yields Snell's law:
$$
\begin{gather}
\frac{\sin(\alpha_1)}{c_1} = \frac{\sin(\alpha_2)}{c_2} \implies \frac{\sin(\alpha_1)}{\sin(\alpha_2)} = \frac{c_1}{c_2} \tag{10}
\end{gather}
$$

Differentiating step 8 a second time reveals:
$$
\begin{gather}
T''(x) = \frac{h_1^2}{c_1 (h_1^2 + x^2)^{3/2}} + \frac{h_2^2}{c_2 (h_2^2 + (a - x)^2)^{3/2}} > 0 \tag{11}
\end{gather}
$$
Because $T''(x) > 0$ strictly for all $x \in \mathbb{R}$, the stationary solution defined by Snell's law is the unique global minimum of transit time.

```easy-tikz
title $\text{Snell's Law: Optical Path Optimization at an Interface}$
xlabel $x$
ylabel $y$
show x from -0.5 to 7.0 and y from -4.0 to 4.5
axes on the edges
size 12 x 8
draw a line from (-0.5, 0.0) to (7.0, 0.0), in gray, very thick
draw a line from (3.0, -3.5) to (3.0, 4.0), in gray, dashed
draw a line from (0.5, 3.5) to (3.0, 0.0), in cyan, very thick
draw a line from (3.0, 0.0) to (6.0, -3.0), in orange, very thick
draw a line from (0.5, 0.0) to (0.5, 3.5), in gray, dashed
draw a line from (6.0, 0.0) to (6.0, -3.0), in gray, dashed
mark (0.5, 3.5), in cyan, large
mark (3.0, 0.0), in green, large
mark (6.0, -3.0), in orange, large
write "$A_1(0, h_1)$" at (0.5, 3.9) in cyan, center
write "$A_2(a, -h_2)$" at (6.0, -3.4) in orange, center
write "$\\text{Interface } y = 0$" at (3.8, 0.4) in gray, right
write "$\\text{Medium 1 } (c_1)$" at (1.4, 0.85) in teal, center
write "$\\text{Medium 2 } (c_2)$" at (5.05, -0.95) in orange, center
write "$(x, 0)$" at (3.35, 0.45) in green, center
write "$\\alpha_1$" at (2.5, 1.2) in cyan, center
write "$\\alpha_2$" at (3.5, -1.2) in orange, center

```

### Classical Algebraic Inequalities via Differential Optimization
The extremum criteria enable the derivation of fundamental inequalities that underpin classical analysis. Consider the parameterized real power function on the positive ray $(0, \infty)$:
$$
\begin{gather}
\textbf{Theorem: The Generalized Power-Bernoulli Differential Inequality} \\[5mm]
\text{Let } \alpha \in \mathbb{R} \setminus \{0, 1\}, \text{ and define } \varphi: (0, \infty) \to \mathbb{R} \text{ by:} \\[2mm]
\varphi(x) := x^\alpha - \alpha x + \alpha - 1 \\[3.5mm]
\text{Then the following strict inequalities hold for all } x \in (0, \infty) \setminus \{1\}: \\[2mm]
\begin{align}
1. \quad & x^\alpha - \alpha x + \alpha - 1 < 0 \quad \text{for } 0 < \alpha < 1; \\[2mm]
2. \quad & x^\alpha - \alpha x + \alpha - 1 > 0 \quad \text{for } \alpha < 0 \ \lor \ \alpha > 1.
\end{align}
\end{gather}
$$
(see [[Proof of the Generalized Power-Bernoulli Differential Inequality]])

Applying substitution and homogenization to the Power-Bernoulli inequality yields the celebrated inequality of Young:
$$
\begin{gather}
\textbf{Theorem: Young's Conjugate Inequality} \\[5mm]
\text{Let } a > 0, \ b > 0, \text{ and let } p, q \in \mathbb{R} \setminus \{0, 1\} \text{ satisfy the conjugate relation:} \\[2mm]
\frac{1}{p} + \frac{1}{q} = 1 \\[3.5mm]
\text{Then the following relations hold:} \\[2mm]
\begin{align}
1. \quad & a^{1/p} b^{1/q} \le \frac{a}{p} + \frac{b}{q} \quad \text{for } p > 1; \\[2mm]
2. \quad & a^{1/p} b^{1/q} \ge \frac{a}{p} + \frac{b}{q} \quad \text{for } p < 1, \ p \neq 0.
\end{align} \\[3.5mm]
\text{In each case, equality is attained if and only if } a = b.
\end{gather}
$$
(see [[Proof of Young's Conjugate Inequality]])

Summing scaled instances of Young's inequality across finite index sets produces the classical discrete $l^p$ inequalities:
$$
\begin{gather}
\textbf{Theorem: Hölder's Discrete Summation Inequality} \\[5mm]
\text{Let } x_1, \dots, x_n \ge 0 \text{ and } y_1, \dots, y_n \ge 0, \text{ and let } \frac{1}{p} + \frac{1}{q} = 1. \text{ Then:} \\[3.5mm]
\begin{align}
1. \quad & \sum_{i=1}^n x_i y_i \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n y_i^q\right)^{1/q} \quad \text{for } p > 1; \\[3.5mm]
2. \quad & \sum_{i=1}^n x_i y_i \ge \left(\sum_{i=1}^n x_i^p\right)^{1/p} \left(\sum_{i=1}^n y_i^q\right)^{1/q} \quad \text{for } p < 1, \ p \neq 0.
\end{align} \\[3.5mm]
\text{Equality holds if and only if the vectors } (x_1^p, \dots, x_n^p) \text{ and } (y_1^q, \dots, y_n^q) \text{ are collinear.}
\end{gather}
$$
(see [[Proof of Hölder's Discrete Summation Inequality]])

From Hölder's inequality emerges the subadditivity of the discrete $l^p$ norm, known as Minkowski's inequality:
$$
\begin{gather}
\textbf{Theorem: Minkowski's Norm Triangle Inequality} \\[5mm]
\text{Let } x_1, \dots, x_n \ge 0 \text{ and } y_1, \dots, y_n \ge 0. \text{ Then:} \\[3.5mm]
\begin{align}
1. \quad & \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/p} \le \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \quad \text{for } p \ge 1; \\[3.5mm]
2. \quad & \left(\sum_{i=1}^n (x_i + y_i)^p\right)^{1/p} \ge \left(\sum_{i=1}^n x_i^p\right)^{1/p} + \left(\sum_{i=1}^n y_i^p\right)^{1/p} \quad \text{for } p < 1, \ p \neq 0.
\end{align} \\[3.5mm]
\text{For } p > 1, \text{ equality holds if and only if } (x_1, \dots, x_n) \text{ and } (y_1, \dots, y_n) \text{ are collinear.}
\end{gather}
$$
(see [[Proof of Minkowski's Norm Triangle Inequality]])

---
# Convexity, Chordal Secants, and Subdifferential Geometry
The study of a curve requires understanding not only whether it rises or falls, but the nature of its curvature: does the trajectory bend upwards, holding water like a basin, or arch downwards like an umbrella? This geometric property is formalized through the concept of *convexity*.

### The Geometric Definition of Convexity
Let $(a, b) \subset \mathbb{R}$ be an open interval. A real-valued function $f: (a, b) \to \mathbb{R}$ is termed *convex* (or *convex downward*) if the secant chord connecting any two points on its graph lies nowhere below the graph itself:
$$
\begin{gather}
\textbf{Definition: Convex and Strictly Convex Functions} \\[5mm]
\text{A function } f: (a, b) \to \mathbb{R} \text{ is called } \textit{convex} \text{ on } (a, b) \text{ if for all } x_1, x_2 \in (a, b) \\[2mm]
\text{and all weights } \alpha_1 \ge 0, \ \alpha_2 \ge 0 \text{ satisfying } \alpha_1 + \alpha_2 = 1: \\[3.5mm]
f(\alpha_1 x_1 + \alpha_2 x_2) \le \alpha_1 f(x_1) + \alpha_2 f(x_2) \\[3.5mm]
\text{The function is } \textit{strictly convex} \text{ if the inequality is strict whenever } x_1 \neq x_2 \text{ and } \alpha_1 \alpha_2 \neq 0.
\end{gather}
$$

If the reversed inequality holds, $f$ is termed *concave* (or *convex upward*). The geometric substance of the definition of convexity states that the *epigraph* of the function:
$$
\begin{gather}
\operatorname{epi}(f) := \{(x, y) \in \mathbb{R}^2 \mid x \in (a, b), \ y \ge f(x)\} \tag{12}
\end{gather}
$$
forms a convex subset of the Euclidean plane $\mathbb{R}^2$.

### The Three-Chord Slope Inequality
To analyze convexity with the machinery of differential calculus, the definition of convexity is recast in terms of secant chord slopes. Let $x_1 < x < x_2$ be three points in $(a, b)$. Expressing $x$ as the convex combination $x = \alpha_1 x_1 + \alpha_2 x_2$, the barycentric coordinates are:
$$
\begin{gather}
\alpha_1 = \frac{x_2 - x}{x_2 - x_1}, \quad \alpha_2 = \frac{x - x_1}{x_2 - x_1} \tag{13}
\end{gather}
$$
Substituting step 13 into the definition of convexity and performing algebraic rearrangement yields the fundamental three-slope ordering:
$$
\begin{gather}
\frac{f(x) - f(x_1)}{x - x_1} \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le \frac{f(x_2) - f(x)}{x_2 - x} \tag{14}
\end{gather}
$$
The inequality of step 14 asserts that as an observer moves from left to right, the slope of the secant chord connecting points on the graph is monotonically non-decreasing.

```easy-tikz
title $\text{Convexity: Secant Chord Domination and Slope Ordering}$
xlabel $x$
ylabel $y$
show x from 0.0 to 7.5 and y from 0.0 to 6.5
axes on the edges
size 12 x 8
plot f(x) = 0.15*x*x - 0.2*x + 1.2, from x = 0.8 to 6.8, in cyan, very thick
draw a line from (1.5, 1.2375) to (6.2, 5.726), in orange, thick
draw a line from (1.5, 1.2375) to (3.8, 2.606), in green, dashed
draw a line from (3.8, 2.606) to (6.2, 5.726), in purple, dashed
draw a line from (1.5, 0.0) to (1.5, 1.2375), in gray, dashed
draw a line from (3.8, 0.0) to (3.8, 2.606), in gray, dashed
draw a line from (6.2, 0.0) to (6.2, 5.726), in gray, dashed
mark (1.5, 1.2375), in orange, large
mark (3.8, 2.606), in green, large
mark (6.2, 5.726), in orange, large
write "$x_1$" at (1.5, 0.4) in gray, center
write "$x$" at (3.8, 0.4) in gray, center
write "$x_2$" at (6.2, 0.4) in gray, center
write "$\\text{Secant Chord}$" at (3.5, 4.3) in orange, center
write "$f(x)$" at (6.25, 6.55) in teal, center
write "$\\text{Slope } k_1$" at (2.9, 1.3) in green, center
write "$\\text{Slope } k_2$" at (5.3, 3.8) in purple, center

```

### Differential Criteria for Convexity
Taking limits as $x \to x_1^+$ and $x \to x_2^-$ within the chord inequality of step 14 links convexity to the monotonicity of the derivative:
$$
\begin{gather}
\textbf{Theorem: First-Order Monotonicity Characterization of Convexity} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be differentiable on } (a, b). \text{ Then:} \\[2mm]
\begin{align}
1. \quad & f \text{ is convex on } (a, b) \iff f' \text{ is non-decreasing on } (a, b); \\[2mm]
2. \quad & f \text{ is strictly convex on } (a, b) \iff f' \text{ is strictly increasing on } (a, b).
\end{align}
\end{gather}
$$
(see [[Proof of First-Order Monotonicity Characterization of Convexity]])

If $f$ possesses a second derivative, the monotonicity theorem for first derivatives immediately provides the standard second-order test:
$$
\begin{gather}
\textbf{Theorem: Second-Order Differential Criterion for Convexity} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be twice differentiable on } (a, b). \text{ Then:} \\[2mm]
\begin{align}
1. \quad & f \text{ is convex on } (a, b) \iff \forall x \in (a, b), \ f''(x) \ge 0; \\[2mm]
2. \quad & (\forall x \in (a, b), \ f''(x) > 0) \implies f \text{ is strictly convex on } (a, b).
\end{align}
\end{gather}
$$
(see [[Proof of Second-Order Differential Criterion for Convexity]])

### The Supporting Hyperplane Property
Geometrically, a convex planar region lies entirely on one side of any supporting line tangent to its boundary. Analytically, this means the tangent line to the graph of a convex function serves as a global lower affine support:
$$
\begin{gather}
\textbf{Theorem: Supporting Tangent Characterization of Convexity} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be differentiable on } (a, b). \text{ Then } f \text{ is convex on } (a, b) \\[2mm]
\text{if and only if for every anchor point } x_0 \in (a, b) \text{ and all } x \in (a, b): \\[3.5mm]
f(x) \ge f(x_0) + f'(x_0)(x - x_0) \\[3.5mm]
\text{Furthermore, } f \text{ is strictly convex if and only if this inequality is strict for all } x \neq x_0.
\end{gather}
$$
(see [[Proof of Supporting Tangent Characterization of Convexity]])

### Inflection Points and Convexity Inversion
A point at which a curve transitions from one direction of convexity to the opposite is called an *inflection point*:
$$
\begin{gather}
\textbf{Definition: Point of Inflection} \\[5mm]
\text{Let } f: U(x_0) \to \mathbb{R} \text{ be continuous on a neighborhood of } x_0. \text{ The point } (x_0, f(x_0)) \\[2mm]
\text{is called a } \textit{point of inflection} \text{ of the graph of } f \text{ if there exists a punctured neighborhood} \\[2mm]
\mathring{U}(x_0) = (x_0 - \delta, x_0) \cup (x_0, x_0 + \delta) \text{ such that } f \text{ is strictly convex on one side} \\[2mm]
\text{and strictly concave on the other side of } x_0.
\end{gather}
$$

If $f$ is twice differentiable at an inflection point $x_0$, the first derivative $f'$ achieves a local extremum at $x_0$. Fermat's lemma forces the second derivative to vanish:
$$
\begin{gather}
\textbf{Proposition: Necessary Condition for an Inflection Point} \\[5mm]
\text{If } (x_0, f(x_0)) \text{ is a point of inflection of the graph of } f \text{ and } f''(x_0) \text{ exists,} \\[2mm]
\text{then the second derivative vanishes identically:} \\[3.5mm]
f''(x_0) = 0
\end{gather}
$$
(see [[Proof of Necessary Condition for an Inflection Point]])

>[!warning]+ Warning: The Fallacy of Tangent Crossing
>Note that $f''(x_0) = 0$ is strictly necessary, not sufficient. For $f(x) = x^4$, $f''(0) = 0$, yet $f''(x) = 12x^2 \ge 0$ everywhere; the function remains strictly convex on all of $\mathbb{R}$, and $x = 0$ is a strict global minimum, not an inflection point.
>
>Furthermore, a curve may cross its tangent line at a point without possessing an inflection point. Consider the pathological mapping:
>$$
>\begin{gather}
>f(x) := \begin{cases} 2x^3 + x^3 \sin\left(\frac{1}{x^2}\right), & x \neq 0 \\ 0, & x = 0 \end{cases} \tag{15}
>\end{gather}
>$$
>Because $x^3 \le f(x) \le 3x^3$ for $x \ge 0$ and $3x^3 \le f(x) \le x^3$ for $x \le 0$, the graph is tangent to the horizontal axis $y = 0$ at the origin and passes strictly from the lower half-plane into the upper half-plane. However, its second derivative oscillates uncontrollably, changing sign infinitely often in every neighborhood of zero. The function fails to be convex or concave on any one-sided interval $(0, \delta)$ or $(-\delta, 0)$.

```easy-tikz
title $\text{Inflection Point: Tangent Piercing and Convexity Inversion}$
xlabel $x$
ylabel $y$
show x from -3.5 to 3.5 and y from -2.0 to 2.0
axes on the edges
size 12 x 8
plot f(x) = sin(x), from x = -3.2 to 3.2, in cyan, very thick
plot tangent(x) = x, from x = -1.8 to 1.8, in orange, thick, dashed
draw a line from (0.0, -1.8) to (0.0, 1.8), in gray, dashed
mark (0.0, 0.0), in green, large
write "$\\text{Concave: } f''(x) < 0$" at (2.45, 1.35) in teal, center
write "$\\text{Convex: } f''(x) > 0$" at (-2.4, -1.2) in teal, center
write "$\\text{Inflection Point } (0, 0)$" at (-0.05, 0.05) in green, left
write "$\\text{Inflexional Tangent } y = x$" at (0.1, -0.13) in orange, right

```

### Jensen's Generalized Convex Inequality
The fundamental definition of convexity extends by mathematical induction from two weights to arbitrary finite convex combinations:
$$
\begin{gather}
\textbf{Theorem: Jensen's Generalized Convex Inequality} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be a convex function on } (a, b). \text{ Let } x_1, \dots, x_n \in (a, b) \\[2mm]
\text{and let } \alpha_1, \dots, \alpha_n \ge 0 \text{ be non-negative weights satisfying } \sum_{i=1}^n \alpha_i = 1. \text{ Then:} \\[3.5mm]
f\left(\sum_{i=1}^n \alpha_i x_i\right) \le \sum_{i=1}^n \alpha_i f(x_i) \\[3.5mm]
\text{If } f \text{ is strictly convex and all } \alpha_i > 0, \text{ equality holds} \\[2mm]
\text{if and only if } x_1 = x_2 = \dots = x_n.
\end{gather}
$$
(see [[Proof of Jensen's Generalized Convex Inequality]])

---
# Structural Regularity and Dual Transforms of Convex Mappings
Beyond their elementary differential properties, convex functions possess deep structural, asymptotic, and dual properties. The following results constitute essential tools throughout quantitative analysis.

### Midpoint-Convexity and Continuity
A classic question in functional analysis asks whether the full chord inequality of convexity can be relaxed to equal weights $\alpha_1 = \alpha_2 = 1/2$. The answer is positive under the mild assumption of continuity:
$$
\begin{gather}
\textbf{Theorem: Midpoint-Convexity Characterization of Continuous Mappings} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be continuous on the open interval } (a, b). \text{ If for all } x_1, x_2 \in (a, b): \\[3.5mm]
f\left(\frac{x_1 + x_2}{2}\right) \le \frac{f(x_1) + f(x_2)}{2} \\[3.5mm]
\text{then } f \text{ is convex on } (a, b).
\end{gather}
$$
(see [[Proof of Midpoint-Convexity Characterization of Continuous Mappings]])

### Asymptotic Rigidity and Boundedness
Convexity imposes severe constraints on the growth of a function defined across the entire real line:
$$
\begin{gather}
\textbf{Theorem: Asymptotic Rigidity and Boundedness of Convex Functions} \\[5mm]
\text{Let } f: \mathbb{R} \to \mathbb{R} \text{ be a convex function defined on the entire real line. Then:} \\[3.5mm]
\begin{align}
1. \quad & \text{If } f \text{ is bounded from above or bounded from below, } f \text{ is identically constant;} \\[2mm]
2. \quad & \text{If } \lim_{x \to -\infty} \frac{f(x)}{x} = \lim_{x \to +\infty} \frac{f(x)}{x} = 0, \text{ then } f \text{ is identically constant;} \\[2mm]
3. \quad & \text{For any convex function defined on a semi-infinite ray } (a, \infty), \text{ the asymptotic ratio} \\[2mm]
& \frac{f(x)}{x} \text{ converges as } x \to +\infty \text{ to a finite limit or diverges to } +\infty.
\end{align}
\end{gather}
$$
(see [[Proof of Asymptotic Rigidity and Boundedness of Convex Functions]])

### Unilateral Differentiability and Countability of Singularities
While a convex function need not be everywhere differentiable (as exhibited by $f(x) = |x|$ at $x = 0$), its directional derivatives exist everywhere:
$$
\begin{gather}
\textbf{Theorem: Unilateral Differential Structure of Convex Functions} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be convex on } (a, b). \text{ Then:} \\[2mm]
\begin{align}
1. \quad & \text{At every point } x \in (a, b), \text{ the left-hand derivative } f'_-(x) \text{ and right-hand derivative} \\[2mm]
& f'_+(x) \text{ exist as finite real numbers and satisfy:} \\[3.5mm]
& f'_-(x) \le f'_+(x); \\[3.5mm]
2. \quad & \text{For any two points } x_1 < x_2 \text{ in } (a, b), \text{ the directional rates satisfy the monotonicity:} \\[3.5mm]
& f'_-(x_1) \le f'_+(x_1) \le \frac{f(x_2) - f(x_1)}{x_2 - x_1} \le f'_-(x_2) \le f'_+(x_2); \\[3.5mm]
3. \quad & \text{The set of angular singular points } S := \{x \in (a, b) \mid f'_-(x) < f'_+(x)\} \text{ where } f \\[2mm]
& \text{fails to be differentiable is at most countable.}
\end{align}
\end{gather}
$$
(see [[Proof of Unilateral Differential Structure of Convex Functions]])

### The Legendre-Fenchel Conjugate Transform
In mathematical physics, thermodynamics, and quantitative optimization, the *Legendre-Fenchel transform* converts a convex function of position into a dual convex function of momentum (or slope):
$$
\begin{gather}
\textbf{Theorem: The Legendre-Fenchel Duality and Conjugate Convexity} \\[5mm]
\text{Let } I \subset \mathbb{R} \text{ be an interval, and let } f: I \to \mathbb{R}. \text{ The Legendre transform } f^* \text{ is defined by:} \\[3.5mm]
f^*(t) := \sup_{x \in I} \big(tx - f(x)\big) \\[3.5mm]
\text{defined on the effective dual domain } I^* := \{t \in \mathbb{R} \mid f^*(t) < +\infty\}. \text{ Then:} \\[2mm]
\begin{align}
1. \quad & I^* \text{ is an interval (or empty), and } f^* \text{ is always convex on } I^*; \\[2mm]
2. \quad & \text{For all } x \in I \text{ and } t \in I^*, \text{ the Fenchel-Young inequality holds:} \\[3.5mm]
& xt \le f(x) + f^*(t); \\[3.5mm]
3. \quad & \text{If } f \text{ is convex and continuous, the transform is involutive: } (f^*)^* \equiv f; \\[2mm]
4. \quad & \text{If } f \text{ is strictly convex and differentiable, } f^*(t) = t x(t) - f(x(t)), \\[2mm]
& \text{where } x(t) \text{ is the unique solution to } t = f'(x).
\end{align}
\end{gather}
$$
(see [[Proof of the Legendre-Fenchel Duality and Conjugate Convexity]])

>[!info]+ Remark: Duality of Power Monomials
>Let $\alpha > 1$, and consider the power monomial $f(x) = \frac{1}{\alpha} x^\alpha$ defined on $[0, \infty)$. Solving $t = f'(x) = x^{\alpha - 1}$ yields $x(t) = t^{1/(\alpha - 1)}$. Defining the conjugate exponent $\beta$ by $\frac{1}{\alpha} + \frac{1}{\beta} = 1$, one finds that $\beta = \frac{\alpha}{\alpha - 1}$.
>
>The Legendre dual function evaluated via the Legendre-Fenchel transform is:
>$$
>\begin{gather}
>f^*(t) = t \cdot t^{\frac{1}{\alpha - 1}} - \frac{1}{\alpha} \left(t^{\frac{1}{\alpha - 1}}\right)^\alpha = t^{\frac{\alpha}{\alpha - 1}} \left(1 - \frac{1}{\alpha}\right) = \frac{1}{\beta} t^\beta \tag{16}
>\end{gather}
>$$
>Substituting step 16 into the Fenchel-Young inequality recovers Young's inequality:
>$$
>\begin{gather}
>xt \le \frac{1}{\alpha} x^\alpha + \frac{1}{\beta} t^\beta \tag{17}
>\end{gather}
>$$
>without requiring any external ad-hoc constructions.

### Differential Curvature and Osculation of Plane Curves
The second derivative determines not only functional convexity, but also the geometric *curvature* of the trajectory:
$$
\begin{gather}
\textbf{Proposition: Differential Curvature and Geometric Osculation of Planar Curves} \\[5mm]
\text{Let } f: (a, b) \to \mathbb{R} \text{ be twice differentiable on } (a, b). \text{ The signed curvature } k(x) \\[2mm]
\text{of the graph } y = f(x) \text{ at the point } (x, f(x)) \text{ is given by:} \\[3.5mm]
k(x) := \frac{f''(x)}{\left(1 + [f'(x)]^2\right)^{3/2}} \\[3.5mm]
\text{The radius of curvature } R(x) \text{ is the reciprocal of the absolute curvature:} \\[3.5mm]
R(x) := \frac{1}{|k(x)|} = \frac{\left(1 + [f'(x)]^2\right)^{3/2}}{|f''(x)|} \\[3.5mm]
\text{The sign of } k(x) \text{ matches the sign of } f''(x) \text{ identically. In particular, } k(x) = 0 \\[2mm]
\text{if and only if the second derivative vanishes at an inflection candidate.}
\end{gather}
$$
(see [[Proof of Differential Curvature and Geometric Osculation of Planar Curves]])

### The Adamović-Mitrinović Trigonometric Inequality
Differential monotonicity analysis yields sharp bounds on classical circular functions:
$$
\begin{gather}
\textbf{Proposition: The Adamović-Mitrinović Trigonometric Inequality} \\[5mm]
\text{For all non-zero real numbers } x \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \setminus \{0\}, \text{ the following strict inequality holds:} \\[3.5mm]
\cos(x) < \left(\frac{\sin(x)}{x}\right)^3
\end{gather}
$$
(see [[Proof of the Adamović-Mitrinović Trigonometric Inequality]])

---
# Indeterminate Forms and L'Hôpital's Asymptotic Rules
Evaluating limits of ratios where both numerator and denominator simultaneously vanish or diverge is a recurring challenge in analysis. While Taylor polynomials resolve such limits near regular points, *L'Hôpital's rule* provides a universal criterion based on Cauchy's Mean Value Theorem.

### The General Ratio Limit Theorem
$$
\begin{gather}
\textbf{Theorem: The Cauchy-L'Hôpital Indeterminate Ratio Rule} \\[5mm]
\text{Let } -\infty \le a < b \le +\infty, \text{ and let } f, g: (a, b) \to \mathbb{R} \text{ be differentiable on } (a, b). \\[2mm]
\text{Assume that } g'(x) \neq 0 \text{ for all } x \in (a, b), \text{ and suppose that:} \\[3.5mm]
\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = A \quad (-\infty \le A \le +\infty) \\[3.5mm]
\text{If either of the following two indeterminate conditions holds:} \\[2mm]
\begin{align}
\text{Case } \left[\frac{0}{0}\right]: \quad & \lim_{x \to a^+} f(x) = 0 \quad \text{and} \quad \lim_{x \to a^+} g(x) = 0; \\[2mm]
\text{Case } \left[\frac{*}{\infty}\right]: \quad & \lim_{x \to a^+} g(x) = \infty \quad (\text{or } -\infty);
\end{align} \\[3.5mm]
\text{then the original functional ratio converges to the identical limit:} \\[3.5mm]
\lim_{x \to a^+} \frac{f(x)}{g(x)} = A
\end{gather}
$$
(see [[Proof of the Cauchy-L'Hôpital Indeterminate Ratio Rule]])

An identical assertion holds for left-sided limits $x \to b^-$, two-sided limits $x \to x_0$, and infinite endpoints $x \to \pm\infty$.

>[!danger]+ Intuition: The Dynamic Motion Analogy
>To grasp L'Hôpital's rule intuitively, visualize two particles moving along parallel tracks towards an origin point. Their positions at temporal parameter $t$ are given by $x = g(t)$ and $y = f(t)$. The ratio of positions $f(t)/g(t)$ represents the slope of the chord connecting the origin to the parametric point $(g(t), f(t))$. 
>
>As both particles approach the origin (the $[0/0]$ regime), Cauchy's theorem asserts that the chord slope over any interval $[t, t_0]$ is realized identically as the ratio of instantaneous velocities $f'(\xi)/g'(\xi)$ at some intermediate instant $\xi$. If the ratio of instantaneous velocities stabilizes to a steady value $A$ as $t \to 0$, the ratio of accumulated distances must settle to the exact same value.

>[!warning]+ Warning: The Fallacy of Premature Differentiation
>L'Hôpital's rule is valid *only* when the ratio constitutes a genuine indeterminate form ($[0/0]$ or $[*/\infty]$). Applying the rule to determinate ratios yields false results.
>
>Consider the ratio $f(x) = \cos(x)$ and $g(x) = \sin(x)$ as $x \to 0^+$. The true limit is determinate:
>$$
>\begin{gather}
>\lim_{x \to 0^+} \frac{\cos(x)}{\sin(x)} = \frac{1}{0^+} = +\infty \tag{18}
>\end{gather}
>$$
>If one mindlessly differentiates numerator and denominator, one obtains:
>$$
>\begin{gather}
>\frac{f'(x)}{g'(x)} = \frac{-\sin(x)}{\cos(x)} \implies \lim_{x \to 0^+} \frac{-\sin(x)}{\cos(x)} = \frac{0}{1} = 0 \tag{19}
>\end{gather}
>$$
>Step 19 contradicts the true limit of step 18. Differentiating without verifying indeterminacy produces invalid results.
>
>Additionally, the converse of L'Hôpital's rule is false: the limit of $f(x)/g(x)$ may exist even if the ratio of derivatives $f'(x)/g'(x)$ oscillates erratically without limit. For example, consider $f(x) = x + \sin(x)$ and $g(x) = x$ as $x \to \infty$. The ratio of functions satisfies $\lim_{x \to \infty} \frac{x + \sin(x)}{x} = 1 + 0 = 1$. However, the ratio of derivatives is $\frac{1 + \cos(x)}{1}$, which oscillates periodically between $0$ and $2$ and fails to converge.

---
# Geometric Analysis and Global Construction of Curves
A central goal of one-variable differential calculus is synthesizing local analytic data into a complete geometric portrait of a curve. Constructing the graph of a function $y = f(x)$ proceeds through an organized protocol:
### The Systematic Curve Investigation Protocol
1. **Domain Topology and Singularities:** Identify the natural domain $\operatorname{dom}(f) \subset \mathbb{R}$, isolating points of discontinuity, jump boundaries, and vertical poles.
2. **Global Symmetries and Invariants:** Test for even symmetry ($f(-x) = f(x)$, reflectional across the $y$-axis), odd symmetry ($f(-x) = -f(x)$, rotational about the origin), and periodicity ($f(x + T) = f(x)$).
3. **Boundary Limits and Asymptotes:**
   - *Vertical Asymptotes:* If $\lim_{x \to x_0^\pm} |f(x)| = +\infty$, the vertical line $x = x_0$ is an asymptote.
   - *Oblique/Horizontal Asymptotes:* A line $y = c_1 x + c_0$ is an asymptote as $x \to \pm\infty$ if $f(x) - (c_1 x + c_0) = o(1)$. The coefficients are determined via:
     $$
     \begin{gather}
     c_1 := \lim_{x \to \pm\infty} \frac{f(x)}{x}, \quad c_0 := \lim_{x \to \pm\infty} \big(f(x) - c_1 x\big) \tag{20}
     \end{gather}
     $$
4. **First-Order Differential Variation:** Compute $f'(x)$, identify stationary points ($f'(x) = 0$) and singular non-differentiable points, construct the sign partition table, and establish the intervals of strict monotonicity and local extrema.
5. **Second-Order Curvature and Inflection:** Compute $f''(x)$, determine the sign partition of the second derivative, establish intervals of convexity ($f''(x) > 0$) and concavity ($f''(x) < 0$), and locate inflection points.
6. **Characteristic Anchors:** Calculate coordinate axis intercepts ($f(0)$ and real solutions to $f(x) = 0$) and assemble the comprehensive curve.

```easy-tikz
title $\text{Global Curve Topology: Monotonicity, Extrema, and Asymptotes}$
xlabel $x$
ylabel $y$
show x from -4.655 to 5.345 and y from -6.822 to 5.178
axes on the edges
size 12 x 8
plot f1(x) = (x*x*x - 3.0*x)/(x*x - 1.0), from x = -4.5 to -1.15, in cyan, very thick
plot f2(x) = (x*x*x - 3.0*x)/(x*x - 1.0), from x = -0.85 to 0.85, in cyan, very thick
plot f3(x) = (x*x*x - 3.0*x)/(x*x - 1.0), from x = 1.15 to 4.5, in cyan, very thick
plot asymp(x) = x, from x = -4.5 to 4.5, in orange, thick, dashed
draw a line from (-1.0, -5.5) to (-1.0, 5.5), in gray, dashed
draw a line from (1.0, -5.5) to (1.0, 5.5), in gray, dashed
mark (0.0, 0.0), in green, large
mark (-1.732, 0.0), in green, large
mark (1.732, 0.0), in green, large
draw an arrow from (-1.35, 4.8) to (-0.05, 0.2) in green
write "$\\text{Oblique Asymptote } y = x$" at (4.7, 5.2) in orange, left
write "$x = -1$" at (-2.3, -2.7) in gray, right
write "$x = 1$" at (1.1, 2.6) in gray, right
write "$\\text{Inflection } (0, 0)$" at (-3.7, 4.8) in green, right

```

---
# Applications of the Study of Functions Through Differential Calculus

### Astrophysics: Effective Potential Wells and Orbital Stability
In classical celestial mechanics and astrophysics, the planar trajectory of a satellite of mass $m$ orbiting a central celestial body of mass $M$ with fixed angular momentum $L > 0$ is governed by the one-dimensional *effective potential energy* $V_{\text{eff}}: (0, \infty) \to \mathbb{R}$:
$$
\begin{gather}
V_{\text{eff}}(r) := \frac{L^2}{2m r^2} - \frac{G M m}{r} \tag{21}
\end{gather}
$$
where $G > 0$ denotes Newton's gravitational constant and $r$ is the radial separation distance. The motion requires determining stable circular orbits, escape thresholds, and the curvature characteristics of the potential well.

##### 1. Asymptotic Profile and Boundary Singularities
Inspecting the boundaries of the radial domain $(0, \infty)$:
- As $r \to 0^+$: The positive centrifugal barrier term $\frac{L^2}{2m r^2}$ scales as $r^{-2}$, dominating the negative gravitational term $-\frac{GMm}{r}$ which scales as $r^{-1}$. Thus:
  $$
  \begin{gather}
  \lim_{r \to 0^+} V_{\text{eff}}(r) = +\infty \tag{22}
  \end{gather}
  $$
  The vertical axis $r = 0$ is a vertical asymptote representing an impenetrable centrifugal barrier.
- As $r \to \infty$: Both terms vanish asymptotically, with the slower-decaying gravitational potential dominating from below:
  $$
  \begin{gather}
  \lim_{r \to \infty} V_{\text{eff}}(r) = 0^- \tag{23}
  \end{gather}
  $$
  The horizontal axis $V = 0$ is a horizontal asymptote.

##### 2. First-Derivative Analysis: Stationary Radius of Circular Equilibrium
Differentiating step 21 with respect to $r$ yields the radial generalized force:
$$
\begin{gather}
V'_{\text{eff}}(r) = -\frac{L^2}{m r^3} + \frac{G M m}{r^2} = \frac{1}{r^3} \left(-\frac{L^2}{m} + G M m r\right) \tag{24}
\end{gather}
$$
Setting $V'_{\text{eff}}(r) = 0$ in step 24 yields a unique stationary point:
$$
\begin{gather}
r_0 = \frac{L^2}{G M m^2} \tag{25}
\end{gather}
$$
For $r \in (0, r_0)$, step 24 shows that $V'_{\text{eff}}(r) < 0$, so $V_{\text{eff}}$ is strictly decreasing. For $r \in (r_0, \infty)$, $V'_{\text{eff}}(r) > 0$, so $V_{\text{eff}}$ is strictly increasing. By the first-derivative test, $r_0$ is a strict global minimum.

The energy of this circular orbit is:
$$
\begin{gather}
V_{\text{eff}}(r_0) = \frac{L^2}{2m \left(\frac{L^2}{GMm^2}\right)^2} - \frac{GMm}{\frac{L^2}{GMm^2}} = \frac{G^2 M^2 m^3}{2L^2} - \frac{G^2 M^2 m^3}{L^2} = -\frac{G^2 M^2 m^3}{2 L^2} < 0 \tag{26}
\end{gather}
$$

##### 3. Second-Derivative Analysis: Orbital Stability and Potential Well Convexity
Differentiating step 24 yields the second derivative:
$$
\begin{gather}
V''_{\text{eff}}(r) = \frac{3L^2}{m r^4} - \frac{2 G M m}{r^3} = \frac{1}{r^4} \left(\frac{3L^2}{m} - 2 G M m r\right) \tag{27}
\end{gather}
$$
Evaluating step 27 at the stationary equilibrium radius $r_0 = \frac{L^2}{GMm^2}$:
$$
\begin{gather}
V''_{\text{eff}}(r_0) = \frac{1}{r_0^4} \left(\frac{3L^2}{m} - 2 \frac{L^2}{m}\right) = \frac{L^2}{m r_0^4} > 0 \tag{28}
\end{gather}
$$
Because $V''_{\text{eff}}(r_0) > 0$, the circular orbit represents a stable equilibrium configuration: small radial perturbations induce harmonic oscillations about $r_0$.

##### 4. Inflection Point and Transition of Convexity
Setting $V''_{\text{eff}}(r) = 0$ in step 27 identifies the inflection radius:
$$
\begin{gather}
r_{\text{infl}} = \frac{3 L^2}{2 G M m^2} = \frac{3}{2} r_0 \tag{29}
\end{gather}
$$
For $r \in (0, r_{\text{infl}})$, $V''_{\text{eff}}(r) > 0$, meaning the potential is strictly convex (downward), forming the stable orbital well. For $r \in (r_{\text{infl}}, \infty)$, $V''_{\text{eff}}(r) < 0$, meaning the potential is concave (convex upward), asymptotically flattening towards the horizontal line $V = 0$.

### Structural Engineering: Quartic Deflection Profiles of an Elastic Beam
In civil and mechanical structural analysis, the transverse deflection $w(x)$ of a uniform horizontal elastic girder of length $L > 0$ clamped at the left boundary $x = 0$ and simply supported at the right boundary $x = L$ under a uniform load $q_0 > 0$ is governed by the fourth-order polynomial:
$$
\begin{gather}
w(x) := \frac{q_0}{48 E I} \left(2x^4 - 3L x^3 + L^3 x\right) \tag{30}
\end{gather}
$$
where $E > 0$ is Young's modulus of elasticity, $I > 0$ is the cross-sectional area moment of inertia, and $x \in [0, L]$. Structural safety requires determining the point of maximum downward deflection, the distribution of bending moments, and the inflection point where internal stress reverses direction.

##### 1. Boundary Anchors and Kinematic Restraints
Evaluating step 30 at the beam boundaries:
- At the clamped clamp root $x = 0$: $w(0) = 0$.
- At the pinned roller support $x = L$: $w(L) = \frac{q_0}{48 E I}(2L^4 - 3L^4 + L^4) = 0$.

##### 2. First-Derivative Analysis: Location of Maximum Sag
The slope of the deflected centerline is given by $w'(x)$:
$$
\begin{gather}
w'(x) = \frac{q_0}{48 E I} \left(8x^3 - 9L x^2 + L^3\right) \tag{31}
\end{gather}
$$
At the clamped boundary $x = 0$, $w'(0) = \frac{q_0 L^3}{48 E I} > 0$. At the pinned boundary $x = L$, evaluating step 31 yields $w'(L) = \frac{q_0}{48 E I}(8L^3 - 9L^3 + L^3) = 0$.

Factoring the cubic polynomial in step 31 using the root at $x = L$:
$$
\begin{gather}
8x^3 - 9L x^2 + L^3 = (x - L)(8x^2 - L x - L^2) \tag{32}
\end{gather}
$$
Setting the quadratic factor to zero yields the interior stationary point in $(0, L)$:
$$
\begin{gather}
x^* = \frac{L + \sqrt{L^2 - 4(8)(-L^2)}}{16} = \frac{1 + \sqrt{33}}{16} L \approx 0.4215 L \tag{33}
\end{gather}
$$
On $[0, x^*)$, $w'(x) > 0$; on $(x^*, L)$, $w'(x) < 0$. By the first-derivative criterion, the maximum transverse displacement occurs at $x^* \approx 0.4215 L$, shifting towards the less rigid pinned end.

##### 3. Second-Derivative Analysis: Bending Moment and Inflection Stress Inversion
According to Euler-Bernoulli beam theory, the internal bending moment $M(x)$ satisfies $M(x) = E I w''(x)$. Differentiating step 31 yields:
$$
\begin{gather}
w''(x) = \frac{q_0}{48 E I} \left(24x^2 - 18L x\right) = \frac{q_0 x}{8 E I} \left(4x - 3L\right) \tag{34}
\end{gather}
$$
Inside the open span $(0, L)$, step 34 vanishes at a unique point:
$$
\begin{gather}
x_{\text{infl}} = \frac{3}{4} L = 0.75 L \tag{35}
\end{gather}
$$
Evaluating the second derivative across the partition:
- For $x \in (0, 0.75 L)$: $4x - 3L < 0$, whence $w''(x) < 0$. The beam is concave (convex upward), experiencing negative bending moment with tension along the upper fibers.
- For $x \in (0.75 L, L)$: $4x - 3L > 0$, whence $w''(x) > 0$. The beam is convex (convex downward), experiencing positive bending moment with tension along the lower fibers.

The point $x = 0.75 L$ is a genuine point of inflection where the internal bending moment vanishes identically.

### Biochemistry: Sigmoidal Allostery and Cooperativity in Enzyme Kinetics
In biochemistry and cellular biophysics, the initial catalytic velocity $v(S)$ of an allosteric multimeric enzyme displaying positive cooperativity is modeled by the Hill equation without logarithms:
$$
\begin{gather}
v(S) := \frac{V_{\max} S^2}{K^2 + S^2} \tag{36}
\end{gather}
$$
where $S \in [0, \infty)$ denotes substrate concentration, $V_{\max} > 0$ is the limiting saturated velocity, and $K > 0$ represents the apparent dissociation constant (the half-saturation concentration where $v(K) = \frac{1}{2} V_{\max}$).

##### 1. Domain Limits and Asymptotic Saturation
Evaluating boundary conditions on $[0, \infty)$:
- At zero substrate concentration: $v(0) = 0$.
- As $S \to \infty$:
  $$
  \begin{gather}
  \lim_{S \to \infty} v(S) = \lim_{S \to \infty} \frac{V_{\max}}{1 + \frac{K^2}{S^2}} = V_{\max} \tag{37}
  \end{gather}
  $$
  The horizontal line $v = V_{\max}$ is a horizontal asymptote.

##### 2. First-Derivative Analysis: Monotonicity
Differentiating step 36 via the quotient rule:
$$
\begin{gather}
v'(S) = V_{\max} \frac{2S(K^2 + S^2) - S^2(2S)}{(K^2 + S^2)^2} = \frac{2 V_{\max} K^2 S}{(K^2 + S^2)^2} \tag{38}
\end{gather}
$$
Because $V_{\max}, K > 0$, for all $S > 0$:
$$
\begin{gather}
v'(S) > 0 \tag{39}
\end{gather}
$$
Step 39 proves that catalytic throughput increases strictly monotonically across all substrate levels. At the origin, $v'(0) = 0$, meaning the velocity curve leaves the origin horizontally rather than with a steep hyperbolic slope.

##### 3. Second-Derivative Analysis: The Inflection Threshold of Ultrasensitivity
Differentiating step 38 yields:
$$
\begin{gather}
v''(S) = 2 V_{\max} K^2 \frac{(K^2 + S^2)^2 - S \cdot 2(K^2 + S^2)(2S)}{(K^2 + S^2)^4} = \frac{2 V_{\max} K^2 (K^2 - 3S^2)}{(K^2 + S^2)^3} \tag{40}
\end{gather}
$$
Setting $v''(S) = 0$ in step 40 produces the critical substrate threshold:
$$
\begin{gather}
K^2 - 3S^2 = 0 \implies S^* = \frac{K}{\sqrt{3}} \tag{41}
\end{gather}
$$
Analyzing the sign partition of $v''(S)$ across $S^*$:
- For $S \in \left(0, \frac{K}{\sqrt{3}}\right)$: $K^2 - 3S^2 > 0$, so $v''(S) > 0$. The reaction velocity is strictly convex (downward). The catalytic throughput accelerates, displaying an ultrasensitive threshold switch.
- For $S \in \left(\frac{K}{\sqrt{3}}, \infty\right)$: $K^2 - 3S^2 < 0$, so $v''(S) < 0$. The reaction velocity is strictly concave, decelerating as the active sites become saturated.

The point $S^* = K/\sqrt{3}$ is an inflection point representing the concentration of maximum marginal sensitivity, where $v'(S)$ attains its global maximum:
$$
\begin{gather}
v'\left(\frac{K}{\sqrt{3}}\right) = \frac{2 V_{\max} K^2 \left(\frac{K}{\sqrt{3}}\right)}{\left(K^2 + \frac{K^2}{3}\right)^2} = \frac{\frac{2}{\sqrt{3}} V_{\max} K^3}{\frac{16}{9} K^4} = \frac{3\sqrt{3}}{8} \frac{V_{\max}}{K} \approx 0.6495 \frac{V_{\max}}{K} \tag{42}
\end{gather}
$$

### Aerodynamics: Pressure Coefficient Distribution Across an Aerodynamic Venturi
In fluid dynamics and aerodynamic duct design, the non-dimensional surface pressure coefficient $C_p(x)$ along the symmetric throat of a planar contraction channel is governed by the rational flow-acceleration model:
$$
\begin{gather}
C_p(x) := 1 - \left(\frac{x^2 - a^2}{x^2 + a^2}\right)^2 \tag{43}
\end{gather}
$$
where $a > 0$ defines the geometric throat half-width and $x \in \mathbb{R}$ is the longitudinal channel coordinate.

##### 1. Symmetry and Asymptotic Recovery
Inspecting algebraic symmetries:
- Even Symmetry: $C_p(-x) = C_p(x)$. The pressure distribution is symmetric about the throat plane $x = 0$.
- Asymptotic Far-Field: As $x \to \pm\infty$:
  $$
  \begin{gather}
  \lim_{x \to \pm\infty} \frac{x^2 - a^2}{x^2 + a^2} = 1 \implies \lim_{x \to \pm\infty} C_p(x) = 1 - 1^2 = 0 \tag{44}
  \end{gather}
  $$
  The horizontal line $C_p = 0$ is a horizontal asymptote.

##### 2. First-Derivative Analysis: Suction Peaks and Stagnation Points
Let $u(x) := \frac{x^2 - a^2}{x^2 + a^2} = 1 - \frac{2a^2}{x^2 + a^2}$. Then $C_p(x) = 1 - u(x)^2$. Differentiating yields:
$$
\begin{gather}
u'(x) = \frac{4a^2 x}{(x^2 + a^2)^2} \tag{45}
\end{gather}
$$
whence:
$$
\begin{gather}
C_p'(x) = -2 u(x) u'(x) = -2 \left(\frac{x^2 - a^2}{x^2 + a^2}\right) \left(\frac{4a^2 x}{(x^2 + a^2)^2}\right) = -\frac{8a^2 x (x - a)(x + a)}{(x^2 + a^2)^3} \tag{46}
\end{gather}
$$
The stationary points occur where $C_p'(x) = 0$, identifying three critical locations: $x = -a$, $x = 0$, and $x = a$.

Evaluating the sign of $C_p'(x)$ across these intervals:
- On $(-\infty, -a)$: $x < 0, x - a < 0, x + a < 0$, so $C_p'(x) > 0$. $C_p$ increases strictly from $0$ to $C_p(-a) = 1$.
- On $(-a, 0)$: $x < 0, x - a < 0, x + a > 0$, so $C_p'(x) < 0$. $C_p$ decreases strictly from $1$ to $C_p(0) = 0$.
- On $(0, a)$: $x > 0, x - a < 0, x + a > 0$, so $C_p'(x) > 0$. $C_p$ increases strictly from $0$ to $C_p(a) = 1$.
- On $(a, \infty)$: All factors are positive, so $C_p'(x) < 0$. $C_p$ decreases strictly from $1$ towards $0$.

By the first-derivative criterion:
- $x = \pm a$ are strict global maxima with value $C_p(\pm a) = 1$ (complete stagnation recovery).
- $x = 0$ is a strict local minimum with value $C_p(0) = 0$ (maximum throat dynamic suction).

### Relativistic Kinematics: Longitudinal Acceleration and Inertial Singularities
In relativistic mechanics, an elementary particle of rest mass $m_0 > 0$ subjected to a constant electrostatic force $F_0 > 0$ along a linear accelerator achieves a velocity $v \in (-c, c)$, where $c > 0$ denotes the speed of light. Its longitudinal acceleration $a(v)$ satisfies:
$$
\begin{gather}
a(v) := \frac{F_0}{m_0} \left(1 - \frac{v^2}{c^2}\right)^{3/2} \tag{47}
\end{gather}
$$
The problem requires analyzing how relativistic mass increase suppresses acceleration as the particle approaches the cosmic speed limit.

##### 1. Domain Boundaries and Symmetry
The physical velocity domain is the open interval $(-c, c)$.
- Even Symmetry: $a(-v) = a(v)$. Acceleration is symmetric with respect to velocity reversals.
- Boundary Asymptotics: As $v \to \pm c^-$:
  $$
  \begin{gather}
  \lim_{v \to c^-} a(v) = 0, \quad \lim_{v \to -c^+} a(v) = 0 \tag{48}
  \end{gather}
  $$

##### 2. First-Derivative Analysis: Maximum Rest Acceleration
Differentiating step 47 with respect to velocity $v$:
$$
\begin{gather}
a'(v) = \frac{F_0}{m_0} \cdot \frac{3}{2} \left(1 - \frac{v^2}{c^2}\right)^{1/2} \left(-\frac{2v}{c^2}\right) = -\frac{3 F_0}{m_0 c^2} v \sqrt{1 - \frac{v^2}{c^2}} \tag{49}
\end{gather}
$$
Setting $a'(v) = 0$ yields a unique stationary point inside $(-c, c)$:
$$
\begin{gather}
v = 0 \tag{50}
\end{gather}
$$
For $v \in (-c, 0)$, $a'(v) > 0$, so acceleration is strictly increasing. For $v \in (0, c)$, $a'(v) < 0$, so acceleration is strictly decreasing. Consequently, the rest frame $v = 0$ provides the strict global maximum of acceleration:
$$
\begin{gather}
a_{\max} = a(0) = \frac{F_0}{m_0} \tag{51}
\end{gather}
$$

##### 3. Second-Derivative Analysis: Inflection Points and Convexity Regimes
Differentiating step 49 via the product rule:
$$
\begin{gather}
a''(v) = -\frac{3 F_0}{m_0 c^2} \left[\sqrt{1 - \frac{v^2}{c^2}} + v \cdot \frac{-\frac{v}{c^2}}{\sqrt{1 - \frac{v^2}{c^2}}}\right] = -\frac{3 F_0}{m_0 c^2 \sqrt{1 - \frac{v^2}{c^2}}} \left(1 - \frac{2v^2}{c^2}\right) \tag{52}
\end{gather}
$$
Setting $a''(v) = 0$ in step 52 produces the relativistic inflection velocities:
$$
\begin{gather}
1 - \frac{2v^2}{c^2} = 0 \implies v_{\text{infl}} = \pm \frac{c}{\sqrt{2}} \tag{53}
\end{gather}
$$
Analyzing the sign of $a''(v)$:
- For $v \in \left(-\frac{c}{\sqrt{2}}, \frac{c}{\sqrt{2}}\right)$: $1 - \frac{2v^2}{c^2} > 0$, whence $a''(v) < 0$. The acceleration profile is strictly concave (convex upward), curving downwards from its maximum peak at $v = 0$.
- For $v \in \left(-c, -\frac{c}{\sqrt{2}}\right) \cup \left(\frac{c}{\sqrt{2}}, c\right)$: $1 - \frac{2v^2}{c^2} < 0$, whence $a''(v) > 0$. The acceleration curve is strictly convex (downward), flattening asymptotically as it approaches zero at the boundary $v \to \pm c$.

The velocities $v = \pm c/\sqrt{2}$ mark inflection points where the relativistic deceleration rate achieves its steepest magnitude.
