---
dg-publish: true
---
Let $f: \mathbb{R} \to \mathbb{R}$ be defined by:
$$
\begin{gather}
f(x) := \begin{cases} \exp\left(-\frac{1}{x^2}\right) & \text{if } x \neq 0 \\[2mm] 0 & \text{if } x = 0 \end{cases} \tag{1}
\end{gather}
$$

**Structural Representation of Derivatives on $\mathbb{R} \setminus \{0\}$:**
On the open punctured domain $\mathbb{R} \setminus \{0\}$, $f$ is the composition of the smooth exponential function $\exp(u)$ and the smooth rational function $u(x) = -x^{-2}$. Consequently, $f \in C^\infty(\mathbb{R} \setminus \{0\})$.

To determine the algebraic form of the $n$-th derivative for $x \neq 0$, let $n \in \mathbb{N}_0$. It can be shown by induction that there exists a real polynomial $P_n(t)$ such that:
$$
\begin{gather}
f^{(n)}(x) = P_n\left(\frac{1}{x}\right) \exp\left(-\frac{1}{x^2}\right), \quad \forall x \neq 0 \tag{2}
\end{gather}
$$

For $n = 0$, setting $P_0(t) \equiv 1$ satisfies step 2.

Differentiating step 2 via the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]] and the [[Proof of The Chain Rule|Chain Rule]] yields:
$$
\begin{gather}
f^{(n+1)}(x) = \frac{d}{dx}\left[P_n\left(\frac{1}{x}\right)\right] \exp\left(-\frac{1}{x^2}\right) + P_n\left(\frac{1}{x}\right) \frac{d}{dx}\left[\exp\left(-\frac{1}{x^2}\right)\right] \tag{3}
\end{gather}
$$

Evaluating the constituent derivatives gives:
$$
\begin{gather}
\frac{d}{dx}\left[P_n\left(\frac{1}{x}\right)\right] = P_n'\left(\frac{1}{x}\right) \left(-\frac{1}{x^2}\right) = -\frac{1}{x^2} P_n'\left(\frac{1}{x}\right) \tag{4}
\end{gather}
$$
$$
\begin{gather}
\frac{d}{dx}\left[\exp\left(-\frac{1}{x^2}\right)\right] = \exp\left(-\frac{1}{x^2}\right) \left(\frac{2}{x^3}\right) = \frac{2}{x^3} \exp\left(-\frac{1}{x^2}\right) \tag{5}
\end{gather}
$$

Substituting step 4 and step 5 into step 3 produces:
$$
\begin{gather}
f^{(n+1)}(x) = \left[ \frac{2}{x^3} P_n\left(\frac{1}{x}\right) - \frac{1}{x^2} P_n'\left(\frac{1}{x}\right) \right] \exp\left(-\frac{1}{x^2}\right) \tag{6}
\end{gather}
$$

Defining the polynomial $P_{n+1}(t)$ by the recurrence:
$$
\begin{gather}
P_{n+1}(t) := 2t^3 P_n(t) - t^2 P_n'(t) \tag{7}
\end{gather}
$$
step 6 takes the form $f^{(n+1)}(x) = P_{n+1}(1/x) \exp(-1/x^2)$, confirming that step 2 holds for all $n \in \mathbb{N}_0$.

**Fundamental Limit of Exponential Flatness:**
Let $k \in \mathbb{R}$ be an arbitrary real exponent. Consider the limit:
$$
\begin{gather}
\lim_{x \to 0} \frac{1}{|x|^k} \exp\left(-\frac{1}{x^2}\right) \tag{8}
\end{gather}
$$

Introduce the substitution $u := \frac{1}{x^2}$. As $x \to 0$, $u \to +\infty$, and $|x| = u^{-1/2}$, so that $|x|^{-k} = u^{k/2}$. Step 8 becomes:
$$
\begin{gather}
\lim_{u \to +\infty} u^{k/2} e^{-u} = \lim_{u \to +\infty} \frac{u^{k/2}}{e^u} \tag{9}
\end{gather}
$$

Because the exponential function $e^u$ grows faster than any polynomial power $u^\alpha$ as $u \to +\infty$ (as established in [[Chapter 2 - Limits of Functions|Module 3, Chapter 2]]), the limit in step 9 evaluates to zero:
$$
\begin{gather}
\lim_{u \to +\infty} \frac{u^{k/2}}{e^u} = 0 \implies \lim_{x \to 0} \frac{1}{x^k} \exp\left(-\frac{1}{x^2}\right) = 0 \tag{10}
\end{gather}
$$
for every $k \in \mathbb{N}_0$.

By the linearity of limits, for any polynomial $Q(t) = \sum_{j=0}^m c_j t^j$:
$$
\begin{gather}
\lim_{x \to 0} Q\left(\frac{1}{x}\right) \exp\left(-\frac{1}{x^2}\right) = \sum_{j=0}^m c_j \lim_{x \to 0} \frac{1}{x^j} \exp\left(-\frac{1}{x^2}\right) = 0 \tag{11}
\end{gather}
$$

**Existence and Vanishing of Higher Derivatives at $x = 0$:**
The property that $f^{(n)}(0) = 0$ for all $n \in \mathbb{N}_0$ is proven by mathematical induction.

*Base Case ($n = 0$):* By definition in step 1, $f(0) = 0$.

*Induction Hypothesis:* Assume that for some integer $n \ge 0$, the $n$-th derivative at the origin exists and satisfies $f^{(n)}(0) = 0$.

*Induction Step:* Evaluate the $(n+1)$-th derivative at the origin via the limit of the difference quotient:
$$
\begin{gather}
f^{(n+1)}(0) = \lim_{x \to 0} \frac{f^{(n)}(x) - f^{(n)}(0)}{x - 0} \tag{12}
\end{gather}
$$

Substituting $f^{(n)}(0) = 0$ and the formula for $f^{(n)}(x)$ from step 2 for $x \neq 0$ into step 12 gives:
$$
\begin{gather}
f^{(n+1)}(0) = \lim_{x \to 0} \frac{P_n\left(\frac{1}{x}\right) \exp\left(-\frac{1}{x^2}\right)}{x} = \lim_{x \to 0} \left[\frac{1}{x} P_n\left(\frac{1}{x}\right)\right] \exp\left(-\frac{1}{x^2}\right) \tag{13}
\end{gather}
$$

Define the auxiliary polynomial $Q(t) := t P_n(t)$. Step 13 can be expressed as:
$$
\begin{gather}
f^{(n+1)}(0) = \lim_{x \to 0} Q\left(\frac{1}{x}\right) \exp\left(-\frac{1}{x^2}\right) \tag{14}
\end{gather}
$$

Applying the fundamental limit property of step 11 to the polynomial $Q(t)$ yields:
$$
\begin{gather}
f^{(n+1)}(0) = 0 \tag{15}
\end{gather}
$$

By mathematical induction, $f^{(n)}(0) = 0$ exists and vanishes for every $n \in \mathbb{N}_0$.

**Continuity of Every Derivative on $\mathbb{R}$:**
For each $n \in \mathbb{N}_0$, $f^{(n)}$ is continuous on $\mathbb{R} \setminus \{0\}$. At the origin, applying step 11 to $P_n$ gives:
$$
\begin{gather}
\lim_{x \to 0} f^{(n)}(x) = \lim_{x \to 0} P_n\left(\frac{1}{x}\right) \exp\left(-\frac{1}{x^2}\right) = 0 = f^{(n)}(0) \tag{16}
\end{gather}
$$
confirming that $f^{(n)}$ is continuous at $x = 0$.

Because every derivative $f^{(n)}$ exists and is continuous on the entire real line $\mathbb{R}$, $f \in C^\infty(\mathbb{R})$, with $f^{(n)}(0) = 0$ for all $n \in \mathbb{N}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
