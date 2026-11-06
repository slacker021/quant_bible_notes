---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f, g: E \to \mathbb{R}$, and let $a \in E$. 

Suppose that $f$ and $g$ are both continuous at the point $a$. If $a \in E \setminus E'$ is an isolated point of $E$, then every mapping on $E$ is vacuously continuous at $a$ by virtue of [[Proof of the Vacuous Continuity at Isolated Domain Points]]. 

Therefore, assume without loss of generality that $a \in E \cap E'$ is an accumulation point of $E$. By the [[Proof of the Commutation of Continuous Mappings with Accumulation Limits]], continuity of $f$ and $g$ at $a$ is equivalent to:
$$
\begin{gather}
\lim_{E \ni x \to a} f(x) = f(a) \quad \text{and} \quad \lim_{E \ni x \to a} g(x) = g(a) \tag{1}
\end{gather}
$$

---
# Theorem 1

Let $\alpha, \beta \in \mathbb{R}$. By the algebraic limit theorem for linear combinations of functions:
$$
\begin{gather}
\lim_{E \ni x \to a} (\alpha f + \beta g)(x) = \lim_{E \ni x \to a} \big(\alpha f(x) + \beta g(x)\big) = \alpha \lim_{E \ni x \to a} f(x) + \beta \lim_{E \ni x \to a} g(x) \tag{2}
\end{gather}
$$

Substituting the functional limits of step 1 into step 2:
$$
\begin{gather}
\lim_{E \ni x \to a} (\alpha f + \beta g)(x) = \alpha f(a) + \beta g(a) = (\alpha f + \beta g)(a) \tag{3}
\end{gather}
$$

Because the limit of the linear combination equals its evaluation at $a$, the function $\alpha f + \beta g$ is continuous at $a$.

---
# Theorem 2

By the algebraic limit theorem for pointwise products of functions:
$$
\begin{gather}
\lim_{E \ni x \to a} (f \cdot g)(x) = \lim_{E \ni x \to a} \big(f(x) g(x)\big) = \left(\lim_{E \ni x \to a} f(x)\right) \cdot \left(\lim_{E \ni x \to a} g(x)\right) \tag{4}
\end{gather}
$$

Substituting the values of step 1 into step 4:
$$
\begin{gather}
\lim_{E \ni x \to a} (f \cdot g)(x) = f(a) \cdot g(a) = (f \cdot g)(a) \tag{5}
\end{gather}
$$

Thus, the pointwise product $f \cdot g$ is continuous at $a$.

---
# Theorem 3

Suppose $g(a) \ne 0$. By [[Proof of Local Neighborhood Invariance of Sign|local sign preservation]], there exists an open neighborhood $U(a)$ such that $g(x) \ne 0$ for all $x \in E \cap U(a)$. 

By the algebraic limit theorem for quotients of functions where the denominator limit is non-zero:
$$
\begin{gather}
\lim_{E \ni x \to a} \left(\frac{f}{g}\right)(x) = \lim_{E \ni x \to a} \frac{f(x)}{g(x)} = \frac{\lim_{E \ni x \to a} f(x)}{\lim_{E \ni x \to a} g(x)} \tag{6}
\end{gather}
$$

Substituting the limits of step 1 into step 6:
$$
\begin{gather}
\lim_{E \ni x \to a} \left(\frac{f}{g}\right)(x) = \frac{f(a)}{g(a)} = \left(\frac{f}{g}\right)(a) \tag{7}
\end{gather}
$$

Consequently, the quotient mapping $f / g$ is continuous at $a$.

---
# Theorem 4

By the reverse triangle inequality, for all $x \in E$:
$$
\begin{gather}
\big| |f|(x) - |f|(a) \big| = \big| |f(x)| - |f(a)| \big| \le |f(x) - f(a)| \tag{8}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given. Because $f$ is continuous at $a$, there exists $\delta > 0$ such that $|x - a| < \delta$ with $x \in E$ implies $|f(x) - f(a)| < \varepsilon$. 

Applying step 8 demonstrates that for the same distance $\delta > 0$:
$$
\begin{gather}
\forall x \in E, \quad |x - a| < \delta \implies \big| |f|(x) - |f|(a) \big| < \varepsilon \tag{9}
\end{gather}
$$

Therefore, the absolute value function $|f|$ is continuous at $a$.

---
# Theorem 5

The pointwise maximum and minimum of two real functions can be expressed through algebraic identities involving absolute values:
$$
\begin{gather}
\max(f, g)(x) = \frac{f(x) + g(x) + |f(x) - g(x)|}{2} \tag{10}
\end{gather}
$$
$$
\begin{gather}
\min(f, g)(x) = \frac{f(x) + g(x) - |f(x) - g(x)|}{2} \tag{11}
\end{gather}
$$

By Theorem 1, the difference $f - g$ is continuous at $a$. 

By Theorem 4, the absolute value $|f - g|$ is continuous at $a$. 

Applying Theorem 1 once more to the sum and difference of the continuous functions in step 10 and step 11 demonstrates that $\max(f, g)$ and $\min(f, g)$ are both continuous at $a$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
