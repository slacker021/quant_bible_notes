---
dg-publish: true
---
# Finite Increments and Local Polynomial Approximations
In [[Chapter 1 - Differentiable Functions|Chapter 1]], differentiability was formulated through the geometry of local linear approximation: a mapping is differentiable at an anchor point if its functional variation decomposes into a continuous linear transformation and a residual that vanishes strictly faster than the perturbation of the argument. In [[Chapter 2 - The Basic Rules of Differentiation|Chapter 2]], the algebraic infrastructure of differentiation was developed, establishing operational formulas for combinations, products, compositions, inverses, and higher-order jets. Yet, despite their computational utility, those results remain strictly pointwise and local. A difference quotient evaluated at an isolated point $x_0$ yields information only within an arbitrarily small neighborhood of that point. Pointwise derivatives alone cannot determine whether a function increases globally across an interval, whether it assumes an extremal value, or how closely a higher-order polynomial tracks the global trajectory of the curve.

### From Pointwise Rates to Global Functional Deformation
Consider a real-valued mapping $f: [a, b] \to \mathbb{R}$. If one only knows that $f'(x) > 0$ at a single anchor point $x_0 \in (a, b)$, one may deduce that $f(x) > f(x_0)$ in an immediate right-sided neighborhood and $f(x) < f(x_0)$ in an immediate left-sided neighborhood. However, this pointwise condition contains no information regarding the global ordering of values: $f$ could plummet precipitously outside that immediate neighborhood. 

To bridge this gap, real analysis establishes the *theorems on finite increments*. These theorems reveal that under suitable topological conditions, the macroscopic chord slope across a finite interval:
$$
\begin{gather}
\frac{f(b) - f(a)}{b - a} \tag{1}
\end{gather}
$$
is not merely an arbitrary average, but is realized identically as the instantaneous tangent slope $f'(\xi)$ at some intermediate interior point $\xi \in (a, b)$. Consequently, knowing that a derivative is non-negative everywhere on an interval guarantees that the functional increment $f(b) - f(a)$ cannot be negative, welding local direction to global monotonicity.

### The Topological Foundations: Compactness, Extremal Values, and Differentiability
The transition from local rates to global increments cannot occur within a purely algebraic framework. It demands the full topological machinery of the real continuum developed in [[Chapter 1 - Basic Properties of Real Numbers|Module 2]] and [[Chapter 2 - Properties of Continuous Functions|Module 4]]. 

Specifically, the finite-increment theorems depend essentially on the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem]]: every continuous real-valued function defined on a compact interval $[a, b] \subset \mathbb{R}$ is bounded and attains its global maximum and minimum values. If a function attains an extremum at an interior point where a tangent line exists, the geometric inclination of that tangent line must be horizontal. This coupling between compactness, extremal attainment, and differential smoothness provides the structural engine for the entirety of classical differential analysis.

---
# Extremal Topologies and Stationary Points

### Local Extrema on General Subsets
Let $E \subseteq \mathbb{R}$ be an arbitrary non-empty subset of the real numbers, and let $f: E \to \mathbb{R}$ be a real-valued function defined on $E$: 
$$
\begin{gather}
\textbf{Definition: Local Extrema} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ and let } f: E \to \mathbb{R}. \text{ A point } x_0 \in E \text{ is called a:} \\[2mm]
1. \text{ Local maximum of } f \text{ if there exists a neighborhood } U_E(x_0) := U(x_0) \cap E \text{ such that:} \\[2mm]
\forall x \in U_E(x_0), \quad f(x) \le f(x_0) \\[3.5mm]
2. \text{ Local minimum of } f \text{ if there exists a neighborhood } U_E(x_0) := U(x_0) \cap E \text{ such that:} \\[2mm]
\forall x \in U_E(x_0), \quad f(x) \ge f(x_0) \\[3.5mm]
3. \text{ Strict local maximum of } f \text{ if for all } x \in \mathring{U}_E(x_0) := (U(x_0) \setminus \{x_0\}) \cap E: \\[2mm]
f(x) < f(x_0) \\[3.5mm]
4. \text{ Strict local minimum of } f \text{ if for all } x \in \mathring{U}_E(x_0) := (U(x_0) \setminus \{x_0\}) \cap E: \\[2mm]
f(x) > f(x_0)
\end{gather}
$$
The generic term *local extremum* denotes either a local maximum or a local minimum, and the corresponding value $f(x_0)$ is termed a *local extreme value* of $f$.

### Topological Classification: Interior vs. Boundary Points
The qualitative nature of an extremum depends profoundly on the topological position of $x_0$ relative to the domain $E$: 
$$
\begin{gather}
\textbf{Definition: Interior Extremum} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ and let } f: E \to \mathbb{R}. \text{ A local extremum } x_0 \in E \text{ is termed an} \\[2mm]
\textit{interior extremum} \text{ if the point } x_0 \text{ is an accumulation point of both directional subsets:} \\[3.5mm]
E^- := \{x \in E \mid x < x_0\} \quad \text{and} \quad E^+ := \{x \in E \mid x > x_0\}
\end{gather}
$$

If $E$ is an open interval $(a, b)$, every point in $E$ is an interior point, and hence every local extremum on an open interval is automatically an interior extremum. Conversely, if $E$ is a closed interval $[a, b]$, the boundary endpoints $a$ and $b$ fail the interiority condition: at $x = a$, the set $E^-$ is empty, rendering $a$ a one-sided boundary extremum rather than an interior extremum.

>[!example]- Example: Topological Anatomy of Extrema on Piecewise Domains
>To illustrate the distinction between interior extrema, boundary extrema, and non-strict extrema, consider the piecewise mapping $f: [-1, \infty) \to \mathbb{R}$ defined by:
>$$
>\begin{gather}
>f(x) := \begin{cases} x^2, & -1 \le x < 2 \\ 4, & x \ge 2 \end{cases} \tag{2}
>\end{gather}
>$$
>Evaluating the local behavior across its domain reveals four distinct structural classes:
>1. At $x = -1$: For all $x \in [-1, 0)$, $f(x) = x^2 \le (-1)^2 = 1$. Thus, $x = -1$ is a strict local maximum. However, because the domain contains no points to the left of $-1$, the directional set $E^-$ is empty; hence $x = -1$ is a boundary extremum, not an interior extremum.
>2. At $x = 0$: The point $0$ is an interior accumulation point, with $E^- = [-1, 0)$ and $E^+ = (0, \infty)$. Because $f(x) = x^2 > 0 = f(0)$ for all $x \in (-1, 1) \setminus \{0\}$, $x = 0$ is a strict interior local minimum.
>3. At $x = 2$: For all $x \in (0, 2)$, $f(x) = x^2 < 4$, while for $x \ge 2$, $f(x) = 4$. Consequently, $f(x) \le 4$ throughout the entire neighborhood $(0, 3) \cap E$. The point $x = 2$ is a non-strict local maximum. It is an interior extremum because $E^-$ and $E^+$ are both non-empty.
>4. For all $x > 2$: In an open neighborhood $(2, \infty)$, the function is identically constant: $f(x) = 4$. Therefore, every point $x \in (2, \infty)$ is simultaneously a local maximum and a local minimum, exhibiting a degenerate plateau of non-strict extrema.

### Fermat's Interior Extremum Lemma
The fundamental analytical condition governing differentiable functions at interior extrema was formulated by Pierre de Fermat in 1636:
$$
\begin{gather}
\textbf{Fermat's Interior Extremum Lemma: } \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ and let } f: E \to \mathbb{R} \text{ be a function defined on } E. \\[2mm]
\text{If } x_0 \in E \text{ is an interior extremum of } f, \text{ and if } f \text{ is differentiable at } x_0, \\[2mm]
\text{then the derivative of } f \text{ at } x_0 \text{ vanishes identically:} \\[3.5mm]
f'(x_0) = 0
\end{gather}
$$
(see [[Proof of Fermat's Interior Extremum Lemma]])

In the language of differentials established in [[Chapter 1 - Differentiable Functions#The Differential Operator|Chapter 1]], Fermat's lemma asserts that at an interior extremum, the differential 1-form vanishes:
$$
\begin{gather}
df(x_0; h) = 0 \cdot h \equiv 0 \tag{3}
\end{gather}
$$
Geometrically, the tangent line to the graph of $f$ at the point $(x_0, f(x_0))$ is parallel to the horizontal coordinate axis.

>[!danger]+ Intuition: The Mechanical Principle of Virtual Work
>The analytical origin of Fermat's lemma is transparent when viewed through one-sided difference quotients. Suppose $x_0$ is an interior local maximum. If an observer perturbs the argument to the right by $h > 0$, the function must decrease or stay flat: $\Delta f = f(x_0 + h) - f(x_0) \le 0$, forcing the right-sided derivative to be non-positive: $f'_+(x_0) \le 0$. Conversely, perturbing to the left by $h < 0$ means the displacement is negative while the increment remains non-positive, forcing the left-sided derivative to be non-negative: $f'_-(x_0) \ge 0$. 
>
>If the function is differentiable at $x_0$, these two directional rates must coincide: $f'_-(x_0) = f'_+(x_0) = f'(x_0)$. The only real number that is simultaneously non-negative and non-positive is zero. Physically, this corresponds to the principle of virtual work in classical mechanics: at a stable equilibrium configuration within an energy potential, the virtual forces vanish.

### Necessary vs. Sufficient Conditions and Pathological Stationary Points
Points at which the derivative of a differentiable function vanishes are called *stationary points* (or *critical points*). It is critical to recognize that Fermat's condition $f'(x_0) = 0$ is strictly a *necessary* condition for an interior extremum, not a *sufficient* one.

>[!warning]+ Warning: The Fallacy of Stationary Inversion
>The vanishing of the derivative does not imply the presence of an extremum:
>1. Monotonic Inflection: The cubic monomial $f(x) = x^3$ is differentiable everywhere on $\mathbb{R}$, and its derivative $f'(x) = 3x^2$ vanishes at $x_0 = 0$. However, $f(x) < 0$ for all $x < 0$ and $f(x) > 0$ for all $x > 0$. The point $x_0 = 0$ is a point of strictly increasing inflection, not an extremum.
>2. Boundary Neglect: For the linear identity function $f(x) = x$ on the compact domain $[0, 1]$, the global minimum occurs at $x = 0$ and the global maximum occurs at $x = 1$. Yet the derivative satisfies $f'(x) = 1 \neq 0$ everywhere on $[0, 1]$. Fermat's lemma does not apply because neither $0$ nor $1$ is an interior point of $[0, 1]$.
>3. Non-Differentiable Extrema: The absolute value function $f(x) = |x|$ has a strict interior global minimum at $x_0 = 0$. However, as shown in Chapter 1, $f'_-(0) = -1 \neq +1 = f'_+(0)$, so $f'(0)$ fails to exist. Extrema can occur at singular points where differentiability breaks down.

### Rolle's Theorem: The Topological Bridge
By combining Fermat's lemma with the global topological compactness of closed intervals, Michel Rolle established the first existence theorem for stationary points in 1691:
$$
\begin{gather}
\textbf{Rolle's Mean Value Theorem: } \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a function satisfying the following three hypotheses:} \\[2mm]
1. \text{ The function } f \text{ is continuous on the closed compact interval } [a, b]; \\[2mm]
2. \text{ The function } f \text{ is differentiable on the open interior interval } (a, b); \\[2mm]
3. \text{ The function assumes equal values at the domain endpoints:} \\[3.5mm]
f(a) = f(b) \\[3.5mm]
\text{Then there exists at least one intermediate point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
f'(\xi) = 0
\end{gather}
$$
(see [[Proof of Rolle's Theorem]])

The architecture of the proof illustrates the interplay between topology and differential calculus:
- By the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem]], continuity on the compact set $[a, b]$ guarantees that $f$ attains both a global maximum $M := \sup_{x \in [a, b]} f(x)$ and a global minimum $m := \inf_{x \in [a, b]} f(x)$.
- If $M = m$, $f$ is identically constant on $[a, b]$, whence $f'(x) = 0$ at every point $\xi \in (a, b)$.
- If $M > m$, the equality $f(a) = f(b)$ prevents both extremal values from being realized exclusively at the boundary endpoints $\{a, b\}$. Thus, at least one extremum must be attained at an interior point $\xi \in (a, b)$.
- Because $\xi$ is an interior extremum and $f$ is differentiable on $(a, b)$, Fermat's lemma forces $f'(\xi) = 0$.

### Generalized Rolle's Theorem and Polynomial Root Interlacing
Rolle's theorem extends directly to functions possessing multiple roots and to higher-order differential systems:
$$
\begin{gather}
\textbf{Generalized Multi-Point Rolle's Theorem: } \\[5mm]
\text{Let } n \in \mathbb{N}, \text{ and let } f: [a, b] \to \mathbb{R} \text{ be a function such that } f \in C^{n-1}[a, b] \\[2mm]
\text{and } f^{(n)}(x) \text{ exists for all } x \in (a, b). \text{ If } f \text{ vanishes at } (n + 1) \text{ distinct points} \\[2mm]
a \le x_0 < x_1 < \dots < x_n \le b, \text{ such that } f(x_k) = 0 \text{ for } k = 0, 1, \dots, n, \\[2mm]
\text{then there exists at least one interior point } \xi \in (x_0, x_n) \text{ such that:} \\[3.5mm]
f^{(n)}(\xi) = 0
\end{gather}
$$
(see [[Proof of the Generalized Multi-Point Rolle Theorem]])

This multi-point formulation immediately yields fundamental algebraic consequences regarding the distribution of roots for real polynomials:
$$
\begin{gather}
\textbf{Proposition: Root Interlacing for Differentiable Polynomials} \\[5mm]
\text{Let } P(x) \text{ be a non-constant polynomial with real coefficients. Then:} \\[2mm]
1. \text{ Between any two consecutive real roots of } P(x), \text{ there exists an odd number} \\[2mm]
\text{(and hence at least one) of real roots of its derivative } P'(x); \\[3.5mm]
2. \text{ If } x_0 \text{ is a root of } P(x) \text{ of multiplicity } m \ge 2, \text{ then } x_0 \text{ is a root of } P'(x) \\[2mm]
\text{of multiplicity exactly } (m - 1); \\[3.5mm]
3. \text{ If all roots of } P(x) \text{ are real and distinct, then all roots of } P'(x) \text{ are real, distinct,} \\[2mm]
\text{and strictly interlace the roots of } P(x).
\end{gather}
$$
(see [[Proof of Polynomial Root Interlacing and Multiplicity Reduction]])

---

# The Finite-Increment Theorems of Differential Calculus

### Lagrange's Mean Value Theorem
While Rolle's theorem requires the rigid condition $f(a) = f(b)$, Joseph-Louis Lagrange recognized in 1797 that subtracting an affine secant correction yields an identity for generic differentiable functions:
$$
\begin{gather}
\textbf{Theorem: Lagrange's Finite-Increment Theorem} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a function satisfying:} \\[2mm]
1. \text{ The function } f \text{ is continuous on the closed compact interval } [a, b]; \\[2mm]
2. \text{ The function } f \text{ is differentiable on the open interior interval } (a, b). \\[3.5mm]
\text{Then there exists at least one interior point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
f(b) - f(a) = f'(\xi)(b - a)
\end{gather}
$$
(see [[Proof of Lagrange's Finite-Increment Theorem]])

Expressing the displacement of the argument as $h := b - a$ and parametrizing the intermediate point as $\xi = a + \theta h$ with $\theta \in (0, 1)$, Lagrange's theorem assumes the classical finite-increment formulation:
$$
\begin{gather}
\Delta f(a; h) = f'(a + \theta h) h, \quad \theta \in (0, 1) \tag{4}
\end{gather}
$$

The proof proceeds by defining the auxiliary secant-deviation function:
$$
\begin{gather}
F(x) := f(x) - f(a) - \frac{f(b) - f(a)}{b - a}(x - a) \tag{5}
\end{gather}
$$
Because $F(a) = 0$ and $F(b) = 0$, $F(x)$ satisfies all three hypotheses of Rolle's theorem on $[a, b]$. Differentiating via the linearity rule established in [[Chapter 2 - The Basic Rules of Differentiation#Linearity of the Differential Operator|Chapter 2]] yields $F'(\xi) = f'(\xi) - \frac{f(b)-f(a)}{b-a} = 0$, producing step 4.

>[!info]+ Remark: Geometric Meaning of the Mean Value Theorem
>Geometrically, the ratio $\frac{f(b) - f(a)}{b - a}$ is the slope of the secant chord joining the boundary points $A = (a, f(a))$ and $B = (b, f(b))$ on the graph of $f$. Lagrange's theorem asserts that under continuous and differentiable conditions, there must exist at least one intermediate point $(\xi, f(\xi))$ where the local tangent line is parallel to the chord $AB$.

### Kinematic Interpretation and the Multivariable Breakdown
Kinematically, if $x$ represents elapsed time and $f(x)$ denotes the rectilinear spatial position of a particle along a one-dimensional coordinate axis, the quotient $\frac{f(b) - f(a)}{b - a}$ represents the *average velocity* over the temporal interval $[a, b]$. Lagrange's theorem asserts that the instantaneous velocity $v(\xi) = f'(\xi)$ must match the average velocity at some intermediate epoch $\xi \in (a, b)$.

>[!warning]+ Warning: Breakdown of the Mean Value Theorem for Vector-Valued Mappings
>It is essential to understand that Lagrange's theorem is strictly a scalar, one-dimensional phenomenon. It fails for vector-valued mappings $\vec{r}: [a, b] \to \mathbb{R}^n$ when $n \ge 2$.
>
>To observe this breakdown, consider a point mass undergoing uniform circular motion in the Euclidean plane $\mathbb{R}^2$ over the time interval $[0, 2\pi]$:
>$$
>\begin{gather}
>\vec{r}(t) := \big(\cos(t), \sin(t)\big) \tag{6}
>\end{gather}
>$$
>The net spatial displacement over the closed orbit is identically zero:
>$$
>\begin{gather}
>\vec{r}(2\pi) - \vec{r}(0) = (1, 0) - (1, 0) = (0, 0) \tag{7}
>\end{gather}
>$$
>If Lagrange's theorem held for vector mappings, there would exist an epoch $\xi \in (0, 2\pi)$ such that:
>$$
>\begin{gather}
>\vec{r}(2\pi) - \vec{r}(0) = \vec{r}'(\xi)(2\pi - 0) \implies \vec{r}'(\xi) = (0, 0) \tag{8}
>\end{gather}
>$$
>However, the instantaneous velocity vector is given by $\vec{r}'(t) = (-\sin(t), \cos(t))$, whose Euclidean speed is constant:
>$$
>\begin{gather}
>\|\vec{r}'(t)\| = \sqrt{(-\sin(t))^2 + (\cos(t))^2} = 1 \neq 0, \quad \forall t \in [0, 2\pi] \tag{9}
>\end{gather}
>$$
>The instantaneous velocity is never zero; hence no intermediate point $\xi$ satisfies the vector Lagrange equation. In higher dimensions, the mean value equality must be replaced by the *Mean Value Inequality*: $\|\vec{r}(b) - \vec{r}(a)\| \le \sup_{\xi \in (a, b)} \|\vec{r}'(\xi)\| (b - a)$.

### The Monotonicity Criterion for Differentiable Functions
Lagrange's finite-increment theorem converts infinitesimal slope information into global inequality bounds:
$$
\begin{gather}
\textbf{Corollary: The Monotonicity Criterion for Differentiable Functions} \\[5mm]
\text{Let } f: \langle a, b \rangle \to \mathbb{R} \text{ be a function differentiable on an arbitrary interval } \langle a, b \rangle. \\[2mm]
1. \text{ The function } f \text{ is non-decreasing on } \langle a, b \rangle \text{ if and only if } f'(x) \ge 0 \text{ for all } x \in \langle a, b \rangle; \\[2mm]
2. \text{ The function } f \text{ is non-increasing on } \langle a, b \rangle \text{ if and only if } f'(x) \le 0 \text{ for all } x \in \langle a, b \rangle; \\[2mm]
3. \text{ If } f'(x) > 0 \text{ for all } x \in \langle a, b \rangle, \text{ then } f \text{ is strictly increasing on } \langle a, b \rangle; \\[2mm]
4. \text{ If } f'(x) < 0 \text{ for all } x \in \langle a, b \rangle, \text{ then } f \text{ is strictly decreasing on } \langle a, b \rangle.
\end{gather}
$$
(see [[Proof of the Monotonicity Criterion for Differentiable Functions]])

The proof follows directly from step 4: for any two points $x_1 < x_2$ in the interval, $f(x_2) - f(x_1) = f'(\xi)(x_2 - x_1)$ for some $\xi \in (x_1, x_2)$. Because $(x_2 - x_1) > 0$, the algebraic sign of $f(x_2) - f(x_1)$ is identical to the algebraic sign of $f'(\xi)$.

### The Rigid Constancy Identity and Uniqueness of Primitives
A fundamental question of analysis is whether a rate of change of zero forces absolute immobility:
$$
\begin{gather}
\textbf{Corollary: Characterization of Constant Functions} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be a connected interval, and let } f: I \to \mathbb{R} \text{ be differentiable on } I. \\[2mm]
\text{The function } f \text{ is identically constant on } I \text{ if and only if:} \\[3.5mm]
f'(x) = 0, \quad \forall x \in I
\end{gather}
$$
(see [[Proof of the Characterization of Constant Functions]])

>[!warning]+ Warning: The Essential Role of Domain Connectedness
>The requirement that the domain $I$ be a connected interval is indispensable. If the domain consists of disconnected components, a vanishing derivative implies constancy only on each individual component, not across the entire domain.
>
>For example, consider the signum function derivative on $E = \mathbb{R} \setminus \{0\} = (-\infty, 0) \cup (0, \infty)$ defined by $f(x) = \frac{x}{|x|}$. For all $x \neq 0$, $f(x)$ is locally constant, satisfying $f'(x) = 0$. However, $f(-1) = -1 \neq +1 = f(1)$; the function is not globally constant on $E$.

This constancy identity establishes the uniqueness of *primitives* (antiderivatives): if two functions $f$ and $g$ possess identical derivatives on a connected interval $I$ ($f'(x) = g'(x)$ for all $x \in I$), then their difference has a derivative that vanishes identically: $(f - g)'(x) = 0$. Thus, $f$ and $g$ differ by an additive constant:
$$
\begin{gather}
f(x) = g(x) + C \tag{10}
\end{gather}
$$

### Cauchy's Generalized Finite-Increment Theorem
To compare two functional variations simultaneously without requiring explicit parametrization by the independent argument, Augustin-Louis Cauchy generalized Lagrange's theorem to a pair of mappings:
$$
\begin{gather}
\textbf{Cauchy's Generalized Finite-Increment Theorem: } \\[5mm]
\text{Let } f, g: [a, b] \to \mathbb{R} \text{ be functions satisfying:} \\[2mm]
1. \text{ Both } f \text{ and } g \text{ are continuous on the closed compact interval } [a, b]; \\[2mm]
2. \text{ Both } f \text{ and } g \text{ are differentiable on the open interior interval } (a, b). \\[3.5mm]
\text{Then there exists at least one intermediate point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
\big(f(b) - f(a)\big) g'(\xi) = \big(g(b) - g(a)\big) f'(\xi)
\end{gather}
$$
(see [[Proof of Cauchy's Generalized Finite-Increment Theorem]])

If, in addition, $g'(x) \neq 0$ for all $x \in (a, b)$, then Rolle's theorem ensures that $g(b) - g(a) \neq 0$, allowing Cauchy's formula to be written as a ratio of incremental rates:
$$
\begin{gather}
\frac{f(b) - f(a)}{g(b) - g(a)} = \frac{f'(\xi)}{g'(\xi)} \tag{11}
\end{gather}
$$

The proof follows by applying Rolle's theorem to the auxiliary function:
$$
\begin{gather}
F(x) := \big(f(b) - f(a)\big) g(x) - \big(g(b) - g(a)\big) f(x) \tag{12}
\end{gather}
$$
Notice that setting $g(x) = x$ in step 11 immediately recovers Lagrange's Mean Value Theorem as a particular case.

Geometrically, consider the planar parametric curve $\vec{r}(t) = (g(t), f(t))$ for $t \in [a, b]$. The secant vector connecting the endpoints is $\Delta \vec{r} = (g(b) - g(a), f(b) - f(a))$. Cauchy's theorem asserts that there exists an interior parameter $\xi \in (a, b)$ such that the instantaneous tangent velocity vector $\vec{r}'(\xi) = (g'(\xi), f'(\xi))$ is collinear with the secant vector $\Delta \vec{r}$.

### The Darboux Intermediate-Value Property of Derivatives
In [[Chapter 2 - Properties of Continuous Functions#The Generalized Darboux Intermediate-Value Property|Module 4]], it was proven that every continuous function satisfies the intermediate-value property. In [[Chapter 2 - The Basic Rules of Differentiation#Pathological Class D^1 \setminus C^1: Differentiability Without Derivative Continuity|Chapter 2]], the pathological mapping $f(x) = x^2 \sin(1/x)$ demonstrated that a derivative $f'(x)$ can be wildly discontinuous. This raises a fundamental structural question: Can a derivative experience an arbitrary jump discontinuity?

Gaston Darboux proved in 1875 that the answer is negative: *all* derivatives—continuous or not—satisfy the intermediate-value property:
$$
\begin{gather}
\textbf{Darboux's Intermediate-Value Theorem for Derivatives: } \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a function differentiable on the closed interval } [a, b]. \\[2mm]
\text{If } f'(a) \neq f'(b), \text{ and if } \gamma \in \mathbb{R} \text{ is any real number lying strictly between } f'(a) \text{ and } f'(b), \\[2mm]
\text{then there exists at least one interior point } \xi \in (a, b) \text{ such that:} \\[3.5mm]
f'(\xi) = \gamma
\end{gather}
$$
(see [[Proof of Darboux's Intermediate-Value Theorem for Derivatives]])

Darboux's theorem establishes a profound rigidity principle for derivatives:
- A derivative can never have a *jump discontinuity* (a discontinuity of the first kind where one-sided limits exist but disagree).
- A derivative can never have a *removable discontinuity*.
- Consequently, if a derivative is discontinuous at a point, that discontinuity must be an *essential discontinuity* (a discontinuity of the second kind involving infinite oscillations or divergent limits).

### The Landau–Kolmogorov Derivative Norm Inequalities
By combining Taylor's expansions with the finite-increment bounds, Edmund Landau and Andrey Kolmogorov established optimal inequalities bounding intermediate derivative norms:
$$
\begin{gather}
\textbf{Theorem: Landau–Kolmogorov Derivative Inequalities} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be twice differentiable on an interval } I \subseteq \mathbb{R}, \text{ and let the supremum norms} \\[2mm]
\text{be denoted by } M_0 := \sup_{x \in I} |f(x)|, \quad M_1 := \sup_{x \in I} |f'(x)|, \quad M_2 := \sup_{x \in I} |f''(x)|. \\[3.5mm]
1. \text{ If } I = \mathbb{R} \text{ and } M_0, M_2 < \infty, \text{ then the first derivative is bounded by:} \\[2mm]
M_1 \le \sqrt{2 M_0 M_2} \\[3.5mm]
\text{where the constant } \sqrt{2} \text{ is sharp;} \\[3.5mm]
2. \text{ If } I \text{ is any interval of length } |I| \ge 2\sqrt{M_0/M_2}, \text{ then:} \\[2mm]
M_1 \le 2\sqrt{M_0 M_2} \\[3.5mm]
\text{where the constant } 2 \text{ is sharp;} \\[3.5mm]
3. \text{ More generally, if } f \in C^p(\mathbb{R}) \text{ with } M_0, M_p < \infty, \text{ then for all } 1 \le k < p: \\[2mm]
M_k \le 2^{\frac{k(p-k)}{2}} M_0^{1 - \frac{k}{p}} M_p^{\frac{k}{p}}
\end{gather}
$$
(see [[Proof of the Landau-Kolmogorov Derivative Inequalities]])

---
# Taylor's Formula and Higher-Order Residual Control

### The Jet Approximation Problem Beyond Affine Bounds
In Chapter 1, the differential $df(x_0; h) = f'(x_0)h$ was constructed as the unique linear map solving the first-order approximation problem:
$$
\begin{gather}
f(x) - \big(f(x_0) + f'(x_0)(x - x_0)\big) = o(x - x_0) \quad \text{as } x \to x_0 \tag{13}
\end{gather}
$$
When investigating higher-order dynamical sensitivities—such as mechanical curvature, acceleration gradients, and financial convexity—an affine approximation becomes insufficient. One seeks a polynomial of degree $n$:
$$
\begin{gather}
P_n(x_0; x) := c_0 + c_1(x - x_0) + c_2(x - x_0)^2 + \dots + c_n(x - x_0)^n \tag{14}
\end{gather}
$$
whose contact with $f$ at $x_0$ is of order $n$, meaning that the polynomial and its first $n$ derivatives coincide with those of $f$ at the anchor point $x_0$:
$$
\begin{gather}
P_n^{(k)}(x_0; x_0) = f^{(k)}(x_0), \quad \forall k \in \{0, 1, \dots, n\} \tag{15}
\end{gather}
$$
Differentiating the polynomial of step 14 shows that $P_n^{(k)}(x_0; x_0) = k! c_k$, which uniquely determines the coefficients:
$$
\begin{gather}
c_k = \frac{f^{(k)}(x_0)}{k!} \tag{16}
\end{gather}
$$
The resulting polynomial is the *Taylor polynomial of degree $n$* of $f$ centered at $x_0$:
$$
\begin{gather}
P_n(x_0; x) := \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k \tag{17}
\end{gather}
$$
The discrepancy between the actual function and its Taylor polynomial defines the *Taylor remainder of order $n$*:
$$
\begin{gather}
r_n(x_0; x) := f(x) - P_n(x_0; x) \tag{18}
\end{gather}
$$
The fundamental ambition of differential calculus is to obtain explicit, usable formulas for the residual $r_n(x_0; x)$.

### Taylor's Formula with the General Schlömilch–Roche Remainder
To derive a master representation for the remainder term, consider an auxiliary displacement function:
$$
\begin{gather}
F(t) := f(x) - \sum_{k=0}^n \frac{f^{(k)}(t)}{k!} (x - t)^k \tag{19}
\end{gather}
$$
Notice that $F(x) = 0$, while $F(x_0) = r_n(x_0; x)$. Differentiating $F(t)$ with respect to $t$ using the Leibniz product rule and chain rule reveals an exceptional telescoping cancellation:
$$
\begin{gather}
F'(t) = -\sum_{k=0}^n \frac{f^{(k+1)}(t)}{k!} (x - t)^k + \sum_{k=1}^n \frac{f^{(k)}(t)}{(k-1)!} (x - t)^{k-1} = -\frac{f^{(n+1)}(t)}{n!} (x - t)^n \tag{20}
\end{gather}
$$
By applying Cauchy's Generalized Mean Value Theorem to $F(t)$ and an auxiliary function $\phi(t)$, one obtains the master Schlömilch–Roche remainder formula:
$$
\begin{gather}
\textbf{Theorem: Taylor's Formula with General Remainder} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ have continuous derivatives up to order } n \text{ on a closed interval with} \\[2mm]
\text{endpoints } x_0 \text{ and } x, \text{ and suppose } f^{(n+1)} \text{ exists on the interior of this interval.} \\[2mm]
\text{Let } \phi \text{ be a function continuous on this closed interval and differentiable on its interior,} \\[2mm]
\text{with } \phi'(t) \neq 0 \text{ everywhere on the interior. Then there exists an intermediate point } \xi \\[2mm]
\text{strictly between } x_0 \text{ and } x \text{ such that:} \\[3.5mm]
r_n(x_0; x) = \frac{1}{n!} \frac{\phi(x) - \phi(x_0)}{\phi'(\xi)} f^{(n+1)}(\xi) (x - \xi)^n
\end{gather}
$$
(see [[Proof of Taylor's Formula with General Remainder]])

### Cauchy's Form of the Remainder
Selecting the linear scaling function $\phi(t) := x - t$, so that $\phi(x) - \phi(x_0) = -(x - x_0)$ and $\phi'(t) = -1$, specializes the general remainder into Cauchy's formula:
$$
\begin{gather}
\textbf{Corollary: Cauchy's Form of the Taylor Remainder} \\[5mm]
\text{Under the hypotheses of Taylor's theorem, there exists an intermediate point } \xi \text{ strictly} \\[2mm]
\text{between } x_0 \text{ and } x \text{ such that:} \\[3.5mm]
r_n(x_0; x) = \frac{1}{n!} f^{(n+1)}(\xi) (x - \xi)^n (x - x_0)
\end{gather}
$$
(see [[Proof of Cauchy's Form of the Taylor Remainder]])

Parametrizing $\xi$ as $\xi = x_0 + \theta(x - x_0)$ with $\theta \in (0, 1)$, Cauchy's remainder assumes the equivalent form:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{n!} (1 - \theta)^n (x - x_0)^{n+1} \tag{21}
\end{gather}
$$

### Lagrange's Form of the Remainder
Selecting the power function $\phi(t) := (x - t)^{n+1}$, so that $\phi(x) - \phi(x_0) = -(x - x_0)^{n+1}$ and $\phi'(t) = -(n+1)(x - t)^n$, yields the most widely utilized representation:
$$
\begin{gather}
\textbf{Corollary: Lagrange's Form of the Taylor Remainder} \\[5mm]
\text{Under the hypotheses of Taylor's theorem, there exists an intermediate point } \xi \text{ strictly} \\[2mm]
\text{between } x_0 \text{ and } x \text{ such that:} \\[3.5mm]
r_n(x_0; x) = \frac{f^{(n+1)}(\xi)}{(n + 1)!} (x - x_0)^{n+1}
\end{gather}
$$
(see [[Proof of Lagrange's Form of the Taylor Remainder]])

Parametrizing the intermediate point as $\xi = x_0 + \theta(x - x_0)$ with $\theta \in (0, 1)$ yields:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x - x_0)\big)}{(n + 1)!} (x - x_0)^{n+1} \tag{22}
\end{gather}
$$
Notice that for $n = 0$, step 22 reduces exactly to the Lagrange Mean Value Theorem: $f(x) - f(x_0) = f'(\xi)(x - x_0)$. Taylor's formula with the Lagrange remainder is thus the exact $n$-th order generalization of the mean value theorem.

### Asymptotic Bisection of the Lagrange Intermediate Point
A natural inquiry concerns the asymptotic location of the intermediate fraction $\theta = \theta(x)$ as $x \to x_0$:
$$
\begin{gather}
\textbf{Proposition: Asymptotic Limit of the Taylor Intermediate Fraction} \\[5mm]
\text{Let } f \text{ have continuous derivatives up to order } (n + 2) \text{ in a neighborhood of } x_0, \\[2mm]
\text{and suppose } f^{(n+2)}(x_0) \neq 0. \text{ In the Lagrange form of the remainder of order } n: \\[3.5mm]
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x)(x - x_0)\big)}{(n + 1)!} (x - x_0)^{n+1} \\[3.5mm]
\text{the intermediate parameter } \theta(x) \in (0, 1) \text{ satisfies the limiting behavior:} \\[3.5mm]
\lim_{x \to x_0} \theta(x) = \frac{1}{n + 2}
\end{gather}
$$
(see [[Proof of the Asymptotic Limit of the Taylor Intermediate Fraction]])

In particular, for the classical first-order Lagrange Mean Value Theorem ($n = 0$), step 22 satisfies:
$$
\begin{gather}
\lim_{x \to x_0} \theta(x) = \frac{1}{0 + 2} = \frac{1}{2} \tag{23}
\end{gather}
$$
The intermediate point $\xi$ asymptotically bisects the interval $[x_0, x]$ as the displacement vanishes.

### The Local Taylor Formula (Peano Form) and Polynomial Uniqueness
When global bounds on $f^{(n+1)}$ are unavailable, but $f$ is known to possess $n$ derivatives at the single anchor point $x_0$, one obtains the local Taylor formula with Peano's remainder:
$$
\begin{gather}
\textbf{Theorem: The Local Taylor Formula with Peano Remainder} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ have } x_0 \text{ as an accumulation point, and let } f: E \to \mathbb{R} \text{ possess derivatives} \\[2mm]
\text{up to order } n \ge 1 \text{ at } x_0. \text{ Then as } E \ni x \to x_0: \\[3.5mm]
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k + o\big((x - x_0)^n\big)
\end{gather}
$$
(see [[Proof of the Local Taylor Formula with Peano Remainder]])

Furthermore, this local asymptotic polynomial is unique:
$$
\begin{gather}
\textbf{Theorem: Uniqueness of Asymptotic Polynomials} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ with accumulation point } x_0, \text{ and suppose there exists a polynomial} \\[2mm]
P_n(x) = \sum_{k=0}^n c_k (x - x_0)^k \text{ such that } f(x) - P_n(x) = o\big((x - x_0)^n\big) \text{ as } x \to x_0. \\[2mm]
\text{Then } P_n(x) \text{ is uniquely determined; if } f \text{ has } n \text{ derivatives at } x_0, \text{ then:} \\[3.5mm]
c_k = \frac{f^{(k)}(x_0)}{k!}, \quad \forall k \in \{0, 1, \dots, n\}
\end{gather}
$$
(see [[Proof of the Uniqueness of Asymptotic Polynomials]])

### Parity Invariance of Taylor Polynomials
The algebraic symmetries of functions impose strict structural constraints on their Taylor polynomials:
$$
\begin{gather}
\textbf{Proposition: Parity Invariance of Taylor Expansions} \\[5mm]
\text{Let } f: (-r, r) \to \mathbb{R} \text{ be a function differentiable } n \text{ times at the origin } x_0 = 0. \\[2mm]
1. \text{ If } f \text{ is an even function } (f(-x) = f(x)), \text{ then for all odd integers } 2k + 1 \le n: \\[2mm]
f^{(2k+1)}(0) = 0 \\[2mm]
\text{and its Taylor polynomial contains exclusively even powers of } x; \\[3.5mm]
2. \text{ If } f \text{ is an odd function } (f(-x) = -f(x)), \text{ then for all even integers } 2k \le n: \\[2mm]
f^{(2k)}(0) = 0 \\[2mm]
\text{and its Taylor polynomial contains exclusively odd powers of } x.
\end{gather}
$$
(see [[Proof of the Parity Invariance of Taylor Expansions]])

### Higher-Order Finite Differences and Derivative Representation
The finite differences of order $k$ introduced in numerical calculus are connected to continuum derivatives via the mean value theorem:
$$
\begin{gather}
\textbf{Proposition: Finite Differences and Differential Representation} \\[5mm]
\text{Let } f \in C^{n-1}[a, b] \text{ with } f^{(n)} \text{ existing on } (a, b). \text{ Let } x_0, x_0 + nh \in [a, b]. \\[2mm]
1. \text{ The } n\text{-th forward finite difference } \Delta^n f(x_0; h^n) \text{ admits the representation:} \\[3.5mm]
\Delta^n f(x_0; h^n) = f^{(n)}(\xi) h^n \\[3.5mm]
\text{for some intermediate point } \xi \text{ in the convex hull of } \{x_0, x_0 + h, \dots, x_0 + nh\}; \\[3.5mm]
2. \text{ If } f^{(n)}(x_0) \text{ exists, then the } n\text{-th derivative is realized as the limit of finite differences:} \\[3.5mm]
f^{(n)}(x_0) = \lim_{h \to 0} \frac{\Delta^n f(x_0; h^n)}{h^n}
\end{gather}
$$
(see [[Proof of the Finite Difference Mean Value Representation]])

### Hermite–Lagrange Interpolation Error with Derivative Remainder
Polynomial interpolation matches functional values and derivatives across multiple discrete nodes:
$$
\begin{gather}
\textbf{Theorem: Hermite–Lagrange Interpolation Error Formula} \\[5mm]
\text{Let } x_1 < x_2 < \dots < x_p \text{ be distinct points in an interval } I, \text{ let } n_1, \dots, n_p \in \mathbb{N} \text{ with} \\[2mm]
\sum_{i=1}^p n_i = n, \text{ and let } f \in C^n(I). \text{ There exists a unique polynomial } H_{n-1}(x) \text{ of degree} \\[2mm]
\le n - 1 \text{ satisfying } H_{n-1}^{(k)}(x_i) = f^{(k)}(x_i) \text{ for } 0 \le k < n_i \text{ and } 1 \le i \le p. \\[2mm]
\text{For every } x \in I, \text{ there exists an intermediate point } \xi \text{ in the smallest interval containing} \\[2mm]
\{x, x_1, \dots, x_p\} \text{ such that the interpolation error satisfies:} \\[3.5mm]
f(x) - H_{n-1}(x) = \frac{\prod_{i=1}^p (x - x_i)^{n_i}}{n!} f^{(n)}(\xi)
\end{gather}
$$
(see [[Proof of the Hermite-Lagrange Interpolation Error Formula]])

Notice that when $p = 1$ (a single node $x_1 = x_0$ of multiplicity $n$), Hermite's formula reproduces Taylor's formula with the Lagrange form of the remainder. When all $n_i = 1$ (distinct interpolation nodes), it reproduces the classical Lagrange interpolation error formula.

---
### Canonical Maclaurin Expansions of Elementary Non-Logarithmic Systems
When the expansion anchor is the origin $x_0 = 0$, the Taylor formula is customarily termed the *Maclaurin formula*. 

##### 1. Circular Trigonometric Systems ($\sin x$ and $\cos x$)
In Chapter 2, the derivatives of the circular sine and cosine were determined to be periodic of period 4:
$$
\begin{gather}
\sin^{(k)}(x) = \sin\left(x + k\frac{\pi}{2}\right), \quad \cos^{(k)}(x) = \cos\left(x + k\frac{\pi}{2}\right) \tag{24}
\end{gather}
$$
Evaluating step 24 at $x_0 = 0$ reveals that $\sin^{(2m)}(0) = 0$, $\sin^{(2m+1)}(0) = (-1)^m$, while $\cos^{(2m)}(0) = (-1)^m$, $\cos^{(2m+1)}(0) = 0$. By applying Taylor's theorem with the Lagrange form of the remainder, one obtains:
$$
\begin{gather}
\sin(x) = \sum_{m=0}^n \frac{(-1)^m}{(2m + 1)!} x^{2m+1} + r_{2n+2}(0; x) \tag{25}
\end{gather}
$$
where the remainder satisfies:
$$
\begin{gather}
r_{2n+2}(0; x) = \frac{\sin\left(\xi + (2n+3)\frac{\pi}{2}\right)}{(2n + 3)!} x^{2n+3} \implies |r_{2n+2}(0; x)| \le \frac{|x|^{2n+3}}{(2n + 3)!} \tag{26}
\end{gather}
$$
Similarly, for the cosine function:
$$
\begin{gather}
\cos(x) = \sum_{m=0}^n \frac{(-1)^m}{(2m)!} x^{2m} + r_{2n+1}(0; x) \tag{27}
\end{gather}
$$
with remainder bound:
$$
\begin{gather}
|r_{2n+1}(0; x)| \le \frac{|x|^{2n+2}}{(2n + 2)!} \tag{28}
\end{gather}
$$
Because $\lim_{n \to \infty} \frac{|x|^n}{n!} = 0$ for all $x \in \mathbb{R}$ (established in [[Chapter 1 - Limits of Sequences|Module 3]]), the Taylor polynomials of $\sin x$ and $\cos x$ converge uniformly to the functions on every bounded interval of the real line.

##### 2. Hyperbolic Systems ($\sinh x$ and $\cosh x$)
Using the derivatives established in Chapter 2 ($\sinh'(x) = \cosh(x)$ and $\cosh'(x) = \sinh(x)$), evaluating successive derivatives at the origin yields $\sinh^{(2m)}(0) = 0$, $\sinh^{(2m+1)}(0) = 1$, and $\cosh^{(2m)}(0) = 1$, $\cosh^{(2m+1)}(0) = 0$. The resulting Maclaurin expansions are:
$$
\begin{gather}
\sinh(x) = \sum_{m=0}^n \frac{x^{2m+1}}{(2m + 1)!} + \frac{\sinh^{(2n+3)}(\xi)}{(2n + 3)!} x^{2n+3} \tag{29}
\end{gather}
$$
$$
\begin{gather}
\cosh(x) = \sum_{m=0}^n \frac{x^{2m}}{(2m)!} + \frac{\cosh^{(2n+2)}(\xi)}{(2n + 2)!} x^{2n+2} \tag{30}
\end{gather}
$$

##### 3. The Algebraic Binomial Expansion ($(1 + x)^\alpha$ for Rational Exponents)
Let $\alpha = \frac{p}{q} \in \mathbb{Q}$ be an arbitrary rational number, and consider $f(x) = (1 + x)^\alpha$ defined on $(-1, 1)$. The successive derivatives are:
$$
\begin{gather}
f^{(k)}(x) = \alpha(\alpha - 1)(\alpha - 2)\dots(\alpha - k + 1) (1 + x)^{\alpha - k} \tag{31}
\end{gather}
$$
Defining the generalized binomial coefficient for rational $\alpha$ by:
$$
\begin{gather}
\binom{\alpha}{k} := \frac{\alpha(\alpha - 1)\dots(\alpha - k + 1)}{k!} \tag{32}
\end{gather}
$$
the Maclaurin expansion with Cauchy form of the remainder becomes:
$$
\begin{gather}
(1 + x)^\alpha = \sum_{k=0}^n \binom{\alpha}{k} x^k + r_n(0; x) \tag{33}
\end{gather}
$$
where Cauchy's formula gives:
$$
\begin{gather}
r_n(0; x) = (n + 1) \binom{\alpha}{n + 1} (1 + \theta x)^{\alpha - n - 1} (1 - \theta)^n x^{n+1}, \quad \theta \in (0, 1) \tag{34}
\end{gather}
$$

##### 4. Inverse Circular Systems ($\arctan x$ and $\arcsin x$)
For the inverse tangent, differentiation yields $\arctan'(x) = \frac{1}{1 + x^2}$. Expanding this derivative as a geometric series for $|x| < 1$:
$$
\begin{gather}
\frac{1}{1 + x^2} = 1 - x^2 + x^4 - x^6 + \dots + (-1)^n x^{2n} + o(x^{2n}) \tag{35}
\end{gather}
$$
By integrating the local Taylor expansion term by term (via uniqueness of polynomial jets), the Maclaurin expansion of the arctangent is:
$$
\begin{gather}
\arctan(x) = \sum_{m=0}^n \frac{(-1)^m}{2m + 1} x^{2m+1} + o(x^{2n+2}) \tag{36}
\end{gather}
$$
Similarly, for the inverse sine, expanding $\arcsin'(x) = (1 - x^2)^{-1/2}$ via the rational binomial expansion with $\alpha = -1/2$ yields:
$$
\begin{gather}
\arcsin(x) = x + \sum_{m=1}^n \frac{(2m - 1)!!}{(2m)!! (2m + 1)} x^{2m+1} + o(x^{2n+2}) \tag{37}
\end{gather}
$$

### Asymptotic Evaluation of Indeterminate Limits
The local Taylor formula provides the most powerful tool in differential calculus for evaluating limits of indeterminate forms without resorting to repeated algorithmic differentiations.

>[!example]- Example: Asymptotic Evaluation of a Trigonometric Indeterminate Form
>Consider the evaluation of the indeterminate limit:
>$$
>\begin{gather}
>L := \lim_{x \to 0} \frac{\arctan(x) - \sin(x)}{x^3} \tag{38}
>\end{gather}
>$$
>Substituting the third-order local Maclaurin expansions for $\sin(x)$ and $\arctan(x)$ as $x \to 0$:
>$$
>\begin{gather}
>\sin(x) = x - \frac{x^3}{6} + o(x^4), \quad \arctan(x) = x - \frac{x^3}{3} + o(x^4) \tag{39}
>\end{gather}
>$$
>Subtracting these two expansions isolates the leading non-vanishing variation:
>$$
>\begin{gather}
>\arctan(x) - \sin(x) = \left(x - \frac{x^3}{3}\right) - \left(x - \frac{x^3}{6}\right) + o(x^4) = -\frac{x^3}{6} + o(x^4) \tag{40}
>\end{gather}
>$$
>Dividing by the cubic monomial $x^3$ yields:
>$$
>\begin{gather}
>\frac{\arctan(x) - \sin(x)}{x^3} = \frac{-\frac{1}{6}x^3 + o(x^4)}{x^3} = -\frac{1}{6} + o(1) \tag{41}
>\end{gather}
>$$
>Taking the limit as $x \to 0$ establishes:
>$$
>\begin{gather}
>L = -\frac{1}{6} \tag{42}
>\end{gather}
>$$

---

# Visual Models of Fundamental Differential Theorems

###  Classification of Local Extrema and Domain Topology
```easy-tikz
title $\text{Topological Classification of Extrema: Boundary vs. Interior}$
xlabel $x$
ylabel $y$
show x from -1.929 to 4.571 and y from -0.54 to 5.46
axes on the edges
size 12 x 8
plot f(x) = x^2, from x = -1.0 to 1.99, in cyan, very thick
plot g(x) = 4.0, from x = 2.0 to 4.0, in orange, very thick
draw a line from (-1.0, 0) to (-1.0, 1.0), in gray, dashed
draw a line from (2.0, 0) to (2.0, 4.0), in gray, dashed
raw tool {"type":"points","name":"P1","points":"(-1.0, 1.0);","size":"large"}
mark (0.0, 0.0), in green, large
mark (2.0, 4.0), in orange, large
draw an arrow from (-0.28, 1.35) to (-0.05, 0.25) in green
draw an arrow from (3, 3) to (2.07, 3.9) in orange
write "$\\text{Boundary Maximum } (-1, 1)$" at (-1.0, 1.5) in purple, center
write "$\\text{Interior Minimum: } f'(0) = 0$" at (-0.45, 1.55) in green, center
write "$\\text{Corner Maximum } (2, 4)$" at (3.13, 2.7) in orange, center
write "$\\text{Plateau of Non-Strict Extrema } y = 4$" at (2.1, 5.15) in orange, below
write "$f(x) = x^2$" at (0.72, 3.05) in teal, right

```

### Rolle's Horizontal Tangency on Compact Intervals
```easy-tikz
title $\text{Rolle's Theorem: Existence of Interior Stationary Point}$
xlabel $x$
ylabel $y$
show x from 0.0 to 7.0 and y from 0.0 to 5.5
axes on the edges
size 12 x 8
plot f(x) = -0.35*(x - 1.0)*(x - 6.0) + 2.0, from x = 1.0 to 6.0, in cyan, very thick
draw a line from (1.0, 0) to (1.0, 2.0), in gray, dashed
draw a line from (6.0, 0) to (6.0, 2.0), in gray, dashed
draw a line from (1.0, 2.0) to (6.0, 2.0), in orange, dashed
plot tangent(x) = 4.19, from x = 2.0 to 5.0, in green, thick
draw a line from (3.5, 0) to (3.5, 4.19), in gray, dashed
mark (1.0, 2.0), in orange, large
mark (6.0, 2.0), in orange, large
mark (3.5, 4.19), in green, large
write "$a$" at (1.0, 0.4) in gray, center
write "$b$" at (6.0, 0.4) in gray, center
write "$\\xi$" at (3.5, 0.4) in gray, center
write "$f(a) = f(b)$" at (3.5, 1.7) in orange, center
write "$\\text{Horizontal Tangent: } f'(\\xi) = 0$" at (3.5, 4.6) in green, center

```

### The Secant-Tangent Parallelism of Lagrange's Theorem
```easy-tikz
title $\text{Lagrange's Finite-Increment Theorem: Parallel Chord and Tangent}$
xlabel $x$
ylabel $y$
show x from 0.0 to 7.5 and y from 0.0 to 6.0
axes on the edges
size 12 x 8
plot f(x) = 0.8 + 2.1*sqrt(x - 0.5), from x = 0.8 to 6.5, in cyan, very thick
plot secant(x) = 1.95 + 0.59*(x - 0.8), from x = 0.8 to 6.5, in orange, thick, dashed
plot tangent(x) = 3.65 + 0.59*(x - 3.1), from x = 1.5 to 5.5, in green, thick
draw a line from (0.8, 0) to (0.8, 1.95), in gray, dashed
draw a line from (6.5, 0) to (6.5, 5.31), in gray, dashed
draw a line from (3.1, 0) to (3.1, 3.65), in gray, dashed
mark (0.8, 1.95), in orange, large
mark (6.5, 5.31), in orange, large
mark (3.1, 3.65), in green, large
write "$a$" at (0.8, 0.4) in gray, center
write "$b$" at (6.5, 0.4) in gray, center
write "$\\xi$" at (3.1, 0.4) in gray, center
write "$\\text{Secant Slope: } \\frac{f(b) - f(a)}{b - a}$" at (4.05, 3.6) in orange, right
write "$\\text{Parallel Tangent: } f'(\\xi)$" at (2.2, 4.0) in green, left

```

### Cauchy's Parametric Plane Curve Tangency
```easy-tikz
title $\text{Cauchy's Theorem: Plane Parametric Chord and Velocity Alignment}$
xlabel $x(t)$
ylabel $y(t)$
show x from 0.0 to 7.0 and y from 0.0 to 6.0
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 0.9*x - 0.08*x^2 + 0.3*sin(1.2*x), from x = 1.0 to 6.0, in cyan, very thick
draw a line from (1.0, 2.1) to (6.0, 4.4), in orange, very thick, dashed
plot tangent(x) = 3.8 + 0.46*(x - 3.2), from x = 1.8 to 4.8, in green, thick
mark (1.0, 2.1), in orange, large
mark (6.0, 4.4), in orange, large
mark (3.2, 3.8), in green, large
write "$A(x(a), y(a))$" at (1.0, 1.6) in orange, center
write "$B(x(b), y(b))$" at (6.0, 4.9) in orange, center
write "$\\text{Secant Vector } \\Delta \\vec{r}$" at (3.5, 2.8) in orange, center
write "$\\text{Tangent Velocity Vector } \\vec{r}'(\\xi)$" at (3.2, 4.4) in green, center

```

### Taylor Polynomial Envelopes for Circular Functions
```easy-tikz
title $\text{Maclaurin Polynomial Convergence Envelopes for } \sin(x)$
xlabel $x$
ylabel $y$
show x from -4.0 to 4.0 and y from -2.5 to 2.5
axes on the edges
size 12 x 8
plot f(x) = sin(x), from x = -3.8 to 3.8, in cyan, very thick
plot p1(x) = x, from x = -2.0 to 2.0, in orange, thick
plot p3(x) = x - (x^3)/6.0, from x = -2.8 to 2.8, in green, thick
plot p5(x) = x - (x^3)/6.0 + (x^5)/120.0, from x = -3.5 to 3.5, in purple, thick
raw tool {"type":"points","name":"P1","color":"black","points":"(0.0, 0.0); ","size":"large"}
write "$f(x) = \\sin(x)$" at (3.2, 0.3) in cyan, right
write "$P_1(x) = x$" at (1.85, 2.3) in orange, right
write "$P_3(x) = x - \\frac{x^3}{6}$" at (0.3, -0.3) in green, right
write "$\\sin(x)$" at (-3.6, 0.9) in teal, center
write "$P_5(x) = x - \\frac{x^3}{6} + \\frac{x^5}{120}$" at (3.2, 1.8) in purple, right

```

---
# Applications of the Basic Theorems of Differential Calculus

### Quantitative Finance: Non-Linear Delta-Gamma Tracking Error Bounds via Lagrange Remainder
In financial derivatives engineering, the market value of a portfolio of European options written on a underlying spot asset $S$ is modeled by a non-linear mapping $V(S)$. When an asset moves from its initial spot price $S_0$ by a finite displacement $h = \Delta S$ over a short rebalancing interval $[S_0 - \epsilon, S_0 + \epsilon]$, the portfolio manager constructs a *delta-gamma neutral hedge*. 

The hedge eliminates the linear sensitivity $\Delta := V'(S_0)$ and the quadratic curvature sensitivity $\Gamma := V''(S_0)$ by taking offsetting positions in the underlying asset and liquid exchange-traded benchmark options. The unhedged residual financial exposure—termed the *tracking error*—is given by:
$$
\begin{gather}
\varepsilon(h) := V(S_0 + h) - \left(V(S_0) + \Delta h + \frac{1}{2}\Gamma h^2\right) \tag{43}
\end{gather}
$$
Under the classical Black–Scholes framework, the value function for an options portfolio is $C^\infty$ on $(0, \infty)$. Applying Taylor's theorem with the Lagrange form of the remainder of order $n = 2$ on the compact price interval $[S_0 - \epsilon, S_0 + \epsilon]$, there exists an intermediate spot price $\xi \in (S_0 - |h|, S_0 + |h|)$ such that:
$$
\begin{gather}
\varepsilon(h) = \frac{V'''(\xi)}{3!} h^3 = \frac{1}{6} V'''(\xi) h^3 \tag{44}
\end{gather}
$$
The third derivative of an option value with respect to the underlying asset is known as *speed* ($\text{Speed} := \frac{\partial^3 V}{\partial S^3} = \frac{\partial \Gamma}{\partial S}$). Let $M_3 := \sup_{S \in [S_0 - \epsilon, S_0 + \epsilon]} |V'''(S)|$ denote the maximum speed over the shock horizon. By virtue of the Lagrange remainder of step 44, the worst-case financial tracking error satisfies the rigorous deterministic bound:
$$
\begin{gather}
|\varepsilon(h)| \le \frac{M_3}{6} |h|^3 \tag{45}
\end{gather}
$$
The cubic decay of step 45 proves why delta-gamma hedging provides exceptional stability during normal volatility regimes: halving the asset displacement $h$ compresses the unhedged risk exposure by an entire factor of eight.

### Classical Mechanics: Potential Energy Stationary States and Equilibrium Stability via Fermat's Lemma
Consider a conservative one-dimensional mechanical system consisting of a rigid pendulum arm of length $L$ and mass $m$ attached to a non-linear torsional spring. When the arm is deflected by an inclination angle $\theta \in (-\pi, \pi)$ from the downward vertical, the net potential energy of the system is the sum of gravitational potential energy and elastic deformation energy:
$$
\begin{gather}
V(\theta) := -mgL \cos(\theta) + \frac{1}{2}\kappa \theta^2 + \frac{1}{4}\beta \theta^4 \tag{46}
\end{gather}
$$
where $\kappa > 0$ is the linear torsional stiffness and $\beta > 0$ represents the hardening non-linear elastic modulus. The system configuration space is the open interval $(-\pi, \pi)$.

According to the principle of virtual work, a static equilibrium configuration is one where the net generalized force $Q(\theta) := -V'(\theta)$ vanishes identically. Differentiating step 46:
$$
\begin{gather}
V'(\theta) = mgL \sin(\theta) + \kappa \theta + \beta \theta^3 \tag{47}
\end{gather}
$$
By Fermat's Interior Extremum Lemma, any local minimum of $V(\theta)$ must occur at an interior stationary point $V'(\theta_0) = 0$. Because $\theta = 0$ yields $\sin(0) = 0$, $\theta_0 = 0$ is always a stationary point. Evaluating the second derivative:
$$
\begin{gather}
V''(\theta) = mgL \cos(\theta) + \kappa + 3\beta \theta^2 \implies V''(0) = mgL + \kappa > 0 \tag{48}
\end{gather}
$$
Because $V''(0) > 0$, the downward vertical state $\theta = 0$ is a strict interior local minimum.

Now suppose the system is inverted, such that the pendulum arm is balanced near the upward vertical $\phi := \theta - \pi \in (-\frac{\pi}{2}, \frac{\pi}{2})$, giving the inverted potential:
$$
\begin{gather}
\widetilde{V}(\phi) := mgL \cos(\phi) + \frac{1}{2}\kappa \phi^2 + \frac{1}{4}\beta \phi^4 \tag{49}
\end{gather}
$$
The first derivative is $\widetilde{V}'(\phi) = -mgL \sin(\phi) + \kappa \phi + \beta \phi^3$. Evaluating the curvature at the upward vertical $\phi = 0$:
$$
\begin{gather}
\widetilde{V}''(0) = -mgL + \kappa \tag{50}
\end{gather}
$$
- Case 1: If $\kappa > mgL$, $\widetilde{V}''(0) > 0$; the upward equilibrium is a strict local minimum and remains unconditionally stable.
- Case 2: If $\kappa < mgL$, $\widetilde{V}''(0) < 0$; the origin becomes a local maximum, destabilizing the vertical post. By Darboux's theorem and the intermediate-value property applied to $\widetilde{V}'(\phi)$, two symmetrical non-zero stationary points $\pm \phi^*$ emerge where $\kappa \phi^* + \beta (\phi^*)^3 = mgL \sin(\phi^*)$, creating two new stable equilibrium branches (a pitchfork bifurcation) without invoking differential equations.

### Aerospace Dynamics: Aerodynamic Lift-to-Moment Sensitivity Coupling via Cauchy's Mean Value Theorem
In flight dynamics and aeronautical design, an aircraft traversing a maneuver undergoes variations in angle of attack $\alpha \in [\alpha_1, \alpha_2]$. The aerodynamic performance is governed by two scalar coefficients: the lift coefficient $C_L(\alpha)$ and the pitching moment coefficient about the center of gravity $C_m(\alpha)$. For safe longitudinal flight, an aircraft must maintain pitch stiffness, meaning that an increase in lift must produce a restoring nose-down pitching moment.

Suppose that during a gust encounter, the angle of attack shifts from $\alpha_1$ to $\alpha_2$. The macroscopic ratio of total lift variation to total moment variation is:
$$
\begin{gather}
\frac{\Delta C_L}{\Delta C_m} = \frac{C_L(\alpha_2) - C_L(\alpha_1)}{C_m(\alpha_2) - C_m(\alpha_1)} \tag{51}
\end{gather}
$$
Both $C_L(\alpha)$ and $C_m(\alpha)$ are smooth functions on $[\alpha_1, \alpha_2]$. Provided that the pitch control surface prevents moment stagnation ($C_m'(\alpha) \neq 0$), Cauchy's Generalized Finite-Increment Theorem guarantees the existence of an intermediate angle of attack $\alpha^* \in (\alpha_1, \alpha_2)$ such that:
$$
\begin{gather}
\frac{C_L(\alpha_2) - C_L(\alpha_1)}{C_m(\alpha_2) - C_m(\alpha_1)} = \frac{C_L'(\alpha^*)}{C_m'(\alpha^*)} \tag{52}
\end{gather}
$$
In aerodynamics, the ratio of derivatives $\frac{dC_m}{dC_L} = \frac{C_m'(\alpha)}{C_L'(\alpha)}$ defines the *static margin*:
$$
\begin{gather}
K_n := -\frac{C_m'(\alpha)}{C_L'(\alpha)} = \frac{x_{np} - x_{cg}}{\bar{c}} \tag{53}
\end{gather}
$$
where $x_{np}$ is the neutral point of the aircraft, $x_{cg}$ is the center of gravity, and $\bar{c}$ is the mean aerodynamic chord. 

Cauchy's theorem of step 52 proves that the macroscopic aerodynamic load shift experienced across an entire gust excursion is governed identically by the local static margin evaluated at an instantaneous intermediate angle of attack $\alpha^*$. Consequently, if the instantaneous static margin $K_n(\alpha)$ remains strictly positive throughout $(\alpha_1, \alpha_2)$, the total flight excursion cannot suffer a catastrophic uncommanded pitch divergence.

### Chemical Kinetics: Maximum Reaction Velocity in Autocatalytic Batch Processes via Rolle's Theorem
In chemical reactor engineering, consider an isothermal liquid-phase batch reactor carrying out a second-order autocatalytic reaction of the form:
$$
\begin{gather}
A + B \xrightarrow{k} 2B \tag{54}
\end{gather}
$$
Let $C_{A0}$ and $C_{B0}$ denote the initial concentrations of reactant $A$ and catalyst product $B$ at time $t = 0$. The reaction extent is parametrized by the fractional conversion of the limiting reactant $X \in [0, 1]$, such that the instantaneous concentrations are:
$$
\begin{gather}
C_A(X) = C_{A0}(1 - X), \quad C_B(X) = C_{B0} + C_{A0}X \tag{55}
\end{gather}
$$
According to the law of mass action, the reaction rate $R(X)$ (in moles per unit volume per second) is:
$$
\begin{gather}
R(X) := k C_A(X) C_B(X) = k C_{A0}^2 (1 - X)\left(\frac{C_{B0}}{C_{A0}} + X\right) \tag{56}
\end{gather}
$$
Defining the initial concentration ratio $\theta_B := \frac{C_{B0}}{C_{A0}} > 0$ and the rate constant factor $K := k C_{A0}^2$, the rate function becomes:
$$
\begin{gather}
R(X) = K(1 - X)(\theta_B + X) = K\big(\theta_B + (1 - \theta_B)X - X^2\big) \tag{57}
\end{gather}
$$
Consider the case where pure reactant $A$ is seeded with an infinitesimal trace of catalyst such that $\theta_B \to 0$. The rate function satisfies boundary conditions:
$$
\begin{gather}
R(0) = 0 \quad \text{and} \quad R(1) = 0 \tag{58}
\end{gather}
$$
Because $R(X)$ is continuous on the compact interval $[0, 1]$, differentiable on $(0, 1)$, and satisfies $R(0) = R(1) = 0$, all hypotheses of Rolle's Theorem are fulfilled on $[0, 1]$. 

Therefore, there exists at least one interior conversion level $X^* \in (0, 1)$ where the derivative vanishes:
$$
\begin{gather}
R'(X^*) = 0 \tag{59}
\end{gather}
$$
Differentiating step 57:
$$
\begin{gather}
R'(X) = K\big((1 - \theta_B) - 2X\big) = 0 \implies X^* = \frac{1 - \theta_B}{2} \tag{60}
\end{gather}
$$
For trace seeding ($\theta_B \ll 1$), the peak reaction rate occurs precisely at the midpoint conversion $X^* \approx 0.5$. Because $R''(X) = -2K < 0$, this stationary point is a global maximum. Rolle's theorem proves that every autocatalytic process must experience an internal maximum reaction rate without needing to integrate the underlying non-linear rate equation.

### Biomedical Engineering: Allometric Metabolic Clearance and Bounded Sensitivity via Lagrange's Theorem
In quantitative pharmacokinetics and physiological scaling, the basal metabolic clearance rate $Cl(M)$ of a therapeutic drug across mammalian species scales with total body mass $M$ according to Kleiber's allometric power law:
$$
\begin{gather}
Cl(M) := \kappa M^{3/4} \tag{61}
\end{gather}
$$
where $\kappa > 0$ is a compound-specific clearance constant and the exponent $3/4$ is a rational number.

When scaling pediatric dosages to adult populations over a body mass interval $[M_1, M_2] \subset (0, \infty)$ (for example, from a child of mass $M_1 = 16\text{ kg}$ to an adult of mass $M_2 = 81\text{ kg}$), the total change in physiological clearance is $\Delta Cl = Cl(M_2) - Cl(M_1)$.

Because $Cl(M)$ is continuous on $[M_1, M_2]$ and differentiable on $(M_1, M_2)$, Lagrange's Finite-Increment Theorem guarantees that there exists an intermediate physiological mass $M^* \in (M_1, M_2)$ such that:
$$
\begin{gather}
Cl(M_2) - Cl(M_1) = Cl'(M^*)(M_2 - M_1) \tag{62}
\end{gather}
$$
Computing the derivative using the power rule for rational exponents established in Chapter 2:
$$
\begin{gather}
Cl'(M) = \frac{3}{4}\kappa M^{-1/4} = \frac{3\kappa}{4 M^{1/4}} \tag{63}
\end{gather}
$$
Substituting step 63 into step 62:
$$
\begin{gather}
\Delta Cl = \frac{3\kappa}{4 (M^*)^{1/4}} (M_2 - M_1) \tag{64}
\end{gather}
$$
Because $M \mapsto M^{-1/4}$ is strictly decreasing on $(0, \infty)$, the intermediate derivative is strictly bounded by the endpoints:
$$
\begin{gather}
\frac{3\kappa}{4 M_2^{1/4}} < Cl'(M^*) < \frac{3\kappa}{4 M_1^{1/4}} \tag{65}
\end{gather}
$$
Multiplying by $(M_2 - M_1)$ yields rigorous deterministic upper and lower bounds for the total clearance increase:
$$
\begin{gather}
\frac{3\kappa (M_2 - M_1)}{4 M_2^{1/4}} < \Delta Cl < \frac{3\kappa (M_2 - M_1)}{4 M_1^{1/4}} \tag{66}
\end{gather}
$$
For $M_1 = 16\text{ kg}$ ($M_1^{1/4} = 2$) and $M_2 = 81\text{ kg}$ ($M_2^{1/4} = 3$), with mass displacement $M_2 - M_1 = 65\text{ kg}$:
$$
\begin{gather}
\frac{3\kappa (65)}{4 \times 3} = 16.25 \kappa < \Delta Cl < \frac{3\kappa (65)}{4 \times 2} = 24.375 \kappa \tag{67}
\end{gather}
$$
The exact variation is $Cl(81) - Cl(16) = \kappa (81^{3/4} - 16^{3/4}) = \kappa(27 - 8) = 19\kappa$, which lies strictly within the analytical bounds of step 67. The intermediate mass $M^*$ is found by solving $\frac{3\kappa}{4(M^*)^{1/4}} \times 65 = 19\kappa$, which yields $(M^*)^{1/4} = \frac{195}{76} \approx 2.5657 \implies M^* \approx 43.33\text{ kg}$, demonstrating that the effective sensitivity point is skewed toward the lower mass boundary.
