---
dg-publish: true
---
# The Study of Functions Using Differential Calculus

Differential calculus transforms the qualitative investigation of functions from empirical graphing into an exact deductive science. By examining the algebraic signs, zeros, and growth rates of the first and second derivatives, the global geometric architecture of a function—its intervals of monotonicity, local and global extrema, curvature, inflection points, asymptotes, and convex duality—is rigorously determined.

This chapter synthesizes Vladimir Zorich’s rigorous chord-based theory of convexity with the pedagogical optimization and curve-sketching protocols of classical analysis, culminating in master analytic inequalities and convex duality.

---

# Conditions for Local Extrema: First and Higher-Order Tests

Fermat's Stationary Point Lemma establishes that stationary points ($f'(x_0) = 0$) are the only candidates for interior extrema among differentiable functions. To distinguish between local maxima, local minima, and non-extremal inflection points, sufficient criteria are required.

$$\begin{gather}
\textbf{Theorem: The First Derivative Test for Local Extrema} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be continuous on an interval } I \text{ and differentiable on } I \setminus \{x_0\}, \text{ where } x_0 \in \text{int}(I). \\[3mm]
\begin{align}
\text{1. Local Maximum:} \quad &\text{If } \exists \delta > 0 \text{ such that } f'(x) \ge 0 \text{ for } x \in (x_0 - \delta, x_0) \text{ and } f'(x) \le 0 \text{ for } x \in (x_0, x_0 + \delta), \\[2mm]
&\text{then } x_0 \text{ is a local maximum of } f. \\[3mm]
\text{2. Local Minimum:} \quad &\text{If } \exists \delta > 0 \text{ such that } f'(x) \le 0 \text{ for } x \in (x_0 - \delta, x_0) \text{ and } f'(x) \ge 0 \text{ for } x \in (x_0, x_0 + \delta), \\[2mm]
&\text{then } x_0 \text{ is a local minimum of } f. \\[3mm]
\text{3. Strict Extremum:} \quad &\text{If the inequalities on } f' \text{ are strict, then } x_0 \text{ is a strict local extremum.} \\[3mm]
\text{4. No Extremum:} \quad &\text{If } f'(x) \text{ preserves a strict sign throughout the punctured neighborhood } \mathring{U}_\delta(x_0), \\[2mm]
&\text{then } x_0 \text{ is not a local extremum.}
\end{align}
\end{gather}$$

When higher derivatives are readily computable, Taylor's expansion yields the higher-order derivative test:

$$\begin{gather}
\textbf{Theorem: The Higher-Order Derivative Test for Extrema} \\[5mm]
\text{Let } f \in C^n(U(x_0)) \text{ for some integer } n \ge 2. \text{ Suppose that:} \\[3.5mm]
f'(x_0) = f''(x_0) = \dots = f^{(n-1)}(x_0) = 0, \quad \text{and} \quad f^{(n)}(x_0) \neq 0. \\[3.5mm]
\begin{align}
\text{1. Even Order (Extremum):} \quad &\text{If } n \text{ is even, } x_0 \text{ is a strict local extremum:} \\[2mm]
&f^{(n)}(x_0) < 0 \implies x_0 \text{ is a strict local maximum,} \\[2mm]
&f^{(n)}(x_0) > 0 \implies x_0 \text{ is a strict local minimum.} \\[3mm]
\text{2. Odd Order (No Extremum):} \quad &\text{If } n \text{ is odd, } x_0 \text{ is not an extremum; it is an inflection point.}
\end{align}
\end{gather}$$
(see [[Proof of the First and Higher-Order Derivative Extrema Tests]])

---

# Convexity and the Master Equivalence Architecture

### Rigorous Definition via Secant Chords
In elementary treatments, convexity is often described visually as "bending upward" or "lying above tangent lines." In rigorous analysis, convexity is defined intrinsically without assuming differentiability, via the position of the curve relative to its *secant chords*:

$$\begin{gather}
\textbf{Definition: Convex Functions} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be an interval. A function } f: I \to \mathbb{R} \text{ is convex on } I \text{ if for all } x_1, x_2 \in I \\[2mm]
\text{and all weights } \alpha_1, \alpha_2 \ge 0 \text{ with } \alpha_1 + \alpha_2 = 1\text{:} \\[3.5mm]
f(\alpha_1 x_1 + \alpha_2 x_2) \le \alpha_1 f(x_1) + \alpha_2 f(x_2).
\end{gather}$$
If the strict inequality holds whenever $x_1 \neq x_2$ and $\alpha_1, \alpha_2 > 0$, $f$ is *strictly convex*. A function $f$ is *concave* if $-f$ is convex.

```easy-tikz
title $\text{Convexity: Secant Chord Lies Above the Graph}$
xlabel $x$
ylabel $y$
show x from 0 to 8 and y from 0 to 6
axes on the edges
size 12 x 8
plot f(x) = 1.0 + 0.08*(x - 1.0)^2, from x = 1.0 to 7.0, in teal, very thick
draw a segment from (2.0, 1.08) to (6.0, 3.00), in blue, thick
draw a line from (1.0, 0.44) to (7.0, 2.84), in red, dashed
draw a segment from (4.0, 0.2) to (4.0, 2.04), in gray, dotted
mark (2.0, 1.08), in blue, large
mark (6.0, 3.00), in blue, large
mark (4.0, 1.72), in teal, large
mark (4.0, 2.04), in blue, large
mark (4.0, 1.64), in red, large
write "$A(x_1, f(x_1))$" at (2.0, 1.35), in blue, above left
write "$B(x_2, f(x_2))$" at (6.05, 3.15), in blue, right
write "$\text{Secant Chord } \alpha_1 f(x_1) + \alpha_2 f(x_2)$" at (4.05, 2.25), in blue, above
write "$\text{Graph Point } f(\alpha_1 x_1 + \alpha_2 x_2)$" at (4.05, 1.45), in teal, right
write "$\text{Supporting Tangent Line}$" at (5.5, 2.0), in red, below right
write "$x_1$" at (2.0, 0.0), in black, below
write "$\alpha_1 x_1 + \alpha_2 x_2$" at (4.0, 0.0), in purple, below
write "$x_2$" at (6.0, 0.0), in black, below
```

### The Master Equivalence Architecture
For differentiable functions, the chord-based definition reconciles completely with differential and geometric characterizations:

$$\begin{gather}
\textbf{Theorem: The Master Equivalence Architecture of Convexity} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be differentiable on an open interval } I \subseteq \mathbb{R}. \\[2mm]
\text{The following statements are logically equivalent:} \\[3mm]
\begin{align}
\text{1. Chord Convexity:} \quad &\forall x_1, x_2 \in I, \ \alpha_1, \alpha_2 \ge 0 \ (\alpha_1 + \alpha_2 = 1) \implies f(\alpha_1 x_1 + \alpha_2 x_2) \le \alpha_1 f(x_1) + \alpha_2 f(x_2). \\[2mm]
\text{2. Monotonic Secant Slopes:} \quad &\text{For any fixed } x_0 \in I, \text{ the slope function } x \mapsto \frac{f(x) - f(x_0)}{x - x_0} \text{ is non-decreasing on } I \setminus \{x_0\}. \\[2mm]
\text{3. Supporting Tangent Lines:} \quad &\forall x_0 \in I, \text{ the tangent line lies entirely below the graph:} \\[2mm]
&f(x) \ge f(x_0) + f'(x_0)(x - x_0) \quad \forall x \in I. \\[2mm]
\text{4. Monotonicity of Derivative:} \quad &f': I \to \mathbb{R} \text{ is monotonically non-decreasing on } I. \\[2mm]
\text{5. Second Derivative Criterion:} \quad &\text{If } f \in C^2(I), \text{ then } f''(x) \ge 0 \quad \forall x \in I.
\end{align}
\end{gather}$$
(see [[Proof of the Master Equivalence Architecture of Convex Functions]])

### Jensen's Inequality
By mathematical induction, the definition of convex functions extends from two points to arbitrary finite convex combinations:

$$\begin{gather}
\textbf{Theorem: Jensen’s Inequality} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be convex on an interval } I. \text{ For any finite collection of points } x_1, \dots, x_n \in I \\[2mm]
\text{and non-negative weights } \alpha_1, \dots, \alpha_n \ge 0 \text{ satisfying } \sum_{i=1}^n \alpha_i = 1\text{:} \\[3.5mm]
f\left( \sum_{i=1}^n \alpha_i x_i \right) \le \sum_{i=1}^n \alpha_i f(x_i).
\end{gather}$$
(see [[Proof of Jensen's Inequality for Convex Functions]])

---

# Classical Analytic Inequalities

Applying Jensen's inequality to standard convex functions generates the fundamental inequalities of mathematical analysis:

$$\begin{gather}
\textbf{Theorem: The Master Classical Inequalities} \\[5mm]
\begin{align}
\text{1. Young's Inequality:} \quad &\text{Let } a, b \ge 0 \text{ and let } p, q > 1 \text{ be conjugate exponents } \left(\frac{1}{p} + \frac{1}{q} = 1\right). \text{ Then:} \\[2mm]
&ab \le \frac{a^p}{p} + \frac{b^q}{q}. \\[3mm]
\text{2. Hölder's Inequality:} \quad &\text{For any vectors } a = (a_1, \dots, a_n) \text{ and } b = (b_1, \dots, b_n) \text{ in } \mathbb{R}^n\text{:} \\[2mm]
&\sum_{k=1}^n |a_k b_k| \le \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} \left( \sum_{k=1}^n |b_k|^q \right)^{1/q}. \\[3mm]
\text{3. Minkowski's Inequality:} \quad &\text{For } p \ge 1 \text{ and } a, b \in \mathbb{R}^n\text{:} \\[2mm]
&\left( \sum_{k=1}^n |a_k + b_k|^p \right)^{1/p} \le \left( \sum_{k=1}^n |a_k|^p \right)^{1/p} + \left( \sum_{k=1}^n |b_k|^p \right)^{1/p}.
\end{align}
\end{gather}$$
(see [[Proof of the Classical Inequalities of Young, Hölder, and Minkowski]])

$$\begin{gather}
\textbf{Theorem: Monotonicity of Generalized Power Means} \\[5mm]
\text{For positive weights } \alpha_i > 0 \text{ with } \sum_{i=1}^n \alpha_i = 1 \text{ and positive values } x_i > 0, \text{ define the power mean:} \\[3.5mm]
M_t(x; \alpha) := \left( \sum_{i=1}^n \alpha_i x_i^t \right)^{1/t} \quad (t \neq 0), \quad M_0(x; \alpha) := \prod_{i=1}^n x_i^{\alpha_i}. \\[3.5mm]
\text{The function } t \mapsto M_t(x; \alpha) \text{ is strictly increasing on } \mathbb{R} \text{ (unless all } x_i \text{ are identical), and is continuous at } t = 0.
\end{gather}$$
(see [[Proof of the Monotonicity of Generalized Power Means]])

---

# L'Hôpital's Rules for Indeterminate Limits

Evaluating limits of indeterminate forms $\frac{0}{0}$ or $\frac{\infty}{\infty}$ is resolved through Cauchy’s Generalized Mean Value Theorem:

$$\begin{gather}
\textbf{Theorem: L'Hôpital’s Rules for Indeterminate Limits} \\[5mm]
\text{Let } -\infty \le a < b \le \infty. \text{ Let } f, g: (a, b) \to \mathbb{R} \text{ be differentiable, with } g'(x) \neq 0 \text{ on } (a, b). \\[2mm]
\text{Suppose that either:} \\[2mm]
\text{(I) } \lim_{x \to a^+} f(x) = 0 \quad \text{and} \quad \lim_{x \to a^+} g(x) = 0 \quad (\text{Form } 0/0), \quad \text{or} \\[2mm]
\text{(II) } \lim_{x \to a^+} |g(x)| = \infty \quad (\text{Form } \infty/\infty). \\[3mm]
\text{If the limit of the ratio of derivatives exists in } \overline{\mathbb{R}}\text{:} \\[3.5mm]
\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = L \in [-\infty, \infty], \\[3.5mm]
\text{then the limit of the original ratio exists and coincides with } L\text{:} \\[2mm]
\lim_{x \to a^+} \frac{f(x)}{g(x)} = \lim_{x \to a^+} \frac{f'(x)}{g'(x)} = L.
\end{gather}$$
(see [[Proof of L'Hôpital's Rules for Indeterminate Limits]])

>[!danger]+ Analytical Pitfall: Non-Reciprocal Nature of L'Hôpital's Rule
>L'Hôpital's rule is an implication, not an equivalence. The existence of $\lim \frac{f'}{g'}$ implies the existence of $\lim \frac{f}{g}$, but the converse fails. Consider:
>$$f(x) = x + \sin x, \quad g(x) = x \quad \text{as } x \to \infty \tag{1}$$
>Here $\frac{f(x)}{g(x)} = 1 + \frac{\sin x}{x} \to 1$. However, $\frac{f'(x)}{g'(x)} = 1 + \cos x$, which oscillates endlessly between 0 and 2. L'Hôpital's rule does not apply, yet the limit of the original ratio exists.

---

# Asymptotes and the Systematic Curve-Sketching Protocol

$$\begin{gather}
\textbf{Definition: Asymptotes} \\[5mm]
\text{1. Vertical Asymptote: The straight line } x = x_0 \text{ is a vertical asymptote if } \lim_{x \to x_0^\pm} |f(x)| = \infty. \\[2mm]
\text{2. Oblique Asymptote: The straight line } y = kx + b \text{ is an oblique asymptote of } f \text{ as } x \to \infty \text{ if:} \\[3.5mm]
\lim_{x \to \infty} \big( f(x) - (kx + b) \big) = 0.
\end{gather}$$

$$\begin{gather}
\textbf{Proposition: Asymptote Computation Formulas} \\[5mm]
\text{A straight line } y = kx + b \text{ is an oblique asymptote as } x \to \infty \text{ if and only if both limits exist in } \mathbb{R}\text{:} \\[3.5mm]
k = \lim_{x \to \infty} \frac{f(x)}{x}, \quad b = \lim_{x \to \infty} \big( f(x) - kx \big).
\end{gather}$$
If $k = 0$, the line $y = b$ is termed a *horizontal asymptote*.

$$\begin{gather}
\textbf{Definition: Points of Inflection} \\[5mm]
\text{A point } x_0 \text{ is a point of inflection of the graph of } f \text{ if } f \text{ has a tangent line at } x_0, \\[2mm]
\text{and there exists } \delta > 0 \text{ such that } f \text{ is strictly convex on } (x_0 - \delta, x_0) \text{ and strictly concave on } (x_0, x_0 + \delta) \\[2mm]
\text{(or vice versa). At an inflection point, the curve crosses its tangent line.}
\end{gather}$$

---

# The Legendre-Fenchel Transform and Convex Duality

$$\begin{gather}
\textbf{Definition: The Legendre-Fenchel Transform} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be a strictly convex function defined on an interval } I \subseteq \mathbb{R}. \\[2mm]
\text{Its Legendre-Fenchel conjugate } f^*: \text{dom}(f^*) \to \mathbb{R} \text{ is the function defined by the dual supremum:} \\[3.5mm]
f^*(p) := \sup_{x \in I} \big( px - f(x) \big).
\end{gather}$$

$$\begin{gather}
\textbf{Theorem: Properties of the Legendre Transform and Involution} \\[5mm]
\text{Let } f: I \to \mathbb{R} \text{ be strictly convex and } C^1. \\[2mm]
\text{1. The supremum defining } f^*(p) \text{ is attained at the unique point } x \in I \text{ where } f'(x) = p, \text{ yielding:} \\[3.5mm]
f^*(p) = p \cdot (f')^{-1}(p) - f\big((f')^{-1}(p)\big). \\[3mm]
\text{2. Involution: Under appropriate closure conditions, } (f^*)^* = f. \\[3mm]
\text{3. Young-Fenchel Duality Inequality: For all } x \in I \text{ and all dual slopes } p \in \text{dom}(f^*)\text{:} \\[3.5mm]
px \le f(x) + f^*(p).
\end{gather}$$
(see [[Proof of the Involution and Duality of the Legendre-Fenchel Transform]])

---

# Rigorous 1D Optimization

Applied optimization frequently requires finding global extrema on open or unbounded intervals (e.g., $(0, \infty)$) where the Weierstrass Extreme Value Theorem does not directly apply. The following theorem provides the analytical justification:

$$\begin{gather}
\textbf{Theorem: The Single Critical Point Unimodality Theorem} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be an arbitrary interval (open, closed, or unbounded) and let } f: I \to \mathbb{R} \text{ be continuous.} \\[2mm]
\text{Suppose } c \in \text{int}(I) \text{ is the unique critical number of } f \text{ in } I. \\[2mm]
\text{If } f \text{ has a local minimum (resp. local maximum) at } c, \text{ then } f(c) \text{ is the strict absolute minimum} \\[2mm]
\text{(resp. strict absolute maximum) of } f \text{ on all of } I\text{:} \\[3.5mm]
f(c) < f(x) \quad \forall x \in I \setminus \{c\}.
\end{gather}$$
(see [[Proof of the Single Critical Point Unimodality Theorem]])

>[!example]- Applied Model: Fermat's Principle and Snell's Law of Refraction
>Consider a light ray traveling from point $A(0, a)$ in medium 1 (speed $v_1$) to point $B(d, -b)$ in medium 2 (speed $v_2$), crossing the interface $y = 0$ at coordinate $x \in (0, d)$.
>The total transit time is:
>$$T(x) = \frac{\sqrt{x^2 + a^2}}{v_1} + \frac{\sqrt{(d - x)^2 + b^2}}{v_2} \tag{2}$$
>Differentiating with respect to $x$:
>$$T'(x) = \frac{x}{v_1 \sqrt{x^2 + a^2}} - \frac{d - x}{v_2 \sqrt{(d - x)^2 + b^2}} = \frac{\sin\theta_1}{v_1} - \frac{\sin\theta_2}{v_2} \tag{3}$$
>Because $T''(x) > 0$, $T(x)$ is strictly convex on $(0, d)$, admitting a unique critical point where $T'(x) = 0$. By the Single Critical Point Unimodality Theorem, this stationary point is the unique global minimum of transit time, yielding Snell's Law:
>$$\frac{\sin\theta_1}{v_1} = \frac{\sin\theta_2}{v_2} \tag{4}$$

>[!example]- Quantitative Economics: The Baumol-Tobin Cash Inventory Optimization
>A financial corporation managing annual cash outflows $Y$ transfers capital in lots of size $K > 0$. Each transaction incurs a fixed brokerage fee $F > 0$, while idle cash incurs an opportunity interest cost $r > 0$. The total annual inventory cost is:
>$$C(K) = \frac{Y}{K}F + \frac{K}{2}r, \quad K \in (0, \infty) \tag{5}$$
>Computing the derivative:
>$$C'(K) = -\frac{YF}{K^2} + \frac{r}{2} = 0 \implies K^* = \sqrt{\frac{2YF}{r}} \tag{6}$$
>Because $C''(K) = \frac{2YF}{K^3} > 0$ on $(0, \infty)$, $K^*$ is the unique critical point. By the Single Critical Point Unimodality Theorem, the square-root lot size $K^*$ minimizes inventory costs globally.
