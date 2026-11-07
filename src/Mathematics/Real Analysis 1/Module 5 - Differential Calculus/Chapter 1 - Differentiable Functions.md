---
dg-publish: true
---
# The Differential and the Derivative
The core analytical mechanism of differential calculus is the local approximation of nonlinear functional behavior by linear mappings. When a complex system—whether an orbital trajectory in celestial mechanics, the state variable of a thermodynamic reservoir, or the pricing manifold of a financial contingent claim—is perturbed within a sufficiently small neighborhood of a reference state, its response is governed predominantly by its first-order linear component. 

In classical real analysis, differentiation is not an ad-hoc algebraic recipe for calculating slope quotients; it is the rigorous study of the *tangent mapping* or *differential*. In this chapter, the theory of differentiation for real-valued functions of a single real variable is deductively constructed from the topological and limit foundations established in the preceding modules.

---
# Functions Differentiable at a Point

### Increments and the Principal Linear Part
Let $E \subseteq \mathbb{R}$ be an arbitrary subset of the real numbers, let $x_0 \in E$ be an interior point of $E$ ($\exists \delta_0 > 0$ such that $(x_0 - \delta_0, x_0 + \delta_0) \subseteq E$), and let $f: E \to \mathbb{R}$ denote a real-valued mapping. 

For any displacement $h \in \mathbb{R}$ satisfying $|h| < \delta_0$, the argument $x_0 + h$ remains within $E$. The resulting difference in the functional value is termed the *increment of the function* at $x_0$ corresponding to the increment $h$ of the argument:
$$\Delta f(x_0; h) := f(x_0 + h) - f(x_0) \tag{1}$$

The central problem of differential calculus consists of isolating from the increment $\Delta f(x_0; h)$ a component that depends linearly on $h$ and serves as the principal part of the increment as $h \to 0$:
$$\begin{gather}
\textbf{Definition: Differentiability at a Point} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(E), \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{The function } f \text{ is differentiable at the point } x_0 \text{ if there exists a real constant } A \in \mathbb{R} \\[2mm]
\text{such that the increment admits the asymptotic expansion:} \\[3.5mm]
\Delta f(x_0; h) = A \cdot h + o(h) \quad \text{as } h \to 0, \\[3.5mm]
\text{which is equivalent to the existence of a function } \alpha(h) \text{ satisfying } \lim_{h \to 0} \alpha(h) = 0 \text{ such that:} \\[2mm]
f(x_0 + h) - f(x_0) = A \cdot h + \alpha(h) \cdot h \quad \forall h \in (-\delta_0, \delta_0).
\end{gather}$$

The linear function $h \mapsto A \cdot h$ is termed the *differential* of the function $f$ at the point $x_0$, denoted by $df(x_0)$ or $df(x_0; h)$. The scalar coefficient $A$ is termed the *derivative* of $f$ at $x_0$, denoted by $f'(x_0)$ or $\frac{df}{dx}(x_0)$.

$$\begin{gather}
\textbf{Theorem: Uniqueness of the Differential and Difference Quotient Criterion} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(E), \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{1. If } f \text{ is differentiable at } x_0, \text{ the linear mapping } h \mapsto A \cdot h \text{ is uniquely determined.} \\[2mm]
\text{2. The function } f \text{ is differentiable at } x_0 \text{ if and only if the limit of the difference quotient exists in } \mathbb{R}\text{:} \\[3.5mm]
f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}.
\end{gather}$$
(see [[Proof of the Uniqueness of the Differential and Derivative]])

>[!danger]+ Intuition: The Local Linear Microscope
>Consider observing the graph of a curved function through an optical microscope focused at the point $(x_0, f(x_0))$. As the magnification increases indefinitely (corresponding to $h \to 0$), the nonlinear curvature of the graph recedes into higher-order insignificance ($o(h)$). The curve increasingly resembles a straight line. Differentiability is the analytical guarantee that this local straight line exists and exhibits a finite, unambiguous inclination.

### The Canonical Differential of the Identity Map
Consider the identity mapping on the real continuum:
$$I: \mathbb{R} \to \mathbb{R}, \quad I(x) = x \tag{2}$$
For any point $x \in \mathbb{R}$ and increment $h$, the increment of the identity map is $\Delta I(x; h) = (x + h) - x = 1 \cdot h + 0$. Comparing this identity with the definition of differentiability at a point establishes that $I$ is differentiable everywhere with $I'(x) \equiv 1$. 

The differential of the identity coordinate function $x$ is denoted simply by $dx$:
$$dx(h) := 1 \cdot h = h \tag{3}$$
Because $dx$ acts on the displacement vector $h$ by reproducing $h$ identically, the differential $df(x_0)(h) = f'(x_0) \cdot h$ can be rewritten in operator-free form:
$$df(x_0) = f'(x_0) \, dx \tag{4}$$
The formula of step 4 demonstrates that Leibniz's classical notation $\frac{df}{dx}(x_0)$ is the literal ratio of two differential forms evaluated along the coordinate line: the increment of the ordinate along the tangent line divided by the coordinate increment.

### Relationship to Continuity
$$\begin{gather}
\textbf{Theorem: Differentiability Implies Pointwise Continuity} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(E), \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{If } f \text{ is differentiable at } x_0, \text{ then } f \text{ is continuous at } x_0.
\end{gather}$$
(see [[Proof of the Differentiability Implies Continuity Criterion]])

The converse of the Differentiability Implies Pointwise Continuity Theorem is false. Pointwise continuity does not guarantee differentiability:
1. **Corner Points:** The absolute value function $f(x) = |x|$ is uniformly continuous across all of $\mathbb{R}$, yet fails to be differentiable at $x_0 = 0$ because:
   $$\lim_{h \to 0^+} \frac{|h| - 0}{h} = 1 \neq -1 = \lim_{h \to 0^-} \frac{|h| - 0}{h} \tag{5}$$
2. **Nowhere-Differentiable Continuous Functions:** There exist functions continuous everywhere on $\mathbb{R}$ that are differentiable at *no* point of $\mathbb{R}$. The canonical construction, due to Karl Weierstrass, is the Fourier series:
   $$W(x) = \sum_{n=0}^\infty a^n \cos(b^n \pi x), \quad 0 < a < 1, \quad ab > 1 + \frac{3}{2}\pi \tag{6}$$
   which exhibits extreme fractal self-similarity, precluding the existence of a principal linear part at any scale.

---

# Geometry of the Differential: Tangency and Contact

### Tangent Lines as Limits of Secants
Let $f: E \to \mathbb{R}$ be defined on a neighborhood of $x_0$. Consider the secant line passing through the fixed point $P_0 = (x_0, f(x_0))$ and a neighboring variable point $P = (x_0 + h, f(x_0 + h))$. The slope of this secant chord is:
$$k(h) = \frac{f(x_0 + h) - f(x_0)}{h} \tag{7}$$

If $f$ is differentiable at $x_0$, as $h \to 0$ the point $P$ traverses the curve toward $P_0$, and the secant slope $k(h)$ converges to the finite value $f'(x_0)$. 

```easy-tikz
title $\text{Secant Chords Converging to the Tangent Line}$
xlabel $x$
ylabel $y$
show x from 0 to 8 and y from 0 to 6
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 0.4*x + 0.08*x^2, from x = 0.5 to 7.0, in teal, very thick
draw a line from (0.5, 1.48) to (7.5, 5.96), in red, thick
draw a segment from (1.0, 1.48) to (6.5, 6.98), in blue, dashed
draw a segment from (1.0, 1.48) to (5.5, 4.60), in purple, dashed
draw a segment from (2.0, 0.2) to (2.0, 2.12), in gray, dotted
draw a segment from (5.0, 0.2) to (5.0, 5.0), in gray, dotted
draw a segment from (3.5, 0.2) to (3.5, 3.38), in gray, dotted
mark (2.0, 2.12), in black, large
mark (5.0, 5.0), in blue, medium
mark (3.5, 3.38), in purple, medium
write "$P_0(x_0, f(x_0))$" at (2.0, 2.45), in black, above left
write "$P_2(x_0 + h_2, f(x_0 + h_2))$" at (5.05, 5.15), in blue, right
write "$P_1(x_0 + h_1, f(x_0 + h_1))$" at (3.55, 3.65), in purple, right
write "$\text{Tangent Line } y = L(x)$" at (6.8, 5.4), in red, right
write "$y = f(x)$" at (6.8, 4.2), in teal, right
write "$x_0$" at (2.0, 0.0), in black, below
write "$x_0 + h_1$" at (3.5, 0.0), in purple, below
write "$x_0 + h_2$" at (5.0, 0.0), in blue, below
```

$$\begin{gather}
\textbf{Definition: The Tangent Line} \\[5mm]
\text{Let } f: E \to \mathbb{R} \text{ be differentiable at } x_0 \in \text{int}(E). \\[2mm]
\text{The tangent line to the graph of } f \text{ at the point } (x_0, f(x_0)) \text{ is the straight line defined by the affine equation:} \\[3.5mm]
y = T(x) := f(x_0) + f'(x_0)(x - x_0)
\end{gather}$$

### Order of Contact
The tangent line is distinguished from all other straight lines intersecting the graph at $(x_0, f(x_0))$ by its order of geometric contact:

$$\begin{gather}
\textbf{Definition: Contact of Order } n \\[5mm]
\text{Two functions } f, \varphi: U(x_0) \to \mathbb{R} \text{ have contact of order } n \in \mathbb{N} \text{ at the point } x_0 \text{ if:} \\[3.5mm]
f(x) - \varphi(x) = o((x - x_0)^n) \quad \text{as } x \to x_0.
\end{gather}$$

$$\begin{gather}
\textbf{Theorem: Geometric Characterization of the Tangent Line} \\[5mm]
\text{Let } f: U(x_0) \to \mathbb{R} \text{ be defined in a neighborhood of } x_0. \\[2mm]
\text{1. The graph of an affine function } \varphi(x) = c_0 + c_1(x - x_0) \text{ has contact of order } 0 \text{ with } f \text{ at } x_0 \\[2mm]
\text{if and only if } c_0 = f(x_0) \text{ and } f \text{ is continuous at } x_0. \\[2mm]
\text{2. The affine function } \varphi(x) \text{ has contact of order } 1 \text{ with } f \text{ at } x_0 \text{ if and only if } f \text{ is differentiable at } x_0 \\[2mm]
\text{and } \varphi(x) \equiv T(x) = f(x_0) + f'(x_0)(x - x_0).
\end{gather}$$
(see [[Proof of the Contact Order of the Tangent Line]])

The Geometric Characterization of the Tangent Line Theorem proves that the tangent line is the *unique* straight line that approximates the curve with residual error decaying strictly faster than the first power of distance:
$$f(x) - T(x) = o(x - x_0) \tag{8}$$

---

# The Role of Coordinates and Affine Invariance

Let $x$ denote the coordinate on the domain line and $y$ the coordinate on the codomain line. Consider performing an affine coordinate change:
$$\tilde{x} = \alpha_1 x + \beta_1, \quad \tilde{y} = \alpha_2 y + \beta_2 \quad (\alpha_1 \neq 0, \alpha_2 \neq 0) \tag{9}$$

Under this change of coordinates, displacements scale linearly:
$$d\tilde{x} = \alpha_1 \, dx, \quad d\tilde{y} = \alpha_2 \, dy \tag{10}$$
The function $y = f(x)$ becomes $\tilde{y} = \tilde{f}(\tilde{x}) = \alpha_2 f\left(\frac{\tilde{x} - \beta_1}{\alpha_1}\right) + \beta_2$.

$$\begin{gather}
\textbf{Theorem: Invariance of the First Differential} \\[5mm]
\text{The differential } df(x_0) \text{ is a geometric invariant of the tangent space } T_{x_0}\mathbb{R}. \\[2mm]
\text{Its representation as an operator on displacements satisfies:} \\[3.5mm]
d\tilde{y}(\tilde{x}_0; d\tilde{x}) = \alpha_2 \, dy(x_0; dx).
\end{gather}$$
(see [[Proof of the Coordinate Invariance of the Differential]])

The first differential represents the intrinsic linear map between tangent spaces $df(x_0): T_{x_0}\mathbb{R} \to T_{f(x_0)}\mathbb{R}$. Its geometric structure does not depend on the arbitrary choice of origin or unit scale.

---
# Linear Approximations, Error Bounds, and Sensitivity
The differential provides the theoretical foundation for linear approximation algorithms in applied mathematics and *numerical analysis*: 
$$\begin{gather}
\textbf{Definition: Linearization} \\[5mm]
\text{Let } f: E \to \mathbb{R} \text{ be differentiable at } x_0 \in \text{int}(E). \\[2mm]
\text{The linear approximation (or linearization) of } f \text{ at } x_0 \text{ is the function:} \\[3.5mm]
L(x) := f(x_0) + f'(x_0)(x - x_0).
\end{gather}$$

In empirical applications, one writes $\Delta f \approx df(x_0; \Delta x)$. To transform this heuristic statement into an analytical theorem, the remainder error must be bounded:
$$\begin{gather}
\textbf{Theorem: Quantitative Linearization Error Bound} \\[5mm]
\text{Let } f \in C^2([x_0 - \delta, x_0 + \delta]) \text{ and let } M_2 = \sup_{t \in [x_0 - \delta, x_0 + \delta]} |f''(t)|. \\[2mm]
\text{Then for every } x \in [x_0 - \delta, x_0 + \delta], \text{ the approximation error satisfies:} \\[3.5mm]
|f(x) - L(x)| \le \frac{M_2}{2} (x - x_0)^2.
\end{gather}$$
(see [[Proof of the Linearization Error Bound]])

>[!example]- Quantitative Application: Financial Delta Hedging
>In continuous-time financial engineering, let $V(S)$ denote the price of an equity derivative viewed as a function of the underlying stock price $S \in (0, \infty)$, holding time and interest rates fixed. A market maker seeking to insulate the portfolio against price fluctuations forms a localized hedge by calculating the financial "Delta":
>$$\Delta := \frac{dV}{dS}(S_0) \tag{11}$$
>The value change of the derivative contract under an asset price shock $\Delta S = S - S_0$ is:
>$$\Delta V = \Delta \cdot \Delta S + \varepsilon(\Delta S) \tag{12}$$
>By selling short $\Delta$ shares of the underlying stock, the hedged portfolio value $\Pi(S) = V(S) - \Delta \cdot S$ exhibits vanishing first-order sensitivity:
>$$\Delta \Pi = \Delta V - \Delta \cdot \Delta S = \varepsilon(\Delta S) = \mathcal{O}((\Delta S)^2) \tag{13}$$
>The residual unhedged financial risk is precisely the second-order Taylor error term governed by the contract's "Gamma" ($\Gamma = \frac{d^2 V}{dS^2}$).

---
# Physical and Kinematic Origins of the Derivative
Having constructed the formal mathematical apparatus of differentiability, its historical origins in the natural sciences can now be examined with deductive clarity.

### 1. Instantaneous Velocity in Classical Kinematics
Consider the rectilinear motion of a point mass whose position along a spatial axis is given as a function of time by $x = x(t)$. Over a finite time interval $[t_0, t_0 + \Delta t]$, the average velocity is:
$$\bar{v}(t_0; \Delta t) = \frac{x(t_0 + \Delta t) - x(t_0)}{\Delta t} \tag{14}$$

If the trajectory is differentiable at $t_0$, the instantaneous velocity is defined as the limit:
$$v(t_0) := \lim_{\Delta t \to 0} \bar{v}(t_0; \Delta t) = \dot{x}(t_0) \tag{15}$$
The displacement over an infinitesimal time step admits the linear expansion:
$$x(t_0 + \Delta t) - x(t_0) = v(t_0)\Delta t + o(\Delta t) \tag{16}$$
In vector kinematics, where $\mathbf{r}(t) = (x(t), y(t), z(t))$ describes orbital motion (such as in Kepler’s two-body problem), the instantaneous velocity vector $\mathbf{v}(t_0) = \dot{\mathbf{r}}(t_0)$ is tangent to the spatial trajectory, with magnitude $\|\mathbf{v}(t_0)\|$ representing speed.

### 2. The Equilibrium Free Surface of a Rotating Fluid
Consider a cylindrical glass of water rotating with constant angular velocity $\omega$ about its vertical $y$-axis. A fluid element of mass $m$ situated on the free surface at distance $x$ from the rotation axis experiences two planar forces:
1. Downward gravitational force: $F_g = mg$.
2. Outward centrifugal force: $F_c = m\omega^2 x$.

In hydrostatic equilibrium, the free liquid surface must align perpendicular to the resultant force vector $\mathbf{F} = m\omega^2 x \, \mathbf{e}_x - mg \, \mathbf{e}_y$.

```easy-tikz
title $\text{Hydrostatic Force Balance on Rotating Liquid Surface}$
xlabel $x$
ylabel $y$
show x from 0 to 6 and y from 0 to 5
axes on the edges
size 10 x 7
plot f(x) = 1.0 + 0.1*x^2, from x = 0 to 5.5, in teal, very thick
draw a segment from (3.0, 1.9) to (5.0, 3.1), in red, thick
draw a segment from (3.0, 1.9) to (3.0, 0.4), in blue, thick, with an arrow at (3.0, 0.4)
draw a segment from (3.0, 1.9) to (4.8, 1.9), in purple, thick, with an arrow at (4.8, 1.9)
draw a segment from (3.0, 1.9) to (4.8, 0.4), in black, thick, with an arrow at (4.8, 0.4)
mark (3.0, 1.9), in black, large
write "$P(x, y)$" at (2.7, 2.15), in black, above
write "$\mathbf{F}_g = -mg\mathbf{e}_y$" at (3.05, 0.5), in blue, left
write "$\mathbf{F}_c = m\omega^2 x\mathbf{e}_x$" at (4.85, 2.15), in purple, above
write "$\mathbf{F}_{\text{net}}$" at (4.9, 0.35), in black, right
write "$\text{Surface } y = f(x)$" at (4.8, 3.8), in teal, right
write "$\text{Tangent Line}$" at (5.0, 3.2), in red, right
```

The inclination tangent of the surface curve $y = f(x)$ must satisfy the slope ratio:
$$\begin{gather}
\textbf{Proposition: Differential Equation of the Rotating Fluid Surface} \\[5mm]
f'(x) = \frac{F_c}{F_g} = \frac{m\omega^2 x}{mg} = \frac{\omega^2}{g}x.
\end{gather}$$
Deducing that a function whose derivative is proportional to $x$ must be quadratic (as proven formally in Chapter 3), the free surface forms a paraboloid of revolution:
$$f(x) = f(0) + \frac{\omega^2}{2g}x^2 \tag{17}$$

### 3. Optical Focal Reflection of Conic Mirrors
Consider the parabola $y = \frac{x^2}{2p}$ with focus located at $F = (0, p/2)$ and directrix $y = -p/2$. Fermat’s principle of least action implies that rays emanating parallel to the symmetry axis must reflect into the focus.

$$\begin{gather}
\textbf{Theorem: The Parabolic Reflection Property} \\[5mm]
\text{Let } P_0 = (x_0, y_0) \text{ be a point on the parabola } y = \frac{x^2}{2p}. \\[2mm]
\text{The tangent line } T \text{ to the parabola at } P_0 \text{ has slope } f'(x_0) = \frac{x_0}{p}. \\[2mm]
\text{The angle between } T \text{ and the vertical line } x = x_0 \text{ equals the angle between } T \text{ and the focal segment } FP_0.
\end{gather}$$
(see [[Proof of the Optical Reflection Property of Parabolas]])

This classical theorem confirms that the tangent line defined purely by the limit of difference quotients corresponds exactly to physical wave reflection in geometric optics.
