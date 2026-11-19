---
dg-publish: true
---
# The Variable Upper Limit Integral and Functional Regularity
Throughout the structural developments of [[Chapter 1 - Definition of the Integral and Description of the Set of Integrable Functions|chapter 1]] and [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|chapter 2]], the endpoints of integration remained fixed geometric boundaries. A profound conceptual transformation occurs when the terminal point of integration is freed, allowing it to vary continuously across the domain. Under this dynamic perspective, integration ceases to be merely a summative calculation producing an isolated real number; it transforms into an analytical mapping that constructs an entirely new function from an existing integrand. The dynamic accumulation function:
$$
\begin{gather}
F(x) := \int_a^x f(t)\,dt \tag{1}
\end{gather}
$$
bridges the discrete summation mechanics of integration with the infinitesimal differential geometry developed in Module 5.

The investigation of this dynamic accumulation mapping reveals one of the most remarkable phenomena in classical real analysis: *integration acts as an intrinsic smoothing operator*. While differentiation is inherently destabilizing—often degrading the regularity of a function, magnifying micro-oscillations, or destroying differentiability entirely—integration systematically absorbs discontinuities, dampens variations, and elevates the regularity class of the input integrand.

### Dynamic Accumulation and Metric Regularity
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$, and let $f \in \mathcal{R}[a, b]$ be an arbitrary Riemann integrable function. By virtue of the subinterval integrability established in Chapter 2, the restriction of $f$ to any subinterval $[a, x] \subseteq [a, b]$ remains Riemann integrable:
$$
\begin{gather}
f|_{[a, x]} \in \mathcal{R}[a, x] \qquad \forall x \in [a, b] \tag{2}
\end{gather}
$$
Consequently, the accumulation assignment in step 1 is unambiguously defined for every $x \in [a, b]$. Under the standard orientation convention, when the upper limit coincides with the base point, the integral vanishes identically:
$$
\begin{gather}
F(a) = \int_a^a f(t)\,dt = 0 \tag{3}
\end{gather}
$$

##### Boundedness and Lipschitz Bounds
Because $f$ is Riemann integrable on $[a, b]$, the Necessity of Boundedness established in Chapter 1 guarantees the existence of a finite real bound $M \in [0, \infty)$ such that:
$$
\begin{gather}
\sup_{t \in [a, b]} |f(t)| \le M < \infty \tag{4}
\end{gather}
$$
Now let $x_1, x_2 \in [a, b]$ be two arbitrary points with $x_1 < x_2$. By applying the interval additivity theorem from Chapter 2, the accumulation integral over $[a, x_2]$ decomposes into the sum of integrals over the adjacent subintervals:
$$
\begin{gather}
\int_a^{x_2} f(t)\,dt = \int_a^{x_1} f(t)\,dt + \int_{x_1}^{x_2} f(t)\,dt \tag{5}
\end{gather}
$$
Subtracting the first integral from both sides yields the spatial displacement identity:
$$
\begin{gather}
F(x_2) - F(x_1) = \int_{x_1}^{x_2} f(t)\,dt \tag{6}
\end{gather}
$$
Invoking the absolute value integral inequality and monotonicity established in Chapter 2, the magnitude of the displacement is bounded by the integral of the absolute value:
$$
\begin{gather}
|F(x_2) - F(x_1)| = \left| \int_{x_1}^{x_2} f(t)\,dt \right| \le \int_{x_1}^{x_2} |f(t)|\,dt \tag{7}
\end{gather}
$$
Substituting the uniform bound $|f(t)| \le M$ from step 4 into step 7 and integrating the constant over $[x_1, x_2]$ gives:
$$
\begin{gather}
|F(x_2) - F(x_1)| \le \int_{x_1}^{x_2} M\,dt = M(x_2 - x_1) \tag{8}
\end{gather}
$$
If $x_1 > x_2$, reversing the roles of indices and utilizing the orientation convention $\int_{x_1}^{x_2} f(t)\,dt = -\int_{x_2}^{x_1} f(t)\,dt$ yields an identical bound in terms of the absolute difference $|x_2 - x_1|$. Combining these results establishes the global Lipschitz estimate:
$$
\begin{gather}
|F(x_2) - F(x_1)| \le M |x_2 - x_1| \qquad \forall x_1, x_2 \in [a, b] \tag{9}
\end{gather}
$$

The metric estimate in step 9 proves that the accumulation function $F$ is Lipschitz continuous on $[a, b]$ with Lipschitz constant $L = M$. In the hierarchical continuum of real function regularity:
$$
\begin{gather}
C^\infty \subset \dots \subset C^1 \subset \mathrm{Lip} \subset \mathrm{AC} \subset \mathrm{UC} \subset C^0 \tag{10}
\end{gather}
$$
Lipschitz continuity represents an exceptionally strong condition. It immediately implies that $F$ is uniformly continuous on $[a, b]$, of bounded variation, and absolutely continuous. Thus, even if the generating integrand $f$ exhibits severe irregularities—such as a dense set of jump discontinuities, oscillatory discontinuities, or non-differentiability at every point—the accumulation mapping $F$ absorbs these variations, producing a uniformly continuous trajectory whose rate of growth is strictly bounded by $M$.

### Differentiability and the Recovery of Local Densities
While boundedness of $f$ guarantees that $F$ is continuous, the existence of classical derivatives for $F$ requires local structural information concerning the behavior of $f$.
```easy-tikz
title $\text{The Variable Upper Limit Accumulation Function and Local Rate of Growth}$
xlabel $t$
ylabel $y$
show x from -0.062 to 12.382 and y from -1.267 to 6.199
axes on the edges
size 12 x 8
plot f(x) = 1.2 + 0.45*x + 0.05*x^2 - 0.007*x^3, from x = 1.0 to 9.0, in teal, very thick
draw a line from (1.5, 0) to (1.5, 1.96), in orange, thick
draw a line from (5.5, 0) to (5.5, 4.02), in green, thick
draw a line from (6.5, 0) to (6.5, 4.31), in red, thick
draw a line from (1.5, 0) to (9.0, 0), in gray, thin
raw tool {"type":"points","name":"P1","points":"(1.5, 1.96);"}
raw tool {"type":"points","name":"P2","color":"purple","points":"(5.5, 4.02);"}
raw tool {"type":"points","name":"P3","color":"magenta","points":"(6.5, 4.31);"}
draw an arrow from (6.9, 2.6) to (6, 1.8)
write "$a$" at (1.5, 0.1) in orange, below
write "$x$" at (5.2, 0.7) in green, below
write "$x + h$" at (7.15, 0.65) in red, below
write "$y = f(t)$" at (9.1, 4.4) in teal, right
write "$h$" at (6.05, 0.05) in gray, below
write "$F(x) = \\int_a^x f(t) \\ dt$" at (3.5, 1.5) in green, center, small
write "$(1.5, 1.96)$" at (1.1, 2.5) in red, center
write "$(5.05, 4.02)$" at (4.85, 4.45) in purple, center
write "$(6.5, 4.31)$" at (6.75, 4.9) in magenta, center
write "$\\Delta F \\approx f(x)h$" at (7.6, 2.8), center, small
```

Let $x_0 \in [a, b]$ and consider a non-zero increment $h \in \mathbb{R} \setminus \{0\}$ such that $x_0 + h \in [a, b]$. The difference quotient of $F$ at $x_0$ is formulated via the displacement formula of step 6:
$$
\begin{gather}
\frac{F(x_0 + h) - F(x_0)}{h} = \frac{1}{h} \int_{x_0}^{x_0 + h} f(t)\,dt \tag{11}
\end{gather}
$$
To assess whether this difference quotient converges to $f(x_0)$ as $h \to 0$, one observes that the constant value $f(x_0)$ can be represented as an integral of an identical constant over the interval of length $h$:
$$
\begin{gather}
f(x_0) = \frac{1}{h} \int_{x_0}^{x_0 + h} f(x_0)\,dt \tag{12}
\end{gather}
$$
Subtracting step 12 from step 11 and employing the linearity of the definite integral yields the fundamental difference representation:
$$
\begin{gather}
\frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) = \frac{1}{h} \int_{x_0}^{x_0 + h} \big( f(t) - f(x_0) \big)\,dt \tag{13}
\end{gather}
$$

Now, assume that the integrand $f$ is continuous at the point $x_0$. By the analytical definition of continuity, for every designated tolerance $\epsilon > 0$, there exists a corresponding control radius $\delta > 0$ such that for all $t \in [a, b]$:
$$
\begin{gather}
|t - x_0| < \delta \implies |f(t) - f(x_0)| < \epsilon \tag{14}
\end{gather}
$$
Whenever the increment satisfies $0 < |h| < \delta$, every evaluation node $t$ in the closed interval between $x_0$ and $x_0 + h$ satisfies the proximity condition $|t - x_0| \le |h| < \delta$. Consequently, the local oscillation of the integrand is uniformly bounded by $\epsilon$. Taking the absolute value of step 13 and applying the integral modulus bound gives:
$$
\begin{gather}
\left| \frac{F(x_0 + h) - F(x_0)}{h} - f(x_0) \right| \le \frac{1}{|h|} \left| \int_{x_0}^{x_0 + h} |f(t) - f(x_0)|\,dt \right| \le \frac{1}{|h|} \cdot \epsilon |h| = \epsilon \tag{15}
\end{gather}
$$
Because the estimate in step 15 holds for all $h$ with $0 < |h| < \delta$, passing to the limit as $h \to 0$ demonstrates that the difference quotient converges precisely to $f(x_0)$:
$$
\begin{gather}
\lim_{h \to 0} \frac{F(x_0 + h) - F(x_0)}{h} = f(x_0) \tag{16}
\end{gather}
$$
If $x_0 = a$ or $x_0 = b$, the limit in step 16 is understood as the appropriate one-sided derivative $F'_+(a) = f(a)$ or $F'_-(b) = f(b)$: 
$$
\begin{gather}
\textbf{Theorem: Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral} \\[5mm]
\text{Let } f \in \mathcal{R}[a, b], \text{ and define the accumulation function } F: [a, b] \to \mathbb{R} \text{ by:} \\[2mm]
F(x) := \int_a^x f(t)\,dt \\[3.5mm]
\text{1. The function } F \text{ is Lipschitz continuous on } [a, b] \text{ with Lipschitz constant } M = \sup_{t \in [a, b]} |f(t)|: \\[2mm]
|F(x_2) - F(x_1)| \le M |x_2 - x_1| \qquad \forall x_1, x_2 \in [a, b] \\[3.5mm]
\text{2. If } f \text{ is continuous at a point } x_0 \in [a, b], \text{ then } F \text{ is differentiable at } x_0, \\[2mm]
\text{and its derivative satisfies:} \\[2mm]
F'(x_0) = f(x_0)
\end{gather}
$$
(see [[Proof of Lipschitz Continuity and Differentiability of the Variable Upper Limit Integral]])

### Existence of Primitives for Continuous Functions
The profound consequence of this theorem concerns the foundational problem of the existence of *primitives* (or *antiderivatives*).

##### Definition: Primitive (Antiderivative)
A function $\Phi: [a, b] \to \mathbb{R}$ is termed a primitive of a function $f: [a, b] \to \mathbb{R}$ on $[a, b]$ if $\Phi$ is continuous on $[a, b]$ and differentiable on $(a, b)$ with:
$$
\begin{gather}
\Phi'(x) = f(x) \qquad \forall x \in (a, b) \tag{17}
\end{gather}
$$
In elementary calculus, antiderivatives are frequently presented as syntactic pattern-matching exercises against a catalog of known derivative formulas. Such an approach provides zero guarantee that an arbitrary continuous function—such as $\exp(-x^2)$ or $\sin(x^2)$—possesses an antiderivative. 

The preceding theorem settles this existential question definitively and universally. If $f \in C[a, b]$, then $f$ is continuous at every single point $x \in [a, b]$. Therefore, the accumulation function $F(x) = \int_a^x f(t)\,dt$ is differentiable at every point of $[a, b]$ with $F'(x) = f(x)$. This establishes that *every continuous real function on a compact interval possesses a primitive*.

>[!danger]+ Intuition: The Smoothing Engine of Integration
>Consider the differential operator $D = \frac{d}{dx}$ and the integral operator $I = \int_a^x$. Differentiation is a local, subtractive operation: it examines the infinitesimal difference between adjacent values and divides by their vanishing distance. This division magnifies high-frequency noise and introduces sharp singularities; if a function has a corner, its derivative has a jump discontinuity; if it has a jump, its derivative fails to exist entirely. 
>
>Conversely, integration is a non-local, aggregative operation: it computes a weighted sum over a continuum of states. The microscopic irregularities and isolated jumps of $f$ are confined to sets of vanishing measure, diluting their disruptive impact across the interval. As a result, the accumulation function $F$ averages out roughness. When $f$ is continuous, the rate of accumulation at the moving boundary $x$ is dictated solely by the instantaneous height $f(x)$, causing the slope of the accumulation curve to trace the integrand with complete fidelity.

>[!info]+ Remark: Variable Lower Limits and the Extended Leibniz Integral Rule
>If the lower limit of integration also varies dynamically, the analytical behavior is readily deduced via interval additivity. Define $G(x) := \int_x^b f(t)\,dt$. By the orientation convention and interval additivity, $G(x) = \int_a^b f(t)\,dt - \int_a^x f(t)\,dt$. Differentiating with respect to $x$ at a continuity point of $f$ gives:
>$$ G'(x) = -\frac{d}{dx} \int_a^x f(t)\,dt = -f(x) $$
>More generally, if $\alpha, \beta: [c, d] \to [a, b]$ are differentiable functions and $f \in C[a, b]$, the composite accumulation mapping:
>$$ H(x) := \int_{\alpha(x)}^{\beta(x)} f(t)\,dt $$
>decomposes into $H(x) = \int_a^{\beta(x)} f(t)\,dt - \int_a^{\alpha(x)} f(t)\,dt$. Applying the chain rule of Module 5 yields the classical Leibniz integral rule:
>$$ H'(x) = f(\beta(x))\beta'(x) - f(\alpha(x))\alpha'(x) $$

>[!warning]+ Warning: Non-Differentiability at Jump Discontinuities
>The hypothesis that $f$ is continuous at $x_0$ cannot be discarded. If $f$ possesses a simple jump discontinuity at $x_0$, so that the one-sided limits $f(x_0^+)$ and $f(x_0^-)$ exist but are unequal, the accumulation function $F$ remains continuous, but it ceases to be differentiable at $x_0$. Instead, the left- and right-hand derivative limits yield distinct values:
>$$ F'_+(x_0) = \lim_{h \to 0^+} \frac{F(x_0 + h) - F(x_0)}{h} = f(x_0^+) $$
>$$ F'_-(x_0) = \lim_{h \to 0^-} \frac{F(x_0 + h) - F(x_0)}{h} = f(x_0^-) $$
>Because $F'_+(x_0) \neq F'_-(x_0)$, the accumulation graph forms a sharp corner at $x_0$, rendering $F$ non-differentiable at the jump location.

---
# The Fundamental Theorem of Calculus: The Newton-Leibniz Formula
The convergence of differential and integral calculus into a single unified analytical discipline represents one of the crowning achievements of classical real analysis. Historically, these two branches developed along separate trajectories motivated by distinct geometric problems: differential calculus emerged from the determination of tangents, instantaneous velocities, and local rates of change—whereas integral calculus arose from the determination of quadratures, curved areas, and total accumulations.

The Newton-Leibniz formula reveals that these two seemingly disparate operations are exact mutual inverses. Differentiation inverts integration at points of continuity, and integration reverses differentiation across connected domains.

### The Unification of Differential and Integral Calculus
To establish the exact mathematical connection, the structure of the family of primitives for a given function shall first be characterized. 

Let $f: [a, b] \to \mathbb{R}$ be a function possessing two distinct primitives, denoted by $\Phi_1$ and $\Phi_2$. By definition, both functions are continuous on $[a, b]$ and satisfy $\Phi_1'(x) = f(x)$ and $\Phi_2'(x) = f(x)$ for all $x \in (a, b)$. Define their difference function:
$$
\begin{gather}
\Delta(x) := \Phi_1(x) - \Phi_2(x) \tag{18}
\end{gather}
$$
The difference $\Delta$ is continuous on $[a, b]$ and differentiable on $(a, b)$, with derivative:
$$
\begin{gather}
\Delta'(x) = \Phi_1'(x) - \Phi_2'(x) = f(x) - f(x) = 0 \qquad \forall x \in (a, b) \tag{19}
\end{gather}
$$
Invoking the Lagrange Mean-Value Theorem from Module 5, for any $x \in (a, b]$, there exists some intermediate evaluation node $\xi \in (a, x)$ such that $\Delta(x) - \Delta(a) = \Delta'(\xi)(x - a) = 0 \cdot (x - a) = 0$. Consequently, $\Delta(x) = \Delta(a)$ for all $x \in [a, b]$. 

This deduction establishes that *any two primitives of a function on a connected interval differ by a constant*:
$$
\begin{gather}
\Phi_1(x) = \Phi_2(x) + C \qquad (C \in \mathbb{R}) \tag{20}
\end{gather}
$$

### The Classical Newton-Leibniz Formula
Now, suppose $f \in \mathcal{R}[a, b]$ possesses an arbitrary primitive $\Phi$ on $[a, b]$. Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ with $a = x_0 < x_1 < \dots < x_n = b$.

The net change of $\Phi$ across the global interval $[a, b]$ can be expressed as a telescoping sum of local increments over the constituent subintervals $[x_{i-1}, x_i]$:
$$
\begin{gather}
\Phi(b) - \Phi(a) = \sum_{i=1}^n \big( \Phi(x_i) - \Phi(x_{i-1}) \big) \tag{21}
\end{gather}
$$
Because $\Phi$ is continuous on $[x_{i-1}, x_i]$ and differentiable on $(x_{i-1}, x_i)$, the Lagrange Mean-Value Theorem guarantees the existence of an intermediate evaluation node $\xi_i \in (x_{i-1}, x_i)$ such that:
$$
\begin{gather}
\Phi(x_i) - \Phi(x_{i-1}) = \Phi'(\xi_i)(x_i - x_{i-1}) = f(\xi_i) \Delta x_i \tag{22}
\end{gather}
$$
Substituting step 22 into step 21 reveals that the net change of the primitive is identically equal to an exact Riemann sum of $f$ over the marked partition $(P, \xi)$:
$$
\begin{gather}
\Phi(b) - \Phi(a) = \sum_{i=1}^n f(\xi_i) \Delta x_i = \sigma(f; P, \xi) \tag{23}
\end{gather}
$$
Notice that the left-hand side of step 23 is a fixed constant independent of the choice of partition $P$ or intermediate nodes $\xi$. Because $f$ is Riemann integrable on $[a, b]$, taking the limit as the partition mesh $\lambda(P) \to 0$ forces the Riemann sum $\sigma(f; P, \xi)$ to converge to the definite integral $\int_a^b f(x)\,dx$. This establishes the Newton-Leibniz formula: 
$$
\begin{gather}
\textbf{Theorem: The Newton-Leibniz Formula} \\[5mm]
\text{Let } f \in \mathcal{R}[a, b], \text{ and suppose there exists a function } \Phi \in C[a, b] \text{ that is differentiable} \\[2mm]
\text{on } (a, b) \text{ with } \Phi'(x) = f(x) \text{ for all } x \in (a, b). \text{ Then:} \\[3.5mm]
\int_a^b f(x)\,dx = \Phi(b) - \Phi(a) =: \big[ \Phi(x) \big]_a^b
\end{gather}
$$
(see [[Proof of the Newton-Leibniz Formula]])

If the integrand $f$ is continuous on $[a, b]$, the existence of a primitive is guaranteed a priori by the accumulation mapping $F(x) = \int_a^x f(t)\,dt$. Because any other primitive $\Phi$ differs from $F$ by a constant $C$, evaluating $\Phi(a) = F(a) + C = 0 + C = C$ implies that $\Phi(x) = F(x) + \Phi(a)$. Evaluating at $x = b$ immediately yields:
$$
\begin{gather}
F(b) = \int_a^b f(t)\,dt = \Phi(b) - \Phi(a) \tag{24}
\end{gather}
$$
This demonstrates that the Newton-Leibniz formula holds unconditionally for all continuous functions.

### Piecewise Primitives and Generalized Integration
In practical applications, integrands often fail to be globally continuous, exhibiting jump discontinuities at a finite number of isolated nodes:
$$
\begin{gather}
E = \{c_1, c_2, \dots, c_k\} \subset (a, b) \tag{25}
\end{gather}
$$
Such functions remain Riemann integrable (as established in Chapter 1), but by Darboux's Theorem on derivatives (Module 5), a function with a jump discontinuity cannot possess a classical derivative everywhere, precluding the existence of a standard primitive on the entire interval $[a, b]$.

To evaluate the definite integral in such settings, the interval of integration is partitioned at the discontinuity nodes:
$$
\begin{gather}
[a, b] = [a, c_1] \cup [c_1, c_2] \cup \dots \cup [c_k, b] \tag{26}
\end{gather}
$$
On each open subinterval $(c_{j-1}, c_j)$, the integrand $f$ is continuous and possesses a localized primitive $\Phi_j$. By extending $\Phi_j$ continuously to the closed subinterval $[c_{j-1}, c_j]$, the Newton-Leibniz formula applies locally:
$$
\begin{gather}
\int_a^b f(x)\,dx = \sum_{j=1}^{k+1} \int_{c_{j-1}}^{c_j} f(x)\,dx = \sum_{j=1}^{k+1} \big( \Phi_j(c_j^-) - \Phi_j(c_{j-1}^+) \big) \tag{27}
\end{gather}
$$
A continuous function $\Phi \in C[a, b]$ that satisfies $\Phi'(x) = f(x)$ everywhere except on a finite set $E$ is termed a *generalized primitive*. For any generalized primitive, the accumulation of local boundary terms in step 27 telescopes globally, preserving the formula $\int_a^b f(x)\,dx = \Phi(b) - \Phi(a)$.

>[!danger]+ Intuition: The Microscopic-Macroscopic Telescoping Bridge
>The Newton-Leibniz formula can be viewed as the continuum realization of telescoping summation. In discrete algebra, summing the forward differences of a sequence collapses the entire interior:
>$$ \sum_{i=1}^n (a_i - a_{i-1}) = (a_1 - a_0) + (a_2 - a_1) + \dots + (a_n - a_{n-1}) = a_n - a_0 $$
>The derivative $\Phi'(x) = f(x)$ represents the local density of change at an infinitesimal scale: $d\Phi \approx f(x)dx$. Integrating this density across the continuum $[a, b]$ sums infinitely many infinitesimal increments $d\Phi$. Every internal boundary cancels out against its adjacent neighbor, leaving only the net boundary evaluation $\Phi(b) - \Phi(a)$. The macroscopic accumulation across the entire system depends solely on the boundary values of the primitive state potential.

>[!warning]+ Warning: Discontinuous Integrands Without Primitives vs. Primitives Without Integrability
>Two common misconceptions must be vigorously avoided:
>1. *Integrable functions need not possess primitives*: The simple signum function $f(x) = \operatorname{sgn}(x)$ on $[-1, 1]$ is Riemann integrable, but it possesses no primitive because no differentiable function can have a derivative with a jump discontinuity (Darboux's Theorem).
>2. *Primitives need not have Riemann integrable derivatives*: A function $\Phi$ can be differentiable everywhere on $[a, b]$, yet its derivative $\Phi'(x) = f(x)$ can be unbounded or have an uncountable set of discontinuities of positive measure (such as Volterra's function), rendering $f$ non-integrable in the classical Riemann sense. The Newton-Leibniz formula requires *both* that $\Phi$ is a primitive and that $f \in \mathcal{R}[a, b]$.

---
# Integral-Theoretic Foundation of the Logarithmic and Exponential Functions
```easy-tikz
title $\text{The Integral-Theoretic Definition and Geometric Dilation of the Natural Logarithm}$
xlabel $t$
ylabel $y$
show x from 0 to 8 and y from 0 to 5
axes on the edges
size 12 x 8
plot f(x) = 2.5/x, from x = 0.55 to 7.5, in teal, very thick
draw a line from (1.0, 0) to (1.0, 2.5), in orange, thick
draw a line from (2.718, 0) to (2.718, 0.92), in green, thick
draw a line from (5.5, 0) to (5.5, 0.45), in red, thick
draw a line from (0.5, 0) to (7.5, 0), in gray, thin
raw tool {"type":"points","name":"P1","color":"blue","points":"(1.0, 2.5);"}
raw tool {"type":"points","name":"P2","color":"orange","points":"(2.718, 0.92);"}
raw tool {"type":"points","name":"P3","color":"purple","points":"(5.5, 0.45);"}
write "$1$" at (1.0, -0.35) in orange, below
write "$e$" at (2.718, -0.35) in green, below
write "$x$" at (5.5, -0.35) in red, below
write "$y = \\frac{1}{t}$" at (3.65, 1.15) in teal, right
write "$\\ln e = 1$" at (1.85, 0.8) in green, center
write "$(1.0, 2.5)$" at (1.6, 2.5) in blue, center
write "$(e, 1)$" at (2.75, 1.35) in orange, center
write "$(5.5, 0.45)$" at (5.45, 0.85) in purple, center
```

### The Fundamental Algebraic Power Function
The analytical motivation for the natural logarithm arises from a fundamental algebraic gap in the catalog of power primitives. For any real exponent $p \in \mathbb{R} \setminus \{-1\}$, the primitive of the algebraic power function $f(t) = t^p$ is given by:
$$
\begin{gather}
\int t^p\,dt = \frac{t^{p+1}}{p+1} + C \tag{28}
\end{gather}
$$
When $p = -1$, the denominator $p + 1$ vanishes, causing the algebraic power rule to suffer an irrecoverable division-by-zero singularity. The function $f(t) = \frac{1}{t}$ is continuous on the open domain $(0, \infty)$, and by the existence theorem for primitives of continuous functions, it *must* possess an antiderivative. Yet, no finite combination of polynomials, rational functions, or algebraic radicals can serve as its primitive. 

### Formal Definition of the Natural Logarithm

##### Definition: The Natural Logarithm Function
The *natural logarithm* function $\ln: (0, \infty) \to \mathbb{R}$ is defined as the accumulation integral of the reciprocal density $t \mapsto \frac{1}{t}$ with base point 1:
$$
\begin{gather}
\ln x := \int_1^x \frac{dt}{t}, \qquad x \in (0, \infty) \tag{29}
\end{gather}
$$

Because the integrand $f(t) = \frac{1}{t}$ is strictly positive and continuous on $(0, \infty)$, the variable upper limit theorem guarantees that $\ln x$ is well-defined and differentiable for every $x > 0$. 

Evaluating step 29 at $x = 1$ yields the foundational anchor:
$$
\begin{gather}
\ln 1 = \int_1^1 \frac{dt}{t} = 0 \tag{30}
\end{gather}
$$
For $x > 1$, the integrand is strictly positive and the integration proceeds in the positive orientation, ensuring that $\ln x > 0$. For $0 < x < 1$, the orientation convention reverses the limits:
$$
\begin{gather}
\ln x = -\int_x^1 \frac{dt}{t} < 0 \qquad \forall x \in (0, 1) \tag{31}
\end{gather}
$$

**Differential and Convexity Properties:**
Applying the differentiability theorem for accumulation functions directly gives the first derivative:
$$
\begin{gather}
\frac{d}{dx} \ln x = \frac{1}{x} > 0 \qquad \forall x \in (0, \infty) \tag{32}
\end{gather}
$$
Because its first derivative is strictly positive everywhere on its domain, the natural logarithm is *strictly increasing* on $(0, \infty)$. Differentiating step 32 produces the second derivative:
$$
\begin{gather}
\frac{d^2}{dx^2} \ln x = -\frac{1}{x^2} < 0 \qquad \forall x \in (0, \infty) \tag{33}
\end{gather}
$$
Because its second derivative is strictly negative throughout $(0, \infty)$, the natural logarithm is *strictly concave* on its entire domain.

### Structural Homomorphism and Algebraic Identities
The defining characteristic of a logarithm is its ability to convert multiplication into addition. Within this integral framework, this algebraic identity is an immediate analytical consequence of domain additivity and linear scaling.

Let $x, y \in (0, \infty)$. By interval additivity, the integral over $[1, xy]$ decomposes into:
$$
\begin{gather}
\ln(xy) = \int_1^{xy} \frac{dt}{t} = \int_1^x \frac{dt}{t} + \int_x^{xy} \frac{dt}{t} = \ln x + \int_x^{xy} \frac{dt}{t} \tag{34}
\end{gather}
$$
To evaluate the remaining integral $\int_x^{xy} \frac{dt}{t}$, introduce the change of variable $t = xu$, where $u$ varies from $1$ to $y$. The differential scales as $dt = x\,du$. Substituting these expressions yields:
$$
\begin{gather}
\int_x^{xy} \frac{dt}{t} = \int_1^y \frac{x\,du}{xu} = \int_1^y \frac{du}{u} = \ln y \tag{35}
\end{gather}
$$
Substituting step 35 into step 34 establishes the fundamental algebraic homomorphism:
$$
\begin{gather}
\ln(xy) = \ln x + \ln y \qquad \forall x, y \in (0, \infty) \tag{36}
\end{gather}
$$

##### Inversion, Quotients, and Exponents:
Setting $y = \frac{1}{x}$ in step 36 and utilizing $\ln 1 = 0$ yields:
$$
\begin{gather}
\ln x + \ln\left(\frac{1}{x}\right) = \ln\left( x \cdot \frac{1}{x} \right) = \ln 1 = 0 \implies \ln\left(\frac{1}{x}\right) = -\ln x \tag{37}
\end{gather}
$$
For any quotient $x/y = x \cdot (1/y)$, combining steps 36 and 37 yields:
$$
\begin{gather}
\ln\left(\frac{x}{y}\right) = \ln x + \ln\left(\frac{1}{y}\right) = \ln x - \ln y \tag{38}
\end{gather}
$$
Furthermore, by mathematical induction on $n \in \mathbb{N}$, $\ln(x^n) = n \ln x$. For negative integers, $\ln(x^{-n}) = \ln(1/x^n) = -n \ln x$. For any rational exponent $r = p/q \in \mathbb{Q}$ with $q \in \mathbb{N}$, setting $u = x^{p/q}$ implies $u^q = x^p$, so that $q \ln u = p \ln x$, yielding $\ln(x^{p/q}) = \frac{p}{q} \ln x$. By continuity of the logarithm and density of $\mathbb{Q}$ in $\mathbb{R}$, this identity extends to all real exponents $r \in \mathbb{R}$:
$$
\begin{gather}
\ln(x^r) = r \ln x \qquad \forall x > 0, r \in \mathbb{R} \tag{39}
\end{gather}
$$

##### Asymptotic Limits and Surjectivity
To determine the global asymptotic limits of $\ln x$, observe that for $t \in [1, 2]$, $\frac{1}{t} \ge \frac{1}{2}$. By monotonicity of the integral:
$$
\begin{gather}
\ln 2 = \int_1^2 \frac{dt}{t} \ge \int_1^2 \frac{1}{2}\,dt = \frac{1}{2} > 0 \tag{40}
\end{gather}
$$
For any positive integer $n \in \mathbb{N}$, the power rule gives $\ln(2^n) = n \ln 2 \ge \frac{n}{2}$. Because $\frac{n}{2} \to \infty$ as $n \to \infty$, and because $\ln x$ is strictly increasing, it follows that:
$$
\begin{gather}
\lim_{x \to \infty} \ln x = \infty \tag{41}
\end{gather}
$$
Similarly, taking the limit as $x \to 0^+$ and utilizing step 37 gives:
$$
\begin{gather}
\lim_{x \to 0^+} \ln x = \lim_{u \to \infty} \ln\left(\frac{1}{u}\right) = -\lim_{u \to \infty} \ln u = -\infty \tag{42}
\end{gather}
$$
Because $\ln: (0, \infty) \to \mathbb{R}$ is continuous, strictly increasing, and unbounded in both directions, the Intermediate Value Theorem ensures that its range is all of $\mathbb{R}$. Thus, $\ln$ is a smooth, order-preserving diffeomorphism mapping the multiplicative group $((0, \infty), \cdot)$ onto the additive group $(\mathbb{R}, +)$: 
$$
\begin{gather}
\textbf{Theorem: Structural and Analytic Properties of the Natural Logarithm} \\[5mm]
\text{The natural logarithm function } \ln: (0, \infty) \to \mathbb{R}, \text{ defined by } \ln x := \int_1^x \frac{dt}{t}, \\[2mm]
\text{satisfies the following complete suite of analytic and algebraic properties:} \\[3.5mm]
\text{1. } \ln 1 = 0, \quad \ln'(x) = \frac{1}{x} > 0, \quad \ln''(x) = -\frac{1}{x^2} < 0 \quad (\text{strictly increasing and strictly concave}). \\[3.5mm]
\text{2. } \ln(xy) = \ln x + \ln y \quad \forall x, y \in (0, \infty) \quad (\text{homomorphism from } ((0, \infty), \cdot) \to (\mathbb{R}, +)). \\[3.5mm]
\text{3. } \ln\left(\frac{x}{y}\right) = \ln x - \ln y, \quad \ln(x^r) = r \ln x \quad \forall x, y > 0, r \in \mathbb{R}. \\[3.5mm]
\text{4. } \lim_{x \to \infty} \ln x = \infty, \quad \lim_{x \to 0^+} \ln x = -\infty, \quad \text{and the mapping } \ln: (0, \infty) \to \mathbb{R} \text{ is bijective.} \\[3.5mm]
\text{5. } \log_a x = \frac{\ln x}{\ln a} \quad \forall x \in (0, \infty), \; a \in (0, \infty) \setminus \{1\} \quad (\text{where } \exp := \ln^{-1}, \; a^x := \exp(x \ln a)).
\end{gather}
$$
(see [[Proof of the Structural and Analytic Properties of the Natural Logarithm]])

### Inversion and the Exponential Function
Because $\ln: (0, \infty) \to \mathbb{R}$ is strictly increasing and bijective, its inverse function exists globally, mapping the entire real line onto the strictly positive reals:
$$
\begin{gather}
\exp := \ln^{-1}: \mathbb{R} \to (0, \infty) \tag{43}
\end{gather}
$$
By definition of the inverse mapping:
$$
\begin{gather}
\exp(y) = x \iff \ln x = y \tag{44}
\end{gather}
$$
Evaluating at $y = 0$ gives $\exp(0) = 1$. The group homomorphism property of $\ln$ translates directly into the exponential addition law:
$$
\begin{gather}
\exp(u + v) = \exp(u)\exp(v) \qquad \forall u, v \in \mathbb{R} \tag{45}
\end{gather}
$$

##### Napier's Constant and Natural Exponentiation
Napier's constant, denoted by $e$, is defined analytically as the unique real number whose natural logarithm equals 1:
$$
\begin{gather}
e := \exp(1) \iff \int_1^e \frac{dt}{t} = 1 \tag{46}
\end{gather}
$$
For any real number $x \in \mathbb{R}$, defining $e^x := \exp(x)$ ensures that $\ln(e^x) = x \ln e = x \cdot 1 = x$. For an arbitrary base $a > 0$ and any exponent $x \in \mathbb{R}$, general real exponentiation is defined rigorously via:
$$
\begin{gather}
a^x := \exp(x \ln a) \tag{47}
\end{gather}
$$

**Differentiability of the Exponential Function:**
Because $\ln x$ is differentiable with non-vanishing derivative $\ln'(x) = \frac{1}{x} \ne 0$, the Inverse Function Theorem from Module 5 guarantees that $\exp(x)$ is differentiable on all of $\mathbb{R}$. Its derivative is given by:
$$
\begin{gather}
\exp'(x) = \frac{1}{\ln'(\exp(x))} = \frac{1}{\frac{1}{\exp(x)}} = \exp(x) \tag{48}
\end{gather}
$$
Thus, the exponential function reproduces itself under differentiation:
$$
\begin{gather}
\frac{d}{dx} e^x = e^x \tag{49}
\end{gather}
$$

### General Base and Common Logarithms
With the natural logarithm and general exponentiation established, the general logarithm to base $a$ (where $a > 0$ and $a \ne 1$) is defined as the inverse of the mapping $x \mapsto a^x$. 

Solving $a^y = x$ by taking the natural logarithm of both sides gives $\ln(a^y) = y \ln a = \ln x$, isolating $y$:
$$
\begin{gather}
\log_a x := \frac{\ln x}{\ln a}, \qquad x \in (0, \infty) \tag{50}
\end{gather}
$$
The derivative of the general logarithm follows immediately by linearity:
$$
\begin{gather}
\frac{d}{dx} \log_a x = \frac{1}{\ln a} \cdot \frac{d}{dx}\ln x = \frac{1}{x \ln a} \tag{51}
\end{gather}
$$
When the base is chosen as the decimal base $a = 10$, one obtains the *common logarithm*, denoted by $\log_{10} x$ or $\lg x$:
$$
\begin{gather}
\log_{10} x := \frac{\ln x}{\ln 10} \tag{52}
\end{gather}
$$
For any two permissible bases $a, b \in (0, \infty) \setminus \{1\}$, the change of base identity emerges directly from step 50:
$$
\begin{gather}
\log_a x = \frac{\log_b x}{\log_b a} \tag{53}
\end{gather}
$$

>[!danger]+ Intuition: Dilation Invariance of the Rectangular Hyperbola
>The structural homomorphism $\ln(xy) = \ln x + \ln y$ is rooted in the geometric symmetry of the rectangular hyperbola $y = 1/t$. Under a horizontal dilation $t \mapsto u = t/x$, the domain interval $[x, xy]$ of length $(y - 1)x$ is compressed by a factor of $x$ down to $[1, y]$ of length $y - 1$. Concurrently, the height of the curve $1/t = 1/(xu) = \frac{1}{x}(1/u)$ is scaled down by exactly the reciprocal factor $1/x$. 
>
>In the differential area element $dA = y(t)dt$, the dilation factor $x$ in the differential $dt = x\,du$ and the contraction factor $1/x$ in the height $y(t) = \frac{1}{x}\frac{1}{u}$ cancel out exactly:
>$$ dA = \frac{dt}{t} = \frac{x\,du}{xu} = \frac{du}{u} $$
>The area under the hyperbola is strictly invariant under coordinate dilation! Consequently, moving from $x$ to $xy$ accumulates precisely the same area as moving from $1$ to $y$.

>[!info]+ Remark: Historical Convergence of the Late-Transcendental Framework
>Historically, John Napier (1614) and Joost Bürgi invented logarithms for computational astronomy before the calculus of fluxions was discovered. Grégoire de Saint-Vincent (1647) discovered that the area under the hyperbola $y = 1/t$ satisfies the additive property of logarithms, and Alfonso Antonio de Sarasa (1649) recognized this connection explicitly. 
>
>The modern Soviet pedagogical paradigm reverses the historical path: rather than constructing real analysis to explain pre-existing computational devices, it proves that the hyperbola $y = 1/t$ is the unique analytical bridge bridging algebraic power functions and the exponential groups.

---
# Integration by Parts and Higher-Order Expansions

### The Definite Product Rule
The operation of differentiation obeys the Leibniz product rule:
$$
\begin{gather}
\frac{d}{dx}\big( u(x)v(x) \big) = u'(x)v(x) + u(x)v'(x) \tag{54}
\end{gather}
$$
When $u$ and $v$ belong to $C^1[a, b]$, both products $u'v$ and $uv'$ are continuous on $[a, b]$, and therefore belong to $\mathcal{R}[a, b]$. Integrating step 54 across the compact interval $[a, b]$ and applying the Newton-Leibniz formula to the left-hand side yields:
$$
\begin{gather}
\int_a^b \frac{d}{dx}\big( u(x)v(x) \big)\,dx = \big[ u(x)v(x) \big]_a^b = u(b)v(b) - u(a)v(a) \tag{55}
\end{gather}
$$
By vector space linearity, the integral of the sum on the right-hand side of step 54 separates into the sum of integrals:
$$
\begin{gather}
\int_a^b \frac{d}{dx}\big( u(x)v(x) \big)\,dx = \int_a^b u'(x)v(x)\,dx + \int_a^b u(x)v'(x)\,dx \tag{56}
\end{gather}
$$
Equating step 55 with step 56 and rearranging terms isolates the integral of $u(x)v'(x)$:
$$
\begin{gather}
\int_a^b u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^b - \int_a^b u'(x)v(x)\,dx \tag{57}
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Integration by Parts for Definite Integrals} \\[5mm]
\text{Let } u, v \in C^1[a, b]. \text{ Then } u v' \text{ and } u' v \text{ are Riemann integrable on } [a, b], \\[2mm]
\text{and the definite integral satisfies the identity:} \\[3.5mm]
\int_a^b u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^b - \int_a^b u'(x)v(x)\,dx
\end{gather}
$$
(see [[Proof of Integration by Parts for Definite Integrals]])

Integration by parts serves as an analytical transformation that transfers a differential operator from one functional factor onto another within an integral inner product. This operator-theoretic property, known as *formal adjointness*, forms the bedrock of distribution theory, weak derivatives, and functional analysis.

### Taylor's Theorem with Integral Remainder
In Module 5, Taylor's Theorem was derived using Cauchy's and Lagrange's Mean-Value Theorems, producing remainder terms evaluated at an unknown, non-constructive intermediate node $\xi \in (x_0, x)$. 

Integration by parts provides a vastly superior, exact analytical formulation: it expresses the Taylor remainder not as an existential bound, but as an explicit, closed-form definite integral.

Let $f \in C^{n+1}[a, b]$ and choose a fixed base expansion node $x_0 \in [a, b]$. For any target evaluation point $x \in [a, b]$, the Fundamental Theorem of Calculus expresses the total change of $f$ as:
$$
\begin{gather}
f(x) = f(x_0) + \int_{x_0}^x f'(t)\,dt \tag{58}
\end{gather}
$$
To evaluate the integral in step 58 via integration by parts, set:
$$
\begin{gather}
u(t) = f'(t) \implies u'(t) = f''(t) \tag{59}
\end{gather}
$$
For the differential factor $v'(t) = 1$, one is at liberty to select *any* primitive $v(t) = t + C$. The critical analytical insight is to select the constant $C = -x$, so that:
$$
\begin{gather}
v(t) = t - x = -(x - t) \tag{60}
\end{gather}
$$
This specific choice guarantees that $v(x) = 0$, completely annihilating the boundary evaluation at the upper limit $t = x$. Applying integration by parts to step 58 gives:
$$
\begin{gather}
\int_{x_0}^x f'(t)\,dt = \big[ f'(t)(t - x) \big]_{x_0}^x - \int_{x_0}^x f''(t)(t - x)\,dt \tag{61}
\end{gather}
$$
Evaluating the boundary bracket yields:
$$
\begin{gather}
\big[ f'(t)(t - x) \big]_{x_0}^x = f'(x)(0) - f'(x_0)(x_0 - x) = f'(x_0)(x - x_0) \tag{62}
\end{gather}
$$
Rewriting $-(t - x) = (x - t)$, step 61 becomes:
$$
\begin{gather}
\int_{x_0}^x f'(t)\,dt = f'(x_0)(x - x_0) + \int_{x_0}^x f''(t)(x - t)\,dt \tag{63}
\end{gather}
$$
Substituting step 63 back into step 58 yields the first-order Taylor expansion with integral remainder:
$$
\begin{gather}
f(x) = f(x_0) + f'(x_0)(x - x_0) + \int_{x_0}^x f''(t)(x - t)\,dt \tag{64}
\end{gather}
$$

Repeating this procedure by parts on the integral remainder, choosing at each stage $u(t) = f^{(k+1)}(t)$ and $v(t) = -\frac{(x - t)^{k+1}}{k+1}$, generates the general expansion by mathematical induction.
$$
\begin{gather}
\textbf{Theorem: Taylor's Formula with Integral Remainder} \\[5mm]
\text{Let } f \in C^{n+1}[a, b] \text{ and let } x_0 \in [a, b]. \text{ Then for every } x \in [a, b], \\[2mm]
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + R_n(x) \\[3.5mm]
\text{where the exact remainder term } R_n(x) \text{ is given by the definite integral:} \\[2mm]
R_n(x) = \frac{1}{n!} \int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt
\end{gather}
$$
(see [[Proof of Taylor's Formula with Integral Remainder]])

### Derivation of Classical Remainder Forms from the Integral Remainder
The integral remainder formula is the master representation from which all classical remainder formulas flow. By applying the Mean-Value Theorems for integrals established in Chapter 2, the classical Lagrange and Cauchy forms emerge as immediate corollaries.

Assume without loss of generality that $x > x_0$, so that the interval of integration is $[x_0, x]$.

##### Derivation of the Lagrange Remainder Form:
Consider the integral remainder:
$$
\begin{gather}
R_n(x) = \frac{1}{n!} \int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt \tag{65}
\end{gather}
$$
In the integrand of step 65, the factor $g(t) := (x - t)^n$ does not change sign on $[x_0, x]$; it satisfies $g(t) \ge 0$ for all $t \in [x_0, x]$. Furthermore, $f^{(n+1)}$ is continuous on $[x_0, x]$. 

Invoking the Generalized First Mean-Value Theorem for Integrals from Chapter 2, there exists an intermediate point $\xi \in [x_0, x]$ such that $f^{(n+1)}$ can be extracted outside the integral:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}(\xi) \int_{x_0}^x (x - t)^n\,dt \tag{66}
\end{gather}
$$
The remaining integral is elementary:
$$
\begin{gather}
\int_{x_0}^x (x - t)^n\,dt = \left[ -\frac{(x - t)^{n+1}}{n+1} \right]_{x_0}^x = 0 - \left( -\frac{(x - x_0)^{n+1}}{n+1} \right) = \frac{(x - x_0)^{n+1}}{n+1} \tag{67}
\end{gather}
$$
Substituting step 67 into step 66 and dividing by $n!$ yields the classical *Lagrange form of the remainder*:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x - x_0)^{n+1} \qquad (\xi \in [x_0, x]) \tag{68}
\end{gather}
$$

##### Derivation of the Cauchy Remainder Form
Alternatively, apply the standard First Mean-Value Theorem for Integrals (Chapter 2) directly to the entire continuous integrand $h(t) := f^{(n+1)}(t)(x - t)^n$ over $[x_0, x]$:
$$
\begin{gather}
\int_{x_0}^x f^{(n+1)}(t)(x - t)^n\,dt = f^{(n+1)}(\xi)(x - \xi)^n (x - x_0) \tag{69}
\end{gather}
$$
Dividing by $n!$ gives the classical *Cauchy form of the remainder*:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n (x - x_0) \qquad (\xi \in [x_0, x]) \tag{70}
\end{gather}
$$
If one expresses the intermediate node as $\xi = x_0 + \theta(x - x_0)$ with $\theta \in (0, 1)$, then $x - \xi = (1 - \theta)(x - x_0)$, converting step 70 into the standard parameterized form:
$$
\begin{gather}
R_n(x) = \frac{f^{(n+1)}\big( x_0 + \theta(x - x_0) \big)}{n!}(1 - \theta)^n (x - x_0)^{n+1} \tag{71}
\end{gather}
$$

>[!danger]+ Intuition: Integrating Against an Infinitesimal Leverage Arm
>The polynomial kernel $(x - t)^n$ within the integral remainder acts as an analytical weighting arm. As $t$ approaches the evaluation boundary $x$, the weight $(x - t)^n$ decays to zero. This decay suppresses the influence of the derivative $f^{(n+1)}$ near the target point $x$, while the factorial denominator $n!$ crushes the entire integral as the expansion order $n$ grows. The integral remainder captures the exact cumulative curvature of $f$ that escapes the linear approximations of the lower-order polynomial terms.

>[!info]+ Remark: Exactness vs. Existential Remainder Forms
>While the Lagrange and Cauchy remainder forms are computationally convenient for quick qualitative bounds, they suffer from a severe analytical defect: the intermediate coordinate $\xi$ depends on $n$, $x_0$, and $x$ in an implicit, non-constructive manner. In advanced quantitative modeling, numerical quadrature, and asymptotic analysis, bounding an unknown $\xi$ often yields loose or divergent estimates. The integral remainder $R_n(x)$, being an explicit definite integral, permits direct bounding via Cauchy-Schwarz, Hölder inequalities, or numerical integration.

---
# The Change of Variable Formula in the Definite Integral

### Analytical Transformation of Coordinates
The change of variable formula in integration corresponds to the chain rule of differential calculus. Let $\phi: [\alpha, \beta] \to \mathbb{R}$ be a continuously differentiable coordinate transformation mapping an abstract parameter interval $[\alpha, \beta]$ into the real line, and let $f$ be a continuous function defined on an interval containing the image $\phi([\alpha, \beta])$.

Suppose that $\phi(\alpha) = a$ and $\phi(\beta) = b$. Because $f$ is continuous on the compact image set $\phi([\alpha, \beta])$, it possesses a primitive $\Phi$ such that $\Phi'(x) = f(x)$. 

Consider the composite function:
$$
\begin{gather}
g(t) := (\Phi \circ \phi)(t) = \Phi(\phi(t)), \qquad t \in [\alpha, \beta] \tag{72}
\end{gather}
$$
Because $\phi$ is differentiable on $[\alpha, \beta]$ and $\Phi$ is differentiable on the image of $\phi$, the Chain Rule of Module 5 establishes that the composite function $g$ is differentiable on $[\alpha, \beta]$ with derivative:
$$
\begin{gather}
g'(t) = \Phi'(\phi(t))\phi'(t) = f(\phi(t))\phi'(t) \tag{73}
\end{gather}
$$
Because $\phi'$ is continuous on $[\alpha, \beta]$ and $f \circ \phi$ is continuous by the continuous composition theorem, the product $g'(t) = f(\phi(t))\phi'(t)$ is continuous, and hence Riemann integrable, on $[\alpha, \beta]$.

Now, apply the Newton-Leibniz formula to the derivative $g'$ over the interval $[\alpha, \beta]$:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = \int_\alpha^\beta g'(t)\,dt = g(\beta) - g(\alpha) \tag{74}
\end{gather}
$$
Evaluating the boundary terms of $g$ via step 72 yields:
$$
\begin{gather}
g(\beta) - g(\alpha) = \Phi(\phi(\beta)) - \Phi(\phi(\alpha)) = \Phi(b) - \Phi(a) \tag{75}
\end{gather}
$$
However, because $\Phi$ is a primitive for $f$ on $[a, b]$, the Newton-Leibniz formula on the original spatial interval asserts that:
$$
\begin{gather}
\Phi(b) - \Phi(a) = \int_a^b f(x)\,dx \tag{76}
\end{gather}
$$
Equating step 74 with step 76 proves the change of variable identity: 
$$
\begin{gather}
\textbf{Theorem: The Change of Variable Formula for Definite Integrals} \\[5mm]
\text{Let } \phi \in C^1[\alpha, \beta] \text{ with } \phi(\alpha) = a \text{ and } \phi(\beta) = b, \text{ and let } f \in C(J), \text{ where } J \subset \mathbb{R} \\[2mm]
\text{is a compact interval containing the image } \phi([\alpha, \beta]). \text{ Then:} \\[3.5mm]
\int_a^b f(x)\,dx = \int_{\phi(\alpha)}^{\phi(\beta)} f(x)\,dx = \int_\alpha^\beta f(\phi(t))\phi'(t)\,dt
\end{gather}
$$
(see [[Proof of the Change of Variable Formula for Definite Integrals]])

### Independence from Monotonicity and Orientation Cancellation
A critical analytical property of the definite integral change of variable formula—one that distinguishes it sharply from both indefinite integration and multivariable transformation theory—is that the coordinate mapping $\phi$ is not required to be monotonic. 

In multivariable calculus and geometric integration, transforming variables $\vec{x} = \phi(\vec{u})$ requires an invertible diffeomorphism, with the volume element transformed by the absolute determinant of the Jacobian: $d\vec{x} = |\det J_\phi|\,d\vec{u}$. 

In the univariate definite Riemann integral, no absolute value appears on the derivative factor $\phi'(t)$, and $\phi$ need not be injective. The mapping $\phi$ may oscillate wildly, turn around, and traverse subregions of $[a, b]$ multiple times.

To understand why monotonicity is completely unnecessary, consider a transformation $\phi: [\alpha, \beta] \to [a, b]$ that reverses direction at an interior critical point $c \in (\alpha, \beta)$. Suppose $\phi$ increases from $\phi(\alpha) = a$ to a local maximum $\phi(c) = d > b$, and subsequently decreases from $d$ to $\phi(\beta) = b$.

Splitting the parameter integral at $c$ via interval additivity gives:
$$
\begin{gather}
\int_\alpha^\beta f(\phi(t))\phi'(t)\,dt = \int_\alpha^c f(\phi(t))\phi'(t)\,dt + \int_c^\beta f(\phi(t))\phi'(t)\,dt \tag{77}
\end{gather}
$$
On $[\alpha, c]$, $\phi$ increases from $a$ to $d$. By the monotonic change of variables:
$$
\begin{gather}
\int_\alpha^c f(\phi(t))\phi'(t)\,dt = \int_a^d f(x)\,dx \tag{78}
\end{gather}
$$
On $[c, \beta]$, $\phi$ decreases from $d$ to $b$. During this traversal, the velocity is negative ($\phi'(t) \le 0$). Applying the transformation directly yields:
$$
\begin{gather}
\int_c^\beta f(\phi(t))\phi'(t)\,dt = \int_{\phi(c)}^{\phi(\beta)} f(x)\,dx = \int_d^b f(x)\,dx \tag{79}
\end{gather}
$$
Summing steps 78 and 79 and invoking the generalized orientation additivity established in Chapter 2 gives:
$$
\begin{gather}
\int_a^d f(x)\,dx + \int_d^b f(x)\,dx = \int_a^b f(x)\,dx \tag{80}
\end{gather}
$$
The overshoot area accumulated over the redundant subsegment $[b, d]$ during the forward journey is traversed in reverse during the backward journey. Because the orientation additivity rule enforces $\int_d^b f = -\int_b^d f$, the forward and backward contributions across $[b, d]$ cancel out identically:
$$
\begin{gather}
\int_b^d f(x)\,dx + \int_d^b f(x)\,dx = 0 \tag{81}
\end{gather}
$$
This algebraic cancellation ensures that the net accumulation across the parameter space $[\alpha, \beta]$ matches the spatial integral from $a$ to $b$ regardless of the number of intermediate oscillations or direction reversals executed by $\phi$.

>[!danger]+ Intuition: Topological Cancellation of Backtracking Folds
>Imagine a surveyor measuring the elevation change between two base camps $A$ and $B$. If the surveyor walks directly from $A$ to $B$, the net elevation gained is $h(B) - h(A)$. If instead the surveyor overshoots past $B$ up a peak $D$, turns around, and descends back to $B$, every foot of elevation gained between $B$ and $D$ is exactly counterbalanced by an identical foot of elevation lost descending from $D$ to $B$. The sign of the velocity $\phi'(t)$ automatically tracks the direction of travel, ensuring that the backtracking folds of the trajectory cancel out algebraically.

>[!warning]+ Warning: Domain Containment and Derivative Discontinuities
>The change of variable theorem requires that the integrand $f$ be continuous on a domain $J$ containing the *entire range* $\phi([\alpha, \beta])$, not merely the endpoint values $\phi(\alpha)$ and $\phi(\beta)$. If the intermediate trajectory $\phi(t)$ escapes the domain of continuity of $f$—for instance, if $\phi(t)$ encounters an essential singularity or a division-by-zero pole at an interior point $t_0 \in (\alpha, \beta)$—the formula breaks down completely, even if the endpoints $a = \phi(\alpha)$ and $b = \phi(\beta)$ reside entirely within the well-behaved domain.

---
# Pathological Gallery: Counterexamples and Converse Singularities

### Converse Failure of Continuity in Derivatives of Everywhere Differentiable Primitives
The differentiability theorem for accumulation functions established that if $f \in C[a, b]$, then $F(x) = \int_a^x f(t)\,dt$ is continuously differentiable with $F' = f$. However, the converse proposition—that every function possessing an antiderivative must have a continuous derivative—fails completely.

>[!example]- Example: Everywhere Differentiable Primitive with Oscillatory Discontinuous Derivative
>**Premise:**
>A function $F: [a, b] \to \mathbb{R}$ is differentiable at every point of $[a, b]$, ensuring that $f(x) := F'(x)$ possesses an exact primitive on $[a, b]$. One investigates whether $f$ is necessarily continuous.
>
>**Analytical Construction:**
>Consider the classic oscillatory function $F: [-1, 1] \to \mathbb{R}$ defined by:
>$$ F(x) := \begin{cases} x^2 \sin\left(\frac{1}{x}\right), & x \ne 0 \\[2mm] 0, & x = 0 \end{cases} \tag{82} $$
>
>**Step-by-Step Investigation:**
>1. For $x \ne 0$, computing the derivative via the standard product and chain rules yields:
>$$ F'(x) = 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) \tag{83} $$
>2. At the origin $x = 0$, evaluating the limit of the difference quotient directly:
>$$ F'(0) = \lim_{h \to 0} \frac{F(h) - F(0)}{h} = \lim_{h \to 0} \frac{h^2 \sin(1/h) - 0}{h} = \lim_{h \to 0} h \sin\left(\frac{1}{h}\right) \tag{84} $$
>Because $|\sin(1/h)| \le 1$, the squeeze theorem guarantees that $|h \sin(1/h)| \le |h| \to 0$, establishing that:
>$$ F'(0) = 0 \tag{85} $$
>Thus, $F$ is differentiable at *every* point of $[-1, 1]$.
>3. Examine the behavior of $F'(x)$ as $x \to 0$ in step 83. While the first term satisfies $\lim_{x \to 0} 2x \sin(1/x) = 0$, the second term $-\cos(1/x)$ oscillates relentlessly across $[-1, 1]$ along sequences $x_k = \frac{1}{k\pi}$. Consequently:
>$$ \lim_{x \to 0} F'(x) \quad \text{does not exist} \tag{86} $$
>Because $\lim_{x \to 0} F'(x) \ne F'(0)$, the derivative $F'$ has an essential oscillatory discontinuity at $x = 0$.
>4. Define $f(x) := F'(x)$. The function $f$ possesses an exact primitive $F$ everywhere on $[-1, 1]$, yet $f$ is discontinuous at the origin. Furthermore, the accumulation function of $f$:
>$$ G(x) := \int_0^x f(t)\,dt = F(x) - F(0) = x^2 \sin\left(\frac{1}{x}\right) \tag{87} $$
>is differentiable everywhere, but its derivative $G'(x) = f(x)$ is discontinuous at $x = 0$.

### Converse Failure of Riemann Integrability in Derivatives of Everywhere Differentiable Functions
A dangerous misconception holds that if a function $V$ is differentiable everywhere on $[0, 1]$ and its derivative $V'$ is bounded, then $V'$ must be Riemann integrable, allowing the Newton-Leibniz formula to apply. Vito Volterra (1881) disproved this assertion by constructing an explicit counterexample.

>[!example]- Example: Volterra's Everywhere Differentiable Function with Non-Integrable Derivative
>**Premise:**
>Let $V: [0, 1] \to \mathbb{R}$ be an everywhere differentiable function with uniformly bounded derivative $|V'(x)| \le 1$. One examines whether $V' \in \mathcal{R}[0, 1]$.
>
>**Analytical Construction:**
>Let $C \subset [0, 1]$ be a "fat" Cantor set—a closed, nowhere dense subset constructed by removing open middle intervals whose lengths decrease rapidly, such that the sum of the lengths of the removed intervals is strictly less than 1. The set $C$ possesses strictly positive Lebesgue measure $\mu(C) = 1 - \alpha > 0$ (for instance, $\mu(C) = 1/2$).
>
>The complement $[0, 1] \setminus C$ is a countable union of disjoint open intervals $I_k = (a_k, b_k)$. On each interval $I_k$, Volterra constructed a modified oscillatory function based on $x^2 \sin(1/x)$. Near the endpoints $a_k$ and $b_k$, the function transitions smoothly to a curve whose derivative oscillates rapidly between $-1$ and $+1$, while flattening out to 0 at the boundaries so that $V(x) = 0$ and $V'(x) = 0$ for all $x \in C$.
>
>**Step-by-Step Investigation:**
>1. Because $V'(x) = 0$ on $C$ and $|V'(x)| \le 1$ on each open interval $I_k$, the function $V: [0, 1] \to \mathbb{R}$ is differentiable at *every* point of $[0, 1]$, and its derivative is globally bounded:
>$$ \sup_{x \in [0, 1]} |V'(x)| \le 1 < \infty \tag{88} $$
>2. However, at every point $c \in C$, the derivative $V'$ oscillates between $-1$ and $+1$ in every neighborhood of $c$. Consequently, the set of discontinuities of $V'$ is precisely the entire fat Cantor set $C$:
>$$ D_{V'} = C \tag{89} $$
>3. Under the Riemann integrability criterion established in Chapter 1, a bounded function is Riemann integrable if and only if its set of discontinuities has measure zero (or negligible oscillation content). Because $\mu(C) > 0$, the upper Darboux integral and lower Darboux integral of $V'$ fail to coincide:
>$$ \underline{\int_0^1} V'(x)\,dx < \overline{\int_0^1} V'(x)\,dx \implies V' \notin \mathcal{R}[0, 1] \tag{90} $$
>4. Volterra's construction demonstrates that *a function can have an exact bounded primitive everywhere on an interval, yet fail to be Riemann integrable*. For such functions, the Riemann integral $\int_0^1 V'(x)\,dx$ is completely undefined, demonstrating that the hypothesis $f \in \mathcal{R}[a, b]$ in the Newton-Leibniz Theorem is strictly necessary and non-redundant.

### Converse Failure of Primitives for Discontinuous Functions
By Darboux's Theorem on derivatives (Module 5), the derivative of any differentiable function must satisfy the Intermediate Value Property. Consequently, functions exhibiting jump discontinuities cannot possess primitives.

>[!example]- Example: Simple Jump Discontinuities and Darboux's Intermediate Value Property
>**Premise:**
>Let $H: [-1, 1] \to \mathbb{R}$ be the Heaviside step function:
>$$ H(x) := \begin{cases} 0, & x < 0 \\[2mm] 1, & x \ge 0 \end{cases} \tag{91} $$
>Because $H$ is monotone and has only a single jump discontinuity at $x = 0$, Chapter 1 guarantees that $H \in \mathcal{R}[-1, 1]$. Its definite integral over $[-1, 1]$ is:
>$$ \int_{-1}^1 H(x)\,dx = \int_{-1}^0 0\,dx + \int_0^1 1\,dx = 0 + 1 = 1 \tag{92} $$
>One investigates whether there exists a classical primitive $\Phi \in C[-1, 1]$ such that $\Phi'(x) = H(x)$ for all $x \in [-1, 1]$.
>
>**Step-by-Step Investigation:**
>1. By Darboux's Theorem on derivatives (Module 5), if a function $\Phi$ is differentiable on an interval, its derivative $\Phi'$ must satisfy the Intermediate Value Property: if $\Phi'$ attains two values $y_1$ and $y_2$, it must attain every intermediate value between $y_1$ and $y_2$. 
>2. However, the image of $H$ is the disconnected discrete set $\{0, 1\}$. It skips every single value in the open interval $(0, 1)$. Therefore, $H$ *cannot be the derivative of any function on any open interval containing the origin*.
>3. If one attempts to define a primitive by integrating piecewise:
>$$ \Phi(x) = \begin{cases} C_1, & x < 0 \\[2mm] x + C_2, & x \ge 0 \end{cases} \tag{93} $$
>For $\Phi$ to be continuous at $x = 0$, one must choose $C_1 = C_2 = C$. Setting $C = 0$ gives $\Phi(x) = \max(0, x)$. While $\Phi$ is continuous everywhere and differentiable for $x \ne 0$, its one-sided derivatives at the origin are:
>$$ \Phi'_-(0) = 0 \ne 1 = \Phi'_+(0) \tag{94} $$
>Thus $\Phi'(0)$ does not exist, confirming that $H$ possesses no classical primitive on $[-1, 1]$.

### Singular Domain Escape in the Change of Variable Formula
The change of variable theorem requires that the integrand $f$ be continuous on a domain containing the *entire range* $\phi([\alpha, \beta])$. If the coordinate transformation escapes the domain of definition, formal calculation produces erroneous values.

>[!example]- Example: Exterior Branch Singularities in Coordinate Substitution
>**Premise:**
>Consider evaluating the proper definite integral of the rational function $f(x) = \frac{1}{(x - 2)^2 + 1}$ over the interval $[-1, 1]$:
>$$ I = \int_{-1}^1 \frac{dx}{(x - 2)^2 + 1} \tag{95} $$
>Because the denominator is strictly positive on all of $\mathbb{R}$, $f$ is smooth and positive, ensuring $I > 0$.
>
>**Step-by-Step Investigation:**
>1. Suppose an analyst attempts the formal substitution $x = \phi(t) = 2 + \tan t$. Choosing parameter endpoints such that $\phi(\alpha) = -1$ and $\phi(\beta) = 1$ requires:
>$$ 2 + \tan \alpha = -1 \implies \tan \alpha = -3 \implies \alpha = \arctan(-3) \approx -1.249 \tag{96} $$
>$$ 2 + \tan \beta = 1 \implies \tan \beta = -1 \implies \beta = -\frac{\pi}{4} \approx -0.785 \tag{97} $$
>Notice that $\alpha < \beta < 0$. On the parameter interval $[\alpha, \beta] \subset (-\pi/2, 0)$, $\tan t$ is smooth and finite. The differential is $dx = \sec^2 t\,dt$. Substituting into the integral:
>$$ \frac{dx}{(x - 2)^2 + 1} = \frac{\sec^2 t\,dt}{\tan^2 t + 1} = \frac{\sec^2 t\,dt}{\sec^2 t} = dt \tag{98} $$
>Integrating step 98 from $\alpha$ to $\beta$ gives:
>$$ \int_\alpha^\beta dt = \beta - \alpha = -\frac{\pi}{4} - \arctan(-3) = \arctan(3) - \frac{\pi}{4} > 0 \tag{99} $$
>This evaluation is valid because $\phi([\alpha, \beta])$ remains within the smooth domain of $\tan t$.
>2. Now, suppose the analyst carelessly selected a different branch of the tangent function, setting $\beta = \frac{3\pi}{4}$ (since $\tan(3\pi/4) = -1$). The parameter interval is now $[\alpha, \frac{3\pi}{4}]$. Within this interval lies the vertical asymptote $t = \frac{\pi}{2} \approx 1.571$. 
>3. As $t \to \frac{\pi}{2}$, $\phi(t) = 2 + \tan t \to \pm \infty$. The image $\phi([\alpha, 3\pi/4])$ escapes the compact domain and blows up to infinity, violating the hypothesis that $\phi \in C^1[\alpha, \beta]$. If one blindly computes the integral ignoring this singularity:
>$$ \int_\alpha^{3\pi/4} dt = \frac{3\pi}{4} - \arctan(-3) \approx 2.356 - (-1.249) = 3.605 \tag{100} $$
>The value in step 100 is completely erroneous. Blind coordinate transformations that escape the analytical domain of definition generate invalid results.

### Non-Differentiability of the Accumulation Function at Dense Removable Discontinuities
The Fundamental Theorem of Calculus guarantees that $F'(x_0) = f(x_0)$ when $f$ is continuous at $x_0$. If $x_0$ is a discontinuity of $f$, $F'(x_0)$ may exist without equaling $f(x_0)$.

>[!example]- Example: Decoupling of Derivative Value and Integrand Value on Dense Point Sets
>**Premise:**
>Let $f: [0, 1] \to \mathbb{R}$ be the modified Dirichlet function:
>$$ f(x) := \begin{cases} 1, & x = 1/n \text{ for some } n \in \mathbb{N} \\[2mm] 0, & \text{otherwise} \end{cases} \tag{101} $$
>The function $f$ is bounded and has only a countable set of discontinuities $\{1/n : n \in \mathbb{N}\} \cup \{0\}$ with a single limit point at 0. By the integrability criterion of Chapter 1, $f \in \mathcal{R}[0, 1]$. 
>
>**Step-by-Step Investigation:**
>1. Because $f(x) = 0$ almost everywhere, the upper and lower Darboux integrals vanish identically, yielding for the accumulation function:
>$$ F(x) = \int_0^x f(t)\,dt = 0 \qquad \forall x \in [0, 1] \tag{102} $$
>The accumulation function $F(x) \equiv 0$ is smooth everywhere, with $F'(x) \equiv 0$. 
>2. Inspect the relationship between $F'(x)$ and $f(x)$ at the evaluation nodes $x_n = 1/n$:
>$$ F'(1/n) = 0 \ne 1 = f(1/n) \tag{103} $$
>Even though $F$ is differentiable at $x_n = 1/n$, its derivative fails to recover the value of the integrand: $F'(1/n) \ne f(1/n)$. This confirms that the identity $F'(x_0) = f(x_0)$ holds if and only if $x_0$ is a point of continuity of $f$.

---
# Applications Involving the Integral and the Derivative

### Quantitative Finance: Continuous-Time Yield Curves, Forward Rates, and Leibniz Sensitivity

##### Premise
In continuous-time fixed income mathematics, the term structure of interest rates is characterized by an instantaneous forward rate curve $r: [0, T^*] \to \mathbb{R}$. The forward rate $r(t)$ represents the annualized interest rate contracted at inception for instantaneous borrowing at time $t$.

The fundamental price at time $t = 0$ of a zero-coupon bond maturing at horizon $T \in [0, T^*]$ delivering 1 unit of currency is defined by the exponential discount accumulation:
$$ P(0, T) := \exp\left( -\int_0^T r(t)\,dt \right) \tag{104} $$
The continuously compounded spot yield to maturity $y(T)$ satisfies $P(0, T) = \exp(-y(T)T)$, so that:
$$ y(T) = \frac{1}{T} \int_0^T r(t)\,dt \tag{105} $$
Consider an empirical forward rate curve modeled by:
$$ r(t) = r_\infty + (r_0 - r_\infty)e^{-\lambda t} + \gamma t e^{-\mu t} \tag{106} $$
where $r_0, r_\infty, \lambda, \mu, \gamma > 0$ are calibrated market parameters.

##### Problem Statement
1. Determine the exact closed-form formula for the zero-coupon bond price $P(0, T)$ and spot yield $y(T)$ using the Newton-Leibniz formula and integration by parts.
2. Compute the instantaneous sensitivity of the bond price with respect to maturity, $\frac{\partial P(0, T)}{\partial T}$, and demonstrate via the Fundamental Theorem of Calculus that:
$$ r(T) = -\frac{\partial}{\partial T} \ln P(0, T) \tag{107} $$
3. Derive the asymptotic yield behavior as $T \to \infty$ and $T \to 0^+$.

##### Step-by-Step Solution
1. Define the accumulation integral $I(T) := \int_0^T r(t)\,dt$. Substituting step 106:
$$ I(T) = \int_0^T r_\infty\,dt + (r_0 - r_\infty)\int_0^T e^{-\lambda t}\,dt + \gamma \int_0^T t e^{-\mu t}\,dt \tag{108} $$
The first two integrals are evaluated directly via the Newton-Leibniz formula:
$$ \int_0^T r_\infty\,dt = r_\infty T \tag{109} $$
$$ \int_0^T e^{-\lambda t}\,dt = \left[ -\frac{e^{-\lambda t}}{\lambda} \right]_0^T = \frac{1 - e^{-\lambda T}}{\lambda} \tag{110} $$
The third integral requires integration by parts. Set $u(t) = t \implies u'(t) = 1$, and $v'(t) = e^{-\mu t} \implies v(t) = -\frac{1}{\mu}e^{-\mu t}$:
$$ \int_0^T t e^{-\mu t}\,dt = \left[ -\frac{t}{\mu}e^{-\mu t} \right]_0^T - \int_0^T \left(-\frac{1}{\mu}e^{-\mu t}\right)dt = -\frac{T}{\mu}e^{-\mu T} + \frac{1}{\mu}\left[ -\frac{e^{-\mu t}}{\mu} \right]_0^T \tag{111} $$
Evaluating the limits:
$$ \int_0^T t e^{-\mu t}\,dt = \frac{1 - e^{-\mu T}}{\mu^2} - \frac{T}{\mu}e^{-\mu T} \tag{112} $$
Summing steps 109, 110, and 112 yields the total accumulation:
$$ I(T) = r_\infty T + (r_0 - r_\infty)\frac{1 - e^{-\lambda T}}{\lambda} + \gamma \left( \frac{1 - e^{-\mu T}}{\mu^2} - \frac{T}{\mu}e^{-\mu T} \right) \tag{113} $$
Consequently, the exact zero-coupon bond price is:
$$ P(0, T) = \exp\left( -r_\infty T - \frac{r_0 - r_\infty}{\lambda}(1 - e^{-\lambda T}) - \frac{\gamma}{\mu^2}(1 - e^{-\mu T}) + \frac{\gamma T}{\mu}e^{-\mu T} \right) \tag{114} $$
and the spot yield curve is:
$$ y(T) = \frac{I(T)}{T} = r_\infty + (r_0 - r_\infty)\frac{1 - e^{-\lambda T}}{\lambda T} + \frac{\gamma}{\mu^2 T}(1 - e^{-\mu T}) - \frac{\gamma}{\mu}e^{-\mu T} \tag{115} $$
2. Next, evaluate the derivative of $\ln P(0, T)$ with respect to $T$. Taking the natural logarithm of step 104:
$$ \ln P(0, T) = -\int_0^T r(t)\,dt \tag{116} $$
Because $r(t)$ is continuous on $[0, T^*]$, the variable upper limit theorem asserts that the integral is differentiable with respect to $T$ with derivative $r(T)$:
$$ \frac{\partial}{\partial T} \ln P(0, T) = -\frac{d}{dT} \int_0^T r(t)\,dt = -r(T) \tag{117} $$
Multiplying by $-1$ establishes step 107. By the chain rule:
$$ \frac{\partial P(0, T)}{\partial T} = P(0, T) \frac{\partial \ln P(0, T)}{\partial T} = -r(T) P(0, T) \tag{118} $$
3. Finally, analyze the asymptotic limits. As $T \to 0^+$, utilizing L'Hôpital's Rule or Taylor series $\frac{1 - e^{-\lambda T}}{T} \to \lambda$:
$$ \lim_{T \to 0^+} y(T) = r_\infty + (r_0 - r_\infty)\frac{\lambda}{\lambda} + \gamma\left( \frac{\mu}{\mu^2} - \frac{1}{\mu} \right) = r_\infty + r_0 - r_\infty = r_0 \tag{119} $$
As $T \to \infty$, the decaying exponentials vanish and terms divided by $T$ vanish:
$$ \lim_{T \to \infty} y(T) = r_\infty \tag{120} $$
This demonstrates that the spot yield curve smoothly interpolates between the instantaneous cash rate $r_0$ and the long-term macroeconomic forward anchor $r_\infty$.

### Theoretical Physics: Relativistic Work, Kinetic Energy, and Taylor Integral Remainder Convergence

##### Premise
In special relativity, the momentum of a particle of rest mass $m_0 > 0$ traveling at velocity $v \in (-c, c)$ (where $c$ is the speed of light) is given by:
$$ p(v) = \frac{m_0 v}{\sqrt{1 - v^2/c^2}} = m_0 c \frac{\beta}{\sqrt{1 - \beta^2}} \tag{121} $$
where $\beta := v/c \in (-1, 1)$. According to relativistic dynamics, the net work done by an external force accelerating the particle from rest ($v = 0$) to a terminal velocity $v$ defines its relativistic kinetic energy $E_k$:
$$ E_k = \int_0^x F\,ds = \int_0^t \frac{dp}{dt'} v(t')\,dt' \tag{122} $$

##### Problem Statement
1. Transform step 122 via the change of variable formula to express $E_k$ as an integral over the velocity domain $[0, v]$, and evaluate the integral using integration by parts to derive Einstein's kinetic energy formula:
$$ E_k = (\gamma - 1)m_0 c^2 \qquad \text{where } \gamma = \frac{1}{\sqrt{1 - v^2/c^2}} \tag{123} $$
2. Express the relativistic correction factor $f(\beta) = (1 - \beta^2)^{-1/2}$ as a second-order Taylor expansion about $\beta = 0$ with exact integral remainder.
3. Apply the Mean-Value Theorem for integrals to establish an explicit upper bound on the absolute error $|E_k - \frac{1}{2}m_0 v^2|$ in the non-relativistic regime $\beta \le 0.1$.

##### Step-by-Step Solution
1. By the chain rule, $dp = p'(v)dv$. Because $v(0) = 0$ and $v(t) = v$, the change of variable theorem transforms step 122 into:
$$ E_k = \int_0^v u\,dp(u) = \int_0^v u p'(u)\,du \tag{124} $$
Apply integration by parts to step 124, setting $u = u \implies du = du$, and $dv = p'(u)du \implies v = p(u)$:
$$ E_k = \big[ u p(u) \big]_0^v - \int_0^v p(u)\,du \tag{125} $$
The boundary term evaluates to:
$$ \big[ u p(u) \big]_0^v = v p(v) - 0 = \frac{m_0 v^2}{\sqrt{1 - v^2/c^2}} = \gamma m_0 v^2 \tag{126} $$
The remaining integral is:
$$ \int_0^v p(u)\,du = \int_0^v \frac{m_0 u}{\sqrt{1 - u^2/c^2}}\,du \tag{127} $$
Introduce the change of variable $w = 1 - u^2/c^2$, so that $dw = -\frac{2u}{c^2}du \implies u\,du = -\frac{c^2}{2}dw$. When $u = 0$, $w = 1$; when $u = v$, $w = 1 - v^2/c^2 = 1/\gamma^2$. Substituting:
$$ \int_0^v p(u)\,du = -\frac{m_0 c^2}{2} \int_1^{1/\gamma^2} w^{-1/2}\,dw = \frac{m_0 c^2}{2} \int_{1/\gamma^2}^1 w^{-1/2}\,dw \tag{128} $$
By the Newton-Leibniz formula:
$$ \frac{m_0 c^2}{2} \big[ 2 w^{1/2} \big]_{1/\gamma^2}^1 = m_0 c^2 \left( 1 - \frac{1}{\gamma} \right) = m_0 c^2 - \frac{m_0 c^2}{\gamma} \tag{129} $$
Substituting steps 126 and 129 into step 125 gives:
$$ E_k = \gamma m_0 v^2 - \left( m_0 c^2 - \frac{m_0 c^2}{\gamma} \right) = m_0 c^2 \left( \gamma \frac{v^2}{c^2} + \frac{1}{\gamma} - 1 \right) \tag{130} $$
Observe the algebraic identity:
$$ \gamma \frac{v^2}{c^2} + \frac{1}{\gamma} = \frac{1}{\sqrt{1 - v^2/c^2}} \frac{v^2}{c^2} + \sqrt{1 - \frac{v^2}{c^2}} = \frac{v^2/c^2 + (1 - v^2/c^2)}{\sqrt{1 - v^2/c^2}} = \frac{1}{\sqrt{1 - v^2/c^2}} = \gamma \tag{131} $$
Substituting step 131 into step 130 yields the celebrated relativistic kinetic energy formula:
$$ E_k = (\gamma - 1)m_0 c^2 \tag{132} $$
2. Next, analyze the Taylor expansion of $g(x) := (1 - x)^{-1/2}$ around $x = 0$, where $x = \beta^2$. The derivatives of $g$ are:
$$ g'(x) = \frac{1}{2}(1 - x)^{-3/2} \implies g'(0) = \frac{1}{2} \tag{133} $$
$$ g''(x) = \frac{3}{4}(1 - x)^{-5/2} \implies g''(0) = \frac{3}{4} \tag{134} $$
$$ g'''(x) = \frac{15}{8}(1 - x)^{-7/2} \tag{135} $$
The first-order Taylor expansion with integral remainder for $g(x)$ is:
$$ g(x) = g(0) + g'(0)x + R_1(x) = 1 + \frac{1}{2}x + \int_0^x g''(t)(x - t)\,dt \tag{136} $$
Setting $x = \beta^2 = v^2/c^2$ and substituting into $E_k = (g(\beta^2) - 1)m_0 c^2$:
$$ E_k = m_0 c^2 \left( \frac{1}{2}\beta^2 + R_1(\beta^2) \right) = \frac{1}{2}m_0 v^2 + m_0 c^2 R_1(\beta^2) \tag{137} $$
3. The difference $|E_k - \frac{1}{2}m_0 v^2| = m_0 c^2 R_1(\beta^2)$ is governed by the integral remainder:
$$ R_1(\beta^2) = \frac{3}{4} \int_0^{\beta^2} (1 - t)^{-5/2}(\beta^2 - t)\,dt \tag{138} $$
Because $(1 - t)^{-5/2}$ is strictly increasing for $t \in [0, \beta^2]$, its maximum is achieved at the upper endpoint $t = \beta^2$:
$$ R_1(\beta^2) \le \frac{3}{4}(1 - \beta^2)^{-5/2} \int_0^{\beta^2} (\beta^2 - t)\,dt = \frac{3}{8}\frac{\beta^4}{(1 - \beta^2)^{5/2}} \tag{139} $$
For $\beta \le 0.1$, $\beta^2 \le 0.01$, and $1 - \beta^2 \ge 0.99$. Therefore:
$$ R_1(0.01) \le \frac{3}{8} \frac{10^{-4}}{(0.99)^{5/2}} \approx \frac{3}{8} \frac{10^{-4}}{0.975} \approx 3.845 \times 10^{-5} \tag{140} $$
Multiplying by $m_0 c^2$ reveals that the relative error of the Newtonian kinetic energy approximation $\frac{1}{2}m_0 v^2$ at $10\%$ the speed of light is strictly bounded by:
$$ \frac{|E_k - \frac{1}{2}m_0 v^2|}{\frac{1}{2}m_0 v^2} = \frac{m_0 c^2 R_1(\beta^2)}{\frac{1}{2}m_0 c^2 \beta^2} = \frac{2 R_1(\beta^2)}{\beta^2} \le \frac{3}{4}\frac{\beta^2}{(1 - \beta^2)^{5/2}} \le \frac{3}{4} \frac{0.01}{0.975} \approx 0.0077 \quad (0.77\%) \tag{141} $$

### Physical Chemistry: Non-Ideal Gas Enthalpy, Entropy Transitions, and Hyperbolic State Integrals

##### Premise
In chemical thermodynamics, the state functions enthalpy $H(T, P)$ and entropy $S(T, P)$ govern the equilibrium dynamics of non-ideal gases. For a gas undergoing a temperature transition from $T_1$ to $T_2$ at constant pressure $P_0$, the fundamental thermodynamic relation defines the net entropy change by the integral:
$$ \Delta S = \int_{T_1}^{T_2} \frac{C_p(T)}{T}\,dt \tag{142} $$
where $C_p(T)$ is the isobaric heat capacity. For non-ideal polyatomic gases over wide thermal ranges, empirical quantum vibrations require heat capacity modeling via the Shomate polynomial:
$$ C_p(T) = A + B T + C T^2 + D T^{-2} \tag{143} $$
where $A, B, C, D > 0$ are substance-specific constants.

##### Problem Statement
1. Derive the closed-form expression for $\Delta S$ by integrating the reciprocal thermal density, demonstrating explicit reliance upon the natural logarithm $\ln(T_2/T_1)$.
2. For an isothermal expansion from volume $V_1$ to $V_2$ at temperature $T_0$, the entropy change of a van der Waals gas satisfying:
$$ \left( P + \frac{a}{V^2} \right)(V - b) = R T_0 \tag{144} $$
is given by the Maxwell relation integral $\Delta S_T = \int_{V_1}^{V_2} \left(\frac{\partial P}{\partial T}\right)_V dV$. Evaluate this integral analytically.
3. Prove that the entropy of expansion of a van der Waals gas exceeds that of an ideal gas across identical volumetric boundaries.

##### Step-by-Step Solution
1. Substitute step 143 into step 142:
$$ \Delta S = \int_{T_1}^{T_2} \left( \frac{A}{T} + B + C T + \frac{D}{T^3} \right) dT \tag{145} $$
Decompose step 145 via vector space linearity:
$$ \Delta S = A \int_{T_1}^{T_2} \frac{dT}{T} + B \int_{T_1}^{T_2} dT + C \int_{T_1}^{T_2} T\,dT + D \int_{T_1}^{T_2} T^{-3}\,dT \tag{146} $$
By definition of the natural logarithm and its quotient property:
$$ \int_{T_1}^{T_2} \frac{dT}{T} = \ln T_2 - \ln T_1 = \ln\left(\frac{T_2}{T_1}\right) \tag{147} $$
Evaluating the remaining algebraic integrals via the Newton-Leibniz formula:
$$ \int_{T_1}^{T_2} dT = T_2 - T_1 \tag{148} $$
$$ \int_{T_1}^{T_2} T\,dT = \frac{1}{2}(T_2^2 - T_1^2) \tag{149} $$
$$ \int_{T_1}^{T_2} T^{-3}\,dt = \left[ -\frac{1}{2T^2} \right]_{T_1}^{T_2} = \frac{1}{2}\left( \frac{1}{T_1^2} - \frac{1}{T_2^2} \right) = \frac{T_2^2 - T_1^2}{2 T_1^2 T_2^2} \tag{150} $$
Summing the four components yields:
$$ \Delta S = A \ln\left(\frac{T_2}{T_1}\right) + B(T_2 - T_1) + \frac{C}{2}(T_2^2 - T_1^2) + \frac{D(T_2^2 - T_1^2)}{2 T_1^2 T_2^2} \tag{151} $$
2. Next, isolate pressure $P$ from the van der Waals equation of state in step 144:
$$ P(T, V) = \frac{R T}{V - b} - \frac{a}{V^2} \tag{152} $$
Differentiating partially with respect to $T$ holding volume $V$ fixed:
$$ \left( \frac{\partial P}{\partial T} \right)_V = \frac{R}{V - b} \tag{153} $$
Substituting step 153 into the isothermal entropy integral yields:
$$ \Delta S_T = \int_{V_1}^{V_2} \frac{R}{V - b}\,dV \tag{154} $$
Perform the change of variable $u = V - b$, so that $du = dV$, with parameter boundaries $u_1 = V_1 - b$ and $u_2 = V_2 - b$:
$$ \Delta S_T = R \int_{V_1 - b}^{V_2 - b} \frac{du}{u} = R \ln\left( \frac{V_2 - b}{V_1 - b} \right) \tag{155} $$
3. Finally, compare step 155 with the entropy of an ideal gas ($b = 0$), where $\Delta S_T^{\text{ideal}} = R \ln(V_2/V_1)$. Consider the quotient:
$$ Q := \frac{V_2 - b}{V_1 - b} \tag{156} $$
For an expansion, $V_2 > V_1 > b > 0$. Subtracting the ideal ratio yields:
$$ \frac{V_2 - b}{V_1 - b} - \frac{V_2}{V_1} = \frac{V_1(V_2 - b) - V_2(V_1 - b)}{V_1(V_1 - b)} = \frac{b(V_2 - V_1)}{V_1(V_1 - b)} > 0 \tag{157} $$
Because the natural logarithm is strictly increasing (as established in Theorem 3), step 157 implies:
$$ \ln\left( \frac{V_2 - b}{V_1 - b} \right) > \ln\left( \frac{V_2}{V_1} \right) \implies \Delta S_T^{\text{vdW}} > \Delta S_T^{\text{ideal}} \tag{158} $$
Physically, the excluded volume $b$ restricts the accessible spatial microstates; expanding a van der Waals gas releases a larger proportion of previously crowded configurational volume, generating a strictly larger entropy surge.

### Systems Biology: Two-Compartment Pharmacokinetics, Intravenous Accumulation, and Total Clearance

##### Premise
In mathematical pharmacokinetics, the physiological distribution of an intravenously administered drug is modeled across a two-compartment architecture: a central intravascular compartment (blood plasma) and a peripheral tissue compartment. 

When a drug is infused intravenously at a variable input rate $k_{\text{in}}(t)$ over a dosing window $[0, T]$, the plasma drug concentration $C_p(t)$ satisfies the coupled differential balance:
$$ C_p(t) = \int_0^t k_{\text{in}}(s) \left( A e^{-\alpha (t - s)} + B e^{-\beta (t - s)} \right) ds \tag{159} $$
where $\alpha > \beta > 0$ represent the distribution and elimination rate constants, and $A, B > 0$ are fractional pharmacokinetic disposition constants.

The *Area Under the Curve* (AUC), defined as the definite integral of plasma concentration:
$$ \mathrm{AUC}_0^T := \int_0^T C_p(t)\,dt \tag{160} $$
governs total systemic drug exposure, and total systemic drug clearance is defined by $\mathrm{CL} = \frac{\text{Total Dose}}{\mathrm{AUC}_0^\infty}$.

##### Problem Statement
1. Consider a zero-order constant infusion of rate $k_{\text{in}}(t) = K_0$ sustained over $[0, T]$. Derive the exact closed-form expression for the plasma concentration profile $C_p(t)$ for $t \in [0, T]$ using the Newton-Leibniz formula.
2. Evaluate the total systemic accumulation $\mathrm{AUC}_0^T = \int_0^T C_p(t)\,dt$ by applying the Newton-Leibniz formula.
3. Calculate the terminal clearance $\mathrm{CL}$ as $T \to \infty$.

##### Step-by-Step Solution
1. For constant infusion $k_{\text{in}}(s) = K_0$, step 159 becomes:
$$ C_p(t) = K_0 A \int_0^t e^{-\alpha (t - s)}\,ds + K_0 B \int_0^t e^{-\beta (t - s)}\,ds \tag{161} $$
Introduce the change of variable $u = t - s \implies du = -ds$. When $s = 0$, $u = t$; when $s = t$, $u = 0$. The integral transforms to:
$$ \int_0^t e^{-\alpha (t - s)}\,ds = -\int_t^0 e^{-\alpha u}\,du = \int_0^t e^{-\alpha u}\,du = \left[ -\frac{e^{-\alpha u}}{\alpha} \right]_0^t = \frac{1 - e^{-\alpha t}}{\alpha} \tag{162} $$
Applying an identical evaluation to the second term gives the closed-form concentration:
$$ C_p(t) = K_0 \left( \frac{A}{\alpha}(1 - e^{-\alpha t}) + \frac{B}{\beta}(1 - e^{-\beta t}) \right) \tag{163} $$
2. To determine $\mathrm{AUC}_0^T$, integrate $C_p(t)$ from 0 to $T$:
$$ \mathrm{AUC}_0^T = \int_0^T C_p(t)\,dt = K_0 \int_0^T \left( \frac{A}{\alpha}(1 - e^{-\alpha t}) + \frac{B}{\beta}(1 - e^{-\beta t}) \right) dt \tag{164} $$
By vector space linearity:
$$ \mathrm{AUC}_0^T = K_0 \frac{A}{\alpha} \int_0^T (1 - e^{-\alpha t})\,dt + K_0 \frac{B}{\beta} \int_0^T (1 - e^{-\beta t})\,dt \tag{165} $$
Evaluating the constituent integral via Newton-Leibniz:
$$ \int_0^T (1 - e^{-\alpha t})\,dt = \left[ t + \frac{e^{-\alpha t}}{\alpha} \right]_0^T = T + \frac{e^{-\alpha T} - 1}{\alpha} = T - \frac{1 - e^{-\alpha T}}{\alpha} \tag{166} $$
Substituting step 166 into step 165 yields the exact accumulation formula:
$$ \mathrm{AUC}_0^T = K_0 \left[ \frac{A}{\alpha}\left( T - \frac{1 - e^{-\alpha T}}{\alpha} \right) + \frac{B}{\beta}\left( T - \frac{1 - e^{-\beta T}}{\beta} \right) \right] \tag{167} $$
3. For an instantaneous bolus dose $D_0$ administered at $t = 0$, the concentration profile simplifies to $C_{\text{bolus}}(t) = D_0(A e^{-\alpha t} + B e^{-\beta t})$. The infinite horizon exposure is:
$$ \mathrm{AUC}_0^\infty = D_0 \int_0^\infty (A e^{-\alpha t} + B e^{-\beta t})\,dt = D_0 \left( \frac{A}{\alpha} + \frac{B}{\beta} \right) \tag{168} $$
Consequently, systemic clearance is given by:
$$ \mathrm{CL} = \frac{D_0}{\mathrm{AUC}_0^\infty} = \frac{1}{\frac{A}{\alpha} + \frac{B}{\beta}} = \frac{\alpha \beta}{A \beta + B \alpha} \tag{169} $$
This establishes that total drug clearance is governed entirely by the harmonic coupling of the micro-rate elimination constants.

### Aerospace Engineering: Non-Isothermal Atmospheric Barometric Formula and Aerodynamic Stagnation

##### Premise
In atmospheric flight dynamics, predicting the stagnation pressure on the leading edge of a hypersonic aircraft requires determining the ambient atmospheric pressure profile $P(z)$ as a function of geometric altitude $z$. 

The hydrostatic equilibrium of a vertical atmospheric column satisfies the differential relation:
$$ \frac{dP}{dz} = -\rho(z) g \tag{170} $$
where $g$ is the gravitational acceleration and $\rho(z)$ is the atmospheric air density. Assuming air behaves as an ideal gas with molar mass $M$ and universal gas constant $R$, the equation of state gives $\rho(z) = \frac{P(z) M}{R T(z)}$. Substituting into step 170 yields the separable differential equation:
$$ \frac{1}{P}\frac{dP}{dz} = -\frac{g M}{R T(z)} \tag{171} $$

##### Problem Statement
1. Integrate step 171 across an altitude window $[0, z]$ using the Fundamental Theorem of Calculus to derive the general non-isothermal barometric pressure equation in terms of the natural logarithm and accumulation mapping.
2. In the troposphere ($z \in [0, z_t]$ with $z_t \approx 11\,\text{km}$), the temperature profile exhibits a linear lapse rate $T(z) = T_0 - L z$, where $T_0$ is sea-level temperature and $L = -\frac{dT}{dz} > 0$. Evaluate the pressure profile $P(z)$ analytically via the change of variable formula.
3. For an aircraft flying at Mach number $\mathrm{Ma}$ at altitude $z$, the compressible aerodynamic stagnation pressure is $P_{\text{stag}}(z) = P(z) \left( 1 + \frac{\gamma - 1}{2}\mathrm{Ma}^2 \right)^{\frac{\gamma}{\gamma - 1}}$. Compute the stagnation pressure at $z = 5000\,\text{m}$ for $\mathrm{Ma} = 0.8$, given $T_0 = 288.15\,\text{K}$, $L = 0.0065\,\text{K/m}$, $P_0 = 101325\,\text{Pa}$, $g = 9.80665\,\text{m/s}^2$, $M = 0.0289644\,\text{kg/mol}$, $R = 8.31446\,\text{J/(mol}\cdot\text{K)}$, and $\gamma = 1.4$.

##### Step-by-Step Solution
1. Integrate both sides of step 171 with respect to altitude from sea level $z = 0$ to altitude $z$:
$$ \int_0^z \frac{1}{P(h)} \frac{dP}{dh}\,dh = -\frac{g M}{R} \int_0^z \frac{dh}{T(h)} \tag{172} $$
By the change of variable formula on the left-hand side, setting $P = P(h) \implies dP = P'(h)dh$:
$$ \int_0^z \frac{1}{P(h)} \frac{dP}{dh}\,dh = \int_{P_0}^{P(z)} \frac{dP}{P} = \ln P(z) - \ln P_0 = \ln\left( \frac{P(z)}{P_0} \right) \tag{173} $$
Equating step 173 with step 172 and exponentiating yields the general barometric formula:
$$ P(z) = P_0 \exp\left( -\frac{g M}{R} \int_0^z \frac{dh}{T(h)} \right) \tag{174} $$
2. Now, substitute the linear tropospheric lapse profile $T(h) = T_0 - L h$ into the accumulation integral:
$$ I_T(z) := \int_0^z \frac{dh}{T_0 - L h} \tag{175} $$
Introduce the change of variable $u = T_0 - L h \implies du = -L\,dh \implies dh = -\frac{1}{L}du$. The boundaries transform from $h = 0 \to u = T_0$ and $h = z \to u = T_0 - L z$. Substituting:
$$ I_T(z) = -\frac{1}{L} \int_{T_0}^{T_0 - L z} \frac{du}{u} = \frac{1}{L} \int_{T_0 - L z}^{T_0} \frac{du}{u} = \frac{1}{L} \left[ \ln T_0 - \ln(T_0 - L z) \right] \tag{176} $$
Applying the quotient property of logarithms:
$$ I_T(z) = -\frac{1}{L} \ln\left( \frac{T_0 - L z}{T_0} \right) = -\frac{1}{L} \ln\left( 1 - \frac{L z}{T_0} \right) \tag{177} $$
Substitute step 177 into the exponential of step 174:
$$ P(z) = P_0 \exp\left( -\frac{g M}{R} \left( -\frac{1}{L} \ln\left( 1 - \frac{L z}{T_0} \right) \right) \right) = P_0 \exp\left( \frac{g M}{R L} \ln\left( 1 - \frac{L z}{T_0} \right) \right) \tag{178} $$
Utilizing the power property of the natural logarithm $\exp(k \ln w) = w^k$:
$$ P(z) = P_0 \left( 1 - \frac{L z}{T_0} \right)^{\frac{g M}{R L}} \tag{179} $$
3. Finally, substitute the specified empirical flight parameters into step 179 at altitude $z = 5000\,\text{m}$:
Compute the dimensionless lapse exponent:
$$ \alpha := \frac{g M}{R L} = \frac{(9.80665)(0.0289644)}{(8.31446)(0.0065)} = \frac{0.284044}{0.054044} \approx 5.2558 \tag{180} $$
Compute the temperature ratio at $z = 5000\,\text{m}$:
$$ T(5000) = 288.15 - (0.0065)(5000) = 288.15 - 32.5 = 255.65\,\text{K} \tag{181} $$
$$ 1 - \frac{L z}{T_0} = \frac{255.65}{288.15} \approx 0.88721 \tag{182} $$
Evaluating ambient pressure:
$$ P(5000) = 101325 \cdot (0.88721)^{5.2558} \approx 101325 \cdot 0.53341 \approx 54048\,\text{Pa} \tag{183} $$
Compute the compressible stagnation pressure multiplier for $\gamma = 1.4$ and $\mathrm{Ma} = 0.8$:
$$ \frac{\gamma - 1}{2}\mathrm{Ma}^2 = \frac{0.4}{2}(0.64) = 0.2 \cdot 0.64 = 0.128 \tag{184} $$
$$ \frac{\gamma}{\gamma - 1} = \frac{1.4}{0.4} = 3.5 \tag{185} $$
$$ \left( 1 + 0.128 \right)^{3.5} = (1.128)^{3.5} \approx 1.5243 \tag{186} $$
Multiplying ambient pressure by the stagnation factor:
$$ P_{\text{stag}}(5000) = (54048\,\text{Pa})(1.5243) \approx 82385\,\text{Pa} \approx 82.39\,\text{kPa} \tag{187} $$
This calculation proves that high-altitude aerodynamic forces can be rigorously derived from first-principles real analysis via coordinate transformation of the hydrostatic equilibrium integral.
