---
dg-publish: true
---
Let $\Psi: \mathbb{R} \to \mathbb{R}$ be the candidate bump function defined by:
$$
\begin{gather}
\Psi(x) := \begin{cases} \exp\left(-\frac{1}{(1+x)^2} - \frac{1}{(1-x)^2}\right) & \text{if } x \in (-1, 1) \\[3mm] 0 & \text{if } |x| \ge 1 \end{cases} \tag{1}
\end{gather}
$$

**Even Parity of the Mapping:**
Evaluating $\Psi$ at $-x$ for any $x \in (-1, 1)$ gives:
$$
\begin{gather}
\Psi(-x) = \exp\left(-\frac{1}{(1+(-x))^2} - \frac{1}{(1-(-x))^2}\right) = \exp\left(-\frac{1}{(1-x)^2} - \frac{1}{(1+x)^2}\right) = \Psi(x) \tag{2}
\end{gather}
$$

Because $\Psi(x) = 0 = \Psi(-x)$ for $|x| \ge 1$, $\Psi$ is an even function on $\mathbb{R}$: $\Psi(-x) = \Psi(x)$ for all $x \in \mathbb{R}$.

**Smoothness on Open Subdomains:**
1. On the interior interval $(-1, 1)$, the functions $(1+x)^2$ and $(1-x)^2$ are strictly positive and non-vanishing. The argument:
$$
\begin{gather}
w(x) := -\frac{1}{(1+x)^2} - \frac{1}{(1-x)^2} \tag{3}
\end{gather}
$$
is a rational function whose denominator has roots exclusively at $x = \pm 1$. Thus, $w \in C^\infty((-1, 1))$. Because the natural exponential function $\exp(u)$ is smooth on $\mathbb{R}$, the composite function $\Psi(x) = \exp(w(x))$ is infinitely differentiable on $(-1, 1)$ by the [[Proof of The Chain Rule|Chain Rule]]: $\Psi \in C^\infty((-1, 1))$.

2. On the exterior open set $(-\infty, -1) \cup (1, \infty)$, $\Psi(x) \equiv 0$ is identically constant. Thus, all derivatives exist and vanish identically: $\Psi^{(n)}(x) = 0$ for all $n \in \mathbb{N}_0$, confirming that $\Psi \in C^\infty((-\infty, -1) \cup (1, \infty))$.

**Regularity at the Boundary Point $x = 1$:**
It remains to verify infinite differentiability at the boundary interface $x = 1$. By symmetry from step 2, the behavior at $x = -1$ is completely analogous.

For $x > 1$, $\Psi(x) \equiv 0$, which ensures that all right-handed derivatives at $x = 1$ vanish:
$$
\begin{gather}
\Psi^{(n)}_+(1) = 0, \quad \forall n \in \mathbb{N}_0 \tag{4}
\end{gather}
$$

Now consider the left-handed approach for $x \in (0, 1)$. Introduce the displacement variable $h := 1 - x \in (0, 1)$. As $x \to 1^-$, $h \to 0^+$.

Expressing the factors in step 1 in terms of $h$ yields:
$$
\begin{gather}
1 - x = h \quad \text{and} \quad 1 + x = 2 - h \tag{5}
\end{gather}
$$

Factoring the exponential in step 1 produces:
$$
\begin{gather}
\Psi(1 - h) = \exp\left(-\frac{1}{(2-h)^2}\right) \exp\left(-\frac{1}{h^2}\right), \quad h \in (0, 1) \tag{6}
\end{gather}
$$

Define the functions $g(h) := \exp\left(-\frac{1}{(2-h)^2}\right)$ and $f(h) := \exp\left(-\frac{1}{h^2}\right)$ for $h \in (0, 1)$. 

The factor $g(h)$ is smooth on $(-1, 2)$ with $g(0) = e^{-1/4} > 0$, guaranteeing that $g$ and all of its derivatives $g^{(k)}$ are continuous and uniformly bounded on $[0, 1/2]$:
$$
\begin{gather}
\sup_{h \in [0, 1/2]} \big|g^{(k)}(h)\big| \le M_k < \infty, \quad \forall k \in \mathbb{N}_0 \tag{7}
\end{gather}
$$

The second factor $f(h) = \exp(-1/h^2)$ is the classical flat function analyzed in the [[Proof of The Cauchy Flatness Theorem|Cauchy Flatness Theorem]]. By the Cauchy Flatness Theorem, for any integer $m \ge 0$ and polynomial $Q(t)$:
$$
\begin{gather}
\lim_{h \to 0^+} \frac{1}{h^m} f(h) = \lim_{h \to 0^+} \frac{1}{h^m} \exp\left(-\frac{1}{h^2}\right) = 0 \tag{8}
\end{gather}
$$

By the [[Proof of The General Leibniz Rule|General Leibniz Rule]], the $n$-th derivative of $\Psi(1 - h) = g(h)f(h)$ with respect to $h$ satisfies:
$$
\begin{gather}
\frac{d^n}{dh^n}\big[g(h)f(h)\big] = \sum_{k=0}^n \binom{n}{k} g^{(n-k)}(h) f^{(k)}(h) \tag{9}
\end{gather}
$$

From step 2 of the [[Proof of The Cauchy Flatness Theorem|Cauchy Flatness Theorem]], each derivative $f^{(k)}(h)$ takes the form $P_k(1/h)\exp(-1/h^2)$ for some polynomial $P_k$. Combining this structure with the boundedness of $g^{(n-k)}$ in step 7 and the fundamental limit of step 8 yields:
$$
\begin{gather}
\lim_{h \to 0^+} \frac{d^n}{dh^n}\big[g(h)f(h)\big] = 0, \quad \forall n \in \mathbb{N}_0 \tag{10}
\end{gather}
$$

Because $\frac{d}{dx} = -\frac{d}{dh}$, taking the left-hand limit of the derivative of $\Psi$ as $x \to 1^-$ yields:
$$
\begin{gather}
\lim_{x \to 1^-} \Psi^{(n)}(x) = (-1)^n \lim_{h \to 0^+} \frac{d^n}{dh^n}\big[g(h)f(h)\big] = 0 \tag{11}
\end{gather}
$$

By induction on difference quotients at $x = 1$, the left-handed derivative satisfies:
$$
\begin{gather}
\Psi^{(n)}_-(1) = \lim_{x \to 1^-} \frac{\Psi^{(n-1)}(x) - \Psi^{(n-1)}(1)}{x - 1} = 0 \tag{12}
\end{gather}
$$

Because the left-handed derivative of step 12 matches the right-handed derivative of step 4:
$$
\begin{gather}
\Psi^{(n)}_-(1) = \Psi^{(n)}_+(1) = 0 \implies \Psi^{(n)}(1) = 0, \quad \forall n \in \mathbb{N}_0 \tag{13}
\end{gather}
$$

By the even symmetry established in step 2, the identical analysis applies at $x = -1$, yielding:
$$
\begin{gather}
\Psi^{(n)}(-1) = 0, \quad \forall n \in \mathbb{N}_0 \tag{14}
\end{gather}
$$

Thus, $\Psi$ is differentiable to all orders at every point $x \in \mathbb{R}$, proving $\Psi \in C^\infty(\mathbb{R})$.

**Compact Support:**
Because the natural exponential mapping satisfies $\exp(u) > 0$ for all real arguments $u \in \mathbb{R}$, the function $\Psi$ is strictly positive throughout $(-1, 1)$:
$$
\begin{gather}
\{x \in \mathbb{R} \mid \Psi(x) \neq 0\} = (-1, 1) \tag{15}
\end{gather}
$$

The support of $\Psi$ is defined as the closure of the non-zero set:
$$
\begin{gather}
\operatorname{supp}(\Psi) := \overline{\{x \in \mathbb{R} \mid \Psi(x) \neq 0\}} = \overline{(-1, 1)} = [-1, 1] \tag{16}
\end{gather}
$$

Because $[-1, 1]$ is closed and bounded in the Euclidean metric space $\mathbb{R}$, it is compact by the Heine-Borel Theorem. 

Therefore, $\Psi$ is a compactly supported smooth bump function on $\mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
