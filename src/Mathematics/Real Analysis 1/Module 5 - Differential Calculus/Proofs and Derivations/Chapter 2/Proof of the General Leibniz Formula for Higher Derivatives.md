---
dg-publish: true
---
Let $u, v: I \to \mathbb{R}$ be $n$ times differentiable functions on an open interval $I \subseteq \mathbb{R}$.

The proof proceeds by the [[Proof that Induction Works|principle of induction]] on $n \in \mathbb{N}$.

---
# Base Case: $n = 1$
For $n = 1$, the product rule yields:
$$
\begin{gather}
(u v)' = u' v + u v' \tag{1}
\end{gather}
$$

Evaluating the right-hand side of the Leibniz formula for $n = 1$:
$$
\begin{gather}
\sum_{k=0}^1 \binom{1}{k} u^{(1-k)} v^{(k)} = \binom{1}{0} u^{(1)} v^{(0)} + \binom{1}{1} u^{(0)} v^{(1)} = 1 \cdot u' v + 1 \cdot u v' = u' v + u v' \tag{2}
\end{gather}
$$
The equation of step 2 matches the equation of step 1, establishing the base case.

---
# Inductive Hypothesis
Assume that for some integer $m \ge 1$, if $u$ and $v$ are $m$ times differentiable, then:
$$
\begin{gather}
(u v)^{(m)} = \sum_{k=0}^m \binom{m}{k} u^{(m-k)} v^{(k)} \tag{3}
\end{gather}
$$

### Inductive Step: $n = m + 1$
Suppose $u$ and $v$ are $m + 1$ times differentiable. Differentiating the equation of step 3 with respect to $x$:
$$
\begin{gather}
(u v)^{(m+1)} = \frac{d}{dx} \left[ \sum_{k=0}^m \binom{m}{k} u^{(m-k)} v^{(k)} \right] = \sum_{k=0}^m \binom{m}{k} \frac{d}{dx} \big( u^{(m-k)} v^{(k)} \big) \tag{4}
\end{gather}
$$

Applying the product rule to each summand:
$$
\begin{gather}
\frac{d}{dx} \big( u^{(m-k)} v^{(k)} \big) = u^{(m-k+1)} v^{(k)} + u^{(m-k)} v^{(k+1)} \tag{5}
\end{gather}
$$

Substituting the equation of step 5 into the equation of step 4 and splitting the sum:
$$
\begin{gather}
(u v)^{(m+1)} = \sum_{k=0}^m \binom{m}{k} u^{(m+1-k)} v^{(k)} + \sum_{k=0}^m \binom{m}{k} u^{(m-k)} v^{(k+1)} \tag{6}
\end{gather}
$$

Shift the index of the second summation by setting $j = k + 1$ (so that $k = j - 1$, running from $j = 1$ to $m + 1$):
$$
\begin{gather}
\sum_{k=0}^m \binom{m}{k} u^{(m-k)} v^{(k+1)} = \sum_{j=1}^{m+1} \binom{m}{j-1} u^{(m+1-j)} v^{(j)} \tag{7}
\end{gather}
$$

Replacing the dummy index $j$ with $k$ and isolating the boundary terms $k = 0$ and $k = m + 1$:
$$
\begin{gather}
(u v)^{(m+1)} = \binom{m}{0} u^{(m+1)} v^{(0)} + \sum_{k=1}^m \left[ \binom{m}{k} + \binom{m}{k-1} \right] u^{(m+1-k)} v^{(k)} + \binom{m}{m} u^{(0)} v^{(m+1)} \tag{8}
\end{gather}
$$

By Pascal's recurrence relation for binomial coefficients:
$$
\begin{gather}
\binom{m}{k} + \binom{m}{k-1} = \binom{m+1}{k} \tag{9}
\end{gather}
$$

Furthermore, $\binom{m}{0} = 1 = \binom{m+1}{0}$ and $\binom{m}{m} = 1 = \binom{m+1}{m+1}$. Substituting these identities into the equation of step 8:
$$
\begin{gather}
(u v)^{(m+1)} = \binom{m+1}{0} u^{(m+1)} v^{(0)} + \sum_{k=1}^m \binom{m+1}{k} u^{(m+1-k)} v^{(k)} + \binom{m+1}{m+1} u^{(0)} v^{(m+1)} \tag{10}
\end{gather}
$$

Combining all terms into a single summation:
$$
\begin{gather}
(u v)^{(m+1)} = \sum_{k=0}^{m+1} \binom{m+1}{k} u^{(m+1-k)} v^{(k)} \tag{11}
\end{gather}
$$

By mathematical induction, the Leibniz formula holds for all integers $n \ge 1$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
