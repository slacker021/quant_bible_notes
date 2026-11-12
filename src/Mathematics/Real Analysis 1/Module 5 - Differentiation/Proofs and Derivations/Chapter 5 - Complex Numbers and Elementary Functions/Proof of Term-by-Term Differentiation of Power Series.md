---
dg-publish: true
---
Let $\sum_{n=0}^\infty c_n (z - z_0)^n$ be a power series with complex coefficients $c_n \in \mathbb{C}$, centered at $z_0 \in \mathbb{C}$, and possessing a strictly positive radius of convergence $R > 0$. Let $f: B(z_0, R) \to \mathbb{C}$ denote its sum function:
$$
\begin{gather}
f(z) := \sum_{n=0}^\infty c_n (z - z_0)^n \tag{1}
\end{gather}
$$
Consider the formally differentiated series:
$$
\begin{gather}
g(z) := \sum_{n=1}^\infty n c_n (z - z_0)^{n-1} \tag{2}
\end{gather}
$$
By the [[Proof of Cauchy-Hadamard Derivative Invariance|Cauchy-Hadamard Derivative Invariance]], the differentiated series $g(z)$ has the exact same radius of convergence $R$, and hence defines a holomorphic function $g: B(z_0, R) \to \mathbb{C}$.

The goal is to prove that $f$ is complex-differentiable at every point $w \in B(z_0, R)$ and that its complex derivative satisfies $f'(w) = g(w)$. Without loss of generality, translate coordinates so that $w = 0$ (or equivalently consider the expansion centered at $z_0 = 0$ for notational clarity).

**Algebraic Decomposition of the Difference Quotient:**
Fix an arbitrary point $w \in B(0, R)$. Let $r := |w| < R$, and choose $\rho$ such that $r < \rho < R$. 

Let $h \in \mathbb{C} \setminus \{0\}$ be a non-zero complex increment chosen sufficiently small such that $|w| + |h| \leq \rho < R$. 

Form the difference quotient of $f$ at $w$:
$$
\begin{gather}
\frac{f(w + h) - f(w)}{h} = \sum_{n=1}^\infty c_n \frac{(w + h)^n - w^n}{h} \tag{3}
\end{gather}
$$
Subtracting $g(w) = \sum_{n=1}^\infty n c_n w^{n-1}$ from step 3 yields:
$$
\begin{gather}
\frac{f(w + h) - f(w)}{h} - g(w) = \sum_{n=2}^\infty c_n \left[ \frac{(w + h)^n - w^n}{h} - n w^{n-1} \right] \tag{4}
\end{gather}
$$
Notice that for $n = 1$, the bracketed expression vanishes identically: $\frac{(w+h) - w}{h} - 1 = 0$, so the summation index in step 4 starts at $n = 2$.

**Factoring the Incremental Kernel:**
To obtain a sharp estimate for the bracketed difference in step 4, apply the binomial expansion to $(w + h)^n$:
$$
\begin{gather}
(w + h)^n - w^n = \sum_{k=1}^n \binom{n}{k} w^{n-k} h^k = n w^{n-1} h + \sum_{k=2}^n \binom{n}{k} w^{n-k} h^k \tag{5}
\end{gather}
$$
Dividing step 5 by $h \neq 0$ and subtracting $n w^{n-1}$ gives:
$$
\begin{gather}
\frac{(w + h)^n - w^n}{h} - n w^{n-1} = \sum_{k=2}^n \binom{n}{k} w^{n-k} h^{k-1} = h \sum_{k=2}^n \binom{n}{k} w^{n-k} h^{k-2} \tag{6}
\end{gather}
$$
Alternatively, express the polynomial difference using the factorization identity:
$$
\begin{gather}
\frac{(w + h)^n - w^n}{h} = \sum_{j=0}^{n-1} (w + h)^{n-1-j} w^j \tag{7}
\end{gather}
$$
Subtracting $n w^{n-1} = \sum_{j=0}^{n-1} w^{n-1}$ from step 7 yields:
$$
\begin{gather}
\frac{(w + h)^n - w^n}{h} - n w^{n-1} = \sum_{j=0}^{n-1} \left[ (w + h)^{n-1-j} w^j - w^{n-1} \right] = \sum_{j=0}^{n-1} w^j \left[ (w + h)^{n-1-j} - w^{n-1-j} \right] \tag{8}
\end{gather}
$$
Factoring out $h$ from each bracketed term via $(w+h)^m - w^m = h \sum_{l=0}^{m-1} (w+h)^{m-1-l} w^l$, and taking absolute values using the triangle inequality with $|w| \leq \rho$ and $|w + h| \leq \rho$, each of the terms is bounded by $\rho^{n-2}$. 

Precisely, from step 6 and the binomial identity:
$$
\begin{gather}
\left| \sum_{k=2}^n \binom{n}{k} w^{n-k} h^{k-2} \right| \leq \sum_{k=2}^n \binom{n}{k} |w|^{n-k} |h|^{k-2} \tag{9}
\end{gather}
$$
Using the inequality $\binom{n}{k} = \frac{n(n-1)}{k(k-1)} \binom{n-2}{k-2} \leq \frac{n(n-1)}{2} \binom{n-2}{k-2}$ for all $k \geq 2$:
$$
\begin{gather}
\sum_{k=2}^n \binom{n}{k} |w|^{n-k} |h|^{k-2} \leq \frac{n(n-1)}{2} \sum_{k=2}^n \binom{n-2}{k-2} |w|^{n-k} |h|^{k-2} = \frac{n(n-1)}{2} (|w| + |h|)^{n-2} \tag{10}
\end{gather}
$$
Because $|w| + |h| \leq \rho$, step 10 establishes the uniform term-wise bound:
$$
\begin{gather}
\left| \frac{(w + h)^n - w^n}{h} - n w^{n-1} \right| \leq |h| \frac{n(n-1)}{2} \rho^{n-2} \tag{11}
\end{gather}
$$

**Bounding the Remainder Series:**
Substitute the bound of step 11 into the series difference of step 4:
$$
\begin{gather}
\left| \frac{f(w + h) - f(w)}{h} - g(w) \right| \leq \sum_{n=2}^\infty |c_n| \left| \frac{(w + h)^n - w^n}{h} - n w^{n-1} \right| \leq \frac{|h|}{2} \sum_{n=2}^\infty n(n-1) |c_n| \rho^{n-2} \tag{12}
\end{gather}
$$
Consider the numerical series appearing on the right side of step 12:
$$
\begin{gather}
M(\rho) := \sum_{n=2}^\infty n(n-1) |c_n| \rho^{n-2} \tag{13}
\end{gather}
$$
By Cauchy-Hadamard Derivative Invariance applied twice, the second formal derivative series $\sum_{n=2}^\infty n(n-1) c_n z^{n-2}$ has radius of convergence $R$. 

Since $\rho < R$ lies strictly within the open disk of convergence, the series in step 13 converges absolutely to a finite non-negative real constant:
$$
\begin{gather}
M(\rho) < \infty \tag{14}
\end{gather}
$$

**Evaluation of the Complex Derivative Limit:**
Combining step 12 and step 14, for every $h$ satisfying $0 < |h| \leq \rho - |w|$, the error is bounded by:
$$
\begin{gather}
0 \leq \left| \frac{f(w + h) - f(w)}{h} - g(w) \right| \leq \frac{M(\rho)}{2} |h| \tag{15}
\end{gather}
$$
Taking the limit as $h \to 0$ in the complex plane, the squeeze theorem directly yields:
$$
\begin{gather}
\lim_{h \to 0} \left| \frac{f(w + h) - f(w)}{h} - g(w) \right| = 0 \tag{16}
\end{gather}
$$
Step 16 proves that the complex difference quotient converges to $g(w)$:
$$
\begin{gather}
f'(w) = \lim_{h \to 0} \frac{f(w + h) - f(w)}{h} = g(w) = \sum_{n=1}^\infty n c_n (w - z_0)^{n-1} \tag{17}
\end{gather}
$$
Because $w \in B(z_0, R)$ was chosen arbitrarily, $f$ is holomorphic on all of $B(z_0, R)$, and its complex derivative is given by the term-by-term differentiated power series.

**Inductive Extension to Derivatives of All Orders:**
Because the derivative $f'(z)$ is itself represented by a power series with the exact same radius of convergence $R$, this argument applies iteratively to $f^{(k)}(z)$ for every $k \in \mathbb{N}$. 

Consequently, $f$ is infinitely complex-differentiable ($C^\infty$) on $B(z_0, R)$, and the $k$-th derivative is obtained by differentiating term-by-term $k$ times:
$$
\begin{gather}
f^{(k)}(z) = \sum_{n=k}^\infty \frac{n!}{(n-k)!} c_n (z - z_0)^{n-k} \tag{18}
\end{gather}
$$
In particular, evaluating step 18 at the center $z = z_0$ yields $f^{(k)}(z_0) = k! \, c_k$, which establishes that every convergent power series is the Taylor series of its sum function:
$$
\begin{gather}
c_k = \frac{f^{(k)}(z_0)}{k!} \tag{19}
\end{gather}
$$
$$
\textbf{Q.E.D}
$$