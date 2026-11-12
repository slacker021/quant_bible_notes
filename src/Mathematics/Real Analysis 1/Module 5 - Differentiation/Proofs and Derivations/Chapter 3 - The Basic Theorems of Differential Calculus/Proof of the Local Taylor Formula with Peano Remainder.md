---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$ have $x_0$ as an accumulation point, and let $f: E \to \mathbb{R}$ possess derivatives up to order $n \ge 1$ at $x_0$.

The claim that the Taylor remainder satisfies $r_n(x_0; x) = o((x - x_0)^n)$ as $x \to x_0$, where:
$$
\begin{gather}
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k + r_n(x_0; x) \tag{1}
\end{gather}
$$
is proven by mathematical induction on the derivative order $n \in \mathbb{N}$.

**Base Case: $n = 1$.**
For $n = 1$, the hypothesis states that $f$ is differentiable at $x_0$. By the definition of the derivative established in [[Chapter 1 - Differentiable Functions#The Pointwise Derivative|Chapter 1]]:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = f'(x_0) \tag{2}
\end{gather}
$$
Subtracting $f'(x_0)$ from both sides of step 2 and combining terms under a single quotient:
$$
\begin{gather}
\lim_{E \ni x \to x_0} \frac{f(x) - f(x_0) - f'(x_0)(x - x_0)}{x - x_0} = 0 \tag{3}
\end{gather}
$$
By definition of Landau's Little-$o$ asymptotic relation, step 3 is equivalent to:
$$
\begin{gather}
f(x) - \big(f(x_0) + f'(x_0)(x - x_0)\big) = o(x - x_0) \quad \text{as } x \to x_0 \tag{4}
\end{gather}
$$
Defining $P_1(x_0; x) := f(x_0) + f'(x_0)(x - x_0)$, step 4 verifies that $r_1(x_0; x) = o(x - x_0)$. The base case $n = 1$ is thus established.

**Induction Hypothesis:**
Assume that the local Taylor formula holds for an integer $(n - 1) \ge 1$: whenever a function possesses $(n - 1)$ derivatives at $x_0$, its remainder of order $(n - 1)$ satisfies $r_{n-1}(x_0; x) = o((x - x_0)^{n-1})$ as $x \to x_0$.

**Induction Step:**
Let $f$ possess $n$ derivatives at $x_0$. Because the $n$-th derivative $f^{(n)}(x_0)$ exists, the $(n - 1)$-th derivative $f^{(n-1)}$ must exist in an open neighborhood $U(x_0)$ of $x_0$, ensuring that the first derivative $f'(t)$ exists everywhere on $U(x_0)$ and is itself $(n - 1)$ times differentiable at $x_0$.

Define the Taylor polynomial of degree $n$ of $f$ centered at $x_0$:
$$
\begin{gather}
P_n(x) := \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} (x - x_0)^k \tag{5}
\end{gather}
$$
and define the remainder function $r_n: U(x_0) \to \mathbb{R}$ by:
$$
\begin{gather}
r_n(x) := f(x) - P_n(x) \tag{6}
\end{gather}
$$
Evaluating step 6 at the anchor point $x = x_0$:
$$
\begin{gather}
r_n(x_0) = f(x_0) - P_n(x_0) = f(x_0) - f(x_0) = 0 \tag{7}
\end{gather}
$$

For every $t \in U(x_0)$, $r_n(t)$ is differentiable with respect to $t$. Differentiating step 5 with respect to $t$:
$$
\begin{gather}
P_n'(t) = \sum_{k=1}^n \frac{f^{(k)}(x_0)}{k!} k (t - x_0)^{k-1} = \sum_{k=1}^n \frac{f^{(k)}(x_0)}{(k - 1)!} (t - x_0)^{k-1} \tag{8}
\end{gather}
$$
Re-indexing step 8 by setting $j := k - 1 \in \{0, 1, \dots, n - 1\}$:
$$
\begin{gather}
P_n'(t) = \sum_{j=0}^{n-1} \frac{(f')^{(j)}(x_0)}{j!} (t - x_0)^j \tag{9}
\end{gather}
$$
Step 9 reveals that $P_n'(t)$ is identically the Taylor polynomial of degree $(n - 1)$ of the derived mapping $g := f'$ centered at $x_0$.

Differentiating the remainder of step 6:
$$
\begin{gather}
r_n'(t) = f'(t) - P_n'(t) \tag{10}
\end{gather}
$$
Because $f'$ possesses $(n - 1)$ derivatives at $x_0$, applying the induction hypothesis to $f'$ yields:
$$
\begin{gather}
r_n'(t) = f'(t) - P_n'(t) = o\big((t - x_0)^{n-1}\big) \quad \text{as } t \to x_0 \tag{11}
\end{gather}
$$

Now let $x \in U(x_0) \setminus \{x_0\}$. Consider the auxiliary function $v(t) := (t - x_0)^n$. Both $r_n(t)$ and $v(t)$ are continuous on the closed interval with endpoints $x_0$ and $x$, and differentiable on its open interior. Furthermore, the derivative $v'(t) = n(t - x_0)^{n-1} \neq 0$ on the interior. 

Applying [[Proof of Cauchy's Generalized Finite-Increment Theorem|Cauchy's Generalized Finite-Increment Theorem]] to $r_n(t)$ and $v(t)$:
$$
\begin{gather}
\frac{r_n(x) - r_n(x_0)}{v(x) - v(x_0)} = \frac{r_n'(\xi)}{v'(\xi)} \tag{12}
\end{gather}
$$
for some intermediate point $\xi$ lying strictly between $x_0$ and $x$.

Substituting $r_n(x_0) = 0$ from step 7 and $v(x_0) = 0$ into step 12:
$$
\begin{gather}
\frac{r_n(x)}{(x - x_0)^n} = \frac{r_n'(\xi)}{n(\xi - x_0)^{n-1}} = \frac{1}{n} \frac{r_n'(\xi)}{(\xi - x_0)^{n-1}} \tag{13}
\end{gather}
$$

Because $\xi$ lies strictly between $x_0$ and $x$, $|\xi - x_0| < |x - x_0|$. As $x \to x_0$, the intermediate point $\xi$ approaches $x_0$. Applying the asymptotic relation of step 11:
$$
\begin{gather}
\lim_{x \to x_0} \frac{r_n(x)}{(x - x_0)^n} = \frac{1}{n} \lim_{\xi \to x_0} \frac{r_n'(\xi)}{(\xi - x_0)^{n-1}} = \frac{1}{n} \times 0 = 0 \tag{14}
\end{gather}
$$

By definition of little-$o$, step 14 establishes that:
$$
\begin{gather}
r_n(x) = o\big((x - x_0)^n\big) \quad \text{as } x \to x_0 \tag{15}
\end{gather}
$$
By mathematical induction, the local Taylor formula holds for all natural numbers $n \in \mathbb{N}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$