---
dg-publish: true
---
Let $X$ and $Y$ be non-empty sets, and let $f: X \to Y$ be a mapping. Let $\text{id}_X: X \to X$ and $\text{id}_Y: Y \to Y$ denote the identity mappings defined by $\text{id}_X(x) = x$ for all $x \in X$ and $\text{id}_Y(y) = y$ for all $y \in Y$. An inverse mapping of $f$ is defined as a mapping $g: Y \to X$ satisfying the commutative identities:
$$
\begin{gather}
(g \circ f)(x) = \text{id}_X(x) = x, \quad \forall x \in X \tag{1} \\[2mm]
(f \circ g)(y) = \text{id}_Y(y) = y, \quad \forall y \in Y \tag{2}
\end{gather}
$$

# Existence
Assume that the mapping $f: X \to Y$ is bijective. By definition, $f$ satisfies two independent structural properties:
1. Surjectivity: For every element $y \in Y$, there exists an element $x \in X$ such that $f(x) = y$.
2. Injectivity: For all elements $x_1, x_2 \in X$, the equality $f(x_1) = f(x_2)$ implies $x_1 = x_2$.

To construct the candidate inverse mapping $g: Y \to X$, assign to each element $y \in Y$ the pre-image set:
$$
\begin{gather}
f^{-1}(\{y\}) = \{x \in X \mid f(x) = y\} \tag{3}
\end{gather}
$$
By the surjectivity of $f$, the set $f^{-1}(\{y\})$ is non-empty for every $y \in Y$, guaranteeing the existence of at least one candidate element $x \in X$ such that $f(x) = y$.

To establish that $g$ defines a valid function, the assigned element must be unique for each $y \in Y$. Suppose there exist two elements $x_1, x_2 \in X$ such that:
$$
\begin{gather}
f(x_1) = y \quad \wedge \quad f(x_2) = y \tag{4}
\end{gather}
$$
From step 4, it follows that $f(x_1) = f(x_2)$. Because $f$ is injective, this equality necessitates:
$$
\begin{gather}
x_1 = x_2 \tag{5}
\end{gather}
$$
Thus, each $y \in Y$ corresponds to a unique element $x \in X$ satisfying $f(x) = y$. Defining $g(y) = x$ where $f(x) = y$ yields a single-valued, well-defined mapping $g: Y \to X$.

Evaluating the composite mapping $g \circ f$ upon an arbitrary element $x \in X$:
$$
\begin{gather}
(g \circ f)(x) = g(f(x)) \tag{6}
\end{gather}
$$
Setting $y = f(x)$, the construction of $g$ mandates that $g(y)$ is the unique element mapped to $y$ by $f$, which is $x$. Substituting this value into step 6 gives:
$$
\begin{gather}
g(f(x)) = x = \text{id}_X(x) \tag{7}
\end{gather}
$$
Because step 7 holds for every $x \in X$, the relation $g \circ f = \text{id}_X$ is verified.

Similarly, evaluating the composite mapping $f \circ g$ upon an arbitrary element $y \in Y$:
$$
\begin{gather}
(f \circ g)(y) = f(g(y)) \tag{8}
\end{gather}
$$
By definition of $g$, the element $x = g(y)$ satisfies $f(x) = y$. Substituting $x$ into step 8 produces
$$
\begin{gather}
f(g(y)) = f(x) = y = \text{id}_Y(y) \tag{9}
\end{gather}
$$
Because step 9 holds for every $y \in Y$, the relation $f \circ g = \text{id}_Y$ is verified. Hence, the mapping $g: Y \to X$ is an inverse mapping of $f$.

---
# Uniqueness
Suppose that there exist two mappings $g_1: Y \to X$ and $g_2: Y \to X$ that both satisfy the inverse criteria with respect to $f$:
$$
\begin{gather}
g_1 \circ f = \text{id}_X, \quad f \circ g_1 = \text{id}_Y \tag{10} \\[2mm]
g_2 \circ f = \text{id}_X, \quad f \circ g_2 = \text{id}_Y \tag{11}
\end{gather}
$$
Utilizing the identity property of mappings alongside the associativity of functional composition:
$$
\begin{gather}
g_1 = g_1 \circ \text{id}_Y = g_1 \circ (f \circ g_2) = (g_1 \circ f) \circ g_2 = \text{id}_X \circ g_2 = g_2 \tag{12}
\end{gather}
$$
Because $g_1 = g_2$, any inverse mapping of $f$ is unique, canonically designated as $f^{-1}: Y \to X$.


---
# Fact 3: Necessity of Bijectivity for the Existence of an Inverse Mapping
Assume that there exists a mapping $g: Y \to X$ satisfying $g \circ f = \text{id}_X$ and $f \circ g = \text{id}_Y$.

To establish injectivity, let $x_1, x_2 \in X$ satisfy:
$$
\begin{gather}
f(x_1) = f(x_2) \tag{13}
\end{gather}
$$
Applying the mapping $g$ to both sides of step 13:
$$
\begin{gather}
g(f(x_1)) = g(f(x_2)) \tag{14}
\end{gather}
$$
Rewriting step 14 through functional composition and utilizing $g \circ f = \text{id}_X$:
$$
\begin{gather}
(g \circ f)(x_1) = (g \circ f)(x_2) \implies \text{id}_X(x_1) = \text{id}_X(x_2) \implies x_1 = x_2 \tag{15}
\end{gather}
$$
Thus, $f$ is injective.

To establish surjectivity, let $y \in Y$ be an arbitrary element. Applying the condition $f \circ g = \text{id}_Y$ to $y$:
$$
\begin{gather}
(f \circ g)(y) = \text{id}_Y(y) = y \implies f(g(y)) = y \tag{16}
\end{gather}
$$
Defining the element $x \in X$ as $x = g(y)$, step (16) confirms that $f(x) = y$. Thus, every element $y \in Y$ possesses an antecedent $x \in X$ under $f$, confirming that $f$ is surjective.

Because $f$ is both injective and surjective, $f$ is bijective.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
