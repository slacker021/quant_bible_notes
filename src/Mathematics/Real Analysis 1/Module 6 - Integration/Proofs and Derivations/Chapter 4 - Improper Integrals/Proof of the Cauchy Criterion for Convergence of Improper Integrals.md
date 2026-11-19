---
dg-publish: true
---
Let $a \in \mathbb{R}$, and let $f: [a, \infty) \to \mathbb{R}$ be a function satisfying:
$$
\begin{gather}
f \in \mathcal{R}[a, B] \quad \text{for all } B \ge a \tag{1}
\end{gather}
$$
Define the accumulation function $F: [a, \infty) \to \mathbb{R}$ by:
$$
\begin{gather}
F(B) := \int_a^B f(x)\,dx \tag{2}
\end{gather}
$$
By definition, the improper integral $\int_a^\infty f(x)\,dx$ converges if and only if the limit of $F(B)$ as $B \to \infty$ exists and is a finite real number:
$$
\begin{gather}
I := \lim_{B \to \infty} F(B) \in \mathbb{R} \tag{3}
\end{gather}
$$
---
# Step 1
Let $B_1, B_2 \in [a, \infty)$ be arbitrary parameters. By the interval additivity of the proper Riemann integral:
$$
\begin{gather}
\int_a^{B_2} f(x)\,dx = \int_a^{B_1} f(x)\,dx + \int_{B_1}^{B_2} f(x)\,dx \tag{4}
\end{gather}
$$

Subtracting $\int_a^{B_1} f(x)\,dx = F(B_1)$ from both sides of step 4:
$$
\begin{gather}
F(B_2) - F(B_1) = \int_{B_1}^{B_2} f(x)\,dx \tag{5}
\end{gather}
$$

Taking the absolute value of both sides of step 5:
$$
\begin{gather}
|F(B_2) - F(B_1)| = \left| \int_{B_1}^{B_2} f(x)\,dx \right| \tag{6}
\end{gather}
$$
---
# Step 2
Assume that the improper integral converges to the finite value $I \in \mathbb{R}$, as defined in step 3.

Let $\varepsilon > 0$ be arbitrary. Define $\varepsilon' := \frac{\varepsilon}{2} > 0$.

By the definition of the limit of a real-valued function at infinity, there exists an exhaustion threshold $B_0 \ge a$ such that:
$$
\begin{gather}
B > B_0 \implies |F(B) - I| < \frac{\varepsilon}{2} \tag{7}
\end{gather}
$$

Let $B_1, B_2 > B_0$ be arbitrary. Adding and subtracting the limit value $I$ within the difference $F(B_2) - F(B_1)$:
$$
\begin{gather}
F(B_2) - F(B_1) = \big( F(B_2) - I \big) - \big( F(B_1) - I \big) \tag{8}
\end{gather}
$$

Applying the triangle inequality to step 8:
$$
\begin{gather}
|F(B_2) - F(B_1)| \le |F(B_2) - I| + |F(B_1) - I| \tag{9}
\end{gather}
$$

Because both $B_1 > B_0$ and $B_2 > B_0$, evaluating step 7 at $B = B_1$ and $B = B_2$ yields:
$$
\begin{gather}
|F(B_1) - I| < \frac{\varepsilon}{2}, \qquad |F(B_2) - I| < \frac{\varepsilon}{2} \tag{10}
\end{gather}
$$

Substituting the bounds from step 10 into step 9:
$$
\begin{gather}
|F(B_2) - F(B_1)| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{11}
\end{gather}
$$

Substituting the identity of step 6 into step 11:
$$
\begin{gather}
\left| \int_{B_1}^{B_2} f(x)\,dx \right| < \varepsilon \quad \text{for all } B_1, B_2 > B_0 \tag{12}
\end{gather}
$$

---
# Step 3
Assume the Cauchy condition holds: for every $\varepsilon > 0$, there exists an exhaustion threshold $B_0 \ge a$ such that:
$$
\begin{gather}
B_1, B_2 > B_0 \implies \left| \int_{B_1}^{B_2} f(x)\,dx \right| = |F(B_2) - F(B_1)| < \varepsilon \tag{13}
\end{gather}
$$

It will be demonstrated that $\lim_{B \to \infty} F(B)$ exists in $\mathbb{R}$.

Let $(x_n)_{n=1}^\infty$ be an arbitrary sequence in $[a, \infty)$ satisfying:
$$
\begin{gather}
\lim_{n \to \infty} x_n = +\infty \tag{14}
\end{gather}
$$

It will be verified that the sequence of accumulation values $(F(x_n))_{n=1}^\infty$ is a Cauchy sequence of real numbers.

Let $\varepsilon > 0$ be given. By the hypothesis of step 13, there exists $B_0 \ge a$ such that:
$$
\begin{gather}
u, v > B_0 \implies |F(u) - F(v)| < \varepsilon \tag{15}
\end{gather}
$$

Because $x_n \to +\infty$ by step 14, there exists an integer index $N \in \mathbb{N}$ such that:
$$
\begin{gather}
n \ge N \implies x_n > B_0 \tag{16}
\end{gather}
$$

Let $n, m \ge N$ be arbitrary. By step 16, both $x_n > B_0$ and $x_m > B_0$. Setting $u = x_n$ and $v = x_m$ in step 15 yields:
$$
\begin{gather}
|F(x_n) - F(x_m)| < \varepsilon \tag{17}
\end{gather}
$$

Because step 17 holds for all $n, m \ge N$, the sequence $(F(x_n))_{n=1}^\infty$ is a Cauchy sequence in $\mathbb{R}$.

By the Cauchy Completeness of the real number system $\mathbb{R}$, every Cauchy sequence converges to a limit in $\mathbb{R}$. Therefore, there exists $I \in \mathbb{R}$ such that:
$$
\begin{gather}
\lim_{n \to \infty} F(x_n) = I \tag{18}
\end{gather}
$$
---
# Step 4
It remains to prove that the limit $I$ in step 18 is independent of the chosen sequence $(x_n)$.

Let $(y_n)_{n=1}^\infty$ be any other sequence in $[a, \infty)$ satisfying $\lim_{n \to \infty} y_n = +\infty$.

By repeating the deduction of step 3, $(F(y_n))_{n=1}^\infty$ is a Cauchy sequence, and therefore converges to a limit:
$$
\begin{gather}
J := \lim_{n \to \infty} F(y_n) \in \mathbb{R} \tag{19}
\end{gather}
$$

Construct the interleaved sequence $(z_n)_{n=1}^\infty$ defined by:
$$
\begin{gather}
z_{2k - 1} := x_k, \qquad z_{2k} := y_k \quad \text{for all } k \in \mathbb{N} \tag{20}
\end{gather}
$$

Because $\lim_{k \to \infty} x_k = +\infty$ and $\lim_{k \to \infty} y_k = +\infty$, for every $E > 0$ there exist $K_1, K_2 \in \mathbb{N}$ such that $x_k > E$ for $k \ge K_1$ and $y_k > E$ for $k \ge K_2$. Setting $K := \max\{K_1, K_2\}$, for all $n \ge 2K$ the condition $z_n > E$ holds. Thus:
$$
\begin{gather}
\lim_{n \to \infty} z_n = +\infty \tag{21}
\end{gather}
$$

Applying the result of step 3 to the sequence $(z_n)$, $(F(z_n))_{n=1}^\infty$ is a Cauchy sequence, and consequently converges to a limit:
$$
\begin{gather}
L := \lim_{n \to \infty} F(z_n) \in \mathbb{R} \tag{22}
\end{gather}
$$

Notice that $(F(x_k))_{k=1}^\infty$ is the subsequence of $(F(z_n))$ consisting of odd-indexed terms:
$$
\begin{gather}
F(x_k) = F(z_{2k - 1}) \tag{23}
\end{gather}
$$
and $(F(y_k))_{k=1}^\infty$ is the subsequence consisting of even-indexed terms:
$$
\begin{gather}
F(y_k) = F(z_{2k}) \tag{24}
\end{gather}
$$

Because every subsequence of a convergent sequence converges to the same limit:
$$
\begin{gather}
I = \lim_{k \to \infty} F(x_k) = \lim_{n \to \infty} F(z_n) = L, \qquad J = \lim_{k \to \infty} F(y_k) = \lim_{n \to \infty} F(z_n) = L \tag{25}
\end{gather}
$$

Equating the limits in step 25:
$$
\begin{gather}
I = J = L \tag{26}
\end{gather}
$$

Because the limit $\lim_{n \to \infty} F(x_n) = I$ is identical for every sequence $x_n \to +\infty$, the Heine Sequential Criterion for functional limits implies that the limit of the function as $B \to \infty$ exists:
$$
\begin{gather}
\lim_{B \to \infty} F(B) = \lim_{B \to \infty} \int_a^B f(x)\,dx = I \in \mathbb{R} \tag{27}
\end{gather}
$$

Thus, the improper integral $\int_a^\infty f(x)\,dx$ converges, completing the proof of sufficiency.

---
# Step 5
For an improper integral of the second kind with singularity at the finite upper endpoint $b$:
$$
\begin{gather}
\int_a^b f(x)\,dx := \lim_{\varepsilon \to 0^+} \int_a^{b - \varepsilon} f(x)\,dx \tag{28}
\end{gather}
$$
where $f \in \mathcal{R}[a, b - \varepsilon]$ for all $\varepsilon \in (0, b - a)$.

Applying the reflection and inversion substitution $u = \frac{1}{b - x}$, the singularity at $x \to b^-$ transforms into an unbounded tail $u \to +\infty$.

Applying the equivalence established in steps 1 through 4 under this transformation: the improper integral $\int_a^b f(x)\,dx$ converges if and only if for every $\varepsilon > 0$, there exists a proximity threshold $\delta_0 \in (0, b - a)$ such that for all $\varepsilon_1, \varepsilon_2 \in (0, \delta_0)$:
$$
\begin{gather}
\left| \int_{b - \varepsilon_1}^{b - \varepsilon_2} f(x)\,dx \right| < \varepsilon \tag{29}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
