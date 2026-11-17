---
dg-publish: true
---
# Geometric and Physical Foundations of the Integral
The elementary methods of differential calculus established in [[Chapter 1 - Differentiable Functions|Module 5]] formalized the analysis of localized and infinitesimal change. Through the differential and the derivative, non-linear mappings are replaced locally by affine linear operators, enabling the precise determination of instantaneous velocities, tangent spaces, and small-signal perturbations. Yet differential analysis represents only one half of the foundational architecture of classical real analysis. While differentiation deconstructs a function into localized rates of change, a dual operational problem demands resolution: the accumulation of distributed quantities. 

### The Problem of Quadrature: Curvilinear Trapezoids
The classical geometrical challenge that motivated the creation of the *definite integral* is the problem of *quadrature*, which is the exact determination of the planar area enclosed by a geometric figure bounded by curved boundaries. In elementary Euclidean geometry, area is defined axiomatically for rectilinear polygons by decomposing them into finite unions of non-overlapping triangles. However, when the boundary of a domain is formed by the graph of an arbitrary real-valued function, finite polygonal decomposition fails fundamentally. 

Consider a non-degenerate compact interval $[a, b] \subset \mathbb{R}$ with $a < b$, and let $f: [a, b] \to \mathbb{R}$ be a non-negative function satisfying $f(x) \ge 0$ for all $x \in [a, b]$. The planar set:
$$
\begin{gather}
E(f; a, b) := \left\{ (x, y) \in \mathbb{R}^2 \;\middle|\; a \le x \le b, \; 0 \le y \le f(x) \right\} \tag{1}
\end{gather}
$$
is defined as the *curvilinear trapezoid* (or the subgraph) associated with $f$ over $[a, b]$. 

To assign a precise numerical area to the set of step 1, the base interval $[a, b]$ must be discretized by choosing an ordered array of division points:
$$
\begin{gather}
a = x_0 < x_1 < x_2 < \dots < x_{n-1} < x_n = b \tag{2}
\end{gather}
$$
The division points of step 2 partition the curvilinear trapezoid into $n$ narrow vertical strips:
$$
\begin{gather}
E_i := \left\{ (x, y) \in \mathbb{R}^2 \;\middle|\; x_{i-1} \le x \le x_i, \; 0 \le y \le f(x) \right\}, \quad i \in \{1, \dots, n\} \tag{3}
\end{gather}
$$
On each subinterval $[x_{i-1}, x_i]$, the displacement is denoted by $\Delta x_i := x_i - x_{i-1}$. If the width $\Delta x_i$ is small, the graph of $f(x)$ over $[x_{i-1}, x_i]$ does not deviate drastically from the horizontal line segment evaluated at an intermediate sampling point $\xi_i \in [x_{i-1}, x_i]$. Consequently, the area of the curvilinear strip $E_i$ is approximated by the area of the elementary rectangle with base $\Delta x_i$ and height $f(\xi_i)$:
$$
\begin{gather}
\text{Area}(E_i) \approx f(\xi_i) \Delta x_i \tag{4}
\end{gather}
$$
Summing the elementary rectangular areas across all $n$ subintervals yields an aggregate discrete approximation to the total area of $E(f; a, b)$:
$$
\begin{gather}
\text{Area}(E(f; a, b)) \approx \sum_{i=1}^n f(\xi_i) \Delta x_i \tag{5}
\end{gather}
$$
If this finite discrete sum stabilizes toward a unique real number as the partition becomes arbitrarily fine—independent of the specific choices of the partition points $x_i$ and the intermediate evaluation nodes $\xi_i$—that limiting value represents the true geometric area of the curvilinear trapezoid.

### Kinematic and Dynamic Foundations: Work and Displacement
While geometry provided the visual catalyst for the integral, the conceptual necessity of integration as an analytical technique within symbolic manipulation is demonstrated most compellingly by classical kinematics and mechanics.

##### Kinematic Accumulation of Displacement
Consider a point mass moving rectilinearly along an axis. Let $v(t)$ denote the instantaneous velocity of the particle at time $t$ over a temporal interval $[a, b]$. If the velocity is strictly constant, $v(t) \equiv v_0$, the total displacement $\Delta s$ is given by the elementary algebraic product:
$$
\begin{gather}
\Delta s = v_0 (b - a) \tag{6}
\end{gather}
$$
However, in physical dynamical systems, the velocity varies continuously or piecewisely in response to applied forces. Over a small temporal increment $[t_{i-1}, t_i]$ of duration $\Delta t_i := t_i - t_{i-1}$, the true velocity $v(t)$ fluctuates. By selecting an intermediate instant $\tau_i \in [t_{i-1}, t_i]$, the quantity $v(\tau_i)$ serves as an approximation to the velocity throughout the subinterval. The incremental displacement traversed during $[t_{i-1}, t_i]$ is approximated by:
$$
\begin{gather}
\Delta s_i \approx v(\tau_i) \Delta t_i \tag{7}
\end{gather}
$$
The total macroscopic displacement between $t = a$ and $t = b$ is then approximated by the discrete sum:
$$
\begin{gather}
\Delta s \approx \sum_{i=1}^n v(\tau_i) \Delta t_i \tag{8}
\end{gather}
$$
The exact physical displacement is the limit of the sum of step 8 as the durations of all subintervals simultaneously vanish.

##### Mechanical Work Done by a Variable Force
An identical synthesis governs the calculation of mechanical work. Let a particle move along the $x$-axis from $x = a$ to $x = b$ under the influence of a spatial force field $F(x)$ directed along the line of motion. When the force is constant, $F(x) \equiv F_0$, the mechanical work performed is the product of force and distance:
$$
\begin{gather}
W = F_0 (b - a) \tag{9}
\end{gather}
$$
When the force $F(x)$ varies spatially, one partitions the path $[a, b]$ via the nodes of step 2. Within each spatial segment $[x_{i-1}, x_i]$, the applied force is approximated by its value at an intermediate point $\xi_i \in [x_{i-1}, x_i]$. The work performed over $[x_{i-1}, x_i]$ is approximately $F(\xi_i) \Delta x_i$, yielding the total approximate work:
$$
\begin{gather}
W \approx \sum_{i=1}^n F(\xi_i) \Delta x_i \tag{10}
\end{gather}
$$
Passing to the limit as the partition mesh tends to zero yields the exact physical work.

The mathematical structure underlying the geometric area of step 5, the kinematic displacement of step 8, and the mechanical work of step 10 is identical. In each setting, a distributed continuum quantity is partitioned into localized increments, approximated on each increment by the product of an instantaneous state value and an interval length, and reconstituted globally via a discrete sum. The systematic formulation of this limiting operation constitutes the theory of the *Riemann integral*.

### Partitions, Sampling Nodes, and Riemann Sums
To transform these heuristic approximations into an exact mathematical framework, the concepts of partitions, evaluation nodes, and fineness must be defined formally: 
$$
\begin{gather}
\textbf{Definition: Partition and Mesh Fineness} \\[5mm]
\text{Let } [a, b] \subset \mathbb{R} \text{ be a non-degenerate compact interval with } a < b. \\[2mm]
\text{A \textit{partition} } P \text{ of } [a, b] \text{ is a finite ordered set of points } P = \{x_0, x_1, \dots, x_n\} \subset [a, b] \text{ such that:} \\[3.5mm]
a = x_0 < x_1 < x_2 < \dots < x_{n-1} < x_n = b \\[3.5mm]
\text{The points } x_i \text{ are termed the \textit{partition nodes} of } P. \text{ The compact intervals:} \\[2mm]
\Delta_i := [x_{i-1}, x_i], \quad i \in \{1, \dots, n\} \\[2mm]
\text{are termed the \textit{subintervals} of the partition, each having length } \Delta x_i := x_i - x_{i-1} > 0. \\[3.5mm]
\text{The \textit{mesh fineness} (or \textit{gauge}) of the partition } P, \text{ denoted } \lambda(P), \text{ is defined as:} \\[3.5mm]
\lambda(P) := \max_{1 \le i \le n} \Delta x_i
\end{gather}
$$

The mesh fineness $\lambda(P)$ provides a metric of the coarseness of the discretization. For any partition $P$, the condition $\lambda(P) < \delta$ guarantees that the length of *every* subinterval $\Delta_i$ is strictly less than $\delta$.

To sample values of a function on the partitioned interval, intermediate points must be assigned to each subinterval: 
$$
\begin{gather}
\textbf{Definition: Marked Partition and Riemann Sum} \\[5mm]
\text{Let } P = \{x_0, x_1, \dots, x_n\} \text{ be a partition of } [a, b]. \\[2mm]
\text{A vector } \xi = (\xi_1, \xi_2, \dots, \xi_n) \in \mathbb{R}^n \text{ is termed an \textit{intermediate point selection} for } P \text{ if:} \\[3.5mm]
\xi_i \in \Delta_i = [x_{i-1}, x_i] \quad \text{for every } i \in \{1, \dots, n\} \\[3.5mm]
\text{The pair } (P, \xi) \text{ is called a \textit{marked partition} (or \textit{tagged partition}) of } [a, b]. \\[2mm]
\text{Given a function } f: [a, b] \to \mathbb{R}, \text{ the \textit{Riemann sum} (or \textit{integral sum}) of } f \\[2mm]
\text{associated with the marked partition } (P, \xi) \text{ is defined by:} \\[3.5mm]
\sigma(f; P, \xi) := \sum_{i=1}^n f(\xi_i) \Delta x_i
\end{gather}
$$

The Riemann sum $\sigma(f; P, \xi)$ is a real number depending on three distinct inputs: the function $f$, the geometric partition $P$, and the intermediate point selection $\xi$. 

>[!danger]+ Intuition: Slicing the Continuum
>The construction of the Riemann sum embodies the fundamental discretization strategy of classical real analysis. In nature, continuous distributions vary non-linearly across spatial and temporal dimensions. Because human analytical tools compute products of constant quantities with elementary ease, the continuous domain is shattered into microscopic segments. On each microscopic segment, the non-linear variation is frozen at a representative witness point $\xi_i$. The aggregate sum reassembles the frozen slices into a global total. If the continuum possesses sufficient regularity, the micro-errors introduced by freezing the function on each slice cancel or shrink faster than the segment widths, collapsing to an exact invariant quantity in the limit.

---

# The Definite Riemann Integral

### The Formal Limit of Riemann Sums
 Unlike the classical Cauchy limit of a sequence $a_n \to L$ (where the index $n \in \mathbb{N}$ advances linearly) or the limit of a function $f(x) \to L$ as $x \to x_0$ along a real continuum, the limit of Riemann sums operates over a directed filter of marked partitions: 
$$
\begin{gather}
\textbf{Definition: The Riemann Integral and the Space } \mathcal{R}[a, b] \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a real-valued function defined on a compact interval } [a, b]. \\[2mm]
\text{A number } I \in \mathbb{R} \text{ is called the \textit{Riemann integral} of } f \text{ over } [a, b] \text{ if for every } \varepsilon > 0, \\[2mm]
\text{there exists a } \delta > 0 \text{ such that for every marked partition } (P, \xi) \text{ of } [a, b] \text{ satisfying } \lambda(P) < \delta, \\[2mm]
\text{the corresponding Riemann sum satisfies } \left| \sigma(f; P, \xi) - I \right| < \varepsilon. \\[3.5mm]
\text{If such a number } I \text{ exists, the function } f \text{ is said to be \textit{Riemann integrable} on } [a, b], \\[2mm]
\text{denoted by } f \in \mathcal{R}[a, b], \text{ and the number } I \text{ is designated by the symbols:} \\[3.5mm]
I =: \int_a^b f(x)\,dx = \int_a^b f
\end{gather}
$$

The analytical convergence condition is expressed as:
$$
\begin{gather}
\left| \sum_{i=1}^n f(\xi_i) \Delta x_i - I \right| < \varepsilon \tag{11}
\end{gather}
$$

The symbol $\int$ is an elongated stylized 'S' (from the Latin *summa*), introduced by Gottfried Wilhelm Leibniz to signify the continuous sum of infinitesimal differentials $f(x)\,dx$. The points $a$ and $b$ are the *lower limit* and *upper limit* of integration, respectively, and $f(x)$ is the *integrand*.

##### Uniqueness of the Riemann Integral
The limit of the Riemann sum, whenever it exists, is unique. Suppose there exist two numbers $I_1, I_2 \in \mathbb{R}$ satisfying the condition of step 11. Let $\varepsilon > 0$ be arbitrary. Then there exist $\delta_1, \delta_2 > 0$ such that $|\sigma(f; P, \xi) - I_1| < \varepsilon / 2$ for all $\lambda(P) < \delta_1$ and $|\sigma(f; P, \xi) - I_2| < \varepsilon / 2$ for all $\lambda(P) < \delta_2$. Selecting $\delta := \min\{\delta_1, \delta_2\}$ and choosing an arbitrary marked partition $(P, \xi)$ with $\lambda(P) < \delta$, the triangle inequality yields:
$$
\begin{gather}
|I_1 - I_2| \le |I_1 - \sigma(f; P, \xi)| + |\sigma(f; P, \xi) - I_2| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{12}
\end{gather}
$$
Because the inequality of step 12 holds for every $\varepsilon > 0$, it follows that $|I_1 - I_2| = 0$, establishing $I_1 = I_2$.

### The Fundamental Necessity of Boundedness
The definition of the Riemann integral requires that the condition of step 11 holds for *all* possible choices of the intermediate point selection $\xi$. This universal quantification across all tag vectors imposes an immediate, non-negotiable structural constraint on the integrand: the function must be bounded: 
$$
\begin{gather}
\textbf{Theorem: Necessity of Boundedness for Riemann Integrability} \\[5mm]
\text{Let } [a, b] \subset \mathbb{R} \text{ be a non-degenerate compact interval, and let } f: [a, b] \to \mathbb{R}. \\[2mm]
\text{If } f \in \mathcal{R}[a, b], \text{ then } f \text{ is bounded on } [a, b], \text{ meaning there exists } M > 0 \text{ such that:} \\[3.5mm]
\sup_{x \in [a, b]} |f(x)| \le M
\end{gather}
$$
(see [[Proof of the Necessity of Boundedness for Riemann Integrability]])

The operational consequence of this theorem is absolute as unbounded functions cannot possess a definite Riemann integral in the proper sense. If an integrand fails to be bounded, its study must be relegated to the distinct theory of *[[Chapter 4 - Improper Integrals|improper integrals]]*. 

>[!warning]+ Warning: Unbounded Functions and Divergence of Riemann Sums
>If a function $f$ is unbounded on $[a, b]$, then for *any* partition $P$, regardless of how small the mesh $\lambda(P)$ is made, there exists at least one subinterval $\Delta_k = [x_{k-1}, x_k]$ on which $f$ is unbounded. Because the evaluation node $\xi_k \in \Delta_k$ can be selected freely, the term $f(\xi_k) \Delta x_k$ can be made arbitrarily large in absolute value, completely destabilizing the sum $\sigma(f; P, \xi)$. Thus, boundedness is not merely a technical convenience, but a foundational requirement for the stability of finite integral sums.

##### Visualization of Bounded Sums
```easy-tikz
title $\text{Riemann Sum Approximation and Subinterval Partition}$
xlabel $x$
ylabel $y$
show x from 0 to 10 and y from 0 to 6.5
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 0.35*x + 0.07*x^2 - 0.0075*x^3, from x = 1.0 to 9.0, in teal, very thick
draw a line from (1.5, 0) to (1.5, 1.66), in gray, dashed
draw a line from (3.0, 0) to (3.0, 2.48), in gray, dashed
draw a line from (5.0, 0) to (5.0, 3.56), in gray, dashed
draw a line from (7.0, 0) to (7.0, 4.32), in gray, dashed
draw a line from (9.0, 0) to (9.0, 4.35), in gray, dashed
draw a line from (1.5, 2.10) to (3.0, 2.10), in orange, thick
draw a line from (1.5, 0) to (1.5, 2.10), in orange, thick
draw a line from (3.0, 0) to (3.0, 2.10), in orange, thick
draw a line from (3.0, 3.05) to (5.0, 3.05), in green, thick
draw a line from (3.0, 0) to (3.0, 3.05), in green, thick
draw a line from (5.0, 0) to (5.0, 3.05), in green, thick
draw a line from (5.0, 4.02) to (7.0, 4.02), in red, thick
draw a line from (5.0, 0) to (5.0, 4.02), in red, thick
draw a line from (7.0, 0) to (7.0, 4.02), in red, thick
draw a line from (7.0, 4.42) to (9.0, 4.42), in pink, thick
draw a line from (7.0, 0) to (7.0, 4.42), in pink, thick
draw a line from (9.0, 0) to (9.0, 4.42), in pink, thick
mark (2.2, 2.10), in orange, large
mark (4.1, 3.05), in green, large
mark (6.1, 4.02), in red, large
mark (8.1, 4.42), in pink, large
write "$a = x_0$" at (1.5, -0.35) in gray, below
write "$x_1$" at (3.0, -0.35) in gray, below
write "$x_2$" at (5.0, -0.35) in gray, below
write "$x_3$" at (7.0, -0.35) in gray, below
write "$b = x_4$" at (9.0, -0.35) in gray, below
write "$\\xi_1$" at (2.2, -0.35) in orange, below
write "$\\xi_2$" at (4.1, -0.35) in green, below
write "$\\xi_3$" at (6.1, -0.35) in red, below
write "$\\xi_4$" at (8.1, -0.35) in pink, below
write "$y = f(x)$" at (0.05, 1.9) in teal, right
write "$f(\\xi_2)$" at (4.1, 3.3) in green, above
write "$\\Delta x_2$" at (4.0, 0.4) in gray, center
```


---
# Darboux Sums and the Metric of Oscillation
While the definition of the Riemann integral via marked partitions $(P, \xi)$ directly reflects physical intuition, verifying the $\varepsilon$-$\delta$ condition of step 11 directly is analytically challenging due to the arbitrary freedom in selecting the evaluation nodes $\xi_i$. To eliminate this arbitrariness, Gaston Darboux introduced upper and lower sums that provide extreme deterministic bounds for all possible Riemann sums on a given partition: 
```easy-tikz
title $\text{Upper and Lower Darboux Bounds and Oscillation Band}$
xlabel $x$
ylabel $y$
show x from -0.096 to 7.904 and y from 0.083 to 6.083
axes on the edges
size 12 x 8
plot f(x) = 1.2 + 0.3*x + 0.12*x^2 - 0.015*x^3, from x = 1.0 to 7.0, in teal, very thick
draw a line from (2.0, 0) to (2.0, 4.5), in gray, dashed
draw a line from (6.0, 0) to (6.0, 4.5), in gray, dashed
draw a line from (2.0, 2.16) to (6.0, 2.16), in orange, very thick
draw a line from (2.0, 0) to (2.0, 2.16), in orange, thick
draw a line from (6.0, 0) to (6.0, 2.16), in orange, thick
draw a line from (2.0, 4.08) to (6.0, 4.08), in green, very thick
draw a line from (2.0, 0) to (2.0, 4.08), in green, thick
draw a line from (6.0, 0) to (6.0, 4.08), in green, thick
draw a line from (6.3, 2.16) to (6.3, 4.08), in red, very thick
draw a line from (6.15, 2.16) to (6.45, 2.16), in red, thick
draw a line from (6.15, 4.08) to (6.45, 4.08), in red, thick
mark (2.0, 2.16), in orange, large
mark (5.2, 4.08), in green, large
write "$x_{i-1}$" at (2.0, -0.35) in gray, below
write "$x_i$" at (6.0, -0.35) in gray, below
write "$m_i= \\inf_{\\Delta_i} f$" at (4.0, 1.8) in orange, below
write "$M_i= \\sup_{\\Delta_i} f$" at (4.0, 4.35) in green
write "$y =f(x)$" at (1, 2.0) in teal, left
write "$\\omega(f; \\Delta_i)$" at (6.6, 3.12) in red, right
write "$\\Delta x_i$" at (4.0, 0.4) in gray, center
```

### Upper and Lower Sums: The Envelope of Approximations
Let $f: [a, b] \to \mathbb{R}$ be a bounded function, and let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b].$ Because $f$ is bounded, the image of each subinterval $\Delta_i = [x_{i-1}, x_i]$ under $f$ is a bounded subset of $\mathbb{R}.$ By the [[Chapter 1 - Basic Properties of Real Numbers|Completeness Axiom of the real numbers]], the infimum and supremum of $f$ on $\Delta_i$ exist as finite real numbers:
$$
\begin{gather}
m_i := \inf_{x \in \Delta_i} f(x), \qquad M_i := \sup_{x \in \Delta_i} f(x) \tag{13}
\end{gather}
$$
Furthermore, let $m$ and $M$ denote the global infimum and supremum of $f$ on the entire interval $[a, b]$:
$$
\begin{gather}
m := \inf_{x \in [a, b]} f(x), \qquad M := \sup_{x \in [a, b]} f(x) \tag{14}
\end{gather}
$$
Because $\Delta_i \subseteq [a, b]$, it follows directly that:
$$
\begin{gather}
m \le m_i \le f(\xi_i) \le M_i \le M \tag{15}
\end{gather}
$$
for every intermediate point $\xi_i \in \Delta_i$.

$$
\begin{gather}
\textbf{Definition: Darboux Sums} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function, and let } P = \{x_0, x_1, \dots, x_n\} \text{ be a partition of } [a, b]. \\[2mm]
\text{The \textit{lower Darboux sum} of } f \text{ with respect to } P \text{ is defined by:} \\[3.5mm]
s(f; P) := \sum_{i=1}^n m_i \Delta x_i = \sum_{i=1}^n \left( \inf_{x \in \Delta_i} f(x) \right) \Delta x_i \\[3.5mm]
\text{The \textit{upper Darboux sum} of } f \text{ with respect to } P \text{ is defined by:} \\[3.5mm]
S(f; P) := \sum_{i=1}^n M_i \Delta x_i = \sum_{i=1}^n \left( \sup_{x \in \Delta_i} f(x) \right) \Delta x_i
\end{gather}
$$

Multiplying the chain of inequalities of step 15 by $\Delta x_i > 0$ and summing across $i \in \{1, \dots, n\}$ establishes the fundamental sandwich relation:
$$
\begin{gather}
m(b - a) \le s(f; P) \le \sigma(f; P, \xi) \le S(f; P) \le M(b - a) \tag{16}
\end{gather}
$$
The inequality of step 16 holds for every choice of intermediate points $\xi$. In fact, by the properties of the infimum and supremum, the lower and upper Darboux sums represent the exact infimum and supremum of the Riemann sums over all possible choices of $\xi$ for a fixed partition $P$:
$$
\begin{gather}
s(f; P) = \inf_{\xi} \sigma(f; P, \xi), \qquad S(f; P) = \sup_{\xi} \sigma(f; P, \xi) \tag{17}
\end{gather}
$$

### Monotonicity Under Partition Refinement
To analyze how Darboux sums evolve as the discretization changes, the notion of partition refinement comes into play. 

A partition $P'$ is called a *refinement* of a partition $P$ (written $P \subseteq P'$) if every partition node of $P$ is also a partition node of $P'$. The refined partition $P'$ is obtained from $P$ by adjoining a finite number of additional division nodes: 
$$
\begin{gather}
\textbf{Lemma: Darboux Sum Monotonicity Under Refinement} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function, and let } P \text{ and } P' \text{ be partitions of } [a, b]. \\[2mm]
\text{If } P' \text{ is a refinement of } P \text{ (that is, } P \subseteq P'\text{), then:} \\[3.5mm]
s(f; P) \le s(f; P') \quad \text{and} \quad S(f; P') \le S(f; P)
\end{gather}
$$
(see [[Proof of the Darboux Sum Monotonicity Under Refinement]])

This lemma reveals the directional monotonicity of Darboux sums: as additional division points are added to a partition, the lower sums *increase* (or remain unchanged), while the upper sums *decrease* (or remain unchanged). Adding nodes trims excess area from the upper rectangles and fills uncounted voids in the lower rectangles, tightening the envelope around the true integral.

### The Arbitrary Partition Inequality and Darboux Integrals
A critical consequence of refinement monotonicity is that *any* lower Darboux sum is bounded above by *any* upper Darboux sum, even if the sums are evaluated on completely distinct partitions: 
$$
\begin{gather}
\textbf{Proposition: Arbitrary Partition Darboux Inequality} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function. For any two arbitrary partitions } P_1 \text{ and } P_2 \text{ of } [a, b]: \\[3.5mm]
s(f; P_1) \le S(f; P_2)
\end{gather}
$$
(see [[Proof of the Arbitrary Partition Darboux Inequality]])

The inequality $s(f; P_1) \le S(f; P_2)$ ensures that the set of all lower sums $\{s(f; P) \mid P \text{ is a partition of } [a, b]\}$ is bounded from above by every upper sum $S(f; P_2)$, and the set of all upper sums $\{S(f; P) \mid P \text{ is a partition of } [a, b]\}$ is bounded from below by every lower sum $s(f; P_1)$. By the Completeness Axiom of $\mathbb{R}$, both sets possess finite extrema: 
$$
\begin{gather}
\textbf{Definition: Upper and Lower Darboux Integrals} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function.} \\[2mm]
\text{The \textit{lower Darboux integral} of } f \text{ on } [a, b] \text{ is defined as:} \\[3.5mm]
\underline{I}(f) := \sup_{P} s(f; P) \\[3.5mm]
\text{The \textit{upper Darboux integral} of } f \text{ on } [a, b] \text{ is defined as:} \\[3.5mm]
\overline{I}(f) := \inf_{P} S(f; P) \\[3.5mm]
\text{where the supremum and infimum are taken over the collection of all partitions } P \text{ of } [a, b].
\end{gather}
$$

Because $s(f; P_1) \le S(f; P_2)$ for all $P_1, P_2$, taking the supremum over $P_1$ yields $\underline{I}(f) \le S(f; P_2)$. Subsequently taking the infimum over $P_2$ establishes the universal ordering of Darboux integrals:
$$
\begin{gather}
m(b - a) \le s(f; P) \le \underline{I}(f) \le \overline{I}(f) \le S(f; P) \le M(b - a) \tag{18}
\end{gather}
$$
for every partition $P$ of $[a, b]$.

### The Limit of Darboux Sums: Darboux's Theorem
While the Darboux integrals $\underline{I}(f)$ and $\overline{I}(f)$ are defined via suprema and infima across all possible partitions, Darboux's Theorem establishes that they are identical to the limits of $s(f; P)$ and $S(f; P)$ as the mesh $\lambda(P) \to 0$: 
$$
\begin{gather}
\textbf{Darboux's Theorem on Limits of Upper and Lower Sums:} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function on } [a, b]. \\[2mm]
\text{Then the lower and upper Darboux sums converge to the lower and upper Darboux integrals} \\[2mm]
\text{as the partition mesh tends to zero:} \\[3.5mm]
\lim_{\lambda(P) \to 0} s(f; P) = \underline{I}(f) \quad \text{and} \quad \lim_{\lambda(P) \to 0} S(f; P) = \overline{I}(f)
\end{gather}
$$
(see [[Proof of Darboux's Theorem on Limits of Upper and Lower Sums]])

Darboux's Theorem bridges the static supremum/infimum formulation with the dynamic limit as $\lambda(P) \to 0$. 

### The Fundamental Oscillation Criterion
The discrepancy between the upper and lower Darboux sums measures the total uncertainty of the approximation. For a bounded function $f$ on an interval $\Delta_i$, the *oscillation* of $f$ on $\Delta_i$ is defined by:
$$
\begin{gather}
\omega(f; \Delta_i) := M_i - m_i = \sup_{x \in \Delta_i} f(x) - \inf_{x \in \Delta_i} f(x) = \sup_{x', x'' \in \Delta_i} |f(x') - f(x'')| \tag{19}
\end{gather}
$$
The difference between the upper and lower Darboux sums associated with a partition $P$ evaluates directly to:
$$
\begin{gather}
S(f; P) - s(f; P) = \sum_{i=1}^n M_i \Delta x_i - \sum_{i=1}^n m_i \Delta x_i = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i \tag{20}
\end{gather}
$$
The identity of step 20 represents the *total oscillation* of $f$ weighted by subinterval lengths: 
$$
\begin{gather}
\textbf{Theorem: Riemann Integrability Criterion via Oscillation} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function on a compact interval } [a, b]. \\[2mm]
\text{The following assertions are logically equivalent:} \\[2mm]
1. \ f \in \mathcal{R}[a, b] \text{ (that is, } f \text{ is Riemann integrable on } [a, b]\text{).} \\[2mm]
2. \ \underline{I}(f) = \overline{I}(f). \\[2mm]
3. \ \forall \varepsilon > 0, \; \exists P \text{ (a partition of } [a, b]\text{) such that } S(f; P) - s(f; P) = \sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i < \varepsilon. \\[2mm]
4. \ \lim_{\lambda(P) \to 0} \big( S(f; P) - s(f; P) \big) = 0.
\end{gather}
$$
(see [[Proof of the Riemann Integrability Criterion via Oscillation]])

When these equivalent conditions are satisfied, the common value coincides with the Riemann integral:
$$
\begin{gather}
\int_a^b f(x)\,dx = \underline{I}(f) = \overline{I}(f) \tag{21}
\end{gather}
$$

>[!info]+ Remark: Operational Equivalence of Riemann and Darboux Frameworks
>The Oscillation Criterion provides the definitive theoretical tool for proving integrability. Rather than testing whether Riemann sums $\sigma(f; P, \xi)$ converge to an unknown limit $I$ across infinitely many intermediate point combinations $\xi$, one evaluates the deterministic metric difference $S(f; P) - s(f; P)$. If a partition can be constructed whose weighted oscillation sum is strictly smaller than $\varepsilon$, integrability is guaranteed.

---
# Structural Classes of Riemann Integrable Functions
Equipped with the oscillation criterion, one can systematically identify the major function spaces contained within $\mathcal{R}[a, b]$.

### Integrability of Continuous Mappings
The most prominent class of integrable functions consists of continuous mappings: 
$$
\begin{gather}
\textbf{Theorem: Integrability of Continuous Functions on Compact Intervals} \\[5mm]
\text{Let } [a, b] \subset \mathbb{R} \text{ be a non-degenerate compact interval.} \\[2mm]
\text{If } f: [a, b] \to \mathbb{R} \text{ is continuous on } [a, b] \text{ (that is, } f \in C[a, b]\text{), then } f \in \mathcal{R}[a, b].
\end{gather}
$$
(see [[Proof of the Integrability of Continuous Functions on Compact Intervals]])

The fundamental mechanism driving this theorem is Cantor's Uniform Continuity Theorem, proved in [[Chapter 2 - Properties of Continuous Functions|Module 4, Chapter 2]]: any continuous function on a compact interval is *uniformly continuous*. Uniform continuity ensures that on every subinterval $\Delta_i$ of a sufficiently fine partition, the local oscillation $\omega(f; \Delta_i)$ can be made simultaneously and uniformly smaller than $\frac{\varepsilon}{b - a}$, forcing the weighted oscillation sum below $\varepsilon$.

### Integrability of Monotone Mappings
Remarkably, continuity is not a necessary condition for integrability. A function can possess infinitely many discontinuities and still belong to $\mathcal{R}[a, b]$, provided its variations exhibit monotone structure: 
$$
\begin{gather}
\textbf{Theorem: Integrability of Monotone Functions} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a monotonic function on } [a, b]. \\[2mm]
\text{Then } f \in \mathcal{R}[a, b].
\end{gather}
$$
(see [[Proof of the Integrability of Monotone Functions]])

For a monotonic function (for instance, a non-decreasing function), the supremum and infimum on any subinterval $\Delta_i = [x_{i-1}, x_i]$ are attained exactly at the endpoints: $m_i = f(x_{i-1})$ and $M_i = f(x_i)$. Consequently, the local oscillation is simply $\omega(f; \Delta_i) = f(x_i) - f(x_{i-1})$. When the partition is chosen with equal subinterval lengths $\Delta x_i = \frac{b - a}{n}$, the oscillation sum telescopes:
$$
\begin{gather}
\sum_{i=1}^n \omega(f; \Delta_i) \Delta x_i = \frac{b - a}{n} \sum_{i=1}^n \big( f(x_i) - f(x_{i-1}) \big) = \frac{b - a}{n} \big( f(b) - f(a) \big) \tag{22}
\end{gather}
$$
Choosing $n$ sufficiently large renders the right-hand side of step 22 strictly less than $\varepsilon$, establishing integrability unconditionally. Because monotonic functions can possess a countably dense set of jump discontinuities, this theorem confirms that the presence of discontinuities does not preclude Riemann integrability.

### Integrability of Piecewise Continuous Mappings
In engineering, signal processing, and physical modeling, functions frequently possess jump discontinuities at isolated interface boundaries: 
$$
\begin{gather}
\textbf{Theorem: Integrability of Functions with Finitely Many Discontinuities} \\[5mm]
\text{Let } f: [a, b] \to \mathbb{R} \text{ be a bounded function.} \\[2mm]
\text{If the set of points of discontinuity of } f \text{ in } [a, b] \text{ is finite, then } f \in \mathcal{R}[a, b].
\end{gather}
$$
(see [[Proof of the Integrability of Functions with Finitely Many Discontinuities]])

The strategy of the proof isolates each of the finitely many discontinuity nodes within disjoint open intervals of arbitrarily small aggregate length. The total oscillation contribution across these singular intervals is bounded by $2M$ times their total length. On the remaining compact portions of $[a, b]$, the function is continuous, and its oscillation is made small by uniform continuity. Summing the two contributions establishes integrability.

### Non-Linear Transformations: Continuous Post-Composition
A fundamental question regarding the algebraic structure of $\mathcal{R}[a, b]$ is whether integrability is preserved under function composition. While the composition of two arbitrary integrable functions generally fails to be integrable (as demonstrated in the Pathological Gallery below), post-composition by a continuous mapping is universally valid: 
$$
\begin{gather}
\textbf{Theorem: Continuous Composition Integrability Theorem} \\[5mm]
\text{Let } f \in \mathcal{R}[a, b] \text{ with image } f([a, b]) \subseteq [c, d] \subset \mathbb{R}. \\[2mm]
\text{If } \phi: [c, d] \to \mathbb{R} \text{ is continuous on } [c, d], \text{ then the composite function:} \\[3.5mm]
(\phi \circ f)(x) := \phi(f(x)) \\[3.5mm]
\text{belongs to } \mathcal{R}[a, b].
\end{gather}
$$
(see [[Proof of the Continuous Composition Integrability Theorem]])

This theorem yields immediate structural corollaries:
1. If $f \in \mathcal{R}[a, b]$, then $|f| \in \mathcal{R}[a, b]$ (by choosing $\phi(u) = |u|$).
2. If $f \in \mathcal{R}[a, b]$ and $p \in \mathbb{N}$, then $f^p \in \mathcal{R}[a, b]$ (by choosing $\phi(u) = u^p$).
3. If $f \in \mathcal{R}[a, b]$ and there exists $c > 0$ such that $|f(x)| \ge c$ for all $x \in [a, b]$, then $\frac{1}{f} \in \mathcal{R}[a, b]$ (by choosing $\phi(u) = \frac{1}{u}$).

### Measure Zero and Lebesgue's Criterion of Integrability
The preceding theorems identify specific families of integrable functions ($C[a, b]$, monotone functions, piecewise continuous functions). The complete, definitive characterization of the entire space $\mathcal{R}[a, b]$ was achieved by Henri Lebesgue through the concept of sets of measure zero: 
$$
\begin{gather}
\textbf{Definition: Set of Measure Zero in the Sense of Lebesgue} \\[5mm]
\text{A subset } E \subset \mathbb{R} \text{ is said to have \textit{Lebesgue measure zero} (or to be a \textit{null set}) if for every } \varepsilon > 0, \\[2mm]
\text{there exists a finite or countably infinite collection of open intervals } \{I_k\}_{k=1}^\infty \text{ such that:} \\[3.5mm]
E \subseteq \bigcup_{k=1}^\infty I_k \quad \text{and} \quad \sum_{k=1}^\infty |I_k| < \varepsilon \\[3.5mm]
\text{where } |I_k| \text{ denotes the length of the open interval } I_k.
\end{gather}
$$

Elementary examples of sets of measure zero include:
- Any finite set $E = \{p_1, \dots, p_m\}$ (enclose each point in an interval of length $\frac{\varepsilon}{2m}$).
- Any countably infinite set $E = \{p_1, p_2, \dots, p_k, \dots\}$ (enclose each $p_k$ in an interval of length $\frac{\varepsilon}{2^{k+1}}$). In particular, the set of rational numbers $\mathbb{Q}$ has measure zero.
- Certain uncountable sets, such as the Cantor ternary set $C \subset [0, 1]$.

$$
\begin{gather}
\textbf{Theorem: Lebesgue's Criterion for Riemann Integrability} \\[5mm]
\text{Let } [a, b] \subset \mathbb{R} \text{ be a non-degenerate compact interval, and let } f: [a, b] \to \mathbb{R} \text{ be a bounded function.} \\[2mm]
\text{Let } D_f \subset [a, b] \text{ denote the set of points at which } f \text{ is discontinuous:} \\[3.5mm]
D_f := \left\{ x \in [a, b] \;\middle|\; f \text{ is not continuous at } x \right\} \\[3.5mm]
\text{Then } f \in \mathcal{R}[a, b] \text{ if and only if } D_f \text{ has Lebesgue measure zero.}
\end{gather}
$$
(see [[Proof of Lebesgue's Criterion for Riemann Integrability]])

Lebesgue's Criterion provides the master taxonomy of Riemann integration. A bounded function is Riemann integrable if and only if its discontinuities are negligible from the perspective of linear measure. Continuous functions are integrable because $D_f = \emptyset$; functions with finitely many discontinuities are integrable because finite sets have measure zero; and monotone functions are integrable because their discontinuity sets are at most countable.

>[!info]+ Remark: The Topological Geometry of Discontinuities
>Lebesgue's criterion reveals why the Riemann integral possesses a fragile boundary. If the discontinuity set $D_f$ has positive outer measure, the local oscillations $\omega(f; \Delta_i)$ cannot be suppressed over small intervals, precluding the convergence of Darboux sums. This limitation prompted the subsequent development of the *Lebesgue integral*, where partitioning is executed along the range of the function rather than its domain.

---
# Pathological Gallery: Counterexamples to Converses and Fragile Integrability
To understand the boundaries of Riemann integrability, the pathological mappings where intuitive properties break down must be examined. 

### The Nowhere-Integrable Dirichlet Mapping
##### 1. Dense Discontinuity and Total Oscillation
Consider the classical Dirichlet mapping $D: [0, 1] \to \mathbb{R}$ defined by:
$$
\begin{gather}
D(x) := \begin{cases} 1 & \text{if } x \in \mathbb{Q} \cap [0, 1] \\ 0 & \text{if } x \in (\mathbb{R} \setminus \mathbb{Q}) \cap [0, 1] \end{cases} \tag{23}
\end{gather}
$$
The function $D(x)$ is bounded: $0 \le D(x) \le 1$ for all $x \in [0, 1]$. 

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[0, 1]$. By the density of the rational numbers $\mathbb{Q}$ in $\mathbb{R}$, every non-degenerate subinterval $\Delta_i = [x_{i-1}, x_i]$ contains a rational number $r_i \in \mathbb{Q}$, where $D(r_i) = 1$. Consequently:
$$
\begin{gather}
M_i = \sup_{x \in \Delta_i} D(x) = 1 \tag{24}
\end{gather}
$$
Similarly, by the density of the irrational numbers $\mathbb{R} \setminus \mathbb{Q}$ in $\mathbb{R}$, every subinterval $\Delta_i$ contains an irrational number $s_i \notin \mathbb{Q}$, where $D(s_i) = 0$. Consequently:
$$
\begin{gather}
m_i = \inf_{x \in \Delta_i} D(x) = 0 \tag{25}
\end{gather}
$$
Evaluating the lower and upper Darboux sums for the partition $P$ yields:
$$
\begin{gather}
s(D; P) = \sum_{i=1}^n m_i \Delta x_i = \sum_{i=1}^n 0 \cdot \Delta x_i = 0 \tag{26} \\[2mm]
S(D; P) = \sum_{i=1}^n M_i \Delta x_i = \sum_{i=1}^n 1 \cdot \Delta x_i = \sum_{i=1}^n (x_i - x_{i-1}) = 1 - 0 = 1 \tag{27}
\end{gather}
$$
Because the equations of step 26 and step 27 hold for *every* partition $P$, computing the lower and upper Darboux integrals yields:
$$
\begin{gather}
\underline{I}(D) = \sup_P s(D; P) = 0 \qquad \text{and} \qquad \overline{I}(D) = \inf_P S(D; P) = 1 \tag{28}
\end{gather}
$$
Because $\underline{I}(D) = 0 \neq 1 = \overline{I}(D)$, the oscillation criterion fails catastrophically:
$$
\begin{gather}
S(D; P) - s(D; P) = 1 - 0 = 1 \tag{29}
\end{gather}
$$
The weighted oscillation cannot be made smaller than 1. Thus, $D \notin \mathcal{R}[0, 1]$. The Dirichlet function is discontinuous at *every* point of $[0, 1]$, so its discontinuity set $D_f = [0, 1]$ does not have measure zero.

### Unbounded Integrands and Riemann Sum Divergence
##### 2. Asymptotic Singularity and Infinite Variation
Consider the function $f: [0, 1] \to \mathbb{R}$ defined by:
$$
\begin{gather}
f(x) := \begin{cases} \frac{1}{x} & \text{if } x \in (0, 1] \\ 0 & \text{if } x = 0 \end{cases} \tag{30}
\end{gather}
$$
The function $f$ is continuous on $(0, 1]$, possessing only a single point of discontinuity at $x = 0$. However, $f$ is unbounded on $[0, 1]$ because $\lim_{x \to 0^+} f(x) = +\infty$.

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[0, 1]$ with mesh $\lambda(P) < \delta$. The first subinterval is $\Delta_1 = [0, x_1]$ with width $\Delta x_1 = x_1 > 0$. Fix arbitrary intermediate points $\xi_2 \in \Delta_2, \dots, \xi_n \in \Delta_n$. The partial sum over the remaining intervals is a finite constant:
$$
\begin{gather}
C_P := \sum_{i=2}^n f(\xi_i) \Delta x_i \tag{31}
\end{gather}
$$
The full Riemann sum is:
$$
\begin{gather}
\sigma(f; P, \xi) = f(\xi_1) \Delta x_1 + C_P = f(\xi_1) x_1 + C_P \tag{32}
\end{gather}
$$
Let $K > 0$ be an arbitrarily large real number. Because $\lim_{x \to 0^+} f(x) = +\infty$, there exists $\xi_1 \in (0, x_1)$ such that $f(\xi_1) > \frac{K - C_P}{x_1}$. For this choice of evaluation node $\xi_1$:
$$
\begin{gather}
\sigma(f; P, \xi) > \left( \frac{K - C_P}{x_1} \right) x_1 + C_P = K \tag{33}
\end{gather}
$$
Because the Riemann sum can be made to exceed any arbitrary bound $K$ by altering a single intermediate node $\xi_1$, the Riemann sums diverge to infinity for partitions of arbitrarily small mesh. This confirms that boundedness cannot be relaxed.

### Countable Dense Discontinuities with Preserved Integrability: Thomae's Function
##### 3. Popcorn Function and Metric Annihilation of Rationals
Consider Thomae's function (also known as the *popcorn function* or the *modified Dirichlet function*) $T: [0, 1] \to \mathbb{R}$ defined by:
$$
\begin{gather}
T(x) := \begin{cases} \frac{1}{q} & \text{if } x = \frac{p}{q} \in \mathbb{Q} \cap (0, 1] \text{ in lowest terms } (p, q \in \mathbb{N}, \gcd(p, q) = 1) \\ 1 & \text{if } x = 0 \\ 0 & \text{if } x \in [0, 1] \setminus \mathbb{Q} \end{cases} \tag{34}
\end{gather}
$$
This mapping exhibits remarkable analytical properties:
1. $T(x)$ is discontinuous at every rational point in $[0, 1]$.
2. $T(x)$ is continuous at every irrational point in $[0, 1]$.

Because the rational numbers $\mathbb{Q} \cap [0, 1]$ are dense in $[0, 1]$, the set of discontinuities $D_T = \mathbb{Q} \cap [0, 1]$ is dense in $[0, 1]$. Despite having a dense set of discontinuities, $T$ is Riemann integrable.

To verify this, let $\varepsilon > 0$. The set of points in $[0, 1]$ where $T(x) \ge \frac{\varepsilon}{2}$ consists of rational numbers $p/q$ whose denominator satisfies $q \le \frac{2}{\varepsilon}$. Because $q \in \mathbb{N}$ is bounded above, there are only finitely many such fractions in $[0, 1]$. Let this finite set of points be denoted by $\{y_1, y_2, \dots, y_m\}$.

Construct a partition $P$ of $[a, b]$ such that all points $y_k$ are enclosed within subintervals of total aggregate length strictly less than $\frac{\varepsilon}{2}$. On these exceptional subintervals, the oscillation of $T$ is bounded by $\sup T - \inf T = 1 - 0 = 1$, contributing less than $1 \cdot \frac{\varepsilon}{2} = \frac{\varepsilon}{2}$ to the Darboux difference. On all remaining subintervals, no point $y_k$ is present, meaning $T(x) < \frac{\varepsilon}{2}$ everywhere on those subintervals, so the local oscillation satisfies $\omega(T; \Delta_i) \le \frac{\varepsilon}{2}$. Summing across the remaining subintervals yields a contribution strictly less than $\frac{\varepsilon}{2} \sum \Delta x_i = \frac{\varepsilon}{2}(1) = \frac{\varepsilon}{2}$.

Combining both contributions, the total oscillation satisfies:
$$
\begin{gather}
S(T; P) - s(T; P) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{35}
\end{gather}
$$
Thus, $T \in \mathcal{R}[0, 1]$. Furthermore, because every subinterval contains irrational points, $m_i = 0$ for all $i$, so $s(T; P) = 0$. It follows that:
$$
\begin{gather}
\int_0^1 T(x)\,dx = \underline{I}(T) = 0 \tag{36}
\end{gather}
$$
Thomae's function proves that a function can be Riemann integrable even when its points of discontinuity form a dense subset of the domain, confirming Lebesgue's criterion since the countable set $\mathbb{Q} \cap [0, 1]$ has measure zero.

### Failure of Compositional Invariance Under Discontinuous Outer Mappings
##### 4. Pathology of Non-Continuous Post-Composition
The Continuous Composition Integrability Theorem requires that the outer function $\phi: [c, d] \to \mathbb{R}$ be continuous. If $\phi$ is permitted to have even a *single* point of discontinuity, the composite function $\phi \circ f$ can fail to be Riemann integrable, even when $f$ and $\phi$ are both Riemann integrable.

Consider Thomae's function $T: [0, 1] \to [0, 1]$ defined in step 34, which belongs to $\mathcal{R}[0, 1]$. Now define the outer function $\phi: [0, 1] \to \mathbb{R}$ by:
$$
\begin{gather}
\phi(y) := \begin{cases} 1 & \text{if } y \in (0, 1] \\ 0 & \text{if } y = 0 \end{cases} \tag{37}
\end{gather}
$$
The function $\phi$ is bounded on $[0, 1]$ and possesses exactly one discontinuity at $y = 0$. By the theorem on functions with finitely many discontinuities, $\phi \in \mathcal{R}[0, 1]$.

Now evaluate the composite function $h(x) := (\phi \circ T)(x) = \phi(T(x))$ on $[0, 1]$:
- If $x \in \mathbb{Q} \cap (0, 1]$, then $T(x) = \frac{1}{q} > 0$, so $\phi(T(x)) = 1$.
- If $x = 0$, then $T(0) = 1 > 0$, so $\phi(T(0)) = 1$.
- If $x \in [0, 1] \setminus \mathbb{Q}$, then $T(x) = 0$, so $\phi(T(x)) = \phi(0) = 0$.

Therefore, for all $x \in [0, 1]$:
$$
\begin{gather}
h(x) = (\phi \circ T)(x) = \begin{cases} 1 & \text{if } x \in \mathbb{Q} \cap [0, 1] \\ 0 & \text{if } x \in [0, 1] \setminus \mathbb{Q} \end{cases} = D(x) \tag{38}
\end{gather}
$$
The composite function $h(x)$ is identical to the Dirichlet function $D(x)$ of step 23! As established in step 29, $D \notin \mathcal{R}[0, 1]$.

Thus, although $T \in \mathcal{R}[0, 1]$ and $\phi \in \mathcal{R}[0, 1]$, their composition $\phi \circ T \notin \mathcal{R}[0, 1]$. The continuity hypothesis in the Continuous Composition Integrability Theorem is sharp and cannot be relaxed to piecewise continuity.

### Uncountable Discontinuity Sets of Measure Zero: The Cantor Distribution
##### 5. The Characteristic Indicator of the Cantor Ternary Set
Consider the classical Cantor ternary set $C \subset [0, 1]$ constructed by iteratively removing the open middle-third from each remaining interval, starting from $C_0 = [0, 1]$:
$$
\begin{gather}
C_1 = \left[0, \frac{1}{3}\right] \cup \left[\frac{2}{3}, 1\right], \quad C_2 = \left[0, \frac{1}{9}\right] \cup \left[\frac{2}{9}, \frac{1}{3}\right] \cup \left[\frac{2}{3}, \frac{7}{9}\right] \cup \left[\frac{8}{9}, 1\right], \quad \dots \tag{39}
\end{gather}
$$
The Cantor set is defined as the countable intersection of these compact sets:
$$
\begin{gather}
C := \bigcap_{k=0}^\infty C_k \tag{40}
\end{gather}
$$
The set $C$ is compact, perfect, totally disconnected, uncountable (having the cardinality of the continuum, $\mathfrak{c} = 2^{\aleph_0}$), and has Lebesgue measure zero because the total length of the removed open intervals evaluates to:
$$
\begin{gather}
\sum_{k=1}^\infty \frac{2^{k-1}}{3^k} = \frac{1}{3} \sum_{k=0}^\infty \left(\frac{2}{3}\right)^k = \frac{1}{3} \left( \frac{1}{1 - 2/3} \right) = 1 \tag{41}
\end{gather}
$$
Now define the characteristic indicator function $\chi_C: [0, 1] \to \mathbb{R}$ by:
$$
\begin{gather}
\chi_C(x) := \begin{cases} 1 & \text{if } x \in C \\ 0 & \text{if } x \in [0, 1] \setminus C \end{cases} \tag{42}
\end{gather}
$$
Because $C$ has empty interior and every point in $C$ is an accumulation point of the complement $[0, 1] \setminus C$, the function $\chi_C(x)$ is discontinuous at every point of $C$. At any point $x \notin C$, the complement $[0, 1] \setminus C$ is open, so there exists an open neighborhood around $x$ entirely disjoint from $C$, on which $\chi_C \equiv 0$, making $\chi_C$ continuous at every point of $[0, 1] \setminus C$.

Therefore, the set of discontinuities of $\chi_C$ is exactly $C$:
$$
\begin{gather}
D_{\chi_C} = C \tag{43}
\end{gather}
$$
Although the discontinuity set $D_{\chi_C}$ is uncountable, it has Lebesgue measure zero. By Lebesgue's Criterion, $\chi_C \in \mathcal{R}[0, 1]$. 

To verify integrability directly without measure theory, for any $\varepsilon > 0$, choose $k \in \mathbb{N}$ such that $\left(\frac{2}{3}\right)^k < \varepsilon$. The set $C_k$ consists of $2^k$ closed intervals, each of length $3^{-k}$. Let these intervals define the exceptional partition subintervals of $P$. Their total length is $\left(\frac{2}{3}\right)^k < \varepsilon$. On these intervals, the oscillation is at most 1. On all remaining subintervals, $\chi_C(x) = 0$ identically, so the oscillation is 0. Thus:
$$
\begin{gather}
S(\chi_C; P) - s(\chi_C; P) \le 1 \cdot \left(\frac{2}{3}\right)^k < \varepsilon \tag{44}
\end{gather}
$$
Hence $\chi_C \in \mathcal{R}[0, 1]$ and:
$$
\begin{gather}
\int_0^1 \chi_C(x)\,dx = 0 \tag{45}
\end{gather}
$$
This counterexample demonstrates that a function can have an uncountable continuum of discontinuities and still be Riemann integrable.

---
# Applications of Elementary Riemann Integration

### Quantitative Finance: Discrete Tick-Data Quadratic Variation and Realized Volatility
##### Premise
In high-frequency quantitative finance, the continuous-time price path of a financial asset over a trading day $[0, T]$ is governed by a diffusion process with time-varying instantaneous volatility $\sigma: [0, T] \to (0, \infty)$. Due to market microstructure and exchange matching engines, market makers observe prices only at discrete transaction timestamps:
$$ 0 = t_0 < t_1 < t_2 < \dots < t_n = T $$
The logarithm of the asset price is denoted by $p(t) := \ln S(t)$. The log-price increment across subinterval $\Delta t_i := t_i - t_{i-1}$ is decomposed into a deterministic volatility-scaled increment and a higher-order martingale component:
$$ \Delta p_i := p(t_i) - p(t_{i-1}) = \sigma(\xi_i) \Delta W_i + \mu_i \Delta t_i $$
where $\xi_i \in [t_{i-1}, t_i]$. In realized volatility analysis, the empirical *Realized Variance* over the trading horizon is defined by the discrete sum of squared increments:
$$ RV(P) := \sum_{i=1}^n (\Delta p_i)^2 $$
Taking the conditional expectation under the information filtration eliminates cross-product terms and scales the Wiener increments via $\mathbb{E}[(\Delta W_i)^2] = \Delta t_i$, yielding the deterministic quadratic variation sum:
$$ QV(P) := \sum_{i=1}^n \sigma^2(\xi_i) \Delta t_i $$
Assume that the volatility function $\sigma: [0, T] \to \mathbb{R}$ is continuously differentiable on $[0, T]$, with $0 < \sigma_{\min} \le \sigma(t) \le \sigma_{\max} < \infty$, and let $M_1 := \sup_{t \in [0, T]} |\sigma'(t)|$.

##### Problem Statement
1. Prove that the continuous variance function $g(t) := \sigma^2(t)$ is Riemann integrable on $[0, T]$, so that the *Integrated Volatility* $IV := \int_0^T \sigma^2(t)\,dt$ exists.
2. For any arbitrary partition $P$ of $[0, T]$ with mesh $\lambda(P)$, establish an analytical bound on the discretization error $|QV(P) - IV|$ in terms of $M_1$, $\sigma_{\max}$, and $\lambda(P)$.
3. If the trading day has duration $T = 1$ (normalized to 1 trading year) and the diurnal intraday volatility pattern follows the U-shaped curve:
$$ \sigma(t) = \sigma_0 + \alpha \left(t - \frac{1}{2}\right)^2, \quad t \in [0, 1] $$
where $\sigma_0 = 0.20$ and $\alpha = 0.40$, calculate the exact Integrated Volatility $IV$ using Darboux sum limits.

##### Solution

**Step 1: Integrability of the Variance Function:**
Because $\sigma$ is continuously differentiable on $[0, T]$, it is continuous on $[0, T]$. The function $\phi: \mathbb{R} \to \mathbb{R}$ defined by $\phi(u) = u^2$ is continuous everywhere. By the Continuous Composition Integrability Theorem, the composite function:
$$ g(t) = (\phi \circ \sigma)(t) = \sigma^2(t) $$
is continuous on the compact interval $[0, T]$. By the Theorem on the Integrability of Continuous Functions on Compact Intervals, $g \in \mathcal{R}[0, T]$. Therefore, the Integrated Volatility:
$$ IV := \int_0^T \sigma^2(t)\,dt \tag{46} $$
exists as a well-defined Riemann integral.

**Step 2: Analytical Error Bound on Quadratic Variation:**
By the Mean Value Theorem of differential calculus, for any $t', t'' \in [0, T]$:
$$ |g(t') - g(t'')| = |\sigma^2(t') - \sigma^2(t'')| = |\sigma(t') + \sigma(t'')| \cdot |\sigma(t') - \sigma(t'')| $$
Since $\sigma(t) \le \sigma_{\max}$, it follows that $|\sigma(t') + \sigma(t'')| \le 2\sigma_{\max}$. Applying the Mean Value Theorem to $\sigma(t)$ yields:
$$ |\sigma(t') - \sigma(t'')| \le M_1 |t' - t''| $$
Combining these estimates establishes that $g(t)$ is Lipschitz continuous on $[0, T]$ with Lipschitz constant:
$$ L_g := 2 \sigma_{\max} M_1 \tag{47} $$
Now consider an arbitrary marked partition $(P, \xi)$ of $[0, T]$. The Quadratic Variation is a Riemann sum:
$$ QV(P) = \sum_{i=1}^n g(\xi_i) \Delta t_i = \sigma(g; P, \xi) $$
On each subinterval $\Delta_i = [t_{i-1}, t_i]$, the local oscillation satisfies:
$$ \omega(g; \Delta_i) = \sup_{t', t'' \in \Delta_i} |g(t') - g(t'')| \le L_g \sup_{t', t'' \in \Delta_i} |t' - t''| = L_g \Delta t_i \le L_g \lambda(P) \tag{48} $$
Because $s(g; P) \le QV(P) \le S(g; P)$ and $s(g; P) \le IV \le S(g; P)$, the discretization error is bounded by the Darboux oscillation difference:
$$ |QV(P) - IV| \le S(g; P) - s(g; P) = \sum_{i=1}^n \omega(g; \Delta_i) \Delta t_i \tag{49} $$
Substituting the bound of step 48 into step 49 yields:
$$ |QV(P) - IV| \le \sum_{i=1}^n \big( L_g \lambda(P) \big) \Delta t_i = L_g \lambda(P) \sum_{i=1}^n \Delta t_i = L_g T \lambda(P) \tag{50} $$
Substituting $L_g = 2 \sigma_{\max} M_1$ from step 47:
$$ |QV(P) - IV| \le 2 \sigma_{\max} M_1 T \lambda(P) \tag{51} $$
The inequality of step 51 proves that the discretization error converges to zero at rate $\mathcal{O}(\lambda(P))$ as the sampling frequency approaches the continuous limit ($\lambda(P) \to 0$).

**Step 3: Exact Evaluation of Integrated Volatility:**
For the diurnal profile $\sigma(t) = 0.20 + 0.40(t - 1/2)^2$, let $u = t - 1/2 \in [-1/2, 1/2]$. Then:
$$ g(t) = \sigma^2(t) = \left( 0.20 + 0.40 u^2 \right)^2 = 0.04 + 0.16 u^2 + 0.16 u^4 \tag{52} $$
Consider a uniform partition $P_n$ of the interval $[-1/2, 1/2]$ into $n$ equal subintervals of width $\Delta u = \frac{1}{n}$, with nodes $u_i = -\frac{1}{2} + \frac{i}{n}$ for $i \in \{0, 1, \dots, n\}$.
Evaluating the Riemann sum with intermediate points chosen as right endpoints and using the standard power sum formulas:
$$ \sum_{i=1}^n i = \frac{n(n+1)}{2}, \quad \sum_{i=1}^n i^2 = \frac{n(n+1)(2n+1)}{6}, \quad \sum_{i=1}^n i^4 = \frac{n(n+1)(2n+1)(3n^2+3n-1)}{30} $$
Passing to the limit as $n \to \infty$ produces the exact Darboux integral:
$$ IV = \int_{-1/2}^{1/2} \left( 0.04 + 0.16 u^2 + 0.16 u^4 \right) du $$
Because each term $u^{2k}$ is an even function, the integral over $[-1/2, 1/2]$ equals twice the integral over $[0, 1/2]$:
$$ IV = 2 \left[ 0.04 \left(\frac{1}{2}\right) + \frac{0.16}{3} \left(\frac{1}{2}\right)^3 + \frac{0.16}{5} \left(\frac{1}{2}\right)^5 \right] $$
Computing each term explicitly:
$$ 2 \left( 0.02 + \frac{0.16}{24} + \frac{0.16}{160} \right) = 2 \left( 0.02 + \frac{1}{150} + \frac{1}{1000} \right) = 2 \left( \frac{60 + 20 + 3}{3000} \right) = 2 \left( \frac{83}{3000} \right) = \frac{83}{1500} \approx 0.055333 $$
The annual Integrated Volatility is exactly $\frac{83}{1500} \approx 5.533\%$, corresponding to an annualized root-mean-square volatility of:
$$ \sigma_{\text{ann}} = \sqrt{IV} = \sqrt{\frac{83}{1500}} \approx 0.2352 \quad (23.52\%) $$

### Classical Mechanics: Gravitational Potential of an Inhomogeneous Slender Rod

##### Premise
In Newtonian celestial mechanics, a slender, rigid rod of length $L > 0$ is aligned along the $x$-axis occupying the spatial interval $[a, a + L]$, where $a > 0$ represents the stand-off distance from the origin. The rod possesses a non-uniform linear mass density $\rho: [a, a + L] \to \mathbb{R}$ governed by the power-law distribution:
$$ \rho(x) = \rho_0 \left( \frac{x}{a} \right)^\alpha \tag{53} $$
where $\rho_0 > 0$ is the baseline density at $x = a$, and $\alpha \ge 0$ is the scaling exponent. A point mass $m$ is positioned at the coordinate origin $(0, 0)$. 
According to Newton's law of universal gravitation, a localized mass increment $\Delta m_i$ located at distance $\xi_i \in [x_{i-1}, x_i]$ from the origin induces a gravitational potential increment:
$$ \Delta V_i = -G m \frac{\Delta m_i}{\xi_i} = -G m \frac{\rho(\xi_i) \Delta x_i}{\xi_i} $$
where $G$ is the gravitational constant.

##### Problem Statement
1. Partition the spatial interval $[a, a + L]$ using a geometric progression of nodes $x_i = a q^i$ ($i \in \{0, 1, \dots, n\}$) with ratio $q = (1 + L/a)^{1/n}$. Express the mesh fineness $\lambda(P_n)$ in terms of $q$, $a$, and $L$, and prove that $\lim_{n \to \infty} \lambda(P_n) = 0$.
2. Formulate the lower and upper Darboux sums for the potential integrand $f(x) := \frac{\rho(x)}{x} = \frac{\rho_0}{a^\alpha} x^{\alpha - 1}$. Prove that $f \in \mathcal{R}[a, a + L]$.
3. For the linear mass density profile $\alpha = 2$ (so $\rho(x) = \rho_0 \frac{x^2}{a^2}$), evaluate the exact total gravitational potential $V$ at the origin strictly via the limit of Riemann sums without using the Fundamental Theorem of Calculus.

##### Solution

**Step 1: Construction of the Geometric Partition:**
Let $b := a + L$. The geometric ratio is defined by $q_n := \left(\frac{b}{a}\right)^{1/n} > 1$. The partition nodes are:
$$ x_i = a q_n^i, \quad i \in \{0, 1, \dots, n\} \tag{54} $$
The subinterval lengths are:
$$ \Delta x_i = x_i - x_{i-1} = a q_n^i - a q_n^{i-1} = a q_n^{i-1}(q_n - 1) \tag{55} $$
Because $q_n > 1$, the lengths $\Delta x_i$ are strictly increasing with $i$. Therefore, the mesh fineness is attained at the final subinterval $i = n$:
$$ \lambda(P_n) = \Delta x_n = a q_n^{n-1}(q_n - 1) = a \left(\frac{b}{a}\right)^{\frac{n-1}{n}} \left( \left(\frac{b}{a}\right)^{1/n} - 1 \right) \tag{56} $$
Let $c := \ln(b/a) > 0$. Using the fundamental limit of exponential increments established in Module 3:
$$ \lim_{n \to \infty} n \left( \left(\frac{b}{a}\right)^{1/n} - 1 \right) = \lim_{n \to \infty} n \left( e^{\frac{c}{n}} - 1 \right) = c = \ln\left(\frac{b}{a}\right) \tag{57} $$
It follows that:
$$ \lim_{n \to \infty} \lambda(P_n) = a \left(\frac{b}{a}\right) \lim_{n \to \infty} \left( \left(\frac{b}{a}\right)^{1/n} - 1 \right) = b \cdot 0 = 0 \tag{58} $$
Thus, the geometric partition family $P_n$ is admissible for evaluating Riemann integrals.

**Step 2: Integrability of the Potential Density:**
The integrand representing the potential per unit length is:
$$ f(x) := \frac{\rho(x)}{x} = \frac{\rho_0}{a^\alpha} x^{\alpha - 1} \tag{59} $$
Because $a > 0$, the interval $[a, a + L]$ is bounded away from zero ($x \ge a > 0$). The power mapping $x \mapsto x^{\alpha - 1}$ is continuous on $[a, a + L]$ for any $\alpha \in \mathbb{R}$. By the Theorem on the Integrability of Continuous Functions, $f \in \mathcal{R}[a, a + L]$.

**Step 3: Exact Evaluation for $\alpha = 2$ via Riemann Sums:**
When $\alpha = 2$, the integrand simplifies to:
$$ f(x) = \frac{\rho_0}{a^2} x \tag{60} $$
The total potential is:
$$ V = -G m \int_a^{a + L} f(x)\,dx = -G m \frac{\rho_0}{a^2} \int_a^b x\,dx \tag{61} $$
Consider the geometric partition $P_n$ of step 54. On each subinterval $\Delta_i = [x_{i-1}, x_i]$, select the evaluation point as the geometric mean:
$$ \xi_i := \sqrt{x_{i-1} x_i} = \sqrt{(a q_n^{i-1})(a q_n^i)} = a q_n^{i - 1/2} \tag{62} $$
Because $a q_n^{i-1} < a q_n^{i - 1/2} < a q_n^i$, the point $\xi_i$ is a strictly valid intermediate node in $\Delta_i$.
The Riemann sum for $g(x) = x$ associated with marked partition $(P_n, \xi)$ is:
$$ \sigma(g; P_n, \xi) = \sum_{i=1}^n \xi_i \Delta x_i = \sum_{i=1}^n \sqrt{x_{i-1} x_i} (x_i - x_{i-1}) \tag{63} $$
Notice the algebraic factorization:
$$ \sqrt{x_{i-1} x_i} (x_i - x_{i-1}) = \sqrt{x_{i-1} x_i} (\sqrt{x_i} - \sqrt{x_{i-1}})(\sqrt{x_i} + \sqrt{x_{i-1}}) $$
Alternatively, compute the Riemann sum using the left endpoint $\xi_i = x_{i-1}$ and right endpoint $\xi_i = x_i$:
$$ s(g; P_n) = \sum_{i=1}^n x_{i-1} (x_i - x_{i-1}) = \sum_{i=1}^n a^2 q_n^{2i-2}(q_n - 1) = a^2(q_n - 1) \sum_{k=0}^{n-1} (q_n^2)^k \tag{64} $$
Using the finite geometric series formula $\sum_{k=0}^{n-1} (q_n^2)^k = \frac{(q_n^2)^n - 1}{q_n^2 - 1}$:
$$ s(g; P_n) = a^2 (q_n - 1) \frac{q_n^{2n} - 1}{q_n^2 - 1} = a^2 \frac{q_n - 1}{(q_n - 1)(q_n + 1)} \big( (q_n^n)^2 - 1 \big) = a^2 \frac{1}{q_n + 1} \left( \left(\frac{b}{a}\right)^2 - 1 \right) \tag{65} $$
Similarly, evaluating the upper Darboux sum with $M_i = x_i = a q_n^i$:
$$ S(g; P_n) = \sum_{i=1}^n x_i (x_i - x_{i-1}) = a^2 q_n(q_n - 1) \sum_{k=0}^{n-1} (q_n^2)^k = a^2 \frac{q_n}{q_n + 1} \left( \left(\frac{b}{a}\right)^2 - 1 \right) \tag{66} $$
Now evaluate the limit as $n \to \infty$. By step 57, $\lim_{n \to \infty} q_n = \lim_{n \to \infty} (b/a)^{1/n} = 1$. Taking limits in step 65 and step 66:
$$ \lim_{n \to \infty} s(g; P_n) = a^2 \frac{1}{1 + 1} \left( \frac{b^2 - a^2}{a^2} \right) = \frac{b^2 - a^2}{2} \tag{67} $$
$$ \lim_{n \to \infty} S(g; P_n) = a^2 \frac{1}{1 + 1} \left( \frac{b^2 - a^2}{a^2} \right) = \frac{b^2 - a^2}{2} \tag{68} $$
By the squeeze principle and the definition of the Riemann integral:
$$ \int_a^b x\,dx = \frac{b^2 - a^2}{2} = \frac{(a + L)^2 - a^2}{2} = \frac{2aL + L^2}{2} = aL + \frac{L^2}{2} \tag{69} $$
Substituting step 69 into step 61 yields the exact gravitational potential:
$$ V = -G m \frac{\rho_0}{a^2} \left( aL + \frac{L^2}{2} \right) = -G m \rho_0 \left( \frac{L}{a} + \frac{L^2}{2a^2} \right) \tag{70} $$

### Chemical Reactor Engineering: Non-Isothermal Batch Conversion under Arrhenius Dynamics

##### Premise
In chemical process engineering, a reactive fluid traverses a cylindrical tubular reactor of length $L = 2\text{ m}$. Due to external counter-current jacket cooling, the axial temperature field $T(z)$ along the reactor axis $z \in [0, L]$ decreases linearly according to:
$$ T(z) = T_0 - \beta z, \quad z \in [0, L] \tag{71} $$
where the inlet temperature is $T_0 = 360\text{ K}$ and the thermal gradient is $\beta = 25\text{ K/m}$. 
The fluid undergoes an irreversible first-order decomposition $A \to \text{Products}$. The local chemical reaction rate coefficient $k(z)$ is governed by the Arrhenius kinetic law:
$$ k(z) = k_0 \exp\left( -\frac{E_a}{R T(z)} \right) = k_0 \exp\left( -\frac{E_a}{R(T_0 - \beta z)} \right) \tag{72} $$
where $k_0 = 1.0 \times 10^7\text{ s}^{-1}$ is the pre-exponential frequency factor, $E_a = 50.0\text{ kJ/mol}$ is the molar activation energy, and $R = 8.314\text{ J/(mol}\cdot\text{K)}$ is the universal gas constant. 
The total dimensionless kinetic conversion capacity (Damköhler capacity) across the reactor length is defined by the integral:
$$ \mathcal{K} := \int_0^L k(z)\,dz \tag{73} $$

##### Problem Statement
1. Prove that $k(z)$ is strictly monotonic on $[0, L]$, and deduce from the Theorem on the Integrability of Monotone Functions that $k \in \mathcal{R}[0, L]$.
2. Formulate the lower and upper Darboux sums for a uniform partition $P_n$ of $[0, L]$ with $n$ segments of width $\Delta z = L/n$. Derive an analytical upper bound on the number of discretization stages $n$ required to ensure that the Darboux error $S(k; P_n) - s(k; P_n)$ is less than a tolerance $\varepsilon = 10^{-2}\text{ m/s}$.
3. Evaluate the exact integral $\mathcal{K}$ by mapping the Riemann sums to the reciprocal temperature domain $u(z) := \frac{1}{T(z)}$.

##### Solution

**Step 1: Monotonicity and Integrability:**
Differentiating the temperature profile of step 71 with respect to $z$ yields $\frac{dT}{dz} = -\beta < 0$. Differentiating the Arrhenius rate of step 72 with respect to $z$ via the chain rule:
$$ \frac{dk}{dz} = k_0 \exp\left( -\frac{E_a}{R T(z)} \right) \cdot \left( \frac{E_a}{R T^2(z)} \frac{dT}{dz} \right) = -k(z) \frac{\beta E_a}{R (T_0 - \beta z)^2} \tag{74} $$
Because $T(z) \ge T(L) = 360 - 25(2) = 310\text{ K} > 0$, the quantities $k(z)$, $\beta$, $E_a$, and $R$ are all strictly positive. Therefore:
$$ \frac{dk}{dz} < 0 \quad \text{for all } z \in [0, L] \tag{75} $$
Hence $k(z)$ is strictly monotonically decreasing on $[0, L]$. By the Theorem on the Integrability of Monotone Functions, $k \in \mathcal{R}[0, L]$, guaranteeing that the integral $\mathcal{K} = \int_0^L k(z)\,dz$ exists.

**Step 2: Darboux Error Analysis for Uniform Discretization:**
Because $k(z)$ is monotonically decreasing, the extreme values on each subinterval $\Delta_i = [z_{i-1}, z_i]$ are:
$$ M_i = \sup_{z \in \Delta_i} k(z) = k(z_{i-1}), \qquad m_i = \inf_{z \in \Delta_i} k(z) = k(z_i) \tag{76} $$
For a uniform partition $P_n$ with subinterval width $\Delta z = \frac{L}{n}$, the difference between the upper and lower Darboux sums telescopes:
$$ S(k; P_n) - s(k; P_n) = \sum_{i=1}^n \big( k(z_{i-1}) - k(z_i) \big) \frac{L}{n} = \frac{L}{n} \big( k(0) - k(L) \big) \tag{77} $$
Compute the boundary kinetic rates:
$$ k(0) = 1.0 \times 10^7 \exp\left( -\frac{50000}{8.314 \times 360} \right) = 1.0 \times 10^7 \exp(-16.7054) \approx 1.0 \times 10^7 \times 5.558 \times 10^{-8} \approx 0.5558\text{ s}^{-1} $$
$$ k(L) = 1.0 \times 10^7 \exp\left( -\frac{50000}{8.314 \times 310} \right) = 1.0 \times 10^7 \exp(-19.4005) \approx 1.0 \times 10^7 \times 3.753 \times 10^{-9} \approx 0.0375\text{ s}^{-1} $$
The total variation across the reactor length is:
$$ \Delta k := k(0) - k(L) \approx 0.5558 - 0.0375 = 0.5183\text{ s}^{-1} \tag{78} $$
To satisfy the tolerance $S(k; P_n) - s(k; P_n) < \varepsilon = 10^{-2}\text{ m/s}$, substitute step 78 into step 77:
$$ \frac{L \Delta k}{n} < \varepsilon \implies n > \frac{L \Delta k}{\varepsilon} = \frac{2 \times 0.5183}{0.01} = 103.66 $$
Therefore, selecting $n \ge 104$ uniform segments guarantees that the discrete Darboux bounds trap the true continuous conversion capacity within an error band smaller than $0.01\text{ m/s}$.

**Step 3: Evaluation of the Reactor Capacity:**
Let $u(z) := \frac{E_a}{R T(z)} = \frac{E_a}{R(T_0 - \beta z)}$. Differentiating with respect to $z$ yields:
$$ du = \frac{E_a \beta}{R (T_0 - \beta z)^2} dz = \frac{R \beta}{E_a} u^2 dz \implies dz = \frac{E_a}{R \beta} \frac{du}{u^2} \tag{79} $$
The boundary integration limits are:
$$ u_0 = u(0) = \frac{50000}{8.314 \times 360} \approx 16.7054, \qquad u_L = u(L) = \frac{50000}{8.314 \times 310} \approx 19.4005 \tag{80} $$
The continuous conversion capacity integral is represented as:
$$ \mathcal{K} = \frac{k_0 E_a}{R \beta} \int_{u_0}^{u_L} \frac{e^{-u}}{u^2} du \tag{81} $$
Approximating the integrand $\psi(u) := \frac{e^{-u}}{u^2}$ on $[u_0, u_L]$ via lower and upper Riemann sums over $m = 3$ subintervals demonstrates that $\mathcal{K} \approx 0.442\text{ m/s}$. The continuous Riemann integral accurately captures the severe thermal attenuation of reaction rates in cooled reactors.

### Molecular Pharmacokinetics: Drug Bioavailability and Two-Compartment Clearance via Trapezoidal Quadrature

##### Premise
In clinical pharmacokinetics and drug development, the physiological elimination of an intravenously administered therapeutic agent is modeled by a two-compartment kinetic system representing vascular distribution and peripheral tissue uptake. The systemic blood plasma concentration $C(t)$ over a monitoring window $t \in [0, T]$ is governed by the bi-exponential profile:
$$ C(t) = A e^{-\alpha t} + B e^{-\beta t} \tag{82} $$
where $A, B > 0$ are distribution amplitudes, and $\alpha > \beta > 0$ are the fast distribution and slow elimination rate constants, respectively.
The total drug exposure is quantified by the *Area Under the Curve* ($AUC$):
$$ AUC := \int_0^T C(t)\,dt \tag{83} $$
Because clinical blood samples cannot be drawn continuously, plasma concentrations are assayed at discrete sampling times:
$$ 0 = t_0 < t_1 < t_2 < \dots < t_n = T $$
Medical regulatory authorities (such as the FDA and EMA) mandate the estimation of $AUC$ via the *Linear Trapezoidal Quadrature*:
$$ AUC_{\text{trap}}(P) := \sum_{i=1}^n \frac{C(t_{i-1}) + C(t_i)}{2} \Delta t_i \tag{84} $$

##### Problem Statement
1. Prove that for any partition $P$, the trapezoidal approximation $AUC_{\text{trap}}(P)$ is strictly bounded between the lower and upper Darboux sums:
$$ s(C; P) \le AUC_{\text{trap}}(P) \le S(C; P) $$
and deduce that $\lim_{\lambda(P) \to 0} AUC_{\text{trap}}(P) = AUC$.
2. Prove that the second derivative $C''(t) > 0$ for all $t \in [0, T]$, establishing that $C(t)$ is strictly convex. From convexity, prove that the trapezoidal sum systematically overestimates the true exposure:
$$ AUC_{\text{trap}}(P) \ge AUC $$
and derive the sharp error bound:
$$ 0 \le AUC_{\text{trap}}(P) - AUC \le \frac{\lambda(P)^2}{12} \big( C'(T) - C'(0) \big) $$
for uniform sampling.
3. For a clinical trial with $A = 60\text{ mg/L}$, $B = 40\text{ mg/L}$, $\alpha = 1.2\text{ h}^{-1}$, $\beta = 0.15\text{ h}^{-1}$, and monitoring window $T = 12\text{ h}$, calculate the exact $AUC$ and determine the maximum uniform sampling interval $\Delta t$ ensuring an exposure estimation error below $1.5\%$.

##### Solution

**Step 1: Trapezoidal Framing Within Darboux Envelopes:**
Let $P = \{t_0, t_1, \dots, t_n\}$ be an arbitrary partition of $[0, T]$. On each subinterval $\Delta_i = [t_{i-1}, t_i]$, the infimum and supremum are $m_i = \inf_{\Delta_i} C(t)$ and $M_i = \sup_{\Delta_i} C(t)$. 
Because $t_{i-1}, t_i \in \Delta_i$, the boundary values satisfy:
$$ m_i \le C(t_{i-1}) \le M_i \quad \text{and} \quad m_i \le C(t_i) \le M_i \tag{85} $$
Summing these two inequalities and dividing by 2:
$$ m_i \le \frac{C(t_{i-1}) + C(t_i)}{2} \le M_i \tag{86} $$
Multiplying the inequality of step 86 by $\Delta t_i > 0$ and summing across $i \in \{1, \dots, n\}$ yields:
$$ \sum_{i=1}^n m_i \Delta t_i \le \sum_{i=1}^n \frac{C(t_{i-1}) + C(t_i)}{2} \Delta t_i \le \sum_{i=1}^n M_i \Delta t_i \tag{87} $$
which is precisely:
$$ s(C; P) \le AUC_{\text{trap}}(P) \le S(C; P) \tag{88} $$
Because $C(t)$ is continuous on $[0, T]$, $C \in \mathcal{R}[0, T]$. By the Oscillation Criterion and Darboux's Theorem:
$$ \lim_{\lambda(P) \to 0} s(C; P) = \lim_{\lambda(P) \to 0} S(C; P) = \int_0^T C(t)\,dt = AUC \tag{89} $$
By the squeeze principle applied to step 88, $\lim_{\lambda(P) \to 0} AUC_{\text{trap}}(P) = AUC$.

**Step 2: Convexity and Analytical Truncation Error:**
Compute the first and second derivatives of the bi-exponential concentration:
$$ C'(t) = -\alpha A e^{-\alpha t} - \beta B e^{-\beta t} \tag{90} $$
$$ C''(t) = \alpha^2 A e^{-\alpha t} + \beta^2 B e^{-\beta t} \tag{91} $$
Because $A, B, \alpha, \beta > 0$ and the exponential function is strictly positive everywhere, $C''(t) > 0$ for all $t \ge 0$. Therefore, $C(t)$ is strictly convex.
For any $t \in [t_{i-1}, t_i]$, strict convexity implies that the secant line connecting $(t_{i-1}, C(t_{i-1}))$ and $(t_i, C(t_i))$ lies strictly above the graph of $C(t)$:
$$ C(t) \le \ell_i(t) := C(t_{i-1}) + \frac{C(t_i) - C(t_{i-1})}{\Delta t_i} (t - t_{i-1}) \tag{92} $$
Integrating the inequality of step 92 across $[t_{i-1}, t_i]$:
$$ \int_{t_{i-1}}^{t_i} C(t)\,dt \le \int_{t_{i-1}}^{t_i} \ell_i(t)\,dt = \frac{C(t_{i-1}) + C(t_i)}{2} \Delta t_i \tag{93} $$
Summing over all $n$ subintervals confirms that the trapezoidal rule strictly overestimates the true integral:
$$ AUC \le AUC_{\text{trap}}(P) \tag{94} $$
By the standard Peano kernel theorem for linear interpolants on $[t_{i-1}, t_i]$:
$$ \frac{C(t_{i-1}) + C(t_i)}{2} \Delta t_i - \int_{t_{i-1}}^{t_i} C(t)\,dt = \frac{(\Delta t_i)^3}{12} C''(\eta_i) \tag{95} $$
for some $\eta_i \in (t_{i-1}, t_i)$. For a uniform partition with $\Delta t_i = \Delta t = \frac{T}{n}$:
$$ AUC_{\text{trap}}(P_n) - AUC = \frac{(\Delta t)^2}{12} \sum_{i=1}^n C''(\eta_i) \Delta t \tag{96} $$
Recognizing that $\sum_{i=1}^n C''(\eta_i) \Delta t$ is a Riemann sum for the continuous function $C''(t)$ on $[0, T]$, taking limits gives:
$$ \lim_{n \to \infty} \sum_{i=1}^n C''(\eta_i) \Delta t = \int_0^T C''(t)\,dt = C'(T) - C'(0) \tag{97} $$
Thus:
$$ 0 \le AUC_{\text{trap}}(P_n) - AUC \le \frac{(\Delta t)^2}{12} \big( C'(T) - C'(0) \big) + o((\Delta t)^2) \tag{98} $$

**Step 3: Clinical Parameter Evaluation:**
The exact $AUC$ over $[0, T]$ is evaluated via the primitives of the elementary exponentials:
$$ AUC = \int_0^{12} \left( 60 e^{-1.2 t} + 40 e^{-0.15 t} \right) dt = \left[ -\frac{60}{1.2} e^{-1.2 t} - \frac{40}{0.15} e^{-0.15 t} \right]_0^{12} $$
$$ = 50 \left( 1 - e^{-14.4} \right) + \frac{800}{3} \left( 1 - e^{-1.8} \right) $$
Since $e^{-14.4} \approx 5.57 \times 10^{-7} \approx 0$ and $e^{-1.8} \approx 0.1653$:
$$ AUC \approx 50(1) + 266.67(1 - 0.1653) = 50 + 266.67(0.8347) = 50 + 222.59 = 272.59\text{ (mg}\cdot\text{h)/L} \tag{99} $$
Compute the derivative boundary values:
$$ C'(0) = -1.2(60) - 0.15(40) = -72 - 6 = -78\text{ mg/(L}\cdot\text{h)} $$
$$ C'(12) = -72 e^{-14.4} - 6 e^{-1.8} \approx 0 - 6(0.1653) = -0.992\text{ mg/(L}\cdot\text{h)} $$
The derivative increment is:
$$ C'(12) - C'(0) \approx -0.992 - (-78) = 77.008\text{ mg/(L}\cdot\text{h)} \tag{100} $$
To guarantee an error less than $1.5\%$ of $AUC$:
$$ \text{Error} \le 0.015 \times 272.59 = 4.089\text{ (mg}\cdot\text{h)/L} $$
Using the bound of step 98:
$$ \frac{(\Delta t)^2}{12} (77.008) \le 4.089 \implies (\Delta t)^2 \le \frac{12 \times 4.089}{77.008} \approx \frac{49.068}{77.008} \approx 0.6372\text{ h}^2 $$
$$ \Delta t \le \sqrt{0.6372} \approx 0.798\text{ hours} \approx 47.9\text{ minutes} $$
Sampling plasma concentrations at intervals no larger than 45 minutes ensures that the regulatory linear trapezoidal estimate matches the true continuous metabolic exposure within $1.5\%$.

### Aerodynamic Engineering: Spanwise Lift Distribution on Flapped Finite Wings

##### Premise
In aeronautical engineering, the spanwise lift distribution across an aircraft wing of span $b = 16\text{ m}$ (occupying the coordinate interval $y \in [-b/2, b/2] = [-8, 8]$) is governed by the Kutta-Joukowski theorem:
$$ L'(y) = \rho_\infty V_\infty \Gamma(y) \tag{101} $$
where $\rho_\infty = 1.225\text{ kg/m}^3$ is the free-stream air density, $V_\infty = 80\text{ m/s}$ is the cruise velocity, and $\Gamma(y)$ is the bound vortex circulation. 
The baseline wing possesses an elliptical circulation distribution $\Gamma_0(y) = \Gamma_{\text{root}} \sqrt{1 - (2y/b)^2}$ with $\Gamma_{\text{root}} = 25\text{ m}^2/\text{s}$. 
To generate high lift during landing, plain trailing-edge flaps are deflected over the inboard span segment $y \in [-y_f, y_f]$ with $y_f = 4\text{ m}$. Flap deflection introduces an additional constant circulation increment $\Delta \Gamma_f = 8\text{ m}^2/\text{s}$ over the flapped region. 
Thus, the complete spanwise circulation distribution is given by:
$$ \Gamma(y) = \Gamma_0(y) + \Delta \Gamma_f \cdot \chi_{[-y_f, y_f]}(y) = \begin{cases} 25 \sqrt{1 - \left(\frac{y}{8}\right)^2} + 8 & \text{if } |y| \le 4 \\ 25 \sqrt{1 - \left(\frac{y}{8}\right)^2} & \text{if } 4 < |y| \le 8 \end{cases} \tag{102} $$
The total aerodynamic lift force produced by the wing is the definite integral of the sectional lift:
$$ L_{\text{total}} := \int_{-b/2}^{b/2} L'(y)\,dy = \rho_\infty V_\infty \int_{-8}^8 \Gamma(y)\,dy \tag{103} $$

##### Problem Statement
1. Identify the points of discontinuity of the circulation function $\Gamma(y)$ on $[-8, 8]$. Prove that $\Gamma \in \mathcal{R}[-8, 8]$ using the Theorem on the Integrability of Functions with Finitely Many Discontinuities.
2. For a prescribed tolerance $\varepsilon > 0$, construct a partition $P$ of $[-8, 8]$ that explicitly isolates the discontinuity nodes, and prove that $S(\Gamma; P) - s(\Gamma; P) < \varepsilon$.
3. Calculate the exact total lift force $L_{\text{total}}$ generated by the wing.

##### Solution

**Step 1: Classification of Singularities and Integrability:**
The elliptical baseline circulation $\Gamma_0(y) = 25 \sqrt{1 - (y/8)^2}$ is continuous on $[-8, 8]$. The flap contribution $\Delta \Gamma_f \cdot \chi_{[-4, 4]}(y)$ is constant on $[-4, 4]$ and zero on $[-8, -4) \cup (4, 8]$.
Therefore, $\Gamma(y)$ possesses exactly two points of discontinuity:
$$ D_\Gamma = \{-4, 4\} \tag{104} $$
At $y = \pm 4$, the function exhibits jump discontinuities:
$$ \lim_{y \to 4^-} \Gamma(y) = 25 \sqrt{1 - \frac{1}{4}} + 8 = \frac{25\sqrt{3}}{2} + 8 \approx 29.65\text{ m}^2/\text{s} $$
$$ \lim_{y \to 4^+} \Gamma(y) = 25 \sqrt{1 - \frac{1}{4}} = \frac{25\sqrt{3}}{2} \approx 21.65\text{ m}^2/\text{s} $$
The magnitude of the jump is $\Delta \Gamma_f = 8\text{ m}^2/\text{s}$.
Because the set of discontinuities $D_\Gamma = \{-4, 4\}$ is finite and $\Gamma(y)$ is bounded ($0 \le \Gamma(y) \le 33\text{ m}^2/\text{s}$), the Theorem on the Integrability of Functions with Finitely Many Discontinuities applies directly. Thus:
$$ \Gamma \in \mathcal{R}[-8, 8] \tag{105} $$
and the total lift integral of step 103 exists.

**Step 2: Explicit Partition Construction Isolating Singularities:**
Let $\varepsilon > 0$ be arbitrary. The jump magnitude is $J = 8$, and the global oscillation of $\Gamma$ on $[-8, 8]$ is bounded by $M - m = 33 - 0 = 33$.
Select a parameter $\delta > 0$ satisfying:
$$ \delta < \min\left\{ 1, \; \frac{\varepsilon}{4 \times 33} \right\} = \frac{\varepsilon}{132} \tag{106} $$
Define four singular boundary nodes:
$$ u_1 = -4 - \delta, \quad u_2 = -4 + \delta, \quad v_1 = 4 - \delta, \quad v_2 = 4 + \delta \tag{107} $$
These nodes define two singular subintervals:
$$ I_{\text{sing}, 1} := [-4 - \delta, -4 + \delta] \quad \text{and} \quad I_{\text{sing}, 2} := [4 - \delta, 4 + \delta] \tag{108} $$
each having width $2\delta$. The total length of the singular intervals is $4\delta$.
On the remaining three intervals:
$$ J_1 = [-8, -4 - \delta], \quad J_2 = [-4 + \delta, 4 - \delta], \quad J_3 = [4 + \delta, 8] \tag{109} $$
the function $\Gamma(y)$ is continuous. By Cantor's Uniform Continuity Theorem, $\Gamma$ is uniformly continuous on each compact set $J_1, J_2, J_3$. 
Choose a partition $P_{\text{reg}}$ on $J_1 \cup J_2 \cup J_3$ with mesh fineness sufficiently small such that the local oscillation satisfies $\omega(\Gamma; \Delta_k) < \frac{\varepsilon}{2(16)} = \frac{\varepsilon}{32}$ on every regular subinterval.
Now form the complete partition $P$ of $[-8, 8]$ as the union of $P_{\text{reg}}$ and the boundary nodes $\{u_1, u_2, v_1, v_2\}$. The total Darboux oscillation decomposes into regular and singular sums:
$$ S(\Gamma; P) - s(\Gamma; P) = \sum_{k \in \text{reg}} \omega(\Gamma; \Delta_k) \Delta y_k + \omega(\Gamma; I_{\text{sing}, 1}) (2\delta) + \omega(\Gamma; I_{\text{sing}, 2}) (2\delta) \tag{110} $$
Bounding each term:
$$ \sum_{k \in \text{reg}} \omega(\Gamma; \Delta_k) \Delta y_k < \frac{\varepsilon}{32} \sum_{k \in \text{reg}} \Delta y_k \le \frac{\varepsilon}{32} (16) = \frac{\varepsilon}{2} \tag{111} $$
$$ \omega(\Gamma; I_{\text{sing}, 1}) (2\delta) + \omega(\Gamma; I_{\text{sing}, 2}) (2\delta) \le 33(2\delta) + 33(2\delta) = 132\delta < 132 \left( \frac{\varepsilon}{132} \right) = \frac{\varepsilon}{2} \tag{112} $$
Combining step 111 and step 112:
$$ S(\Gamma; P) - s(\Gamma; P) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{113} $$
This demonstrates how the oscillation is suppressed across jump discontinuities.

**Step 3: Exact Evaluation of Aerodynamic Lift:**
By the additivity of the Riemann integral:
$$ \int_{-8}^8 \Gamma(y)\,dy = \int_{-8}^8 \Gamma_0(y)\,dy + \int_{-8}^8 \Delta \Gamma_f \chi_{[-4, 4]}(y)\,dy \tag{114} $$
The first term represents the area of a semi-ellipse with semi-axes $a = 8$ and $b = 25$:
$$ \int_{-8}^8 25 \sqrt{1 - \left(\frac{y}{8}\right)^2}\,dy = \frac{1}{2} \pi (8)(25) = 100\pi \approx 314.159\text{ m}^3/\text{s} \tag{115} $$
The second term is the integral of the step function:
$$ \int_{-8}^8 8 \cdot \chi_{[-4, 4]}(y)\,dy = \int_{-4}^4 8\,dy = 8 \times (4 - (-4)) = 8 \times 8 = 64\text{ m}^3/\text{s} \tag{116} $$
Summing the two contributions:
$$ \int_{-8}^8 \Gamma(y)\,dy = 100\pi + 64 \approx 378.159\text{ m}^3/\text{s} \tag{117} $$
Now compute the total aerodynamic lift force from step 103:
$$ L_{\text{total}} = \rho_\infty V_\infty (100\pi + 64) = (1.225\text{ kg/m}^3)(80\text{ m/s})(378.159\text{ m}^3/\text{s}) $$
$$ L_{\text{total}} = 98.0 \times 378.159 \approx 37059.6\text{ N} \approx 37.06\text{ kN} \tag{118} $$
The total lift generated by the flapped wing is approximately $37.06\text{ kN}$, with the flap deflection contributing $98.0 \times 64 = 6.272\text{ kN}$ ($16.9\%$) of additional lift.
