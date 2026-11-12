---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be an open set, let $n \in \mathbb{N}$, and let $u, v: E \to \mathbb{R}$ be $n$-times differentiable functions on $E$.

The proposition is proven by mathematical induction on the order of differentiation $n$.

**Base Case ($n = 1$):**
For $n = 1$, $u$ and $v$ are differentiable on $E$. By the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]], the product function $(uv)$ is differentiable on $E$, and its first derivative is given by:
$$
\begin{gather}
(uv)'(x) = u'(x)v(x) + u(x)v'(x) \tag{1}
\end{gather}
$$

Evaluating the binomial summation formula for $n = 1$ gives:
$$
\begin{gather}
\sum_{k=0}^1 \binom{1}{k} u^{(k)}(x) v^{(1-k)}(x) = \binom{1}{0} u^{(0)}(x) v^{(1)}(x) + \binom{1}{1} u^{(1)}(x) v^{(0)}(x) = u(x)v'(x) + u'(x)v(x) \tag{2}
\end{gather}
$$

Because step 1 and step 2 are identical, the formula holds for $n = 1$.

**Induction Hypothesis:**
Assume that for an arbitrary integer $m \ge 1$, if $u, v$ are $m$-times differentiable on $E$, then $(uv)$ is $m$-times differentiable on $E$, and its $m$-th derivative satisfies:
$$
\begin{gather}
(uv)^{(m)}(x) = \sum_{k=0}^m \binom{m}{k} u^{(k)}(x) v^{(m-k)}(x) \tag{3}
\end{gather}
$$

**Induction Step ($n = m + 1$):**
Suppose that $u$ and $v$ are $(m + 1)$-times differentiable on $E$. Then for each $k \in \{0, 1, \dots, m\}$, the derivative $u^{(k)}$ is differentiable on $E$ with derivative $u^{(k+1)}$, and $v^{(m-k)}$ is differentiable on $E$ with derivative $v^{(m-k+1)}$.

Differentiating both sides of the induction hypothesis in step 3 with respect to $x$ using the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]] gives:
$$
\begin{gather}
(uv)^{(m+1)}(x) = \frac{d}{dx} \left[ \sum_{k=0}^m \binom{m}{k} u^{(k)}(x) v^{(m-k)}(x) \right] = \sum_{k=0}^m \binom{m}{k} \frac{d}{dx}\left[ u^{(k)}(x) v^{(m-k)}(x) \right] \tag{4}
\end{gather}
$$

Applying the Leibniz product rule to each product term in step 4 yields:
$$
\begin{gather}
\frac{d}{dx}\left[ u^{(k)}(x) v^{(m-k)}(x) \right] = u^{(k+1)}(x) v^{(m-k)}(x) + u^{(k)}(x) v^{(m-k+1)}(x) \tag{5}
\end{gather}
$$

Substituting step 5 into step 4 and splitting the sum into two separate summations yields:
$$
\begin{gather}
(uv)^{(m+1)}(x) = \sum_{k=0}^m \binom{m}{k} u^{(k+1)}(x) v^{(m-k)}(x) + \sum_{k=0}^m \binom{m}{k} u^{(k)}(x) v^{(m+1-k)}(x) \tag{6}
\end{gather}
$$

In the first summation of step 6, introduce the index shift $j := k + 1$. As $k$ runs from $0$ to $m$, the shifted index $j$ runs from $1$ to $m + 1$:
$$
\begin{gather}
\sum_{k=0}^m \binom{m}{k} u^{(k+1)}(x) v^{(m-k)}(x) = \sum_{j=1}^{m+1} \binom{m}{j-1} u^{(j)}(x) v^{(m+1-j)}(x) \tag{7}
\end{gather}
$$

Relabeling the dummy index $j$ back to $k$ in step 7 and isolating the boundary term $k = m + 1$ produces:
$$
\begin{gather}
\sum_{k=1}^{m+1} \binom{m}{k-1} u^{(k)}(x) v^{(m+1-k)}(x) = \binom{m}{m} u^{(m+1)}(x) v(x) + \sum_{k=1}^m \binom{m}{k-1} u^{(k)}(x) v^{(m+1-k)}(x) \tag{8}
\end{gather}
$$

Similarly, isolating the boundary term $k = 0$ in the second summation of step 6 gives:
$$
\begin{gather}
\sum_{k=0}^m \binom{m}{k} u^{(k)}(x) v^{(m+1-k)}(x) = \binom{m}{0} u(x) v^{(m+1)}(x) + \sum_{k=1}^m \binom{m}{k} u^{(k)}(x) v^{(m+1-k)}(x) \tag{9}
\end{gather}
$$

Adding step 8 and step 9 together and grouping the intermediate summations yields:
$$
\begin{gather}
(uv)^{(m+1)}(x) = \binom{m}{0} u(x) v^{(m+1)}(x) + \sum_{k=1}^m \left[ \binom{m}{k-1} + \binom{m}{k} \right] u^{(k)}(x) v^{(m+1-k)}(x) + \binom{m}{m} u^{(m+1)}(x) v(x) \tag{10}
\end{gather}
$$

By virtue of Pascal's combinatorial recurrence identity:
$$
\begin{gather}
\binom{m}{k-1} + \binom{m}{k} = \binom{m+1}{k} \tag{11}
\end{gather}
$$
and the boundary identities $\binom{m}{0} = 1 = \binom{m+1}{0}$ and $\binom{m}{m} = 1 = \binom{m+1}{m+1}$.

Substituting step 11 and the boundary values into step 10 allows all terms to be gathered into a single binomial summation:
$$
\begin{gather}
(uv)^{(m+1)}(x) = \binom{m+1}{0} u(x) v^{(m+1)}(x) + \sum_{k=1}^m \binom{m+1}{k} u^{(k)}(x) v^{(m+1-k)}(x) + \binom{m+1}{m+1} u^{(m+1)}(x) v(x) \tag{12}
\end{gather}
$$
which condenses to:
$$
\begin{gather}
(uv)^{(m+1)}(x) = \sum_{k=0}^{m+1} \binom{m+1}{k} u^{(k)}(x) v^{(m+1-k)}(x) \tag{13}
\end{gather}
$$

By the principle of mathematical induction, the General Leibniz Rule holds for all integers $n \in \mathbb{N}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
