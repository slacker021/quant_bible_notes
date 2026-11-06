---
dg-publish: true
---
Let the Dirichlet function $\mathbf{1}_{\mathbb{Q}}: \mathbb{R} \to \mathbb{R}$ be defined by:
$$
\begin{gather}
\mathbf{1}_{\mathbb{Q}}(x) := \begin{cases} 1, & x \in \mathbb{Q} \\ 0, & x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \tag{1}
\end{gather}
$$
and let $a \in \mathbb{R}$ be an arbitrary real number.

# Proposition 1
Fix the error tolerance:
$$
\begin{gather}
\varepsilon_0 := \frac{1}{2} \tag{2}
\end{gather}
$$
Let $\delta > 0$ be an arbitrary positive distance, defining the symmetric metric interval $(a - \delta, a + \delta)$. 

There are two mutually exclusive cases governing the point $a$:
* Case 1: $a \in \mathbb{Q}$. In this case, step 1 gives $\mathbf{1}_{\mathbb{Q}}(a) = 1$. By the density of the irrational numbers in $\mathbb{R}$, there exists an irrational number $\xi \in \mathbb{R} \setminus \mathbb{Q}$ such that:
$$
\begin{gather}
\xi \in (a - \delta, a + \delta) \iff |\xi - a| < \delta \tag{3}
\end{gather}
$$
Evaluating the functional deviation at $\xi$ yields:
$$
\begin{gather}
|\mathbf{1}_{\mathbb{Q}}(\xi) - \mathbf{1}_{\mathbb{Q}}(a)| = |0 - 1| = 1 > \frac{1}{2} = \varepsilon_0 \tag{4}
\end{gather}
$$

* Case 2: $a \in \mathbb{R} \setminus \mathbb{Q}$. In this case, step 1 gives $\mathbf{1}_{\mathbb{Q}}(a) = 0$. By the density of the rational numbers in $\mathbb{R}$ (consequence of the [[Proof of Archimedean Corollaries]]), there exists a rational number $r \in \mathbb{Q}$ such that:
$$
\begin{gather}
r \in (a - \delta, a + \delta) \iff |r - a| < \delta \tag{5}
\end{gather}
$$
Evaluating the functional deviation at $r$ yields:
$$
\begin{gather}
|\mathbf{1}_{\mathbb{Q}}(r) - \mathbf{1}_{\mathbb{Q}}(a)| = |1 - 0| = 1 > \frac{1}{2} = \varepsilon_0 \tag{6}
\end{gather}
$$

In both cases, for every distance $\delta > 0$, there exists a point $x \in \mathbb{R}$ satisfying $|x - a| < \delta$ for which:
$$
\begin{gather}
|\mathbf{1}_{\mathbb{Q}}(x) - \mathbf{1}_{\mathbb{Q}}(a)| \ge \varepsilon_0 \tag{7}
\end{gather}
$$

Step 7 constitutes the exact logical negation of the Cauchy metric criterion for continuity. Because $a \in \mathbb{R}$ was arbitrary, $\mathbf{1}_{\mathbb{Q}}$ is discontinuous at every point of $\mathbb{R}$.

---
# Proposition 2
A discontinuity at an accumulation point $a \in \mathbb{R}$ is an essential discontinuity of the second kind if at least one of the one-sided directional limits $\lim_{x \to a^+} \mathbf{1}_{\mathbb{Q}}(x)$ or $\lim_{x \to a^-} \mathbf{1}_{\mathbb{Q}}(x)$ fails to exist. 

Consider the right-hand directional approach towards $a$. For each natural number $n \in \mathbb{N}$, consider the open right-hand interval:
$$
\begin{gather}
I_n^+ := \left(a, \ a + \frac{1}{n}\right) \tag{8}
\end{gather}
$$

By the density of the rational numbers, there exists a rational term $r_n \in \mathbb{Q} \cap I_n^+$. The resulting sequence $\{r_n\}_{n=1}^\infty$ satisfies:
$$
\begin{gather}
a < r_n < a + \frac{1}{n} \implies \lim_{n \to \infty} r_n = a \tag{9}
\end{gather}
$$
Because each $r_n \in \mathbb{Q}$, step 1 yields $\mathbf{1}_{\mathbb{Q}}(r_n) = 1$ for all $n \in \mathbb{N}$. Therefore:
$$
\begin{gather}
\lim_{n \to \infty} \mathbf{1}_{\mathbb{Q}}(r_n) = 1 \tag{10}
\end{gather}
$$

Concurrently, by the density of the irrational numbers, there exists an irrational term $\xi_n \in (\mathbb{R} \setminus \mathbb{Q}) \cap I_n^+$. The resulting sequence $\{\xi_n\}_{n=1}^\infty$ satisfies:
$$
\begin{gather}
a < \xi_n < a + \frac{1}{n} \implies \lim_{n \to \infty} \xi_n = a \tag{11}
\end{gather}
$$
Because each $\xi_n \in \mathbb{R} \setminus \mathbb{Q}$, step 1 yields $\mathbf{1}_{\mathbb{Q}}(\xi_n) = 0$ for all $n \in \mathbb{N}$. Therefore:
$$
\begin{gather}
\lim_{n \to \infty} \mathbf{1}_{\mathbb{Q}}(\xi_n) = 0 \tag{12}
\end{gather}
$$

By the Heine sequential characterization of directional limits (from the [[Proof of the Equivalence of Cauchy and Heine Definitions]]), if the right-hand limit $\lim_{x \to a^+} \mathbf{1}_{\mathbb{Q}}(x)$ existed, then every sequence converging to $a$ from the right would generate an image sequence converging to the same value. Because the limits in step 10 and step 12 are distinct ($1 \neq 0$), the right-hand limit does not exist:
$$
\begin{gather}
\lim_{x \to a^+} \mathbf{1}_{\mathbb{Q}}(x) \quad \text{does not exist} \tag{13}
\end{gather}
$$

By an identical construction on the left-hand intervals $I_n^- := (a - \frac{1}{n}, a)$, selecting sequences of rational and irrational points demonstrates that the left-hand limit does not exist:
$$
\begin{gather}
\lim_{x \to a^-} \mathbf{1}_{\mathbb{Q}}(x) \quad \text{does not exist} \tag{14}
\end{gather}
$$

Because both directional limits fail to exist at every point $a \in \mathbb{R}$, every real number represents an essential discontinuity of the second kind.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$