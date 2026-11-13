---
dg-publish: true
---
# The Concept of the Primitive Mapping

### Definition and Fundamental Properties of Primitives
In differential calculus, the operation of differentiation assigns to a differentiable function $F: I \to \mathbb{R}$ on an interval $I \subseteq \mathbb{R}$ its derivative mapping $f = F': I \to \mathbb{R}$. The inverse operational problem—determining a function whose instantaneous rate of change reproduces a prescribed target mapping $f$ across an entire domain—constitutes the foundational inquiry of *integral* calculus.

Let $I \subseteq \mathbb{R}$ denote a non-degenerate interval (open, closed, or semi-infinite). A function $F: I \to \mathbb{R}$ is defined as a *primitive* (or *antiderivative*) of $f: I \to \mathbb{R}$ if $F$ is everywhere differentiable on $I$ and its derivative identically coincides with $f$ at every point of the domain: 
$$
\begin{gather}
\textbf{Definition: Primitive Mapping} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be a non-degenerate interval, and let } f: I \to \mathbb{R} \text{ be a real-valued mapping.} \\[2mm]
\text{A function } F: I \to \mathbb{R} \text{ is said to be a primitive of } f \text{ on } I \text{ if } F \text{ is differentiable on } I \text{ and satisfies:} \\[3.5mm]
F'(x) = f(x) \quad \forall x \in I.
\end{gather}
$$
(see [[Proof of Primitive Well-Definedness and Properties]])

The operator mapping $F \mapsto F'$ represents a many-to-one transformation because the differentiation of an additive constant yields zero. Consequently, a primitive mapping is never strictly unique. The structure of the complete pre-image $D^{-1}(\{f\})$, termed the *indefinite integral* and traditionally denoted by $\int f(x) \, dx$, is governed by the topology of the underlying domain.

$$
\begin{gather}
\textbf{Theorem: Kernel of the Differential Operator and } \\[2mm] 
\textbf{Uniqueness up to Additive Constants} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be a non-degenerate interval, and let } F_1, F_2: I \to \mathbb{R} \text{ be two primitives of } f \text{ on } I. \\[2mm]
\text{Then there exists a unique real scalar } C \in \mathbb{R} \text{ such that:} \\[3.5mm]
F_1(x) - F_2(x) = C \quad \forall x \in I.
\end{gather}
$$
(see [[Proof of Uniqueness of Primitives up to Additive Constants on Connected Domains]])

The connectedness of the domain $I$ is an indispensable topological prerequisite for this theorem. If the underlying domain consists of a disconnected union of disjoint open intervals, say $E = I_1 \cup I_2$ with $I_1 \cap I_2 = \emptyset$, the null-space of the differential operator $D = \frac{d}{dx}$ expands from the one-dimensional field $\mathbb{R}$ to a vector space of dimension equal to the cardinality of the connected components. On such a disconnected set, two primitives may differ by distinct, independent constants on each respective connected component.

> [!danger]+ Intuition: The Coordinate Phase Shift of the Velocity Field
> Consider a point particle whose instantaneous velocity is continuously prescribed as $v(t) = f(t)$. The primitive $F(t)$ physically tracks the particle's spatial position along a one-dimensional coordinate axis. Because the kinematic equations dictate only the rate of displacement, the physical laws remain invariant under rigid translations of the spatial reference frame. Shifting the spatial origin by a constant offset $C$ leaves the instantaneous velocity vector entirely unaltered. The indefinite integral does not designate a single rigid trajectory, but rather an entire foliation of parallel trajectory fibers parameterized by the initial spatial configuration $F(t_0) = x_0$.

The geometry of this family of primitive mappings illustrates how rigid translations generate the complete solution space across an interval:
```easy-tikz
title $\text{Foliation of Primitive Curves Under Rigid Vertical Translations}$
xlabel $x$
ylabel $y$
show x from -3.5 to 3.5 and y from -2.5 to 4.5
axes on the edges
size 12 x 8
plot f1(x) = 0.25*x^3 - x - 1.0, from x = -2.8 to 2.8, in cyan, thick
plot f2(x) = 0.25*x^3 - x + 0.5, from x = -2.8 to 2.8, in orange, thick
plot f3(x) = 0.25*x^3 - x + 2.0, from x = -2.8 to 2.8, in green, thick
draw a line from (1.0, -2.5) to (1.0, 4.0), in gray, dashed
mark (1.0, -1.75), in cyan, large
mark (1.0, -0.25), in orange, large
mark (1.0, 1.25), in green, large
draw a line from (0.0, -1.75) to (2.0, -1.75), in cyan, thin
draw a line from (0.0, -0.25) to (2.0, -0.25), in orange, thin
draw a line from (0.0, 1.25) to (2.0, 1.25), in green, thin
write "$F(x) - C_1$" at (2.05, -1.3) in teal, right
write "$F(x)$" at (2.55, 3.65) in orange, right
write "$F(x) + C_2$" at (1.55, 4.7) in green, right
write "$\\text{Identical Slopes: } F'(x_0) = f(x_0)$" at (-2.38, -2.1) in gray, right

```

The transformation of primitives under smooth coordinate changes provides an essential invariance property:
$$
\begin{gather}
\textbf{Proposition: Invariance of Primitives under Diffeomorphisms} \\[5mm]
\text{Let } I, J \subseteq \mathbb{R} \text{ be open intervals, and let } \varphi: J \to I \text{ be a } C^1\text{-diffeomorphism with } \varphi'(t) \neq 0 \text{ for all } t \in J. \\[2mm]
\text{If } F: I \to \mathbb{R} \text{ is a primitive of } f: I \to \mathbb{R} \text{ on } I, \text{ then the composite pullback mapping } \Phi = F \circ \varphi: J \to \mathbb{R} \\[2mm]
\text{is a primitive of the differential form pullback } (f \circ \varphi) \cdot \varphi' \text{ on } J: \\[3.5mm]
\Phi'(t) = \frac{d}{dt}\big(F(\varphi(t))\big) = f(\varphi(t)) \varphi'(t) \quad \forall t \in J.
\end{gather}
$$
(see [[Proof of Invariance of Primitives under Diffeomorphisms]])

### The Darboux Continuity Constraint for Primitives
A fundamental question arises: Does every real mapping $f: I \to \mathbb{R}$ admit a primitive? The answer is negative. The existence of an antiderivative imposes rigid structural constraints upon the local and global geometry of $f$.

By [[Chapter 3 - The Basic Theorems of Differential Calculus#The Darboux Intermediate-Value Property of Derivatives|Darboux's Theorem on Derivatives]], the derivative of any everywhere differentiable function on an interval possesses the *intermediate value property* (the Darboux property). Specifically, if $f = F'$, then for any two points $a, b \in I$ with $a < b$, the image $f([a, b])$ contains the entire closed interval bounded by $f(a)$ and $f(b)$.

$$
\begin{gather}
\textbf{Theorem: Darboux Obstruction to Antidifferentiation} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be an interval, and let } f: I \to \mathbb{R} \text{ be a function admitting a primitive } F \text{ on } I. \\[2mm]
\text{Then } f(I) \text{ is a connected subset of } \mathbb{R}. \text{ In particular, } f \text{ cannot exhibit jump discontinuities} \\[2mm]
\text{or removable discontinuities at any point of } I.
\end{gather}
$$
(see [[Proof of Darboux Obstruction and Intermediate Value Theorem for Derivatives]])

The practical implication of Darboux's obstruction is immediate: elementary step functions, such as the Heaviside step function $H: \mathbb{R} \to \mathbb{R}$ defined by:
$$
\begin{gather}
H(x) := \begin{cases} 0, & x < 0, \\ 1, & x \ge 0, \end{cases}
\end{gather}
$$
cannot serve as the derivative of any function across an open neighborhood containing the origin. Any function $F$ whose derivative exists on an open interval must map connected sets to connected sets.

Nevertheless, the Darboux property does not require continuity. Highly oscillatory functions may admit primitives while oscillating wildly near a single point. Consider the canonical function:
$$
\begin{gather}
F(x) := \begin{cases} x^2 \sin\left(\frac{1}{x}\right), & x \neq 0, \\ 0, & x = 0. \end{cases}
\end{gather}
$$
Evaluating the derivative via the difference quotient at the origin:
$$
\begin{gather}
F'(0) = \lim_{h \to 0} \frac{h^2 \sin(1/h) - 0}{h} = \lim_{h \to 0} h \sin\left(\frac{1}{h}\right) = 0.
\end{gather}
$$
For $x \neq 0$, the product and chain rules yield:
$$
\begin{gather}
f(x) := F'(x) = 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right).
\end{gather}
$$
The derivative $f(x)$ possesses an antiderivative everywhere on $\mathbb{R}$ by construction, yet $f(x)$ is discontinuous at $x = 0$ due to the persistent oscillation of $\cos(1/x)$ between $-1$ and $+1$ as $x \to 0$.

```easy-tikz
title $\text{Phase Portrait of the Oscillatory Primitive and Discontinuous Derivative}$
xlabel $x$
ylabel $y$
show x from -1.316 to 1.684 and y from -1.46 to 1.54
axes on the edges
size 12 x 8
plot f(x) = x^2 * sin(1.0 / (abs(x) + 0.04)), from x = -1.2 to 1.2, in cyan, thick
plot envelope_pos(x) = x^2, from x = -1.2 to 1.2, in orange, dashed
plot envelope_neg(x) = -x^2, from x = -1.2 to 1.2, in orange, dashed
mark (0.0, 0.0), in green, large
write "$F(x) = x^2 \\sin(1/x)$" at (0.45, 0.95) in cyan, right
write "$y = \\pm x^2$" at (0.85, 0.65) in orange, right
write "$F'(0) = 0 \\text{ exists everywhere}$" at (-0.66, 0.68) in green, right

```

---
# Algebraic Methods and Transformation Rules for Primitives

### Linearity and the Method of Decomposition
The differentiation operator $D: C^1(I) \to C^0(I)$ is an $\mathbb{R}$-linear transformation on function spaces. Because the inverse image of a linear operator inherits this algebraic structure, the formation of primitives is likewise linear over the field of real numbers: 
$$
\begin{gather}
\textbf{Proposition: Linearity of the Indefinite Integral} \\[5mm]
\text{Let } f, g: I \to \mathbb{R} \text{ admit primitives } F, G \text{ on an interval } I, \text{ and let } \alpha, \beta \in \mathbb{R}. \\[2mm]
\text{Then the linear combination } \alpha f + \beta g \text{ admits the primitive } \alpha F + \beta G \text{ on } I: \\[3.5mm]
\int \big(\alpha f(x) + \beta g(x)\big) \, dx = \alpha \int f(x) \, dx + \beta \int g(x) \, dx.
\end{gather}
$$
(see [[Proof of Linearity of Primitives and Method of Decomposition]])

The practical consequence of linearity is the *method of decomposition*: an integrand that resists immediate recognition may be decomposed into an algebraic sum of elementary components, each of which admits a standard tabulated antiderivative.

### Change of Variables (Substitution Rule)
The chain rule of differential calculus, which asserts that $(F \circ \varphi)'(t) = F'(\varphi(t)) \varphi'(t)$, translates directly into the primary operational engine for transforming integrands: the change of variables: 
$$
\begin{gather}
\textbf{Theorem: First and Second Substitution Rules for Primitives} \\[5mm]
\text{1. First Substitution Rule (Direct Substitution):} \\[2mm]
\text{Let } \varphi: J \to I \text{ be differentiable on an open interval } J, \text{ and let } f: I \to \mathbb{R} \text{ possess a primitive } F. \\[2mm]
\text{Then the composite function } (f \circ \varphi) \varphi' \text{ possesses the primitive } F \circ \varphi \text{ on } J: \\[3.5mm]
\int f(\varphi(t)) \varphi'(t) \, dt = F(\varphi(t)) + C = \left[ \int f(u) \, du \right]_{u = \varphi(t)}. \\[5mm]
\text{2. Second Substitution Rule (Inverse Substitution):} \\[2mm]
\text{Let } \varphi: J \to I \text{ be a bijective, continuously differentiable mapping with } \varphi'(t) \neq 0 \text{ for all } t \in J, \\[2mm]
\text{and let } \psi = \varphi^{-1}: I \to J \text{ denote its inverse. If } g(t) := f(\varphi(t)) \varphi'(t) \text{ admits a primitive } G(t), \\[2mm]
\text{then } f(x) \text{ admits the primitive } G(\psi(x)) \text{ on } I: \\[3.5mm]
\int f(x) \, dx = \left[ \int f(\varphi(t)) \varphi'(t) \, dt \right]_{t = \varphi^{-1}(x)}.
\end{gather}
$$
(see [[Proof of Change of Variables Formula for Indefinite Integrals]])

The validity of the inverse substitution rule requires that $\varphi'(t)$ maintains a strict sign on $J$, ensuring that $\varphi$ is strictly monotonic and topologically homeomorphic onto its image.

### Integration by Parts
The product rule of differential calculus, $(u \cdot v)' = u' v + u v'$, provides the second foundational transformation method for primitives: integration by parts: 
$$
\begin{gather}
\textbf{Theorem: Integration by Parts for Primitives} \\[5mm]
\text{Let } u, v: I \to \mathbb{R} \text{ be continuously differentiable functions on an open interval } I. \\[2mm]
\text{If the function } u'(x) v(x) \text{ admits a primitive on } I, \text{ then } u(x) v'(x) \text{ also admits a primitive on } I, \text{ and:} \\[3.5mm]
\int u(x) v'(x) \, dx = u(x) v(x) - \int u'(x) v(x) \, dx.
\end{gather}
$$
(see [[Proof of Integration by Parts for Primitives]])

Expressed in differential notation with $du = u'(x)\,dx$ and $dv = v'(x)\,dx$, this identity assumes the compact form:
$$
\begin{gather}
\int u \, dv = u v - \int v \, du.
\end{gather}
$$

A recurring algorithmic manifestation of integration by parts is the derivation of recursive invariant reduction formulas: 
$$
\begin{gather}
\textbf{Proposition: Recursive Invariant for Quadratic Denominators} \\[5mm]
\text{Define the parametric sequence of primitives for } n \in \mathbb{N}: \\[2mm]
I_n(x) := \int \frac{dx}{(x^2 + 1)^n}. \\[3.5mm]
\text{Applying integration by parts with } u = (x^2 + 1)^{-n} \text{ and } dv = dx \text{ establishes the recurrence relation:} \\[3.5mm]
I_{n+1}(x) = \frac{x}{2n (x^2 + 1)^n} + \frac{2n - 1}{2n} I_n(x) \quad \forall n \ge 1, \\[3.5mm]
\text{anchored by the base primitive } I_1(x) = \arctan(x) + C.
\end{gather}
$$
(see [[Proof of Recursive Invariant for Quadratic Denominators]])

---
# Integration of Rational Functions and Algebraic Decidability

### Partial Fraction Decomposition Over the Real Field
A central triumph of classical algebra is that the primitive of any real rational function $R(x) = \frac{P(x)}{Q(x)}$ can be computed systematically in closed form using elementary transcendental functions (specifically, rational fractions, natural logarithms, and inverse tangents).

Let $P(x), Q(x) \in \mathbb{R}[x]$ be polynomials with real coefficients, where $Q(x)$ is monic and non-zero. If $\deg(P) \ge \deg(Q)$, polynomial Euclidean long division yields:
$$
\begin{gather}
\frac{P(x)}{Q(x)} = S(x) + \frac{P_0(x)}{Q(x)}, \quad \text{with } \deg(P_0) < \deg(Q),
\end{gather}
$$
where the polynomial part $S(x)$ integrates immediately to a polynomial primitive.

By the Fundamental Theorem of Algebra, any monic polynomial $Q(x) \in \mathbb{R}[x]$ factors uniquely over $\mathbb{R}$ into products of linear factors and irreducible quadratic factors:
$$
\begin{gather}
Q(x) = \prod_{j=1}^r (x - a_j)^{m_j} \prod_{k=1}^s (x^2 + p_k x + q_k)^{n_k},
\end{gather}
$$
where $p_k^2 - 4q_k < 0$, and $m_j, n_k \in \mathbb{N}$.

$$
\begin{gather}
\textbf{Theorem: Partial Fraction Decomposition over the Real Field} \\[5mm]
\text{Let } \frac{P_0(x)}{Q(x)} \text{ be a proper real rational fraction with } \deg(P_0) < \deg(Q). \\[2mm]
\text{Then there exist uniquely determined real constants } A_{j,\ell}, B_{k,r}, C_{k,r} \in \mathbb{R} \text{ such that:} \\[3.5mm]
\frac{P_0(x)}{Q(x)} = \sum_{j=1}^r \sum_{\ell=1}^{m_j} \frac{A_{j,\ell}}{(x - a_j)^\ell} + \sum_{k=1}^s \sum_{r=1}^{n_k} \frac{B_{k,r} x + C_{k,r}}{(x^2 + p_k x + q_k)^r}.
\end{gather}
$$
(see [[Proof of Partial Fraction Decomposition Theorem over the Real Field]])

### Reduction Formulas and Primitives of Quadratic Denominators
By linearity, evaluating the indefinite integral of any rational function reduces to integrating terms of two elementary classes:
1. Linear fractions:
$$
\begin{gather}
\int \frac{A}{(x - a)^\ell} \, dx = \begin{cases} A \ln |x - a| + C, & \ell = 1, \\[2mm] \frac{A}{(1 - \ell)(x - a)^{\ell - 1}} + C, & \ell > 1. \end{cases}
\end{gather}
$$
2. Quadratic fractions:
$$
\begin{gather}
\int \frac{B x + C}{(x^2 + p x + q)^n} \, dx.
\end{gather}
$$
Completing the square in the denominator via $x^2 + p x + q = (x + p/2)^2 + (q - p^2/4) =: u^2 + a^2$ (where $a = \sqrt{q - p^2/4} > 0$) separates the quadratic fraction into a logarithmic derivative and a purely rational term:
$$
\begin{gather}
\int \frac{B x + C}{(x^2 + p x + q)^n} \, dx = \frac{B}{2} \int \frac{2u \, du}{(u^2 + a^2)^n} + \left(C - \frac{Bp}{2}\right) \int \frac{du}{(u^2 + a^2)^n}.
\end{gather}
$$
The first term yields a rational function for $n > 1$ or $\frac{B}{2}\ln(u^2 + a^2)$ for $n = 1$. The second term is resolved by the recursive reduction formula for $I_n(u/a)$.

This decomposition reveals that every real rational function possesses an elementary primitive consisting exclusively of rational terms, logarithms of linear and quadratic factors, and arctangents of linear arguments.

$$
\begin{gather}
\textbf{Theorem: Ostrowsky's Rational Integral Criterion} \\[5mm]
\text{Let } R(x) = \frac{P(x)}{Q(x)} \in \mathbb{R}(x) \text{ be a proper rational function, where } Q(x) = \prod_{j=1}^r (x - \alpha_j)^{m_j} \\[2mm]
\text{in its algebraic closure } \mathbb{C}[x], \text{ with distinct roots } \alpha_j. \\[2mm]
\text{Then the primitive } \int R(x) \, dx \text{ is itself a rational function } S(x) \in \mathbb{R}(x) \\[2mm]
\text{if and only if the complex residues at all poles vanish identically:} \\[3.5mm]
\operatorname{Res}\big(R(x); \alpha_j\big) = 0 \quad \forall j \in \{1, \dots, r\}.
\end{gather}
$$
(see [[Proof of Ostrowsky's Rational Integral Criterion]])

---
# Transformation of Non-Rational and Trigonometric Classes

### Primitives of Rational Trigonometric Expressions: The Weierstrass Universal Substitution
Integrands formulated as rational expressions of circular functions, $R(\sin x, \cos x)$, can be transformed into purely rational algebraic integrands through the *Weierstrass half-angle substitution*.

$$
\begin{gather}
\textbf{Theorem: Weierstrass Universal Half-Angle Substitution} \\[5mm]
\text{Let } R(u, v) \text{ be a rational function of two real variables. On any open interval } I_k = ((2k-1)\pi, (2k+1)\pi), \\[2mm]
\text{the substitution } t := \tan\left(\frac{x}{2}\right) \text{ transforms the trigonometric differential form into a rational fraction:} \\[3.5mm]
\sin x = \frac{2t}{1 + t^2}, \quad \cos x = \frac{1 - t^2}{1 + t^2}, \quad dx = \frac{2 \, dt}{1 + t^2}, \\[3.5mm]
\text{yielding the algebraic identity:} \\[3.5mm]
\int R(\sin x, \cos x) \, dx = \left[ \int R\left(\frac{2t}{1 + t^2}, \frac{1 - t^2}{1 + t^2}\right) \frac{2 \, dt}{1 + t^2} \right]_{t = \tan(x/2)}.
\end{gather}
$$
(see [[Proof of Weierstrass Universal Substitution Theorem]])

The geometric underpinning of the Weierstrass substitution is the stereographic projection of the unit circle $u^2 + v^2 = 1$ from the point $(-1, 0)$ onto the vertical axis $u = 0$. Every ray through $(-1, 0)$ with slope $t$ intersects the unit circle at a unique point $(\cos x, \sin x)$:

```easy-tikz
title $\text{Stereographic Projection and the Weierstrass Half-Angle Parameterization}$
xlabel $u$
ylabel $v$
show x from -2.475 to 2.525 and y from -1.881 to 2.619
axes on the edges
size 12 x 8
plot top(x) = sqrt(max(0.0, 1.0 - x^2)), from x = -1.0 to 1.0, in cyan, thick
plot bottom(x) = -sqrt(max(0.0, 1.0 - x^2)), from x = -1.0 to 1.0, in cyan, thick
draw a line from (0.0, -2.0) to (0.0, 2.3), in gray, dashed
draw a line from (-1.0, 0.0) to (0.0, 1.2), in orange, thick
draw a line from (0.0, 1.2) to (0.47, 0.88), in orange, thick, dashed
mark (-1.0, 0.0), in green, large
mark (0.0, 1.2), in orange, large
mark (0.47, 0.88), in cyan, large
write "$(-1, 0)$" at (-1.1, -0.05) in green, left
write "$(0, t)$" at (0.1, 1.35) in orange, right
write "$(\\cos x, \\sin x)$" at (0.6, 1.05) in cyan, right
write "$\\text{Projection Ray: } v = t(u + 1)$" at (-2.18, 1.35) in orange, right

```

Although the substitution $t = \tan(x/2)$ is algebraically universal, it can inflate polynomial degrees. When integrands possess parity symmetries, specialized alternative transformations reduce computational overhead:
1. If $R(-\sin x, \cos x) = -R(\sin x, \cos x)$ (odd in $\sin x$), the substitution $u = \cos x$ rationalizes the expression.
2. If $R(\sin x, -\cos x) = -R(\sin x, \cos x)$ (odd in $\cos x$), the substitution $u = \sin x$ rationalizes the expression.
3. If $R(-\sin x, -\cos x) = R(\sin x, \cos x)$ (even with respect to both signs simultaneously), the direct tangent substitution $t = \tan x$ rationalizes the integral with $\sin^2 x = \frac{t^2}{1+t^2}$, $\cos^2 x = \frac{1}{1+t^2}$, and $dx = \frac{dt}{1+t^2}$.

### Primitives of Quadratic Irrationals: The Euler Substitutions
Integrals containing square roots of quadratic polynomials, $\int R(x, \sqrt{a x^2 + b x + c}) \, dx$, represent algebraic curves of genus zero. Such expressions can be rationalized by parameterizing the conic section $y^2 = a x^2 + b x + c$ through secant lines passing through a known point on the curve. This geometric construction produces the three *Euler substitutions*: 
$$
\begin{gather}
\textbf{Theorem: The Three Euler Substitutions for Quadratic Irrationals} \\[5mm]
\text{Let } y = \sqrt{a x^2 + b x + c} \text{ with } b^2 - 4ac \neq 0. \text{ Then } \int R(x, y) \, dx \text{ rationalizes via:} \\[5mm]
\text{1. First Euler Substitution (applicable when } a > 0\text{):} \\[2mm]
\sqrt{a x^2 + b x + c} = \pm \sqrt{a} x + t. \\[2mm]
\text{Squaring eliminates the quadratic term } a x^2, \text{ resolving } x \text{ and } dx \text{ as rational functions of } t: \\[3.5mm]
x = \frac{t^2 - c}{b \mp 2\sqrt{a}t}, \quad dx = 2\frac{\mp \sqrt{a}t^2 + bt \mp c\sqrt{a}}{(b \mp 2\sqrt{a}t)^2} \, dt. \\[5mm]
\text{2. Second Euler Substitution (applicable when } c > 0\text{):} \\[2mm]
\sqrt{a x^2 + b x + c} = x t \pm \sqrt{c}. \\[2mm]
\text{Squaring eliminates the constant term } c, \text{ isolating } x \text{ as a rational function of } t: \\[3.5mm]
x = \frac{\pm 2\sqrt{c}t - b}{a - t^2}, \quad dx = 2\frac{\pm \sqrt{c}t^2 - bt \pm a\sqrt{c}}{(a - t^2)^2} \, dt. \\[5mm]
\text{3. Third Euler Substitution (applicable when } a x^2 + b x + c = a(x - x_1)(x - x_2) \text{ has real roots):} \\[2mm]
\sqrt{a(x - x_1)(x - x_2)} = t (x - x_1). \\[2mm]
\text{Dividing by } (x - x_1) \text{ resolves } x \text{ linearly in terms of } t^2: \\[3.5mm]
x = \frac{a x_2 - x_1 t^2}{a - t^2}, \quad dx = \frac{2a(x_2 - x_1)t}{(a - t^2)^2} \, dt.
\end{gather}
$$
(see [[Proof of the Three Euler Substitutions for Quadratic Irrationals]])

A fundamental question regarding algebraic integrability was resolved by Pafnuty Chebyshev: Under what conditions can an irrational differential binomial be integrated in terms of elementary functions?

$$
\begin{gather}
\textbf{Theorem: Chebyshev's Differential Binomial Integration Criterion} \\[5mm]
\text{Let } p, q, r \in \mathbb{Q} \text{ be rational numbers with } a, b \in \mathbb{R} \setminus \{0\}. \\[2mm]
\text{The differential binomial primitive:} \\[3.5mm]
\int x^p (a + b x^q)^r \, dx \\[3.5mm]
\text{is expressible in terms of elementary functions if and only if at least one of} \\[2mm]
\text{the following three conditions is satisfied:} \\[2mm]
1. \; r \in \mathbb{Z} \quad (\text{rationalization via } x = t^N, \text{ where } N \text{ is the common denominator of } p \text{ and } q), \\[2mm]
2. \; \frac{p + 1}{q} \in \mathbb{Z} \quad (\text{rationalization via the substitution } a + b x^q = t^s, \text{ where } s \text{ is the denominator of } r), \\[2mm]
3. \; \frac{p + 1}{q} + r \in \mathbb{Z} \quad (\text{rationalization via } a x^{-q} + b = t^s, \text{ where } s \text{ is the denominator of } r).
\end{gather}
$$
(see [[Proof of Chebyshev's Differential Binomial Theorem]])

