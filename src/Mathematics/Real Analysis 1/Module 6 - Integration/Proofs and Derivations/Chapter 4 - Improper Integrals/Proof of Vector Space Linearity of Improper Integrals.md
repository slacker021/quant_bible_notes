---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f, g: [a, \infty) \to \mathbb{R}$ be functions satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B], \quad g \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Assume that the improper integrals of $f$ and $g$ over the semi-infinite domain $[a, \infty)$ converge to finite real numbers:
$$
\begin{gather}
I_f := \int_a^\infty f(x)\,dx = \lim_{B \to \infty} \int_a^B f(x)\,dx \in \mathbb{R} \tag{2}
\end{gather}
$$
$$
\begin{gather}
I_g := \int_a^\infty g(x)\,dx = \lim_{B \to \infty} \int_a^B g(x)\,dx \in \mathbb{R} \tag{3}
\end{gather}
$$
Let $\alpha, \beta \in \mathbb{R}$ be arbitrary real scalars.

---
# Step 1
By the linear space properties of the Riemann integral on compact intervals established in [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|Chapter 2]], the space $\mathcal{R}[a, B]$ forms a vector space over $\mathbb{R}$. For every scalar pair $\alpha, \beta \in \mathbb{R}$ and for each exhaustion parameter $B \ge a$, the linear combination $\alpha f + \beta g$ is Riemann integrable on $[a, B]$:
$$
\begin{gather}
\alpha f + \beta g \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{4}
\end{gather}
$$
Furthermore, the Riemann integral operator on the compact domain $[a, B]$ is strictly linear:
$$
\begin{gather}
\int_a^B \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^B f(x)\,dx + \beta \int_a^B g(x)\,dx \tag{5}
\end{gather}
$$
---
# Step 2
Define the accumulation functions $F, G, H: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
F(B) := \int_a^B f(x)\,dx \tag{6}
\end{gather}
$$
$$
\begin{gather}
G(B) := \int_a^B g(x)\,dx \tag{7}
\end{gather}
$$
$$
\begin{gather}
H(B) := \int_a^B \big( \alpha f(x) + \beta g(x) \big)\,dx \tag{8}
\end{gather}
$$
Substituting the expressions of step 6, step 7, and step 8 into the identity of step 5 gives:
$$
\begin{gather}
H(B) = \alpha F(B) + \beta G(B) \quad \text{for all } B \ge a \tag{9}
\end{gather}
$$
By virtue of the convergence hypotheses in step 2 and step 3, the asymptotic limits of $F(B)$ and $G(B)$ exist as finite real numbers:
$$
\begin{gather}
\lim_{B \to \infty} F(B) = I_f \in \mathbb{R} \tag{10}
\end{gather}
$$
$$
\begin{gather}
\lim_{B \to \infty} G(B) = I_g \in \mathbb{R} \tag{11}
\end{gather}
$$
---
# Step 3
Applying the definition of the improper integral of the first kind to the linear combination $\alpha f + \beta g$:
$$
\begin{gather}
\int_a^\infty \big( \alpha f(x) + \beta g(x) \big)\,dx := \lim_{B \to \infty} H(B) = \lim_{B \to \infty} \big( \alpha F(B) + \beta G(B) \big) \tag{12}
\end{gather}
$$
Recall the algebraic limit theorems for real-valued functions on unbounded intervals. Whenever two functions possess finite real limits as the parameter tends to infinity, the limit of any linear combination equals the corresponding linear combination of the respective limits:
$$
\begin{gather}
\lim_{B \to \infty} \big( \alpha F(B) + \beta G(B) \big) = \alpha \left( \lim_{B \to \infty} F(B) \right) + \beta \left( \lim_{B \to \infty} G(B) \right) \tag{13}
\end{gather}
$$
Substituting the limits from step 10 and step 11 into step 13 yields:
$$
\begin{gather}
\lim_{B \to \infty} H(B) = \alpha I_f + \beta I_g \tag{14}
\end{gather}
$$
Because $\alpha, \beta, I_f, I_g \in \mathbb{R}$, the combination $\alpha I_f + \beta I_g$ is a uniquely defined finite real number. Consequently, the limit in step 12 exists in $\mathbb{R}$, establishing that the improper integral of $\alpha f + \beta g$ converges:
$$
\begin{gather}
\int_a^\infty \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^\infty f(x)\,dx + \beta \int_a^\infty g(x)\,dx \tag{15}
\end{gather}
$$
---
# Step 4
Let $-\infty < a < b < \infty$, and let $f, g: [a, b) \to \mathbb{R}$ satisfy $f, g \in \mathcal{R}[a, b - \varepsilon]$ for every $\varepsilon \in (0, b - a)$, with convergent improper integrals:
$$
\begin{gather}
\int_a^b f(x)\,dx = \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} f(x)\,dx \in \mathbb{R}, \qquad \int_a^b g(x)\,dx = \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} g(x)\,dx \in \mathbb{R} \tag{16}
\end{gather}
$$
For each fixed $\varepsilon \in (0, b - a)$, applying the linearity of the proper Riemann integral on the compact interval $[a, b - \varepsilon]$ gives:
$$
\begin{gather}
\int_a^{b - \varepsilon} \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^{b - \varepsilon} f(x)\,dx + \beta \int_a^{b - \varepsilon} g(x)\,dx \tag{17}
\end{gather}
$$
Passing to the one-sided limit as $\varepsilon \to 0^+$ on both sides of step 17 and invoking the algebraic limit theorems:
$$
\begin{gather}
\lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} f(x)\,dx + \beta \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} g(x)\,dx \tag{18}
\end{gather}
$$
which confirms that:
$$
\begin{gather}
\int_a^b \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_a^b f(x)\,dx + \beta \int_a^b g(x)\,dx \tag{19}
\end{gather}
$$
An identical argument applies to left-endpoint singularities on $(a, b]$ by examining the one-sided limit $\lim_{\delta \to 0^+} \int_{a + \delta}^b$.

---
# Step 5
Let $f, g: \mathbb{R} \to \mathbb{R}$ possess convergent improper integrals over $(-\infty, \infty)$. By definition, for an arbitrary partition node $c \in \mathbb{R}$, both component improper integrals over $(-\infty, c]$ and $[c, \infty)$ converge independently for both functions.

Applying the linearity established in step 15 to the semi-infinite interval $[c, \infty)$ and symmetrically to $(-\infty, c]$:
$$
\begin{gather}
\int_{-\infty}^c \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_{-\infty}^c f(x)\,dx + \beta \int_{-\infty}^c g(x)\,dx \tag{20}
\end{gather}
$$
$$
\begin{gather}
\int_c^\infty \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_c^\infty f(x)\,dx + \beta \int_c^\infty g(x)\,dx \tag{21}
\end{gather}
$$
Summing step 20 and step 21 yields:
$$
\begin{gather}
\int_{-\infty}^\infty \big( \alpha f(x) + \beta g(x) \big)\,dx = \alpha \int_{-\infty}^\infty f(x)\,dx + \beta \int_{-\infty}^\infty g(x)\,dx \tag{22}
\end{gather}
$$
This demonstrates that the collection of convergent improper integrals forms a real vector space across all domain types.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
