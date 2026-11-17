---
dg-publish: true
---
# Linear Space Structure of Integrable Functions
The analytical machinery established in [[Chapter 1 - Definition of the Integral and Description of the Set of Integrable Functions|Chapter 1]] defined the definite Riemann integral as the unique real limit of Riemann sums over tagged partitions as the mesh fineness vanishes. That construction settled the foundational question of integrability and identified broad functional classes—continuous functions, monotone functions, and bounded functions with negligible discontinuity sets—belonging to the integrable family $\mathcal{R}[a, b]$. 

With the existence of the integral established, the operational and algebraic architecture of integration must now be analyzed. Rather than viewing the integral merely as an isolated numerical calculation associated with an individual integrand, modern real analysis conceives of integration as an operator acting upon functional spaces. The family of integrable functions $\mathcal{R}[a, b]$ possesses rich geometric and algebraic structures: it forms an infinite-dimensional real vector space, closed under linear combinations and pointwise products, upon which the definite integral operates as a continuous, positive, linear functional.

### The Algebra of Riemann Integrable Functions
Let $[a, b] \subset \mathbb{R}$ be a non-degenerate compact interval with $a < b$. The space of all real-valued functions defined on $[a, b]$ is denoted by $\mathbb{R}^{[a, b]}$. Under the standard operations of pointwise function addition:
$$
\begin{gather}
(f + g)(x) := f(x) + g(x) \tag{1}
\end{gather}
$$
and pointwise scalar multiplication:
$$
\begin{gather}
(\alpha f)(x) := \alpha f(x) \tag{2}
\end{gather}
$$
for $\alpha \in \mathbb{R}$ and $x \in [a, b]$, the set $\mathbb{R}^{[a, b]}$ constitutes a real vector space. 

To demonstrate that the subset of Riemann integrable functions $\mathcal{R}[a, b] \subset \mathbb{R}^{[a, b]}$ forms a linear subspace, one must establish that any real linear combination of integrable functions remains Riemann integrable, and that the integral operator commutes with scalar scaling and finite summation.

Let $P = \{x_0, x_1, \dots, x_n\}$ be an arbitrary partition of $[a, b]$ with intermediate evaluation nodes $\xi = (\xi_1, \dots, \xi_n)$ where $\xi_i \in [x_{i-1}, x_i]$. For any two functions $f, g: [a, b] \to \mathbb{R}$ and arbitrary real scalars $\alpha, \beta \in \mathbb{R}$, the Riemann sum of the linear combination $h := \alpha f + \beta g$ satisfies an exact discrete algebraic identity:
$$
\begin{gather}
\sigma(\alpha f + \beta g; P, \xi) = \sum_{i=1}^n \big( \alpha f(\xi_i) + \beta g(\xi_i) \big) \Delta x_i \tag{3}
\end{gather}
$$
Distributing the subinterval lengths $\Delta x_i$ and rearranging the finite sum yields:
$$
\begin{gather}
\sigma(\alpha f + \beta g; P, \xi) = \alpha \sum_{i=1}^n f(\xi_i) \Delta x_i + \beta \sum_{i=1}^n g(\xi_i) \Delta x_i = \alpha \sigma(f; P, \xi) + \beta \sigma(g; P, \xi) \tag{4}
\end{gather}
$$
The algebraic identity of step 4 reveals that at the discrete level of Riemann sums, the aggregation operator is strictly linear. Passing to the limit as the partition mesh $\lambda(P) \to 0$ preserves this linear structure: 
$$
\begin{gather}
\textbf{Theorem: Linearity of the Riemann Integral} \\[5mm]
\text{Let } f, g \in \mathcal{R}[a, b] \text{ and let } \alpha, \beta \in \mathbb{R}. \text{ Then the linear combination } (\alpha f + \beta g) \in \mathcal{R}[a, b], \\[2mm]
\text{and the integration operator satisfies the linear relation:} \\[3.5mm]
\int_a^b \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^b f(x)\,dx + \beta \int_a^b g(x)\,dx
\end{gather}
$$
(see [[Proof of the Linearity of the Riemann Integral]])

An immediate consequence of this theorem is that the set of Riemann integrable functions $\mathcal{R}[a, b]$ is a real linear vector space over $\mathbb{R}$, and the definite integral:
$$
\begin{gather}
I: \mathcal{R}[a, b] \to \mathbb{R}, \qquad I(f) := \int_a^b f(x)\,dx \tag{5}
\end{gather}
$$
is a linear functional on $\mathcal{R}[a, b]$. By mathematical induction, the linearity relation extends to any finite linear combination:
$$
\begin{gather}
\int_a^b \left( \sum_{k=1}^m \alpha_k f_k(x) \right) dx = \sum_{k=1}^m \alpha_k \int_a^b f_k(x)\,dx \tag{6}
\end{gather}
$$
for arbitrary functions $f_1, \dots, f_m \in \mathcal{R}[a, b]$ and scalars $\alpha_1, \dots, \alpha_m \in \mathbb{R}$.

>[!danger]+ Intuition: The Integral as an Infinite-Dimensional Dot Product
>In finite-dimensional Euclidean space $\mathbb{R}^n$, the inner product between a vector $v = (v_1, \dots, v_n)$ and the uniform weighting vector $\mathbf{1} = (1, \dots, 1)$ computes the sum of the components: $\langle v, \mathbf{1} \rangle = \sum_{i=1}^n v_i$. The linearity of the inner product $\langle \alpha u + \beta v, \mathbf{1} \rangle = \alpha \langle u, \mathbf{1} \rangle + \beta \langle v, \mathbf{1} \rangle$ is an elementary algebraic property. The Riemann integral represents the continuum counterpart of this discrete dot product. The function $f$ plays the role of an infinite-dimensional vector whose indices are the continuum of points $x \in [a, b]$, and the differential $dx$ acts as the uniform infinitesimal measure. The linearity of the definite integral is the direct analytical manifestation of the distributivity of multiplication over addition extended across the real continuum.

### Integrability of Products and the Algebra Property
While the sum and scalar multiple of integrable functions follow immediately from the linearity of discrete summation, the behavior of the pointwise product of two functions:
$$
\begin{gather}
(fg)(x) := f(x)g(x) \tag{7}
\end{gather}
$$
presents a deeper analytical challenge. In general, the Riemann sum of a product does not decompose into the product of Riemann sums:
$$
\begin{gather}
\sum_{i=1}^n f(\xi_i) g(\xi_i) \Delta x_i \neq \left( \sum_{i=1}^n f(\xi_i) \Delta x_i \right) \left( \sum_{i=1}^n g(\xi_i) \Delta x_i \right) \tag{8}
\end{gather}
$$
Consequently, the integrability of $fg$ cannot be deduced by passing to the limit in an elementary algebraic identity of integral sums.

Instead, the integrability of the product relies on the structural bridge between vector space linearity and the [[Chapter 1 - Definition of the Integral and Description of the Set of Integrable Functions|Continuous Composition Integrability Theorem]]. Recall that if $h \in \mathcal{R}[a, b]$ with range contained in a compact interval $[u, v]$, and if $\phi: [u, v] \to \mathbb{R}$ is continuous, then the composite function $\phi \circ h$ is Riemann integrable on $[a, b]$.

Consider the squaring function $\phi: \mathbb{R} \to \mathbb{R}$ defined by $\phi(t) = t^2$. Because $\phi$ is continuous on all of $\mathbb{R}$, it follows that whenever $h \in \mathcal{R}[a, b]$, the square $h^2 \in \mathcal{R}[a, b]$. 

Now, let $f, g \in \mathcal{R}[a, b]$. By vector space linearity, both the sum $(f + g)$ and the difference $(f - g)$ belong to $\mathcal{R}[a, b]$. Applying the continuous squaring operation yields $(f + g)^2 \in \mathcal{R}[a, b]$ and $(f - g)^2 \in \mathcal{R}[a, b]$. The pointwise product $fg$ can then be isolated via the algebraic polarization identity:
$$
\begin{gather}
f(x)g(x) = \frac{1}{4} \Big( \big( f(x) + g(x) \big)^2 - \big( f(x) - g(x) \big)^2 \Big) \tag{9}
\end{gather}
$$
Because the right-hand side of step 9 is a linear combination of functions already known to be integrable, the product $fg$ must itself be integrable.
$$
\begin{gather}
\textbf{Theorem: Integrability of the Product of Integrable Functions} \\[5mm]
\text{Let } f, g \in \mathcal{R}[a, b]. \text{ Then the pointwise product } fg \text{ is Riemann integrable on } [a, b]: \\[3.5mm]
fg \in \mathcal{R}[a, b]
\end{gather}
$$
(see [[Proof of the Integrability of the Product of Integrable Functions]])

The algebraic implications of this result are profound. A vector space endowed with an associative, bilinear multiplication that distributes over addition is termed an *algebra* over a field. Because pointwise multiplication of real functions is commutative, associative, and distributive over addition, the space $\mathcal{R}[a, b]$ forms a commutative, associative real algebra.

>[!info]+ Remark: Failure of Multiplicativity and the Non-Commutative Product Integral
>It must be emphasized with absolute clarity that while the space $\mathcal{R}[a, b]$ is closed under multiplication, the integral operator itself is *not* multiplicative:
>$$ \int_a^b f(x)g(x)\,dx \neq \left( \int_a^b f(x)\,dx \right) \left( \int_a^b g(x)\,dx \right) $$
>For a concrete demonstration, setting $f(x) = g(x) = x$ on $[0, 1]$ gives $\int_0^1 x^2\,dx = 1/3$, whereas $(\int_0^1 x\,dx)^2 = (1/2)^2 = 1/4 \ne 1/3$. The integral of a product computes the total accumulation of an interactively coupled density, which depends intricately on the spatial covariance of the two functions across the interval.

---
# Domain Decomposition and Additivity Over Subintervals
The preceding results analyzed the behavior of the integral when the domain of integration $[a, b]$ remains fixed while the integrands vary within the functional space $\mathcal{R}[a, b]$. A complementary structural perspective examines the behavior of the integral when the integrand $f$ is fixed while the geometric domain of integration is partitioned, expanded, or inverted.

### Domain Splitting and Piecewise Integration
The geometric intuition of area mandates that if a planar region is divided into two non-overlapping subregions by a vertical line, the total area must equal the sum of the areas of the constituent components. In the language of real analysis, this corresponds to partitioning the interval $[a, b]$ at an intermediate node $c \in (a, b)$ into two adjoining compact subintervals $[a, c]$ and $[c, b]$.

To establish that integrability on the whole interval is completely equivalent to joint integrability on the subintervals, the Darboux upper and lower sums must be analyzed. Any partition $P$ of $[a, b]$ can be refined by adjoining the division point $c$, generating partitions $P'$ of $[a, c]$ and $P''$ of $[c, b]$. The Darboux sums over the refined partition decouple into exact sums:
$$
\begin{gather}
s(f; P \cup \{c\}) = s(f|_{[a, c]}; P') + s(f|_{[c, b]}; P'') \tag{10}
\end{gather}
$$
$$
\begin{gather}
S(f; P \cup \{c\}) = S(f|_{[a, c]}; P') + S(f|_{[c, b]}; P'') \tag{11}
\end{gather}
$$
The difference between the upper and lower sums over $[a, b]$ then decomposes into the sum of the oscillations over $[a, c]$ and $[c, b]$:
$$
\begin{gather}
S(f; P \cup \{c\}) - s(f; P \cup \{c\}) = \big( S(f|_{[a, c]}; P') - s(f|_{[a, c]}; P') \big) + \big( S(f|_{[c, b]}; P'') - s(f|_{[c, b]}; P'') \big) \tag{12}
\end{gather}
$$
Because the terms on the right-hand side of step 12 are strictly non-negative, the oscillation over the whole domain can be made smaller than $\varepsilon$ if and only if the oscillations over both subdomains can simultaneously be made arbitrarily small: 
$$
\begin{gather}
\textbf{Theorem: Interval Additivity of the Definite Integral} \\[5mm]
\text{Let } [a, b] \subset \mathbb{R} \text{ be a compact interval, and let } c \in (a, b). \\[2mm]
\text{A function } f: [a, b] \to \mathbb{R} \text{ is Riemann integrable on } [a, b] \text{ if and only if } f \text{ is Riemann integrable} \\[2mm]
\text{on both subintervals } [a, c] \text{ and } [c, b]: \\[3.5mm]
f \in \mathcal{R}[a, b] \iff f \in \mathcal{R}[a, c] \quad \text{and} \quad f \in \mathcal{R}[c, b] \\[3.5mm]
\text{When these conditions hold, the integral satisfies the domain additivity formula:} \\[3.5mm]
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx
\end{gather}
$$
(see [[Proof of Interval Additivity of the Definite Integral]])

```easy-tikz
title $\text{Interval Additivity of the Definite Integral}$
xlabel $x$
ylabel $y$
show x from 0 to 10 and y from 0 to 6
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 0.4*x + 0.08*x^2 - 0.009*x^3, from x = 1.0 to 9.0, in teal, very thick
draw a line from (1.5, 0) to (1.5, 1.75), in orange, thick
draw a line from (5.0, 0) to (5.0, 3.875), in green, thick
draw a line from (8.5, 0) to (8.5, 4.65), in red, thick
draw a line from (1.5, 0) to (8.5, 0), in gray, thin
raw tool {"type":"points","name":"P1","color":"magenta","points":"(1.5, 1.75);"}
raw tool {"type":"points","name":"P2","color":"purple","points":"(5.0, 3.875);"}
mark (8.5, 4.65) in brown
write "$a$" at (1.5, -0.35) in orange, below
write "$c$" at (5.0, -0.35) in green, below
write "$b$" at (8.5, -0.35) in red, below
write "$y = f(x)$" at (5.6, 4.9) in teal, right
write "$[a, c]$" at (3.25, -0.35) in gray, below
write "$[c, b]$" at (6.75, -0.35) in gray, below
write "$\\int_a^c f(x) \\ dx$" at (3.2, 1.35) in orange, center, large
write "$\\int_c^b f(x) \\ dx$" at (6.7, 2.3) in green, center, large
write "$(a, 1.75)$" at (1.1, 2.1) in magenta, center
write "$(c, 3.875)$" at (4.45, 4.3) in purple, center
write "$(b, 4.65)$" at (8.45, 5.05) in brown, center
```

By finite induction, the interval additivity formula of step 13 extends to any finite partition of $[a, b]$ into $m$ consecutive contiguous subintervals:
$$
\begin{gather}
a = c_0 < c_1 < c_2 < \dots < c_m = b \implies \int_a^b f(x)\,dx = \sum_{k=1}^m \int_{c_{k-1}}^{c_k} f(x)\,dx \tag{13}
\end{gather}
$$
This additive property enables the evaluation of integrals for piecewise continuous or piecewise elementary functions by splitting the integration domain at the boundary nodes of regularity.

>[!danger]+ Intuition: Domain Slicing and Flux Conservation
>In continuum physics, the total mass of an inhomogeneous rod extending from $x = a$ to $x = b$ is the spatial integral of its linear mass density $\rho(x)$. If the rod is physically cut into two pieces at an arbitrary internal location $x = c$, the sum of the masses of the two individual fragments must equal the mass of the uncut rod. Mass can neither be created nor destroyed by the purely conceptual act of drawing a boundary at $c$. The interval additivity theorem demonstrates that the Riemann integral faithfully respects this fundamental physical conservation law.

### Directed Intervals and Orientation Inversion
Up to this point, the symbol $\int_a^b f(x)\,dx$ has been defined strictly under the geometric assumption that the lower limit $a$ is strictly less than the upper limit $b$, reflecting integration across a standard positively oriented interval $[a, b]$. 

However, in mechanics, vector analysis, and thermodynamic cycles, integration frequently takes place along oriented curves where motion may proceed from right to left, or where the terminal boundary coincides with the initial point. To endow the definite integral with algebraic flexibility and eliminate the need for conditional case analyses based on the relative ordering of limits, one introduces standard orientation conventions: 
$$
\begin{gather}
\textbf{Definition: Oriented Integrals and Boundary Conventions} \\[5mm]
\text{Let } f \text{ be defined at the point } a \in \mathbb{R}. \text{ The integral over a degenerate interval is defined by:} \\[3.5mm]
\int_a^a f(x)\,dx := 0 \\[3.5mm]
\text{Furthermore, if } a < b \text{ and } f \in \mathcal{R}[a, b], \text{ the integral with reversed orientation is defined by:} \\[3.5mm]
\int_b^a f(x)\,dx := -\int_a^b f(x)\,dx
\end{gather}
$$

The convention $\int_a^a f = 0$ is geometrically natural: an interval of zero length possesses zero measure, collapsing the area of the associated curvilinear trapezoid to zero. The skew-symmetric convention $\int_b^a f = -\int_a^b f$ reflects the reversal of the directed line increment: traversing the domain from $b$ down to $a$ reverses the sign of every subinterval increment $\Delta x_i = x_i - x_{i-1} < 0$.

### The Generalized Orientation Additivity Formula
The remarkable utility of the orientation conventions is that they completely liberate the interval additivity relation from the geometric restriction $a < c < b$. Once orientation is accounted for, the additivity equation holds for *any* three points $a, b, c$, regardless of their relative locations on the real line: 
$$
\begin{gather}
\textbf{Theorem: Generalized Orientation Additivity Formula} \\[5mm]
\text{Let } J \subset \mathbb{R} \text{ be an interval, and let } f: J \to \mathbb{R} \text{ be a function that is Riemann integrable} \\[2mm]
\text{on every compact subinterval of } J. \text{ Then for any three arbitrary points } a, b, c \in J, \\[2mm]
\text{regardless of their relative spatial ordering:} \\[3.5mm]
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx
\end{gather}
$$
(see [[Proof of the Generalized Orientation Additivity Formula]])

To understand why this relation holds unconditionally, consider an alternative permutation where $c$ lies strictly to the right of the terminal point $b$, so that $a < b < c$. By the classical additivity theorem applied to the nested intervals $[a, b]$ and $[b, c]$:
$$
\begin{gather}
\int_a^c f(x)\,dx = \int_a^b f(x)\,dx + \int_b^c f(x)\,dx \tag{14}
\end{gather}
$$
Subtracting $\int_b^c f(x)\,dx$ from both sides of step 14 yields:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx - \int_b^c f(x)\,dx \tag{15}
\end{gather}
$$
Applying the orientation inversion convention $-\int_b^c f(x)\,dx = \int_c^b f(x)\,dx$ transforms step 15 directly into:
$$
\begin{gather}
\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx \tag{16}
\end{gather}
$$
The remaining permutations (such as $c < a < b$ or cases involving coincident points) resolve with identical algebraic consistency.

>[!warning]+ Warning: Integrability on the Enclosing Hull
>The validity of the generalized formula $\int_a^b f = \int_a^c f + \int_c^b f$ hinges strictly on the hypothesis that $f$ is integrable on the minimal compact interval enclosing *all three points*, namely $[\min\{a, b, c\}, \max\{a, b, c\}]$. If $c$ is selected outside $[a, b]$ in a region where $f$ exhibits non-integrable singularities, the terms $\int_a^c f$ and $\int_c^b f$ become undefined, rendering the identity invalid.

---
# Order Structure, Monotonicity, and Integral Inequalities
In addition to its vector space and domain-additive structures, the Riemann integral interacts harmoniously with the standard ordering of the real numbers. The preservation of inequalities under integration represents one of the most powerful tools in analysis, enabling the derivation of universal bounds, asymptotic estimates, and functional norms.

### Positivity and Strict Positivity of the Integral
Let $[a, b]$ be an interval with $a < b$. If a function $f: [a, b] \to \mathbb{R}$ is non-negative, satisfying $f(x) \ge 0$ for all $x \in [a, b]$, then for every marked partition $(P, \xi)$, the terms in the Riemann sum satisfy $f(\xi_i) \Delta x_i \ge 0$. Because a finite sum of non-negative real numbers is non-negative, it follows that:
$$
\begin{gather}
\sigma(f; P, \xi) \ge 0 \tag{17}
\end{gather}
$$
Taking the limit as the mesh fineness $\lambda(P) \to 0$, the non-strict inequality is preserved, guaranteeing that $\int_a^b f(x)\,dx \ge 0$.

However, an important analytical distinction arises regarding *strict* positivity. If a non-negative function $f(x) \ge 0$ is not identically zero, does its integral necessarily satisfy $\int_a^b f(x)\,dx > 0$? 

In general, the answer is negative: if $f(x)$ vanishes everywhere on $[a, b]$ except at a single isolated point $x_0$ where $f(x_0) = 1$, then $f$ possesses a single discontinuity, $f \in \mathcal{R}[a, b]$, yet $\int_a^b f(x)\,dx = 0$. However, if the hypothesis of continuity is imposed, strict positivity is restored.

If $f \in C[a, b]$, $f(x) \ge 0$, and there exists some $x_0 \in [a, b]$ where $f(x_0) = c > 0$, then by the permanence of sign property of continuous functions, there exists a neighborhood $[\alpha, \beta] \subset [a, b]$ with $\alpha < \beta$ on which $f(x) \ge c / 2 > 0$. By interval additivity and monotonicity:
$$
\begin{gather}
\int_a^b f(x)\,dx \ge \int_\alpha^\beta f(x)\,dx \ge \frac{c}{2} (\beta - \alpha) > 0 \tag{18}
\end{gather}
$$
This distinction between general integrable functions and continuous functions is critical across functional analysis.

### Monotonicity and Dominated Bounding
The linearity of the integral immediately extends positivity to general inequalities between two functions. Let $f, g \in \mathcal{R}[a, b]$ satisfy the pointwise dominance condition:
$$
\begin{gather}
f(x) \le g(x) \quad \text{for all } x \in [a, b] \tag{19}
\end{gather}
$$
Define the non-negative difference function $h(x) := g(x) - f(x) \ge 0$. By linearity, $h \in \mathcal{R}[a, b]$. Applying the positivity property to $h$ yields:
$$
\begin{gather}
\int_a^b \big( g(x) - f(x) \big)\,dx \ge 0 \implies \int_a^b g(x)\,dx - \int_a^b f(x)\,dx \ge 0 \tag{20}
\end{gather}
$$
which establishes the monotonicity of the integral:
$$
\begin{gather}
\int_a^b f(x)\,dx \le \int_a^b g(x)\,dx \tag{21}
\end{gather}
$$

A direct application of monotonicity provides the universal Darboux bounds for an integrable function. Because every integrable function $f$ is bounded, there exist finite bounds $m := \inf_{x \in [a, b]} f(x)$ and $M := \sup_{x \in [a, b]} f(x)$. The constant functions $m$ and $M$ satisfy $m \le f(x) \le M$ for all $x \in [a, b]$. Integrating this compound inequality yields:
$$
\begin{gather}
\int_a^b m\,dx \le \int_a^b f(x)\,dx \le \int_a^b M\,dx \tag{22}
\end{gather}
$$
Because the integral of a constant $k$ is $k(b - a)$, step 22 collapses to the universal bounding inequality:
$$
\begin{gather}
m(b - a) \le \int_a^b f(x)\,dx \le M(b - a) \tag{23}
\end{gather}
$$

### The Absolute Value Inequality and Norm Properties
Another fundamental consequence of order preservation is the integral triangle inequality. For any real number $u \in \mathbb{R}$, the absolute value satisfies $-|u| \le u \le |u|$. Applying this to an integrable function $f(x)$ gives:
$$
\begin{gather}
-|f(x)| \le f(x) \le |f(x)| \quad \text{for all } x \in [a, b] \tag{24}
\end{gather}
$$
Because the absolute value function $\phi(t) = |t|$ is continuous on $\mathbb{R}$, the Continuous Composition Integrability Theorem guarantees that $|f| \in \mathcal{R}[a, b]$. Integrating the compound inequality of step 24 yields:
$$
\begin{gather}
-\int_a^b |f(x)|\,dx \le \int_a^b f(x)\,dx \le \int_a^b |f(x)|\,dx \tag{25}
\end{gather}
$$
The double inequality of step 25 is equivalent to the absolute value inequality:
$$
\begin{gather}
\left| \int_a^b f(x)\,dx \right| \le \int_a^b |f(x)|\,dx \tag{26}
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Monotonicity and the Absolute Value Integral Inequality} \\[5mm]
\text{Let } f, g \in \mathcal{R}[a, b] \text{ with } a \le b. \\[2mm]
1. \text{ If } f(x) \ge 0 \text{ for all } x \in [a, b], \text{ then } \int_a^b f(x)\,dx \ge 0. \\[2mm]
2. \text{ If } f \in C[a, b], \; f(x) \ge 0 \text{ on } [a, b], \text{ and } \exists x_0 \in [a, b] \text{ such that } f(x_0) > 0, \text{ then } \int_a^b f(x)\,dx > 0. \\[2mm]
3. \text{ If } f(x) \le g(x) \text{ for all } x \in [a, b], \text{ then } \int_a^b f(x)\,dx \le \int_a^b g(x)\,dx. \\[2mm]
4. \text{ If } m \le f(x) \le M \text{ on } [a, b], \text{ then } m(b - a) \le \int_a^b f(x)\,dx \le M(b - a). \\[2mm]
5. \text{ The function } |f| \in \mathcal{R}[a, b], \text{ and the integral satisfies the absolute bound:} \\[3.5mm]
\left| \int_a^b f(x)\,dx \right| \le \int_a^b |f(x)|\,dx
\end{gather}
$$
(see [[Proof of Monotonicity and the Absolute Value Integral Inequality]])

>[!danger]+ Intuition: Destructive Interference and Geometric Length
>The inequality $|\int_a^b f| \le \int_a^b |f|$ represents the continuous limit of the classical triangle inequality for finite sums: $|\sum v_i| \le \sum |v_i|$. When a function oscillates between positive and negative values, integration aggregates signed quantities, causing positive and negative areas to cancel—a phenomenon identical to destructive wave interference in acoustics and electrodynamics. By contrast, integrating $|f|$ rectifies all negative contributions, accumulating the total absolute displacement regardless of direction. Consequently, the net displacement $|\int_a^b f|$ can never exceed the total distance traversed $\int_a^b |f|$.

### The Cauchy-Bunyakovsky-Schwarz Inequality
The combination of linearity, product integrability, and positivity endows the space of integrable functions with a natural inner product structure. For functions $f, g \in \mathcal{R}[a, b]$, define the pairing:
$$
\begin{gather}
\langle f, g \rangle := \int_a^b f(x)g(x)\,dx \tag{27}
\end{gather}
$$
The pairing of step 27 is symmetric ($\langle f, g \rangle = \langle g, f \rangle$) and bilinear:
$$
\begin{gather}
\langle \alpha f_1 + \beta f_2, g \rangle = \alpha \langle f_1, g \rangle + \beta \langle f_2, g \rangle \tag{28}
\end{gather}
$$
Furthermore, for any $f \in \mathcal{R}[a, b]$, the square $f(x)^2 \ge 0$, which implies:
$$
\begin{gather}
\langle f, f \rangle = \int_a^b f(x)^2\,dx \ge 0 \tag{29}
\end{gather}
$$
Thus, $\langle \cdot, \cdot \rangle$ defines a positive semi-definite bilinear form on $\mathcal{R}[a, b]$. 

The central geometric inequality governing any space endowed with a positive semi-definite inner product is the celebrated *Cauchy-Bunyakovsky-Schwarz (CBS) inequality*. In the context of real integration, this inequality was first derived by the Russian mathematician Viktor Bunyakovsky in 1859 (predating Hermann Schwarz's work by two decades).

The analytical derivation proceeds by considering an arbitrary real parameter $\lambda \in \mathbb{R}$. Form the linear combination $\lambda f + g \in \mathcal{R}[a, b]$. Its square is non-negative everywhere:
$$
\begin{gather}
\big( \lambda f(x) + g(x) \big)^2 \ge 0 \quad \text{for all } x \in [a, b] \tag{30}
\end{gather}
$$
Integrating the inequality of step 30 across $[a, b]$ and expanding via linearity yields:
$$
\begin{gather}
Q(\lambda) := \int_a^b \big( \lambda f(x) + g(x) \big)^2\,dx = \lambda^2 \int_a^b f(x)^2\,dx + 2\lambda \int_a^b f(x)g(x)\,dx + \int_a^b g(x)^2\,dx \ge 0 \tag{31}
\end{gather}
$$
The expression $Q(\lambda)$ in step 31 is a quadratic polynomial in $\lambda$:
$$
\begin{gather}
Q(\lambda) = A\lambda^2 + 2B\lambda + C \ge 0 \tag{32}
\end{gather}
$$
where:
$$
\begin{gather}
A := \int_a^b f(x)^2\,dx, \qquad B := \int_a^b f(x)g(x)\,dx, \qquad C := \int_a^b g(x)^2\,dx \tag{33}
\end{gather}
$$
If $A = 0$ and $f$ is continuous, then $f \equiv 0$, in which case $B = 0$ and the inequality reduces to $0 \le 0$, which holds with equality. If $A > 0$, the quadratic $Q(\lambda)$ is non-negative for all real $\lambda$ if and only if its discriminant is non-positive:
$$
\begin{gather}
\Delta = (2B)^2 - 4AC \le 0 \implies 4B^2 - 4AC \le 0 \implies B^2 \le AC \tag{34}
\end{gather}
$$
Substituting the explicit integrals from step 33 into step 34 yields the Cauchy-Bunyakovsky-Schwarz inequality: 
$$
\begin{gather}
\textbf{Theorem: Cauchy-Bunyakovsky-Schwarz Inequality for Integrals} \\[5mm]
\text{Let } f, g \in \mathcal{R}[a, b]. \text{ Then their product satisfies the inequality:} \\[3.5mm]
\left( \int_a^b f(x)g(x)\,dx \right)^2 \le \left( \int_a^b f(x)^2\,dx \right) \left( \int_a^b g(x)^2\,dx \right) \\[3.5mm]
\text{Furthermore, if } f, g \in C[a, b], \text{ equality holds if and only if } f \text{ and } g \text{ are linearly dependent} \\[2mm]
\text{on } [a, b], \text{ meaning there exist scalars } \alpha, \beta \in \mathbb{R}, \text{ not both zero, such that } \alpha f(x) + \beta g(x) \equiv 0.
\end{gather}
$$
(see [[Proof of the Cauchy-Bunyakovsky-Schwarz Inequality for Integrals]])

Taking the square root of both sides of the CBS inequality yields:
$$
\begin{gather}
\left| \int_a^b f(x)g(x)\,dx \right| \le \|f\|_{L^2} \|g\|_{L^2} \tag{35}
\end{gather}
$$
where $\|f\|_{L^2} := \left( \int_a^b f(x)^2\,dx \right)^{1/2}$ defines the standard $L^2$ norm.

>[!info]+ Remark: From Cauchy-Schwarz to $L^2$ Geometry
>The Cauchy-Bunyakovsky-Schwarz inequality guarantees that the angle $\theta$ between two non-zero functions in $C[a, b]$ can be defined rigorously by:
>$$ \cos \theta := \frac{\int_a^b f(x)g(x)\,dx}{\|f\|_{L^2} \|g\|_{L^2}} \in [-1, 1] $$
>Two functions are said to be *orthogonal* if $\int_a^b f(x)g(x)\,dx = 0$. This geometric formulation provides the bedrock for Fourier analysis, orthogonal polynomials (Legendre, Chebyshev, Hermite), and quantum mechanics, where physical observables correspond to self-adjoint operators on pre-Hilbert functional spaces.

---
# The Mean-Value Theorems for Integrals
The differential Mean-Value Theorem established in [[Chapter 1 - Differentiable Functions|Module 5]] connected the global increment of a differentiable function to its instantaneous local derivative at an intermediate point: $f(b) - f(a) = f'(\xi)(b - a)$. In an analogous fashion, the Mean-Value Theorems for integrals link the macroscopic aggregate value of a definite integral to an intermediate state of the integrand: 
```easy-tikz
title $\text{Geometric Interpretation of the First Mean-Value Theorem}$
xlabel $x$
ylabel $y$
show x from 0 to 10 and y from 0 to 6.5
axes on the edges
size 12 x 8
plot f(x) = 1.2 + 0.7*x + 0.02*x^2 - 0.015*x^3, from x = 1.0 to 9.0, in teal, very thick
draw a line from (1.5, 0) to (1.5, 3.5), in orange, thick
draw a line from (8.5, 0) to (8.5, 3.5), in red, thick
draw a line from (1.5, 3.1) to (8.5, 3.1), in green, very thick
draw a line from (4.45, 0) to (4.45, 3.1), in pink, dashed
mark (4.45, 3.1), in pink, large
write "$a$" at (1.5, -0.35) in orange, below
write "$b$" at (8.5, -0.35) in red, below
write "$\\xi$" at (4.45, -0.35) in pink, below
write "$y = f(x)$" at (3.9, 3.8) in teal, right
write "$y = f(\\xi) = \\mu$" at (6.15, 3.5) in green, right
write "$\\text{Area} = f(\\xi)(b - a)$" at (4.65, 1.6) in purple, center
write "$\\text{Deficit}$" at (2.5, 3.5) in orange, above
write "$\\text{Excess}$" at (9.25, 3.7) in red, below
```

### The First Mean-Value Theorem and Integral Averages
Let $f \in \mathcal{R}[a, b]$ with $a < b$, and let $m = \inf_{[a, b]} f$ and $M = \sup_{[a, b]} f$. Dividing the universal Darboux inequality $m(b - a) \le \int_a^b f(x)\,dx \le M(b - a)$ by the positive interval length $(b - a) > 0$ yields:
$$
\begin{gather}
m \le \frac{1}{b - a} \int_a^b f(x)\,dx \le M \tag{36}
\end{gather}
$$
The central quantity in step 36 represents the *integral average* (or arithmetic mean value) of the function $f$ over $[a, b]$:
$$
\begin{gather}
\mu := \frac{1}{b - a} \int_a^b f(x)\,dx \tag{37}
\end{gather}
$$
Step 36 demonstrates that the average $\mu$ always belongs to the range of bounds $[m, M]$.

If the integrand $f$ is continuous on $[a, b]$, the Intermediate Value Theorem (Bolzano-Cauchy theorem) guarantees that $f$ attains every value between its absolute minimum $m$ and absolute maximum $M$. Because $\mu \in [m, M]$, there must exist at least one point $\xi \in [a, b]$ such that $f(\xi) = \mu$: 
$$
\begin{gather}
\textbf{First Mean-Value Theorem for Integrals: } \\[5mm]
\text{Let } f \in \mathcal{R}[a, b] \text{ with } a < b, \text{ and let } m = \inf_{x \in [a, b]} f(x), \; M = \sup_{x \in [a, b]} f(x). \\[2mm]
1. \text{ Average Value Form: There exists a real number } \mu \in [m, M] \text{ such that:} \\[3.5mm]
\int_a^b f(x)\,dx = \mu (b - a) \\[3.5mm]
2. \text{ Continuous Form: If } f \in C[a, b], \text{ then there exists at least one intermediate node } \xi \in [a, b] \text{ such that:} \\[3.5mm]
\int_a^b f(x)\,dx = f(\xi)(b - a)
\end{gather}
$$
(see [[Proof of the First Mean-Value Theorem for Integrals]])

Geometrically, the First Mean-Value Theorem states that the area of the curvilinear trapezoid under $y = f(x)$ over $[a, b]$ is exactly equal to the area of a rectangle having the identical base $[a, b]$ and constant height $f(\xi)$. As illustrated in the accompanying figure, the area of the region where the curve exceeds the horizontal line $y = f(\xi)$ (the excess) precisely balances the area of the region where the curve falls below $y = f(\xi)$ (the deficit).

>[!danger]+ Intuition: The Leveling of Mass and Fluid Incompressibility
>Imagine an incompressible fluid contained in a rectangular tank whose bottom spans $[a, b]$. Suppose the surface of the fluid has been agitated into waves described by the profile $y = f(x)$. If the fluid is allowed to settle under gravity without loss of volume, the chaotic surface will flatten into a perfectly horizontal plane at height $\mu = f(\xi)$. The total volume of fluid is conserved: $\int_a^b f(x)\,dx = \mu (b - a)$. The First Mean-Value Theorem guarantees that for a continuous wave profile, the calm equilibrium level $\mu$ must coincide with the initial fluid height at some spatial coordinate $\xi$.

### The Generalized First Mean-Value Theorem with Weight Function
In many scientific and engineering contexts, physical quantities are distributed non-uniformly across space. For example, when calculating the center of mass of a rod with variable density, or computing the expected value of an asset return under a continuous probability density, the integrand appears as a product $f(x)g(x)$, where $g(x)$ serves as a non-negative weighting factor.

Suppose $f, g \in \mathcal{R}[a, b]$ with $a < b$, and assume that $g$ does not change sign on $[a, b]$—for instance, $g(x) \ge 0$ for all $x \in [a, b]$. Multiplying the Darboux bounds $m \le f(x) \le M$ by the non-negative quantity $g(x) \ge 0$ preserves the inequalities pointwise:
$$
\begin{gather}
m g(x) \le f(x)g(x) \le M g(x) \quad \text{for all } x \in [a, b] \tag{38}
\end{gather}
$$
Integrating the compound inequality of step 38 via monotonicity gives:
$$
\begin{gather}
m \int_a^b g(x)\,dx \le \int_a^b f(x)g(x)\,dx \le M \int_a^b g(x)\,dx \tag{39}
\end{gather}
$$
If $\int_a^b g(x)\,dx = 0$, then step 39 forces $\int_a^b f(x)g(x)\,dx = 0$, and the formula holds for any $\mu$. If $\int_a^b g(x)\,dx > 0$, dividing by this integral yields:
$$
\begin{gather}
m \le \mu := \frac{\int_a^b f(x)g(x)\,dx}{\int_a^b g(x)\,dx} \le M \tag{40}
\end{gather}
$$
If $f$ is continuous, the Intermediate Value Theorem again guarantees the existence of a witness point $\xi \in [a, b]$ such that $f(\xi) = \mu$: 
$$
\begin{gather}
\textbf{Generalized First Mean-Value Theorem for Integrals: } \\[5mm]
\text{Let } f, g \in \mathcal{R}[a, b] \text{ with } a < b. \text{ Let } m = \inf_{x \in [a, b]} f(x), \; M = \sup_{x \in [a, b]} f(x), \\[2mm]
\text{and assume that } g \text{ does not change sign on } [a, b] \text{ (that is, } g(x) \ge 0 \text{ or } g(x) \le 0 \text{ for all } x \in [a, b]\text{)}. \\[2mm]
1. \text{ Bounded Form: There exists a real number } \mu \in [m, M] \text{ such that:} \\[3.5mm]
\int_a^b f(x)g(x)\,dx = \mu \int_a^b g(x)\,dx \\[3.5mm]
2. \text{ Continuous Form: If } f \in C[a, b], \text{ then there exists at least one intermediate node } \xi \in [a, b] \text{ such that:} \\[3.5mm]
\int_a^b f(x)g(x)\,dx = f(\xi) \int_a^b g(x)\,dx
\end{gather}
$$
(see [[Proof of the Generalized First Mean-Value Theorem for Integrals]])

Setting the weight function $g(x) \equiv 1$ recovers the standard First Mean-Value Theorem as an immediate corollary.

>[!warning]+ Warning: Sign Invariance Requirement on the Weight
>The hypothesis that $g(x)$ does not change sign on $[a, b]$ is indispensable. If $g(x)$ alternates between positive and negative values, multiplying $m \le f(x) \le M$ by $g(x)$ reverses the inequality on regions where $g(x) < 0$, causing step 38 to collapse entirely. As demonstrated in the Pathological Gallery, failure of sign invariance can lead to catastrophic mathematical contradictions.

### The Second Mean-Value Theorem: Bonnet and Weierstrass Formulations
While the First Mean-Value Theorem requires the weight function $g(x)$ to maintain a constant sign, many analytical problems involve integrands where the weight oscillates rapidly—such as high-frequency Fourier integrals $\int_a^b f(x) \sin(\omega x)\,dx$. In such cases, the First Mean-Value Theorem is inapplicable. 

To handle oscillatory products, analysis relies on the *Second Mean-Value Theorem* (often associated with Pierre Ossian Bonnet, Karl Weierstrass, and Paul du Bois-Reymond). Rather than constraining the sign of $g(x)$, the Second Mean-Value Theorem transfers structural requirements to $f(x)$, demanding that $f$ be monotonic.

The conceptual engine behind the Second Mean-Value Theorem is the continuous analogue of Abel's summation by parts formula:
$$
\begin{gather}
\sum_{k=1}^n a_k b_k = A_n b_n - \sum_{k=1}^{n-1} A_k (b_{k+1} - b_k) \tag{41}
\end{gather}
$$
where $A_k = \sum_{j=1}^k a_j$. In the continuum, summation by parts transforms into integration by parts, allowing the monotonicity of $f$ to control the accumulation of the integral of $g$.

The Second Mean-Value Theorem exists in two classical formulations: Bonnet's form, which applies to non-negative monotonic functions, and the Weierstrass / du Bois-Reymond form, which applies to general monotonic functions: 
$$
\begin{gather}
\textbf{Second Mean-Value Theorem for Integrals: } \\[5mm]
\text{Let } g \in \mathcal{R}[a, b] \text{ with } a < b. \\[2mm]
1. \text{ Bonnet Form (Non-Negative Monotonic Decreasing):} \\[2mm]
\text{If } f: [a, b] \to \mathbb{R} \text{ is monotonic decreasing and non-negative } (f(x_1) \ge f(x_2) \ge 0 \text{ for } a \le x_1 < x_2 \le b), \\[2mm]
\text{then there exists at least one intermediate point } \xi \in [a, b] \text{ such that:} \\[3.5mm]
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx \\[3.5mm]
\text{If } f \text{ is monotonic increasing and non-negative } (0 \le f(x_1) \le f(x_2) \text{ for } a \le x_1 < x_2 \le b), \\[2mm]
\text{then there exists at least one intermediate point } \xi \in [a, b] \text{ such that:} \\[3.5mm]
\int_a^b f(x)g(x)\,dx = f(b) \int_\xi^b g(x)\,dx \\[3.5mm]
2. \text{ Weierstrass / du Bois-Reymond Form (General Monotonic):} \\[2mm]
\text{If } f: [a, b] \to \mathbb{R} \text{ is monotonic on } [a, b] \text{ (not necessarily non-negative),} \\[2mm]
\text{then there exists at least one intermediate point } \xi \in [a, b] \text{ such that:} \\[3.5mm]
\int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \int_\xi^b g(x)\,dx
\end{gather}
$$
(see [[Proof of the Second Mean-Value Theorem for Integrals]])

Notice that in Bonnet's decreasing formulation, the function $f(x)$ is pulled outside the integral evaluated strictly at the boundary point $a$, leaving only the integral of $g$ evaluated over a truncated subinterval $[a, \xi]$. This property makes the Second Mean-Value Theorem indispensable for bounding oscillatory integrals: if the primitive of $g$ is uniformly bounded, $|\int_a^u g(x)\,dx| \le K$ for all $u \in [a, b]$, then Bonnet's theorem immediately yields:
$$
\begin{gather}
\left| \int_a^b f(x)g(x)\,dx \right| = \left| f(a) \int_a^\xi g(x)\,dx \right| \le K f(a) \tag{42}
\end{gather}
$$
providing an asymptotic bound that is completely independent of the upper limit $b$. This bound is crucial in the study of improper integrals and the convergence of Fourier series, explored in [[Chapter 4 - Improper Integrals|Chapter 5]].

>[!info]+ Remark: Derivation of the Weierstrass Form from Bonnet's Theorem
>The general Weierstrass formulation follows directly from Bonnet's theorem via a vertical translation. If $f$ is monotonic decreasing on $[a, b]$, the shifted function $h(x) := f(x) - f(b)$ satisfies $h(x) \ge 0$ and is monotonic decreasing. Applying Bonnet's theorem to $h(x)g(x)$ yields:
>$$ \int_a^b \big( f(x) - f(b) \big) g(x)\,dx = \big( f(a) - f(b) \big) \int_a^\xi g(x)\,dx $$
>Expanding the left-hand side and rearranging:
>$$ \int_a^b f(x)g(x)\,dx = f(a) \int_a^\xi g(x)\,dx + f(b) \left( \int_a^b g(x)\,dx - \int_a^\xi g(x)\,dx \right) $$
>Applying interval additivity to the bracketed difference produces $\int_a^b g - \int_a^\xi g = \int_\xi^b g$, establishing the Weierstrass identity.

---
# Pathological Gallery: Counterexamples and Converse Singularities

### Converse Failure of Product Integrability
The theorem on product integrability establishes that $f, g \in \mathcal{R}[a, b] \implies fg \in \mathcal{R}[a, b]$. However, the converse implication:
$$
\begin{gather}
fg \in \mathcal{R}[a, b] \centernot\implies f \in \mathcal{R}[a, b] \quad \text{or} \quad g \in \mathcal{R}[a, b] \tag{43}
\end{gather}
$$
is completely false.

>[!example]- Example: Dirichlet-Type Phase Cancellation
>Consider the classic Dirichlet indicator function $\mathcal{D}: [0, 1] \to \mathbb{R}$ defined by $\mathcal{D}(x) = 1$ for $x \in \mathbb{Q}$ and $\mathcal{D}(x) = 0$ for $x \notin \mathbb{Q}$. As demonstrated in Chapter 1, $\mathcal{D} \notin \mathcal{R}[0, 1]$ because its oscillation is $\omega(\mathcal{D}; \Delta_i) = 1$ on every subinterval.
>
>Define two modified functions $f, g: [0, 1] \to \mathbb{R}$ by:
>$$ f(x) := 2\mathcal{D}(x) - 1 = \begin{cases} 1 & \text{if } x \in \mathbb{Q} \cap [0, 1] \\ -1 & \text{if } x \notin \mathbb{Q} \cap [0, 1] \end{cases} \tag{44} $$
>and set $g(x) := f(x)$. 
>
>For any partition $P$ of $[0, 1]$, every subinterval $\Delta_i$ contains both rational and irrational numbers. Thus:
>$$ m_i = \inf_{\Delta_i} f = -1, \qquad M_i = \sup_{\Delta_i} f = 1 \implies \omega(f; \Delta_i) = 2 \tag{45} $$
>The upper and lower Darboux sums satisfy $S(f; P) = 1(1) = 1$ and $s(f; P) = -1(1) = -1$. Because $S(f; P) - s(f; P) = 2 > 0$ for all partitions, neither $f$ nor $g$ is Riemann integrable:
>$$ f \notin \mathcal{R}[0, 1], \qquad g \notin \mathcal{R}[0, 1] \tag{46} $$
>However, computing their pointwise product yields:
>$$ (fg)(x) = f(x)^2 = (\pm 1)^2 = 1 \quad \text{for all } x \in [0, 1] \tag{47} $$
>The product function $fg \equiv 1$ is a constant function, which is continuous and immediately Riemann integrable as a constant function:
>$$ fg \in \mathcal{R}[0, 1], \qquad \int_0^1 (fg)(x)\,dx = 1 \tag{48} $$
>This counterexample proves that the product of two severely pathological, non-integrable functions can collapse into a smooth, constant integrable function.

### Converse Failure of Absolute Value Integrability
Theorem 5 established that if $f \in \mathcal{R}[a, b]$, then $|f| \in \mathcal{R}[a, b]$. However, the converse proposition:
$$
\begin{gather}
|f| \in \mathcal{R}[a, b] \centernot\implies f \in \mathcal{R}[a, b] \tag{49}
\end{gather}
$$
fails dramatically. The absolute value operation rectifies negative values, destroying sign fluctuations that may prevent the original function from possessing a Riemann limit.
>[!example]- Example: Rectification of Oscillatory Discontinuities
>Reconsider the modified Dirichlet function $f(x)$ defined in step 44 over $[0, 1]$:
>$$ f(x) = \begin{cases} 1 & \text{if } x \in \mathbb{Q} \cap [0, 1] \\ -1 & \text{if } x \notin \mathbb{Q} \cap [0, 1] \end{cases} \tag{50} $$
>As established in step 46, $f$ is nowhere continuous and fails the Darboux integrability criterion on every partition, so $f \notin \mathcal{R}[0, 1]$.
>
>However, taking the pointwise absolute value yields:
>$$ |f(x)| = | \pm 1 | = 1 \quad \text{for all } x \in [0, 1] \tag{51} $$
>The rectified function $|f|$ is everywhere constant on $[0, 1]$, hence $|f| \in C[0, 1] \subset \mathcal{R}[0, 1]$ with $\int_0^1 |f(x)|\,dx = 1$.
>
>Therefore, integrability of the absolute magnitude $|f|$ provides zero guarantee regarding the integrability of the signed function $f$.

### Converse Failure of Positivity
The positivity property guarantees that $f(x) \ge 0 \implies \int_a^b f(x)\,dx \ge 0$. The converse claim:
$$
\begin{gather}
\int_a^b f(x)\,dx \ge 0 \centernot\implies f(x) \ge 0 \quad \text{on } [a, b] \tag{52}
\end{gather}
$$
is elementary to refute, yet conceptually instructive.

>[!example]- Example: Macroscopic Area Offset
>Let $f(x) = x$ on the asymmetric interval $[-1, 2]$. Evaluating the definite integral:
>$$ \int_{-1}^2 x\,dx = \left[ \frac{x^2}{2} \right]_{-1}^2 = \frac{4}{2} - \frac{1}{2} = \frac{3}{2} > 0 \tag{53} $$
>The integral is strictly positive. Yet on the subinterval $[-1, 0)$, $f(x) < 0$, attaining a minimum of $f(-1) = -1$. 
>
>Because the definite integral is a global aggregate, large positive contributions over one subregion can completely overwhelm negative values over another, leaving the total net integral positive despite extensive local negativity.

Furthermore, even if the integral vanishes identically, $\int_a^b f(x)\,dx = 0$, for a non-negative function $f(x) \ge 0$, one cannot conclude that $f(x) \equiv 0$ without continuity:
>[!example]- Example: Measure-Zero Discontinuous Impulses
>Define $f: [0, 1] \to \mathbb{R}$ by:
>$$ f(x) := \begin{cases} 1 & \text{if } x = 1/2 \\ 0 & \text{if } x \in [0, 1] \setminus \{1/2\} \end{cases} \tag{54} $$
>By construction, $f(x) \ge 0$ for all $x \in [0, 1]$, and $f$ is not identically zero since $f(1/2) = 1 > 0$. However, $f$ has only a single point of discontinuity at $x = 1/2$. By the Theorem on Functions with Finitely Many Discontinuities from Chapter 1, $f \in \mathcal{R}[0, 1]$.
>
>For any $\varepsilon > 0$, choosing a partition with a narrow subinterval $[1/2 - \delta, 1/2 + \delta]$ enclosing $x = 1/2$ demonstrates that $S(f; P) \le 2\delta < \varepsilon$, proving:
>$$ \int_0^1 f(x)\,dx = 0 \tag{55} $$
>Thus, $\int_a^b f = 0$ does not imply $f \equiv 0$ unless $f$ is continuous.

### Singularities and Degeneracies of Mean-Value Nodes
The First Mean-Value Theorem guarantees that for $f \in C[a, b]$, there exists $\xi \in [a, b]$ such that $\int_a^b f(x)\,dx = f(\xi)(b - a)$. Two important caveats govern this result: the witness node $\xi$ is generally *not unique*, and if continuity is dropped, such a node $\xi$ may *fail to exist entirely*.

>[!example]- Example: Multiplicity of Mean-Value Nodes
>Consider the oscillatory function $f(x) = \sin(2\pi x)$ on the unit interval $[0, 1]$. The function is smooth, $f \in C^\infty[0, 1]$.
>The integral average is:
>$$ \mu = \frac{1}{1 - 0} \int_0^1 \sin(2\pi x)\,dx = \left[ -\frac{\cos(2\pi x)}{2\pi} \right]_0^1 = -\frac{1}{2\pi} + \frac{1}{2\pi} = 0 \tag{56} $$
>To satisfy the Mean-Value Theorem, one must solve $f(\xi) = \mu = 0$ for $\xi \in [0, 1]$:
>$$ \sin(2\pi \xi) = 0 \implies 2\pi \xi \in \{0, \pi, 2\pi\} \implies \xi \in \left\{ 0, \; \frac{1}{2}, \; 1 \right\} \tag{57} $$
>There exist three distinct nodes within $[a, b]$ (and one strictly interior node $\xi = 1/2 \in (0, 1)$) satisfying the theorem. In general, for oscillatory functions, the set of mean-value nodes can be arbitrarily large.

>[!example]- Example: Total Failure of the Mean-Value Node for Discontinuous Integrands
>Consider the Heaviside step function $H: [0, 1] \to \mathbb{R}$ defined by:
>$$ H(x) := \begin{cases} 0 & \text{if } 0 \le x < 1/2 \\ 1 & \text{if } 1/2 \le x \le 1 \end{cases} \tag{58} $$
>Because $H$ is monotonic and has only one jump discontinuity at $x = 1/2$, $H \in \mathcal{R}[0, 1]$.
>By interval additivity, the integral is:
>$$ \int_0^1 H(x)\,dx = \int_0^{1/2} 0\,dx + \int_{1/2}^1 1\,dx = 0 + 1 \times \left(1 - \frac{1}{2}\right) = \frac{1}{2} \tag{59} $$
>The integral average is:
>$$ \mu = \frac{1}{1 - 0} \int_0^1 H(x)\,dx = \frac{1}{2} \tag{60} $$
>While $\mu = 1/2 \in [m, M] = [0, 1]$ (satisfying Part 1 of Theorem 7), the function $H(x)$ takes only the values $0$ and $1$:
>$$ H([0, 1]) = \{0, 1\} \tag{61} $$
>There exists *no point* $\xi \in [0, 1]$ such that $H(\xi) = 1/2$. Part 2 of the First Mean-Value Theorem fails completely when continuity is violated.

### Breakdown of Weighted Mean-Value Theorems Under Sign Change
The Generalized First Mean-Value Theorem requires that the weight function $g(x)$ maintain a constant sign on $[a, b]$. If this condition is violated, the theorem collapses immediately.

>[!example]- Example: Annihilation of the Weighted Integral via Sign Alternation
>Let $[a, b] = [-1, 1]$. Define the continuous functions:
>$$ f(x) := x, \qquad g(x) := x \tag{62} $$
>Both functions are continuous on $[-1, 1]$, but $g(x)$ changes sign at $x = 0$, being strictly negative on $[-1, 0)$ and strictly positive on $(0, 1]$.
>
>Compute the left-hand side of the Generalized Mean-Value relation:
>$$ \int_{-1}^1 f(x)g(x)\,dx = \int_{-1}^1 x^2\,dx = \left[ \frac{x^3}{3} \right]_{-1}^1 = \frac{1}{3} - \left(-\frac{1}{3}\right) = \frac{2}{3} \tag{63} $$
>Now compute the integral of the weight function alone:
>$$ \int_{-1}^1 g(x)\,dx = \int_{-1}^1 x\,dx = \left[ \frac{x^2}{2} \right]_{-1}^1 = \frac{1}{2} - \frac{1}{2} = 0 \tag{64} $$
>If the Generalized Mean-Value Theorem held, there would exist a number $\mu \in [\inf f, \sup f] = [-1, 1]$ such that:
>$$ \int_{-1}^1 f(x)g(x)\,dx = \mu \int_{-1}^1 g(x)\,dx \implies \frac{2}{3} = \mu \times 0 = 0 \tag{65} $$
>The equation of step 65 is an absolute contradiction ($2/3 = 0$). The failure of $g(x)$ to preserve sign caused the denominator $\int g$ to vanish through destructive cancellation while the coupled product integral $\int fg = \int x^2 > 0$ remained strictly positive.

---
# Applications Involving Linearity, Additivity, and Monotonicity of the Integral 

### Quantitative Finance: Portfolio Risk Dispersion and CBS Inequality Bounds

##### Premise
In continuous-time fixed income mathematics, an institutional investment portfolio generates a continuous stream of cash flows over a finite planning horizon $t \in [0, T]$. Let $c(t) \ge 0$ denote the continuous cash-flow density, and let $r > 0$ be the constant instantaneous discount rate. The present value of the cash-flow stream is given by:
$$ PV := \int_0^T c(t) e^{-r t}\,dt \tag{66} $$
Define the normalized payment probability density $w: [0, T] \to \mathbb{R}$ by:
$$ w(t) := \frac{c(t) e^{-r t}}{PV} \tag{67} $$
Because $c(t) \ge 0$, $w(t) \ge 0$ for all $t \in [0, T]$, and by linearity, $\int_0^T w(t)\,dt = 1$.

The *Macaulay duration* $D$ represents the weighted average payment time of the portfolio:
$$ D := \int_0^T t w(t)\,dt \tag{68} $$
The *convexity second moment* $M_2$ is defined by:
$$ M_2 := \int_0^T t^2 w(t)\,dt \tag{69} $$
In classical Redington and Fong-Vasicek portfolio immunization theory, the vulnerability of the portfolio to non-parallel shifts in the yield curve is governed by the *cash-flow dispersion* (or duration variance):
$$ \sigma_D^2 := \int_0^T (t - D)^2 w(t)\,dt \tag{70} $$

##### Problem Statement
1. Prove analytically via the Cauchy-Bunyakovsky-Schwarz inequality that $M_2 \ge D^2$, and deduce that the dispersion satisfies $\sigma_D^2 \ge 0$ with equality if and only if all cash flows are concentrated at a single maturity.
2. Consider a stylized mortgage-backed security (MBS) cash-flow stream exhibiting delayed amortization modeled by the linear-exponential density:
$$ c(t) = C_0 t e^{-\lambda t}, \quad t \in [0, T] \tag{71} $$
where $C_0 > 0$, $\lambda > 0$, and let $\kappa := r + \lambda$.
Using the Generalized First Mean-Value Theorem, prove that there exists an effective discounting node $\tau \in [0, T]$ such that the duration can be represented as $D = \tau \int_0^T w(t)\,dt = \tau$, and derive the exact closed-form expressions for $PV$, $D$, and $\sigma_D^2$ as functions of $\kappa$ and $T$.
3. For parameters $r = 0.04$, $\lambda = 0.08$ (so $\kappa = 0.12$), and horizon $T = 10\text{ years}$, compute the duration $D$, the dispersion $\sigma_D$, and the sharp Fong-Vasicek immunization risk bound:
$$ \Delta PV / PV \ge -D \Delta r - \frac{1}{2} M_2 (\Delta r)^2 - \frac{1}{2} \sigma_D^2 K_{\text{max}} $$
for a yield shock $\Delta r = 0.01$ and maximum yield curvature $K_{\text{max}} = 0.0025$.

##### Solution

**Step 1: Cauchy-Bunyakovsky-Schwarz Derivation of Dispersion Non-Negativity:**
Consider the functions $f(t) := t \sqrt{w(t)}$ and $g(t) := \sqrt{w(t)}$ on $[0, T]$. 
Because $w(t) \ge 0$ is integrable, both $f$ and $g$ are square-integrable. Apply the Cauchy-Bunyakovsky-Schwarz inequality:
$$ \left( \int_0^T f(t)g(t)\,dt \right)^2 \le \left( \int_0^T f(t)^2\,dt \right) \left( \int_0^T g(t)^2\,dt \right) \tag{72} $$
Evaluate each integral individually:
$$ \int_0^T f(t)g(t)\,dt = \int_0^T t \sqrt{w(t)} \sqrt{w(t)}\,dt = \int_0^T t w(t)\,dt = D \tag{73} $$
$$ \int_0^T f(t)^2\,dt = \int_0^T t^2 w(t)\,dt = M_2 \tag{74} $$
$$ \int_0^T g(t)^2\,dt = \int_0^T w(t)\,dt = 1 \tag{75} $$
Substituting steps 73–75 into step 72 yields:
$$ D^2 \le M_2 \times 1 \implies M_2 \ge D^2 \tag{76} $$
Now expand the definition of cash-flow dispersion:
$$ \sigma_D^2 = \int_0^T (t^2 - 2tD + D^2) w(t)\,dt = \int_0^T t^2 w(t)\,dt - 2D \int_0^T t w(t)\,dt + D^2 \int_0^T w(t)\,dt \tag{77} $$
By linearity, step 77 simplifies to:
$$ \sigma_D^2 = M_2 - 2D(D) + D^2(1) = M_2 - D^2 \tag{78} $$
Because step 76 established $M_2 \ge D^2$, it follows immediately that:
$$ \sigma_D^2 = M_2 - D^2 \ge 0 \tag{79} $$
By the CBS equality condition, equality holds if and only if $f(t) = \alpha g(t)$, meaning $t \sqrt{w(t)} = \alpha \sqrt{w(t)}$ for almost all $t$ where $w(t) \ne 0$. This requires $t = \alpha$ wherever $w(t) > 0$, which corresponds to a zero-coupon bond paying at a single maturity $t = \alpha$.

**Step 2: Analytical Valuation and Duration Computation:**
The cash-flow present value density is $c(t)e^{-rt} = C_0 t e^{-\kappa t}$.
The present value integral is:
$$ PV = C_0 \int_0^T t e^{-\kappa t}\,dt \tag{80} $$
Integrating by parts with $u = t$ and $dv = e^{-\kappa t}dt$:
$$ \int_0^T t e^{-\kappa t}\,dt = \left[ -\frac{t}{\kappa} e^{-\kappa t} \right]_0^T + \frac{1}{\kappa} \int_0^T e^{-\kappa t}\,dt = -\frac{T}{\kappa} e^{-\kappa T} + \frac{1}{\kappa^2} \big( 1 - e^{-\kappa T} \big) \tag{81} $$
Factoring $1/\kappa^2$:
$$ PV = \frac{C_0}{\kappa^2} \Big( 1 - (1 + \kappa T) e^{-\kappa T} \Big) \tag{82} $$
The weight function is:
$$ w(t) = \frac{t e^{-\kappa t}}{\int_0^T u e^{-\kappa u}\,du} \tag{83} $$
By the Generalized First Mean-Value Theorem applied to $f(t) = t$ and the non-negative weight $g(t) = w(t) \ge 0$, there exists $\tau \in [0, T]$ such that:
$$ D = \int_0^T t w(t)\,dt = \tau \int_0^T w(t)\,dt = \tau \tag{84} $$
Thus the Macaulay duration $D$ is precisely the mean-value node $\tau \in (0, T)$.
To find $D$ explicitly, compute $\int_0^T t^2 e^{-\kappa t}\,dt$:
$$ \int_0^T t^2 e^{-\kappa t}\,dt = \left[ -\frac{t^2}{\kappa} e^{-\kappa t} \right]_0^T + \frac{2}{\kappa} \int_0^T t e^{-\kappa t}\,dt = -\frac{T^2}{\kappa} e^{-\kappa T} + \frac{2}{\kappa^3} \Big( 1 - (1 + \kappa T) e^{-\kappa T} \Big) \tag{85} $$
Dividing by the integral in step 81:
$$ D = \frac{-\frac{T^2}{\kappa} e^{-\kappa T} + \frac{2}{\kappa^3} \big( 1 - (1 + \kappa T) e^{-\kappa T} \big)}{\frac{1}{\kappa^2} \big( 1 - (1 + \kappa T) e^{-\kappa T} \big)} = \frac{2}{\kappa} - \frac{T^2 e^{-\kappa T}}{\frac{1}{\kappa} \big( 1 - (1 + \kappa T) e^{-\kappa T} \big)} \tag{86} $$
Similarly, integrating $t^3 e^{-\kappa t}$ evaluates $M_2$, from which $\sigma_D^2 = M_2 - D^2$ is determined.

**Step 3: Numerical Parameter Evaluation:**
For $\kappa = 0.12$ and $T = 10$, compute the dimensionless quantity $\kappa T = 1.20$.
The exponential factor is:
$$ e^{-1.20} \approx 0.301194 \tag{87} $$
Compute the bracketed term in step 82:
$$ 1 - (1 + 1.20)(0.301194) = 1 - 2.20 \times 0.301194 = 1 - 0.662627 = 0.337373 \tag{88} $$
The base integral is:
$$ \int_0^{10} t e^{-0.12 t}\,dt = \frac{0.337373}{(0.12)^2} = \frac{0.337373}{0.0144} \approx 23.4287\text{ years}^2 \tag{89} $$
Now compute the second moment integral:
$$ \int_0^{10} t^2 e^{-0.12 t}\,dt = -\frac{100}{0.12} (0.301194) + \frac{2}{0.12} (23.4287) = -250.995 + 390.478 = 139.483\text{ years}^3 \tag{90} $$
The duration is:
$$ D = \frac{\int_0^{10} t^2 e^{-0.12 t}\,dt}{\int_0^{10} t e^{-0.12 t}\,dt} = \frac{139.483}{23.4287} \approx 5.9535\text{ years} \tag{91} $$
Notice that $D = 5.9535 \in (0, 10)$, verifying the Mean-Value Theorem.
Now compute the third moment integral:
$$ \int_0^{10} t^3 e^{-0.12 t}\,dt = \left[ -\frac{t^3}{0.12} e^{-0.12 t} \right]_0^{10} + \frac{3}{0.12} \int_0^{10} t^2 e^{-0.12 t}\,dt $$
$$ = -\frac{1000}{0.12} (0.301194) + 25 \times 139.483 = -2509.95 + 3487.08 = 977.13\text{ years}^4 \tag{92} $$
The convexity second moment is:
$$ M_2 = \frac{977.13}{23.4287} \approx 41.7065\text{ years}^2 \tag{93} $$
Verify the CBS bound: $M_2 = 41.7065 > D^2 = (5.9535)^2 \approx 35.4442$. The bound holds strictly!
The duration dispersion is:
$$ \sigma_D^2 = M_2 - D^2 = 41.7065 - 35.4442 = 6.2623\text{ years}^2 \tag{94} $$
$$ \sigma_D = \sqrt{6.2623} \approx 2.5025\text{ years} \tag{95} $$
Finally, evaluate the Fong-Vasicek immunization bound for $\Delta r = 0.01$ and $K_{\text{max}} = 0.0025$:
$$ \Delta PV / PV \ge - (5.9535)(0.01) - \frac{1}{2} (41.7065)(0.01)^2 - \frac{1}{2} (6.2623)(0.0025) $$
$$ = -0.059535 - \frac{1}{2} (41.7065)(0.0001) - \frac{1}{2} (0.015656) $$
$$ = -0.059535 - 0.002085 - 0.007828 = -0.069448 \approx -6.94\% \tag{96} $$
The value of the portfolio will decline by at most $6.94\%$ under the specified non-parallel yield curve shock.

### Classical Mechanics: Oscillatory Work Integrals via Bonnet's Second Mean-Value Theorem

##### Premise
Consider a particle of mass $m$ subjected to an underdamped harmonic driving force and linear viscous drag. Over a time interval $t \in [0, T]$, the velocity of the particle decays exponentially due to dissipation, $v(t) = v_0 e^{-\gamma t}$ with $\gamma > 0$, while the applied external force oscillates at driving frequency $\omega > 0$:
$$ F(t) = F_0 \sin(\omega t) \tag{97} $$
The mechanical work delivered to the system by the external force over $[0, T]$ is given by the definite integral:
$$ W(T) := \int_0^T F(t) v(t)\,dt = F_0 v_0 \int_0^T e^{-\gamma t} \sin(\omega t)\,dt \tag{98} $$

##### Problem Statement
1. Verify that the hypotheses of Bonnet's form of the Second Mean-Value Theorem are satisfied by the integrand of step 98.
2. Apply Bonnet's Second Mean-Value Theorem to prove that there exists an intermediate time $\xi \in [0, T]$ such that:
$$ W(T) = \frac{F_0 v_0}{\omega} \big( 1 - \cos(\omega \xi) \big) \tag{99} $$
and deduce the universal, duration-independent upper bound:
$$ |W(T)| \le \frac{2 F_0 v_0}{\omega} \quad \text{for all } T > 0 \text{ and all } \gamma > 0 \tag{100} $$
3. For physical parameters $F_0 = 50\text{ N}$, $v_0 = 4\text{ m/s}$, damping $\gamma = 0.5\text{ s}^{-1}$, driving frequency $\omega = 10\text{ rad/s}$, and terminal time $T = 3\pi / (2\omega) \approx 0.4712\text{ s}$, compute the exact work $W(T)$ and determine the exact numerical value of the mean-value time $\xi \in [0, T]$.

##### Solution

**Step 1: Verification of Bonnet's Hypotheses:**
Decompose the integrand into $f(t) := e^{-\gamma t}$ and $g(t) := \sin(\omega t)$.
1. Monotonicity and Non-Negativity: For $\gamma > 0$, $f'(t) = -\gamma e^{-\gamma t} < 0$, so $f(t)$ is strictly decreasing on $[0, T]$. Furthermore, $f(t) = e^{-\gamma t} > 0$ for all $t \in [0, T]$, so $f$ is non-negative and decreasing.
2. Integrability: The function $g(t) = \sin(\omega t)$ is continuous on $[0, T]$, hence $g \in \mathcal{R}[0, T]$.
All hypotheses of Bonnet's form of the Second Mean-Value Theorem (Theorem 9, Part 1) are satisfied.

**Step 2: Bonnet Reduction and Universal Bound:**
By Bonnet's theorem, there exists $\xi \in [0, T]$ such that:
$$ \int_0^T e^{-\gamma t} \sin(\omega t)\,dt = e^{-\gamma \cdot 0} \int_0^\xi \sin(\omega t)\,dt = 1 \cdot \int_0^\xi \sin(\omega t)\,dt \tag{101} $$
Evaluate the primitive of the sine function:
$$ \int_0^\xi \sin(\omega t)\,dt = \left[ -\frac{\cos(\omega t)}{\omega} \right]_0^\xi = \frac{1 - \cos(\omega \xi)}{\omega} \tag{102} $$
Multiplying by $F_0 v_0$ yields:
$$ W(T) = \frac{F_0 v_0}{\omega} \big( 1 - \cos(\omega \xi) \big) \tag{103} $$
Because $-1 \le \cos(\omega \xi) \le 1$, the bracketed factor satisfies $0 \le 1 - \cos(\omega \xi) \le 2$. 
Therefore:
$$ 0 \le W(T) \le \frac{2 F_0 v_0}{\omega} \tag{104} $$
proving that the absolute work is strictly bounded by $2 F_0 v_0 / \omega$ for *any* duration $T$, no matter how long the force acts, and for *any* damping coefficient $\gamma > 0$.

**Step 3: Exact Evaluation and Witness Node Determination:**
The exact integral is evaluated via integration by parts:
$$ \int_0^T e^{-\gamma t} \sin(\omega t)\,dt = \left[ -\frac{e^{-\gamma t}}{\gamma^2 + \omega^2} \big( \gamma \sin(\omega t) + \omega \cos(\omega t) \big) \right]_0^T $$
$$ = \frac{\omega}{\gamma^2 + \omega^2} - \frac{e^{-\gamma T}}{\gamma^2 + \omega^2} \big( \gamma \sin(\omega T) + \omega \cos(\omega T) \big) \tag{105} $$
Substitute the given parameters: $F_0 = 50$, $v_0 = 4 \implies F_0 v_0 = 200\text{ W}$.
$\gamma = 0.5$, $\omega = 10 \implies \gamma^2 + \omega^2 = 0.25 + 100 = 100.25$.
For $T = \frac{3\pi}{2\omega} = \frac{3\pi}{20} \approx 0.471239\text{ s}$:
$$ \omega T = \frac{3\pi}{2} \implies \sin(\omega T) = -1, \quad \cos(\omega T) = 0 \tag{106} $$
The exponential damping term is:
$$ e^{-\gamma T} = e^{-0.5 \times 0.471239} = e^{-0.235619} \approx 0.790076 \tag{107} $$
Evaluate step 105:
$$ \int_0^T e^{-\gamma t} \sin(\omega t)\,dt = \frac{10}{100.25} - \frac{0.790076}{100.25} \big( 0.5(-1) + 10(0) \big) $$
$$ = \frac{10 - 0.790076(-0.5)}{100.25} = \frac{10 + 0.395038}{100.25} = \frac{10.395038}{100.25} \approx 0.103691\text{ s} \tag{108} $$
The exact work delivered is:
$$ W(T) = 200 \times 0.103691 \approx 20.7382\text{ Joules} \tag{109} $$
The universal upper bound from step 100 is:
$$ W_{\text{max}} = \frac{2(200)}{10} = 40.0\text{ Joules} \tag{110} $$
Because $20.7382 \le 40.0$, the bound is confirmed.
To determine the exact Bonnet node $\xi$, equate step 103 to the exact work:
$$ \frac{200}{10} \big( 1 - \cos(10 \xi) \big) = 20.7382 \implies 20 \big( 1 - \cos(10 \xi) \big) = 20.7382 $$
$$ 1 - \cos(10 \xi) = \frac{20.7382}{20} = 1.03691 \implies \cos(10 \xi) = -0.03691 \tag{111} $$
Taking the principal arccosine:
$$ 10 \xi = \arccos(-0.03691) \approx 1.60771\text{ rad} \tag{112} $$
$$ \xi = \frac{1.60771}{10} \approx 0.16077\text{ s} \tag{113} $$
Because $0 \le 0.16077 \le 0.47124 = T$, the node $\xi$ lies strictly inside the integration interval, verifying Bonnet's Second Mean-Value Theorem with complete precision.

### Chemical Kinetics: Thermal Conversion in Non-Isothermal Continuous Reactors

##### Premise
In chemical reaction engineering, a reactant $A$ decomposes via a first-order irreversible reaction $A \to B$ inside a steady-state plug flow reactor (PFR) of length $L = 5\text{ m}$. The fluid flows axially with uniform interstitial velocity $u = 0.25\text{ m/s}$. The local reaction rate constant $k(z)$ depends on the axial position $z \in [0, L]$ through the Arrhenius temperature relation:
$$ k(z) = k_0 \exp\left( -\frac{E_a}{R T(z)} \right) \tag{114} $$
where $k_0 = 1.5 \times 10^7\text{ s}^{-1}$ is the pre-exponential factor, $E_a = 50.0\text{ kJ/mol}$ is the activation energy, $R = 8.314\text{ J/(mol}\cdot\text{K)}$ is the universal gas constant, and $T(z)$ is the axial temperature profile in Kelvin.
Due to exothermic heat generation balanced by wall cooling, the temperature profile increases linearly along the reactor:
$$ T(z) = T_0 + \beta z, \quad z \in [0, L] \tag{115} $$
with inlet temperature $T_0 = 320\text{ K}$ and temperature gradient $\beta = 12\text{ K/m}$ (so the exit temperature is $T(L) = 320 + 12(5) = 380\text{ K}$).

The Damköhler number across the reactor is given by the integral of the reaction rate:
$$ Da := \frac{1}{u} \int_0^L k(z)\,dz \tag{116} $$
The exit conversion $X_A \in [0, 1]$ is related to $Da$ by $X_A = 1 - e^{-Da}$.

##### Problem Statement
1. Prove that $k(z)$ is strictly increasing on $[0, L]$. Using the monotonicity of the definite integral, establish rigorous upper and lower bounds on the Damköhler number $Da$ using only the inlet and outlet reaction rates.
2. Apply the First Mean-Value Theorem for integrals to prove that there exists an *effective reactor temperature* $T_{\text{eff}} \in (T_0, T(L))$ such that $Da = \frac{L}{u} k_0 \exp\left(-\frac{E_a}{R T_{\text{eff}}}\right)$, and show that $T_{\text{eff}}$ strictly exceeds the spatial average temperature $\bar{T} = \frac{T_0 + T(L)}{2}$.
3. Compute the exact Damköhler number $Da$ and exit conversion $X_A$, and find the exact numerical value of $T_{\text{eff}}$.

##### Solution

**Step 1: Monotonicity and Extremal Rate Bounds:**
Compute the derivative of $k(z)$ with respect to $z$:
$$ \frac{dk}{dz} = k_0 \frac{d}{dz} \left[ \exp\left( -\frac{E_a}{R(T_0 + \beta z)} \right) \right] = k(z) \left( \frac{E_a \beta}{R(T_0 + \beta z)^2} \right) \tag{117} $$
Because $E_a, \beta, R, T(z) > 0$ and $k(z) > 0$, $dk/dz > 0$ for all $z \in [0, L]$. Therefore, $k(z)$ is strictly increasing.
Its minimum occurs at the inlet $z = 0$, and its maximum occurs at the exit $z = L$:
$$ k_{\text{min}} = k(0) = k_0 \exp\left( -\frac{E_a}{R T_0} \right) \tag{118} $$
$$ k_{\text{max}} = k(L) = k_0 \exp\left( -\frac{E_a}{R T(L)} \right) \tag{119} $$
By the monotonicity of the definite integral (Theorem 5, Part 4):
$$ k_{\text{min}} L \le \int_0^L k(z)\,dz \le k_{\text{max}} L \tag{120} $$
Dividing by $u > 0$ yields the rigorous bounds on $Da$:
$$ \frac{L}{u} k_{\text{min}} \le Da \le \frac{L}{u} k_{\text{max}} \tag{121} $$

**Step 2: Mean-Value Effective Temperature and Convexity:**
Because $T(z)$ is continuous and $k(z)$ is continuous on $[0, L]$, the First Mean-Value Theorem (Theorem 7, Part 2) guarantees the existence of a node $\zeta \in (0, L)$ such that:
$$ \int_0^L k(z)\,dz = k(\zeta) L \implies Da = \frac{L}{u} k(\zeta) \tag{122} $$
Define the effective reactor temperature by $T_{\text{eff}} := T(\zeta) = T_0 + \beta \zeta$. 
Then:
$$ Da = \frac{L}{u} k_0 \exp\left( -\frac{E_a}{R T_{\text{eff}}} \right) \tag{123} $$
Because $\zeta \in (0, L)$, $T_0 < T_{\text{eff}} < T(L)$.
Now consider the second derivative of the Arrhenius function $\phi(T) := k_0 \exp(-E_a / (RT))$ with respect to $T$:
$$ \frac{d\phi}{dT} = \phi(T) \frac{E_a}{R T^2} \tag{124} $$
$$ \frac{d^2\phi}{dT^2} = \phi(T) \left( \frac{E_a^2}{R^2 T^4} - \frac{2E_a}{R T^3} \right) = \phi(T) \frac{E_a}{R T^3} \left( \frac{E_a}{R T} - 2 \right) \tag{125} $$
For typical chemical reactions, $E_a / (RT) \gg 2$ (here $50000 / (8.314 \times 380) \approx 15.8 > 2$).
Therefore, $d^2\phi/dT^2 > 0$, meaning $k(T)$ is strictly convex.
By Jensen's inequality for convex functions, the integral average of a convex function strictly exceeds the function evaluated at the average temperature:
$$ \frac{1}{L} \int_0^L k(z)\,dz = k(T_{\text{eff}}) > k(\bar{T}) \tag{126} $$
Because $k(T)$ is strictly increasing, $k(T_{\text{eff}}) > k(\bar{T})$ implies:
$$ T_{\text{eff}} > \bar{T} = \frac{T_0 + T(L)}{2} \tag{127} $$
The effective kinetic temperature of the reactor is strictly higher than the arithmetic mean temperature due to the exponential sensitivity of reaction rates at elevated temperatures.

**Step 3: Numerical Evaluation:**
Compute the parameters:
$\frac{E_a}{R} = \frac{50000}{8.314} \approx 6013.95\text{ K}$.
At $T_0 = 320\text{ K}$:
$$ \frac{E_a}{R T_0} = \frac{6013.95}{320} \approx 18.7936 \implies k(0) = 1.5 \times 10^7 \times e^{-18.7936} \approx 0.10375\text{ s}^{-1} \tag{128} $$
At $T(L) = 380\text{ K}$:
$$ \frac{E_a}{R T(L)} = \frac{6013.95}{380} \approx 15.8262 \implies k(L) = 1.5 \times 10^7 \times e^{-15.8262} \approx 2.0125\text{ s}^{-1} \tag{129} $$
Notice that the reaction rate increases by a factor of $2.0125 / 0.10375 \approx 19.4$ along the reactor!
The Damköhler bounds from step 121 are:
$$ Da_{\text{min}} = \frac{5}{0.25} \times 0.10375 = 20 \times 0.10375 = 2.075 \tag{130} $$
$$ Da_{\text{max}} = 20 \times 2.0125 = 40.25 \tag{131} $$
To evaluate the exact integral $\int_0^L k(z)\,dz$, substitute $T = T_0 + \beta z$, so $dz = dT / \beta$:
$$ \int_0^5 k(z)\,dz = \frac{k_0}{\beta} \int_{320}^{380} \exp\left(-\frac{E_a}{RT}\right) dT \tag{132} $$
Substitute $u = \frac{E_a}{RT}$, so $T = \frac{E_a}{Ru}$ and $dT = -\frac{E_a}{Ru^2} du$:
$$ \int_{320}^{380} \exp\left(-\frac{E_a}{RT}\right) dT = \frac{E_a}{R} \int_{15.8262}^{18.7936} \frac{e^{-u}}{u^2}\,du \tag{133} $$
Using the standard two-term asymptotic expansion $\int_u^\infty \frac{e^{-t}}{t^2} dt \approx \frac{e^{-u}}{u^2} (1 - \frac{2}{u})$:
At $u_1 = 15.8262$: $\frac{e^{-15.8262}}{(15.8262)^2} (1 - \frac{2}{15.8262}) \approx \frac{1.3417 \times 10^{-7}}{250.47} (0.8736) \approx 4.680 \times 10^{-10}\text{ K}$.
At $u_2 = 18.7936$: $\frac{e^{-18.7936}}{(18.7936)^2} (1 - \frac{2}{18.7936}) \approx \frac{6.9168 \times 10^{-9}}{353.20} (0.8936) \approx 1.750 \times 10^{-11}\text{ K}$.
Difference $\approx (4.680 - 0.175) \times 10^{-10} = 4.505 \times 10^{-10}\text{ K}$.
Multiply by $\frac{E_a}{R} = 6013.95$:
$$ \int_{320}^{380} \exp\left(-\frac{E_a}{RT}\right) dT \approx 6013.95 \times 4.505 \times 10^{-10} \approx 2.709 \times 10^{-6}\text{ K} \tag{134} $$
Now compute $\int_0^5 k(z)\,dz$:
$$ \int_0^5 k(z)\,dz = \frac{1.5 \times 10^7}{12} \times 2.709 \times 10^{-6} \approx 1.25 \times 10^6 \times 2.709 \times 10^{-6} \approx 3.386\text{ m/s} \tag{135} $$
The exact Damköhler number is:
$$ Da = \frac{3.386}{0.25} \approx 13.544 \tag{136} $$
Notice that $Da = 13.544$ lies strictly within the predicted bounds $[2.075, 40.25]$.
The reactant conversion is:
$$ X_A = 1 - e^{-13.544} \approx 1 - 1.31 \times 10^{-6} \approx 0.9999987 \approx 99.9999\% \tag{137} $$
Now find the effective temperature $T_{\text{eff}}$:
$$ k(T_{\text{eff}}) = \frac{Da \times u}{L} = \frac{3.386}{5} = 0.6772\text{ s}^{-1} \tag{138} $$
Equating to the Arrhenius rate:
$$ 1.5 \times 10^7 \exp\left(-\frac{6013.95}{T_{\text{eff}}}\right) = 0.6772 \implies \exp\left(-\frac{6013.95}{T_{\text{eff}}}\right) = \frac{0.6772}{1.5 \times 10^7} \approx 4.5147 \times 10^{-8} \tag{139} $$
$$ -\frac{6013.95}{T_{\text{eff}}} = \ln(4.5147 \times 10^{-8}) \approx -16.9118 \implies T_{\text{eff}} = \frac{6013.95}{16.9118} \approx 355.61\text{ K} \tag{140} $$
The arithmetic mean temperature is:
$$ \bar{T} = \frac{320 + 380}{2} = 350.0\text{ K} \tag{141} $$
Comparing step 140 and step 141:
$$ T_{\text{eff}} = 355.61\text{ K} > 350.0\text{ K} = \bar{T} \tag{142} $$
confirming the theoretical prediction that the effective kinetic temperature strictly exceeds the spatial average.

### Biomedical Engineering: Hemodynamic Cardiac Output and Stewart-Hamilton Transits

##### Premise
In cardiovascular medicine and hemodynamic monitoring, the *Stewart-Hamilton indicator dilution technique* represents the gold standard for measuring cardiac output (the volumetric flow rate of blood pumped by the heart, denoted $Q$). A known mass $m_0$ of a biocompatible indicator (such as indocyanine green) is rapidly injected as a bolus into the pulmonary artery. The downstream blood concentration $C(t)$ is measured continuously at a peripheral systemic artery (e.g., the femoral artery) over the observation window $t \in [0, T]$.
By the principle of conservation of mass, the total injected mass equals the integral of the mass flow rate:
$$ m_0 = \int_0^T Q(t) C(t)\,dt \tag{143} $$
Assuming steady mean blood flow $Q(t) \equiv Q$, linearity of the integral yields the classical Stewart-Hamilton formula:
$$ Q = \frac{m_0}{\int_0^T C(t)\,dt} \tag{144} $$
The *mean transit time* (MTT) represents the average duration required for indicator molecules to traverse the cardiopulmonary vascular circuit:
$$ MTT := \frac{\int_0^T t C(t)\,dt}{\int_0^T C(t)\,dt} \tag{145} $$
The central vascular blood volume is then determined via the volume-transit relation $V_{\text{central}} = Q \times MTT$.

In clinical hemodynamics, the concentration curve decomposes naturally into primary cardiopulmonary transit and systemic recirculation. Using interval additivity, the total domain $[0, T]$ is split at $t_c$ (the onset of recirculation):
$$ \int_0^T C(t)\,dt = \int_0^{t_c} C_{\text{primary}}(t)\,dt + \int_{t_c}^T C_{\text{recirc}}(t)\,dt \tag{146} $$
The primary transit is accurately described by the classical gamma-variate distribution:
$$ C(t) = C_0 \left(\frac{t}{t_p}\right)^\alpha \exp\left( -\alpha \left(\frac{t}{t_p} - 1\right) \right), \quad t \in [0, t_c] \tag{147} $$
where $t_p$ is the time of peak concentration, $C_0 = C(t_p)$ is the peak concentration, and $\alpha > 0$ is a dimensionless shape parameter.

##### Problem Statement
1. Apply the Generalized First Mean-Value Theorem to prove that $MTT \in (0, T)$ corresponds to an exact evaluation node $\xi$ for the identity function $f(t) = t$.
2. Consider an injection of $m_0 = 10\text{ mg}$ of dye. Over the primary phase $[0, t_c]$ with $t_c = 30\text{ s}$, the curve parameters are $t_p = 10\text{ s}$, $C_0 = 2.5\text{ mg/L}$, and $\alpha = 2$. Recirculation over $[30, 60]\text{ s}$ adds an integrated exposure of $\int_{30}^{60} C(t)\,dt = 12.5\text{ (mg}\cdot\text{s)/L}$, with recirculation transit integral $\int_{30}^{60} t C(t)\,dt = 525\text{ (mg}\cdot\text{s}^2)\text{/L}$.
Using interval additivity, calculate the total integrated concentration exposure $\int_0^{60} C(t)\,dt$, the cardiac output $Q$ in $\text{L/min}$, the overall mean transit time $MTT$, and the central blood volume $V_{\text{central}}$ in liters.

##### Solution

**Step 1: Mean Transit Time as a Mean-Value Node:**
Because $C(t) \ge 0$ is the physical mass concentration of dye, the weight function $g(t) := C(t)$ is non-negative on $[0, T]$. 
Apply the Generalized First Mean-Value Theorem (Theorem 8, Part 2) with $f(t) = t$ and $g(t) = C(t)$. 
Because $f(t)$ is continuous and $C(t) \ge 0$, there exists an intermediate point $\xi \in [0, T]$ such that:
$$ \int_0^T t C(t)\,dt = \xi \int_0^T C(t)\,dt \tag{148} $$
Dividing by $\int_0^T C(t)\,dt > 0$ yields:
$$ MTT = \frac{\int_0^T t C(t)\,dt}{\int_0^T C(t)\,dt} = \xi \tag{149} $$
Thus, the mean transit time $MTT$ is identically the mean-value evaluation node $\xi \in (0, T)$.

**Step 2: Analytical Integration of the Primary Exposure:**
For $\alpha = 2$ and $t_p = 10\text{ s}$, the primary concentration curve of step 147 is:
$$ C(t) = 2.5 \left(\frac{t}{10}\right)^2 \exp\left( -2 \left(\frac{t}{10} - 1\right) \right) = 2.5 \frac{t^2}{100} e^2 e^{-0.2 t} = 0.025 e^2 t^2 e^{-0.2 t} \tag{150} $$
The constant prefactor is:
$$ K := 0.025 e^2 \approx 0.025 \times 7.389056 \approx 0.184726\text{ mg/(L}\cdot\text{s}^2) \tag{151} $$
The primary exposure integral is:
$$ I_0 := \int_0^{30} C(t)\,dt = K \int_0^{30} t^2 e^{-0.2 t}\,dt \tag{152} $$
Let $u = 0.2 t$, so $t = 5u$ and $dt = 5 du$. The upper limit becomes $u = 0.2(30) = 6$:
$$ \int_0^{30} t^2 e^{-0.2 t}\,dt = \int_0^6 (25 u^2) e^{-u} (5 du) = 125 \int_0^6 u^2 e^{-u}\,du \tag{153} $$
Using the standard repeated integration by parts formula $\int u^2 e^{-u} du = -e^{-u}(u^2 + 2u + 2)$:
$$ \int_0^6 u^2 e^{-u}\,du = \left[ -e^{-u}(u^2 + 2u + 2) \right]_0^6 = 2 - e^{-6}(36 + 12 + 2) = 2 - 50 e^{-6} \tag{154} $$
Because $e^{-6} \approx 0.00247875$:
$$ 2 - 50(0.00247875) = 2 - 0.123938 = 1.876062 \tag{155} $$
Thus:
$$ \int_0^{30} t^2 e^{-0.2 t}\,dt = 125 \times 1.876062 \approx 234.5078\text{ s}^3 \tag{156} $$
The primary exposure is:
$$ I_0 = 0.184726 \times 234.5078 \approx 43.320\text{ (mg}\cdot\text{s)/L} \tag{157} $$
Now compute the first moment integral for the primary transit:
$$ J_0 := \int_0^{30} t C(t)\,dt = K \int_0^{30} t^3 e^{-0.2 t}\,dt \tag{158} $$
Transforming variables with $t = 5u$:
$$ \int_0^{30} t^3 e^{-0.2 t}\,dt = \int_0^6 (125 u^3) e^{-u} (5 du) = 625 \int_0^6 u^3 e^{-u}\,du \tag{159} $$
Integrating by parts $\int u^3 e^{-u} du = -e^{-u}(u^3 + 3u^2 + 6u + 6)$:
$$ \int_0^6 u^3 e^{-u}\,du = \left[ -e^{-u}(u^3 + 3u^2 + 6u + 6) \right]_0^6 = 6 - e^{-6}(216 + 108 + 36 + 6) = 6 - 366 e^{-6} \tag{160} $$
$$ 6 - 366(0.00247875) = 6 - 0.907223 = 5.092777 \tag{161} $$
Thus:
$$ \int_0^{30} t^3 e^{-0.2 t}\,dt = 625 \times 5.092777 \approx 3182.986\text{ s}^4 \tag{162} $$
The primary first moment is:
$$ J_0 = 0.184726 \times 3182.986 \approx 587.981\text{ (mg}\cdot\text{s}^2)\text{/L} \tag{163} $$

**Step 3: Domain Additivity and Hemodynamic Synthesis:**
By interval additivity (Theorem 3):
$$ I_{\text{total}} = \int_0^{60} C(t)\,dt = \int_0^{30} C(t)\,dt + \int_{30}^{60} C(t)\,dt = 43.320 + 12.500 = 55.820\text{ (mg}\cdot\text{s)/L} \tag{164} $$
$$ J_{\text{total}} = \int_0^{60} t C(t)\,dt = \int_0^{30} t C(t)\,dt + \int_{30}^{60} t C(t)\,dt = 587.981 + 525.000 = 1112.981\text{ (mg}\cdot\text{s}^2)\text{/L} \tag{165} $$
Compute the cardiac output $Q$ from step 144 with $m_0 = 10\text{ mg}$:
$$ Q = \frac{10\text{ mg}}{55.820\text{ (mg}\cdot\text{s)/L}} \approx 0.179147\text{ L/s} \tag{166} $$
Converting to standard clinical units ($\text{L/min}$):
$$ Q = 0.179147 \times 60 \approx 10.749\text{ L/min} \tag{167} $$
Compute the overall mean transit time $MTT$:
$$ MTT = \frac{J_{\text{total}}}{I_{\text{total}}} = \frac{1112.981}{55.820} \approx 19.939\text{ seconds} \tag{168} $$
Notice that $MTT = 19.939 \in (0, 60)$, verifying Theorem 8.
Finally, determine the central blood volume:
$$ V_{\text{central}} = Q \times MTT = (0.179147\text{ L/s}) \times (19.939\text{ s}) \approx 3.572\text{ Liters} \tag{169} $$
The patient exhibits a cardiac output of $10.75\text{ L/min}$ and a central vascular volume of $3.57\text{ L}$.

### Structural Engineering: Bending Moment Envelopes and Elastic Beam Deflections

##### Premise
In structural mechanics, a simply supported elastic beam of length $L = 10\text{ m}$ and uniform flexural rigidity $EI = 4.0 \times 10^7\text{ N}\cdot\text{m}^2$ spans the horizontal domain $x \in [0, L]$. The beam supports a piecewise continuous transverse distributed load $q(x)$:
$$ q(x) = \begin{cases} q_0 & \text{if } 0 \le x < L/2 \\ q_0 \left( 2 - \frac{2x}{L} \right) & \text{if } L/2 \le x \le L \end{cases} \tag{170} $$
where $q_0 = 12\text{ kN/m} = 12000\text{ N/m}$. The load is uniform over the left half, and linearly tapers to zero over the right half.

The downward vertical deflection $w(x)$ of the beam at any point $x \in [0, L]$ is governed by the Euler-Bernoulli beam equation:
$$ EI \frac{d^2 w}{dx^2} = -M(x) \tag{171} $$
where $M(x)$ is the internal bending moment.
By Green's function theory, the mid-span deflection $w(L/2)$ can be expressed directly as an integral of the bending moment:
$$ w(L/2) = \frac{1}{EI} \int_0^L G(x) M(x)\,dx \tag{172} $$
where $G(x) := G(L/2, x)$ is the influence Green's function for the mid-span deflection of a simply supported beam:
$$ G(x) = \begin{cases} \frac{x}{2} & \text{if } 0 \le x \le L/2 \\ \frac{L - x}{2} & \text{if } L/2 < x \le L \end{cases} \tag{173} $$
The total elastic strain energy stored in the deformed beam is:
$$ U := \frac{1}{2EI} \int_0^L M(x)^2\,dx \tag{174} $$

##### Problem Statement
1. Use interval additivity of the integral to calculate the total downward load $W_{\text{total}} = \int_0^L q(x)\,dx$ and the reaction forces $R_A, R_B$ at the supports $x = 0$ and $x = L$.
2. Formulate the bending moment $M(x)$ across both subintervals $[0, L/2]$ and $[L/2, L]$. Prove via the Cauchy-Bunyakovsky-Schwarz inequality that the mid-span deflection is strictly bounded by the total strain energy:
$$ |w(L/2)| \le \frac{1}{EI} \sqrt{2EI \cdot U} \cdot \|G\|_{L^2} = \sqrt{\frac{2U}{EI}} \cdot \|G\|_{L^2} \tag{175} $$
and evaluate the $L^2$ norm $\|G\|_{L^2} = \left(\int_0^L G(x)^2\,dx\right)^{1/2}$.
3. Calculate the exact bending moment distribution $M(x)$, the exact total strain energy $U$, the exact mid-span deflection $w(L/2)$, and verify that the CBS inequality bound of step 175 is satisfied.

##### Solution

**Step 1: Total Load and Support Reactions via Interval Additivity:**
By interval additivity (Theorem 3):
$$ W_{\text{total}} = \int_0^{10} q(x)\,dx = \int_0^5 q_0\,dx + \int_5^{10} q_0 \left( 2 - \frac{x}{5} \right) dx \tag{176} $$
Evaluate the sub-integrals:
$$ \int_0^5 q_0\,dx = 5 q_0 = 5 \times 12000 = 60000\text{ N} \tag{177} $$
$$ \int_5^{10} \left( 2 - \frac{x}{5} \right) dx = \left[ 2x - \frac{x^2}{10} \right]_5^{10} = (20 - 10) - \left(10 - \frac{25}{10}\right) = 10 - 7.5 = 2.5\text{ m} \tag{178} $$
$$ \int_5^{10} q(x)\,dx = 2.5 q_0 = 2.5 \times 12000 = 30000\text{ N} \tag{179} $$
The total applied load is:
$$ W_{\text{total}} = 60000 + 30000 = 90000\text{ N} = 90\text{ kN} \tag{180} $$
Now compute the total moment about the left support $x = 0$:
$$ M_0 = \int_0^L x q(x)\,dx = \int_0^5 x q_0\,dx + \int_5^{10} x q_0 \left( 2 - \frac{x}{5} \right) dx \tag{181} $$
$$ \int_0^5 x\,dx = \left[ \frac{x^2}{2} \right]_0^5 = 12.5\text{ m}^2 \tag{182} $$
$$ \int_5^{10} \left( 2x - \frac{x^2}{5} \right) dx = \left[ x^2 - \frac{x^3}{15} \right]_5^{10} = \left(100 - \frac{1000}{15}\right) - \left(25 - \frac{125}{15}\right) $$
$$ = \left(100 - 66.667\right) - \left(25 - 8.333\right) = 33.333 - 16.667 = 16.667 = \frac{50}{3}\text{ m}^2 \tag{183} $$
Total moment:
$$ M_0 = 12000 \times \left( 12.5 + \frac{50}{3} \right) = 12000 \times \frac{87.5}{3} = 4000 \times 87.5 = 350000\text{ N}\cdot\text{m} \tag{184} $$
By static equilibrium, $R_B L = M_0$:
$$ R_B = \frac{350000}{10} = 35000\text{ N} = 35\text{ kN} \tag{185} $$
$$ R_A = W_{\text{total}} - R_B = 90000 - 35000 = 55000\text{ N} = 55\text{ kN} \tag{186} $$

**Step 2: Cauchy-Bunyakovsky-Schwarz Deflection Bound:**
Apply the CBS inequality (Theorem 6) to the deflection integral of step 172:
$$ |w(L/2)| = \frac{1}{EI} \left| \int_0^L G(x) M(x)\,dx \right| \le \frac{1}{EI} \left( \int_0^L G(x)^2\,dx \right)^{1/2} \left( \int_0^L M(x)^2\,dx \right)^{1/2} \tag{187} $$
By definition of strain energy, $\int_0^L M(x)^2\,dx = 2EI \cdot U$. 
Substituting this into step 187 gives:
$$ |w(L/2)| \le \frac{1}{EI} \|G\|_{L^2} \sqrt{2EI \cdot U} = \sqrt{\frac{2U}{EI}} \|G\|_{L^2} \tag{188} $$
Now evaluate $\|G\|_{L^2}^2$:
By symmetry of $G(x)$ about $x = L/2 = 5$:
$$ \|G\|_{L^2}^2 = \int_0^{10} G(x)^2\,dx = 2 \int_0^5 \left(\frac{x}{2}\right)^2 dx = 2 \int_0^5 \frac{x^2}{4}\,dx = \frac{1}{2} \left[ \frac{x^3}{3} \right]_0^5 = \frac{1}{2} \times \frac{125}{3} = \frac{125}{6}\text{ m}^3 \tag{189} $$
Taking the square root:
$$ \|G\|_{L^2} = \sqrt{\frac{125}{6}} \approx \sqrt{20.8333} \approx 4.56435\text{ m}^{3/2} \tag{190} $$

**Step 3: Exact Moment Field and Mid-Span Deflection:**
For $x \in [0, 5]$:
$$ M(x) = R_A x - \int_0^x q_0 (x - u)\,du = 55000 x - 6000 x^2 \tag{191} $$
At the mid-span $x = 5$:
$$ M(5) = 55000(5) - 6000(25) = 275000 - 150000 = 125000\text{ N}\cdot\text{m} = 125\text{ kN}\cdot\text{m} \tag{192} $$
For $x \in [5, 10]$, working from the right support $R_B = 35000\text{ N}$ with coordinate $s := 10 - x \in [0, 5]$:
The load from the right is $q(s) = q_0 \frac{2s}{10} = \frac{12000}{5} s = 2400 s$.
The bending moment from the right is:
$$ M(s) = R_B s - \int_0^s 2400 u (s - u)\,du = 35000 s - 2400 \left[ \frac{s u^2}{2} - \frac{u^3}{3} \right]_0^s = 35000 s - 400 s^3 \tag{193} $$
At $s = 5$ ($x = 5$):
$$ M(s=5) = 35000(5) - 400(125) = 175000 - 50000 = 125000\text{ N}\cdot\text{m} \tag{194} $$
which matches step 192, confirming continuity of $M(x)$ across the partition node $x = 5$.

Now compute the exact mid-span deflection using step 172:
$$ w(5) = \frac{1}{EI} \left( \int_0^5 \frac{x}{2} M(x)\,dx + \int_0^5 \frac{s}{2} M(s)\,ds \right) \tag{195} $$
Evaluate the left integral:
$$ \int_0^5 \frac{x}{2} (55000 x - 6000 x^2)\,dx = \int_0^5 (27500 x^2 - 3000 x^3)\,dx $$
$$ = 27500 \left(\frac{125}{3}\right) - 3000 \left(\frac{625}{4}\right) = 1145833.33 - 468750 = 677083.33\text{ N}\cdot\text{m}^3 \tag{196} $$
Evaluate the right integral:
$$ \int_0^5 \frac{s}{2} (35000 s - 400 s^3)\,ds = \int_0^5 (17500 s^2 - 200 s^4)\,ds $$
$$ = 17500 \left(\frac{125}{3}\right) - 200 \left(\frac{3125}{5}\right) = 729166.67 - 125000 = 604166.67\text{ N}\cdot\text{m}^3 \tag{197} $$
Summing the two integrals gives the total numerator:
$$ \int_0^{10} G(x) M(x)\,dx = 677083.33 + 604166.67 = 1281250\text{ N}\cdot\text{m}^3 \tag{198} $$
The exact mid-span deflection is:
$$ w(5) = \frac{1281250}{4.0 \times 10^7} = 0.03203125\text{ m} \approx 32.03\text{ mm} \tag{199} $$
Now compute the total strain energy $U$:
$$ 2EI \cdot U = \int_0^5 (55000 x - 6000 x^2)^2 dx + \int_0^5 (35000 s - 400 s^3)^2 ds \tag{200} $$
Left integral:
$$ \int_0^5 (3.025 \times 10^9 x^2 - 6.6 \times 10^8 x^3 + 3.6 \times 10^7 x^4)\,dx $$
$$ = 3.025 \times 10^9 \left(\frac{125}{3}\right) - 6.6 \times 10^8 \left(\frac{625}{4}\right) + 3.6 \times 10^7 \left(\frac{3125}{5}\right) $$
$$ = 1.260417 \times 10^{11} - 1.031250 \times 10^{11} + 2.2500 \times 10^{10} = 4.541667 \times 10^{10}\text{ N}^2\cdot\text{m}^3 \tag{201} $$
Right integral:
$$ \int_0^5 (1.225 \times 10^9 s^2 - 2.8 \times 10^7 s^4 + 1.6 \times 10^5 s^6)\,ds $$
$$ = 1.225 \times 10^9 \left(\frac{125}{3}\right) - 2.8 \times 10^7 \left(\frac{3125}{5}\right) + 1.6 \times 10^5 \left(\frac{78125}{7}\right) $$
$$ = 5.104167 \times 10^{10} - 1.7500 \times 10^{10} + 1.7857 \times 10^9 = 3.532738 \times 10^{10}\text{ N}^2\cdot\text{m}^3 \tag{202} $$
Total moment square integral:
$$ \int_0^{10} M(x)^2\,dx = (4.541667 + 3.532738) \times 10^{10} = 8.074405 \times 10^{10}\text{ N}^2\cdot\text{m}^3 \tag{203} $$
The strain energy is:
$$ U = \frac{8.074405 \times 10^{10}}{2 \times 4.0 \times 10^7} = \frac{8.074405 \times 10^{10}}{8.0 \times 10^7} \approx 1009.30\text{ Joules} \tag{204} $$
Now compute the CBS upper bound from step 188:
$$ w_{\text{CBS}} = \frac{1}{EI} \|G\|_{L^2} \|M\|_{L^2} = \frac{1}{4.0 \times 10^7} \times \sqrt{20.8333} \times \sqrt{8.074405 \times 10^{10}} $$
$$ = \frac{1}{4.0 \times 10^7} \times 4.56435 \times 284155 \approx \frac{1297000}{4.0 \times 10^7} \approx 0.032425\text{ m} = 32.43\text{ mm} \tag{205} $$
Comparing the exact deflection from step 199 to the CBS bound from step 205:
$$ w(5) = 32.03\text{ mm} \le 32.43\text{ mm} = w_{\text{CBS}} \tag{206} $$
The Cauchy-Bunyakovsky-Schwarz bound is satisfied with remarkable precision, capturing the true physical deflection within $1.25\%$ error.
