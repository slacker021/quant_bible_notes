---
dg-publish: true
---
# The Basic Rules of Differentiation
Having established the foundational concept of the differential as the principal linear part of a local increment, the task now turns to developing the structural algebra of differentiation. Rather than recalculating limits of difference quotients from first principles for every combination of functions, differential calculus provides a closed operational algebra: given differentiable constituent functions, their linear combinations, products, quotients, compositions, and inverses can be differentiated systematically.

Throughout this chapter, all functions are real-valued mappings of a single real variable, $f: E \to \mathbb{R}$ with $E \subseteq \mathbb{R}$, and all points $x_0$ are interior points of the respective domains.

---
# Differentiation and the Arithmetic Operations
$$\begin{gather}
\textbf{Theorem: The Arithmetic Algebra of Derivatives and Differentials} \\[5mm]
\text{Let } f, g: E \to \mathbb{R} \text{ be functions defined on a neighborhood of } x_0 \in \mathbb{R}, \text{ and suppose both } f \text{ and } g \\
\text{are differentiable at } x_0. \text{ Then:} \\[3mm]
\begin{align}
\text{1. Linearity:} \quad &(c_1 f + c_2 g)'(x_0) = c_1 f'(x_0) + c_2 g'(x_0) \quad \forall c_1, c_2 \in \mathbb{R}, \\[2mm]
&d(c_1 f + c_2 g)(x_0) = c_1 \, df(x_0) + c_2 \, dg(x_0). \\[3mm]
\text{2. Leibniz Product Rule:} \quad &(f \cdot g)'(x_0) = f'(x_0)g(x_0) + f(x_0)g'(x_0), \\[2mm]
&d(fg)(x_0) = g(x_0) \, df(x_0) + f(x_0) \, dg(x_0). \\[3mm]
\text{3. Quotient Rule:} \quad &\text{If } g(x_0) \neq 0, \text{ then } \frac{f}{g} \text{ is differentiable at } x_0, \text{ with:} \\[2mm]
&\left(\frac{f}{g}\right)'(x_0) = \frac{f'(x_0)g(x_0) - f(x_0)g'(x_0)}{(g(x_0))^2}, \\[2mm]
&d\left(\frac{f}{g}\right)(x_0) = \frac{g(x_0) \, df(x_0) - f(x_0) \, dg(x_0)}{(g(x_0))^2}.
\end{align}
\end{gather}$$
(see [[Proof of the Arithmetic Rules of Differentiation]])

>[!danger]+ Intuition: The Geometric Cross-Term of the Product Rule
>Consider a rectangle whose side lengths are $u(x)$ and $v(x)$, yielding instantaneous area $A(x) = u(x)v(x)$. When the argument $x$ is perturbed by an increment $h$, the dimensions expand by $\Delta u$ and $\Delta v$. The increment of the area is:
>$$\Delta A = (u + \Delta u)(v + \Delta v) - uv = v \Delta u + u \Delta v + \Delta u \Delta v \tag{1}$$
>Because both $u$ and $v$ are differentiable, $\Delta u = u' h + o(h)$ and $\Delta v = v' h + o(h)$. The corner rectangle $\Delta u \Delta v = \mathcal{O}(h^2)$ decays faster than $h$, leaving the two linear rectangular strips $v \, du + u \, dv$ as the exact differential.

---
# The Chain Rule and Carathéodory's Formulation

>[!warning]+ Warning: The Classical Singularity Pitfall
>In elementary calculus, the rule for differentiating a composite function $z = g(f(x))$ is frequently justified by writing the ratio of difference quotients:
>$$\frac{\Delta z}{\Delta x} = \frac{\Delta z}{\Delta y} \cdot \frac{\Delta y}{\Delta x} \tag{2}$$
>where $y = f(x)$ and $\Delta y = f(x + h) - f(x)$. 
>
>This naive argument possesses an insurmountable analytical flaw: the intermediate increment $\Delta y$ may vanish at points arbitrarily close to $x_0$ (for instance, if $f(x) = x^2 \sin(1/x)$ or if $f$ is constant), producing a division by zero that renders the equation of step 2 meaningless.

### Carathéodory’s Equivalence Criterion
To bypass this pitfall with complete analytical rigor, differentiability is reformulated via continuous slope extensions:
$$\begin{gather}
\textbf{Theorem: Carathéodory’s Criterion for Differentiability} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(E), \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{The function } f \text{ is differentiable at } x_0 \text{ if and only if there exists a function } \psi: E \to \mathbb{R} \\[2mm]
\text{such that } \psi \text{ is continuous at } x_0 \text{ and satisfies:} \\[3.5mm]
f(x) - f(x_0) = \psi(x)(x - x_0) \quad \forall x \in E. \\[3.5mm]
\text{In this case, } \psi(x_0) = f'(x_0).
\end{gather}$$
(see [[Proof of Carathéodory's Differentiability Criterion]])

### The Invariant Chain Rule
Using Carathéodory’s continuous slope function, the *Chain Rule* emerges simply as the preservation of continuity under composition:
$$\begin{gather}
\textbf{Theorem: The Invariant Chain Rule} \\[5mm]
\text{Let } X, Y \subseteq \mathbb{R}, \text{ let } x_0 \in \text{int}(X), \text{ let } f: X \to Y, \text{ and let } g: Y \to \mathbb{R}. \\[2mm]
\text{Suppose } f \text{ is differentiable at } x_0, \text{ and } g \text{ is differentiable at } y_0 = f(x_0) \in \text{int}(Y). \\[2mm]
\text{Then the composite function } (g \circ f): X \to \mathbb{R} \text{ is differentiable at } x_0. \\[2mm]
\text{Its differential is the composition of the respective linear tangent maps:} \\[3.5mm]
d(g \circ f)(x_0) = dg(y_0) \circ df(x_0), \\[3.5mm]
\text{which in coordinate derivative form reads:} \\[2mm]
(g \circ f)'(x_0) = g'(f(x_0)) \cdot f'(x_0).
\end{gather}$$
(see [[Proof of the Invariant Chain Rule]])

Because $dg(y_0)$ acts on displacements $k$ by $dg(y_0)(k) = g'(y_0)k$, evaluating the composition on the argument differential $dx$ yields:
$$d(g \circ f)(x_0)(dx) = dg(y_0)(df(x_0)(dx)) = g'(y_0) \cdot \big( f'(x_0) dx \big) = \big( g'(f(x_0)) f'(x_0) \big) dx \tag{3}$$
proving that the differential form $df = f' dx$ remains formally invariant whether $x$ is an independent variable or a dependent intermediate function.

---
# Differentiation of the Inverse Function

$$\begin{gather}
\textbf{Theorem: Differentiation of the Inverse Function} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be a continuous, strictly monotonic function defined on an interval } I \subseteq \mathbb{R}, \\[2mm]
\text{and let } J = f(I) \text{ denote its image interval. Let } x_0 \in \text{int}(I) \text{ and } y_0 = f(x_0) \in \text{int}(J). \\[2mm]
\text{If } f \text{ is differentiable at } x_0 \text{ and } f'(x_0) \neq 0, \text{ then the inverse function } f^{-1}: J \to I \\[2mm]
\text{is differentiable at } y_0, \text{ with derivative given by the reciprocal:} \\[3.5mm]
(f^{-1})'(y_0) = \frac{1}{f'(x_0)} = \frac{1}{f'(f^{-1}(y_0))}.
\end{gather}$$
(see [[Proof of the Differentiation of Inverse Functions]])

>[!danger]+ Intuition: Geometric Reflection Across the Diagonal
>The graph of $y = f(x)$ and the graph of $x = f^{-1}(y)$ are identical geometric subsets of $\mathbb{R}^2$. Under the reflection mapping $(x, y) \mapsto (y, x)$ across the line $y = x$, a straight line with non-zero slope $m = f'(x_0)$ reflects into a straight line with reciprocal slope $\tilde{m} = \frac{1}{m}$. The analytical non-vanishing condition $f'(x_0) \neq 0$ is the exact geometric requirement that prevents the reflected tangent line from becoming vertical. 
>
>Simply put, the both graphs of $y$ and $x$ look like reflections of one another, with an invisible line equidistant to both plots acting as a sort of mirror. 

---
# Parametric Curves and Single-Variable Implicit Calculus
In classical applied real analysis, functional relations are frequently defined not by an explicit formula $y = f(x)$, but through a parametric representation or an implicit equation. 

To maintain deductive purity in single-variable real analysis, parametric differentiation is grounded strictly upon the one-dimensional *Inverse Function Theorem* and the one-dimensional Chain Rule, completely avoiding unproven multivariable partial derivatives:
$$\begin{gather}
\textbf{Theorem: Differentiation of Parametric Curves} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be an open interval, and let } \varphi, \psi: I \to \mathbb{R} \text{ be differentiable functions describing} \\[2mm]
\text{a planar curve } t \mapsto (x(t), y(t)) = (\varphi(t), \psi(t)). \\[2mm]
\text{Let } t_0 \in I \text{ be a parameter value such that } \varphi'(t_0) \neq 0. \\[2mm]
\text{Then there exists an open neighborhood } U(t_0) \text{ on which } \varphi \text{ is strictly monotonic, admitting a differentiable} \\[2mm]
\text{inverse } t = \varphi^{-1}(x) \text{ on } V(x_0) \text{ with } x_0 = \varphi(t_0). \\[2mm]
\text{The composite single-variable function } y(x) := (\psi \circ \varphi^{-1})(x) \text{ is differentiable at } x_0, \text{ with derivative:} \\[3.5mm]
\frac{dy}{dx}(x_0) = \frac{\psi'(t_0)}{\varphi'(t_0)} = \frac{\dot{y}(t_0)}{\dot{x}(t_0)}.
\end{gather}$$
(see [[Proof of the Differentiation of Parametric Functions]])

If $\varphi$ and $\psi$ are twice differentiable, applying the Chain Rule and Quotient Rule to $\frac{dy}{dx}(t) = \frac{\dot{y}(t)}{\dot{x}(t)}$ yields the second parametric derivative:
$$\frac{d^2 y}{dx^2}(x_0) = \frac{d}{dt}\left(\frac{\dot{y}}{\dot{x}}\right) \cdot \frac{dt}{dx} = \frac{\ddot{y}\dot{x} - \dot{y}\ddot{x}}{\dot{x}^2} \cdot \frac{1}{\dot{x}} = \frac{\dot{x}\ddot{y} - \dot{y}\ddot{x}}{\dot{x}^3} \tag{4}$$

>[!example]- Physical Application: Relativistic Velocity Addition Under Lorentz Boosts
>In special relativity, let the trajectory of a particle observed in an inertial frame $K$ be parameterized by its coordinate $x = x(t)$. Under a Lorentz boost with relative velocity $v$, the coordinates $(\tilde{x}, \tilde{t})$ in frame $\tilde{K}$ are given by the linear parameterization:
>$$\tilde{x}(t) = \gamma(x(t) - vt), \quad \tilde{t}(t) = \gamma\left(t - \frac{v}{c^2}x(t)\right), \quad \text{where } \gamma = \frac{1}{\sqrt{1 - v^2/c^2}} \tag{5}$$
>Viewing $(\tilde{x}, \tilde{t})$ as a parametric curve driven by parameter $t$, the Differentiation of Parametric Curves Theorem establishes that the velocity observed in $\tilde{K}$ is:
>$$\tilde{u} = \frac{d\tilde{x}}{d\tilde{t}} = \frac{\dot{\tilde{x}}(t)}{\dot{\tilde{t}}(t)} = \frac{\gamma(\dot{x}(t) - v)}{\gamma\left(1 - \frac{v}{c^2}\dot{x}(t)\right)} = \frac{u - v}{1 - \frac{uv}{c^2}} \tag{6}$$
>where $u = \dot{x}(t)$ is the particle velocity in $K$. The equation of step 6 is Einstein's velocity addition law, derived purely as the derivative of a parametric single-variable curve.

---
# Higher-Order Derivatives and the General Leibniz Rule
Let $f: E \to \mathbb{R}$ be differentiable on an open interval $I \subseteq E$. The derivative $f'$ is itself a real-valued function $f': I \to \mathbb{R}$: 
$$\begin{gather}
\textbf{Definition: Higher-Order Derivatives} \\[5mm]
\text{The second derivative of } f \text{ at } x_0 \in I, \text{ denoted } f''(x_0) \text{ or } f^{(2)}(x_0), \text{ is defined as:} \\[3.5mm]
f''(x_0) := (f')'(x_0) = \lim_{h \to 0} \frac{f'(x_0 + h) - f'(x_0)}{h}. \\[3.5mm]
\text{Inductively, for any integer } n \ge 2, \text{ the } n\text{-th derivative of } f \text{ at } x_0 \text{ is defined as:} \\[3.5mm]
f^{(n)}(x_0) := \big( f^{(n-1)} \big)'(x_0).
\end{gather}$$
A function possessing continuous derivatives up to order $n$ on an open set $U$ is said to be of class $C^n(U)$. If derivatives of all orders exist, $f \in C^\infty(U)$ (smooth function).

$$\begin{gather}
\textbf{Theorem: The General Leibniz Rule for Products} \\[5mm]
\text{Let } u, v: I \to \mathbb{R} \text{ be } n \text{ times differentiable functions on an open interval } I. \\[2mm]
\text{Then the product function } (u \cdot v) \text{ is } n \text{ times differentiable on } I, \text{ and satisfies:} \\[3.5mm]
(u \cdot v)^{(n)}(x) = \sum_{k=0}^n \binom{n}{k} u^{(n-k)}(x) v^{(k)}(x), \\[3.5mm]
\text{where } \binom{n}{k} = \frac{n!}{k!(n - k)!} \text{ denotes the binomial coefficient.}
\end{gather}$$
(see [[Proof of the General Leibniz Formula for Higher Derivatives]])

### Non-Invariance of Higher-Order Differentials
While the first differential $df = f'(x)dx$ is invariant under arbitrary coordinate changes, higher-order differentials are *not* invariant. 

Let $y = f(x)$. Differentiating $dy = f'(x)dx$ again under the assumption that $x$ is an independent variable (so that $dx$ is constant, $d^2 x = 0$) gives:
$$d^2 y = d(f'(x)dx) = f''(x)(dx)^2 \tag{7}$$

However, if $x = \varphi(t)$ is a dependent variable of $t$, applying the product rule to $dy = f'(x(t)) \dot{x}(t) dt$ reveals:
$$d^2 y = f''(x)(dx)^2 + f'(x) d^2 x \tag{8}$$
The second term $f'(x) d^2 x$ represents the acceleration of the coordinate frame. This failure of invariance necessitates extreme care when dealing with higher-order differentials in coordinate changes.
