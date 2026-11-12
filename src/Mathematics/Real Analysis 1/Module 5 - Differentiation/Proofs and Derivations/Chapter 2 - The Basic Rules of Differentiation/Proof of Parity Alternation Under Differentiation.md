---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ be a symmetric domain around the origin, satisfying the property that $x \in E$ if and only if $-x \in E$. Let $f: E \to \mathbb{R}$ be a function differentiable on $E$.

# Corollary 1
Assume that $f$ is an even function on $E$, satisfying the identity:
$$
\begin{gather}
f(-x) = f(x), \quad \forall x \in E \tag{1}
\end{gather}
$$

Let $x \in E$. By the definition of the derivative as the limit of the difference quotient, evaluating the derivative at the point $-x \in E$ gives:
$$
\begin{gather}
f'(-x) = \lim_{h \to 0} \frac{f(-x + h) - f(-x)}{h} \tag{2}
\end{gather}
$$
where $h \in \mathbb{R} \setminus \{0\}$ is chosen sufficiently small such that $-x + h \in E$.

Rewriting the first term of the numerator using the even symmetry of step 1 yields:
$$
\begin{gather}
f(-x + h) = f(-(x - h)) = f(x - h) \tag{3}
\end{gather}
$$

Substituting step 3 and $f(-x) = f(x)$ into step 2 produces:
$$
\begin{gather}
f'(-x) = \lim_{h \to 0} \frac{f(x - h) - f(x)}{h} \tag{4}
\end{gather}
$$

Introduce the change of variable $k := -h$. As $h \to 0$, it follows that $k \to 0$ with $k \neq 0$. Substituting $h = -k$ into step 4 yields:
$$
\begin{gather}
\frac{f(x - h) - f(x)}{h} = \frac{f(x + k) - f(x)}{-k} = -\frac{f(x + k) - f(x)}{k} \tag{5}
\end{gather}
$$

Taking the limit as $k \to 0$ across step 5 and using the differentiability of $f$ at $x$ yields:
$$
\begin{gather}
f'(-x) = -\lim_{k \to 0} \frac{f(x + k) - f(x)}{k} = -f'(x) \tag{6}
\end{gather}
$$

Because $f'(-x) = -f'(x)$ holds for all $x \in E$, the derivative function $f'$ is odd on $E$.

---
# Corollary 2
Assume that $f$ is an odd function on $E$, satisfying the identity:
$$
\begin{gather}
f(-x) = -f(x), \quad \forall x \in E \tag{7}
\end{gather}
$$

Let $x \in E$. Evaluating the derivative of $f$ at $-x$ via the difference quotient gives:
$$
\begin{gather}
f'(-x) = \lim_{h \to 0} \frac{f(-x + h) - f(-x)}{h} \tag{8}
\end{gather}
$$

Applying the odd parity relation of step 7 to the terms in the numerator produces:
$$
\begin{gather}
f(-x + h) = f(-(x - h)) = -f(x - h) \tag{9}
\end{gather}
$$
and $f(-x) = -f(x)$. Substituting these relations into step 8 yields:
$$
\begin{gather}
\frac{f(-x + h) - f(-x)}{h} = \frac{-f(x - h) - (-f(x))}{h} = -\frac{f(x - h) - f(x)}{h} \tag{10}
\end{gather}
$$

Setting the increment variable $k := -h$, step 10 becomes:
$$
\begin{gather}
-\frac{f(x - h) - f(x)}{h} = -\frac{f(x + k) - f(x)}{-k} = \frac{f(x + k) - f(x)}{k} \tag{11}
\end{gather}
$$

Taking the limit as $k \to 0$ of step 11 and invoking the differentiability of $f$ at $x$ gives:
$$
\begin{gather}
f'(-x) = \lim_{k \to 0} \frac{f(x + k) - f(x)}{k} = f'(x) \tag{12}
\end{gather}
$$

Because $f'(-x) = f'(x)$ holds for all $x \in E$, the derivative function $f'$ is even on $E$.

---
# Corollary 3
Let $E \subseteq \mathbb{R}$ be an open interval symmetric around the origin with $0 \in E$.

If $f$ is an even function on $E$, then by Corollary 1, its derivative $f'$ is an odd function on $E$.

Conversely, assume that the derivative $f': E \to \mathbb{R}$ is an odd function, satisfying:
$$
\begin{gather}
f'(-x) = -f'(x), \quad \forall x \in E \tag{13}
\end{gather}
$$

Define the odd-difference auxiliary mapping $H: E \to \mathbb{R}$ by:
$$
\begin{gather}
H(x) := f(x) - f(-x), \quad \forall x \in E \tag{14}
\end{gather}
$$

Evaluating the derivative of $f(-x)$ with respect to $x$ via the substitution $k = -h$ demonstrates that:
$$
\begin{gather}
\frac{d}{dx}\big(f(-x)\big) = \lim_{h \to 0} \frac{f(-(x + h)) - f(-x)}{h} = \lim_{h \to 0} \frac{f(-x - h) - f(-x)}{h} = -f'(-x) \tag{15}
\end{gather}
$$

Differentiating the auxiliary function $H(x)$ of step 14 via the linearity of differentiation and substituting step 15 yields:
$$
\begin{gather}
H'(x) = f'(x) - \frac{d}{dx}\big(f(-x)\big) = f'(x) - \big(-f'(-x)\big) = f'(x) + f'(-x) \tag{16}
\end{gather}
$$

Applying the odd condition of step 13 to the term $f'(-x)$ in step 16 gives:
$$
\begin{gather}
H'(x) = f'(x) + \big(-f'(x)\big) = 0, \quad \forall x \in E \tag{17}
\end{gather}
$$

Because $E$ is an open connected interval and $H'(x) = 0$ identically throughout $E$, the Mean Value Theorem guarantees that $H(x)$ is constant on $E$:
$$
\begin{gather}
H(x) = C, \quad \forall x \in E \tag{18}
\end{gather}
$$
for some real constant $C \in \mathbb{R}$.

Evaluating $H(x)$ at the origin $x = 0 \in E$ yields:
$$
\begin{gather}
C = H(0) = f(0) - f(-0) = f(0) - f(0) = 0 \tag{19}
\end{gather}
$$

Substituting $C = 0$ from step 19 into step 18 reveals that:
$$
\begin{gather}
H(x) = f(x) - f(-x) = 0 \implies f(-x) = f(x), \quad \forall x \in E \tag{20}
\end{gather}
$$

Thus, $f$ is an even function on $E$, completing the equivalence.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
