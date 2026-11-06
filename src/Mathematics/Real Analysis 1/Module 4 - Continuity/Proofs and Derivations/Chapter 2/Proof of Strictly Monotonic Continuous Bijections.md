---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $f: I \to \mathbb{R}$ be strictly monotonic on $I$. 

Without loss of generality, assume throughout this proof that $f$ is strictly increasing:
$$
\begin{gather}
\forall x_1, x_2 \in I \ \big(x_1 < x_2 \implies f(x_1) < f(x_2)\big) \tag{1}
\end{gather}
$$
(If $f$ is strictly decreasing, the argument applies symmetrically to $-f$).

**Necessity ($\implies$ Continuity implies Interval Image):**
Assume that $f$ is continuous on the interval $I$. 

By the [[Proof of the Image of an Interval under Continuous Mappings]], the continuous image of any interval is an interval. 

Therefore, $J = f(I)$ is an interval.

**Sufficiency ($\impliedby$ Interval Image implies Continuity):**
Conversely, assume that the image set $J = f(I)$ is an interval. 

It must be established that $f$ is continuous at an arbitrary point $x_0 \in I$. 

Let an arbitrary error tolerance $\varepsilon > 0$ be given.

*Case 1: The point $x_0$ is an interior point of $I$.*
Because $x_0 \in \operatorname{int}(I)$, there exist points $a, b \in I$ such that:
$$
\begin{gather}
a < x_0 < b \tag{2}
\end{gather}
$$

Because $f$ is strictly increasing, evaluating step 2 yields:
$$
\begin{gather}
f(a) < f(x_0) < f(b) \tag{3}
\end{gather}
$$

Choose a refined tolerance parameter:
$$
\begin{gather}
\varepsilon_1 := \min\big(\varepsilon, \ f(x_0) - f(a), \ f(b) - f(x_0)\big) > 0 \tag{4}
\end{gather}
$$

Define the target codomain values:
$$
\begin{gather}
y_1 := f(x_0) - \varepsilon_1 \quad \text{and} \quad y_2 := f(x_0) + \varepsilon_1 \tag{5}
\end{gather}
$$

By step 4, $f(a) \le y_1 < f(x_0) < y_2 \le f(b)$. Because $f(a), f(b) \in J$ and $J$ is an interval, the intermediate values belong to $J$:
$$
\begin{gather}
y_1 \in J \quad \text{and} \quad y_2 \in J \tag{6}
\end{gather}
$$

Because $J = f(I)$, there exist domain points $x_1, x_2 \in I$ such that:
$$
\begin{gather}
f(x_1) = y_1 \quad \text{and} \quad f(x_2) = y_2 \tag{7}
\end{gather}
$$

Because $f$ is strictly increasing and $y_1 < f(x_0) < y_2$, it follows that:
$$
\begin{gather}
x_1 < x_0 < x_2 \tag{8}
\end{gather}
$$

Define the domain radius:
$$
\begin{gather}
\delta := \min(x_0 - x_1, \ x_2 - x_0) > 0 \tag{9}
\end{gather}
$$

Let $x \in I$ satisfy $|x - x_0| < \delta$. Then:
$$
\begin{gather}
x_1 \le x_0 - \delta < x < x_0 + \delta \le x_2 \implies x_1 < x < x_2 \tag{10}
\end{gather}
$$

Applying the strictly increasing property of $f$ to step 10:
$$
\begin{gather}
f(x_1) < f(x) < f(x_2) \tag{11}
\end{gather}
$$

Substituting step 5 and step 7 into step 11:
$$
\begin{gather}
f(x_0) - \varepsilon_1 < f(x) < f(x_0) + \varepsilon_1 \iff |f(x) - f(x_0)| < \varepsilon_1 \le \varepsilon \tag{12}
\end{gather}
$$

This verifies that $f$ is continuous at $x_0$.

*Case 2: The point $x_0$ is an endpoint of $I$.*
If $x_0$ is the left endpoint of $I$, an identical one-sided argument choosing $y_2 = f(x_0) + \varepsilon_1 \in J$ yields a one-sided delta $\delta > 0$ such that $x_0 \le x < x_0 + \delta \implies |f(x) - f(x_0)| < \varepsilon$. 

If $x_0$ is the right endpoint of $I$, the symmetric left-sided argument holds. 

Therefore, $f$ is continuous at every point $x_0 \in I$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
