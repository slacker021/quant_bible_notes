---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, and let $f: E \to \mathbb{R}$ be uniformly continuous on $E$. 

Let $\{x_n\}_{n=1}^\infty \subseteq E$ be an arbitrary Cauchy sequence in $E$. 

Recall that a sequence $\{y_n\}_{n=1}^\infty \subseteq \mathbb{R}$ is Cauchy if for every error tolerance $\varepsilon > 0$, there exists an index threshold $N \in \mathbb{N}$ such that for all indices $m, n \ge N$:
$$
\begin{gather}
|y_n - y_m| < \varepsilon \tag{1}
\end{gather}
$$

Let an arbitrary tolerance $\varepsilon > 0$ be given. 

By the definition of uniform continuity of $f$ on $E$, there exists a single uniform distance $\delta > 0$ such that for all elements $x', x'' \in E$:
$$
\begin{gather}
|x' - x''| < \delta \implies |f(x') - f(x'')| < \varepsilon \tag{2}
\end{gather}
$$

Now consider the strictly positive value $\delta > 0$ as the error tolerance for the Cauchy sequence $\{x_n\}_{n=1}^\infty$. 

Because $\{x_n\}_{n=1}^\infty$ is a Cauchy sequence, there exists an index threshold $N_0 \in \mathbb{N}$ such that for all indices $m, n \ge N_0$:
$$
\begin{gather}
|x_n - x_m| < \delta \tag{3}
\end{gather}
$$

Because $\{x_n\} \subseteq E$, setting $x' = x_n \in E$ and $x'' = x_m \in E$ permits the direct application of step 2 to step 3. 

It follows that for all indices $m, n \ge N_0$:
$$
\begin{gather}
|f(x_n) - f(x_m)| < \varepsilon \tag{4}
\end{gather}
$$

Because $\varepsilon > 0$ was arbitrary, the image sequence $\{f(x_n)\}_{n=1}^\infty$ satisfies the Cauchy criterion of step 1. 

Therefore, $\{f(x_n)\}_{n=1}^\infty$ is a Cauchy sequence in $\mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
