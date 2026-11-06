---
dg-publish: true
---
Let $f: U(x_0) \to \mathbb{R}$ be $n$ times differentiable at the interior point $x_0 \in \mathbb{R}$.

Define the remainder function $R_n(x)$ by:
$$
\begin{gather}
R_n(x) := f(x) - P_n(x_0; x) = f(x) - \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k \tag{1}
\end{gather}
$$

We must prove that:
$$
\begin{gather}
\lim_{x \to x_0} \frac{R_n(x)}{(x - x_0)^n} = 0 \tag{2}
\end{gather}
$$

### Step 1: Base Case ($n = 1$)
For $n = 1$, by Definition 1.1 of differentiability:
$$
\begin{gather}
R_1(x) = f(x) - f(x_0) - f'(x_0)(x - x_0) = o(x - x_0) \tag{3}
\end{gather}
$$
Dividing by $(x - x_0)$ yields $\lim_{x \to x_0} \frac{R_1(x)}{x - x_0} = 0$, establishing the base case.

### Step 2: Inductive Application of L'Hôpital / Cauchy MVT
For $n \ge 2$, by hypothesis $f$ is $(n-1)$ times differentiable on a neighborhood of $x_0$, and $f^{(n)}(x_0)$ exists. 

Evaluating the derivatives of $R_n(x)$ at $x = x_0$:
$$
\begin{gather}
R_n^{(k)}(x_0) = f^{(k)}(x_0) - P_n^{(k)}(x_0; x_0) = f^{(k)}(x_0) - f^{(k)}(x_0) = 0 \quad \forall k = 0, 1, \dots, n \tag{4}
\end{gather}
$$

Define the denominator function $g(x) := (x - x_0)^n$. Its derivatives satisfy:
$$
\begin{gather}
g^{(k)}(x_0) = 0 \quad \forall k = 0, 1, \dots, n-1, \quad \text{and} \quad g^{(n-1)}(x) = n!(x - x_0) \tag{5}
\end{gather}
$$

Applying Cauchy's Generalized Mean Value Theorem (Theorem 3.6) repeatedly $n - 1$ times on the interval between $x_0$ and $x$:
$$
\begin{gather}
\frac{R_n(x)}{(x - x_0)^n} = \frac{R_n'(x_1)}{n(x_1 - x_0)^{n-1}} = \frac{R_n''(x_2)}{n(n-1)(x_2 - x_0)^{n-2}} = \dots = \frac{R_n^{(n-1)}(x_{n-1})}{n!(x_{n-1} - x_0)} \tag{6}
\end{gather}
$$
where $x_{n-1}$ lies strictly between $x_0$ and $x$.

### Step 3: Evaluation of the Final Ratio
Differentiating $R_n(x)$ explicitly $n-1$ times:
$$
\begin{gather}
R_n^{(n-1)}(t) = f^{(n-1)}(t) - f^{(n-1)}(x_0) - f^{(n)}(x_0)(t - x_0) \tag{7}
\end{gather}
$$

Substituting equation (7) at $t = x_{n-1}$ into equation (6):
$$
\begin{gather}
\frac{R_n(x)}{(x - x_0)^n} = \frac{1}{n!} \left( \frac{f^{(n-1)}(x_{n-1}) - f^{(n-1)}(x_0)}{x_{n-1} - x_0} - f^{(n)}(x_0) \right) \tag{8}
\end{gather}
$$

As $x \to x_0$, the intermediate point $x_{n-1} \to x_0$. By definition of the $n$-th derivative $f^{(n)}(x_0) = (f^{(n-1)})'(x_0)$:
$$
\begin{gather}
\lim_{x_{n-1} \to x_0} \frac{f^{(n-1)}(x_{n-1}) - f^{(n-1)}(x_0)}{x_{n-1} - x_0} = f^{(n)}(x_0) \tag{9}
\end{gather}
$$

Taking the limit as $x \to x_0$ in equation (8):
$$
\begin{gather}
\lim_{x \to x_0} \frac{R_n(x)}{(x - x_0)^n} = \frac{1}{n!} \big( f^{(n)}(x_0) - f^{(n)}(x_0) \big) = 0 \tag{10}
\end{gather}
$$
which proves that $R_n(x) = o((x - x_0)^n)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
