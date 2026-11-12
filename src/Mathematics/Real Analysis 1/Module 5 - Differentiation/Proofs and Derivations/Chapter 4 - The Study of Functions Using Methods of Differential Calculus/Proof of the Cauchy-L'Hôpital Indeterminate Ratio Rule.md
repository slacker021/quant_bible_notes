---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, and let $f, g: (a, b) \to \mathbb{R}$ be differentiable functions on $(a, b)$. Assume that $g'(x) \neq 0$ for all $x \in (a, b)$, and suppose that:
$$
\begin{gather}
\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = A \tag{1}
\end{gather}
$$
where $-\infty \le A \le +\infty$.

Notice that because $g'$ is non-zero everywhere on the interval $(a, b)$, [[Proof of Darboux's Intermediate-Value Theorem for Derivatives|Darboux's Theorem]] guarantees that $g'$ cannot change sign on $(a, b)$. Thus, $g'$ is either strictly positive or strictly negative throughout $(a, b)$, whence $g$ is strictly monotonic.

---
# Case 1: The Indeterminate Form [0 / 0]
Suppose that:
$$
\begin{gather}
\lim_{x \to a^+} f(x) = 0 \quad \text{and} \quad \lim_{x \to a^+} g(x) = 0 \tag{2}
\end{gather}
$$

Extend the functions $f$ and $g$ to the half-open interval $[a, b)$ by defining their boundary values at $a$:
$$
\begin{gather}
f(a) := 0 \quad \text{and} \quad g(a) := 0 \tag{3}
\end{gather}
$$
By virtue of step 2, both extended functions $f$ and $g$ are continuous at $x = a$, and therefore continuous on $[a, x]$ for every $x \in (a, b)$. Furthermore, they are differentiable on the open subinterval $(a, x)$.

Let $x \in (a, b)$ be an arbitrary point. Applying [[Proof of Cauchy's Generalized Finite-Increment Theorem|Cauchy's Generalized Finite-Increment Theorem]] to $f$ and $g$ on the interval $[a, x]$ guarantees the existence of an intermediate point $\xi \in (a, x)$ such that:
$$
\begin{gather}
\big[f(x) - f(a)\big] g'(\xi) = \big[g(x) - g(a)\big] f'(\xi) \tag{4}
\end{gather}
$$
Substituting the boundary values $f(a) = 0$ and $g(a) = 0$ into step 4 yields:
$$
\begin{gather}
f(x) g'(\xi) = g(x) f'(\xi) \tag{5}
\end{gather}
$$

Because $g$ is strictly monotonic and $g(a) = 0$, $g(x) \neq 0$ for all $x \in (a, b)$. Because $g'(\xi) \neq 0$, dividing step 5 by $g(x) g'(\xi)$ gives:
$$
\begin{gather}
\frac{f(x)}{g(x)} = \frac{f'(\xi)}{g'(\xi)} \tag{6}
\end{gather}
$$

As $x \to a^+$, because $a < \xi < x$, the squeeze theorem forces $\xi \to a^+$. 

Consequently, taking the limit as $x \to a^+$ in step 6 yields:
$$
\begin{gather}
\lim_{x \to a^+} \frac{f(x)}{g(x)} = \lim_{\xi \to a^+} \frac{f'(\xi)}{g'(\xi)} = A \tag{7}
\end{gather}
$$
which establishes the theorem for the indeterminate form $\left[\frac{0}{0}\right]$.

---
# Case 2: The Indeterminate Form [* / $\infty$]
Suppose that:
$$
\begin{gather}
\lim_{x \to a^+} g(x) = \infty \quad (\text{or } -\infty) \tag{8}
\end{gather}
$$

**Subcase 2A: The limit $A$ is finite ($A \in \mathbb{R}$).**
Let $\varepsilon > 0$ be given. Because $\lim_{x \to a^+} \frac{f'(x)}{g'(x)} = A$, there exists a point $c \in (a, b)$ such that for all $t \in (a, c)$:
$$
\begin{gather}
\left| \frac{f'(t)}{g'(t)} - A \right| < \frac{\varepsilon}{2} \iff A - \frac{\varepsilon}{2} < \frac{f'(t)}{g'(t)} < A + \frac{\varepsilon}{2} \tag{9}
\end{gather}
$$

Now choose any $x \in (a, c)$. Applying [[Proof of Cauchy's Generalized Finite-Increment Theorem|Cauchy's Generalized Finite-Increment Theorem]] on the interval $[x, c]$ guarantees the existence of an intermediate point $\xi \in (x, c) \subset (a, c)$ such that:
$$
\begin{gather}
\frac{f(x) - f(c)}{g(x) - g(c)} = \frac{f'(\xi)}{g'(\xi)} \tag{10}
\end{gather}
$$
Because $\xi \in (a, c)$, step 9 applies to $\xi$:
$$
\begin{gather}
A - \frac{\varepsilon}{2} < \frac{f(x) - f(c)}{g(x) - g(c)} < A + \frac{\varepsilon}{2} \tag{11}
\end{gather}
$$

To isolate $\frac{f(x)}{g(x)}$, express the ratio as:
$$
\begin{gather}
\frac{f(x)}{g(x)} = \frac{f(x) - f(c)}{g(x) - g(c)} \cdot \frac{g(x) - g(c)}{g(x)} + \frac{f(c)}{g(x)} = \frac{f(x) - f(c)}{g(x) - g(c)} \left(1 - \frac{g(c)}{g(x)}\right) + \frac{f(c)}{g(x)} \tag{12}
\end{gather}
$$
Because $c$ is fixed and $\lim_{x \to a^+} |g(x)| = \infty$, the terms $\frac{g(c)}{g(x)} \to 0$ and $\frac{f(c)}{g(x)} \to 0$ as $x \to a^+$. 

Define the factor $\mu(x) := 1 - \frac{g(c)}{g(x)}$ and $\nu(x) := \frac{f(c)}{g(x)}$. Then $\lim_{x \to a^+} \mu(x) = 1$ and $\lim_{x \to a^+} \nu(x) = 0$. 

Shrinking the neighborhood $(a, c)$ to $(a, c_0)$ if necessary, for all $x \in (a, c_0)$ the deviations are sufficiently small that step 11 and step 12 imply:
$$
\begin{gather}
\left| \frac{f(x)}{g(x)} - A \right| < \varepsilon, \quad \forall x \in (a, c_0) \tag{13}
\end{gather}
$$
Because $\varepsilon > 0$ was arbitrary, step 13 proves that:
$$
\begin{gather}
\lim_{x \to a^+} \frac{f(x)}{g(x)} = A \tag{14}
\end{gather}
$$

**Subcase 2B: The limit is infinite ($A = +\infty$ or $A = -\infty$).**
If $A = +\infty$, for any $M > 0$, there exists $c \in (a, b)$ such that $\frac{f'(t)}{g'(t)} > 2M$ for all $t \in (a, c)$. For any $x \in (a, c)$, Cauchy's theorem gives $\frac{f(x) - f(c)}{g(x) - g(c)} = \frac{f'(\xi)}{g'(\xi)} > 2M$. Multiplying by $\left(1 - \frac{g(c)}{g(x)}\right) \to 1$ and adding $\frac{f(c)}{g(x)} \to 0$ ensures that $\frac{f(x)}{g(x)} > M$ for all $x$ sufficiently close to $a^+$. Hence $\lim_{x \to a^+} \frac{f(x)}{g(x)} = +\infty$. An identical argument with $-f$ establishes the case $A = -\infty$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
