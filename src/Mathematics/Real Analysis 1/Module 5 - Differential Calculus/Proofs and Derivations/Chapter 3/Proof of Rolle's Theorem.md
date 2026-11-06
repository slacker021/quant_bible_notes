---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be continuous on the closed interval $[a, b]$, differentiable on the open interval $(a, b)$, and suppose $f(a) = f(b)$.

### Step 1: Application of the Weierstrass Extreme Value Theorem
Because $[a, b]$ is a compact subset of $\mathbb{R}$ and $f$ is continuous on $[a, b]$, by the Weierstrass Extreme Value Theorem (Theorem 2.5 of Module 4), $f$ is bounded and attains both its absolute maximum $M$ and absolute minimum $m$ on $[a, b]$:
$$
\begin{gather}
M = \max_{x \in [a, b]} f(x) = f(x_{\max}), \quad m = \min_{x \in [a, b]} f(x) = f(x_{\min}) \tag{1}
\end{gather}
$$
for some points $x_{\max}, x_{\min} \in [a, b]$.

### Step 2: The Constant Case ($M = m$)
If $M = m$, then for all $x \in [a, b]$:
$$
\begin{gather}
m \le f(x) \le M \implies f(x) = M = \text{const} \tag{2}
\end{gather}
$$
The derivative of a constant function vanishes identically on $(a, b)$. In this case, $f'(\xi) = 0$ holds for *every* $\xi \in (a, b)$.

### Step 3: The Non-Constant Case ($M > m$)
Suppose $M > m$. By hypothesis, $f(a) = f(b)$. Therefore, the endpoints $f(a)$ and $f(b)$ cannot simultaneously equal both $M$ and $m$. 

Consequently, at least one of the extrema (either $M$ or $m$) must be attained at an interior point of the interval $(a, b)$:
1. If $M > f(a)$, then $x_{\max} \notin \{a, b\}$, which implies that $x_{\max} \in (a, b)$. Set $\xi := x_{\max}$.
2. If $m < f(a)$, then $x_{\min} \notin \{a, b\}$, which implies that $x_{\min} \in (a, b)$. Set $\xi := x_{\min}$.

In either scenario, $\xi \in (a, b)$ is an interior point of the domain where $f$ attains a local extremum. 

Because $f$ is differentiable on $(a, b)$, $f$ is differentiable at $\xi$. By Theorem 3.1 (Fermat's Stationary Point Lemma):
$$
\begin{gather}
f'(\xi) = 0 \tag{3}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
