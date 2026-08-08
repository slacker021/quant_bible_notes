---
dg-publish: true
---
Let $X, Y, Z,$ and $W$ be sets, and let $f: X \to Y$, $g: Y \to Z$, and $h: Z \to W$ be mappings.

# Domain and Codomain Agreement
Consider the composite mapping $g \circ f$. Because $f: X \to Y$ and $g: Y \to Z$, the composition $g \circ f$ is a well-defined function mapping $g \circ f: X \to Z$. Composing this resulting function with $h: Z \to W$ yields
$$
\begin{gather}
h \circ (g \circ f) : X \to W \tag{1}
\end{gather}
$$
Similarly, consider the composite mapping $h \circ g$. Because $g: Y \to Z$ and $h: Z \to W$, the composition $h \circ g$ is a well-defined function mapping $h \circ g: Y \to W$. Composing $f: X \to Y$ with this resulting function yields
$$
\begin{gather}
(h \circ g) \circ f : X \to W \tag{2}
\end{gather}
$$
Both composite mappings $h \circ (g \circ f)$ and $(h \circ g) \circ f$ share the common domain $X$ and the common codomain $W$.

# Pointwise Evaluation
Let $x \in X$ be an arbitrary element of the domain. Evaluating the left-hand composite mapping at $x$ yields: 
$$
\begin{aligned}
(h \circ (g \circ f))(x) &= h\big((g \circ f)(x)\big) \\
&= h\big(g(f(x))\big)
\end{aligned} \tag{3}
$$
Evaluating the right-hand composite mapping at $x$ yields: 
$$
\begin{aligned}
((h \circ g) \circ f)(x) &= (h \circ g)\big(f(x)\big) \\
&= h\big(g(f(x))\big)
\end{aligned} \tag{4}
$$
Because $(h \circ (g \circ f))(x) = ((h \circ g) \circ f)(x) = h(g(f(x)))$ for every $x \in X$, and both composite functions possess identical domains and codomains, the Principle of Extensionality for functions confirms that:
$$
\begin{gather}
h \circ (g \circ f) = (h \circ g) \circ f \tag{5}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
