---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f: [a, \infty) \to \mathbb{R}$ be a function satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Let $c \in (a, \infty)$ be an arbitrary intermediate coordinate. Because $f \in \mathcal{R}[a, B]$ for every $B \ge c > a$, the hereditary property of the Riemann integral on subintervals guarantees that:
$$
\begin{gather}
f \in \mathcal{R}[a, c] \quad \text{and} \quad f \in \mathcal{R}[c, B] \quad \text{for all } B \ge c \tag{2}
\end{gather}
$$
---
# Step 1
Let $B \in [c, \infty)$. Because $a < c \le B$, by the interval additivity of the proper Riemann integral established in [[Chapter 2 - Linearity, Additivity, and Monotonicity of the Integral|Chapter 2]]:
$$
\begin{gather}
\int_a^B f(x)\,dx = \int_a^c f(x)\,dx + \int_c^B f(x)\,dx \tag{3}
\end{gather}
$$
The first term on the right-hand side of step 3 is an ordinary proper Riemann integral evaluated over the fixed compact interval $[a, c]$. As such, this term is completely independent of the upper exhaustion parameter $B$:
$$
\begin{gather}
K := \int_a^c f(x)\,dx \in \mathbb{R} \tag{4}
\end{gather}
$$
Substituting the constant $K$ into step 3 yields the fundamental decomposition for all $B \ge c$:
$$
\begin{gather}
\int_a^B f(x)\,dx = K + \int_c^B f(x)\,dx \tag{5}
\end{gather}
$$
Subtracting $K$ from both sides of step 5 yields the equivalent expression:
$$
\begin{gather}
\int_c^B f(x)\,dx = \int_a^B f(x)\,dx - K \tag{6}
\end{gather}
$$
---
# Step 2
Assume that the improper integral of $f$ over $[a, \infty)$ converges to a finite real number $I_a \in \mathbb{R}$:
$$
\begin{gather}
I_a := \int_a^\infty f(x)\,dx = \lim_{B \to \infty} \int_a^B f(x)\,dx \in \mathbb{R} \tag{7}
\end{gather}
$$
To determine the convergence status of the improper integral over $[c, \infty)$, evaluate the limit of the accumulation function $\int_c^B f(x)\,dx$ as $B \to \infty$. Taking the limit on both sides of step 6:
$$
\begin{gather}
\lim_{B \to \infty} \int_c^B f(x)\,dx = \lim_{B \to \infty} \left( \int_a^B f(x)\,dx - K \right) \tag{8}
\end{gather}
$$
Because the limit $\lim_{B \to \infty} \int_a^B f(x)\,dx = I_a$ exists in $\mathbb{R}$ and $K \in \mathbb{R}$ is a constant scalar, the difference rule for functional limits guarantees that the limit on the right-hand side of step 8 exists and satisfies:
$$
\begin{gather}
\lim_{B \to \infty} \int_c^B f(x)\,dx = I_a - K = \int_a^\infty f(x)\,dx - \int_a^c f(x)\,dx \tag{9}
\end{gather}
$$
Because $I_a - K \in \mathbb{R}$ is a finite real scalar, the limit exists. By definition, the improper integral $\int_c^\infty f(x)\,dx$ converges.

---
# Step 3
Conversely, assume that the improper integral of $f$ over $[c, \infty)$ converges to a finite real number $I_c \in \mathbb{R}$:
$$
\begin{gather}
I_c := \int_c^\infty f(x)\,dx = \lim_{B \to \infty} \int_c^B f(x)\,dx \in \mathbb{R} \tag{10}
\end{gather}
$$
Taking the limit as $B \to \infty$ on both sides of the accumulation identity of step 5:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B f(x)\,dx = \lim_{B \to \infty} \left( K + \int_c^B f(x)\,dx \right) \tag{11}
\end{gather}
$$
Applying the sum rule for functional limits:
$$
\begin{gather}
\lim_{B \to \infty} \int_a^B f(x)\,dx = K + \lim_{B \to \infty} \int_c^B f(x)\,dx = K + I_c = \int_a^c f(x)\,dx + \int_c^\infty f(x)\,dx \tag{12}
\end{gather}
$$
Because $K + I_c \in \mathbb{R}$ is finite, the limit exists. By definition, the improper integral $\int_a^\infty f(x)\,dx$ converges, and its value satisfies the identity:
$$
\begin{gather}
\int_a^\infty f(x)\,dx = \int_a^c f(x)\,dx + \int_c^\infty f(x)\,dx \tag{13}
\end{gather}
$$
This establishes the bidirectional equivalence of convergence along with the domain additivity formula.

---
# Step 4

Let $f: \mathbb{R} \to \mathbb{R}$ satisfy $f \in \mathcal{R}[A, B]$ for all compact intervals $[A, B] \subset \mathbb{R}$. Let $c_1, c_2 \in \mathbb{R}$ be two arbitrary partition coordinates satisfying $c_1 < c_2$.

For any exhaustion parameters $A < c_1$ and $B > c_2$, interval additivity of the proper Riemann integral yields:
$$
\begin{gather}
\int_A^B f(x)\,dx = \int_A^{c_1} f(x)\,dx + \int_{c_1}^{c_2} f(x)\,dx + \int_{c_2}^B f(x)\,dx \tag{14}
\end{gather}
$$
Rearranging step 14 into component branches:
$$
\begin{gather}
\int_A^{c_2} f(x)\,dx = \int_A^{c_1} f(x)\,dx + \int_{c_1}^{c_2} f(x)\,dx \tag{15}
\end{gather}
$$
$$
\begin{gather}
\int_{c_1}^B f(x)\,dx = \int_{c_1}^{c_2} f(x)\,dx + \int_{c_2}^B f(x)\,dx \tag{16}
\end{gather}
$$
Taking the limits $A \to -\infty$ in step 15 and $B \to \infty$ in step 16:
$$
\begin{gather}
\int_{-\infty}^{c_2} f(x)\,dx = \int_{-\infty}^{c_1} f(x)\,dx + \int_{c_1}^{c_2} f(x)\,dx \tag{17}
\end{gather}
$$
$$
\begin{gather}
\int_{c_1}^\infty f(x)\,dx = \int_{c_1}^{c_2} f(x)\,dx + \int_{c_2}^\infty f(x)\,dx \tag{18}
\end{gather}
$$
Adding step 17 and step 18 together:
$$
\begin{gather}
\int_{-\infty}^{c_2} f(x)\,dx + \int_{c_2}^\infty f(x)\,dx = \int_{-\infty}^{c_1} f(x)\,dx + \int_{c_1}^\infty f(x)\,dx \tag{19}
\end{gather}
$$
The identity of step 19 proves that the convergence and the numerical value of the improper integral $\int_{-\infty}^\infty f(x)\,dx$ are strictly invariant under the choice of the intermediate node $c$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
