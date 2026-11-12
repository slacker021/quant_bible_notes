---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval (open, closed, or semi-infinite), and let $f: I \to \mathbb{R}$ be a function admitting a primitive $F: I \to \mathbb{R}$ on $I$. By definition of an antiderivative, $F$ is everywhere differentiable on $I$ with:
$$
\begin{gather}
F'(x) = f(x) \quad \forall x \in I \tag{1}
\end{gather}
$$
---
# Proposition 1 (Intermediate-Value Property for Derivatives)
Let $a, b \in I$ with $a < b$, and suppose that the derivative values at the endpoints are unequal:
$$
\begin{gather}
f(a) \neq f(b) \tag{2}
\end{gather}
$$
Let $\gamma \in \mathbb{R}$ be any real scalar lying strictly between $f(a)$ and $f(b)$. Then there exists at least one point $\xi \in (a, b)$ such that:
$$
\begin{gather}
f(\xi) = \gamma \tag{3}
\end{gather}
$$

This assertion is precisely Darboux's Intermediate-Value Theorem applied to the differentiable function $F$ on $[a, b]$, where $F' = f$. The full proof—established via the minimization of the auxiliary function $g(x) := F(x) - \gamma x$ on $[a, b]$, application of the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem (Extreme Value Theorem)]], boundary exclusion using one-sided derivatives, and [[Proof of Fermat's Interior Extremum Lemma|Fermat's Interior Extremum Lemma]]—is detailed and established in [[Proof of Darboux's Intermediate-Value Theorem for Derivatives|Darboux's Intermediate-Value Theorem for Derivatives]]. Hence, Proposition 1 is verified.

---
# Proposition 2
Let $f: I \to \mathbb{R}$ possess a primitive on an interval $I$. 

1. **Connectedness of the Range:**
Recall that a subset $S \subseteq \mathbb{R}$ is topologically connected if and only if $S$ is an interval (meaning whenever $u, v \in S$ with $u < v$, the entire segment $[u, v] \subseteq S$). Let $u, v \in f(I)$ with $u < v$. There exist points $a, b \in I$ such that $f(a) = u$ and $f(b) = v$. By Proposition 1, for every intermediate value $\gamma \in (u, v)$, there exists $\xi$ between $a$ and $b$ (and hence $\xi \in I$) such that $f(\xi) = \gamma$. Thus, $[u, v] \subseteq f(I)$, which proves that the image $f(I)$ is an interval and therefore a connected subset of $\mathbb{R}$.

2. **Impossibility of Jump Discontinuities:**
Suppose, for the sake of contradiction, that $f$ has a jump discontinuity (a discontinuity of the first kind) at an interior point $x_0 \in I$. That is, both one-sided limits exist in $\mathbb{R}$ but are unequal:
$$
\begin{gather}
f(x_0^-) := \lim_{x \to x_0^-} f(x) \quad \text{and} \quad f(x_0^+) := \lim_{x \to x_0^+} f(x), \quad \text{with } f(x_0^-) \neq f(x_0^+) \tag{4}
\end{gather}
$$
Without loss of generality, assume $f(x_0^-) < f(x_0^+)$. 

By the definition of one-sided limits, for any sequence $x_n \to x_0$ with $x_n < x_0$, $f(x_n) \to f(x_0^-)$; and for $x_n > x_0$, $f(x_n) \to f(x_0^+)$. By Lagrange's Mean-Value Theorem applied to $F$ on $[x, x_0]$:
$$
\begin{gather}
\frac{F(x_0) - F(x)}{x_0 - x} = F'(\xi_x) = f(\xi_x) \tag{5}
\end{gather}
$$
for some $\xi_x \in (x, x_0)$. Taking the limit as $x \to x_0^-$ forces $\xi_x \to x_0^-$, which implies:
$$
\begin{gather}
F'_-(x_0) = \lim_{x \to x_0^-} \frac{F(x_0) - F(x)}{x_0 - x} = \lim_{\xi \to x_0^-} f(\xi) = f(x_0^-) \tag{6}
\end{gather}
$$
Similarly, taking the limit as $x \to x_0^+$ on $[x_0, x]$ forces:
$$
\begin{gather}
F'_+(x_0) = \lim_{x \to x_0^+} \frac{F(x) - F(x_0)}{x - x_0} = \lim_{\xi \to x_0^+} f(\xi) = f(x_0^+) \tag{7}
\end{gather}
$$
However, because $F$ is differentiable at $x_0$, both one-sided derivatives must coincide with the full derivative $F'(x_0) = f(x_0)$:
$$
\begin{gather}
f(x_0^-) = F'_-(x_0) = F'(x_0) = F'_+(x_0) = f(x_0^+) \tag{8}
\end{gather}
$$
Equality 8 contradicts the assumption that $f(x_0^-) \neq f(x_0^+)$. 

3. **Impossibility of Removable Discontinuities:**
If $f$ has a removable discontinuity at $x_0$, then $\lim_{x \to x_0} f(x) = L \in \mathbb{R}$ exists, but $f(x_0) \neq L$. By the identical mean-value argument, $F'(x_0) = \lim_{x \to x_0} f(\xi_x) = L$, forcing $f(x_0) = L$, which is an immediate contradiction.

Therefore, no function possessing a primitive can exhibit jump or removable discontinuities at any point of its domain. Any discontinuity of an antiderivative derivative must be an essential (oscillatory or infinite) discontinuity.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
