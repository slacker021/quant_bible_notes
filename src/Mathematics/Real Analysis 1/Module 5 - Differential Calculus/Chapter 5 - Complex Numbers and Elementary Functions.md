---
dg-publish: true
---
# Complex Numbers and Elementary Functions

The real continuum $\mathbb{R}$, constructed through Dedekind cuts in Module 2, is topologically complete and linearly ordered. However, it is algebraically incomplete: negative numbers possess no real square roots, and simple polynomial equations such as $x^2 + 1 = 0$ admit no solutions in $\mathbb{R}$. 

By embedding the real line into the two-dimensional field of **complex numbers** $\mathbb{C}$, analysis achieves algebraic closedness. This extension does not merely provide roots for algebraic equations; it fundamentally unifies the transcendental elementary functions—exponential, trigonometric, and hyperbolic—into manifestations of a single complex analytic function. 

In this chapter, the theory of complex numbers is developed with strict adherence to single-variable analysis, preparing the ground for the natural science differential equations of Chapter 6 and the integration of rational functions in Chapter 7.

---

# The Algebraic Field of Complex Numbers

### Axiomatic Construction
$$\begin{gather}
\textbf{Definition 5.1: The Field of Complex Numbers} \\[5mm]
\text{The set of complex numbers } \mathbb{C} \text{ is the Cartesian product } \mathbb{R} \times \mathbb{R} = \{(x, y) : x, y \in \mathbb{R}\} \\[2mm]
\text{equipped with vector addition and polynomial-style multiplication:} \\[3.5mm]
(x_1, y_1) + (x_2, y_2) := (x_1 + x_2, \ y_1 + y_2) \tag{1} \\[2mm]
(x_1, y_1) \cdot (x_2, y_2) := (x_1 x_2 - y_1 y_2, \ x_1 y_2 + x_2 y_1) \tag{2}
\end{gather}$$

Under these operations, $\mathbb{C}$ is a field with additive identity $0_{\mathbb{C}} = (0, 0)$ and multiplicative identity $1_{\mathbb{C}} = (1, 0)$. 

The subset of elements of the form $(x, 0)$ forms a subfield isomorphic to the real line $\mathbb{R}$ via the identification $(x, 0) \equiv x$. The special element $i := (0, 1)$ is termed the **imaginary unit**. Computing its square from equation (2):
$$i^2 = (0, 1) \cdot (0, 1) = (0 \cdot 0 - 1 \cdot 1, \ 0 \cdot 1 + 1 \cdot 0) = (-1, 0) \equiv -1 \tag{3}$$

Every complex number $z = (x, y)$ can thus be represented uniquely in algebraic form as:
$$z = x + iy \quad (x, y \in \mathbb{R}) \tag{4}$$
The scalar $x = \operatorname{Re}(z)$ is the **real part**, and $y = \operatorname{Im}(z)$ is the **imaginary part**.

### Conjugation and Modulus
$$\begin{gather}
\textbf{Definition 5.2: Complex Conjugation and Modulus} \\[5mm]
\text{For any complex number } z = x + iy \in \mathbb{C}\text{:} \\[2mm]
\text{1. The complex conjugate of } z \text{ is: } \bar{z} := x - iy. \\[2mm]
\text{2. The modulus (or absolute value) of } z \text{ is: } |z| := \sqrt{z \bar{z}} = \sqrt{x^2 + y^2} \ge 0.
\end{gather}$$

The modulus satisfies all metric norm properties on $\mathbb{C}$:
1. Positive definiteness: $|z| \ge 0$, and $|z| = 0 \iff z = 0$.
2. Multiplicativity: $|z_1 z_2| = |z_1| |z_2|$.
3. Triangle inequality: $|z_1 + z_2| \le |z_1| + |z_2|$ and $||z_1| - |z_2|| \le |z_1 - z_2|$.

### Polar Representation and de Moivre's Formula
In the geometric plane $\mathbb{R}^2$, identifying $(x, y)$ with polar coordinates $(r, \varphi)$ via $x = r \cos\varphi$ and $y = r \sin\varphi$ yields the **trigonometric form**:
$$z = r(\cos\varphi + i\sin\varphi) \tag{5}$$
where $r = |z|$ is the modulus, and $\varphi = \operatorname{Arg}(z) \in (-\pi, \pi]$ is the principal argument.

$$\begin{gather}
\textbf{Theorem 5.1: De Moivre's Formula and Roots of Unity} \\[5mm]
\text{1. For any } z = r(\cos\varphi + i\sin\varphi) \in \mathbb{C} \text{ and any integer } n \in \mathbb{Z}\text{:} \\[3.5mm]
z^n = r^n \big( \cos(n\varphi) + i\sin(n\varphi) \big). \\[3.5mm]
\text{2. For any } n \in \mathbb{N}, \text{ the equation } w^n = z \text{ possesses exactly } n \text{ distinct roots in } \mathbb{C}\text{:} \\[3.5mm]
w_k = \sqrt[n]{r} \left( \cos\left(\frac{\varphi + 2\pi k}{n}\right) + i\sin\left(\frac{\varphi + 2\pi k}{n}\right) \right), \quad k = 0, 1, \dots, n - 1.
\end{gather}$$
(see [[Proof of De Moivre's Formula and Roots of Unity]])

The roots of unity for $z = 1$ form a regular $n$-gon inscribed in the unit circle $|w| = 1$.

---

# Convergence and Power Series in the Complex Plane

Equipped with the Euclidean distance $d(z_1, z_2) = |z_1 - z_2|$, $\mathbb{C} \cong \mathbb{R}^2$ is a complete metric space.

$$\begin{gather}
\textbf{Definition 5.3: Convergence of Complex Sequences} \\[5mm]
\text{A sequence } \{z_n\}_{n=1}^\infty \subset \mathbb{C} \text{ with } z_n = x_n + i y_n \text{ converges to } z_0 = x_0 + i y_0 \in \mathbb{C} \text{ if:} \\[3.5mm]
\lim_{n \to \infty} |z_n - z_0| = 0 \iff \lim_{n \to \infty} x_n = x_0 \quad \text{and} \quad \lim_{n \to \infty} y_n = y_0.
\end{gather}$$

### Complex Power Series
Consider an infinite series of complex terms $\sum_{n=0}^\infty c_n (z - z_0)^n$ with $c_n \in \mathbb{C}$.

$$\begin{gather}
\textbf{Theorem 5.2: The Cauchy-Hadamard Theorem in } \mathbb{C} \\[5mm]
\text{Let } \sum_{n=0}^\infty c_n (z - z_0)^n \text{ be a power series. Define the radius of convergence } R \in [0, \infty] \text{ by:} \\[3.5mm]
\frac{1}{R} := \limsup_{n \to \infty} \sqrt[n]{|c_n|}. \\[3.5mm]
\text{1. If } |z - z_0| < R, \text{ the series converges absolutely in } \mathbb{C}. \\[2mm]
\text{2. If } |z - z_0| > R, \text{ the series diverges.}
\end{gather}$$
(see [[Proof of the Cauchy-Hadamard Theorem in the Complex Field]])

Inside the disk of convergence $B_R(z_0) = \{z \in \mathbb{C} : |z - z_0| < R\}$, the power series defines a continuous, infinitely differentiable function whose derivative can be computed by term-by-term differentiation.

---

# Euler's Formula and the Unification of Elementary Functions

In real analysis, the exponential function $e^x$, the trigonometric functions $\cos x, \sin x$, and the hyperbolic functions $\cosh x, \sinh x$ appear as disparate classes with distinct geometric definitions. Through complex power series, they are revealed to be identical.

$$\begin{gather}
\textbf{Definition 5.4: The Complex Exponential Function} \\[5mm]
\text{For any complex number } z \in \mathbb{C}, \text{ the complex exponential is defined by the power series:} \\[3.5mm]
e^z := \sum_{n=0}^\infty \frac{z^n}{n!} = 1 + z + \frac{z^2}{2!} + \frac{z^3}{3!} + \dots
\end{gather}$$
Because $\lim_{n \to \infty} \sqrt[n]{\frac{1}{n!}} = 0$, by Theorem 5.2 the radius of convergence is $R = \infty$. The series converges absolutely for every $z \in \mathbb{C}$.

$$\begin{gather}
\textbf{Theorem 5.3: Euler’s Formula} \\[5mm]
\text{For every real number } \theta \in \mathbb{R}\text{:} \\[3.5mm]
e^{i\theta} = \cos\theta + i\sin\theta.
\end{gather}$$
(see [[Proof of Euler's Formula and the Unification of Elementary Functions]])

Setting $\theta = \pi$ in Euler's formula produces the identity:
$$e^{i\pi} + 1 = 0 \tag{6}$$

### Complex Definitions of Circular and Hyperbolic Functions
$$\begin{gather}
\textbf{Definition 5.5: Unified Analytic Functions} \\[5mm]
\begin{align}
\cos z &:= \frac{e^{iz} + e^{-iz}}{2}, \quad &\sin z &:= \frac{e^{iz} - e^{-iz}}{2i}, \\[3mm]
\cosh z &:= \frac{e^z + e^{-z}}{2}, \quad &\sinh z &:= \frac{e^z - e^{-z}}{2}.
\end{align}
\end{gather}$$

Direct evaluation reveals the fundamental bridge between circular rotations and hyperbolic shears:
$$\cos(iz) = \cosh z, \quad \sin(iz) = i\sinh z \tag{7}$$

>[!example]- Trigonometric Summation via Complex Geometric Series
>Evaluating Dirichlet-type sums $\sum_{k=0}^n \cos(kx)$ directly using real trigonometric formulas is algebraically tedious. In $\mathbb{C}$, applying Euler's formula converts the sum into a geometric progression:
>$$\sum_{k=0}^n \cos(kx) = \operatorname{Re}\left( \sum_{k=0}^n e^{ikx} \right) = \operatorname{Re}\left( \frac{1 - e^{i(n+1)x}}{1 - e^{ix}} \right) = \frac{\sin\left(\frac{n+1}{2}x\right) \cos\left(\frac{n}{2}x\right)}{\sin(x/2)} \tag{8}$$

---

# Complex-Valued Functions of a Real Variable

To prevent premature multivariable entanglements, differential calculus in Module 5 operates on complex-valued functions defined on real domains:
$$f: I \to \mathbb{C}, \quad I \subseteq \mathbb{R} \tag{9}$$

Such a function decomposes uniquely into a pair of real-valued functions:
$$f(t) = u(t) + i v(t), \quad u(t) = \operatorname{Re}(f(t)), \quad v(t) = \operatorname{Im}(f(t)) \tag{10}$$

$$\begin{gather}
\textbf{Definition 5.6: Differentiation of Complex-Valued Functions} \\[5mm]
\text{A complex-valued function } f: I \to \mathbb{C} \text{ is differentiable at } t_0 \in \text{int}(I) \text{ if } u \text{ and } v \text{ are differentiable at } t_0. \\[2mm]
\text{The derivative is defined componentwise by:} \\[3.5mm]
f'(t_0) := u'(t_0) + i v'(t_0) = \lim_{h \to 0} \frac{f(t_0 + h) - f(t_0)}{h}.
\end{gather}$$

All arithmetic rules of differentiation (linearity, product rule, quotient rule) extend identically to complex-valued functions.

$$\begin{gather}
\textbf{Proposition 5.1: Derivative of the Complex Exponential Trajectory} \\[5mm]
\text{Let } \lambda = \alpha + i\omega \in \mathbb{C} \text{ with } \alpha, \omega \in \mathbb{R}. \text{ The function } f(t) = e^{\lambda t} = e^{\alpha t}(\cos(\omega t) + i\sin(\omega t)) \text{ satisfies:} \\[3.5mm]
\frac{d}{dt} \big( e^{\lambda t} \big) = \lambda e^{\lambda t}.
\end{gather}$$
This single proposition governs the characteristic equation method for solving oscillatory differential equations in Chapter 6.

---

# The Fundamental Theorem of Algebra

The crowning achievement of complex numbers in mathematical analysis is the complete factorization of algebraic polynomials.

$$\begin{gather}
\textbf{Theorem 5.4: The Fundamental Theorem of Algebra (d'Alembert-Gauss)} \\[5mm]
\text{Every non-constant polynomial with complex coefficients:} \\[3.5mm]
P(z) = a_n z^n + a_{n-1} z^{n-1} + \dots + a_1 z + a_0 \quad (a_n \neq 0, \ n \ge 1) \\[3.5mm]
\text{possesses at least one root in } \mathbb{C}, \text{ that is, } \exists z_0 \in \mathbb{C} \text{ such that } P(z_0) = 0.
\end{gather}$$
(see [[Proof of the Fundamental Theorem of Algebra via the Minimum Modulus Principle]])

### Factorization Over the Real Field
By the polynomial division algorithm, if $P(z_0) = 0$, then $P(z) = (z - z_0) Q(z)$ for some polynomial $Q(z)$ of degree $n - 1$. Iterating this division establishes that every polynomial of degree $n$ factors completely into $n$ linear factors over $\mathbb{C}$:
$$P(z) = a_n (z - z_1)(z - z_2)\dots(z - z_n) \tag{11}$$

If $P(x) \in \mathbb{R}[x]$ has real coefficients, non-real roots occur in complex-conjugate pairs: $P(z_0) = 0 \implies P(\bar{z}_0) = 0$. Combining the linear factors $(x - z_0)(x - \bar{z}_0) = x^2 - 2\operatorname{Re}(z_0)x + |z_0|^2$ produces real quadratic factors with negative discriminant:

$$\begin{gather}
\textbf{Corollary 5.1: Canonical Real Factorization of Polynomials} \\[5mm]
\text{Every polynomial } P(x) \in \mathbb{R}[x] \text{ factors uniquely over } \mathbb{R} \text{ into linear and irreducible quadratic factors:} \\[3.5mm]
P(x) = a_n (x - c_1)^{k_1}\dots(x - c_r)^{k_r} (x^2 + p_1 x + q_1)^{m_1}\dots(x^2 + p_s x + q_s)^{m_s}, \\[3.5mm]
\text{where } p_j^2 - 4q_j < 0 \text{ for each } j = 1, \dots, s.
\end{gather}$$

Corollary 5.1 is the exact algebraic foundation required for the complete decomposition of rational functions into partial fractions in Chapter 7.
