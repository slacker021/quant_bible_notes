---
dg-publish: true
---
# The Exhaustion of Domains and Singular Integrands: Foundations of Improper Integration
The classical Riemann integral developed in [[Chapter 1 - Definition of the Integral and Description of the Set of Integrable Functions|Chapter 1]], [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|Chapter 2]], and [[Chapter 3 - The Integral and the Derivative|Chapter 3]] was formulated upon two structural hypotheses:
1. **Compactness of the Integration Domain:** The set over which the summation process operates is a closed, bounded interval $[a, b] \subset \mathbb{R}$ of finite Euclidean length $|b - a| < \infty$.
2. **Uniform Boundedness of the Integrand:** The mapping $f: [a, b] \to \mathbb{R}$ admits finite bounds, satisfying $\sup_{x \in [a, b]} |f(x)| < \infty$.

The theory of *improper integrals* extends the reach of integral calculus beyond these two classical boundaries, with the improper integral not as a new variety of summation, but as a *topological exhaustion process*. The Riemann integral across an expanding or contracting compact subdomain where classical real analysis holds unconditionally is first computed, before being passed to the analytical limit as the subdomain exhausts the original singular domain.

### Improper Integrals of the First Kind: Unbounded Domains
The first extension addresses situations where the integrand remains bounded on every compact subinterval, but the domain of integration extends indefinitely to infinity: 
$$
\begin{gather}
\textbf{Definition: Improper Integral on a Semi-Infinite Interval } [a, \infty) \\[5mm]
\text{Let } a \in \mathbb{R}, \text{ and let } f: [a, \infty) \to \mathbb{R} \text{ be a function satisfying } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[2mm]
\text{The \textit{improper integral of the first kind} of } f \text{ over } [a, \infty) \text{ is defined as the analytical limit:} \\[3.5mm]
\int_a^\infty f(x)\,dx := \lim_{B \to \infty} \int_a^B f(x)\,dx. \\[3.5mm]
\text{If this limit exists and is finite in } \mathbb{R}, \text{ the improper integral is termed \textit{convergent},} \\[2mm]
\text{and the finite limiting value is assigned as the value of the integral.} \\[2mm]
\text{If the limit does not exist in } \mathbb{R}, \text{ the improper integral is termed \textit{divergent}.}
\end{gather}
$$
The geometric exhaustion process for the unbounded tail domain is illustrated below:
```easy-tikz
title $\text{Geometric Exhaustion of Unbounded Tail Domains}$
xlabel $x$
ylabel $y$
show x from 0 to 10 and y from 0 to 5
axes on the edges
size 12 x 8
plot f(x) = 4.0 / (x + 0.5), from x = 0.5 to 9.5, in teal, very thick
draw a line from (1.0, 0) to (1.0, 2.67), in orange, thick
draw a line from (4.0, 0) to (4.0, 0.89), in green, thick
draw a line from (7.0, 0) to (7.0, 0.53), in red, thick
draw a line from (1.0, 0) to (9.5, 0), in gray, thin
raw tool {"type":"points","name":"P1","color":"purple","points":"(1.0, 2.67);"}
raw tool {"type":"points","name":"P2","color":"blue","points":"(4.0, 0.89);"}
raw tool {"type":"points","name":"P3","color":"magenta","points":"(7.0, 0.53);"}
draw an arrow from (1.45, 3.8) to (0.4, 2.2) in purple
draw an arrow from (6.9, 2.05) to (9.5, 0.75) in magenta
write "$a$" at (1.0, -0.4) in orange, below
write "$B_1$" at (4.0, -0.4) in green, below
write "$B_2$" at (7.0, -0.4) in red, below
write "$f(x)$" at (0, 4.25) in teal, right
write "$(a, 2.67)$" at (1.8, 2.7) in purple, center
write "$(4.0, 0.89)$" at (4, 1.3) in blue, center
write "$(7.0,0.53)$" at (6.9, 0.85) in magenta, center
write "$F(B) = \\int_{a}^B f(x) \\ dx$" at (2.8, 3.75) in purple, center
write "$\\lim_{B \\to \\infty} F(B)$" at (5.9, 2.1) in magenta, center
```
In an identical manner, improper integration across left-unbounded semi-infinite intervals is defined symmetrically:
$$
\begin{gather}
\textbf{Definition: Improper Integral on a Semi-Infinite Interval } (-\infty, b] \\[5mm]
\text{Let } b \in \mathbb{R}, \text{ and let } f: (-\infty, b] \to \mathbb{R} \text{ be a function satisfying } f \in \mathcal{R}[A, b] \text{ for all } A \le b. \\[2mm]
\text{The \textit{improper integral of the first kind} of } f \text{ over } (-\infty, b] \text{ is defined as the analytical limit:} \\[3.5mm]
\int_{-\infty}^b f(x)\,dx := \lim_{A \to -\infty} \int_A^b f(x)\,dx. \\[3.5mm]
\text{If this limit exists and is finite in } \mathbb{R}, \text{ the improper integral is termed \textit{convergent};} \\[2mm]
\text{otherwise, the improper integral is termed \textit{divergent}.}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Improper Integral Over the Entire Real Line } (-\infty, \infty) \\[5mm]
\text{Let } f: \mathbb{R} \to \mathbb{R} \text{ be a function satisfying } f \in \mathcal{R}[A, B] \text{ for all compact intervals } [A, B] \subset \mathbb{R}. \\[2mm]
\text{The \textit{improper integral} of } f \text{ over } (-\infty, \infty) \text{ is defined by decomposing} \\[2mm]
\text{the real continuum at an arbitrary partition node } c \in \mathbb{R}: \\[3.5mm]
\int_{-\infty}^\infty f(x)\,dx := \int_{-\infty}^c f(x)\,dx + \int_c^\infty f(x)\,dx. \\[3.5mm]
\text{The integral over } (-\infty, \infty) \text{ is termed \textit{convergent} if and only if both component} \\[2mm]
\text{improper integrals } \int_{-\infty}^c f(x)\,dx \text{ and } \int_c^\infty f(x)\,dx \text{ converge independently.} \\[2mm]
\text{If at least one constituent integral diverges, the integral } \int_{-\infty}^\infty f(x)\,dx \text{ is declared \textit{divergent}.}
\end{gather}
$$

##### Invariance Under the Choice of Partition Node:
Observe that the convergence status and the numerical value of the improper integral over $(-\infty, \infty)$ are strictly invariant with respect to the chosen intermediate point $c$. Indeed, if $c_1 < c_2$ are two real numbers, then for any $A < c_1$ and $B > c_2$, the interval additivity of the proper Riemann integral established in [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|Chapter 2]] yields:
$$
\begin{gather}
\int_A^B f(x)\,dx = \int_A^{c_1} f(x)\,dx + \int_{c_1}^{c_2} f(x)\,dx + \int_{c_2}^B f(x)\,dx \tag{4}
\end{gather}
$$
Passing to the independent limits $A \to -\infty$ and $B \to \infty$ demonstrates that:
$$
\begin{gather}
\int_{-\infty}^{c_1} f(x)\,dx + \int_{c_1}^\infty f(x)\,dx = \int_{-\infty}^{c_2} f(x)\,dx + \int_{c_2}^\infty f(x)\,dx \tag{5}
\end{gather}
$$
thereby confirming that the partition node $c$ serves merely as an analytical scaffold.

### Improper Integrals of the Second Kind: Singular Integrands on Bounded Intervals
The second extension addresses the dual geometric phenomenon: the domain of integration $[a, b]$ is bounded, but the integrand exhibits an unbounded asymptotic singularity at one or more points in the closure of the domain: 
$$
\begin{gather}
\textbf{Definition: Improper Integral with a Right-Endpoint Singularity} \\[5mm]
\text{Let } -\infty < a < b < \infty, \text{ and let } f: [a, b) \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[a, b - \varepsilon] \\[2mm]
\text{for every } \varepsilon \in (0, b - a), \text{ with } f \text{ potentially unbounded as } x \to b^-. \\[2mm]
\text{The \textit{improper integral of the second kind} of } f \text{ over } [a, b] \text{ is defined by:} \\[3.5mm]
\int_a^b f(x)\,dx := \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} f(x)\,dx. \\[3.5mm]
\text{If this one-sided limit exists as a finite real scalar, the improper integral \textit{converges};} \\[2mm]
\text{otherwise, the improper integral \textit{diverges}.}
\end{gather}
$$

Symmetrically, when the singularity resides at the left boundary point:
$$
\begin{gather}
\textbf{Definition: Improper Integral with a Left-Endpoint Singularity} \\[5mm]
\text{Let } -\infty < a < b < \infty, \text{ and let } f: (a, b] \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[a + \delta, b] \\[2mm]
\text{for every } \delta \in (0, b - a), \text{ with } f \text{ potentially unbounded as } x \to a^+. \\[2mm]
\text{The \textit{improper integral of the second kind} of } f \text{ over } [a, b] \text{ is defined by:} \\[3.5mm]
\int_a^b f(x)\,dx := \lim_{\delta \to 0^+} \int_{a + \delta}^b f(x)\,dx. \\[3.5mm]
\text{If this one-sided limit exists as a finite real scalar, the improper integral \textit{converges};} \\[2mm]
\text{otherwise, the improper integral \textit{diverges}.}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Improper Integral with an Interior Singularity} \\[5mm]
\text{Let } c \in (a, b) \text{ be an interior singular point of } f: [a, b] \setminus \{c\} \to \mathbb{R}, \\[2mm]
\text{and suppose } f \in \mathcal{R}[a, c - \varepsilon_1] \text{ and } f \in \mathcal{R}[c + \varepsilon_2, b] \text{ for all sufficiently small } \varepsilon_1, \varepsilon_2 > 0. \\[2mm]
\text{The \textit{improper integral} of } f \text{ over } [a, b] \text{ is defined by the independent sum:} \\[3.5mm]
\int_a^b f(x)\,dx := \lim_{\varepsilon_1 \to 0^+} \int_a^{c - \varepsilon_1} f(x)\,dx + \lim_{\varepsilon_2 \to 0^+} \int_{c + \varepsilon_2}^b f(x)\,dx. \\[3.5mm]
\text{The improper integral \textit{converges} if and only if both one-sided limits exist independently in } \mathbb{R}.
\end{gather}
$$

> [!danger]+ Intuition: The Topological Exhaustion Principle
> The improper integral as an architectural exhaustion of an incomplete geometric territory can be visualized. When an engineer seeks to calculate the mass of an infinitely long tapered beam or a planar region that shoots upward into an infinite spire, measuring the whole object simultaneously is physically impossible. 
> 
> An artificial boundary—a safety gate at position $B$ or distance $\varepsilon$ from the singularity is placed. On the safe side of the gate, the territory is compact and the density is bounded, allowing the classical Riemann quadrature developed in Chapter 1 to evaluate the exact mass $F(B)$ or $F(\varepsilon)$. One then systematically recedes the gate toward infinity or toward the singular boundary. If the accumulated mass stabilizes toward a definitive finite equilibrium, the infinite structure possesses finite macroscopic measure. If the mass grows without bound or oscillates chaotically, the structure cannot be assigned a finite measure.

### The Cauchy Principal Value: Symmetric Cancellation Versus Genuine Convergence
A frequent point of conceptual confusion in analysis arises from coupling the limit processes at opposite ends of a singular point. To preserve the additive and structural integrity of integration, analysis demands that exhaustion boundaries recede *independently*. When the boundaries are forced to recede symmetrically at identical rates, one obtains the *Cauchy Principal Value* (designated in the Soviet literature by *valeur principale*, abbreviated $\operatorname{v.p.}$ or $\operatorname{p.v.}$): 
$$
\begin{gather}
\textbf{Definition: Cauchy Principal Value on Unbounded Domains} \\[5mm]
\text{Let } f: \mathbb{R} \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[-R, R] \text{ for all } R > 0. \\[2mm]
\text{The \textit{Cauchy Principal Value} of the improper integral of } f \text{ over } (-\infty, \infty) \\[2mm]
\text{is defined by the single symmetric limit:} \\[3.5mm]
\operatorname{p.v.} \int_{-\infty}^\infty f(x)\,dx := \lim_{R \to \infty} \int_{-R}^R f(x)\,dx.
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Cauchy Principal Value for an Interior Singularity} \\[5mm]
\text{Let } f \text{ have an isolated singularity at an interior node } c \in (a, b), \text{ with } f \in \mathcal{R}[a, c - \varepsilon] \\[2mm]
\text{and } f \in \mathcal{R}[c + \varepsilon, b] \text{ for all sufficiently small } \varepsilon > 0. \\[2mm]
\text{The \textit{Cauchy Principal Value} of the integral of } f \text{ over } [a, b] \text{ is defined by:} \\[3.5mm]
\operatorname{p.v.} \int_a^b f(x)\,dx := \lim_{\varepsilon \to 0^+} \left( \int_a^{c - \varepsilon} f(x)\,dx + \int_{c + \varepsilon}^b f(x)\,dx \right).
\end{gather}
$$

> [!warning]+ Warning: The Principal Value Does Not Imply Convergence
> The existence of the Cauchy Principal Value is a strictly weaker condition than the convergence of the improper integral. If an improper integral converges over $(-\infty, \infty)$, its Cauchy Principal Value necessarily exists and coincides with the value of the improper integral. However, the converse assertion is categorically false.
> 
> Consider the elementary identity mapping $f(x) = x$ across $(-\infty, \infty)$. For any finite symmetric boundary $R > 0$, the anti-symmetry of the integrand implies:
> $$ \int_{-R}^R x\,dx = \left[ \frac{x^2}{2} \right]_{-R}^R = \frac{R^2}{2} - \frac{(-R)^2}{2} = 0 $$
> Consequently, the Cauchy Principal Value converges to zero:
> $$ \operatorname{p.v.} \int_{-\infty}^\infty x\,dx = \lim_{R \to \infty} 0 = 0 $$
> Yet the improper integral $\int_{-\infty}^\infty x\,dx$ is utterly divergent! Selecting independent limits $A \to -\infty$ and $B \to \infty$ reveals that:
> $$ \lim_{B \to \infty} \int_0^B x\,dx = \lim_{B \to \infty} \frac{B^2}{2} = +\infty, \qquad \lim_{A \to -\infty} \int_A^0 x\,dx = \lim_{A \to -\infty} \left(-\frac{A^2}{2}\right) = -\infty $$
> The apparent convergence of the Cauchy Principal Value was an artifact of forcing equal cancellation rates between $+\infty$ and $-\infty$. A similar pathology occurs for $f(x) = 1/x$ on $[-1, 1]$, where $\operatorname{p.v.} \int_{-1}^1 \frac{dx}{x} = 0$, while the genuine improper integral diverges at the origin.

### Vector Space Linearity and Domain Additivity
Convergent improper integrals inherit the core algebraic properties of proper Riemann integrals established in Chapter 2, forming a real vector space: 
$$
\begin{gather}
\textbf{Proposition: Vector Space Linearity of Improper Integrals} \\[5mm]
\text{Let } f, g: [a, \infty) \to \mathbb{R} \text{ be functions whose improper integrals } \int_a^\infty f(x)\,dx \text{ and } \int_a^\infty g(x)\,dx \text{ converge.} \\[2mm]
\text{Then for any scalars } \alpha, \beta \in \mathbb{R}, \text{ the improper integral of the linear combination } \alpha f + \beta g \text{ converges, and:} \\[3.5mm]
\int_a^\infty \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^\infty f(x)\,dx + \beta \int_a^\infty g(x)\,dx.
\end{gather}
$$
(see [[Proof of Vector Space Linearity of Improper Integrals]])

This identity follows directly from the linearity of the proper Riemann integral on each compact subinterval $[a, B]$:
$$
\begin{gather}
\int_a^B \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^B f(x)\,dx + \beta \int_a^B g(x)\,dx \tag{12}
\end{gather}
$$
combined with the elementary algebraic limit theorem for convergent sequences and functions: 
$$
\begin{gather}
\textbf{Proposition: Domain Additivity for Improper Integrals} \\[5mm]
\text{Let } f: [a, \infty) \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[2mm]
\text{For any intermediate coordinate } c \in (a, \infty), \text{ the improper integral } \int_a^\infty f(x)\,dx \text{ converges} \\[2mm]
\text{if and only if } \int_c^\infty f(x)\,dx \text{ converges. In the event of convergence:} \\[3.5mm]
\int_a^\infty f(x)\,dx = \int_a^c f(x)\,dx + \int_c^\infty f(x)\,dx \\[3.5mm]
\text{where } \int_a^c f(x)\,dx \text{ is an ordinary proper Riemann integral.}
\end{gather}
$$
(see [[Proof of Domain Additivity for Improper Integrals]])

### Advanced Operations: Integration by Parts and Substitution
The two foundational operational tools of differential and integral calculus—integration by parts and integration by substitution—extend naturally to improper integrals under appropriate asymptotic boundary behavior: 
$$
\begin{gather}
\textbf{Proposition: Integration by Parts for Improper Integrals} \\[5mm]
\text{Let } u, v \in C^1[a, \infty) \text{ be continuously differentiable functions on } [a, \infty). \\[2mm]
\text{If the asymptotic limit } \lim_{x \to \infty} u(x)v(x) \text{ exists and is finite, and if the improper integral} \\[2mm]
\int_a^\infty u'(x)v(x)\,dx \text{ converges, then the improper integral } \int_a^\infty u(x)v'(x)\,dx \text{ converges, and satisfies:} \\[3.5mm]
\int_a^\infty u(x)v'(x)\,dx = \big[ u(x)v(x) \big]_a^\infty - \int_a^\infty u'(x)v(x)\,dx \\[3.5mm]
\text{where the asymptotic evaluation bracket is defined by:} \\[2mm]
\big[ u(x)v(x) \big]_a^\infty := \lim_{B \to \infty} u(B)v(B) - u(a)v(a) = \lim_{B \to \infty} \big[ u(x)v(x) \big]_a^B.
\end{gather}
$$
(see [[Proof of Integration by Parts for Improper Integrals]])

$$
\begin{gather}
\textbf{Proposition: Change of Variable (Substitution) for Improper Integrals} \\[5mm]
\text{Let } \phi: [\alpha, \beta) \to [a, b) \text{ be a continuously differentiable, strictly increasing bijection satisfying} \\[2mm]
\phi(\alpha) = a \quad \text{and} \quad \lim_{t \to \beta^-} \phi(t) = b \quad (\text{where } b, \beta \le \infty). \\[2mm]
\text{Let } f: [a, b) \to \mathbb{R} \text{ be continuous. Then the improper integrals share identical convergence status,} \\[2mm]
\text{and if either converges, they evaluate to the same value:} \\[3.5mm]
\int_a^b f(x)\,dx = \int_\alpha^\beta f\big(\phi(t)\big) \phi'(t)\,dt.
\end{gather}
$$
(see [[Proof of Change of Variable (Substitution) for Improper Integrals]])

---
# Convergence Criteria for Non-Negative Integrands
When analyzing the convergence of an improper integral whose integrand changes signs, cancellation between positive and negative lobes introduces oscillatory complexities. In contrast, when the integrand is strictly non-negative ($f(x) \ge 0$), the geometric area accumulates monotonically. In this setting, the convergence of the improper integral simplifies to the question of whether the accumulating area remains bounded above.

### The Monotonicity Criterion
Let $f: [a, \infty) \to \mathbb{R}$ be a non-negative function satisfying $f(x) \ge 0$ for all $x \ge a$, with $f \in \mathcal{R}[a, B]$ for every $B \ge a$. Consider the variable upper limit accumulation function:
$$
\begin{gather}
F(B) := \int_a^B f(x)\,dx \qquad (B \ge a) \tag{17}
\end{gather}
$$
For any two coordinates $a \le B_1 \le B_2$, the interval additivity and monotonicity of the Riemann integral established in Chapter 2 ensure that:
$$
\begin{gather}
F(B_2) - F(B_1) = \int_a^{B_2} f(x)\,dx - \int_a^{B_1} f(x)\,dx = \int_{B_1}^{B_2} f(x)\,dx \ge 0 \tag{18}
\end{gather}
$$
The accumulation mapping $F: [a, \infty) \to \mathbb{R}$ is therefore a monotonically non-decreasing function of the exhaustion parameter $B$: 
$$
\begin{gather}
\textbf{Theorem: Monotonicity Criterion for Non-Negative Improper Integrals} \\[5mm]
\text{Let } f: [a, \infty) \to \mathbb{R} \text{ be non-negative on } [a, \infty), \text{ with } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[2mm]
\text{The improper integral } \int_a^\infty f(x)\,dx \text{ converges if and only if the accumulation function} \\[2mm]
F(B) = \int_a^B f(x)\,dx \text{ is bounded above on } [a, \infty). \\[3.5mm]
\text{Whenever bounded, the value of the improper integral coincides with the supremum:} \\[3.5mm]
\int_a^\infty f(x)\,dx = \sup_{B \ge a} \int_a^B f(x)\,dx = \lim_{B \to \infty} F(B). \\[2mm]
\text{If } F(B) \text{ is unbounded above, the improper integral diverges to } +\infty.
\end{gather}
$$
(see [[Proof of the Monotonicity Criterion for Non-Negative Improper Integrals]])

The Monotonicity Criterion establishes that for non-negative integrands, oscillation is impossible: an improper integral of a non-negative function either converges to a finite positive number or diverges strictly to $+\infty$.

### Direct and Limit Comparison Tests
Because convergence for non-negative functions is governed entirely by boundedness, one can establish the convergence or divergence of an unknown integral by bounding it against a known benchmark: 
$$
\begin{gather}
\textbf{Theorem: Direct and Limit Comparison Tests for Improper Integrals} \\[5mm]
\text{Let } f, g: [a, \infty) \to \mathbb{R} \text{ be functions such that } f, g \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[3.5mm]
\textbf{Part 1 (Direct Comparison):} \\[2mm]
\text{Suppose that } 0 \le f(x) \le g(x) \text{ for all } x \ge a. \\[2mm]
\text{1. If } \int_a^\infty g(x)\,dx \text{ converges, then } \int_a^\infty f(x)\,dx \text{ converges, and satisfies:} \\[3.5mm]
\int_a^\infty f(x)\,dx \le \int_a^\infty g(x)\,dx. \\[2mm]
\text{2. If } \int_a^\infty f(x)\,dx \text{ diverges to } +\infty, \text{ then } \int_a^\infty g(x)\,dx \text{ diverges to } +\infty. \\[3.5mm]
\textbf{Part 2 (Limit Comparison):} \\[2mm]
\text{Suppose that } f(x) > 0 \text{ and } g(x) > 0 \text{ on } [a, \infty), \text{ and suppose the asymptotic limit exists:} \\[3.5mm]
L := \lim_{x \to \infty} \frac{f(x)}{g(x)}. \\[2mm]
\text{1. If } 0 < L < \infty, \text{ then } \int_a^\infty f(x)\,dx \text{ and } \int_a^\infty g(x)\,dx \text{ share identical convergence status.} \\[2mm]
\text{2. If } L = 0 \text{ and } \int_a^\infty g(x)\,dx \text{ converges, then } \int_a^\infty f(x)\,dx \text{ converges.} \\[2mm]
\text{3. If } L = \infty \text{ and } \int_a^\infty g(x)\,dx \text{ diverges, then } \int_a^\infty f(x)\,dx \text{ diverges.}
\end{gather}
$$
(see [[Proof of the Direct and Limit Comparison Tests for Improper Integrals]])

> [!info]+ Remark: Asymptotic Scale Analysis
> In operational practice, the Limit Comparison Test is the primary workhorse for classifying algebraic integrands. If $f(x) \sim c\,x^{-\alpha}$ as $x \to \infty$ for some exponent $\alpha \in \mathbb{R}$ and constant $c > 0$, setting $g(x) = x^{-\alpha}$ produces $L = c \in (0, \infty)$. The convergence of the complex integral $\int_a^\infty f(x)\,dx$ is thereby reduced immediately to the convergence of the canonical power integral $\int_a^\infty x^{-\alpha}\,dx$.

### Canonical Benchmark Integrals: The $p$-Scale and Logarithmic Refinements
To execute the Direct and Limit Comparison Tests, real analysis requires an authoritative library of benchmark functions whose convergence behavior is completely solved. The primary benchmark is the family of power-law functions $x^{-p}$: 
$$
\begin{gather}
\textbf{Theorem: Convergence Criteria for Canonical p-Integrals} \\[5mm]
\textbf{Case 1 (Unbounded Tail Domain):} \\[2mm]
\text{For } a > 0, \text{ the improper integral of the first kind } \int_a^\infty \frac{dx}{x^p} \text{ converges if and only if } p > 1. \\[2mm]
\text{When } p > 1, \text{ its exact analytical value is:} \\[3.5mm]
\int_a^\infty \frac{dx}{x^p} = \frac{a^{1 - p}}{p - 1}. \\[2mm]
\text{When } p \le 1, \text{ the integral diverges to } +\infty. \\[5mm]
\textbf{Case 2 (Singular Endpoint Domain):} \\[2mm]
\text{For } b > 0, \text{ the improper integral of the second kind } \int_0^b \frac{dx}{x^p} \text{ converges if and only if } p < 1. \\[2mm]
\text{When } p < 1, \text{ its exact analytical value is:} \\[3.5mm]
\int_0^b \frac{dx}{x^p} = \frac{b^{1 - p}}{1 - p}. \\[2mm]
\text{When } p \ge 1, \text{ the integral diverges to } +\infty. \\[5mm]
\textbf{Case 3 (Logarithmic Refinement):} \\[2mm]
\text{For } a > 1, \text{ the logarithmic improper integral } \int_a^\infty \frac{dx}{x(\ln x)^p} \text{ converges if and only if } p > 1. \\[2mm]
\text{When } p > 1, \text{ its value is } \frac{(\ln a)^{1 - p}}{p - 1}; \text{ when } p \le 1, \text{ it diverges to } +\infty.
\end{gather}
$$
(see [[Proof of the Convergence Criteria for Canonical p-Integrals]])

> [!danger]+ Intuition: The Boundary Duality of Power Singularities
> The reader should reflect upon the profound geometric duality between Case 1 and Case 2 of the canonical $p$-integrals.
> - At infinity ($x \to \infty$), the domain of integration is infinitely wide. For the total area under the curve to remain finite, the graph of $f(x)$ must decay toward the horizontal axis with sufficient velocity. The threshold $p = 1$ (the harmonic hyperbola $1/x$) represents the critical dividing line: any exponent $p > 1$ forces the curve down fast enough to enclose a finite area, while $p \le 1$ allows area to leak out indefinitely.
> - At the origin ($x \to 0^+$), the domain is bounded, but the curve shoots upward into an infinitely tall vertical spire. For this spire to enclose a finite area, the integrand must blow up slowly enough. Here, $p < 1$ ensures that the singularity is sufficiently weak (e.g. $1/\sqrt{x}$), while $p \ge 1$ creates a spire that is too thick at its base to admit a finite area.
> 
> The harmonic function $f(x) = 1/x$ is uniquely hostile to integration: it diverges at both ends simultaneously! It diverges over $[1, \infty)$ because it decays too slowly, and it diverges over $(0, 1]$ because it blows up too rapidly.

---
# The Cauchy-Maclaurin Integral Test and Series Remainder Bounds
The structural parallel between improper integrals of the first kind $\int_1^\infty f(x)\,dx$ and infinite numerical series $\sum_{n=1}^\infty a_n$ is one of the most fruitful unifications in analysis. An infinite series can be interpreted as the integral of a piecewise-constant step function whose step heights equal the terms $a_n$. When a sequence $a_n = f(n)$ is generated by sampling a continuous, monotonically decreasing function, the smooth curve $y = f(x)$ weaves between the upper and lower Darboux-type step functions, locking the convergence of the discrete sum to the continuous quadrature: 
```easy-tikz
title $\text{The Cauchy-Maclaurin Integral Test: Staircase Rectangular Bounds}$
xlabel $x$
ylabel $y$
show x from 0 to 8 and y from 0 to 6
axes on the edges
size 12 x 8
plot f(x) = 4.5 / x, from x = 0.8 to 7.5, in teal, very thick
draw a line from (1.0, 0) to (1.0, 4.5), in orange, thick
draw a line from (1.0, 4.5) to (2.0, 4.5), in orange, thick
draw a line from (2.0, 0) to (2.0, 4.5), in orange, thick
draw a line from (2.0, 2.25) to (3.0, 2.25), in green, thick
draw a line from (3.0, 0) to (3.0, 2.25), in green, thick
draw a line from (3.0, 1.5) to (4.0, 1.5), in red, thick
draw a line from (4.0, 0) to (4.0, 1.5), in red, thick
draw a line from (4.0, 1.125) to (5.0, 1.125), in pink, thick
draw a line from (5.0, 0) to (5.0, 1.125), in pink, thick
write "$f(1)$" at (1.5, 4.8) in orange, above
write "$f(2)$" at (2.5, 2.5) in green, above
write "$f(3)$" at (3.5, 1.8) in red, above
write "$y = f(x)$" at (0.15, 6.1) in teal, right
write "$\\int_1^\\infty f(x)\\,dx \\le \\sum_{n=1}^\\infty f(n)$" at (5.4, 2.5) in purple, center
write "$f(4)$" at (4.5, 1.45) in magenta, center
```

### Discrete-Continuous Quadrature Duality
Let $f: [1, \infty) \to [0, \infty)$ be a continuous, monotonically decreasing function, satisfying:
$$
\begin{gather}
x_1 \le x_2 \implies f(x_1) \ge f(x_2) \ge 0 \tag{19}
\end{gather}
$$
For every integer $k \in \mathbb{N}$, the subinterval $[k, k + 1]$ has unit length $|[k, k + 1]| = 1$. The monotonicity condition of step 19 implies that for every $x \in [k, k + 1]$:
$$
\begin{gather}
f(k + 1) \le f(x) \le f(k) \tag{20}
\end{gather}
$$
Integrating the compound inequality of step 20 across $[k, k + 1]$ using the monotonicity of the proper Riemann integral yields:
$$
\begin{gather}
f(k + 1) \le \int_k^{k + 1} f(x)\,dx \le f(k) \tag{21}
\end{gather}
$$
Summing the left-hand inequality of step 21 over $k = 1, 2, \dots, N - 1$ produces a lower bound for the integral:
$$
\begin{gather}
\sum_{k=2}^N f(k) = \sum_{k=1}^{N - 1} f(k + 1) \le \sum_{k=1}^{N - 1} \int_k^{k + 1} f(x)\,dx = \int_1^N f(x)\,dx \tag{22}
\end{gather}
$$
Similarly, summing the right-hand inequality of step 21 over $k = 1, 2, \dots, N$ produces an upper bound:
$$
\begin{gather}
\int_1^{N + 1} f(x)\,dx = \sum_{k=1}^N \int_k^{k + 1} f(x)\,dx \le \sum_{k=1}^N f(k) \tag{23}
\end{gather}
$$
Combining step 22 and step 23 establishes the fundamental sandwich bounds governing the partial sums $S_N := \sum_{n=1}^N f(n)$ and the accumulation integrals:
$$
\begin{gather}
\int_1^{N + 1} f(x)\,dx \le \sum_{n=1}^N f(n) \le f(1) + \int_1^N f(x)\,dx \tag{24}
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Cauchy-Maclaurin Integral Test and Series Remainder Bounds} \\[5mm]
\text{Let } f: [1, \infty) \to [0, \infty) \text{ be a continuous, monotonically decreasing non-negative function.} \\[3.5mm]
\textbf{Part 1 (Convergence Equivalence):} \\[2mm]
\text{The infinite series } \sum_{n=1}^\infty f(n) \text{ converges if and only if the improper integral } \int_1^\infty f(x)\,dx \text{ converges.} \\[3.5mm]
\textbf{Part 2 (Rigorous Remainder Bounds):} \\[2mm]
\text{If the series converges to the sum } S := \sum_{n=1}^\infty f(n), \text{ then for every integer } N \ge 1, \\[2mm]
\text{the truncation remainder } R_N := S - \sum_{n=1}^N f(n) = \sum_{n=N+1}^\infty f(n) \text{ satisfies the sharp bounds:} \\[3.5mm]
\int_{N + 1}^\infty f(x)\,dx \le R_N \le \int_N^\infty f(x)\,dx. \\[3.5mm]
\textbf{Part 3 (The Euler-Mascheroni Constant):} \\[2mm]
\text{In the divergent harmonic case } f(x) = \frac{1}{x}, \text{ the sequence of differences } d_n := \sum_{k=1}^n \frac{1}{k} - \ln n \\[2mm]
\text{is strictly monotonically decreasing and bounded below by } 0. \text{ Consequently, the limit} \\[3.5mm]
\gamma := \lim_{n \to \infty} \left( \sum_{k=1}^n \frac{1}{k} - \ln n \right) \\[2mm]
\text{exists in } (0, 1]. \text{ The constant } \gamma \approx 0.5772156649\dots \text{ is the Euler-Mascheroni constant.}
\end{gather}
$$
(see [[Proof of the Cauchy-Maclaurin Integral Test and Series Remainder Bounds]])

The sequence of harmonic differences established in Part 3 isolates the discrete logarithmic defect:
$$
\begin{gather}
d_n := \sum_{k=1}^n \frac{1}{k} - \ln n \tag{25}
\end{gather}
$$
The limiting value of step 25 defines the fundamental Euler-Mascheroni constant:
$$
\begin{gather}
\gamma := \lim_{n \to \infty} \left( \sum_{k=1}^n \frac{1}{k} - \ln n \right) \tag{26}
\end{gather}
$$

### Concrete Applications to $p$-Series and Asymptotic Estimation
The immediate consequence of the Cauchy-Maclaurin Integral Test is the definitive classification of the Riemann $p$-series $\sum_{n=1}^\infty \frac{1}{n^p}$. Because $f(x) = x^{-p}$ is continuous and strictly decreasing on $[1, \infty)$ for all $p > 0$, the convergence of the series is identical to that of $\int_1^\infty x^{-p}\,dx$. By the canonical benchmarks, $\sum_{n=1}^\infty \frac{1}{n^p}$ converges if and only if $p > 1$.

Furthermore, Part 2 provides an effective numerical tool. When approximating the sum of a convergent series by its $N$-th partial sum $S_N$, the remainder $R_N = \sum_{n=N+1}^\infty n^{-p}$ is bounded by:
$$
\begin{gather}
\frac{1}{(p - 1)(N + 1)^{p - 1}} = \int_{N + 1}^\infty \frac{dx}{x^p} \le R_N \le \int_N^\infty \frac{dx}{x^p} = \frac{1}{(p - 1)N^{p - 1}} \tag{27}
\end{gather}
$$
This allows the computation of series to any desired precision with an explicitly controlled error bound.

---
# General Convergence Criteria for Oscillating Integrands
When an integrand oscillates, taking both positive and negative values on $[a, \infty)$, the accumulation function $F(B) = \int_a^B f(x)\,dx$ is no longer monotone. It can fluctuate, surge, and dip. Here, boundedness alone is insufficient to guarantee convergence (for example, $\int_0^B \sin x\,dx = 1 - \cos B$ is bounded in $[0, 2]$, but oscillates endlessly without converging). To rigorously detect convergence under oscillation, analysis deploys the Cauchy Criterion and the tests of Dirichlet and Abel.

### The Cauchy Criterion for Improper Integrals
The fundamental completeness of the real continuum $\mathbb{R}$ implies that a function $F(B)$ possesses a finite limit as $B \to \infty$ if and only if its values become arbitrarily close to each other for all sufficiently large parameters. Translated to improper integrals, this yields the intrinsic Cauchy Criterion: 
$$
\begin{gather}
\textbf{Theorem: Cauchy Criterion for Convergence of Improper Integrals} \\[5mm]
\text{Let } f: [a, \infty) \to \mathbb{R} \text{ be a function satisfying } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[2mm]
\text{The improper integral } \int_a^\infty f(x)\,dx \text{ converges if and only if for every } \varepsilon > 0, \\[2mm]
\text{there exists an exhaustion threshold } B_0 \ge a \text{ such that for all } B_1, B_2 > B_0: \\[3.5mm]
\left| \int_{B_1}^{B_2} f(x)\,dx \right| < \varepsilon.
\end{gather}
$$
(see [[Proof of the Cauchy Criterion for Convergence of Improper Integrals]])

An identical criterion governs improper integrals of the second kind: $\int_a^b f(x)\,dx$ (with singularity at $b$) converges if and only if for every $\varepsilon > 0$, there exists $\delta_0 > 0$ such that for all $\varepsilon_1, \varepsilon_2 \in (0, \delta_0)$:
$$
\begin{gather}
\left| \int_{b - \varepsilon_1}^{b - \varepsilon_2} f(x)\,dx \right| < \varepsilon \tag{28}
\end{gather}
$$

### Absolute Versus Conditional Convergence
The Cauchy Criterion naturally segregates convergent improper integrals into two fundamentally distinct analytical categories: those that converge because the total absolute area under the curve is finite, and those that converge solely due to delicate destructive interference between alternating positive and negative lobes: 
$$
\begin{gather}
\textbf{Definition: Absolute and Conditional Convergence} \\[5mm]
\text{Let } f: [a, \infty) \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[3.5mm]
\textbf{1. Absolute Convergence:} \\[2mm]
\text{The improper integral } \int_a^\infty f(x)\,dx \text{ is termed \textit{absolutely convergent} if} \\[2mm]
\text{the improper integral of its absolute value converges:} \\[3.5mm]
\int_a^\infty |f(x)|\,dx < \infty. \\[3.5mm]
\textbf{2. Conditional Convergence:} \\[2mm]
\text{The improper integral } \int_a^\infty f(x)\,dx \text{ is termed \textit{conditionally convergent} if} \\[2mm]
\int_a^\infty f(x)\,dx \text{ converges, but } \int_a^\infty |f(x)|\,dx = +\infty.
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Absolute Convergence Implies Convergence for Improper Integrals} \\[5mm]
\text{Let } f: [a, \infty) \to \mathbb{R} \text{ satisfy } f \in \mathcal{R}[a, B] \text{ for all } B \ge a. \\[2mm]
\text{If the improper integral } \int_a^\infty |f(x)|\,dx \text{ converges, then the improper integral } \int_a^\infty f(x)\,dx \text{ converges.} \\[2mm]
\text{Furthermore, the value of the integral is bounded by the integral of the absolute value:} \\[3.5mm]
\left| \int_a^\infty f(x)\,dx \right| \le \int_a^\infty |f(x)|\,dx.
\end{gather}
$$
(see [[Proof that Absolute Convergence Implies Convergence for Improper Integrals]])

The validity of this theorem hinges upon the absolute value inequality for proper Riemann integrals established in Chapter 2:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| \le \int_{B_1}^{B_2} |f(x)|\,dx \tag{30}
\end{gather}
$$
Whenever the absolute integral converges, the right side of step 30 can be made smaller than $\varepsilon$ by the Cauchy Criterion, which immediately forces the left side below $\varepsilon$.

### Dirichlet's and Abel's Tests for Improper Integrals
When an improper integral does not converge absolutely, comparison tests are powerless. To prove conditional convergence for products of the form $\int_a^\infty f(x)g(x)\,dx$, where $f(x)$ oscillates rapidly and $g(x)$ acts as an amplitude modulator, analysis relies on the continuous analogues of Dirichlet's and Abel's summation criteria. 

The analytical engine driving both proofs is the *Second Mean-Value Theorem for Integrals (Bonnet's Theorem)* proven in [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|Chapter 2]], which allows a monotonic factor to be factored out of an integral at an intermediate point: 
$$
\begin{gather}
\textbf{Theorem: Dirichlet's Test for Improper Integrals} \\[5mm]
\text{Let } f, g: [a, \infty) \to \mathbb{R} \text{ be functions such that } f \in \mathcal{R}[a, B] \text{ and } g \in C^1[a, B] \text{ for all } B \ge a. \\[2mm]
\text{Suppose the following two conditions are satisfied:} \\[2mm]
\text{1. The primitive of } f \text{ is uniformly bounded on } [a, \infty): \\[3.5mm]
\exists M > 0 \quad \text{such that} \quad \forall B \ge a, \quad \left| \int_a^B f(x)\,dx \right| \le M. \\[2mm]
\text{2. The function } g \text{ is monotonic on } [a, \infty) \text{ and decays to zero at infinity:} \\[3.5mm]
\lim_{x \to \infty} g(x) = 0. \\[3.5mm]
\text{Then the improper integral } \int_a^\infty f(x)g(x)\,dx \text{ converges.}
\end{gather}
$$
(see [[Proof of Dirichlet's Test for Improper Integrals]])

$$
\begin{gather}
\textbf{Theorem: Abel's Test for Improper Integrals} \\[5mm]
\text{Let } f, g: [a, \infty) \to \mathbb{R} \text{ be functions such that } f \in \mathcal{R}[a, B] \text{ and } g \in C^1[a, B] \text{ for all } B \ge a. \\[2mm]
\text{Suppose the following two conditions are satisfied:} \\[2mm]
\text{1. The improper integral } \int_a^\infty f(x)\,dx \text{ converges.} \\[2mm]
\text{2. The function } g \text{ is monotonic and uniformly bounded on } [a, \infty): \\[3.5mm]
\exists K > 0 \quad \text{such that} \quad \forall x \ge a, \quad |g(x)| \le K. \\[3.5mm]
\text{Then the improper integral } \int_a^\infty f(x)g(x)\,dx \text{ converges.}
\end{gather}
$$
(see [[Proof of Abel's Test for Improper Integrals]])

> [!danger]+ Intuition: Oscillatory Damping and Phase Cancellation
> Dirichlet's test captures the mathematics of phase cancellation. Consider a physical system driven by an alternating signal $f(x) = \sin x$. The integral of $\sin x$ over $[0, B]$ oscillates harmonically between $0$ and $2$; it never settles, but it never escapes the bound $M = 2$.
> 
> When this signal is multiplied by a damping factor $g(x) = 1/x$ that monotonically decreases to zero, each successive positive lobe of the product is slightly smaller in area than the preceding negative lobe, and slightly larger than the following positive lobe. The accumulated area behaves like an alternating numerical series $\sum (-1)^k a_k$ with $a_k \searrow 0$. By Leibniz's alternating logic, the total area is trapped between successively tightening bounds and converges to a finite value. 
> 
> Abel's test, by contrast, takes an integral that already converges on its own merit, and multiplies it by a smooth, bounded, monotone amplifier $g(x)$ (such as $g(x) = \arctan x$ or $g(x) = 1 - e^{-x}$). Because $g(x)$ approaches a finite steady state without oscillating, it cannot disturb the delicate convergence already achieved by $f(x)$.

### The Canonical Oscillatory Benchmarks: The Dirichlet Sinc and Fresnel Integrals
The archetypal specimen of conditional convergence in analysis is the *Dirichlet Sinc Integral*: 
$$
\begin{gather}
\textbf{Theorem: Conditional Convergence of the Dirichlet Sinc Integral} \\[5mm]
\text{The improper integral of the sinc function} \\[3.5mm]
\int_0^\infty \frac{\sin x}{x}\,dx \\[3.5mm]
\text{converges conditionally, and its exact value is:} \\[3.5mm]
\int_0^\infty \frac{\sin x}{x}\,dx = \frac{\pi}{2}. \\[3.5mm]
\text{However, the improper integral of its absolute value diverges to infinity:} \\[3.5mm]
\int_0^\infty \left| \frac{\sin x}{x} \right|\,dx = +\infty.
\end{gather}
$$
(see [[Proof of Conditional Convergence of the Dirichlet Sinc Integral]])

##### Structural Analysis of the Sinc Integral
The improper sinc integral under evaluation is denoted by:
$$
\begin{gather}
I := \int_0^\infty \frac{\sin x}{x}\,dx \tag{31}
\end{gather}
$$
The reader will notice that the integrand in step 31 features a potential singularity at $x = 0$. However, by virtue of the classical limit $\lim_{x \to 0} \frac{\sin x}{x} = 1$, the singularity is removable. Defining $f(0) := 1$ renders $f$ continuous on $[0, 1]$, making $\int_0^1 \frac{\sin x}{x}\,dx$ an ordinary proper Riemann integral. 

The entire improper challenge resides in the tail domain $[1, \infty)$. Over $[1, \infty)$, setting $f(x) = \sin x$ and $g(x) = \frac{1}{x}$, the primitive $F(B) = \int_1^B \sin x\,dx = \cos 1 - \cos B$ is bounded by $|\cos 1 - \cos B| \le 2$, while $g(x) = 1/x$ is strictly decreasing with $\lim_{x \to \infty} 1/x = 0$. Dirichlet's test immediately guarantees that $\int_1^\infty \frac{\sin x}{x}\,dx$ converges.

Conversely, the divergence of $\int_1^\infty \frac{|\sin x|}{x}\,dx$ is revealed by partitioning the positive ray into half-periods $[(k - 1)\pi, k\pi]$ for $k \ge 1$:
$$
\begin{gather}
\int_0^{n\pi} \frac{|\sin x|}{x}\,dx = \sum_{k=1}^n \int_{(k - 1)\pi}^{k\pi} \frac{|\sin x|}{x}\,dx \tag{32}
\end{gather}
$$
On the interval $[(k - 1)\pi, k\pi]$, the denominator satisfies $x \le k\pi$. Therefore:
$$
\begin{gather}
\int_{(k - 1)\pi}^{k\pi} \frac{|\sin x|}{x}\,dx \ge \frac{1}{k\pi} \int_{(k - 1)\pi}^{k\pi} |\sin x|\,dx = \frac{1}{k\pi} \int_0^\pi \sin t\,dt = \frac{2}{\pi k} \tag{33}
\end{gather}
$$
Summing step 33 across $k = 1, 2, \dots, n$ yields:
$$
\begin{gather}
\int_0^{n\pi} \frac{|\sin x|}{x}\,dx \ge \frac{2}{\pi} \sum_{k=1}^n \frac{1}{k} \tag{34}
\end{gather}
$$
As $n \to \infty$, the harmonic series on the right diverges to $+\infty$, proving that the absolute integral diverges to infinity.

##### The Fresnel Integrals of Wave Optics
Another celebrated family of conditionally convergent improper integrals originates in the diffraction theory of Augustin-Jean Fresnel:
$$
\begin{gather}
J_1 := \int_0^\infty \sin(x^2)\,dx, \qquad J_2 := \int_0^\infty \cos(x^2)\,dx \tag{35}
\end{gather}
$$
These integrals present a startling analytical phenomenon: the integrands $\sin(x^2)$ and $\cos(x^2)$ do *not* tend to zero as $x \to \infty$! They oscillate with ever-increasing frequency between $-1$ and $+1$. 

To demonstrate the convergence of $J_1$, one splits the domain at $x = 1$ and applies the change of variable $u = x^2$ ($x = \sqrt{u}, dx = \frac{du}{2\sqrt{u}}$):
$$
\begin{gather}
\int_1^\infty \sin(x^2)\,dx = \frac{1}{2} \int_1^\infty \frac{\sin u}{\sqrt{u}}\,du \tag{36}
\end{gather}
$$
On $[1, \infty)$, the integral in step 36 satisfies Dirichlet's test with $f(u) = \sin u$ (bounded primitive) and $g(u) = u^{-1/2}$ (monotonically decaying to zero). Thus, the Fresnel integrals converge conditionally, evaluating in complex analysis to $\frac{1}{2}\sqrt{\frac{\pi}{2}}$.

---
# Multiple Singularities and Compound Domains
In advanced applications, an improper integral often possesses compound singularities: the domain may be unbounded while the integrand simultaneously blows up at one or more finite points.
### The Canonical Compound Power Integral
A canonical archetype studied extensively in Zorich §6.5 is the two-parameter compound rational integral:
$$
\begin{gather}
K(p, q) := \int_0^\infty \frac{dx}{x^p + x^q} \qquad (0 < p < q) \tag{37}
\end{gather}
$$
This integral contains two distinct singularities: a singular point at the origin $x \to 0^+$, and an unbounded tail at $x \to \infty$. To evaluate its convergence, one partitions the domain at an arbitrary non-singular point, conventionally $x = 1$:
$$
\begin{gather}
K(p, q) = \int_0^1 \frac{dx}{x^p + x^q} + \int_1^\infty \frac{dx}{x^p + x^q} =: I_1 + I_2 \tag{38}
\end{gather}
$$

##### Convergence of the Origin Component $I_1$
On the interval $(0, 1]$, as $x \to 0^+$, the lower-order power dominates because $0 < p < q$:
$$
\begin{gather}
x^p + x^q = x^p \big( 1 + x^{q - p} \big) \sim x^p \tag{39}
\end{gather}
$$
Formally, computing the limit ratio against $g_1(x) = x^{-p}$:
$$
\begin{gather}
\lim_{x \to 0^+} \frac{\frac{1}{x^p + x^q}}{\frac{1}{x^p}} = \lim_{x \to 0^+} \frac{1}{1 + x^{q - p}} = 1 \in (0, \infty) \tag{40}
\end{gather}
$$
By the Limit Comparison Test, $I_1$ converges if and only if $\int_0^1 \frac{dx}{x^p}$ converges. Referring to the canonical $p$-integrals, this occurs if and only if:
$$
\begin{gather}
p < 1 \tag{41}
\end{gather}
$$

##### Convergence of the Tail Component $I_2$
On the interval $[1, \infty)$, as $x \to \infty$, the higher-order power dominates:
$$
\begin{gather}
x^p + x^q = x^q \big( 1 + x^{p - q} \big) \sim x^q \tag{42}
\end{gather}
$$
Computing the limit ratio against $g_2(x) = x^{-q}$:
$$
\begin{gather}
\lim_{x \to \infty} \frac{\frac{1}{x^p + x^q}}{\frac{1}{x^q}} = \lim_{x \to \infty} \frac{1}{x^{p - q} + 1} = 1 \in (0, \infty) \tag{43}
\end{gather}
$$
By the Limit Comparison Test, $I_2$ converges if and only if $\int_1^\infty \frac{dx}{x^q}$ converges, which requires:
$$
\begin{gather}
q > 1 \tag{44}
\end{gather}
$$
##### The Combined Existence Criterion
Combining step 41 and step 44 establishes that the compound integral $K(p, q)$ converges if and only if the exponents strictly bracket unity:
$$
\begin{gather}
p < 1 < q \tag{45}
\end{gather}
$$
If $p \ge 1$, the integral diverges at the origin; if $q \le 1$, it diverges at infinity.

---
# Pathological Gallery: Classical Counterexamples to the Converse

### Counterexample 1: The Asymmetry of the Cauchy Principal Value
**False Proposition:** If $\lim_{R \to \infty} \int_{-R}^R f(x)\,dx$ exists and is finite, then the improper integral $\int_{-\infty}^\infty f(x)\,dx$ converges.

##### Rigorous Counterexample
Let $f(x) = \frac{x}{1 + x^2}$ on $(-\infty, \infty)$.
Because $f$ is an odd function ($f(-x) = -f(x)$), for any symmetric finite truncation $[-R, R]$, the integral vanishes identically:
$$
\begin{gather}
\int_{-R}^R \frac{x}{1 + x^2}\,dx = 0 \implies \operatorname{p.v.} \int_{-\infty}^\infty \frac{x}{1 + x^2}\,dx = \lim_{R \to \infty} 0 = 0 \tag{46}
\end{gather}
$$
Now consider the improper integral under independent exhaustion boundaries $A \to -\infty$ and $B \to \infty$:
$$
\begin{gather}
\int_0^B \frac{x}{1 + x^2}\,dx = \left[ \frac{1}{2} \ln(1 + x^2) \right]_0^B = \frac{1}{2} \ln(1 + B^2) \tag{47}
\end{gather}
$$
As $B \to \infty$, step 47 diverges strictly to $+\infty$. Symmetrically, as $A \to -\infty$, $\int_A^0 f(x)\,dx \to -\infty$. Because neither constituent integral converges, the improper integral $\int_{-\infty}^\infty \frac{x}{1 + x^2}\,dx$ is thoroughly divergent. The existence of the principal value in step 46 was an artifact of rigid symmetric cancellation.

### Counterexample 2: The Spike Phenomenon — Convergence Without Vanishing Tails
**False Proposition:** If the improper integral of the first kind $\int_a^\infty f(x)\,dx$ converges, then the integrand must decay to zero at infinity, that is, $\lim_{x \to \infty} f(x) = 0$.

##### Rigorous Counterexample
In the theory of numerical series, convergence of $\sum a_n$ strictly implies that the terms vanish: $\lim a_n = 0$. In improper integration, this converse is completely false. A continuous function can enclose a finite total area while repeatedly shooting up to immense heights, provided the peaks become sufficiently narrow.

Construct a non-negative continuous function $f: [0, \infty) \to \mathbb{R}$ consisting of triangular spikes erected at every integer $n \ge 2$. For each $n \ge 2$, define a symmetric triangular spike centered at $x = n$ of height $h_n = n$ and base width $2\delta_n = \frac{2}{n^3}$:
$$
\begin{gather}
f_n(x) := \begin{cases}
n - n^4 |x - n| & \text{if } |x - n| \le \frac{1}{n^3} \\[2mm]
0 & \text{otherwise}
\end{cases} \tag{48}
\end{gather}
$$
Outside these disjoint triangular intervals $[n - n^{-3}, n + n^{-3}]$, define $f(x) \equiv 0$. The geometric area of the $n$-th triangular spike is exactly its base multiplied by half its height:
$$
\begin{gather}
A_n = \int_{n - n^{-3}}^{n + n^{-3}} f_n(x)\,dx = \frac{1}{2} \times \left( \frac{2}{n^3} \right) \times n = \frac{1}{n^2} \tag{49}
\end{gather}
$$
For any parameter $B \ge 2$, letting $N = \lfloor B \rfloor$, the accumulation function satisfies:
$$
\begin{gather}
F(B) = \int_0^B f(x)\,dx \le \sum_{n=2}^{N + 1} A_n = \sum_{n=2}^{N + 1} \frac{1}{n^2} \tag{50}
\end{gather}
$$
Because the series $\sum_{n=2}^\infty \frac{1}{n^2}$ converges (with sum $\frac{\pi^2}{6} - 1$), the accumulation function $F(B)$ is bounded above on $[0, \infty)$ by $\frac{\pi^2}{6} - 1$. By the Monotonicity Criterion, the improper integral converges:
$$
\begin{gather}
\int_0^\infty f(x)\,dx = \sum_{n=2}^\infty \frac{1}{n^2} < \infty \tag{51}
\end{gather}
$$
However, at the sequence of integer coordinates $x = n$, the integrand satisfies $f(n) = n \to \infty$. Consequently:
$$
\begin{gather}
\limsup_{x \to \infty} f(x) = +\infty \tag{52}
\end{gather}
$$
The limit $\lim_{x \to \infty} f(x)$ does not exist, demonstrating that an integrand does not even need to remain bounded, let alone vanish, for its improper integral to converge.

### Counterexample 3: Failure of Product Convergence for Conditionally Convergent Integrals
**False Proposition:** If $\int_a^\infty f(x)\,dx$ and $\int_a^\infty g(x)\,dx$ both converge, then their pointwise product integral $\int_a^\infty f(x)g(x)\,dx$ converges.

##### Rigorous Counterexample
While the product of two absolutely convergent improper integrals often converges, conditional convergence is fragile. 
Let $f(x) = g(x) = \frac{\sin x}{\sqrt{x}}$ on $[\pi, \infty)$.
By Dirichlet's test, setting the oscillatory factor as $\sin x$ and the monotonic factor as $x^{-1/2} \searrow 0$, the improper integral converges:
$$
\begin{gather}
\int_\pi^\infty \frac{\sin x}{\sqrt{x}}\,dx \quad \text{converges} \tag{53}
\end{gather}
$$
Now form the product $f(x)g(x)$:
$$
\begin{gather}
f(x)g(x) = \left( \frac{\sin x}{\sqrt{x}} \right)^2 = \frac{\sin^2 x}{x} \tag{54}
\end{gather}
$$
Applying the trigonometric half-angle identity $\sin^2 x = \frac{1 - \cos(2x)}{2}$ gives:
$$
\begin{gather}
\int_\pi^B \frac{\sin^2 x}{x}\,dx = \frac{1}{2} \int_\pi^B \frac{dx}{x} - \frac{1}{2} \int_\pi^B \frac{\cos(2x)}{x}\,dx \tag{55}
\end{gather}
$$
In step 55, the second integral $\int_\pi^\infty \frac{\cos(2x)}{x}\,dx$ converges by Dirichlet's test (since $\int_\pi^B \cos(2x)\,dx = \frac{\sin(2B)}{2}$ is bounded by $1/2$ and $1/x \searrow 0$). 
However, the first integral is the divergent harmonic integral:
$$
\begin{gather}
\lim_{B \to \infty} \frac{1}{2} \int_\pi^B \frac{dx}{x} = \lim_{B \to \infty} \frac{1}{2} \big( \ln B - \ln \pi \big) = +\infty \tag{56}
\end{gather}
$$
The algebraic difference of a divergent integral and a convergent integral diverges strictly to $+\infty$. Thus:
$$
\begin{gather}
\int_\pi^\infty \left( \frac{\sin x}{\sqrt{x}} \right)^2 dx = +\infty \tag{57}
\end{gather}
$$
The product of two convergent improper integrals diverges completely.

### Counterexample 4: Non-Monotone Decay and the Breakdown of Dirichlet's Test
**False Proposition:** If $f(x)$ has a bounded primitive on $[a, \infty)$ and $g(x)$ is continuous with $\lim_{x \to \infty} g(x) = 0$, then $\int_a^\infty f(x)g(x)\,dx$ converges. (That is, the monotonicity hypothesis in Dirichlet's test can be dropped).

##### Rigorous Counterexample
The monotonicity of $g(x)$ is vital; decay to zero alone is insufficient if $g(x)$ oscillates in resonance with $f(x)$.
Set $f(x) = \sin x$. The primitive $F(B) = \int_0^B \sin x\,dx = 1 - \cos B$ is bounded by $M = 2$.
Now define the non-monotonic decaying modulator:
$$
\begin{gather}
g(x) := \frac{\sin x}{x} \qquad (x \ge \pi) \tag{58}
\end{gather}
$$
Because $|\sin x| \le 1$ for all $x \ge \pi$, the modulator satisfies $|g(x)| \le \frac{1}{x} \to 0$ as $x \to \infty$. However, $g(x)$ is not monotonic; it oscillates across the axis.
The resulting integrand is:
$$
\begin{gather}
f(x)g(x) = \sin x \cdot \frac{\sin x}{x} = \frac{\sin^2 x}{x} \tag{59}
\end{gather}
$$
As established in step 57 of Counterexample 3, $\int_\pi^\infty \frac{\sin^2 x}{x}\,dx$ diverges to $+\infty$. Abandoning the monotonicity hypothesis causes Dirichlet's test to fail completely.

---
# Applications of Improper Integrals

### Physics: Gravitational and Electrostatic Potentials of Infinite Media
In classical field theory, computing the potential energy generated by continuous mass or charge distributions requires evaluating improper integrals with singular integrands and infinite spatial domains.

##### 1. Problem Formulation
1. In nuclear physics and plasma shielding, the electrostatic potential between charged particles is modeled by the *Yukawa potential*:
$$ V(r) = \frac{q^2}{4\pi \varepsilon_0} \frac{e^{-\mu r}}{r} \qquad (r > 0) $$
where $\mu \ge 0$ is the screening mass parameter. Compute the total integrated electrostatic energy stored across the entire three-dimensional space outside a hard-sphere core of radius $r_0 > 0$:
$$ U_{\text{field}} = \int_{r_0}^\infty 4\pi r^2 \big( V(r) \big)^2\,dr $$
Demonstrate how the screening parameter $\mu > 0$ guarantees convergence, and analyze the unscreened Coulomb limit $\mu \to 0^+$.
2. Consider a test particle of mass $m$ projected vertically outward from the boundary of an infinite cosmic gas cloud whose gravitational field produces an inward acceleration given by:
$$ g(z) = \frac{g_0}{(1 + z / z_0)^p} \qquad (z \ge 0) $$
where $g_0 > 0$, $z_0 > 0$, and $p > 0$. Using the Work-Energy Theorem, determine the critical exponent $p$ such that the particle requires a *finite escape velocity* to completely escape to $z = \infty$, and calculate the escape velocity $v_{\text{esc}}$.

##### 2. Mathematical Deduction and Solution
**Phase 1: Field Energy of the Yukawa Potential:**
Substituting the Yukawa potential into the spatial energy integral:
$$ U_{\text{field}} = 4\pi \left( \frac{q^2}{4\pi \varepsilon_0} \right)^2 \int_{r_0}^\infty r^2 \left( \frac{e^{-2\mu r}}{r^2} \right) dr = \frac{q^4}{4\pi \varepsilon_0^2} \int_{r_0}^\infty e^{-2\mu r}\,dr \tag{72} $$
The integrand in step 72 is $f(r) = e^{-2\mu r}$. For $\mu > 0$, this is an improper integral of the first kind. Evaluating the limit of the proper Riemann integral:
$$ \int_{r_0}^\infty e^{-2\mu r}\,dr = \lim_{B \to \infty} \left[ -\frac{e^{-2\mu r}}{2\mu} \right]_{r_0}^B = \lim_{B \to \infty} \left( \frac{e^{-2\mu r_0}}{2\mu} - \frac{e^{-2\mu B}}{2\mu} \right) \tag{73} $$
Since $\mu > 0$, $\lim_{B \to \infty} e^{-2\mu B} = 0$. The improper integral converges unconditionally to:
$$ \int_{r_0}^\infty e^{-2\mu r}\,dr = \frac{e^{-2\mu r_0}}{2\mu} \tag{74} $$
Substituting step 74 into step 72 yields the exact field energy:
$$ U_{\text{field}} = \frac{q^4}{8\pi \varepsilon_0^2 \mu} e^{-2\mu r_0} \tag{75} $$
In the unscreened Coulomb limit ($\mu \to 0^+$):
$$ \lim_{\mu \to 0^+} U_{\text{field}} = \lim_{\mu \to 0^+} \frac{q^4 e^{-2\mu r_0}}{8\pi \varepsilon_0^2 \mu} = +\infty \tag{76} $$
When $\mu = 0$, the integral in step 72 becomes $\int_{r_0}^\infty 1\,dr = \lim_{B \to \infty} (B - r_0) = \infty$. This proves that a purely Coulombic field possesses an infinite total electrostatic energy across unbounded space unless screened by an exponentially decaying factor.

**Phase 2: Gravitational Escape Velocity:**
By the Work-Energy Theorem, the mechanical work performed against the gravitational field during an escape to infinity is:
$$ W_{\text{escape}} = \int_0^\infty m g(z)\,dz = m g_0 \int_0^\infty \left( 1 + \frac{z}{z_0} \right)^{-p} dz \tag{77} $$
Setting $u = 1 + z/z_0$, where $dz = z_0 du$, step 77 transforms into:
$$ W_{\text{escape}} = m g_0 z_0 \int_1^\infty u^{-p}\,du \tag{78} $$
By the canonical $p$-integral theorem, $\int_1^\infty u^{-p}\,du$ converges if and only if:
$$ p > 1 \tag{79} $$
If $p \le 1$, the work required to escape to infinity is infinite ($W_{\text{escape}} = \infty$), which implies that no finite initial kinetic energy $E_k = \frac{1}{2}m v_0^2$ can achieve escape: the particle is permanently gravitationally bound.

When $p > 1$, evaluating the improper integral yields:
$$ W_{\text{escape}} = m g_0 z_0 \left[ \frac{u^{1 - p}}{1 - p} \right]_1^\infty = \frac{m g_0 z_0}{p - 1} \tag{80} $$
Equating initial kinetic energy to escape work:
$$ \frac{1}{2} m v_{\text{esc}}^2 = W_{\text{escape}} = \frac{m g_0 z_0}{p - 1} \tag{81} $$
Solving for $v_{\text{esc}}$ establishes the exact escape velocity:
$$ v_{\text{esc}} = \sqrt{\frac{2 g_0 z_0}{p - 1}} \tag{82} $$
In standard Newtonian gravity, the field outside a spherical planet decays as $g(z) \propto (R + z)^{-2}$, corresponding to $p = 2$. For $p = 2$, step 82 recovers the classical escape velocity $v_{\text{esc}} = \sqrt{2 g_0 z_0}$.

### Chemistry: The Maxwell-Boltzmann Energy Continuum and Reaction Activation Kinetics
In physical chemistry and statistical mechanics, reaction rates are governed by collisions between molecules possessing kinetic energies exceeding a critical threshold. The distribution of molecular energies across the continuum $[0, \infty)$ is modeled by an improper gamma-type integral.
##### 1. Problem Formulation
In a gas at absolute temperature $T$, the Maxwell-Boltzmann distribution states that the probability density of a molecule possessing kinetic energy $E \ge 0$ is:
$$ f(E) = \frac{2}{\sqrt{\pi}} (k_B T)^{-3/2} E^{1/2} e^{-E / (k_B T)} \qquad (E \ge 0) $$
where $k_B$ is the Boltzmann constant.

According to collision theory, a chemical reaction occurs only when colliding molecules possess kinetic energy exceeding the activation energy threshold $E_a > 0$. The reactive fraction of collisions is therefore given by the improper integral of the high-energy tail:
$$ P(E \ge E_a) = \int_{E_a}^\infty f(E)\,dx = \frac{2}{\sqrt{\pi}} (k_B T)^{-3/2} \int_{E_a}^\infty E^{1/2} e^{-E / (k_B T)}\,dE $$

1. Prove that the total probability integral $\int_0^\infty f(E)\,dE = 1$ converges, thereby confirming that $f(E)$ is a valid normalized probability density.
2. Evaluate the improper integral $P(E \ge E_a)$ rigorously via integration by parts, and demonstrate how the leading asymptotic term recovers the classical *Arrhenius activation factor* $e^{-E_a / (k_B T)}$ when $E_a \gg k_B T$.

##### 2. Mathematical Deduction and Solution
**Phase 1: Normalization of the Maxwell-Boltzmann Distribution:**
To evaluate $\int_0^\infty f(E)\,dE$, introduce the dimensionless substitution $u = \sqrt{E / (k_B T)}$. Then $E = k_B T u^2$ and $dE = 2 k_B T u\,du$. 
The integration boundaries remain $E = 0 \implies u = 0$ and $E \to \infty \implies u \to \infty$. Substituting these into the integral:
$$ \int_0^\infty f(E)\,dE = \frac{2}{\sqrt{\pi}} (k_B T)^{-3/2} \int_0^\infty (k_B T u^2)^{1/2} e^{-u^2} (2 k_B T u\,du) = \frac{4}{\sqrt{\pi}} \int_0^\infty u^2 e^{-u^2}\,du \tag{83} $$
To evaluate $\int_0^\infty u^2 e^{-u^2}\,du$, apply integration by parts for improper integrals: set $w(u) = u$ and $v'(u) = u e^{-u^2}$, which gives $w'(u) = 1$ and $v(u) = -\frac{1}{2}e^{-u^2}$.
$$ \int_0^\infty u^2 e^{-u^2}\,du = \lim_{B \to \infty} \left[ -\frac{u}{2} e^{-u^2} \right]_0^B + \frac{1}{2} \int_0^\infty e^{-u^2}\,du \tag{84} $$
By L'Hôpital's rule, $\lim_{B \to \infty} \frac{B}{e^{B^2}} = 0$, so the boundary term vanishes. The remaining integral is the canonical Gaussian integral $\int_0^\infty e^{-u^2}\,du = \frac{\sqrt{\pi}}{2}$. Substituting this into step 84 yields:
$$ \int_0^\infty u^2 e^{-u^2}\,du = 0 + \frac{1}{2} \left( \frac{\sqrt{\pi}}{2} \right) = \frac{\sqrt{\pi}}{4} \tag{85} $$
Multiplying step 85 by $\frac{4}{\sqrt{\pi}}$ confirms normalization:
$$ \int_0^\infty f(E)\,dE = \frac{4}{\sqrt{\pi}} \left( \frac{\sqrt{\pi}}{4} \right) = 1 \tag{86} $$

**Phase 2: High-Energy Reactive Tail and the Arrhenius Term:**
Now consider the tail integral over $[E_a, \infty)$. Perform the substitution $x = E / (k_B T)$, with $dx = dE / (k_B T)$:
$$ P(E \ge E_a) = \frac{2}{\sqrt{\pi}} \int_{x_a}^\infty x^{1/2} e^{-x}\,dx \tag{87} $$
where $x_a := \frac{E_a}{k_B T} > 0$. Apply integration by parts to step 87: set $u(x) = x^{1/2}$ and $v'(x) = e^{-x}$, so $u'(x) = \frac{1}{2}x^{-1/2}$ and $v(x) = -e^{-x}$.
$$ \int_{x_a}^\infty x^{1/2} e^{-x}\,dx = \lim_{B \to \infty} \big[ -x^{1/2}e^{-x} \big]_{x_a}^B + \frac{1}{2} \int_{x_a}^\infty x^{-1/2} e^{-x}\,dx \tag{88} $$
Because $\lim_{B \to \infty} B^{1/2}e^{-B} = 0$, the boundary evaluation yields:
$$ \int_{x_a}^\infty x^{1/2} e^{-x}\,dx = x_a^{1/2} e^{-x_a} + \frac{1}{2} \int_{x_a}^\infty x^{-1/2} e^{-x}\,dx \tag{89} $$
Substituting step 89 into step 87:
$$ P(E \ge E_a) = \frac{2}{\sqrt{\pi}} x_a^{1/2} e^{-x_a} + \frac{1}{\sqrt{\pi}} \int_{x_a}^\infty x^{-1/2} e^{-x}\,dx \tag{90} $$
For high activation energies ($E_a \gg k_B T \implies x_a \gg 1$), one bounds the remaining integral:
$$ \int_{x_a}^\infty x^{-1/2} e^{-x}\,dx \le x_a^{-1/2} \int_{x_a}^\infty e^{-x}\,dx = x_a^{-1/2} e^{-x_a} \tag{91} $$
Comparing this with the leading term, the remainder is $O(x_a^{-1/2}e^{-x_a})$, which is suppressed by a factor of $1/x_a$ relative to the principal term $x_a^{1/2}e^{-x_a}$.
Factoring out the leading terms:
$$ P(E \ge E_a) = \frac{2}{\sqrt{\pi}} \sqrt{\frac{E_a}{k_B T}} e^{-E_a / (k_B T)} \left[ 1 + O\left( \frac{k_B T}{E_a} \right) \right] \tag{92} $$
Step 92 provides the rigorous derivation of the exponential Arrhenius factor $e^{-E_a / (k_B T)}$, revealing the pre-exponential temperature dependence $\sqrt{E_a / k_B T}$ as the consequence of improper integration of the continuous Maxwell-Boltzmann energy distribution.

### Biology: Pharmacokinetic Clearance, Area Under the Curve (AUC), and Deep-Tissue Trapping
In pharmacology and physiology, the total systemic exposure of an organism to a pharmaceutical compound is quantified by the Area Under the Plasma Concentration Curve ($\text{AUC}_{0, \infty}$). The mathematical structure of clearance determines whether the body successfully eliminates the drug or suffers toxic accumulation.

##### 1. Problem Formulation
Following intravenous administration of a drug at $t = 0$, the vascular plasma concentration $C(t)$ is monitored across the patient's lifetime $[0, \infty)$. Two pharmacokinetic clearance models are considered:
1. **Standard Two-Compartment Model:** Clearance occurs via two parallel first-order elimination pathways (vascular metabolism and renal excretion):
$$ C_1(t) = A e^{-\alpha t} + B e^{-\beta t} \qquad (t \ge 0) $$
where $A, B > 0$ and $\alpha > \beta > 0$.
2. **Deep-Tissue Trapping Model:** The drug binds reversibly to bone marrow or adipose tissue, leading to an asymptotically slow, heavy-tailed power-law elimination profile:
$$ C_2(t) = \frac{C_0}{(1 + t / t_0)^p} \qquad (t \ge 0) $$
where $C_0 > 0$, $t_0 > 0$, and $p > 0$.

For both models:
1. Compute the *total systemic exposure* $\text{AUC}_{0, \infty} := \int_0^\infty C(t)\,dt$, determining parameter convergence conditions.
2. Compute the *Mean Residence Time* (MRT), defined as the normalized first temporal moment of the concentration curve:
$$ \text{MRT} := \frac{\int_0^\infty t C(t)\,dt}{\int_0^\infty C(t)\,dt} $$
determining the exact analytical conditions under which the drug possesses a finite mean residence time.

##### 2. Mathematical Deduction and Solution
**Phase 1: Two-Compartment Model Analysis:**
For the exponential model $C_1(t)$, the total exposure is the sum of two improper integrals of the first kind:
$$ \text{AUC}_1 = \int_0^\infty \big( A e^{-\alpha t} + B e^{-\beta t} \big)\,dt = A \int_0^\infty e^{-\alpha t}\,dt + B \int_0^\infty e^{-\beta t}\,dt \tag{93} $$
Since $\alpha > 0$ and $\beta > 0$, each integral converges unconditionally:
$$ \int_0^\infty e^{-\alpha t}\,dt = \left[ -\frac{e^{-\alpha t}}{\alpha} \right]_0^\infty = \frac{1}{\alpha}, \qquad \int_0^\infty e^{-\beta t}\,dt = \frac{1}{\beta} \tag{94} $$
Substituting step 94 into step 93:
$$ \text{AUC}_1 = \frac{A}{\alpha} + \frac{B}{\beta} \tag{95} $$
Now compute the first moment integral $\int_0^\infty t C_1(t)\,dt$:
$$ \int_0^\infty t C_1(t)\,dt = A \int_0^\infty t e^{-\alpha t}\,dt + B \int_0^\infty t e^{-\beta t}\,dt \tag{96} $$
Integrating by parts for improper integrals: set $u = t$ and $v' = e^{-\alpha t}$, giving $u' = 1$ and $v = -\alpha^{-1}e^{-\alpha t}$.
$$ \int_0^\infty t e^{-\alpha t}\,dt = \lim_{T \to \infty} \left[ -\frac{t}{\alpha} e^{-\alpha t} \right]_0^T + \frac{1}{\alpha} \int_0^\infty e^{-\alpha t}\,dt = 0 + \frac{1}{\alpha^2} = \frac{1}{\alpha^2} \tag{97} $$
Applying this result to both terms in step 96 yields:
$$ \int_0^\infty t C_1(t)\,dt = \frac{A}{\alpha^2} + \frac{B}{\beta^2} \tag{98} $$
Substituting step 95 and step 98 into the MRT definition:
$$ \text{MRT}_1 = \frac{\frac{A}{\alpha^2} + \frac{B}{\beta^2}}{\frac{A}{\alpha} + \frac{B}{\beta}} = \frac{A \beta^2 + B \alpha^2}{\alpha \beta (A \beta + B \alpha)} \tag{99} $$
Because $\alpha, \beta > 0$, the mean residence time $\text{MRT}_1$ is finite.

**Phase 2: Power-Law Deep-Tissue Trapping Model Analysis:**
For the power-law profile $C_2(t)$, the total exposure integral is:
$$ \text{AUC}_2 = \int_0^\infty \frac{C_0}{(1 + t / t_0)^p}\,dt \tag{100} $$
Using the substitution $u = 1 + t / t_0$, where $dt = t_0 du$, step 100 transforms into:
$$ \text{AUC}_2 = C_0 t_0 \int_1^\infty u^{-p}\,du \tag{101} $$
By the canonical $p$-integral benchmarks, step 101 converges if and only if:
$$ p > 1 \tag{102} $$
If $p \le 1$, $\text{AUC}_2 = \infty$, indicating chronic toxic drug accumulation.
When $p > 1$, evaluating the integral:
$$ \text{AUC}_2 = C_0 t_0 \left[ \frac{u^{1 - p}}{1 - p} \right]_1^\infty = \frac{C_0 t_0}{p - 1} \tag{103} $$
Next, evaluate the first moment integral for the mean residence time:
$$ \int_0^\infty t C_2(t)\,dt = C_0 \int_0^\infty t \left( 1 + \frac{t}{t_0} \right)^{-p} dt \tag{104} $$
Applying the same substitution $u = 1 + t/t_0 \implies t = t_0 (u - 1)$:
$$ \int_0^\infty t C_2(t)\,dt = C_0 t_0^2 \int_1^\infty (u - 1) u^{-p}\,du = C_0 t_0^2 \left[ \int_1^\infty u^{1 - p}\,du - \int_1^\infty u^{-p}\,du \right] \tag{105} $$
In step 105, the leading term is $\int_1^\infty u^{-(p - 1)}\,du$. By the canonical benchmarks, this integral converges if and only if:
$$ p - 1 > 1 \iff p > 2 \tag{106} $$
If $1 < p \le 2$, a striking physiological anomaly emerges: the total systemic exposure $\text{AUC}_2$ is finite, but the Mean Residence Time is *infinite* ($\text{MRT}_2 = \infty$). The patient successfully clears the bulk of the dose, but trace molecules linger in deep tissues indefinitely.

When $p > 2$, both improper integrals in step 105 converge:
$$ \int_1^\infty u^{1 - p}\,du = \frac{1}{p - 2}, \qquad \int_1^\infty u^{-p}\,du = \frac{1}{p - 1} \tag{107} $$
Substituting step 107 into step 105:
$$ \int_0^\infty t C_2(t)\,dt = C_0 t_0^2 \left( \frac{1}{p - 2} - \frac{1}{p - 1} \right) = \frac{C_0 t_0^2}{(p - 1)(p - 2)} \tag{108} $$
Dividing step 108 by the exposure from step 103 yields the exact Mean Residence Time:
$$ \text{MRT}_2 = \frac{\frac{C_0 t_0^2}{(p - 1)(p - 2)}}{\frac{C_0 t_0}{p - 1}} = \frac{t_0}{p - 2} \tag{109} $$
This demonstrates how improper integration analysis establishes clinical safety margins: a therapeutic drug must be engineered to possess an elimination exponent $p > 2$ to guarantee both finite total exposure and finite mean residence time.

### Engineering: Laplace Transform Domain Stability and Resonant Filter Impulse Responses
In electrical and control engineering, analyzing linear time-invariant (LTI) continuous filters requires improper integration to establish system stability and evaluate frequency responses.

##### 1. Problem Formulation
An electrical RLC bandpass filter or underdamped mechanical suspension subject to an impulsive Dirac input $\delta(t)$ generates a causal impulse response:
$$ h(t) = A e^{-\sigma t} \sin(\omega_0 t) \qquad (t \ge 0) $$
where $A > 0$ is the amplification factor, $\sigma \in \mathbb{R}$ is the damping factor, and $\omega_0 > 0$ is the natural resonant frequency.

1. Compute the unilateral *Laplace Transform* of the impulse response, defined as the improper parametric integral of the first kind:
$$ H(s) := \mathcal{L}\{h(t)\}(s) = \int_0^\infty h(t) e^{-st}\,dt \qquad (s \in \mathbb{C}) $$
Determine the exact *Region of Convergence (ROC)* in the complex plane $s = \xi + i\eta$.
2. Evaluate the *Bounded-Input Bounded-Output (BIBO) stability* of the filter, which requires the impulse response to be absolutely integrable:
$$ \|h\|_1 := \int_0^\infty |h(t)|\,dt < \infty $$
3. Evaluate the total *electrical energy dissipation* $E_{\text{total}}$ delivered to a unit load, defined by the $L^2$-energy integral:
$$ E_{\text{total}} := \int_0^\infty \big( h(t) \big)^2\,dt $$
and determine the critical threshold for the damping coefficient $\sigma$.

##### 2. Mathematical Deduction and Solution
**Phase 1: Computation of the Laplace Transform and ROC:**
Writing the Laplace integral explicitly:
$$ H(s) = A \int_0^\infty e^{-\sigma t} \sin(\omega_0 t) e^{-st}\,dt = A \int_0^\infty e^{-(s + \sigma)t} \sin(\omega_0 t)\,dt \tag{110} $$
Let $s = \xi + i\eta$, so $s + \sigma = (\xi + \sigma) + i\eta$. Taking the absolute value of the integrand:
$$ \big| e^{-(s + \sigma)t} \sin(\omega_0 t) \big| = e^{-(\xi + \sigma)t} |\sin(\omega_0 t)| \le e^{-(\xi + \sigma)t} \tag{111} $$
By the Direct Comparison Test, the improper integral converges absolutely if $\int_0^\infty e^{-(\xi + \sigma)t}\,dt$ converges, which occurs if and only if the real part satisfies:
$$ \operatorname{Re}(s) + \sigma > 0 \iff \operatorname{Re}(s) > -\sigma \tag{112} $$
The Region of Convergence is the open half-plane $\text{ROC} = \{s \in \mathbb{C} : \operatorname{Re}(s) > -\sigma\}$.

To compute the closed-form integral on the ROC, apply integration by parts twice to $I(B) = \int_0^B e^{-(s + \sigma)t} \sin(\omega_0 t)\,dt$:
First integration by parts: set $u = \sin(\omega_0 t)$ and $v' = e^{-(s + \sigma)t}$, giving $u' = \omega_0 \cos(\omega_0 t)$ and $v = -\frac{e^{-(s + \sigma)t}}{s + \sigma}$.
$$ I(B) = \left[ -\frac{e^{-(s + \sigma)t}}{s + \sigma} \sin(\omega_0 t) \right]_0^B + \frac{\omega_0}{s + \sigma} \int_0^B e^{-(s + \sigma)t} \cos(\omega_0 t)\,dt \tag{113} $$
Second integration by parts on the remaining integral: set $w = \cos(\omega_0 t)$ and $v' = e^{-(s + \sigma)t}$, giving $w' = -\omega_0 \sin(\omega_0 t)$ and $v = -\frac{e^{-(s + \sigma)t}}{s + \sigma}$.
$$ \int_0^B e^{-(s + \sigma)t} \cos(\omega_0 t)\,dt = \left[ -\frac{e^{-(s + \sigma)t}}{s + \sigma} \cos(\omega_0 t) \right]_0^B - \frac{\omega_0}{s + \sigma} I(B) \tag{114} $$
Substituting step 114 back into step 113 and collecting $I(B)$ terms:
$$ \left[ 1 + \frac{\omega_0^2}{(s + \sigma)^2} \right] I(B) = \frac{\omega_0}{(s + \sigma)^2} - \frac{e^{-(s + \sigma)B}}{s + \sigma} \left( \sin(\omega_0 B) + \frac{\omega_0}{s + \sigma} \cos(\omega_0 B) \right) \tag{115} $$
Since $\operatorname{Re}(s + \sigma) > 0$, the boundary term involving $e^{-(s + \sigma)B}$ vanishes as $B \to \infty$. Passing to the limit:
$$ \frac{(s + \sigma)^2 + \omega_0^2}{(s + \sigma)^2} \int_0^\infty e^{-(s + \sigma)t} \sin(\omega_0 t)\,dt = \frac{\omega_0}{(s + \sigma)^2} \tag{116} $$
Multiplying through by $\frac{(s + \sigma)^2}{(s + \sigma)^2 + \omega_0^2}$ and scaling by $A$ yields the transfer function:
$$ H(s) = \frac{A \omega_0}{(s + \sigma)^2 + \omega_0^2} \tag{117} $$

**Phase 2: BIBO Stability:**
BIBO stability requires $\|h\|_1 = A \int_0^\infty e^{-\sigma t}|\sin(\omega_0 t)|\,dt < \infty$.
Partition the domain into half-periods $I_k = \left[ \frac{k\pi}{\omega_0}, \frac{(k + 1)\pi}{\omega_0} \right]$ for $k = 0, 1, 2, \dots$:
$$ \int_0^\infty e^{-\sigma t} |\sin(\omega_0 t)|\,dt = \sum_{k=0}^\infty \int_{\frac{k\pi}{\omega_0}}^{\frac{(k + 1)\pi}{\omega_0}} e^{-\sigma t} |\sin(\omega_0 t)|\,dt \tag{118} $$
On each subinterval, substitute $t = \frac{k\pi}{\omega_0} + \tau$, where $\tau \in [0, \pi/\omega_0]$:
$$ \int_{\frac{k\pi}{\omega_0}}^{\frac{(k + 1)\pi}{\omega_0}} e^{-\sigma t} |\sin(\omega_0 t)|\,dt = e^{-\frac{\sigma k\pi}{\omega_0}} \int_0^{\pi/\omega_0} e^{-\sigma \tau} \sin(\omega_0 \tau)\,d\tau \tag{119} $$
The integral over $\tau$ in step 119 is a strictly positive constant $C(\sigma, \omega_0) > 0$. The infinite summation in step 118 becomes a geometric series:
$$ \|h\|_1 = A \, C(\sigma, \omega_0) \sum_{k=0}^\infty \left( e^{-\frac{\sigma \pi}{\omega_0}} \right)^k \tag{120} $$
The geometric series in step 120 converges if and only if the common ratio satisfies $e^{-\frac{\sigma \pi}{\omega_0}} < 1$, which holds if and only if:
$$ \sigma > 0 \tag{121} $$
If $\sigma \le 0$, the series diverges, meaning the system is unstable and will experience runaway resonance or sustained oscillations.

**Phase 3: Total Electrical Energy Dissipation:**
The total energy dissipation is given by:
$$ E_{\text{total}} = A^2 \int_0^\infty e^{-2\sigma t} \sin^2(\omega_0 t)\,dt \tag{122} $$
Using the half-angle identity $\sin^2(\omega_0 t) = \frac{1 - \cos(2\omega_0 t)}{2}$:
$$ E_{\text{total}} = \frac{A^2}{2} \int_0^\infty e^{-2\sigma t}\,dt - \frac{A^2}{2} \int_0^\infty e^{-2\sigma t} \cos(2\omega_0 t)\,dt \tag{123} $$
For $\sigma > 0$, the first integral converges to:
$$ \int_0^\infty e^{-2\sigma t}\,dt = \frac{1}{2\sigma} \tag{124} $$
The second integral is evaluated by setting $s = 0$ in the Laplace transform of $\cos(2\omega_0 t)e^{-2\sigma t}$, which yields:
$$ \int_0^\infty e^{-2\sigma t} \cos(2\omega_0 t)\,dt = \frac{2\sigma}{(2\sigma)^2 + (2\omega_0)^2} = \frac{\sigma}{2(\sigma^2 + \omega_0^2)} \tag{125} $$
Substituting step 124 and step 125 into step 123:
$$ E_{\text{total}} = \frac{A^2}{2} \left[ \frac{1}{2\sigma} - \frac{\sigma}{2(\sigma^2 + \omega_0^2)} \right] = \frac{A^2}{4\sigma} \left[ 1 - \frac{\sigma^2}{\sigma^2 + \omega_0^2} \right] = \frac{A^2}{4\sigma} \left[ \frac{\omega_0^2}{\sigma^2 + \omega_0^2} \right] \tag{126} $$
Simplifying yields the final energy formula:
$$ E_{\text{total}} = \frac{A^2 \omega_0^2}{4\sigma (\sigma^2 + \omega_0^2)} \tag{127} $$
This demonstrates that total energy dissipation is strictly finite if and only if $\sigma > 0$. As the damping approaches zero ($\sigma \to 0^+$), the total dissipated energy balloons toward infinity ($E_{\text{total}} \to \infty$), illustrating how improper integral convergence governs the physical boundaries of resonant engineering systems.
