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
# Proposition 1 
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

To substantiate this, consider without loss of generality the case:
$$
\begin{gather}
f(a) < \gamma < f(b) \tag{4}
\end{gather}
$$
If instead $f(a) > \gamma > f(b)$, one applies the identical deduction to the negated function $\widetilde{F}(x) := -F(x)$ with derivative $\widetilde{f}(x) = -f(x)$ and target value $-\gamma$, as $-f(a) < -\gamma < -f(b)$.

Define the auxiliary potential function $g: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := F(x) - \gamma x \quad \forall x \in [a, b] \tag{5}
\end{gather}
$$

Because $F$ is differentiable on $[a, b]$, $F$ is continuous on $[a, b]$ by virtue of [[Proof that Differentiability Implies Continuity|Differentiability Implies Continuity]]. The linear component $x \mapsto \gamma x$ is continuous on $\mathbb{R}$. Hence, $g$ is continuous on the compact interval $[a, b]$.

By the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem (Extreme Value Theorem)]], the continuous function $g$ attains its global minimum on the compact set $[a, b]$ at some point $\xi \in [a, b]$:
$$
\begin{gather}
g(\xi) = \min_{x \in [a, b]} g(x) \tag{6}
\end{gather}
$$

Differentiating step 5 gives:
$$
\begin{gather}
g'(x) = F'(x) - \gamma = f(x) - \gamma \quad \forall x \in [a, b] \tag{7}
\end{gather}
$$

Evaluate this derivative at the left endpoint $x = a$:
$$
\begin{gather}
g'(a) = f(a) - \gamma < 0 \tag{8}
\end{gather}
$$
by step 4. By definition of the right-sided derivative:
$$
\begin{gather}
\lim_{x \to a^+} \frac{g(x) - g(a)}{x - a} = g'(a) < 0 \tag{9}
\end{gather}
$$
By the sign-preservation theorem for limits, there exists $\delta_1 > 0$ such that for all $x \in (a, a + \delta_1) \cap [a, b]$:
$$
\begin{gather}
\frac{g(x) - g(a)}{x - a} < 0 \tag{10}
\end{gather}
$$
Since $x > a$, multiplying by $(x - a) > 0$ yields:
$$
\begin{gather}
g(x) - g(a) < 0 \implies g(x) < g(a) \tag{11}
\end{gather}
$$
Inequality 11 establishes that $g(a)$ cannot be the minimum of $g$ on $[a, b]$. Consequently, $\xi \neq a$.

Next, evaluate the derivative at the right endpoint $x = b$:
$$
\begin{gather}
g'(b) = f(b) - \gamma > 0 \tag{12}
\end{gather}
$$
by step 4. By definition of the left-sided derivative:
$$
\begin{gather}
\lim_{x \to b^-} \frac{g(x) - g(b)}{x - b} = g'(b) > 0 \tag{13}
\end{gather}
$$
By sign-preservation, there exists $\delta_2 > 0$ such that for all $x \in (b - \delta_2, b) \cap [a, b]$:
$$
\begin{gather}
\frac{g(x) - g(b)}{x - b} > 0 \tag{14}
\end{gather}
$$
Since $x < b$, the denominator is negative: $x - b < 0$. Multiplying step 14 by $(x - b)$ reverses the inequality:
$$
\begin{gather}
g(x) - g(b) < 0 \implies g(x) < g(b) \tag{15}
\end{gather}
$$
Inequality 15 establishes that $g(b)$ cannot be the minimum of $g$ on $[a, b]$. Consequently, $\xi \neq b$.

Combining these two exclusions demonstrates that the global minimizer is strictly interior:
$$
\begin{gather}
\xi \in (a, b) \tag{16}
\end{gather}
$$

Because $\xi$ is an interior local extremum of $g$ and $g$ is differentiable at $\xi$, [[Proof of Fermat's Interior Extremum Lemma|Fermat's Interior Extremum Lemma]] requires that the derivative vanishes:
$$
\begin{gather}
g'(\xi) = 0 \tag{17}
\end{gather}
$$
Substituting step 7 into step 17 yields:
$$
\begin{gather}
f(\xi) - \gamma = 0 \implies f(\xi) = \gamma \tag{18}
\end{gather}
$$
with $\xi \in (a, b)$.

---
# Proposition 2
Let $f: I \to \mathbb{R}$ possess a primitive on an interval $I$. 

1. **Connectedness of the Range:**
Recall that a subset $S \subseteq \mathbb{R}$ is topologically connected if and only if $S$ is an interval (meaning whenever $u, v \in S$ with $u < v$, the entire segment $[u, v] \subseteq S$). Let $u, v \in f(I)$ with $u < v$. There exist points $a, b \in I$ such that $f(a) = u$ and $f(b) = v$. By Proposition 1, for every intermediate value $\gamma \in (u, v)$, there exists $\xi$ between $a$ and $b$ (and hence $\xi \in I$) such that $f(\xi) = \gamma$. Thus, $[u, v] \subseteq f(I)$, which proves that the image $f(I)$ is an interval and therefore a connected subset of $\mathbb{R}$.

2. **Impossibility of Jump Discontinuities:**
Suppose, for the sake of contradiction, that $f$ has a jump discontinuity (a discontinuity of the first kind) at an interior point $x_0 \in I$. That is, both one-sided limits exist in $\mathbb{R}$ but are unequal:
$$
\begin{gather}
f(x_0^-) := \lim_{x \to x_0^-} f(x) \quad \text{and} \quad f(x_0^+) := \lim_{x \to x_0^+} f(x), \quad \text{with } f(x_0^-) \neq f(x_0^+) \tag{19}
\end{gather}
$$
Without loss of generality, assume $f(x_0^-) < f(x_0^+)$. 

By the definition of one-sided limits, for any sequence $x_n \to x_0$ with $x_n < x_0$, $f(x_n) \to f(x_0^-)$; and for $x_n > x_0$, $f(x_n) \to f(x_0^+)$. By Lagrange's Mean-Value Theorem applied to $F$ on $[x, x_0]$:
$$
\begin{gather}
\frac{F(x_0) - F(x)}{x_0 - x} = F'(\xi_x) = f(\xi_x) \tag{20}
\end{gather}
$$
for some $\xi_x \in (x, x_0)$. Taking the limit as $x \to x_0^-$ forces $\xi_x \to x_0^-$, which implies:
$$
\begin{gather}
F'_-(x_0) = \lim_{x \to x_0^-} \frac{F(x_0) - F(x)}{x_0 - x} = \lim_{\xi \to x_0^-} f(\xi) = f(x_0^-) \tag{21}
\end{gather}
$$
Similarly, taking the limit as $x \to x_0^+$ on $[x_0, x]$ forces:
$$
\begin{gather}
F'_+(x_0) = \lim_{x \to x_0^+} \frac{F(x) - F(x_0)}{x - x_0} = \lim_{\xi \to x_0^+} f(\xi) = f(x_0^+) \tag{22}
\end{gather}
$$
However, because $F$ is differentiable at $x_0$, both one-sided derivatives must coincide with the full derivative $F'(x_0) = f(x_0)$:
$$
\begin{gather}
f(x_0^-) = F'_-(x_0) = F'(x_0) = F'_+(x_0) = f(x_0^+) \tag{23}
\end{gather}
$$
Equality 23 contradicts the assumption that $f(x_0^-) \neq f(x_0^+)$. 

3. **Impossibility of Removable Discontinuities:**
If $f$ has a removable discontinuity at $x_0$, then $\lim_{x \to x_0} f(x) = L \in \mathbb{R}$ exists, but $f(x_0) \neq L$. By the identical mean-value argument, $F'(x_0) = \lim_{x \to x_0} f(\xi_x) = L$, forcing $f(x_0) = L$, which is an immediate contradiction.

Therefore, no function possessing a primitive can exhibit jump or removable discontinuities at any point of its domain. Any discontinuity of an antiderivative derivative must be an essential (oscillatory or infinite) discontinuity.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
