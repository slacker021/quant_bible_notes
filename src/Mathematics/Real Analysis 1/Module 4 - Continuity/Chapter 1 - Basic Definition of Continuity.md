---
dg-publish: true
---
# Foundations of Continuity and Discontinuity
Mathematical models across the quantitative sciences rely fundamentally on the preservation of proximity. When an econometrician perturbs a risk factor, an engineer alters an external load, a neurobiologist measures an incoming sensory stimulus, or an options market maker hedges an inventory position, the validity of the underlying model depends upon whether a sufficiently small adjustment in the input guarantees a controlled, bounded change in the output state. The rigorous formulation of this stability property is *continuity*.

In classical analysis, continuity is not an innate property of physical space, nor is it merely the absence of visual breaks in a drawn curve. Rather, it is a precise metric and topological regularity condition governing how mappings interact with domain topologies, accumulation points, and neighborhood filter bases. 

---
# Pointwise Continuity

### The Problem of Local Preservation
Let $E \subseteq \mathbb{R}$ represent an arbitrary non-empty subset of the real numbers, and let the mapping $f: E \to \mathbb{R}$ denote a real-valued function defined on $E$. Additionally, consider a fixed point $a \in E$. The central problem of local continuity consists of determining whether the functional values $f(x)$ can be kept arbitrarily close to $f(a)$ solely by constraining the argument $x \in E$ to a sufficiently tight neighborhood centered at $a$: 
$$\begin{gather}
\textbf{Definition: Pointwise Continuity (Metric } \varepsilon\text{-}\delta \textbf{ Formulation)} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } f: E \to \mathbb{R}, \text{ and let } a \in E. \\[2mm]
\text{The function } f \text{ is continuous at the point } a \text{ if for every positive tolerance } \varepsilon > 0, \\[2mm]
\text{there exists a corresponding distance } \delta > 0 \text{ such that for all } x \in E, \\[2mm]
\text{the condition } |x - a| < \delta \text{ strictly guarantees that } |f(x) - f(a)| < \varepsilon\text{:} \\[3.5mm]
\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon\big)
\end{gather}$$

Notice that the punctured inequality $0 < |x - a|$, which is mandatory when evaluating functional limits at accumulation points, is deliberately absent here. Because $a \in E$, evaluating the condition at $x = a$ yields $|a - a| = 0 < \delta$, which immediately implies $|f(a) - f(a)| = 0 < \varepsilon$ for every $\varepsilon > 0$.

```easy-tikz
title $\text{The } (\varepsilon, \delta) \text{ Metric Window of Pointwise Continuity}$
xlabel $x$
ylabel $f(x)$
show x from 0 to 7.5 and y from 0 to 5.5
axes on the edges
size 12 x 8
R_eps: shade where x >= 0.2 and x <= 7.0 and y >= 1.7 and y <= 3.7, in red, opacity 0.08, not filled
R_del: shade where x >= 2.3 and x <= 4.7 and y >= 0.2 and y <= 4.8, in blue, opacity 0.08, not filled
R_box: shade where x >= 2.3 and x <= 4.7 and y >= 1.7 and y <= 3.7, in purple, opacity 0.18, with a dashed outline
draw a segment from (0.2, 3.7) to (7.0, 3.7), in red, dashed
draw a segment from (0.2, 1.7) to (7.0, 1.7), in red, dashed
draw a segment from (2.3, 0.2) to (2.3, 4.8), in blue, dashed
draw a segment from (4.7, 0.2) to (4.7, 4.8), in blue, dashed
draw a segment from (0.2, 2.7) to (3.5, 2.7), in gray, dashed
draw a segment from (3.5, 0.2) to (3.5, 2.7), in gray, dashed
plot f(x) = 2.7 + 0.55*(x - 3.5) + 0.06*(x - 3.5)^3, from x = 0.8 to 6.0, in teal, very thick
mark (3.5, 2.7), in black, large
draw a brace from (2.3, 3.85) to (3.5, 3.85), in blue, labelled "$\\delta$"
draw a brace from (3.5, 3.85) to (4.7, 3.85), in blue, labelled "$\\delta$"
draw a brace from (4.85, 3.7) to (4.85, 2.7), in red, labelled "$\\varepsilon$"
draw a brace from (4.85, 2.7) to (4.85, 1.7), in red, labelled "$\\varepsilon$"
write "$a - \\delta$" at (1.97, 0.7) in blue, below
write "$a$" at (3.5, 0.15), in black, below
write "$a + \\delta$" at (5.15, 0.75) in blue, below
write "$f(a) + \\varepsilon$" at (0.85, 3.75), in red, above
write "$f(a)$" at (0.65, 2.75), in black, above
write "$f(a) - \\varepsilon$" at (0.85, 1.65), in red, below
write "$(a, f(a))$" at (3.55, 2.50), in black, right
write "$y= f(x)$" at (5.9, 4.6) in teal, right
```


Translating the metric intervals $(a - \delta, a + \delta)$ and $(f(a) - \varepsilon, f(a) + \varepsilon)$ into open topological sets yields the coordinate-free characterization:
$$\begin{gather}
\textbf{Definition: Pointwise Continuity (Topological Neighborhood Formulation)} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } f: E \to \mathbb{R}, \text{ and let } a \in E. \\[2mm]
\text{The mapping } f \text{ is continuous at the point } a \text{ if for every open neighborhood } V(f(a)) \text{ of } f(a) \text{ in } \mathbb{R}, \\[2mm]
\text{there exists an open neighborhood } U(a) \text{ of } a \text{ in } \mathbb{R} \text{ such that the direct image of } U(a) \cap E \\[2mm]
\text{under } f \text{ is entirely contained within } V(f(a))\text{:} \\[3.5mm]
\forall V(f(a)), \ \exists U(a) \quad \text{such that} \quad f(U(a) \cap E) \subseteq V(f(a))
\end{gather}$$

### The Isolated Point Phenomenon
The presence or absence of neighboring domain points profoundly alters the operational meaning of continuity. Recall from [[Chapter 3 - Basic Lemmas Connected with the Completeness of the Real Numbers|limit points]] that a point $a \in E$ is an accumulation point of $E$ ($a \in E'$) if every punctured neighborhood $\mathring{U}(a) := U(a) \setminus \{a\}$ contains at least one element of $E$. Conversely, if $a \in E$ is not an accumulation point, it is an *isolated point* of $E$: 
$$\begin{gather}
\textbf{Lemma: Vacuous Continuity at Isolated Domain Points} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{If } a \in E \setminus E' \text{ is an isolated point of } E, \text{ then } f \text{ is automatically continuous at } a.
\end{gather}$$
(see [[Proof of the Vacuous Continuity at Isolated Domain Points]])

Because an isolated point $a \in E$ admits an open radius $\delta_0 > 0$ such that $(a - \delta_0, a + \delta_0) \cap E = \{a\}$, the antecedent $|x - a| < \delta_0$ for $x \in E$ forces $x = a$. The consequent $|f(a) - f(a)| = 0 < \varepsilon$ is satisfied unconditionally for every $\varepsilon > 0$. 

Consequently, continuity at an isolated point carries zero analytical information regarding the functional behavior of $f$; it is a purely topological artifact of domain isolation. The substantive mathematical theory of continuity resides entirely at accumulation points $a \in E \cap E'$: 
$$\begin{gather}
\textbf{Theorem: Commutation of Continuous Mappings with Accumulation Limits} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } f: E \to \mathbb{R}, \text{ and let } a \in E \cap E'. \\[2mm]
\text{Then } f \text{ is continuous at } a \text{ if and only if the functional limit exists and equals } f(a)\text{:} \\[3.5mm]
f \text{ is continuous at } a \iff \lim_{E \ni x \to a} f(x) = f(a)
\end{gather}$$
(see [[Proof of the Commutation of Continuous Mappings with Accumulation Limits]])

Because the identity mapping satisfies $\lim_{E \ni x \to a} x = a$, the theorem demonstrates that continuity at an accumulation point represents the exact condition permitting an operator to commute with the limit process:
$$\lim_{E \ni x \to a} f(x) = f\left(\lim_{E \ni x \to a} x\right) \tag{1}$$

---
# The Multi-Faceted Equivalence Architecture

In addition to the basic definition of pointwise continuity, there are other ways of defining what it means for a function to be continuous at a specific point. Deep problems frequently become tractable only when shifting between metric, sequential, filter, or variational characterizations: 
$$\begin{gather}
\textbf{Theorem: The Master Equivalence Architecture of Continuity} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } f: E \to \mathbb{R}, \text{ and let } a \in E \cap E'. \\[2mm]
\text{The following five statements are logically equivalent:} \\[3.5mm]
\begin{align}
\text{1. Cauchy Metric Bound:} \quad &\forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(|x - a| < \delta \implies |f(x) - f(a)| < \varepsilon\big). \\[2mm]
\text{2. Topological Neighborhoods:} \quad &\forall V(f(a)), \ \exists U(a) \quad \text{such that} \quad f(U(a) \cap E) \subseteq V(f(a)). \\[2mm]
\text{3. Heine Sequential Sampler:} \quad &\forall \{x_n\}_{n=1}^\infty \subseteq E, \ \left(\lim_{n \to \infty} x_n = a \implies \lim_{n \to \infty} f(x_n) = f(a)\right). \\[2mm]
\text{4. Filter Base Limit:} \quad &\lim_{\mathcal{B}_a} f(x) = f(a), \ \text{where } \mathcal{B}_a := \{U(a) \cap E \mid U(a) \text{ is an open neighborhood of } a\}. \\[2mm]
\text{5. Cauchy Local Oscillation:} \quad &\omega(f; a) := \lim_{\delta \to 0^+} \omega(f; U_\delta(a) \cap E) = 0.
\end{align}
\end{gather}$$
(see [[Proof of the Master Equivalence Architecture of Continuity]])

The logical equivalence of these five pillars forms a closed deductive cycle:
```easy-tikz
title $\text{The Closed Deductive Cycle of Continuity Characterizations}$
show x from -8.567 to 8.165 and y from -5.967 to 7.263
axes on the edges
set show_axis_label = false
size 13 x 9
xlabel ""
ylabel ""
shade where x >= 0.3 and x <= 7.9 and y >= 5.3 and y <= 6.9, opacity 0.15, outlined
shade where x >= -0.65 and x <= 7.9 and y >= 1.5 and y <= 3.4 in teal, opacity 0.15, outlined
shade where x >= -8.3 and x <= -1.6 and y >= 5.3 and y <= 6.9 in purple, opacity 0.15, outlined
shade where x >= 0.7 and x <= 7.9 and y >= -4.5 and y <= -2.4 in orange, opacity 0.15, outlined
shade where x >= -8.4 and x <= -2.9 and y >= -3.8 and y <= -1.6 in green, opacity 0.15, outlined
write "$\\text{1. Neighborhood Continuity}$" at (4.1, 5.3) in blue, small
write "$\\forall V(f(a)), \\exists U(a): f(E \\cap U(a)) \\subseteq V(f(a))$" at (4.1, 6), small
write "$\\text{2. Cauchy } (\\varepsilon\\text{-}\\delta) \\text{ Continuity}$" at (3.6, 1.6) in teal
write "$\\forall \\varepsilon > 0, \\exists \\delta > 0: |x-a|<\\delta \\Rightarrow |f(x)-f(a)|<\\varepsilon$" at (3.6, 2.5), small
write "$\\text{3. Metric Continuity}$" at (-5.1, 5.2) in purple
write "$d_Y(f(x), f(a)) < \\varepsilon \\text{ when } d_X(x, a) < \\delta$" at (-4.9, 5.9), small
write "$\\text{4. Heine (Sequential) Continuity}$" at (4.3, -4.5) in orange
write "$x_n \\to a \\Rightarrow f(x_n) \\to f(a)$" at (4.15, -3.5), small
write "$\\text{5. Topological Continuity}$" at (-5.6, -3.3) in green
write "$f^{-1}(G) \\text{ is open in } (E, \\tau_E)$" at (-6, -2.5), small
draw an arrow from (7.85, 5.3) to (7.9, 3.4) in blue, thick, labelled "$(1) \\Rightarrow (2)$"
draw a double arrow from (-0.7, 2) to (-1.6, 5.4) in purple, thick, labelled "$(2) \\Leftrightarrow (3)$"
draw an arrow from (7.9, 1.5) to (2.7, -2.35) in teal, thick, labelled "$(2) \\Rightarrow (4)$"
draw an arrow from (0.65, -2.4) to (-2.9, -3.8) in orange, thick, labelled "$(4) \\Rightarrow (5)$"
draw an arrow from (0.3, 5.3) to (-2.9, -1.6) in green, thick, labelled "$(5) \\Rightarrow (1)$"
```
### Analysis of the Five Pillars
1. **The Cauchy Metric Formulation:** Serves as the computational baseline. By explicitly constructing $\delta$ as a functional dependent on both the location $a$ and the error bound $\varepsilon$ (i.e., $\delta = \delta(\varepsilon; a)$), the analyst obtains concrete control over bounds.
2. **The Topological Neighborhood Formulation:** Decouples continuity from distance metrics. It establishes that continuity is fundamentally about the preservation of open sets, providing the direct foundation for modern geometry and general topology.
3. **The Heine Sequential Criterion:** Translates the static geometry of metric intervals into dynamic temporal processes. A mapping is continuous if and only if it preserves the limits of all converging sequences. This forms the analytical bridge connecting discrete numerical schemes, Monte Carlo approximations, and tree models to continuous-time limits.
4. **The Filter Base Formulation:** Provides a coordinate-free limit concept over the system of non-punctured neighborhoods $\mathcal{B}_a := \{U(a) \cap E\}$. Unlike punctured limit bases, retaining the anchor point $a$ inside every filter element ensures that the limit over the base coincides with the functional value $f(a)$.
5. **The Cauchy Oscillation Criterion:** Measures the internal dispersion of the function. For any non-empty set $X \subseteq E$, the oscillation is defined as:
$$\omega(f; X) := \sup_{x_1, x_2 \in X} |f(x_1) - f(x_2)| = \sup_{x \in X} f(x) - \inf_{x \in X} f(x) \tag{2}$$
Continuity asserts that compressing the domain neighborhood collapses the functional variation to zero:
$$\omega(f; a) := \lim_{\delta \to 0^+} \omega(f; (a - \delta, a + \delta) \cap E) = 0 \tag{3}$$

This formulation provides the analytical foundation for the Riemann integrability criterion.

>[!warning]+ Warning: The Asymmetry of the Heine Criterion
>The Heine criterion is theoretically symmetric but operationally asymmetric. Proving continuity via Heine requires demonstrating convergence across *every conceivable sequence* converging to $a$, which is often more labor-intensive than directly solving the metric inequality.
>
>Conversely, the Heine formulation is the definitive tool for demonstrating *discontinuity*. To show that a function is discontinuous at $a$, the analyst needs only produce a single sequence $\{x_n\} \to a$ such that $f(x_n) \not\to f(a)$, or two sequences $\{x_n\} \to a$ and $\{y_n\} \to a$ whose image sequences converge to distinct limits.

---
# Global Preimage Topology on the Real Line
Moving from pointwise continuity to continuity on entire domains requires examining how mappings pull back open subsets of the codomain: 
$$\begin{gather}
\textbf{Definition: Relative Open and Closed Subsets} \\[5mm]
\text{Let } E \subseteq \mathbb{R}. \text{ A subset } U \subseteq E \text{ is relatively open in } E \text{ if there exists an open set } G \subseteq \mathbb{R} \\[2mm]
\text{such that } U = G \cap E. \text{ Similarly, } K \subseteq E \text{ is relatively closed in } E \text{ if } K = F \cap E \text{ for some closed } F \subseteq \mathbb{R}.
\end{gather}$$

$$\begin{gather}
\textbf{Theorem: The Global Open Preimage Characterization} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{The function } f \text{ is continuous at every point of } E \text{ if and only if} \\[2mm]
\text{for every open set } G \subseteq \mathbb{R}, \text{ the complete preimage } f^{-1}(G) \text{ is relatively open in } E\text{:} \\[3.5mm]
f \in C(E; \mathbb{R}) \iff \forall G \subseteq \mathbb{R} \text{ open}, \ \exists \Omega \subseteq \mathbb{R} \text{ open such that } f^{-1}(G) = \Omega \cap E
\end{gather}$$
(see [[Proof of the Global Open Preimage Characterization]])

$$\begin{gather}
\textbf{Corollary: Closed Preimage Duality} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ and let } f: E \to \mathbb{R}. \\[2mm]
\text{The function } f \text{ is continuous on } E \text{ if and only if for every closed set } F \subseteq \mathbb{R}, \\[2mm]
\text{the complete preimage } f^{-1}(F) \text{ is relatively closed in } E.
\end{gather}$$
(see [[Proof of the Closed Preimage Duality]])

By taking set complements, $f^{-1}(\mathbb{R} \setminus G) = E \setminus f^{-1}(G)$, demonstrating that the preservation of openness under preimages directly implies the preservation of closedness under preimages.

>[!question]+ Application: Preimage Threshold Regions in Financial Barrier Contracts
>The Global Open Preimage Characterization provides a direct topological test for determining whether state-dependent financial contracts define open or closed activation domains. Consider an underlying asset price $S \in E = [0, \infty)$ and a continuous valuation or risk-indicator function $f: E \to \mathbb{R}$ (such as a basket price or spread function).
>
>A knock-out barrier provision deactivates the contract whenever the indicator remains strictly inside an open target corridor $G = (L_{\min}, L_{\max}) \subset \mathbb{R}$, corresponding to the preimage safe-harbor region:
>
>$$S \in f^{-1}(G) = \{S \in E \mid L_{\min} < f(S) < L_{\max}\} \tag{4}$$
>
>Because $f$ is continuous on $E$ and $G$ is open in $\mathbb{R}$, the Global Open Preimage Characterization guarantees that $f^{-1}(G)$ is relatively open in $E$. Consequently, any current state $S_0 \in f^{-1}(G)$ possesses a non-zero price buffer $\delta > 0$ such that small price perturbations within $(S_0 - \delta, S_0 + \delta) \cap E$ cannot trigger barrier breach. Conversely, the breach set $f^{-1}(\mathbb{R} \setminus G) = E \setminus f^{-1}(G)$ is guaranteed by Closed Preimage Duality to be relatively closed in $E$, ensuring that the boundary of contract termination is included in the breach domain.

---
# Directional Continuity and Jump Operators
At interior points of a domain, an argument can approach a target point along two opposing trajectories: the left-hand direction ($x < a$) and right-hand direction ($x > a$). Disentangling these trajectories via [[Chapter 2 - Limits of Functions|one-sided limits]] isolates directional functional behavior: 
$$\begin{gather}
\textbf{Definition: Directional Continuity} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } f: E \to \mathbb{R}, \text{ and let } a \in E. \\[3.5mm]
\text{1. Left-Continuity: If } a \in (E \cap (-\infty, a])', \ f \text{ is left-continuous at } a \text{ if:} \\[2mm]
\lim_{E \ni x \to a^-} f(x) = f(a) \iff \forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(a - \delta < x \le a \implies |f(x) - f(a)| < \varepsilon\big). \\[3.5mm]
\text{2. Right-Continuity: If } a \in (E \cap [a, \infty))', \ f \text{ is right-continuous at } a \text{ if:} \\[2mm]
\lim_{E \ni x \to a^+} f(x) = f(a) \iff \forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(a \le x < a + \delta \implies |f(x) - f(a)| < \varepsilon\big).
\end{gather}$$

$$\begin{gather}
\textbf{Theorem: The Two-Sided Equivalence Principle} \\[5mm]
\text{Let } a \text{ be an interior point of } E \subseteq \mathbb{R}, \text{ such that } (a - \eta, a + \eta) \subseteq E \text{ for some } \eta > 0. \\[2mm]
\text{A function } f: E \to \mathbb{R} \text{ is continuous at } a \text{ if and only if it is simultaneously} \\[2mm]
\text{left-continuous and right-continuous at } a\text{:} \\[3.5mm]
f \text{ is continuous at } a \iff \lim_{x \to a^-} f(x) = \lim_{x \to a^+} f(x) = f(a)
\end{gather}$$
(see [[Proof of the Two-Sided Equivalence Principle]])

When the directional limits exist as finite real numbers but fail to coincide, the function exhibits a finite jump: 
$$\begin{gather}
\textbf{Definition: The Jump Dislocation Operator} \\[5mm]
\text{Let } a \in \operatorname{int}(E), \text{ and suppose the one-sided limits } f(a^-) := \lim_{x \to a^-} f(x) \\[2mm]
\text{and } f(a^+) := \lim_{x \to a^+} f(x) \text{ both exist as finite real numbers.} \\[3.5mm]
\text{The jump dislocation operator } \Delta f(a) \text{ is defined as the directional difference:} \\[3.5mm]
\Delta f(a) := f(a^+) - f(a^-)
\end{gather}$$

The geometry of directional limits and the resulting jump dislocation is illustrated below:
```easy-tikz
title $\text{Anatomy of a Jump Discontinuity of the First Kind}$
xlabel $x$
ylabel $f(x)$
show x from 1.457 to 6.191 and y from 1.109 to 4.66
axes on the edges
size 12 x 8
plot f_left(x) = 1.17 + 0.3*(x - 0.5) - 0.04*(x - 2.2)^2 from x = 0 to 3.5 in blue, very thick
plot f_right(x) = 4 + 0.35*sin(1.4*(x - 3.5)) + 0.12*(x - 3.5) from x = 3.5 to 7 in red, very thick
draw a segment from (3.5, 0) to (3.5, 4.7), in gray, dashed
draw a line from (0, 2) to (3.5, 2) in blue, dashed
draw a line from (0, 4) to (3.5, 4) in red, dashed
draw a line from (0, 3) to (3.5, 3) in purple, dashed
draw a double arrow from (4.25, 2) to (4.25, 4) in teal, thick
draw a line from (3.5, 2) to (4.25, 2) in gray, dashed
draw a line from (3.5, 4) to (4.25, 4) in gray, dashed
mark (3.5, 3) in purple, large
mark (3.5, 2) in blue, small
mark (3.5, 4), small
write "$a$" at (3.5, 0.15), in black, below
write "$f(a^-)$" at (0.4, 2.05) in blue
write "$f(a)$" at (0.45, 2.85), in purple, above
write "$f(a^+)$" at (0.35, 3.95) in red
write "$\\text{Left-hand limit } (a, f(a^-))$" at (3.45, 2.3) in blue, left
write "$\\text{Isolated value } (a, f(a))$" at (3.25, 3.18) in purple, left
write "$\\text{Right-hand limit } (a, f(a^+))$" at (3.45, 4.25) in red, left
write "$\\Delta f(a) = f(a^+)- f(a^-)$" at (4.35, 2.85) in teal, right
```

>[!question]+ Application: Càdlàg Price Trajectories and Order-Book Dislocations
>In empirical financial engineering, asset price trajectories subject to macroeconomic announcements, earnings surprises, or liquidity crunches are modeled as càdlàg functions (continu à droite, limite à gauche—right-continuous with left limits). 
>
>For a càdlàg price path $S(t)$, the left limit $S(t^-) = \lim_{s \to t^-} S(s)$ captures the pre-announcement asset valuation, while $S(t) = S(t^+)$ defines the executed transaction price immediately following the arrival of new information. The instantaneous market shock is quantified by the jump dislocation operator:
>
>$$\Delta S(t) := S(t) - S(t^-) \tag{5}$$
>
>Directional continuity provides the structural framework required to model discrete jump events alongside continuous price movements.

---
# The Taxonomy of Functional Discontinuities

When $a \in E \cap E'$ and the continuity condition $\lim_{x \to a} f(x) = f(a)$ fails, the breakdown occurs through distinct mathematical mechanisms. The systematic taxonomy of discontinuities partitions these breakdowns into four exhaustive classes:
```easy-tikz
title $\text{Complete Taxonomy of Pointwise Discontinuities at } x = a$
show x from -6.189 to 6.211 and y from -4.482 to 4.518
axes on the edges
set show_axis_label = false
size 14 x 9
R_root: shade where x >= -2.6 and x <= 2.6 and y >= 2.8 and y <= 4.4 in black, opacity 0.12, outlined
R_k1: shade where x >= -5.6 and x <= -0.8 and y >= 0.3 and y <= 1.7, in blue, opacity 0.15, outlined
R_k2: shade where x >= 0.8 and x <= 5.6 and y >= 0.3 and y <= 1.7, in red, opacity 0.15, outlined
R_rem: shade where x >= -5.9 and x <= -3.3 and y >= -3.8 and y <= -1.4, in teal, opacity 0.15, outlined
R_jmp: shade where x >= -3.0 and x <= -0.4 and y >= -3.8 and y <= -1.4, in purple, opacity 0.15, outlined
R_inf: shade where x >= 0.4 and x <= 3.0 and y >= -3.8 and y <= -1.4, in orange, opacity 0.15, outlined
R_osc: shade where x >= 3.3 and x <= 5.9 and y >= -3.8 and y <= -1.4, in magenta, opacity 0.15, outlined
draw an arrow from (-1.2, 2.8) to (-3.2, 1.75), in blue, thick
draw an arrow from (1.2, 2.8) to (3.2, 1.75), in red, thick
draw an arrow from (-3.8, 0.3) to (-4.6, -1.35), in teal, thick
draw an arrow from (-2.6, 0.3) to (-1.7, -1.35), in purple, thick
draw an arrow from (2.6, 0.3) to (1.7, -1.35), in orange, thick
draw an arrow from (3.8, 0.3) to (4.6, -1.35), in magenta, thick
write "$\\text{Point of Discontinuity } (x = a)$" at (-0.4, 3.6)
write "$\\lim_{x \\to a} f(x) \\neq f(a) \\text{ or limit DNE}$" at (0.4, 3.2), small
write "$\\text{Discontinuity of the First Kind}$" at (-3.2, 0.85) in blue
write "$f(a^-), f(a^+) \\in \\mathbb{R} \\text{ both exist \\& finite}$" at (-3.2, 0.3), small
write "$\\text{Discontinuity of the Second Kind}$" at (3.2, 1) in red
write "$\\text{Essential: } f(a^-) \\text{ or } f(a^+) \\text{ DNE or } \\pm\\infty$" at (3.2, 0.4), small
write "$\\text{Removable}$" at (-4.6, -2.2) in teal
write "$f(a^-) = f(a^+) \\neq f(a)$" at (-4.6, -2.85), small
write "$\\Delta f(a) = 0$" at (-4.65, -3.55) in teal, small
write "$\\text{Jump}$" at (-1.7, -2.2) in purple
write "$f(a^-) \\neq f(a^+)$" at (-1.7, -2.75), small
write "$\\Delta f(a) \\neq 0 \\text{ finite}$" at (-1.7, -3.45) in purple, small
write "$\\text{Infinite / Pole}$" at (1.7, -2.2) in orange
write "$f(a^\\pm) = \\pm\\infty$" at (1.65, -2.8), small
write "$\\text{Unbounded blow-up}$" at (1.7, -3.5) in orange, small
write "$\\text{Oscillatory}$" at (4.65, -2.2) in magenta
write "$\\text{e.g. } \\sin(1/(x-a))$" at (4.65, -2.8), small
write "$\\text{No directional limit}$" at (4.6, -3.5) in magenta, small
```
### 1. Removable Discontinuity
A point $a \in E'$ is a removable discontinuity of $f$ if the two-sided functional limit exists finitely, but either fails to equal $f(a)$, or $f$ is undefined at $a$:
$$\lim_{E \ni x \to a} f(x) = L \in \mathbb{R}, \quad \text{where } L \ne f(a) \tag{6}$$

The defect is termed *removable* because the function can be rendered continuous at $a$ by redefining a single point:
$$\tilde{f}(x) := \begin{cases} f(x), & x \in E \setminus \{a\} \\ L, & x = a \end{cases} \tag{7}$$

### 2. Discontinuity of the First Kind (Jump Discontinuity)
A point $a \in E'$ is a discontinuity of the first kind (or simple jump) if the one-sided limits $f(a^-)$ and $f(a^+)$ both exist as finite real numbers, but fail to coincide:
$$f(a^-) \in \mathbb{R}, \quad f(a^+) \in \mathbb{R}, \quad \text{and} \quad f(a^-) \ne f(a^+) \tag{8}$$
Here, the jump dislocation magnitude is non-zero: $|\Delta f(a)| = |f(a^+) - f(a^-)| > 0$. No isolated redefinition of $f(a)$ can restore continuity.

### 3. Discontinuity of the Second Kind
##### Essential / Oscillatory Discontinuity
A point $a \in E'$ is an essential discontinuity of the second kind if at least one of the directional limits fails to exist due to non-convergent oscillation within a bounded or unbounded region.

##### Infinite Discontinuity
A point $a \in E'$ is an infinite discontinuity of the second kind if at least one of the one-sided directional limits diverges to $+\infty$, $-\infty$, or unsigned $\infty$.

### A More Concise Expression of Discontinuity
The restoration of continuity at a removable discontinuity may be expressed formally:
$$
\begin{gather}
\textbf{Theorem: Removable Discontinuities and Continuous Extensions} \\[5mm]
\text{Let } f:E \rightarrow \mathbb{R} \text{ and let } a \in E \cap E'. \text{ If the functional limit exists finitely: } \\[3.5mm]
\lim_{ E \owns x \to a } f(x) = L \in \mathbb{R}  \\[3.5mm]
\text{but } L \neq f(a), \text{ then the modified function } \overline{f} : E \rightarrow \mathbb{R} \text{ defined by: } \\[3.5mm]
\overline{f}(x) := \begin{cases} f(x), & x \in E \setminus \{ a \} \\[2mm]
L, & x = a \end{cases} \\[3.5mm]
\text{is continuous at the point } a. 
\end{gather}
$$
(see [[Proof of Removable Discontinuities and Continuous Extensions]])

---
# The Pathological Gallery (Classical Counterexamples)
Counterexamples in analysis serve as formal boundary tests for analytical concepts. The following classical constructions illustrate the edge behaviors of functional continuity.

### 1. The Dirichlet Function: Nowhere Continuous
Consider the indicator function of the rational field within the real numbers:
$$\mathbf{1}_{\mathbb{Q}}(x) := \begin{cases} 1, & x \in \mathbb{Q} \\ 0, & x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \tag{9}$$
$$\begin{gather}
\textbf{Proposition: Total Discontinuity of the Dirichlet Function} \\[5mm]
\text{The Dirichlet function } \mathbf{1}_{\mathbb{Q}}: \mathbb{R} \to \mathbb{R} \text{ is discontinuous at every point } a \in \mathbb{R}. \\[2mm]
\text{Every point } a \in \mathbb{R} \text{ is an essential discontinuity of the second kind.}
\end{gather}$$
(see [[Proof of the Total Discontinuity of the Dirichlet Function]])

##### Analytical Assessment 
By the density of both the rational numbers $\mathbb{Q}$ and the irrational numbers $\mathbb{R} \setminus \mathbb{Q}$, every open interval $(a - \delta, a + \delta)$, regardless of how small $\delta > 0$ is chosen, contains points mapping to $1$ and points mapping to $0$. Choosing an error tolerance $\varepsilon_0 = \frac{1}{2}$ guarantees that the Cauchy metric condition fails for every point $a \in \mathbb{R}$. 

Furthermore, because every directional half-interval $(a - \delta, a)$ and $(a, a + \delta)$ contains dense subsets of both rational and irrational numbers, neither the left-hand nor the right-hand functional limit exists. This renders every point an essential discontinuity of the second kind. The total breakdown of continuity across $\mathbb{R}$ causes standard Riemann integration to fail, establishing the necessity for Lebesgue measure theory.

### 2. Thomae’s Function: Rational Discontinuity, Irrational Continuity
Consider the function $R: (0, 1) \to \mathbb{R}$, introduced by *Carl Johannes Thomae*, defined by:
$$R(x) := \begin{cases} \frac{1}{q}, & \text{if } x = \frac{p}{q} \in \mathbb{Q} \cap (0, 1) \text{ in lowest terms } (p, q \in \mathbb{N}, \ \gcd(p, q) = 1) \\ 0, & \text{if } x \in (0, 1) \setminus \mathbb{Q} \end{cases} \tag{10}$$

$$\begin{gather}
\textbf{Proposition: Dense-Irrational Continuity of Thomae's Function} \\[5mm]
\text{Thomae's function } R \text{ is discontinuous at every rational point } a \in \mathbb{Q} \cap (0, 1), \\[2mm]
\text{and continuous at every irrational point } a \in (0, 1) \setminus \mathbb{Q}.
\end{gather}$$
(see [[Proof that Thomae's Function is Dense-Irrational Continuous]])

##### Analytical Assessment 
At any rational point $a = \frac{p_0}{q_0}$, the functional value is strictly positive: $R(a) = \frac{1}{q_0} > 0$. By the density of the irrationals, every interval $(a - \delta, a + \delta)$ contains an irrational $\xi$ where $R(\xi) = 0$. Setting $\varepsilon_0 = \frac{1}{2q_0}$ causes the metric condition to fail for all $\delta > 0$, proving discontinuity at rational inputs.

Conversely, at any irrational point $a \in (0, 1) \setminus \mathbb{Q}$, the functional value is $R(a) = 0$. For any tolerance $\varepsilon > 0$, by the Archimedean property there are only a *finite number* of rational fractions in $(0, 1)$ whose denominators satisfy $q \le \frac{1}{\varepsilon}$. Because $a$ is irrational, it maintains a strictly positive distance $\delta > 0$ from this finite set of rationals. Restricting the domain to $(a - \delta, a + \delta)$ ensures that any rational point $x = \frac{p}{q}$ inside the interval must have $q > \frac{1}{\varepsilon}$, guaranteeing that $|R(x) - R(a)| = \frac{1}{q} < \varepsilon$. 

Thomae's function proves that a real-valued function can be continuous on an uncountable dense subset ($\mathbb{R} \setminus \mathbb{Q}$) while remaining discontinuous on a countable dense subset ($\mathbb{Q}$).

### 3. The Isolated Continuous Point: Modulated Rational Indicator
Consider the modulated indicator function:
$$f(x) := \begin{cases} x, & x \in \mathbb{Q} \\ 0, & x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \tag{11}$$

$$\begin{gather}
\textbf{Proposition: Single-Point Continuity of Modulated Indicator} \\[5mm]
\text{The function } f(x) = x \cdot \mathbf{1}_{\mathbb{Q}}(x) \text{ is continuous at exactly one point: } x = 0. \\[2mm]
\text{It is discontinuous at every non-zero point } x \in \mathbb{R} \setminus \{0\}.
\end{gather}$$
(see [[Proof of the Single-Point Continuity of Modulated Indicator]])

##### Analytical Assessment 
For all $x \in \mathbb{R}$, the absolute value is bounded by $|f(x)| \le |x|$. At $x = 0$, $f(0) = 0$. Given $\varepsilon > 0$, selecting $\delta = \varepsilon$ guarantees that $|x - 0| < \delta \implies |f(x) - f(0)| \le |x| < \varepsilon$, establishing continuity at the origin. 

Conversely, for any non-zero point $a \ne 0$, the function oscillates between $0$ (on irrationals) and values near $a$ (on rationals). For an error tolerance $\varepsilon_0 = \frac{|a|}{2}$, every neighborhood contains witness points violating the metric bound. Thus, continuity can exist at an isolated single point while failing everywhere else on $\mathbb{R}$.

### 4. The Essential Oscillatory Singularity: Reciprocal Sine Function
Consider the function defined for $x \ne 0$ by:
$$f(x) := \sin\left(\frac{1}{x}\right), \quad x \in \mathbb{R} \setminus \{0\} \tag{12}$$

$$\begin{gather}
\textbf{Proposition: Oscillatory Breakdown of the Reciprocal Sine Function} \\[5mm]
\text{The function } f(x) = \sin(1/x) \text{ possesses no limit as } x \to 0. \\[2mm]
\text{No assignment of } f(0) \in \mathbb{R} \text{ can make the function continuous at } x = 0.
\end{gather}$$
(see [[Proof that the Reciprocal Sine Function is Discontinuous When Its Input is Zero]])

##### Analytical Assessment 
The failure of the limit is revealed via the Heine sequential criterion. Construct two sequences converging to zero:
$$x_n = \frac{1}{\frac{\pi}{2} + 2\pi n}, \qquad y_n = \frac{1}{\pi n}, \quad n \in \mathbb{N} \tag{13}$$

While $\lim_{n \to \infty} x_n = 0$ and $\lim_{n \to \infty} y_n = 0$, evaluating the image sequences yields:
$$f(x_n) = \sin\left(\frac{\pi}{2} + 2\pi n\right) = 1 \implies \lim_{n \to \infty} f(x_n) = 1 \tag{14}$$

$$f(y_n) = \sin(\pi n) = 0 \implies \lim_{n \to \infty} f(y_n) = 0 \tag{15}$$

Because distinct sequences converging to the same input point yield image sequences converging to disparate values ($1 \ne 0$), the two-sided limit does not exist, creating an essential discontinuity of the second kind.

---
# Applications of Continuity at Point

### Quantitative Finance: Asset Continuum vs. Order Book Microstructure and Binary Payoffs
In continuous-time financial models, asset valuations $S$ are idealized as spanning the positive continuum $\mathbb{R}_{>0}$. However, exchange matching engines operate on a discrete tick grid $E = \tau \mathbb{Z} = \{0, \tau, 2\tau, \dots\}$, where $\tau > 0$ is the minimum tick size (e.g., $\tau = \$0.01$). 

Consider the order-book execution map $P: \mathbb{R}_{>0} \to E$ that maps an unconstrained valuation $S$ to the prevailing limit order quote via floor quantization:
$$P(S) = \tau \left\lfloor \frac{S}{\tau} \right\rfloor \tag{16}$$

At any tick boundary $S_k = k\tau$ for $k \in \mathbb{N}$, evaluating the directional limits yields:
$$\lim_{S \to S_k^-} P(S) = \tau (k - 1) = S_k - \tau, \qquad \lim_{S \to S_k^+} P(S) = \tau k = S_k \tag{17}$$

Because $P(S_k) = S_k$, the pricing map is right-continuous, but undergoes a jump discontinuity of the first kind with jump amplitude $\Delta P(S_k) = \tau$.

Concurrently, consider the terminal payoff $V: \mathbb{R}_{\ge 0} \to \mathbb{R}$ of a binary cash-or-nothing digital call option with strike price $K > 0$ and payout $B > 0$:
$$V(S) = B \cdot \mathbf{1}_{[K, \infty)}(S) = \begin{cases} B, & S \ge K \\ 0, & 0 \le S < K \end{cases} \tag{18}$$

Evaluating the directional limits at the strike price $K$:
$$\lim_{S \to K^-} V(S) = 0, \qquad \lim_{S \to K^+} V(S) = B \tag{19}$$

Because $V(K) = B = \lim_{S \to K^+} V(S)$, the contract payoff is right-continuous (càdlàg), but possesses a jump discontinuity of the first kind with amplitude $\Delta V(K) = B - 0 = B \ne 0$.

>[!question]+ Application: Derivative Discontinuities and Hedging Singularities
>In derivative risk management, hedging portfolios rely on matching the sensitivity of the contract value to shifts in the underlying price $S$. For a continuous payoff (such as a standard European call $(S - K)^+$), the payoff is continuous everywhere. 
>
>For the binary digital call $V(S)$, the step dislocation of magnitude $B$ at $S = K$ creates an intractable structural challenge: approaching the strike price $K$ near expiration, maintaining a delta-neutral hedge requires an unbounded position in the underlying asset, exposing market makers to severe execution slippage. Payoff discontinuities directly generate computational and liquidity singularities.

### Mechanical Engineering: Coulomb Friction and the Velocity Dislocation
In mechanical and civil systems (such as automotive brake calipers, seismic fault lines, or machine ways), dry friction between two solid surfaces in relative motion is modeled by the *Charles-Augustin de Coulomb* and *Guillaume Amontons* constitutive relation. The resistive friction force $F_f$ is parameterized as a function of relative sliding velocity $v \in \mathbb{R}$:
$$F_f(v) := -\mu_k F_N \operatorname{sgn}(v) = \begin{cases} -\mu_k F_N, & v > 0 \\ 0, & v = 0 \\ +\mu_k F_N, & v < 0 \end{cases} \tag{20}$$

where $\mu_k > 0$ is the kinetic friction coefficient, $F_N > 0$ is the normal load force, and $\operatorname{sgn}(v)$ is the signum function.

Analyzing continuity across the velocity domain:
* For any $v_0 \ne 0$, choosing $\delta = |v_0| > 0$ keeps the sign of $v$ constant on $U_\delta(v_0)$, making $F_f(v)$ locally constant and hence continuous: $\lim_{v \to v_0} F_f(v) = F_f(v_0)$.
* At $v = 0$ (the transition between static adhesion and kinetic sliding), evaluating the one-sided limits yields:
$$\lim_{v \to 0^+} F_f(v) = -\mu_k F_N, \qquad \lim_{v \to 0^-} F_f(v) = +\mu_k F_N \tag{21}$$

The directional limits are finite real numbers but fail to agree. The force mapping exhibits a jump discontinuity of the first kind at $v = 0$ with jump amplitude:
$$\Delta F_f(0) = \lim_{v \to 0^+} F_f(v) - \lim_{v \to 0^-} F_f(v) = -2\mu_k F_N \ne 0 \tag{22}$$

This finite dislocation explains the mechanical instability known as "stick-slip" chatter (such as the squeal of railway wheels or brake chatter), which arises directly from the jump discontinuity of $F_f(v)$ at the zero-velocity boundary.

### Physics: Projectile Motion and Geometric Obstacle Truncation
Consider a projectile launched in a uniform gravitational field from an origin $(0, 0)$ with fixed initial speed $v_0$ and launch angle $\theta \in (0, \pi/2)$. Kinematic trajectory equations define the elevation $y$ as a function of horizontal distance $x$:
$$y(x; \theta) = x \tan\theta - \frac{g x^2}{2 v_0^2 \cos^2\theta} \tag{23}$$

An impenetrable vertical wall of fixed height $H > 0$ is situated at a horizontal distance $x = d > 0$.

If the projectile clears the wall ($y(d; \theta) \ge H$), its total horizontal flight distance is the unobstructed parabolic ground range:
$$R(\theta) = \frac{v_0^2 \sin(2\theta)}{g} \tag{24}$$

where $R(\theta) > d$. If the projectile's altitude at $x = d$ satisfies $y(d; \theta) < H$, the trajectory impacts the barrier, and horizontal displacement terminates abruptly at $L(\theta) = d$.

The total horizontal travel distance $L: (0, \pi/2) \to \mathbb{R}$ is defined piecewise:
$$L(\theta) = \begin{cases} d, & \text{if } y(d; \theta) < H \\ \frac{v_0^2 \sin(2\theta)}{g}, & \text{if } y(d; \theta) \ge H \end{cases} \tag{25}$$

Because $y(d; \theta)$ is a continuous function of $\theta$, there exists a critical launch angle $\theta^* \in (0, \pi/2)$ such that $y(d; \theta^*) = H$. Evaluating the directional limits of horizontal range as $\theta \to \theta^*$:
$$\lim_{\theta \to \theta^{*-}} L(\theta) = d, \qquad \lim_{\theta \to \theta^{*+}} L(\theta) = \frac{v_0^2 \sin(2\theta^*)}{g} > d \tag{26}$$

Because the left-hand limit is $d$ while the right-hand limit equals the unobstructed range $R(\theta^*) > d$, the mapping $L(\theta)$ undergoes a jump discontinuity of the first kind at $\theta = \theta^*$. A continuous parameter variation ($\theta$) produces a discontinuous state transition due to spatial boundary constraints.

### Neurobiology: The All-or-None Action Potential Threshold
In cellular electrophysiology, the generation of nerve impulses in an axon obeys the classical *all-or-none law*. Let $S \in [0, S_{\max}]$ represent the magnitude of an injected depolarizing current stimulus. Let $V_{\text{peak}}: [0, S_{\max}] \to \mathbb{R}$ denote the peak membrane potential reached by the neuron.

Below a critical voltage threshold $S_{\text{th}} > 0$, the cell membrane behaves as a passive RC circuit, generating a sub-threshold graded potential:
$$V_{\text{peak}}(S) = V_{\text{rest}} + \alpha S, \quad 0 \le S < S_{\text{th}} \tag{27}$$

where $V_{\text{rest}} \approx -70\text{ mV}$ is the resting potential and $\alpha > 0$ is the passive membrane sensitivity. 

When the stimulus reaches or exceeds the threshold $S_{\text{th}}$, voltage-gated sodium channels open in a regenerative cascade, producing an action potential of fixed amplitude $V_{\text{spike}} \approx +40\text{ mV}$, invariant to further stimulus increases:
$$V_{\text{peak}}(S) = \begin{cases} V_{\text{rest}} + \alpha S, & 0 \le S < S_{\text{th}} \\ V_{\text{spike}}, & S \ge S_{\text{th}} \end{cases} \tag{28}$$

Evaluating the directional limits at the biological threshold $S = S_{\text{th}}$:
$$\lim_{S \to S_{\text{th}}^-} V_{\text{peak}}(S) = V_{\text{rest}} + \alpha S_{\text{th}} \approx -55\text{ mV} \tag{29}$$

$$\lim_{S \to S_{\text{th}}^+} V_{\text{peak}}(S) = V_{\text{spike}} \approx +40\text{ mV} \tag{30}$$

Because $V_{\text{peak}}(S_{\text{th}}) = V_{\text{spike}} = \lim_{S \to S_{\text{th}}^+} V_{\text{peak}}(S)$, the biological response is strictly right-continuous, but exhibits a jump discontinuity of the first kind with jump amplitude:

$$\Delta V_{\text{peak}}(S_{\text{th}}) = +40\text{ mV} - (-55\text{ mV}) = +95\text{ mV} \ne 0 \tag{31}$$

This functional discontinuity acts as a vital biological filter: the metric jump ensures that continuous microscopic biochemical noise is extinguished, while true physiological signals trigger reliable digital spikes.

### Chemical Thermodynamics: Phase Transitions and Density Discontinuities
In physical chemistry, the macroscopic state of pure water ($\text{H}_2\text{O}$) at standard atmospheric pressure ($P = 1\text{ atm}$) is parameterized by its thermodynamic temperature $T \in \mathbb{R}_{>0}$. Consider the mass density function $\rho: (T_{\min}, T_{\max}) \to \mathbb{R}_{>0}$ across the normal melting point $T_m = 273.15\text{ K}$ ($0^\circ\text{C}$).
* For $T < T_m$, the substance exists in the solid phase (ice $I_h$), forming an open hexagonal crystal lattice:
$$\lim_{T \to T_m^-} \rho(T) = \rho_{\text{ice}}(T_m) \approx 0.9167\text{ g/cm}^3 \tag{32}$$

* For $T > T_m$, the crystal structure collapses into a fluid phase, enabling tighter molecular packing:
$$\lim_{T \to T_m^+} \rho(T) = \rho_{\text{liquid}}(T_m) \approx 0.9998\text{ g/cm}^3 \tag{33}$$

Defining the density at the coexistence equilibrium point $T_m$ as $\rho(T_m)$, the temperature-density state mapping is governed by:
$$\rho(T) = \begin{cases} \rho_{\text{ice}}(T), & T < T_m \\ \rho(T_m), & T = T_m \\ \rho_{\text{liquid}}(T), & T > T_m \end{cases} \tag{34}$$

In thermodynamic classification (*Paul Ehrenfest* taxonomy), a first-order phase transition is characterized by a finite step change in primary thermodynamic state variables:
$$\Delta \rho(T_m) = \lim_{T \to T_m^+} \rho(T) - \lim_{T \to T_m^-} \rho(T) \approx 0.9998 - 0.9167 = 0.0831\text{ g/cm}^3 \ne 0 \tag{35}$$

Because the directional limits exist finitely but do not coincide, the temperature-density mapping exhibits a jump discontinuity of the first kind at $T = T_m$. Phase transitions in matter are physical manifestations of functional jump discontinuities, formalized entirely through directional limits without requiring differential equations of state.