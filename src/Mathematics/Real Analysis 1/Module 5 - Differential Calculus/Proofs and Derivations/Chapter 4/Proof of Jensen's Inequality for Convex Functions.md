---
dg-publish: true
---
Let $f: I \to \mathbb{R}$ be a convex function on an interval $I \subseteq \mathbb{R}$.

The proof proceeds by mathematical induction on $n \in \mathbb{N}$, where $n \ge 2$.

### Base Case: $n = 2$
For $n = 2$, let $x_1, x_2 \in I$ and let $\alpha_1, \alpha_2 \ge 0$ with $\alpha_1 + \alpha_2 = 1$. By Definition 4.1:
$$
\begin{gather}
f(\alpha_1 x_1 + \alpha_2 x_2) \le \alpha_1 f(x_1) + \alpha_2 f(x_2) \tag{1}
\end{gather}
$$
This matches the statement identically.

### Inductive Hypothesis
Assume that for some integer $m \ge 2$, for any collection of points $y_1, \dots, y_m \in I$ and non-negative weights $\beta_1, \dots, \beta_m \ge 0$ satisfying $\sum_{k=1}^m \beta_k = 1$:
$$
\begin{gather}
f\left( \sum_{k=1}^m \beta_k y_k \right) \le \sum_{k=1}^m \beta_k f(y_k) \tag{2}
\end{gather}
$$

### Inductive Step: $n = m + 1$
Let $x_1, \dots, x_m, x_{m+1} \in I$ and let $\alpha_1, \dots, \alpha_m, \alpha_{m+1} \ge 0$ with $\sum_{k=1}^{m+1} \alpha_k = 1$.

If $\alpha_{m+1} = 1$, then $\alpha_1 = \dots = \alpha_m = 0$, and the inequality reduces to $f(x_{m+1}) \le f(x_{m+1})$, which holds trivially.

Assume $\alpha_{m+1} < 1$. Set $\gamma := 1 - \alpha_{m+1} = \sum_{k=1}^m \alpha_k > 0$.

Decompose the linear combination into a convex combination of two elements:
$$
\begin{gather}
\sum_{k=1}^{m+1} \alpha_k x_k = \sum_{k=1}^m \alpha_k x_k + \alpha_{m+1} x_{m+1} = \gamma \left( \sum_{k=1}^m \frac{\alpha_k}{\gamma} x_k \right) + \alpha_{m+1} x_{m+1} \tag{3}
\end{gather}
$$

Define the normalized intermediate point:
$$
\begin{gather}
\bar{x} := \sum_{k=1}^m \frac{\alpha_k}{\gamma} x_k \tag{4}
\end{gather}
$$

Because $\sum_{k=1}^m \frac{\alpha_k}{\gamma} = \frac{1}{\gamma}\sum_{k=1}^m \alpha_k = \frac{\gamma}{\gamma} = 1$, and $I$ is an interval (convex set in $\mathbb{R}$), $\bar{x} \in I$.

Because $\gamma + \alpha_{m+1} = 1$, applying the base case ($n = 2$) to $\bar{x}$ and $x_{m+1}$:
$$
\begin{gather}
f\left( \sum_{k=1}^{m+1} \alpha_k x_k \right) = f(\gamma \bar{x} + \alpha_{m+1} x_{m+1}) \le \gamma f(\bar{x}) + \alpha_{m+1} f(x_{m+1}) \tag{5}
\end{gather}
$$

Now, applying the inductive hypothesis (2) to $\bar{x} = \sum_{k=1}^m \left(\frac{\alpha_k}{\gamma}\right) x_k$:
$$
\begin{gather}
f(\bar{x}) \le \sum_{k=1}^m \frac{\alpha_k}{\gamma} f(x_k) \tag{6}
\end{gather}
$$

Multiplying inequality (6) by $\gamma > 0$:
$$
\begin{gather}
\gamma f(\bar{x}) \le \sum_{k=1}^m \alpha_k f(x_k) \tag{7}
\end{gather}
$$

Substituting inequality (7) into inequality (5):
$$
\begin{gather}
f\left( \sum_{k=1}^{m+1} \alpha_k x_k \right) \le \sum_{k=1}^m \alpha_k f(x_k) + \alpha_{m+1} f(x_{m+1}) = \sum_{k=1}^{m+1} \alpha_k f(x_k) \tag{8}
\end{gather}
$$

By mathematical induction, Jensen's inequality holds for all integers $n \ge 2$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
