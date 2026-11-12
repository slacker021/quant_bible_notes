---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a convex function on $(a, b)$. Let $n \in \mathbb{N}$ with $n \ge 1$, let $x_1, \dots, x_n \in (a, b)$, and let $\alpha_1, \dots, \alpha_n \ge 0$ be non-negative real weights satisfying:
$$
\begin{gather}
\sum_{i=1}^n \alpha_i = 1 \tag{1}
\end{gather}
$$

The assertion that:
$$
\begin{gather}
f\left(\sum_{i=1}^n \alpha_i x_i\right) \le \sum_{i=1}^n \alpha_i f(x_i) \tag{2}
\end{gather}
$$
is established by mathematical induction on the number of nodes $n$.

**Base Case: $n = 1$ and $n = 2$.**
For $n = 1$, step 1 requires $\alpha_1 = 1$. The left-hand side and right-hand side of step 2 both reduce to $f(x_1)$, so equality holds trivially.

For $n = 2$, the weights satisfy $\alpha_1, \alpha_2 \ge 0$ and $\alpha_1 + \alpha_2 = 1$. Step 2 becomes:
$$
\begin{gather}
f(\alpha_1 x_1 + \alpha_2 x_2) \le \alpha_1 f(x_1) + \alpha_2 f(x_2) \tag{3}
\end{gather}
$$
which is the foundational definition of convexity for a function on an interval. If $f$ is strictly convex, $\alpha_1, \alpha_2 > 0$, and $x_1 \neq x_2$, the definition of strict convexity ensures that the inequality in step 3 is strict.

**Induction Hypothesis:**
Assume that step 2 holds for some integer $k \ge 2$: for any collection of $k$ points $y_1, \dots, y_k \in (a, b)$ and any non-negative weights $\beta_1, \dots, \beta_k \ge 0$ with $\sum_{i=1}^k \beta_i = 1$, the inequality:
$$
\begin{gather}
f\left(\sum_{i=1}^k \beta_i y_i\right) \le \sum_{i=1}^k \beta_i f(y_i) \tag{4}
\end{gather}
$$
holds. Furthermore, if $f$ is strictly convex and all $\beta_i > 0$, equality holds if and only if $y_1 = \dots = y_k$.

**Induction Step:**
Now consider $k + 1$ points $x_1, \dots, x_{k+1} \in (a, b)$ and non-negative weights $\alpha_1, \dots, \alpha_{k+1} \ge 0$ satisfying $\sum_{i=1}^{k+1} \alpha_i = 1$.

If $\alpha_{k+1} = 1$, then $\alpha_1 = \dots = \alpha_k = 0$, and the inequality reduces to the trivial identity $f(x_{k+1}) \le f(x_{k+1})$. 

Thus, assume that $\alpha_{k+1} < 1$. Define the remaining aggregate weight $S_k$ by:
$$
\begin{gather}
S_k := \sum_{i=1}^k \alpha_i = 1 - \alpha_{k+1} > 0 \tag{5}
\end{gather}
$$
The linear convex combination of the $k + 1$ points can be partitioned into:
$$
\begin{gather}
\sum_{i=1}^{k+1} \alpha_i x_i = S_k \left(\sum_{i=1}^k \frac{\alpha_i}{S_k} x_i\right) + \alpha_{k+1} x_{k+1} \tag{6}
\end{gather}
$$
Define the intermediate barycentric point:
$$
\begin{gather}
z := \sum_{i=1}^k \frac{\alpha_i}{S_k} x_i \tag{7}
\end{gather}
$$
Because the weights $\frac{\alpha_i}{S_k}$ are non-negative and sum to $\sum_{i=1}^k \frac{\alpha_i}{S_k} = \frac{S_k}{S_k} = 1$, the point $z$ is a convex combination of points in $(a, b)$, and hence $z \in (a, b)$.

Because $S_k + \alpha_{k+1} = 1$, applying the two-point convexity inequality (the base case $n = 2$) to $z$ and $x_{k+1}$ gives:
$$
\begin{gather}
f\left(\sum_{i=1}^{k+1} \alpha_i x_i\right) = f\big(S_k z + \alpha_{k+1} x_{k+1}\big) \le S_k f(z) + \alpha_{k+1} f(x_{k+1}) \tag{8}
\end{gather}
$$

Now apply the induction hypothesis of step 4 to the point $z$ defined in step 7, using the $k$ weights $\beta_i := \frac{\alpha_i}{S_k}$:
$$
\begin{gather}
f(z) = f\left(\sum_{i=1}^k \frac{\alpha_i}{S_k} x_i\right) \le \sum_{i=1}^k \frac{\alpha_i}{S_k} f(x_i) \tag{9}
\end{gather}
$$
Multiplying step 9 by the strictly positive scalar $S_k > 0$ yields:
$$
\begin{gather}
S_k f(z) \le \sum_{i=1}^k \alpha_i f(x_i) \tag{10}
\end{gather}
$$
Substituting the upper bound of step 10 into step 8 proves the inequality for $k + 1$ terms:
$$
\begin{gather}
f\left(\sum_{i=1}^{k+1} \alpha_i x_i\right) \le \sum_{i=1}^k \alpha_i f(x_i) + \alpha_{k+1} f(x_{k+1}) = \sum_{i=1}^{k+1} \alpha_i f(x_i) \tag{11}
\end{gather}
$$

**Strict Convexity and Equality Conditions:**
If $f$ is strictly convex and all $\alpha_i > 0$, equality in step 8 holds if and only if $z = x_{k+1}$. Furthermore, equality in step 9 holds by the induction hypothesis if and only if $x_1 = x_2 = \dots = x_k$. If $x_1 = \dots = x_k$, then $z = \sum_{i=1}^k \frac{\alpha_i}{S_k} x_1 = x_1$. Therefore, equality holds across the entire chain if and only if $x_1 = \dots = x_k = x_{k+1}$.

By mathematical induction, the theorem is established for all $n \in \mathbb{N}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
