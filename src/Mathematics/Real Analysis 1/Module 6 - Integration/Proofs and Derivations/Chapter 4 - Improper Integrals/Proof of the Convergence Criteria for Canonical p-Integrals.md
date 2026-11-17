---
dg-publish: true
---
Let $p \in \mathbb{R}$, and consider the canonical power integrand $f_p(x) := x^{-p} = \frac{1}{x^p}$.

---
# Case 1
Let $a > 0$. The improper integral of the first kind is defined by the limiting exhaustion:
$$
\begin{gather}
\int_a^\infty \frac{dx}{x^p} := \lim_{B \to \infty} \int_a^B \frac{dx}{x^p} \tag{1}
\end{gather}
$$
For every parameter $B > a$, the power function $x \mapsto x^{-p}$ is continuous on the compact interval $[a, B]$, hence $x^{-p} \in \mathcal{R}[a, B]$.

### Step 1
When $p \neq 1$, an antiderivative of $x^{-p}$ on $[a, B]$ is given by $F(x) = \frac{x^{1 - p}}{1 - p}$. By the Newton-Leibniz Fundamental Theorem of Calculus:
$$
\begin{gather}
\int_a^B \frac{dx}{x^p} = \left[ \frac{x^{1 - p}}{1 - p} \right]_a^B = \frac{B^{1 - p} - a^{1 - p}}{1 - p} = \frac{a^{1 - p} - B^{1 - p}}{p - 1} \tag{2}
\end{gather}
$$
### Step 2
Suppose $p > 1$. Define $\alpha := p - 1 > 0$. The exponent of $B$ in step 2 is $1 - p = -\alpha < 0$. Rewriting the power:
$$
\begin{gather}
B^{1 - p} = B^{-\alpha} = \frac{1}{B^\alpha} \tag{3}
\end{gather}
$$

Because $\alpha > 0$, taking the limit as $B \to \infty$ yields:
$$
\begin{gather}
\lim_{B \to \infty} \frac{1}{B^\alpha} = 0 \tag{4}
\end{gather}
$$

Substituting step 4 into step 2 and applying the limit arithmetic theorems:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B \frac{dx}{x^p} = \lim_{B \to \infty} \frac{a^{1 - p} - B^{1 - p}}{p - 1} = \frac{a^{1 - p} - 0}{p - 1} = \frac{a^{1 - p}}{p - 1} \tag{5}
\end{gather}
$$

Because the limit in step 5 is a finite real number, the improper integral $\int_a^\infty x^{-p}\,dx$ converges for $p > 1$, and its value is $\frac{a^{1 - p}}{p - 1}$.

### Step 3
Suppose $p < 1$. Define $\beta := 1 - p > 0$. The exponent of $B$ in step 2 is $\beta > 0$. Therefore:
$$
\begin{gather}
\lim_{B \to \infty} B^{1 - p} = \lim_{B \to \infty} B^\beta = +\infty \tag{6}
\end{gather}
$$

Because $1 - p = \beta > 0$, dividing by $\beta$ preserves the positive divergence:
$$
\begin{gather}
\lim_{B \to \infty} \frac{B^{1 - p} - a^{1 - p}}{1 - p} = \frac{1}{\beta} \left( \lim_{B \to \infty} B^\beta - a^\beta \right) = +\infty \tag{7}
\end{gather}
$$

Thus, the improper integral diverges to $+\infty$ whenever $p < 1$.

### Step 4
When $p = 1$, an antiderivative of $x^{-1}$ on $[a, B]$ is the natural logarithm $\ln x$. By the Newton-Leibniz formula:
$$
\begin{gather}
\int_a^B \frac{dx}{x} = [\ln x]_a^B = \ln B - \ln a \tag{8}
\end{gather}
$$

Because the natural logarithm is strictly increasing and unbounded above:
$$
\begin{gather}
\lim_{B \to \infty} (\ln B - \ln a) = +\infty \tag{9}
\end{gather}
$$

Thus, the improper integral diverges to $+\infty$ when $p = 1$.

Combining step 5, step 7, and step 9 completes the proof for Case 1: $\int_a^\infty x^{-p}\,dx$ converges if and only if $p > 1$.

---
# Case 2
Let $b > 0$. The improper integral of the second kind with singularity at $x = 0$ is defined by:
$$
\begin{gather}
\int_0^b \frac{dx}{x^p} := \lim_{\varepsilon \to 0^+} \int_\varepsilon^b \frac{dx}{x^p} \tag{10}
\end{gather}
$$
For every $\varepsilon \in (0, b)$, the integrand $x^{-p}$ is continuous on $[\varepsilon, b]$, hence $x^{-p} \in \mathcal{R}[\varepsilon, b]$.

### Step 1
When $p \neq 1$, applying the Newton-Leibniz formula on $[\varepsilon, b]$:
$$
\begin{gather}
\int_\varepsilon^b \frac{dx}{x^p} = \left[ \frac{x^{1 - p}}{1 - p} \right]_\varepsilon^b = \frac{b^{1 - p} - \varepsilon^{1 - p}}{1 - p} \tag{11}
\end{gather}
$$

### Step 2
Suppose $p < 1$. Define $\beta := 1 - p > 0$. As $\varepsilon \to 0^+$:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \varepsilon^{1 - p} = \lim_{\varepsilon \to 0^+} \varepsilon^\beta = 0 \tag{12}
\end{gather}
$$

Substituting step 12 into step 11:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \int_\varepsilon^b \frac{dx}{x^p} = \frac{b^{1 - p} - 0}{1 - p} = \frac{b^{1 - p}}{1 - p} \tag{13}
\end{gather}
$$

Thus, the improper integral converges finitely for $p < 1$, and its value is $\frac{b^{1 - p}}{1 - p}$.

### Step 3
Suppose $p > 1$. Define $\alpha := p - 1 > 0$. The exponent $1 - p = -\alpha < 0$. Therefore:
$$
\begin{gather}
\varepsilon^{1 - p} = \frac{1}{\varepsilon^\alpha} \tag{14}
\end{gather}
$$

Because $\alpha > 0$, taking the right-hand limit as $\varepsilon \to 0^+$:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \frac{1}{\varepsilon^\alpha} = +\infty \tag{15}
\end{gather}
$$

Rewriting step 11:
$$
\begin{gather}
\frac{b^{1 - p} - \varepsilon^{1 - p}}{1 - p} = \frac{\varepsilon^{-\alpha} - b^{-\alpha}}{\alpha} = \frac{1}{\alpha} \left( \frac{1}{\varepsilon^\alpha} - \frac{1}{b^\alpha} \right) \tag{16}
\end{gather}
$$

Taking the limit as $\varepsilon \to 0^+$ in step 16 and applying step 15:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \int_\varepsilon^b \frac{dx}{x^p} = \frac{1}{\alpha} (+\infty) = +\infty \tag{17}
\end{gather}
$$

Thus, the improper integral diverges to $+\infty$ whenever $p > 1$.

### Step 4
When $p = 1$, evaluating the proper integral on $[\varepsilon, b]$:
$$
\begin{gather}
\int_\varepsilon^b \frac{dx}{x} = [\ln x]_\varepsilon^b = \ln b - \ln \varepsilon \tag{18}
\end{gather}
$$

Taking the right-hand limit as $\varepsilon \to 0^+$:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \ln \varepsilon = -\infty \implies \lim_{\varepsilon \to 0^+} (\ln b - \ln \varepsilon) = \ln b - (-\infty) = +\infty \tag{19}
\end{gather}
$$

Thus, the improper integral diverges to $+\infty$ when $p = 1$.

Combining step 13, step 17, and step 19 completes the proof for Case 2: $\int_0^b x^{-p}\,dx$ converges if and only if $p < 1$.

---
# Case 3
Let $a > 1$. Consider the improper integral:
$$
\begin{gather}
\int_a^\infty \frac{dx}{x(\ln x)^p} := \lim_{B \to \infty} \int_a^B \frac{dx}{x(\ln x)^p} \tag{20}
\end{gather}
$$

### Step 1
For every $B > a$, the function $g(x) := \ln x$ is strictly increasing, continuously differentiable, and maps the interval $[a, B]$ bijectively onto $[\ln a, \ln B]$. The derivative is:
$$
\begin{gather}
g'(x) = \frac{1}{x} \tag{21}
\end{gather}
$$

By the Change of Variables Theorem for proper Riemann integrals:
$$
\begin{gather}
\int_a^B \frac{dx}{x(\ln x)^p} = \int_a^B (\ln x)^{-p} \cdot \frac{1}{x}\,dx = \int_{g(a)}^{g(B)} u^{-p}\,du = \int_{\ln a}^{\ln B} u^{-p}\,du \tag{22}
\end{gather}
$$

### Step 2
Because $a > 1$, the lower limit of the transformed integral satisfies $\ln a > 0$.

Taking the limit as $B \to \infty$, the continuity and unboundedness of the natural logarithm imply:
$$
\begin{gather}
\lim_{B \to \infty} g(B) = \lim_{B \to \infty} \ln B = +\infty \tag{23}
\end{gather}
$$

Setting $C := \ln B$, as $B \to \infty$ the parameter $C \to +\infty$. Applying the definition of the improper integral of the first kind:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B \frac{dx}{x(\ln x)^p} = \lim_{C \to \infty} \int_{\ln a}^C u^{-p}\,du = \int_{\ln a}^\infty u^{-p}\,du \tag{24}
\end{gather}
$$

Because $\ln a > 0$, the integral on the right-hand side of step 24 is an instance of Case 1 with lower limit $\ln a$ and exponent $p$.

Applying the convergence classification established in Case 1:
1. If $p > 1$, the integral converges finitely to:
$$
\begin{gather}
\int_a^\infty \frac{dx}{x(\ln x)^p} = \frac{(\ln a)^{1 - p}}{p - 1} \tag{25}
\end{gather}
$$
2. If $p \le 1$, the integral diverges strictly to $+\infty$:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B \frac{dx}{x(\ln x)^p} = +\infty \tag{26}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
