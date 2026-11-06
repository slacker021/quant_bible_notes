---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $f: I \to \mathbb{R}$ be continuous and strictly monotonic on $I$. 

Without loss of generality, assume that $f$ is strictly increasing. 

**Bijectivity and Existence of the Inverse Mapping:**
Let $x_1, x_2 \in I$ with $x_1 \ne x_2$. By trichotomy, either $x_1 < x_2$ or $x_2 < x_1$. 

Because $f$ is strictly increasing:
$$
\begin{gather}
x_1 < x_2 \implies f(x_1) < f(x_2) \quad \text{and} \quad x_2 < x_1 \implies f(x_2) < f(x_1) \tag{1}
\end{gather}
$$

In either case, $f(x_1) \ne f(x_2)$, which proves that $f$ is strictly injective on $I$. 

Let $J := f(I)$ denote the direct image of $I$ under $f$. By construction, $f: I \to J$ is surjective. 

Because $f$ is both injective and surjective, it is a bijection. Consequently, the inverse mapping $f^{-1}: J \to I$ exists uniquely:
$$
\begin{gather}
\forall y \in J, \quad f(f^{-1}(y)) = y \quad \text{and} \quad \forall x \in I, \quad f^{-1}(f(x)) = x \tag{2}
\end{gather}
$$

**Strict Monotonicity of $f^{-1}$:**
Let $y_1, y_2 \in J$ with $y_1 < y_2$. 

Define the unique preimage points:
$$
\begin{gather}
x_1 := f^{-1}(y_1) \in I \quad \text{and} \quad x_2 := f^{-1}(y_2) \in I \tag{3}
\end{gather}
$$

Suppose, for the sake of contradiction, that $x_1 \ge x_2$. 

Because $f$ is strictly increasing:
* If $x_1 = x_2$, then $f(x_1) = f(x_2) \implies y_1 = y_2$, contradicting $y_1 < y_2$.
* If $x_1 > x_2$, then $f(x_1) > f(x_2) \implies y_1 > y_2$, contradicting $y_1 < y_2$.

Consequently, $x_1 < x_2$, which means:
$$
\begin{gather}
f^{-1}(y_1) < f^{-1}(y_2) \tag{4}
\end{gather}
$$

Thus, the inverse mapping $f^{-1}: J \to I$ is strictly increasing on $J$.

**Continuity of $f^{-1}$:**
Because $f$ is continuous on the interval $I$, the [[Proof of the Image of an Interval under Continuous Mappings]] establishes that the codomain $J = f(I)$ is an interval. 

Now consider the inverse function $f^{-1}: J \to \mathbb{R}$. 

By the result of step 4, $f^{-1}$ is strictly monotonic on the interval $J$. 

Evaluating the direct image of $J$ under $f^{-1}$:
$$
\begin{gather}
f^{-1}(J) = f^{-1}(f(I)) = I \tag{5}
\end{gather}
$$

By hypothesis, the set $I$ is an interval. 

Applying the [[Proof of Strictly Monotonic Continuous Bijections]] to the mapping $f^{-1}$: because $f^{-1}$ is strictly monotonic on the interval $J$ and its direct image $f^{-1}(J) = I$ is an interval, the function $f^{-1}$ is continuous at every point of $J$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
