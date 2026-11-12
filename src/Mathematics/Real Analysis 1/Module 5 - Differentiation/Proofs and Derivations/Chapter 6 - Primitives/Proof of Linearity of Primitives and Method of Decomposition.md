---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $f, g: I \to \mathbb{R}$ be two real-valued functions. Suppose that $f$ and $g$ each admit primitives on $I$, denoted by $F, G: I \to \mathbb{R}$ respectively.

By the definition of a primitive, $F$ and $G$ are differentiable on $I$ and satisfy:
$$
\begin{gather}
F'(x) = f(x) \quad \text{and} \quad G'(x) = g(x) \quad \forall x \in I \tag{1}
\end{gather}
$$

Let $\alpha, \beta \in \mathbb{R}$ be arbitrary real scalars.

---
# Proposition 1 
Define the linear combination function $H: I \to \mathbb{R}$ by:
$$
\begin{gather}
H(x) := \alpha F(x) + \beta G(x), \quad \forall x \in I \tag{2}
\end{gather}
$$

Because $F$ and $G$ are differentiable on $I$ and the differentiation operator is linear over the field $\mathbb{R}$ (as established in [[Proof of The Linearity of Differentiation|The Linearity of Differentiation]]), the function $H$ is differentiable at every point $x \in I$.

Evaluating the derivative of $H$ at an arbitrary point $x \in I$ yields:
$$
\begin{gather}
H'(x) = \frac{d}{dx} \big( \alpha F(x) + \beta G(x) \big) = \alpha F'(x) + \beta G'(x) \tag{3}
\end{gather}
$$

Substituting the primitive relationships from step 1 into step 3 produces:
$$
\begin{gather}
H'(x) = \alpha f(x) + \beta g(x) \quad \forall x \in I \tag{4}
\end{gather}
$$

Step 4 proves that $H = \alpha F + \beta G$ is a primitive of the linear combination $(\alpha f + \beta g)$ on the interval $I$. 

In terms of affine indefinite integral equivalence classes:
$$
\begin{gather}
\int \big(\alpha f(x) + \beta g(x)\big) \, dx = \alpha \int f(x) \, dx + \beta \int g(x) \, dx \tag{5}
\end{gather}
$$
meaning that every member of the set on the left can be represented as a sum of members from the scaled sets on the right, and vice versa.

---
# Proposition 2
By induction, let $\{f_k\}_{k=1}^m$ be a finite collection of functions on $I$ admitting primitives $\{F_k\}_{k=1}^m$, and let $\{c_k\}_{k=1}^m \subset \mathbb{R}$ be scalars.

Then the linear combination $\sum_{k=1}^m c_k f_k$ admits the primitive $\sum_{k=1}^m c_k F_k$ on $I$:
$$
\begin{gather}
\frac{d}{dx} \left( \sum_{k=1}^m c_k F_k(x) \right) = \sum_{k=1}^m c_k F'_k(x) = \sum_{k=1}^m c_k f_k(x) \tag{6}
\end{gather}
$$
and consequently:
$$
\begin{gather}
\int \left( \sum_{k=1}^m c_k f_k(x) \right) dx = \sum_{k=1}^m c_k \int f_k(x) \, dx \tag{7}
\end{gather}
$$

This algebraic identity validates the *method of decomposition*: whenever an integrand can be decomposed as a finite linear combination of terms whose antiderivatives are known, the primitive of the original function is obtained by summing the corresponding scaled primitives.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
