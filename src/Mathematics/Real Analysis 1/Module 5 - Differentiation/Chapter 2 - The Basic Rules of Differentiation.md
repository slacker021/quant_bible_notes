---
dg-publish: true
---
# Algebraic Infrastructure of Differentiation
In [[Chapter 1 - Differentiable Functions|Chapter 1]], differentiability was formulated through the lens of local linear approximation: a real-valued mapping is differentiable at an anchor point if its local increment decomposes into a continuous linear transformation and a remainder term that decays strictly faster than the perturbation of the argument. While the difference quotient provides the formal definition of this property, evaluating limits of incremental ratios for every composite, rational, or transcendental mapping encountered in the quantitative sciences is computationally prohibitive and structurally inefficient.

The calculus of differentiation overcomes this limitation by recognizing that the differential operator respects the algebraic structures of the underlying function spaces. When endowed with pointwise addition and multiplication, the collection of differentiable functions constitutes an associative and commutative algebra over the real field $\mathbb{R}$. This chapter establishes the operational machinery that permits the derivative of an arbitrarily complex mapping to be determined systematically from its constituent elementary components.

### Linearity of the Differential Operator
Let $E \subseteq \mathbb{R}$ be a non-empty subset, and let $x_0 \in E \cap E'$ be an accumulation point of $E$. The simplest algebraic operations on real-valued functions are pointwise addition and scalar multiplication. The differential operator acts as a continuous linear map from the vector space of differentiable functions into $\mathbb{R}$: 
$$
\begin{gather}
\textbf{Theorem: The Linearity of Differentiation} \\[5mm]
\text{Let } f: E \to \mathbb{R} \text{ and } g: E \to \mathbb{R} \text{ be functions differentiable at } x_0 \in E \cap E', \\[2mm]
\text{and let } \alpha, \beta \in \mathbb{R} \text{ be arbitrary real constants. Then the linear combination} \\[2mm]
(\alpha f + \beta g): E \to \mathbb{R} \\[2mm]
\text{is differentiable at } x_0, \text{ and its derivative satisfies:} \\[3.5mm]
(\alpha f + \beta g)'(x_0) = \alpha f'(x_0) + \beta g'(x_0)
\end{gather}
$$
(see [[Proof of The Linearity of Differentiation]])

Expressed in the language of differentials, linearity signifies that the differential operator $d$ commutes with the vector space operations on $C^1$ manifolds:
$$
\begin{gather}
d(\alpha f + \beta g)(x_0) = \alpha \, df(x_0) + \beta \, dg(x_0) \tag{1}
\end{gather}
$$

>[!danger]+ Intuition: Linear Superposition of Local Slopes
>Because the differential represents the tangent slope of a functional graph, the derivative of a linear combination is the exact linear combination of the respective tangent slopes. Geometrically, scaling a function vertically scales its steepness by the identical factor; adding two functions tilts the tangent line by the sum of their individual inclination angles in linear coordinates.

### The Leibniz Product Rule and the Non-Linear Interaction of Increments
While addition preserves linearity directly, the pointwise product $(f \cdot g)(x) := f(x)g(x)$ introduces a non-linear coupling between the variations of the factors. Consider the total increment of the product function under a displacement $h = \Delta x$:
$$
\begin{gather}
\Delta(fg)(x_0; h) = f(x_0 + h)g(x_0 + h) - f(x_0)g(x_0) \tag{2}
\end{gather}
$$
Adding and subtracting the cross-term $f(x_0)g(x_0 + h)$ decomposes the increment into two distinct rectangular variations:
$$
\begin{gather}
\Delta(fg)(x_0; h) = f(x_0)\Delta g(x_0; h) + g(x_0 + h)\Delta f(x_0; h) \tag{3}
\end{gather}
$$
Dividing by the scalar displacement $h$ and appealing to the continuity of $g$ at $x_0$ yields the celebrated formula discovered by Gottfried Wilhelm Leibniz:

$$
\begin{gather}
\textbf{Theorem: The Leibniz Product Rule} \\[5mm]
\text{Let } f: E \to \mathbb{R} \text{ and } g: E \to \mathbb{R} \text{ be functions differentiable at } x_0 \in E \cap E'. \\[2mm]
\text{Then the product function } (fg): E \to \mathbb{R} \text{ is differentiable at } x_0, \\[2mm]
\text{and its derivative satisfies:} \\[3.5mm]
(fg)'(x_0) = f'(x_0)g(x_0) + f(x_0)g'(x_0)
\end{gather}
$$
(see [[Proof of The Leibniz Product Rule]])

In terms of differential 1-forms, the product rule adopts an elegant symmetric formulation:
$$
\begin{gather}
d(fg)(x_0) = g(x_0) \, df(x_0) + f(x_0) \, dg(x_0) \tag{4}
\end{gather}
$$
The equation of step 4 reveals that the differential operator acts on the ring of functions as a formal *derivation*—an algebraic mapping satisfying the Leibniz condition.

>[!example]- Example: Monomial Differentiation via Mathematical Induction
>Let $n \in \mathbb{N}$ and consider the power monomial $f_n(x) := x^n$. For $n = 1$, the derivative is $f_1'(x) = 1 = 1 \cdot x^0$. Assuming the induction hypothesis holds for $n = k$, such that $(x^k)' = k x^{k-1}$, the product rule applied to $x^{k+1} = x \cdot x^k$ yields:
>$$
>\begin{gather}
>(x^{k+1})' = (x)' x^k + x (x^k)' = 1 \cdot x^k + x \big(k x^{k-1}\big) = (k + 1)x^k \tag{5}
>\end{gather}
>$$
>By the principle of mathematical induction, the power rule holds for all positive integers:
>$$
>\begin{gather}
>\frac{d}{dx} x^n = n x^{n-1}, \quad \forall n \in \mathbb{N} \tag{6}
>\end{gather}
>$$
>Combining step 6 with the linearity theorem establishes that every polynomial $P_n(x) = \sum_{k=0}^n c_k x^k$ is differentiable on the entire real line $\mathbb{R}$, with derivative $P_n'(x) = \sum_{k=1}^n k c_k x^{k-1}$.

### The Quotient Rule and Inversion of Functions
To extend the differential algebra to rational mappings, consider the reciprocal function $r(x) := \frac{1}{g(x)}$. Provided that $g(x_0) \neq 0$, the continuity of $g$ guarantees that $g(x) \neq 0$ throughout a sufficiently small open neighborhood $U(x_0)$. 

The variation of the reciprocal mapping is given by:
$$
\begin{gather}
\Delta\left(\frac{1}{g}\right)(x_0; h) = \frac{1}{g(x_0 + h)} - \frac{1}{g(x_0)} = -\frac{g(x_0 + h) - g(x_0)}{g(x_0)g(x_0 + h)} \tag{7}
\end{gather}
$$
Taking the limit of the quotient as $h \to 0$ and combining the result with the Leibniz product rule for $f(x) \cdot \frac{1}{g(x)}$ generates the general quotient rule:
$$
\begin{gather}
\textbf{Theorem: The Quotient Rule of Differentiation} \\[5mm]
\text{Let } f: E \to \mathbb{R} \text{ and } g: E \to \mathbb{R} \text{ be differentiable at } x_0 \in E \cap E', \\[2mm]
\text{with the restriction that } g(x_0) \neq 0. \text{ Then the quotient mapping } \frac{f}{g}: E \setminus g^{-1}(\{0\}) \to \mathbb{R} \\[2mm]
\text{is differentiable at } x_0, \text{ and its derivative satisfies:} \\[3.5mm]
\left(\frac{f}{g}\right)'(x_0) = \frac{f'(x_0)g(x_0) - f(x_0)g'(x_0)}{[g(x_0)]^2}
\end{gather}
$$
(see [[Proof of The Quotient Rule of Differentiation]])

Translating the statement of the theorem into differential notation yields:
$$
\begin{gather}
d\left(\frac{f}{g}\right)(x_0) = \frac{g(x_0)\,df(x_0) - f(x_0)\,dg(x_0)}{[g(x_0)]^2} \tag{8}
\end{gather}
$$

>[!example]- Example: The Circular Tangent, Cotangent, Secant, and Cosecant Derivatives
>Applying the quotient rule to the circular trigonometric ratios using the elementary derivatives established in Chapter 1 ($\sin'(x) = \cos(x)$ and $\cos'(x) = -\sin(x)$) produces the standard trigonometric derivative catalog:
>$$
>\begin{gather}
>\frac{d}{dx} \tan(x) = \frac{d}{dx}\left(\frac{\sin(x)}{\cos(x)}\right) = \frac{\cos(x)\cos(x) - \sin(x)(-\sin(x))}{\cos^2(x)} = \frac{1}{\cos^2(x)} = 1 + \tan^2(x) \tag{9} \\[2mm]
>\frac{d}{dx} \cot(x) = \frac{d}{dx}\left(\frac{\cos(x)}{\sin(x)}\right) = \frac{-\sin(x)\sin(x) - \cos(x)\cos(x)}{\sin^2(x)} = -\frac{1}{\sin^2(x)} = -(1 + \cot^2(x)) \tag{10} \\[2mm]
>\frac{d}{dx} \sec(x) = \frac{d}{dx}\left(\frac{1}{\cos(x)}\right) = -\frac{-\sin(x)}{\cos^2(x)} = \sec(x)\tan(x) \tag{11} \\[2mm]
>\frac{d}{dx} \csc(x) = \frac{d}{dx}\left(\frac{1}{\sin(x)}\right) = -\frac{\cos(x)}{\sin^2(x)} = -\csc(x)\cot(x) \tag{12}
>\end{gather}
>$$

### Symmetry Inversion Under Differentiation
An essential structural property of the differential operator is its transmission of geometric symmetry. When a function exhibits even or odd parity across the origin, differentiation alters that parity systematically: 
$$
\begin{gather}
\textbf{Corollary: Parity Alternation Under Differentiation} \\[5mm]
\text{Let } E \subseteq \mathbb{R} \text{ be a symmetric domain around the origin } (x \in E \iff -x \in E), \\[2mm]
\text{and let } f: E \to \mathbb{R} \text{ be a differentiable function on } E. \text{ Then:} \\[2mm]
1. \text{ If } f \text{ is an even function } (f(-x) = f(x)), \text{ its derivative } f' \text{ is an odd function } (f'(-x) = -f'(x)). \\[2mm]
2. \text{ If } f \text{ is an odd function } (f(-x) = -f(x)), \text{ its derivative } f' \text{ is an even function } (f'(-x) = f'(x)). \\[2mm]
3. \text{ If } E \text{ is an open interval containing } 0, \text{ then } f' \text{ is odd if and only if } f \text{ is even.}
\end{gather}
$$
(see [[Proof of Parity Alternation Under Differentiation]])

---
# Composition, Inversion, and Structural Transformations
While arithmetic operations account for linear and rational interactions, the vast majority of physical and financial models involve the nested nesting of dependencies: a quantity $z$ depends on an intermediate state $y$, which itself is driven by an underlying coordinate $x$.

### The Carathéodory Formulation of Differentiability
The standard limit definition of differentiability involves division by the increment $h$, which complicates proofs of the chain rule when the intermediate function exhibits stagnation ($\Delta y = 0$ for non-zero $\Delta x$). In 1950, Constantin Carathéodory introduced an elegant reformulation that circumvents this division entirely:
$$
\begin{gather}
\textbf{Theorem: The Carathéodory Differentiability Criterion} \\[5mm]
\text{Let } E \subseteq \mathbb{R}, \text{ let } x_0 \in E \cap E', \text{ and let } f: E \to \mathbb{R}. \text{ The function } f \text{ is differentiable at } x_0 \\[2mm]
\text{if and only if there exists a function } \phi: E \to \mathbb{R} \text{ that is continuous at } x_0 \text{ such that:} \\[3.5mm]
f(x) - f(x_0) = \phi(x)(x - x_0), \quad \forall x \in E \\[3.5mm]
\text{Under these equivalent conditions, the value of the auxiliary function at the anchor point is:} \\[2mm]
\phi(x_0) = f'(x_0)
\end{gather}
$$
(see [[Proof of The Carathéodory Differentiability Criterion]])

##### Higher-Order Jet Regularity of the Carathéodory Auxiliary Function
The utility of Carathéodory's formulation extends directly to higher-order differential structures:
$$
\begin{gather}
\textbf{Proposition: Higher-Order Smoothness of the Carathéodory Factor} \\[5mm]
\text{Let } f: U(x_0) \to \mathbb{R} \text{ be defined on a neighborhood of } x_0, \text{ and suppose that} \\[2mm]
f(x) - f(x_0) = \phi(x)(x - x_0) \\[2mm]
\text{for some function } \phi: U(x_0) \to \mathbb{R}. \text{ If } \phi \in C^{n-1}(U(x_0)), \text{ then } f \text{ possesses an } n\text{-th order} \\[2mm]
\text{derivative } f^{(n)}(x_0) \text{ at } x_0, \text{ given by the formula:} \\[3.5mm]
f^{(n)}(x_0) = n \, \phi^{(n-1)}(x_0)
\end{gather}
$$
(see [[Proof of Higher-Order Smoothness of the Carathéodory Factor]])

### The Chain Rule for Composite Mappings
With Carathéodory's criterion established, the differentiation of composite functions reduces to an elementary product of continuous factors: 
$$
\begin{gather}
\textbf{Theorem: The Chain Rule} \\[5mm]
\text{Let } X, Y \subseteq \mathbb{R}, \text{ let } f: X \to Y, \text{ and let } g: Y \to \mathbb{R}. \text{ Suppose that } x_0 \in X \cap X' \text{ and that} \\[2mm]
y_0 := f(x_0) \in Y \cap Y'. \text{ If } f \text{ is differentiable at } x_0 \text{ and } g \text{ is differentiable at } y_0, \\[2mm]
\text{then the composite mapping } (g \circ f): X \to \mathbb{R} \text{ is differentiable at } x_0, \\[2mm]
\text{and its derivative satisfies:} \\[3.5mm]
(g \circ f)'(x_0) = g'(f(x_0)) \cdot f'(x_0)
\end{gather}
$$
(see [[Proof of The Chain Rule]])

##### Invariance of the Form of the First Differential
The primary operational power of the Chain Rule lies in the geometric behavior of differentials. If $y = f(x)$ and $z = g(y)$, then regarding $y$ as an independent variable yields the differential $dz = g'(y) \, dy$. If $y$ is instead regarded as a dependent variable governed by $x$, then the differential of $z$ with respect to $x$ is:
$$
\begin{gather}
dz = (g \circ f)'(x) \, dx = g'(f(x)) \cdot f'(x) \, dx \tag{13}
\end{gather}
$$
Because $dy = f'(x) \, dx$, substituting $dy$ into step 13 restores the exact linear relation:
$$
\begin{gather}
dz = g'(y) \, dy \tag{14}
\end{gather}
$$
The formal expression of the first differential $df = f'(x) \, dx$ retains its structure regardless of whether $x$ is an independent coordinate or an intermediate function of a deeper parameter $t$. This universal property is termed the *first-order differential invariance*.

### The Inverse Function Theorem for Single-Variable Mappings
If a continuous mapping $f: X \to Y$ is strictly monotonic on an interval $X \subset \mathbb{R}$, it defines a bijection onto its image $Y := f(X)$, guaranteeing the existence of a continuous inverse mapping $f^{-1}: Y \to X$. The differentiation of this inverse corresponds geometrically to interchanging the roles of the abscissa and ordinate axes, reflecting the tangent line across the main diagonal $y = x$: 
$$
\begin{gather}
\textbf{Theorem: The Derivative of an Inverse Function} \\[5mm]
\text{Let } X, Y \subset \mathbb{R} \text{ be open intervals, and let } f: X \to Y \text{ and } f^{-1}: Y \to X \text{ be mutually inverse} \\[2mm]
\text{continuous bijections. If } f \text{ is differentiable at } x_0 \in X \text{ with non-vanishing derivative } f'(x_0) \neq 0, \\[2mm]
\text{then the inverse mapping } f^{-1} \text{ is differentiable at } y_0 := f(x_0) \in Y, \\[2mm]
\text{and its derivative satisfies:} \\[3.5mm]
(f^{-1})'(y_0) = \frac{1}{f'(x_0)} = \frac{1}{f'(f^{-1}(y_0))}
\end{gather}
$$
(see [[Proof of The Derivative of an Inverse Function]])

In differential notation, the relationship between inverse derivatives is expressed by reciprocal differentials:
$$
\begin{gather}
dx = \frac{1}{f'(x)} \, dy \iff \frac{dx}{dy} = \frac{1}{\frac{dy}{dx}} \tag{15}
\end{gather}
$$

>[!info]+ Remark: Topological Sharpness and the Necessity of Inverse Continuity
>The hypothesis in the Inverse Function Theorem requiring $f^{-1}$ to be continuous at $y_0$ cannot be omitted. If the global topology of the mapping allows the image to fracture such that $f^{-1}$ is discontinuous at $y_0$, the existence of a non-zero derivative $f'(x_0)$ does not guarantee that the difference quotient $\frac{f^{-1}(y) - f^{-1}(y_0)}{y - y_0}$ will converge.
>
>Consider the function $f: \mathbb{R} \to \mathbb{R}$ defined by:
>$$
>\begin{gather}
>f(x) = \begin{cases} 2x & \text{if } x \in \mathbb{Q} \\ 3x & \text{if } x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \tag{16}
>\end{gather}
>$$
>At $x_0 = 0$, $f$ is continuous only at 0 and discontinuous everywhere else; its inverse is likewise discontinuous everywhere except at 0. Even if a mapping is constructed to be differentiable at a single point with non-zero slope, any topological tearing that renders $f^{-1}$ discontinuous along approaching sequences destroys the convergence of the inverse derivative quotient.

##### Extension of the Power Rule to Rational Exponents
With the Inverse Function Theorem established, the power rule can be rigorously extended from integers to all rational numbers $r = p/q \in \mathbb{Q}$, with $p \in \mathbb{Z}$ and $q \in \mathbb{N}$:

Let $y = f(x) = x^{1/q}$ on $(0, \infty)$. The inverse mapping is $x = g(y) = y^q$. By virtue of the integer power rule, $g'(y) = q y^{q-1} \neq 0$ on $(0, \infty)$. Invoking the Inverse Function Theorem:
$$
\begin{gather}
(x^{1/q})' = \frac{1}{g'(y)} = \frac{1}{q y^{q-1}} = \frac{1}{q (x^{1/q})^{q-1}} = \frac{1}{q} x^{\frac{1}{q} - 1} \tag{17}
\end{gather}
$$
Applying the Chain Rule to $x^{p/q} = (x^{1/q})^p$ then yields:
$$
\begin{gather}
\frac{d}{dx} x^{p/q} = p(x^{1/q})^{p-1} \cdot \left(\frac{1}{q} x^{\frac{1}{q}-1}\right) = \frac{p}{q} x^{\frac{p}{q}-1} \tag{18}
\end{gather}
$$
Thus, the power rule $\frac{d}{dx} x^r = r x^{r-1}$ is valid for all rational exponents $r \in \mathbb{Q}$ on $(0, \infty)$.

---
# The Twelve Transcendental Systems
In quantitative analysis, functional modeling relies heavily on circular and hyperbolic geometries. To ensure complete clarity, the six fundamental hyperbolic functions, the six inverse circular functions, and the six inverse hyperbolic functions are systematically defined, accompanied by their governing algebraic identities and derivative formulas.

### The Six Fundamental Hyperbolic Functions
Hyperbolic functions arise naturally as the symmetric and antisymmetric components of the natural exponential mapping $\exp(x) = e^x$: 
$$
\begin{align}
& \textbf{Definition: The Six Fundamental Hyperbolic Functions}  \\[5mm]
 & \hspace{0.2in} \text{Let } x \in \mathbb{R}. \text{ The hyperbolic functions are defined analytically as follows:} \\[2mm]
 & \hspace{0.2in} 1. \text{ Hyperbolic Sine: } \sinh(x) := \frac{e^x - e^{-x}}{2}, \quad x \in \mathbb{R} \\[2mm]
 & \hspace{0.2in} 2. \text{ Hyperbolic Cosine: } \cosh(x) := \frac{e^x + e^{-x}}{2}, \quad x \in \mathbb{R} \\[2mm]
 & \hspace{0.2in} 3. \text{ Hyperbolic Tangent: } \tanh(x) := \frac{\sinh(x)}{\cosh(x)} = \frac{e^x - e^{-x}}{e^x + e^{-x}}, \quad x \in \mathbb{R} \\[2mm]
 & \hspace{0.2in} 4. \text{ Hyperbolic Cotangent: } \coth(x) := \frac{\cosh(x)}{\sinh(x)} = \frac{e^x + e^{-x}}{e^x - e^{-x}}, \quad x \in \mathbb{R} \setminus \{0\} \\[2mm]
 & \hspace{0.2in} 5. \text{ Hyperbolic Secant: } \operatorname{sech}(x) := \frac{1}{\cosh(x)} = \frac{2}{e^x + e^{-x}}, \quad x \in \mathbb{R} \\[2mm]
 & \hspace{0.2in} 6. \text{ Hyperbolic Cosecant: } \operatorname{csch}(x) := \frac{1}{\sinh(x)} = \frac{2}{e^x - e^{-x}}, \quad x \in \mathbb{R} \setminus \{0\}
\end{align}
$$

##### Fundamental Hyperbolic Identities
From these exponential formulations emerge the fundamental structural identities:
$$
\begin{gather}
\cosh^2(x) - \sinh^2(x) = 1 \tag{19} \\[2mm]
1 - \tanh^2(x) = \operatorname{sech}^2(x) \tag{20} \\[2mm]
\coth^2(x) - 1 = \operatorname{csch}^2(x), \quad \forall x \neq 0 \tag{21} \\[2mm]
\sinh(x \pm y) = \sinh(x)\cosh(y) \pm \cosh(x)\sinh(y) \tag{22} \\[2mm]
\cosh(x \pm y) = \cosh(x)\cosh(y) \pm \sinh(x)\sinh(y) \tag{23} \\[2mm]
\tanh(x \pm y) = \frac{\tanh(x) \pm \tanh(y)}{1 \pm \tanh(x)\tanh(y)} \tag{24} \\[2mm]
\sinh(2x) = 2\sinh(x)\cosh(x), \quad \cosh(2x) = \cosh^2(x) + \sinh^2(x) = 2\cosh^2(x) - 1 \tag{25}
\end{gather}
$$

##### Derivatives of the Hyperbolic Functions
Differentiating the defining linear combinations of $e^x$ and $e^{-x}$ via the chain and quotient rules yields:
$$
\begin{gather}
\textbf{Proposition: Derivatives of the Six Hyperbolic Functions} \\[5mm]
\text{The derivatives of the six fundamental hyperbolic functions are given by:} \\[3.5mm]
\frac{d}{dx} \sinh(x) = \cosh(x) \tag{26} \\[2mm]
\frac{d}{dx} \cosh(x) = \sinh(x) \tag{27} \\[2mm]
\frac{d}{dx} \tanh(x) = \frac{1}{\cosh^2(x)} = \operatorname{sech}^2(x) = 1 - \tanh^2(x) \tag{28} \\[2mm]
\frac{d}{dx} \coth(x) = -\frac{1}{\sinh^2(x)} = -\operatorname{csch}^2(x) = 1 - \coth^2(x), \quad x \neq 0 \tag{29} \\[2mm]
\frac{d}{dx} \operatorname{sech}(x) = -\operatorname{sech}(x)\tanh(x) \tag{30} \\[2mm]
\frac{d}{dx} \operatorname{csch}(x) = -\operatorname{csch}(x)\coth(x), \quad x \neq 0 \tag{31}
\end{gather}
$$
(see [[Proof of Derivatives of the Six Hyperbolic Functions]])

### The Six Inverse Circular Trigonometric Functions
Because the circular functions $\sin, \cos, \dots$ are periodic, their functional inverses are constructed by restricting each mapping to its principal branch of strict monotonicity:
$$
\begin{align}
& \textbf{Definition: The Six Inverse Circular Functions} \\[5mm]
 & \hspace{0.2in} \text{The canonical inverse circular functions are defined as the principal branch inverses:} \\[2mm]
 & \hspace{0.2in} 1. \text{ Arcsine: } \arcsin: [-1, 1] \to \left[-\frac{\pi}{2}, \frac{\pi}{2}\right], \quad y = \arcsin(x) \iff x = \sin(y) \\[2mm]
 & \hspace{0.2in} 2. \text{ Arccosine: } \arccos: [-1, 1] \to [0, \pi], \quad y = \arccos(x) \iff x = \cos(y) \\[2mm]
 & \hspace{0.2in} 3. \text{ Arctangent: } \arctan: \mathbb{R} \to \left(-\frac{\pi}{2}, \frac{\pi}{2}\right), \quad y = \arctan(x) \iff x = \tan(y) \\[2mm]
 & \hspace{0.2in} 4. \text{ Arccotangent: } \operatorname{arccot}: \mathbb{R} \to (0, \pi), \quad y = \operatorname{arccot}(x) \iff x = \cot(y) \\[2mm]
 & \hspace{0.2in} 5. \text{ Arcsecant: } \operatorname{arcsec}: (-\infty, -1] \cup [1, \infty) \to \left[0, \frac{\pi}{2}\right) \cup \left(\frac{\pi}{2}, \pi\right], \quad y = \operatorname{arcsec}(x) \iff x = \sec(y) \\[2mm]
 & \hspace{0.2in} 6. \text{ Arccosecant: } \operatorname{arccsc}: (-\infty, -1] \cup [1, \infty) \to \left[-\frac{\pi}{2}, 0\right) \cup \left(0, \frac{\pi}{2}\right], \quad y = \operatorname{arccsc}(x) \iff x = \csc(y)
\end{align}
$$

##### Inverse Circular Identities
These principal inverses satisfy the standard complementarity and reciprocal relations:
$$
\begin{gather}
\arcsin(x) + \arccos(x) = \frac{\pi}{2}, \quad \forall x \in [-1, 1] \tag{32} \\[2mm]
\arctan(x) + \operatorname{arccot}(x) = \frac{\pi}{2}, \quad \forall x \in \mathbb{R} \tag{33} \\[2mm]
\operatorname{arcsec}(x) + \operatorname{arccsc}(x) = \frac{\pi}{2}, \quad \forall |x| \ge 1 \tag{34} \\[2mm]
\operatorname{arcsec}(x) = \arccos\left(\frac{1}{x}\right), \quad \operatorname{arccsc}(x) = \arcsin\left(\frac{1}{x}\right), \quad \forall |x| \ge 1 \tag{35}
\end{gather}
$$

##### Derivatives of the Inverse Circular Functions
Applying the Inverse Function Theorem to each principal branch produces the classic algebraic derivatives:
$$
\begin{gather}
\textbf{Proposition: Derivatives of the Inverse Circular Functions} \\[5mm]
\text{The derivatives of the six inverse circular functions on their interior domains are:} \\[3.5mm]
\frac{d}{dx} \arcsin(x) = \frac{1}{\sqrt{1 - x^2}}, \quad x \in (-1, 1) \tag{36} \\[2mm]
\frac{d}{dx} \arccos(x) = -\frac{1}{\sqrt{1 - x^2}}, \quad x \in (-1, 1) \tag{37} \\[2mm]
\frac{d}{dx} \arctan(x) = \frac{1}{1 + x^2}, \quad x \in \mathbb{R} \tag{38} \\[2mm]
\frac{d}{dx} \operatorname{arccot}(x) = -\frac{1}{1 + x^2}, \quad x \in \mathbb{R} \tag{39} \\[2mm]
\frac{d}{dx} \operatorname{arcsec}(x) = \frac{1}{|x|\sqrt{x^2 - 1}}, \quad |x| > 1 \tag{40} \\[2mm]
\frac{d}{dx} \operatorname{arccsc}(x) = -\frac{1}{|x|\sqrt{x^2 - 1}}, \quad |x| > 1 \tag{41}
\end{gather}
$$
(see [[Proof of Derivatives of the Inverse Circular Functions]])

### The Six Inverse Hyperbolic (Area) Functions
In contrast to circular functions, hyperbolic functions describe sectors of equilateral hyperbolas $x^2 - y^2 = 1$. The inverse hyperbolic functions are historically and conceptually designated with the prefix *ar-* (representing *area*, referencing the hyperbolic sector area):
$$
\begin{align}
& \textbf{Definition: The Six Inverse Hyperbolic Functions} \\[5mm]
 & \hspace{0.2in} \text{The canonical inverse hyperbolic functions are defined as the bijective branch inverses:} \\[2mm]
 & \hspace{0.2in} 1. \text{ Area Hyperbolic Sine: } \operatorname{arsinh}: \mathbb{R} \to \mathbb{R}, \quad y = \operatorname{arsinh}(x) \iff x = \sinh(y) \\[2mm]
 & \hspace{0.2in} 2. \text{ Area Hyperbolic Cosine: } \operatorname{arcosh}: [1, \infty) \to [0, \infty), \quad y = \operatorname{arcosh}(x) \iff x = \cosh(y), \; y \ge 0 \\[2mm]
 & \hspace{0.2in} 3. \text{ Area Hyperbolic Tangent: } \operatorname{artanh}: (-1, 1) \to \mathbb{R}, \quad y = \operatorname{artanh}(x) \iff x = \tanh(y) \\[2mm]
 & \hspace{0.2in} 4. \text{ Area Hyperbolic Cotangent: } \operatorname{arcoth}: (-\infty, -1) \cup (1, \infty) \to \mathbb{R} \setminus \{0\}, \quad y = \operatorname{arcoth}(x) \iff x = \coth(y) \\[2mm]
 & \hspace{0.2in} 5. \text{ Area Hyperbolic Secant: } \operatorname{arsech}: (0, 1] \to [0, \infty), \quad y = \operatorname{arsech}(x) \iff x = \operatorname{sech}(y), \; y \ge 0 \\[2mm]
 & \hspace{0.2in} 6. \text{ Area Hyperbolic Cosecant: } \operatorname{arcsch}: \mathbb{R} \setminus \{0\} \to \mathbb{R} \setminus \{0\}, \quad y = \operatorname{arcsch}(x) \iff x = \operatorname{csch}(y)
\end{align}
$$

>[!info]+ Remark: Purely Functional Definition of the Inverse Hyperbolic Mappings
>In the deductive curriculum of *The Quant's Bible*, integral-dependent transcendental primitives are introduced exclusively after the construction of the Riemann integral in [[Module 6 - Integration]]. Consequently, the inverse hyperbolic functions are defined strictly and self-containedly as the functional inverses of their bijective restrictions. Their derivatives are derived purely algebraically via the Inverse Function Theorem and the fundamental Pythagorean identity $\cosh^2(y) - \sinh^2(y) = 1$, preserving strict modular independence without premature circular dependencies.

##### Algebraic Identities of the Inverse Hyperbolic Functions
Through purely algebraic and functional manipulations, the inverse hyperbolic functions satisfy structural reciprocal relations analogous to their circular counterparts:
$$
\begin{gather}
\operatorname{arsech}(x) = \operatorname{arcosh}\left(\frac{1}{x}\right), \quad \forall x \in (0, 1] \tag{42} \\[2mm]
\operatorname{arcsch}(x) = \operatorname{arsinh}\left(\frac{1}{x}\right), \quad \forall x \in \mathbb{R} \setminus \{0\} \tag{43} \\[2mm]
\operatorname{arcoth}(x) = \operatorname{artanh}\left(\frac{1}{x}\right), \quad \forall |x| > 1 \tag{44} \\[2mm]
\operatorname{artanh}(x) \pm \operatorname{artanh}(y) = \operatorname{artanh}\left(\frac{x \pm y}{1 \pm xy}\right), \quad \forall x, y \in (-1, 1) \tag{45}
\end{gather}
$$

##### Derivatives of the Inverse Hyperbolic Functions
Applying the Inverse Function Theorem to the hyperbolic relations produces the inverse derivative formulas:
$$
\begin{gather}
\textbf{Proposition: Derivatives of the Inverse Hyperbolic Functions} \\[5mm]
\text{The derivatives of the six inverse hyperbolic functions on their interior domains are:} \\[3.5mm]
\frac{d}{dx} \operatorname{arsinh}(x) = \frac{1}{\sqrt{x^2 + 1}}, \quad x \in \mathbb{R} \tag{46} \\[2mm]
\frac{d}{dx} \operatorname{arcosh}(x) = \frac{1}{\sqrt{x^2 - 1}}, \quad x \in (1, \infty) \tag{47} \\[2mm]
\frac{d}{dx} \operatorname{artanh}(x) = \frac{1}{1 - x^2}, \quad x \in (-1, 1) \tag{48} \\[2mm]
\frac{d}{dx} \operatorname{arcoth}(x) = \frac{1}{1 - x^2} = -\frac{1}{x^2 - 1}, \quad |x| > 1 \tag{49} \\[2mm]
\frac{d}{dx} \operatorname{arsech}(x) = -\frac{1}{x\sqrt{1 - x^2}}, \quad x \in (0, 1) \tag{50} \\[2mm]
\frac{d}{dx} \operatorname{arcsch}(x) = -\frac{1}{|x|\sqrt{1 + x^2}}, \quad x \neq 0 \tag{51}
\end{gather}
$$
(see [[Proof of Derivatives of the Inverse Hyperbolic Functions]])

### Master Catalog of Elementary Derivatives (Part 2)
Continuing from the first part of the catalog established in [[Chapter 1 - Differentiable Functions|Chapter 1]], the operational rules and structural theorems established throughout this chapter yield the derivative formulas for the remaining fundamental elementary, hyperbolic, and inverse transcendental functions on their respective domains:
$$
\begin{gather}
\textbf{Theorem: Master Catalog of Elementary Derivatives (Part 2)} \\[5mm]
\text{The fundamental elementary, hyperbolic, and inverse transcendental functions admit} \\[2mm]
\text{the following derivative formulas on their domains:} \\[3.5mm]
\begin{align}
\text{10. Constant Function: } & \frac{d}{dx}(c) = 0 \quad (c \in \mathbb{R}, \ x \in \mathbb{R}). \\[2mm]
\text{11. Inverse Trigonometric Sine: } & \frac{d}{dx}\big(\arcsin(x)\big) = \frac{1}{\sqrt{1 - x^2}} \quad (x \in (-1, 1)). \\[2mm]
\text{12. Inverse Trigonometric Cosine: } & \frac{d}{dx}\big(\arccos(x)\big) = -\frac{1}{\sqrt{1 - x^2}} \quad (x \in (-1, 1)). \\[2mm]
\text{13. Inverse Trigonometric Tangent: } & \frac{d}{dx}\big(\arctan(x)\big) = \frac{1}{1 + x^2} \quad (x \in \mathbb{R}). \\[2mm]
\text{14. Inverse Trigonometric Cotangent: } & \frac{d}{dx}\big(\operatorname{arccot}(x)\big) = -\frac{1}{1 + x^2} \quad (x \in \mathbb{R}). \\[2mm]
\text{15. Inverse Trigonometric Secant: } & \frac{d}{dx}\big(\operatorname{arcsec}(x)\big) = \frac{1}{|x|\sqrt{x^2 - 1}} \quad (|x| > 1). \\[2mm]
\text{16. Inverse Trigonometric Cosecant: } & \frac{d}{dx}\big(\operatorname{arccsc}(x)\big) = -\frac{1}{|x|\sqrt{x^2 - 1}} \quad (|x| > 1). \\[2mm]
\text{17. Hyperbolic Sine: } & \frac{d}{dx}\big(\sinh(x)\big) = \cosh(x) \quad (x \in \mathbb{R}). \\[2mm]
\text{18. Hyperbolic Cosine: } & \frac{d}{dx}\big(\cosh(x)\big) = \sinh(x) \quad (x \in \mathbb{R}). \\[2mm]
\text{19. Hyperbolic Tangent: } & \frac{d}{dx}\big(\tanh(x)\big) = \operatorname{sech}^2(x) \quad (x \in \mathbb{R}). \\[2mm]
\text{20. Hyperbolic Cotangent: } & \frac{d}{dx}\big(\coth(x)\big) = -\operatorname{csch}^2(x) \quad (x \in \mathbb{R} \setminus \{0\}). \\[2mm]
\text{21. Hyperbolic Secant: } & \frac{d}{dx}\big(\operatorname{sech}(x)\big) = -\operatorname{sech}(x)\tanh(x) \quad (x \in \mathbb{R}). \\[2mm]
\text{22. Hyperbolic Cosecant: } & \frac{d}{dx}\big(\operatorname{csch}(x)\big) = -\operatorname{csch}(x)\coth(x) \quad (x \in \mathbb{R} \setminus \{0\}). \\[2mm]
\text{23. Area Hyperbolic Sine: } & \frac{d}{dx}\big(\operatorname{arsinh}(x)\big) = \frac{1}{\sqrt{x^2 + 1}} \quad (x \in \mathbb{R}). \\[2mm]
\text{24. Area Hyperbolic Cosine: } & \frac{d}{dx}\big(\operatorname{arcosh}(x)\big) = \frac{1}{\sqrt{x^2 - 1}} \quad (x \in (1, \infty)). \\[2mm]
\text{25. Area Hyperbolic Tangent: } & \frac{d}{dx}\big(\operatorname{artanh}(x)\big) = \frac{1}{1 - x^2} \quad (x \in (-1, 1)). \\[2mm]
\text{26. Area Hyperbolic Cotangent: } & \frac{d}{dx}\big(\operatorname{arcoth}(x)\big) = \frac{1}{1 - x^2} \quad (|x| > 1). \\[2mm]
\text{27. Area Hyperbolic Secant: } & \frac{d}{dx}\big(\operatorname{arsech}(x)\big) = -\frac{1}{x\sqrt{1 - x^2}} \quad (x \in (0, 1)). \\[2mm]
\text{28. Area Hyperbolic Cosecant: } & \frac{d}{dx}\big(\operatorname{arcsch}(x)\big) = -\frac{1}{|x|\sqrt{1 + x^2}} \quad (x \in \mathbb{R} \setminus \{0\}).
\end{align}
\end{gather}
$$
(see [[Proof of Derivatives of the Six Hyperbolic Functions]], [[Proof of Derivatives of the Inverse Circular Functions]], and [[Proof of Derivatives of the Inverse Hyperbolic Functions]])

---
# Implicit Differentiation, Parametric Curves, and Mechanical Invariants
In many analytical problems, the relationship between dependent and independent coordinates is specified not via an explicit formula $y = f(x)$, but through an algebraic constraint equation $F(x, y) = 0$ or via a shared temporal parameter $t \mapsto (x(t), y(t))$.

### Differentiation of Simple Implicit Functions
Suppose that $y = y(x)$ is a differentiable function satisfying an algebraic identity $F(x, y(x)) \equiv 0$ on an interval $I \subset \mathbb{R}$. Under appropriate smoothness conditions, differentiating both sides with respect to $x$ via the Chain Rule enables the determination of $y'(x)$ without resolving $y$ into an explicit functional form: 
$$
\begin{gather}
\textbf{Proposition: The Implicit Derivative Proposition} \\[5mm]
\text{Let } x = x(t) \text{ and } y = y(t) \text{ be differentiable functions defined on an open neighborhood } U(t_0). \\[2mm]
\text{Suppose that } x'(t_0) \neq 0. \text{ Then there exists a neighborhood } V(x_0) \text{ of } x_0 = x(t_0) \\[2mm]
\text{on which the inverse function } t = t(x) \text{ is defined and differentiable, and the composite} \\[2mm]
\text{implicit function } y(x) := y(t(x)) \text{ is differentiable at } x_0 \text{ with derivative:} \\[3.5mm]
y'_x(x_0) = \frac{y'_t(t_0)}{x'_t(t_0)}
\end{gather}
$$
(see [[Proof of The Implicit Derivative Proposition]])

### Parametric Differentiation and Kinematic Velocity
When a physical trajectory is represented parametrically as $\vec{r}(t) = (x(t), y(t))$, the spatial tangent slope of the orbit in Cartesian coordinates is given by the ratio of component velocities:
$$
\begin{gather}
\frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{\dot{y}(t)}{\dot{x}(t)} \tag{52}
\end{gather}
$$
provided that the horizontal velocity $\dot{x}(t)$ is non-zero. The parameter $t$ acts as a gauge, and the invariance of the first differential guarantees that the spatial slope is independent of the speed at which the curve is traversed.

### Conservation Laws in Celestial Mechanics: The Gravitational $N$-Body Problem
As an illustration of the Leibniz product rule and vector chain rule applied to system invariants, consider the motion of $n$ celestial bodies interacting solely through mutual Newtonian gravitation: 
$$
\begin{gather}
\textbf{Theorem: Conservation of Total Mechanical Energy in Gravitational Systems} \\[5mm]
\text{Consider } n \text{ point masses } m_1, m_2, \dots, m_n > 0 \text{ in } \mathbb{R}^3 \text{ with positions } \vec{r}_i(t) \text{ governed by Newton's law:} \\[3.5mm]
m_i \frac{d^2 \vec{r}_i}{dt^2} = -G \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \\[3.5mm]
\text{Define the total mechanical energy } E(t) := K(t) + U(t), \text{ where:} \\[2mm]
K(t) := \frac{1}{2} \sum_{i=1}^n m_i \left\|\frac{d\vec{r}_i}{dt}\right\|^2, \quad U(t) := -\frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|} \\[3.5mm]
\text{Then the total energy is an invariant first integral of the motion:} \\[2mm]
\frac{dE}{dt} \equiv 0 \implies E(t) = \text{constant}
\end{gather}
$$
(see [[Proof of Conservation of Total Mechanical Energy in Gravitational Systems]])

---

# Higher-Order Derivatives and Differential Regularity
A single derivative provides the best linear approximation to a mapping near an anchor point. To construct higher-order polynomial approximations (such as Taylor series) and examine geometric curvature, the process of differentiation must be iterated.

### Successive Derivatives and Higher-Order Differentials
Let $f: E \to \mathbb{R}$ be differentiable on an open interval $E \subseteq \mathbb{R}$. The derivative $f': E \to \mathbb{R}$ is itself a real-valued mapping. If $f'$ is differentiable at an anchor point $x_0 \in E$, its derivative is termed the *second derivative* of $f$ at $x_0$:
$$
\begin{gather}
f''(x_0) := \frac{d^2 f}{dx^2}(x_0) := (f')'(x_0) \tag{53}
\end{gather}
$$
Recursively, for any integer $n \in \mathbb{N}$, the $n$-th derivative $f^{(n)}(x_0)$ is defined by:
$$
\begin{gather}
f^{(n)}(x_0) := \big(f^{(n-1)}\big)'(x_0) \tag{54}
\end{gather}
$$
with the convention that $f^{(0)} := f$.

##### The Higher Differentials and Non-Invariance Under Composition
For an independent coordinate $x$, the increment $dx = h$ is a constant scalar that does not vary with $x$. Under this condition, the higher differentials are defined recursively by $d^n f(x) := d(d^{n-1} f(x))$, producing:
$$
\begin{gather}
d^n f(x) = f^{(n)}(x) \, (dx)^n \tag{55}
\end{gather}
$$

>[!warning]+ Warning: Failure of Invariance for Higher-Order Differentials
>While the first differential $df = f'(x) \, dx$ preserves its structural form under arbitrary coordinate transformations (first-order invariance), higher differentials do not enjoy this invariance.
>
>Suppose $z = f(y)$ and $y = g(x)$. Differentiating $dz = f'(y) \, dy$ via the product rule yields:
>$$
>\begin{gather}
>d^2 z = d\big(f'(y) \, dy\big) = f''(y) \, (dy)^2 + f'(y) \, d^2 y \tag{56}
>\end{gather}
>$$
>The second differential $d^2 z$ matches the classical form $f''(y) (dy)^2$ if and only if $d^2 y \equiv 0$, which occurs precisely when $y = g(x)$ is an affine linear function ($g''(x) = 0$). For non-linear transformations, the second-order term $f'(y) \, d^2 y$ introduces an inertial acceleration component that distorts the pure differential form.

### The General Leibniz Formula for Product Derivatives
Determining the $n$-th derivative of a product of two smooth functions yields a structural identity with the binomial expansion:

$$
\begin{gather}
\textbf{Theorem: The General Leibniz Rule} \\[5mm]
\text{Let } u, v: E \to \mathbb{R} \text{ be } n\text{-times differentiable functions on an open set } E \subseteq \mathbb{R}. \\[2mm]
\text{Then their product } (uv): E \to \mathbb{R} \text{ is } n\text{-times differentiable on } E, \\[2mm]
\text{and its } n\text{-th derivative satisfies the binomial expansion:} \\[3.5mm]
(uv)^{(n)}(x) = \sum_{k=0}^n \binom{n}{k} u^{(k)}(x) \, v^{(n-k)}(x)
\end{gather}
$$
(see [[Proof of The General Leibniz Rule]])

##### The Inversion Duality Identity for Higher Derivatives
A non-trivial application of the Leibniz formula emerges when examining the behavior of smooth functions under modular coordinate inversion $x \mapsto \frac{1}{x}$:

$$
\begin{gather}
\textbf{Proposition: The Inversion Duality Formula} \\[5mm]
\text{Let } f \in C^\infty(\mathbb{R}). \text{ Then for all non-zero coordinates } x \neq 0 \text{ and all } n \in \mathbb{N}: \\[3.5mm]
\frac{1}{x^{n+1}} f^{(n)}\left(\frac{1}{x}\right) = (-1)^n \frac{d^n}{dx^n} \left(x^{n-1} f\left(\frac{1}{x}\right)\right)
\end{gather}
$$
(see [[Proof of The Inversion Duality Formula]])

### Jet Reconstruction and Taylor-Hermite Polynomial Interpolation
A fundamental question in polynomial approximation is whether a set of derivative specifications at an anchor point uniquely characterizes a polynomial:
$$
\begin{gather}
\textbf{Proposition: Polynomial Reconstruction from Jet Coordinates} \\[5mm]
\text{Let } x_0 \in \mathbb{R}, \text{ and let } (\alpha_0, \alpha_1, \dots, \alpha_n) \in \mathbb{R}^{n+1} \text{ be an arbitrary sequence of real coefficients.} \\[2mm]
\text{Then there exists a unique polynomial } P_n(x) \text{ of degree at most } n \text{ whose derivatives at } x_0 \text{ satisfy:} \\[3.5mm]
P_n^{(k)}(x_0) = \alpha_k, \quad \forall k \in \{0, 1, \dots, n\} \\[3.5mm]
\text{This unique polynomial is given explicitly by the Taylor expansion:} \\[2mm]
P_n(x) = \sum_{k=0}^n \frac{\alpha_k}{k!} (x - x_0)^k
\end{gather}
$$
(see [[Proof of Polynomial Reconstruction from Jet Coordinates]])

### The Smoothness Hierarchy and Pathological Classes
The collection of real-valued functions defined on an interval $I$ forms a hierarchy of nested function spaces:
$$
\begin{gather}
C^0(I) \supset D^1(I) \supset C^1(I) \supset \cdots \supset C^k(I) \supset \cdots \supset C^\infty(I) \supset C^\omega(I) \tag{57}
\end{gather}
$$
where $C^0$ denotes continuous functions, $D^1$ denotes differentiable functions, $C^k$ denotes functions whose $k$-th derivative is continuous, $C^\infty$ denotes smooth functions possessing derivatives of all orders, and $C^\omega$ denotes real-analytic functions that coincide locally with their Taylor power series.

Every inclusion in the sequence of step 57 is strict.

##### Pathological Class $D^1 \setminus C^1$: Differentiability Without Derivative Continuity
In elementary analysis, it is frequently presumed that if a function possesses a derivative everywhere, that derivative must be continuous. This intuition is false:
$$
\begin{gather}
\textbf{Proposition: Differentiability Without Derivative Continuity} \\[5mm]
\text{Consider the function } f: \mathbb{R} \to \mathbb{R} \text{ defined by:} \\[2mm]
f(x) = \begin{cases} x^2 \sin\left(\frac{1}{x}\right) & \text{if } x \neq 0 \\ 0 & \text{if } x = 0 \end{cases} \\[3.5mm]
\text{Then } f \text{ is differentiable at every point } x \in \mathbb{R}, \text{ with derivative:} \\[2mm]
f'(x) = \begin{cases} 2x \sin\left(\frac{1}{x}\right) - \cos\left(\frac{1}{x}\right) & \text{if } x \neq 0 \\ 0 & \text{if } x = 0 \end{cases} \\[3.5mm]
\text{However, the derivative mapping } f': \mathbb{R} \to \mathbb{R} \text{ is discontinuous at } x = 0.
\end{gather}
$$
(see [[Proof of Differentiability Without Derivative Continuity]])

As $x \to 0$, the factor $2x \sin(1/x)$ vanishes, but the term $\cos(1/x)$ oscillates between $-1$ and $+1$ with infinite frequency. Consequently, $\lim_{x \to 0} f'(x)$ does not exist, establishing that $f \in D^1(\mathbb{R}) \setminus C^1(\mathbb{R})$.

##### The Cauchy Flatness Phenomenon and Non-Analytic Smooth Functions
Even more striking is the divide between infinitely differentiable functions ($C^\infty$) and real-analytic functions ($C^\omega$). Augustin-Louis Cauchy discovered that a smooth function can be completely flat at an anchor point without being zero elsewhere:
$$
\begin{gather}
\textbf{Theorem: The Cauchy Flatness Theorem} \\[5mm]
\text{Consider the function } f: \mathbb{R} \to \mathbb{R} \text{ defined by:} \\[2mm]
f(x) = \begin{cases} \exp\left(-\frac{1}{x^2}\right) & \text{if } x \neq 0 \\ 0 & \text{if } x = 0 \end{cases} \\[3.5mm]
\text{Then } f \in C^\infty(\mathbb{R}), \text{ and every derivative of } f \text{ vanishes at the origin:} \\[2mm]
f^{(n)}(0) = 0, \quad \forall n \in \mathbb{N}
\end{gather}
$$
(see [[Proof of The Cauchy Flatness Theorem]])

Because every derivative vanishes at the origin, the Taylor series of $f$ centered at $x_0 = 0$ is identically zero: $\sum_{n=0}^\infty \frac{f^{(n)}(0)}{n!} x^n \equiv 0$. Yet, for all $x \neq 0$, $f(x) = \exp(-1/x^2) > 0$. The Taylor series converges everywhere, but it fails to represent the function at any point outside the origin.

##### Partition-of-Unity Bump Functions
Translating and composing Cauchy's flat function yields smooth bump functions with compact support:
$$
\begin{gather}
\textbf{Corollary: Existence of Compactly Supported Smooth Bump Functions} \\[5mm]
\text{The function } \Psi: \mathbb{R} \to \mathbb{R} \text{ defined by:} \\[2mm]
\Psi(x) = \begin{cases} \exp\left(-\frac{1}{(1+x)^2} - \frac{1}{(1-x)^2}\right) & \text{if } x \in (-1, 1) \\ 0 & \text{if } |x| \ge 1 \end{cases} \\[3.5mm]
\text{is infinitely differentiable on the entire real line } (\Psi \in C^\infty(\mathbb{R})) \text{ and satisfies } \operatorname{supp}(\Psi) = [-1, 1].
\end{gather}
$$
(see [[Proof of Existence of Compactly Supported Smooth Bump Functions]])

Such functions serve as the foundational building blocks for smooth partitions of unity, cutoff operators, and mollifiers in distribution theory and differential topology.

---
# Visualizations of Transcendental Geometries

### Tangent Line Reflection Across the Diagonal $y = x$
The Inverse Function Theorem states that the graph of an inverse function $f^{-1}$ is obtained by reflecting the graph of $f$ across the identity line $y = x$. At corresponding points $(x_0, y_0)$ and $(y_0, x_0)$, the tangent slopes are reciprocal: $\tan(\beta) = \frac{1}{\tan(\alpha)}$: 
```easy-tikz
title $\text{Geometric Reciprocity of Inverse Function Tangents}$
xlabel $x$
ylabel $y$
show x from -0.5 to 6.5 and y from -0.5 to 6.5
axes on the edges
size 12 x 8
plot f(x) = 0.5*x^2 + 0.5, from x = 0.2 to 3.2, in cyan, very thick
plot finv(x) = sqrt(max(0, 2*(x - 0.5))), from x = 0.51 to 5.8, in orange, very thick
plot diag(x) = x, from x = 0 to 6.0, in orchid, dashed
plot tan1(x) = 1.0 + 1.0*(x - 1.0), from x = 0.0 to 3.5, in green, thick
plot tan2(x) = 1.0 + 1.0*(x - 1.0), from x = 0.0 to 3.5, in green, thick
draw a line from (1.0, 0) to (1.0, 1.0) in gray, dashed
draw a line from (0, 1.0) to (1.0, 1.0) in gray, dashed
raw tool {"type":"points","name":"P1","color":"green","points":"(1.0, 1.0);","size":"large"}
write "$y = x$" at (5.5, 5.8) in orchid, right
write "$y= f(x)$" at (2.4, 4.5) in teal, left
write "$y = f^{-1}(x)$" at (5.3, 2.65) in orange, below
write "$(x_0, y_0)$" at (1.8, 2.8) in white, left
write "$(y_0, x_0)$" at (2.8, 1.7) in white, right
write "$\\text{Slope: } m$" at (0.8, 1.6) in green, left
```

### The Geometry of the Hyperbolic Sine and Cosine
The hyperbolic sine and cosine govern coordinates on equilateral hyperbolas $x^2 - y^2 = 1$ in identical fashion to circular coordinates on the unit circle $x^2 + y^2 = 1$. The hyperbolic cosine exhibits even symmetry, while the hyperbolic sine exhibits odd symmetry: 
```easy-tikz
title $\text{Profiles of the Hyperbolic Functions } \sinh(x) \text{ and } \cosh(x)$
xlabel $x$
ylabel $y$
show x from -3.5 to 3.5 and y from -4.0 to 5.5
axes on the edges
size 12 x 8
plot ch(x) = 0.5*(exp(x) + exp(-x)), from x = -2.3 to 2.3, in cyan, very thick
plot sh(x) = 0.5*(exp(x) - exp(-x)), from x = -2.3 to 2.3, in orange, very thick
plot asymp1(x) = 0.5*exp(x), from x = -1.0 to 2.4, in orchid, dashed
plot asymp2(x) = 0.5*exp(-x), from x = -2.4 to 1.0, in orchid, dashed
draw a line from (-3.0, 1.0) to (3.0, 1.0) in gray, dashed
raw tool {"type":"points","name":"Apex","points":"(0.0, 1.0);","size":"large"}
write "$y = \cosh(x)$" at (1.7, 3.8) in cyan, left
write "$y = \sinh(x)$" at (1.8, 2.2) in orange, right
write "$y = \frac{1}{2}e^x$" at (2.3, 4.8) in orchid, right
write "$y = \frac{1}{2}e^{-x}$" at (-2.3, 4.8) in orchid, left
write "$(0, 1)$" at (0.0, 0.6) in white, center
write "$\cosh^2(x) - \sinh^2(x) = 1$" at (0.0, -3.2) in green, center
```

### The Cauchy Flatness Curve
Cauchy's function $f(x) = \exp(-1/x^2)$ provides visual proof of infinite tangency: as the curve approaches the origin, its decay is faster than every power monomial $x^n$, forcing all successive derivatives to zero and welding the curve seamlessly to the horizontal axis: 
```easy-tikz
title $\text{The Cauchy Flat Function } f(x) = \exp(-1/x^2)$
xlabel $x$
ylabel $y$
show x from -3.5 to 3.5 and y from -0.5 to 1.5
axes on the edges
size 12 x 8
plot c(x) = (abs(x) < 0.05 ? 0.0 : exp(-1.0/(x^2))), from x = -3.2 to 3.2, in cyan, very thick
plot flat(x) = 0.0, from x = -1.2 to 1.2, in green, thick
draw a line from (-3.0, 1.0) to (3.0, 1.0) in gray, dashed
raw tool {"type":"points","name":"Origin","points":"(0.0, 0.0);","size":"large"}
write "$y = \exp\left(-\frac{1}{x^2}\right)$" at (2.0, 1.15) in cyan, right
write "$\\text{Asymptote } y = 1$" at (-1, 1.13) in gray, left
write "$\text{Infinitely Flat Apex: } f^{(n)}(0) = 0, \; \forall n \in \mathbb{N}$" at (0.0, -0.3) in green, center
write "$(0,0)$" at (0.0, 0.15) in white, center
```

---
# Applications of the Basic Rules of Differentiation

### Quantitative Finance: Bond Convexity and Second-Order Price Sensitivities
In fixed-income portfolio management, the price sensitivity of a bond to shifts in interest rate yield $y$ is described locally by its Taylor polynomial. Let $P(y) = \sum_{k=1}^m C_k (1 + y)^{-t_k}$ denote the price of a bond paying cash flows $C_k$ at future maturity dates $t_k$.

Applying the rational power rule and linearity established in this chapter, the first derivative of the price with respect to yield is:
$$
\begin{gather}
\frac{dP}{dy} = -\sum_{k=1}^m t_k C_k (1 + y)^{-(t_k + 1)} = -\frac{1}{1 + y} \sum_{k=1}^m t_k C_k (1 + y)^{-t_k} \tag{58}
\end{gather}
$$
The *Modified Duration* $D^* := -\frac{1}{P}\frac{dP}{dy}$ captures the first-order linear approximation of the price swing. However, for non-infinitesimal interest rate shocks, the linear approximation introduces systematic pricing error due to the non-linear curvature of the discounting function.

Applying the differentiation operator a second time via the power rule produces the second-order derivative:
$$
\begin{gather}
\frac{d^2 P}{dy^2} = \sum_{k=1}^m t_k (t_k + 1) C_k (1 + y)^{-(t_k + 2)} > 0 \tag{59}
\end{gather}
$$
The financial metric governing this curvature is the *Dollar Convexity*, normalized per dollar of investment as:
$$
\begin{gather}
C := \frac{1}{P} \frac{d^2 P}{dy^2} = \frac{1}{P (1 + y)^2} \sum_{k=1}^m t_k (t_k + 1) \frac{C_k}{(1 + y)^{t_k}} \tag{60}
\end{gather}
$$
By virtue of the second-order differential expansion $dP = \frac{dP}{dy} \Delta y + \frac{1}{2} \frac{d^2 P}{dy^2} (\Delta y)^2 + o\big((\Delta y)^2\big)$, the percentage return on the bond under a yield perturbation $\Delta y$ satisfies:
$$
\begin{gather}
\frac{\Delta P}{P} \approx -D^* \, \Delta y + \frac{1}{2} C \, (\Delta y)^2 \tag{61}
\end{gather}
$$
Because the second derivative is strictly positive ($C > 0$), bond prices are strictly convex functions of yield. The second-order term $\frac{1}{2} C (\Delta y)^2$ is always positive, demonstrating that a bond's price rises more when yields fall than it declines when yields rise by an identical magnitude. Quantitative risk desks utilize this second differential to construct gamma-neutral and convexity-hedged asset allocations.

### Classical Mechanics: Relativistic Rapidity and Hyperbolic Velocity Composition
In special relativity, the velocity $u$ of a particle moving along a spatial axis cannot exceed the speed of light $c$. When composing velocities between inertial reference frames moving at relative speed $v$, Newtonian Galilean addition $u' = u + v$ fails. Instead, velocities combine according to the Einstein addition formula:
$$
\begin{gather}
u' = \frac{u + v}{1 + \frac{uv}{c^2}} \tag{62}
\end{gather}
$$
The non-linear structure of step 62 is identical to the addition identity for the hyperbolic tangent established in step 24:
$$
\begin{gather}
\tanh(\theta_1 + \theta_2) = \frac{\tanh(\theta_1) + \tanh(\theta_2)}{1 + \tanh(\theta_1)\tanh(\theta_2)} \tag{63}
\end{gather}
$$
By defining the dimensionless velocity $\beta := \frac{u}{c} \in (-1, 1)$, one introduces the *relativistic rapidity* $\theta$ via the inverse hyperbolic tangent mapping:
$$
\begin{gather}
\theta := \operatorname{artanh}(\beta) = \operatorname{artanh}\left(\frac{u}{c}\right) \tag{64}
\end{gather}
$$
Under this functional transformation, the non-linear velocity composition law of step 62 linearizes completely:
$$
\begin{gather}
\theta' = \theta_u + \theta_v \tag{65}
\end{gather}
$$
Differentiating rapidity with respect to velocity using the derivative of the inverse hyperbolic tangent (step 48) and the Chain Rule yields:
$$
\begin{gather}
\frac{d\theta}{du} = \frac{d}{du}\operatorname{artanh}\left(\frac{u}{c}\right) = \frac{1}{1 - \left(\frac{u}{c}\right)^2} \cdot \frac{1}{c} = \frac{c}{c^2 - u^2} \tag{66}
\end{gather}
$$
Evaluating the acceleration in rapidity coordinates reveals that while spatial acceleration $a = \frac{du}{dt}$ must decay to zero as $u \to c$ under a constant applied force, the rate of change of rapidity $\frac{d\theta}{d\tau}$ with respect to proper time $\tau$ remains invariant, reflecting constant proper force.

### Fluid Mechanics: Laminar Shear Stress and Invariant Vorticity in Poiseuille Flow
Consider the steady laminar flow of an incompressible viscous Newtonian fluid between two infinite parallel plates separated by a distance $2h$, driven by an axial pressure gradient $-\frac{dP}{dx} = G > 0$. The fluid velocity $u(y)$ parallel to the channel axis depends exclusively on the transverse coordinate $y \in [-h, h]$.

The velocity field satisfies the second-order Navier-Stokes differential equation:
$$
\begin{gather}
\mu \frac{d^2 u}{dy^2} = -G \tag{67}
\end{gather}
$$
subject to the no-slip boundary conditions $u(-h) = u(h) = 0$, where $\mu > 0$ represents the dynamic shear viscosity. 

Integrating step 67 produces the parabolic plane Poiseuille profile:
$$
\begin{gather}
u(y) = \frac{G}{2\mu} \big(h^2 - y^2\big) \tag{68}
\end{gather}
$$
Applying the monomial differentiation rule to step 68 yields the transverse velocity gradient:
$$
\begin{gather}
\frac{du}{dy} = -\frac{G}{\mu} y \tag{69}
\end{gather}
$$
According to Newton's law of viscosity, the local shear stress $\tau(y)$ exerted between adjacent fluid layers is proportional to the first derivative of velocity:
$$
\begin{gather}
\tau(y) = \mu \frac{du}{dy} = -G y \tag{70}
\end{gather}
$$
The shear stress varies linearly across the channel, vanishing at the central streamline $y = 0$ and attaining maximum shear magnitude $|\tau| = Gh$ at the solid boundaries. 

The fluid *vorticity* $\vec{\omega} := \nabla \times \vec{v}$ measures the local rate of angular rotation of fluid elements. For plane flow, the vorticity vector is oriented along the binormal axis $z$, with magnitude:
$$
\begin{gather}
\omega_z(y) = -\frac{du}{dy} = \frac{G}{\mu} y \tag{71}
\end{gather}
$$
Differentiating the vorticity once more yields the fluid rate-of-strain curvature:
$$
\begin{gather}
\frac{d\omega_z}{dy} = -\frac{d^2 u}{dy^2} = \frac{G}{\mu} = \text{constant} \tag{72}
\end{gather}
$$
The constancy of the second derivative of the velocity field in step 72 signifies that the shear deformation rate across adjacent lamina is uniform throughout the channel, a foundational principle in hydrodynamic lubrication and pipeline transport design.
