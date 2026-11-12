---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be a real-valued function defined on the non-degenerate closed interval $[a, b]$ with $a < b$, satisfying the following hypotheses:
1. The function $f$ is continuous on the compact interval $[a, b]$;
2. The function $f$ is differentiable on the open interior interval $(a, b)$;
3. The function satisfies the boundary equality $f(a) = f(b)$.

By virtue of the [[Chapter 2 - Properties of Continuous Functions#The Second Weierstrass Theorem: Attainment of Extrema|Second Weierstrass Theorem]], a continuous real-valued function on a compact metric space is bounded and attains its supremum and infimum. Therefore, there exist points $x_m, x_M \in [a, b]$ such that:
$$
\begin{gather}
m := \inf_{x \in [a, b]} f(x) = f(x_m) \tag{1}
\end{gather}
$$
$$
\begin{gather}
M := \sup_{x \in [a, b]} f(x) = f(x_M) \tag{2}
\end{gather}
$$
By definition of the infimum and supremum, the inequality $m \le M$ holds identically. Two mutually exhaustive cases emerge:

**Case 1: $m = M$.**
If the infimum coincides with the supremum, then for every $x \in [a, b]$:
$$
\begin{gather}
m \le f(x) \le M \implies f(x) = M \tag{3}
\end{gather}
$$
The function $f$ is identically constant across the entire interval $[a, b]$. Consequently, for every point $\xi \in (a, b)$, the difference quotient vanishes identically for all sufficiently small perturbations:
$$
\begin{gather}
f'(\xi) = \lim_{h \to 0} \frac{f(\xi + h) - f(\xi)}{h} = \lim_{h \to 0} \frac{M - M}{h} = 0 \tag{4}
\end{gather}
$$
In this degenerate scenario, every interior point $\xi \in (a, b)$ serves as a stationary point.

**Case 2: $m < M$.**
Assume that the minimum and maximum values are strictly distinct. By hypothesis 3, the function assumes equal values at the endpoints of the interval:
$$
\begin{gather}
f(a) = f(b) \tag{5}
\end{gather}
$$
If both extremal values were attained exclusively on the two-point boundary $\{a, b\}$, then:
$$
\begin{gather}
f(x_m) \in \{f(a), f(b)\} \quad \text{and} \quad f(x_M) \in \{f(a), f(b)\} \tag{6}
\end{gather}
$$
By step 5, $\{f(a), f(b)\}$ consists of a single singleton value $\{f(a)\}$. Step 6 would then force:
$$
\begin{gather}
m = f(x_m) = f(a) = f(x_M) = M \tag{7}
\end{gather}
$$
which directly contradicts the assumption $m < M$. 

Therefore, it is impossible for both extrema to occur at the boundary. At least one of the two points $x_m$ or $x_M$ must belong strictly to the open interior:
$$
\begin{gather}
x_m \in (a, b) \quad \text{or} \quad x_M \in (a, b) \tag{8}
\end{gather}
$$

Let $\xi \in (a, b)$ denote an interior point that attains one of these global extrema:
- If $M > f(a)$, choose $\xi = x_M \in (a, b)$, which constitutes an interior global maximum;
- If $m < f(a)$, choose $\xi = x_m \in (a, b)$, which constitutes an interior global minimum.

Because $\xi \in (a, b)$, the point $\xi$ is an interior accumulation point of $[a, b]$. Furthermore, by hypothesis 2, $f$ is differentiable at $\xi$. 

By virtue of [[Proof of Fermat's Interior Extremum Lemma|Fermat's Interior Extremum Lemma]], the derivative of any function differentiable at an interior local extremum vanishes identically. It follows that:
$$
\begin{gather}
f'(\xi) = 0 \tag{9}
\end{gather}
$$
where $\xi \in (a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$