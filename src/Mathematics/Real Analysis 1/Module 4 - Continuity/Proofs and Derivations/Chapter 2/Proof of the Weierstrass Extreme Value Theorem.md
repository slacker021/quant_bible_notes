---
dg-publish: true
---
Let $K \subset \mathbb{R}$ be a non-empty compact subset of $\mathbb{R}$, and let $f: K \to \mathbb{R}$ be continuous on $K$. 

By the [[Proof of the Weierstrass Global Boundedness Theorem]], the image set $f(K) \subseteq \mathbb{R}$ is bounded. 

Because $K$ is non-empty, the image set $f(K)$ is a non-empty bounded subset of the real line. 

By the Completeness Axiom (Least Upper Bound / Greatest Lower Bound Property) of $\mathbb{R}$, the supremum and infimum exist as finite real numbers:
$$
\begin{gather}
M := \sup_{x \in K} f(x) \in \mathbb{R} \quad \text{and} \quad m := \inf_{x \in K} f(x) \in \mathbb{R} \tag{1}
\end{gather}
$$

It remains to establish that there exist points $x^*, x_* \in K$ such that $f(x^*) = M$ and $f(x_*) = m$. 

**Attainment of the Supremum:**
By the characterization of the supremum, for every natural number $n \in \mathbb{N}$, the reduced value $M - \frac{1}{n}$ is not an upper bound for $f(K)$. 

Therefore, there exists an element $x_n \in K$ such that:
$$
\begin{gather}
M - \frac{1}{n} < f(x_n) \le M \tag{2}
\end{gather}
$$

Consider the sequence of points $\{x_n\}_{n=1}^\infty \subseteq K$. 

Because $K$ is bounded, the sequence $\{x_n\}$ is bounded in $\mathbb{R}$. 

By the Bolzano–Weierstrass Theorem, $\{x_n\}$ possesses a convergent subsequence $\{x_{n_k}\}_{k=1}^\infty$ with limit:
$$
\begin{gather}
\lim_{k \to \infty} x_{n_k} = x^* \tag{3}
\end{gather}
$$

Because $K$ is closed in $\mathbb{R}$ and $\{x_{n_k}\} \subseteq K$, the limit point belongs to $K$:
$$
\begin{gather}
x^* \in K \tag{4}
\end{gather}
$$

Because $f$ is continuous on $K$, it is continuous at $x^*$. By the Heine sequential criterion:
$$
\begin{gather}
\lim_{k \to \infty} f(x_{n_k}) = f(x^*) \tag{5}
\end{gather}
$$

Evaluating the inequality of step 2 along the subsequence indices $n_k$:
$$
\begin{gather}
M - \frac{1}{n_k} < f(x_{n_k}) \le M \tag{6}
\end{gather}
$$

Taking the limit of step 6 as $k \to \infty$, and noting that $\lim_{k \to \infty} \frac{1}{n_k} = 0$:
$$
\begin{gather}
M \le \lim_{k \to \infty} f(x_{n_k}) \le M \implies \lim_{k \to \infty} f(x_{n_k}) = M \tag{7}
\end{gather}
$$

Combining step 5 and step 7:
$$
\begin{gather}
f(x^*) = M = \sup_{x \in K} f(x) \tag{8}
\end{gather}
$$
which proves that $f$ attains its absolute supremum at $x^* \in K$.

**Attainment of the Infimum:**
Consider the negated function $g: K \to \mathbb{R}$ defined by $g(x) := -f(x)$. 

Because $f$ is continuous on $K$, $g$ is continuous on $K$ by [[Proof of Preservation of Continuity under Algebraic Field Operations]]. 

By the elementary properties of the supremum and infimum:
$$
\begin{gather}
\sup_{x \in K} g(x) = \sup_{x \in K} \big(-f(x)\big) = -\inf_{x \in K} f(x) = -m \tag{9}
\end{gather}
$$

Applying the result of step 8 to the function $g$, there exists a point $x_* \in K$ such that:
$$
\begin{gather}
g(x_*) = \sup_{x \in K} g(x) = -m \tag{10}
\end{gather}
$$

Substituting $g(x_*) = -f(x_*)$ into step 10:
$$
\begin{gather}
-f(x_*) = -m \iff f(x_*) = m = \inf_{x \in K} f(x) \tag{11}
\end{gather}
$$
which proves that $f$ attains its absolute infimum at $x_* \in K$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
