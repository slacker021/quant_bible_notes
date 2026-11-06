---
dg-publish: true
---
# Primitives

Having developed the operational algebra of differentiation, the inverse problem naturally arises: given a real-valued function $f: I \to \mathbb{R}$, does there exist a function $F: I \to \mathbb{R}$ whose derivative coincides with $f$? 

In the differential calculus of a single variable, the search for an antiderivative or **primitive** is the algebraic counterpart to differentiation. While computing the derivative of an elementary function is a deterministic algebraic procedure that never leads beyond the class of elementary functions, finding a primitive in closed form is an inverse problem of profound depth, frequently generating transcendental non-elementary functions.

This chapter systematically develops the theory of primitives, establishing the fundamental integration techniques (parts and substitution), the algorithmic integration of rational fractions via Ostrogradsky's method, Euler substitutions for algebraic irrationals, and Pafnuty Chebyshev's landmark theorem on differential binomials.

---

# The Concept of the Primitive and the Indefinite Integral

$$\begin{gather}
\textbf{Definition 7.1: The Primitive} \\[5mm]
\text{Let } I \subseteq \mathbb{R} \text{ be an interval, and let } f: I \to \mathbb{R}. \\[2mm]
\text{A differentiable function } F: I \to \mathbb{R} \text{ is termed a primitive (or antiderivative) of } f \text{ on } I \text{ if:} \\[3.5mm]
F'(x) = f(x) \quad \forall x \in I.
\end{gather}$$

By Darboux's Theorem (Theorem 3.7), a necessary condition for $f$ to possess a primitive on an interval $I$ is that $f(I)$ must be an interval (ruling out functions with jump discontinuities, such as the Heaviside step function). As proven subsequently in Module 6 via the Fundamental Theorem of Calculus, every *continuous* function on an interval admits a primitive.

$$\begin{gather}
\textbf{Theorem 7.1: Interval Uniqueness of Primitives} \\[5mm]
\text{Let } F_1, F_2: I \to \mathbb{R} \text{ be two primitives of the same function } f \text{ on an interval } I. \\[2mm]
\text{Then } F_1 \text{ and } F_2 \text{ differ by an additive constant on } I\text{:} \\[3.5mm]
F_1(x) - F_2(x) \equiv C \quad \forall x \in I \quad (C \in \mathbb{R}).
\end{gather}$$
(see [[Proof of the Interval Uniqueness of Primitives]])

$$\begin{gather}
\textbf{Definition 7.2: The Indefinite Integral} \\[5mm]
\text{The collection of all primitives of a function } f \text{ on an interval } I \text{ is termed the indefinite integral of } f, \\[2mm]
\text{denoted by the symbolic expression:} \\[3.5mm]
\int f(x) \, dx := F(x) + C, \quad \text{where } F'(x) = f(x) \text{ and } C \in \mathbb{R} \text{ is an arbitrary constant.}
\end{gather}$$

---

# Basic General Methods of Finding Primitives

All integration formulas follow directly by inverting the master rules of differentiation established in Chapter 2.

$$\begin{gather}
\textbf{Theorem 7.2: Operational Rules of the Indefinite Integral} \\[5mm]
\begin{align}
\text{1. Linearity:} \quad &\int \big( c_1 f(x) + c_2 g(x) \big) dx = c_1 \int f(x) \, dx + c_2 \int g(x) \, dx. \\[3mm]
\text{2. Integration by Parts:} \quad &\text{If } u, v: I \to \mathbb{R} \text{ are continuously differentiable on } I\text{:} \\[2mm]
&\int u(x) v'(x) \, dx = u(x) v(x) - \int u'(x) v(x) \, dx, \quad \text{or} \quad \int u \, dv = uv - \int v \, du. \\[3mm]
\text{3. Change of Variable (Substitution):} \quad &\text{Let } \varphi: J \to I \text{ be differentiable on } J. \text{ If } F \text{ is a primitive of } f \text{ on } I\text{:} \\[2mm]
&\int f(\varphi(t)) \varphi'(t) \, dt = \left( \int f(x) \, dx \right)\Bigg|_{x = \varphi(t)} = F(\varphi(t)) + C.
\end{align}
\end{gather}$$
(see [[Proof of the Formulas for Integration by Parts and Change of Variable]])

---

# Primitives of Rational Functions and Ostrogradsky's Method

A rational function is the quotient of two real polynomials $R(x) = \frac{P(x)}{Q(x)}$. If $\deg P \ge \deg Q$, polynomial long division separates $R(x) = S(x) + \frac{P_0(x)}{Q(x)}$ where $\deg P_0 < \deg Q$.

By Corollary 5.1 (Canonical Real Factorization), the denominator factors over $\mathbb{R}$ into real linear and irreducible quadratic factors:
$$Q(x) = a_n (x - c_1)^{k_1}\dots(x - c_r)^{k_r} (x^2 + p_1 x + q_1)^{m_1}\dots(x^2 + p_s x + q_s)^{m_s} \tag{1}$$

Every proper rational fraction decomposes uniquely into real partial fractions:
$$\frac{P(x)}{Q(x)} = \sum_{i=1}^r \sum_{j=1}^{k_i} \frac{A_{ij}}{(x - c_i)^j} + \sum_{i=1}^s \sum_{j=1}^{m_i} \frac{M_{ij} x + N_{ij}}{(x^2 + p_i x + q_i)^j} \tag{2}$$

Because each partial fraction integrates into rational functions, logarithms $\ln|x - c_i|$, and arctangents $\arctan\left(\frac{2x+p}{\sqrt{4q-p^2}}\right)$, **every rational function is integrable in elementary functions**.

### Ostrogradsky’s Algebraic Reduction Method
When $Q(x)$ has high-order multiple roots, computing partial fraction coefficients requires solving enormous linear systems. Mikhail Ostrogradsky discovered an algebraic method that separates the rational part of the integral *without* factoring $Q(x)$ into linear roots:

$$\begin{gather}
\textbf{Theorem 7.3: Ostrogradsky's Algebraic Reduction Theorem} \\[5mm]
\text{Let } \frac{P(x)}{Q(x)} \text{ be a proper rational fraction. Define:} \\[3.5mm]
Q_1(x) := \gcd\big(Q(x), Q'(x)\big), \quad Q_2(x) := \frac{Q(x)}{Q_1(x)}. \\[3.5mm]
\text{Then there exist unique polynomials } P_1(x) \text{ and } P_2(x) \text{ with } \deg P_1 < \deg Q_1 \text{ and } \deg P_2 < \deg Q_2 \text{ such that:} \\[3.5mm]
\int \frac{P(x)}{Q(x)} \, dx = \frac{P_1(x)}{Q_1(x)} + \int \frac{P_2(x)}{Q_2(x)} \, dx.
\end{gather}$$
(see [[Proof of Ostrogradsky's Algebraic Reduction Theorem for Rational Primitives]])

The polynomials $P_1(x)$ and $P_2(x)$ are determined entirely through polynomial differentiation and Euclidean polynomial division, reducing the remaining integrand $\frac{P_2(x)}{Q_2(x)}$ to a denominator with purely simple (multiplicity 1) roots.

---

# Primitives of Trigonometric Functions

Consider primitives of the form $\int R(\cos x, \sin x) \, dx$, where $R(u, v)$ is a rational function of two arguments.

$$\begin{gather}
\textbf{Proposition 7.1: The Universal Half-Angle Substitution (Weierstrass Substitution)} \\[5mm]
\text{The substitution } t = \tan\left(\frac{x}{2}\right) \quad (x \in (-\pi, \pi)) \text{ rationalizes any trigonometric integral via the identities:} \\[3.5mm]
\sin x = \frac{2t}{1 + t^2}, \quad \cos x = \frac{1 - t^2}{1 + t^2}, \quad dx = \frac{2 \, dt}{1 + t^2}.
\end{gather}$$

While universal, the substitution $t = \tan(x/2)$ frequently inflates the polynomial degree. More efficient symmetric substitutions are applied based on parity:
1. If $R(-\cos x, \sin x) = -R(\cos x, \sin x)$ (odd in $\cos x$), substitute $t = \sin x$.
2. If $R(\cos x, -\sin x) = -R(\cos x, \sin x)$ (odd in $\sin x$), substitute $t = \cos x$.
3. If $R(-\cos x, -\sin x) = R(\cos x, \sin x)$ (even in both), substitute $t = \tan x$, where $\cos^2 x = \frac{1}{1+t^2}$ and $dx = \frac{dt}{1+t^2}$.

---

# Primitives of Algebraic Irrationals and Euler's Substitutions

Consider integrals of the form $\int R(x, \sqrt{a x^2 + b x + c}) \, dx$. Leonhard Euler established that any such quadratic irrational can be reduced to the integral of a rational function through one of three canonical algebraic substitutions:

$$\begin{gather}
\textbf{Theorem 7.4: Euler's Canonical Substitutions} \\[5mm]
\begin{align}
\text{1. First Euler Substitution } (a > 0)\text{:} \quad &\sqrt{a x^2 + b x + c} = \sqrt{a} x + t. \\[2mm]
&\text{Squaring eliminates } a x^2, \text{ expressing } x \text{ rationally as: } x = \frac{t^2 - c}{b - 2\sqrt{a}t}. \\[3mm]
\text{2. Second Euler Substitution } (c > 0)\text{:} \quad &\sqrt{a x^2 + b x + c} = x t + \sqrt{c}. \\[2mm]
&\text{Squaring eliminates } c, \text{ expressing } x \text{ rationally as: } x = \frac{2\sqrt{c}t - b}{a - t^2}. \\[3mm]
\text{3. Third Euler Substitution } (b^2 - 4ac > 0)\text{:} \quad &\text{Let } x_1, x_2 \in \mathbb{R} \text{ be distinct real roots. Set:} \\[2mm]
&\sqrt{a x^2 + b x + c} = \sqrt{a(x - x_1)(x - x_2)} = (x - x_1) t. \\[2mm]
&\text{Squaring yields: } a(x - x_2) = (x - x_1)t^2 \implies x = \frac{a x_2 - x_1 t^2}{a - t^2}.
\end{align}
\end{gather}$$
(see [[Proof of Euler's Substitutions for Algebraic Irrationals]])

Because a real quadratic polynomial with real coefficients either has $a > 0$, or $c > 0$, or distinct real roots ($b^2 - 4ac > 0$), at least one of Euler's three substitutions is always applicable whenever the quadratic radicand is non-negative on an interval.

---

# Non-Elementary Integrals and Chebyshev's Differential Binomial Theorem

While all rational functions and algebraic functions of quadratic radicals integrate into elementary functions, the vast majority of primitives cannot be expressed in finite terms of elementary functions:
- The Gaussian Error Function: $\int e^{-x^2} dx$
- The Sine and Cosine Integrals: $\int \frac{\sin x}{x} dx, \quad \int \frac{\cos x}{x} dx$
- The Logarithmic Integral: $\int \frac{dx}{\ln x}$
- Elliptic Integrals: $\int \frac{dx}{\sqrt{(1 - x^2)(1 - k^2 x^2)}} \quad (0 < k < 1)$

### Chebyshev’s Theorem on Differential Binomials
Pafnuty Chebyshev resolved the exact boundary of elementary integrability for the differential binomial:

$$\begin{gather}
\textbf{Theorem 7.5: Chebyshev’s Differential Binomial Theorem} \\[5mm]
\text{Consider the differential binomial integral:} \\[3.5mm]
\int x^m (a + b x^n)^p \, dx \quad (a, b \in \mathbb{R} \setminus \{0\}, \ m, n, p \in \mathbb{Q}, \ n \neq 0). \\[3.5mm]
\text{This integral can be expressed in terms of elementary functions if and only if at least one of} \\[2mm]
\text{the following three conditions is satisfied:} \\[3mm]
\begin{align}
\text{1. } &p \in \mathbb{Z} \quad (\text{rationalized by substituting } x = z^N, \text{ where } N = \text{lcm}(\text{denom}(m), \text{denom}(n))). \\[2mm]
\text{2. } &\frac{m + 1}{n} \in \mathbb{Z} \quad (\text{rationalized by substituting } a + b x^n = z^N, \text{ where } N = \text{denom}(p)). \\[2mm]
\text{3. } &\frac{m + 1}{n} + p \in \mathbb{Z} \quad (\text{rationalized by substituting } a x^{-n} + b = z^N, \text{ where } N = \text{denom}(p)).
\end{align}
\end{gather}$$
(see [[Proof of Chebyshev's Theorem on Differential Binomials]])

Theorem 7.5 demonstrates that integration, unlike differentiation, is fundamentally an existential problem that probes the algebraic independence of transcendental function fields.
