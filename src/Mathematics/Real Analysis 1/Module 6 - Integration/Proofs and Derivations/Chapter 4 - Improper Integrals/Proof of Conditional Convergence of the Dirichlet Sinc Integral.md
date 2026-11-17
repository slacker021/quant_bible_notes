---
dg-publish: true
---
Let the sinc integrand $f: (0, \infty) \to \mathbb{R}$ be defined by:
$$
\begin{gather}
f(x) := \frac{\sin x}{x} \tag{1}
\end{gather}
$$
The improper integral under investigation is:
$$
\begin{gather}
I := \int_0^\infty \frac{\sin x}{x}\,dx := \lim_{\substack{\varepsilon \to 0^+ \\ B \to \infty}} \int_\varepsilon^B \frac{\sin x}{x}\,dx \tag{2}
\end{gather}
$$
---
# Part 1

### Step 1
Consider the behavior of $f(x)$ as $x \to 0^+$. By the fundamental trigonometric limit:
$$
\begin{gather}
\lim_{x \to 0^+} \frac{\sin x}{x} = 1 \tag{3}
\end{gather}
$$

Extend $f$ to the closed domain $[0, \infty)$ by defining the value at zero:
$$
\begin{gather}
\widetilde{f}(x) := \begin{cases} \dfrac{\sin x}{x}, & x > 0 \\[2mm] 1, & x = 0 \end{cases} \tag{4}
\end{gather}
$$

By step 3, $\lim_{x \to 0^+} \widetilde{f}(x) = 1 = \widetilde{f}(0)$, which establishes that $\widetilde{f}$ is continuous on $[0, 1]$.

Because every continuous function on a compact interval is Riemann integrable, $\widetilde{f} \in \mathcal{R}[0, 1]$. Consequently, the singularity at the origin is removable, and the integral across $[0, 1]$ is a proper Riemann integral:
$$
\begin{gather}
I_{\text{head}} := \int_0^1 \frac{\sin x}{x}\,dx = \int_0^1 \widetilde{f}(x)\,dx \in \mathbb{R} \tag{5}
\end{gather}
$$

By interval additivity, for any parameter $B \ge 1$:
$$
\begin{gather}
\int_0^B \widetilde{f}(x)\,dx = \int_0^1 \widetilde{f}(x)\,dx + \int_1^B \frac{\sin x}{x}\,dx \tag{6}
\end{gather}
$$

The convergence of the improper integral $I$ is therefore equivalent to the convergence of the tail integral:
$$
\begin{gather}
I_{\text{tail}} := \int_1^\infty \frac{\sin x}{x}\,dx = \lim_{B \to \infty} \int_1^B \frac{\sin x}{x}\,dx \tag{7}
\end{gather}
$$
### Step 2
On the domain $[1, \infty)$, factor the integrand into the product $u(x)v(x)$, where:
$$
\begin{gather}
u(x) := \sin x, \qquad v(x) := \frac{1}{x} \tag{8}
\end{gather}
$$

The functions $u$ and $v$ satisfy the hypotheses of Dirichlet's Test for Improper Integrals:
1. Primitive boundedness of $u$: For every $B \ge 1$, evaluating the primitive via the Newton-Leibniz formula:
$$
\begin{gather}
\int_1^B u(x)\,dx = \int_1^B \sin x\,dx = [-\cos x]_1^B = \cos 1 - \cos B \tag{9}
\end{gather}
$$
Applying the triangle inequality to step 9:
$$
\begin{gather}
\left| \int_1^B \sin x\,dx \right| = |\cos 1 - \cos B| \le |\cos 1| + |\cos B| \le 1 + 1 = 2 \tag{10}
\end{gather}
$$
Thus, the primitive of $u$ is uniformly bounded on $[1, \infty)$ by the constant $M = 2$.

2. Monotonic decay of $v$: The function $v(x) = \frac{1}{x}$ is continuously differentiable on $[1, \infty)$ with derivative:
$$
\begin{gather}
v'(x) = -\frac{1}{x^2} < 0 \quad \text{for all } x \ge 1 \tag{11}
\end{gather}
$$
Hence $v$ is strictly monotonically decreasing on $[1, \infty)$. Furthermore:
$$
\begin{gather}
\lim_{x \to \infty} v(x) = \lim_{x \to \infty} \frac{1}{x} = 0 \tag{12}
\end{gather}
$$

Because both conditions of Dirichlet's Test for Improper Integrals are satisfied, the tail improper integral converges to a finite real value:
$$
\begin{gather}
I_{\text{tail}} = \int_1^\infty \frac{\sin x}{x}\,dx \in \mathbb{R} \tag{13}
\end{gather}
$$

Taking the limit as $B \to \infty$ in step 6 and applying step 5 and step 13:
$$
\begin{gather}
\int_0^\infty \frac{\sin x}{x}\,dx = I_{\text{head}} + I_{\text{tail}} \in \mathbb{R} \tag{14}
\end{gather}
$$
which confirms that the improper integral converges.

---
# Part 2
Consider the improper integral of the absolute value:
$$
\begin{gather}
\int_0^\infty \left| \frac{\sin x}{x} \right|\,dx = \lim_{B \to \infty} \int_0^B \frac{|\sin x|}{x}\,dx \tag{15}
\end{gather}
$$

### Step 1
Let $n \in \mathbb{N}$ be an arbitrary positive integer. Partition the interval $[0, n\pi]$ into $n$ contiguous subintervals of length $\pi$:
$$
\begin{gather}
[0, n\pi] = \bigcup_{k=1}^n [(k - 1)\pi, k\pi] \tag{16}
\end{gather}
$$

By the interval additivity of the Riemann integral:
$$
\begin{gather}
\int_0^{n\pi} \frac{|\sin x|}{x}\,dx = \sum_{k=1}^n \int_{(k - 1)\pi}^{k\pi} \frac{|\sin x|}{x}\,dx \tag{17}
\end{gather}
$$
### Step 2
On the $k$-th subinterval $[(k - 1)\pi, k\pi]$, the variable $x$ satisfies $x \le k\pi$. Because $|\sin x| \ge 0$:
$$
\begin{gather}
\frac{|\sin x|}{x} \ge \frac{|\sin x|}{k\pi} \quad \text{for all } x \in [(k - 1)\pi, k\pi] \tag{18}
\end{gather}
$$

Integrating the inequality of step 18 across $[(k - 1)\pi, k\pi]$:
$$
\begin{gather}
\int_{(k - 1)\pi}^{k\pi} \frac{|\sin x|}{x}\,dx \ge \frac{1}{k\pi} \int_{(k - 1)\pi}^{k\pi} |\sin x|\,dx \tag{19}
\end{gather}
$$

Apply the affine substitution $x = t + (k - 1)\pi$ to the integral on the right-hand side of step 19. The differential is $dx = dt$, and the limits transform to $t \in [0, \pi]$. Using the angle-addition formula for the sine function:
$$
\begin{gather}
\sin\big( t + (k - 1)\pi \big) = \sin t \cos\big( (k - 1)\pi \big) + \cos t \sin\big( (k - 1)\pi \big) = (-1)^{k-1} \sin t \tag{20}
\end{gather}
$$

Taking the absolute value in step 20, because $\sin t \ge 0$ for all $t \in [0, \pi]$:
$$
\begin{gather}
\big| \sin\big( t + (k - 1)\pi \big) \big| = |(-1)^{k-1}| |\sin t| = \sin t \tag{21}
\end{gather}
$$

Evaluating the integral:
$$
\begin{gather}
\int_{(k - 1)\pi}^{k\pi} |\sin x|\,dx = \int_0^\pi \sin t\,dt = [-\cos t]_0^\pi = -\cos\pi - (-\cos 0) = 1 + 1 = 2 \tag{22}
\end{gather}
$$

Substituting step 22 into step 19 yields the subinterval bound:
$$
\begin{gather}
\int_{(k - 1)\pi}^{k\pi} \frac{|\sin x|}{x}\,dx \ge \frac{2}{\pi k} \tag{23}
\end{gather}
$$
### Step 3
Substituting the bound of step 23 into the summation of step 17:
$$
\begin{gather}
\int_0^{n\pi} \frac{|\sin x|}{x}\,dx \ge \sum_{k=1}^n \frac{2}{\pi k} = \frac{2}{\pi} \sum_{k=1}^n \frac{1}{k} \tag{24}
\end{gather}
$$

For an arbitrary parameter $B \ge \pi$, let $n := \left\lfloor \frac{B}{\pi} \right\rfloor \in \mathbb{N}$ denote the integer part. Then $n\pi \le B$.

Because $\frac{|\sin x|}{x} \ge 0$, interval additivity and positivity imply:
$$
\begin{gather}
\int_0^B \frac{|\sin x|}{x}\,dx \ge \int_0^{n\pi} \frac{|\sin x|}{x}\,dx \ge \frac{2}{\pi} \sum_{k=1}^n \frac{1}{k} \tag{25}
\end{gather}
$$

As $B \to \infty$, the index $n = \left\lfloor \frac{B}{\pi} \right\rfloor \to \infty$. By the divergence of the harmonic series to $+\infty$:
$$
\begin{gather}
\lim_{n \to \infty} \sum_{k=1}^n \frac{1}{k} = +\infty \tag{26}
\end{gather}
$$

Taking the limit as $B \to \infty$ in step 25:
$$
\begin{gather}
\lim_{B \to \infty} \int_0^B \frac{|\sin x|}{x}\,dx \ge \frac{2}{\pi} \lim_{n \to \infty} \sum_{k=1}^n \frac{1}{k} = +\infty \tag{27}
\end{gather}
$$

Thus, the improper integral of the absolute value diverges to $+\infty$:
$$
\begin{gather}
\int_0^\infty \left| \frac{\sin x}{x} \right|\,dx = +\infty \tag{28}
\end{gather}
$$

Because $\int_0^\infty \frac{\sin x}{x}\,dx$ converges (step 14) while $\int_0^\infty \left| \frac{\sin x}{x} \right|\,dx = +\infty$ (step 28), the improper integral of the sinc function is conditionally convergent.

---
# Part 3

### Step 1
For each positive integer $n \in \mathbb{N}$, consider the Dirichlet trigonometric sum:
$$
\begin{gather}
D_n(t) := \frac{1}{2} + \sum_{k=1}^n \cos(kt) \tag{29}
\end{gather}
$$

Multiplying step 29 by $2\sin(t/2)$ and applying the product-to-sum identity $2\cos(kt)\sin(t/2) = \sin((k + 1/2)t) - \sin((k - 1/2)t)$:
$$
\begin{gather}
2\sin(t/2) D_n(t) = \sin(t/2) + \sum_{k=1}^n \Big( \sin((k + 1/2)t) - \sin((k - 1/2)t) \Big) \tag{30}
\end{gather}
$$

The sum in step 30 telescopes, leaving:
$$
\begin{gather}
2\sin(t/2) D_n(t) = \sin((n + 1/2)t) \implies D_n(t) = \frac{\sin((n + 1/2)t)}{2\sin(t/2)} \tag{31}
\end{gather}
$$

Integrating step 29 across $[0, \pi]$:
$$
\begin{gather}
\int_0^\pi D_n(t)\,dt = \int_0^\pi \frac{1}{2}\,dt + \sum_{k=1}^n \int_0^\pi \cos(kt)\,dt = \frac{\pi}{2} + \sum_{k=1}^n \left[ \frac{\sin(kt)}{k} \right]_0^\pi = \frac{\pi}{2} + 0 = \frac{\pi}{2} \tag{32}
\end{gather}
$$

Applying the change of variable $t = 2u$ ($dt = 2\,du$) to step 31 and step 32:
$$
\begin{gather}
\int_0^\pi \frac{\sin((n + 1/2)t)}{2\sin(t/2)}\,dt = \int_0^{\pi/2} \frac{\sin((2n + 1)u)}{2\sin u} \cdot 2\,du = \int_0^{\pi/2} \frac{\sin((2n + 1)u)}{\sin u}\,du = \frac{\pi}{2} \tag{33}
\end{gather}
$$

### Step 2
Define the auxiliary function $h: [0, \pi/2] \to \mathbb{R}$ by:
$$
\begin{gather}
h(u) := \begin{cases} \dfrac{1}{u} - \dfrac{1}{\sin u} = \dfrac{\sin u - u}{u \sin u}, & u \in (0, \pi/2] \\[3mm] 0, & u = 0 \end{cases} \tag{34}
\end{gather}
$$

Applying Taylor's Theorem to $\sin u$ near $u = 0$:
$$
\begin{gather}
\sin u = u - \frac{u^3}{6} + \mathcal{O}(u^5) \tag{35}
\end{gather}
$$

Substituting step 35 into step 34:
$$
\begin{gather}
\lim_{u \to 0^+} h(u) = \lim_{u \to 0^+} \frac{-\frac{u^3}{6} + \mathcal{O}(u^5)}{u^2 + \mathcal{O}(u^4)} = \lim_{u \to 0^+} \left( -\frac{u}{6} + \mathcal{O}(u^3) \right) = 0 = h(0) \tag{36}
\end{gather}
$$
Thus, $h$ is continuous at $u = 0$.

Computing the derivative of $h$ on $(0, \pi/2]$:
$$
\begin{gather}
h'(u) = -\frac{1}{u^2} + \frac{\cos u}{\sin^2 u} = \frac{u^2 \cos u - \sin^2 u}{u^2 \sin^2 u} \tag{37}
\end{gather}
$$

Expanding the numerator and denominator near $u = 0$ via Taylor expansions:
$$
\begin{gather}
u^2 \cos u - \sin^2 u = u^2 \left( 1 - \frac{u^2}{2} + \mathcal{O}(u^4) \right) - \left( u - \frac{u^3}{6} + \mathcal{O}(u^5) \right)^2 = -\frac{u^4}{6} + \mathcal{O}(u^6) \tag{38}
\end{gather}
$$
and:
$$
\begin{gather}
u^2 \sin^2 u = u^4 + \mathcal{O}(u^6) \tag{39}
\end{gather}
$$

Taking the limit of step 37 as $u \to 0^+$:
$$
\begin{gather}
\lim_{u \to 0^+} h'(u) = \lim_{u \to 0^+} \frac{-\frac{u^4}{6} + \mathcal{O}(u^6)}{u^4 + \mathcal{O}(u^6)} = -\frac{1}{6} \tag{40}
\end{gather}
$$

Because $h'$ is continuous on $(0, \pi/2]$ and possesses a finite right-hand limit at $u = 0$, $h \in C^1[0, \pi/2]$.

### Step 3
By the Riemann-Lebesgue Lemma for continuously differentiable functions on compact intervals, for any $h \in C^1[0, \pi/2]$:
$$
\begin{gather}
\lim_{\lambda \to \infty} \int_0^{\pi/2} h(u) \sin(\lambda u)\,du = 0 \tag{41}
\end{gather}
$$

Setting $\lambda = 2n + 1$ with $n \in \mathbb{N}$:
$$
\begin{gather}
\lim_{n \to \infty} \int_0^{\pi/2} h(u) \sin((2n + 1)u)\,du = 0 \tag{42}
\end{gather}
$$

Decomposing the sinc integral on $[0, \pi/2]$ using step 34:
$$
\begin{gather}
\frac{\sin((2n + 1)u)}{u} = \frac{\sin((2n + 1)u)}{\sin u} + h(u) \sin((2n + 1)u) \tag{43}
\end{gather}
$$

Integrating step 43 across $[0, \pi/2]$:
$$
\begin{gather}
\int_0^{\pi/2} \frac{\sin((2n + 1)u)}{u}\,du = \int_0^{\pi/2} \frac{\sin((2n + 1)u)}{\sin u}\,du + \int_0^{\pi/2} h(u) \sin((2n + 1)u)\,du \tag{44}
\end{gather}
$$

Substituting the identity of step 33 into step 44:
$$
\begin{gather}
\int_0^{\pi/2} \frac{\sin((2n + 1)u)}{u}\,du = \frac{\pi}{2} + \int_0^{\pi/2} h(u) \sin((2n + 1)u)\,du \tag{45}
\end{gather}
$$

Taking the limit as $n \to \infty$ in step 45 and applying step 42:
$$
\begin{gather}
\lim_{n \to \infty} \int_0^{\pi/2} \frac{\sin((2n + 1)u)}{u}\,du = \frac{\pi}{2} + 0 = \frac{\pi}{2} \tag{46}
\end{gather}
$$

### Step 4
Apply the change of variable $x = (2n + 1)u$ to the integral in step 46. The differential is $dx = (2n + 1)\,du$, and the ratio transforms as:
$$
\begin{gather}
\frac{\sin((2n + 1)u)}{u}\,du = \frac{\sin x}{\frac{x}{2n + 1}} \cdot \frac{dx}{2n + 1} = \frac{\sin x}{x}\,dx \tag{47}
\end{gather}
$$

The limits of integration transform from $u = 0$ to $x = 0$, and from $u = \pi/2$ to $x = (n + 1/2)\pi$. Therefore:
$$
\begin{gather}
\int_0^{\pi/2} \frac{\sin((2n + 1)u)}{u}\,du = \int_0^{(n + 1/2)\pi} \frac{\sin x}{x}\,dx \tag{48}
\end{gather}
$$

Substituting step 48 into step 46:
$$
\begin{gather}
\lim_{n \to \infty} \int_0^{(n + 1/2)\pi} \frac{\sin x}{x}\,dx = \frac{\pi}{2} \tag{49}
\end{gather}
$$

Define the continuous accumulation function $F(B) := \int_0^B \frac{\sin x}{x}\,dx$. In Part 1 (step 14), it was proven that the improper integral converges to a finite value:
$$
\begin{gather}
I = \lim_{B \to \infty} F(B) \in \mathbb{R} \tag{50}
\end{gather}
$$

By the definition of functional limits, if $\lim_{B \to \infty} F(B) = I$, then for every sequence of points $(B_n)_{n=1}^\infty$ diverging to $+\infty$, the sequence of values $(F(B_n))_{n=1}^\infty$ converges to $I$.

Consider the sequence $B_n := (n + 1/2)\pi$. Because $\lim_{n \to \infty} B_n = +\infty$:
$$
\begin{gather}
I = \lim_{B \to \infty} F(B) = \lim_{n \to \infty} F(B_n) = \lim_{n \to \infty} \int_0^{(n + 1/2)\pi} \frac{\sin x}{x}\,dx \tag{51}
\end{gather}
$$

Equating step 49 and step 51:
$$
\begin{gather}
\int_0^\infty \frac{\sin x}{x}\,dx = \frac{\pi}{2} \tag{52}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
