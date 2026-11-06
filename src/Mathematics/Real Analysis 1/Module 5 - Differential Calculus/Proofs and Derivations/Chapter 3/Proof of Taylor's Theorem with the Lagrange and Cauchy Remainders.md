---
dg-publish: true
---
Let $f \in C^n([a, b])$ and suppose $f$ is $(n+1)$ times differentiable on $(a, b)$. Let $x_0, x \in [a, b]$ with $x \neq x_0$.

Fix $x$, and define an auxiliary function $F: [x_0, x] \to \mathbb{R}$ of the variable $t$ by:
$$
\begin{gather}
F(t) := f(x) - \sum_{k=0}^n \frac{f^{(k)}(t)}{k!}(x - t)^k \tag{1}
\end{gather}
$$

Evaluating $F$ at $t = x$:
$$
\begin{gather}
F(x) = f(x) - f(x) - 0 = 0 \tag{2}
\end{gather}
$$

Evaluating $F$ at $t = x_0$:
$$
\begin{gather}
F(x_0) = f(x) - \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k = R_n(x_0; x) \tag{3}
\end{gather}
$$

### Step 1: Differentiating the Auxiliary Function
Differentiating $F(t)$ with respect to $t$ using the product rule:
$$
\begin{gather}
F'(t) = -\frac{d}{dt}\left[ f(t) + \sum_{k=1}^n \frac{f^{(k)}(t)}{k!}(x - t)^k \right] \tag{4}
\end{gather}
$$

Expanding the derivative of each term:
$$
\begin{gather}
F'(t) = -f'(t) - \sum_{k=1}^n \left( \frac{f^{(k+1)}(t)}{k!}(x - t)^k - \frac{f^{(k)}(t)}{(k-1)!}(x - t)^{k-1} \right) \tag{5}
\end{gather}
$$

The sum telescopes completely, as every term except the highest cancels:
$$
\begin{gather}
F'(t) = -\frac{f^{(n+1)}(t)}{n!}(x - t)^n \tag{6}
\end{gather}
$$

### Step 2: Application of Cauchy's Generalized Mean Value Theorem
Let $\Phi: [x_0, x] \to \mathbb{R}$ be a continuous function on $[x_0, x]$, differentiable with non-vanishing derivative on $(x_0, x)$.

Applying Theorem 3.6 (Cauchy's Mean Value Theorem) to $F(t)$ and $\Phi(t)$ on $[x_0, x]$:
$$
\begin{gather}
\frac{F(x) - F(x_0)}{\Phi(x) - \Phi(x_0)} = \frac{F'(\xi)}{\Phi'(\xi)} \tag{7}
\end{gather}
$$
for some $\xi$ strictly between $x_0$ and $x$.

Substituting $F(x) = 0$, $F(x_0) = R_n(x_0; x)$, and equation (6) into equation (7):
$$
\begin{gather}
\frac{-R_n(x_0; x)}{\Phi(x) - \Phi(x_0)} = \frac{-\frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n}{\Phi'(\xi)} \tag{8}
\end{gather}
$$

Rearranging for the remainder:
$$
\begin{gather}
R_n(x_0; x) = \frac{\Phi(x) - \Phi(x_0)}{\Phi'(\xi)} \frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n \tag{9}
\end{gather}
$$

### Step 3: Derivation of the Lagrange Remainder Form
Choose $\Phi(t) := (x - t)^{n+1}$.
Then $\Phi'(t) = -(n+1)(x - t)^n$, $\Phi(x) = 0$, and $\Phi(x_0) = (x - x_0)^{n+1}$.
Substituting these expressions into equation (9):
$$
\begin{gather}
R_n(x_0; x) = \frac{0 - (x - x_0)^{n+1}}{-(n+1)(x - \xi)^n} \frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x - x_0)^{n+1} \tag{10}
\end{gather}
$$
which is the Lagrange form of the remainder.

### Step 4: Derivation of the Cauchy Remainder Form
Choose $\Phi(t) := x - t$.
Then $\Phi'(t) = -1$, $\Phi(x) = 0$, and $\Phi(x_0) = x - x_0$.
Substituting into equation (9):
$$
\begin{gather}
R_n(x_0; x) = \frac{0 - (x - x_0)}{-1} \frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n = \frac{f^{(n+1)}(\xi)}{n!}(x - \xi)^n (x - x_0) \tag{11}
\end{gather}
$$

Writing $\xi = x_0 + \theta(x - x_0)$ with $\theta \in (0, 1)$, we have $x - \xi = (1 - \theta)(x - x_0)$. Substituting into equation (11) gives:
$$
\begin{gather}
R_n(x_0; x) = \frac{f^{(n+1)}(x_0 + \theta(x - x_0))}{n!} (1 - \theta)^n (x - x_0)^{n+1} \tag{12}
\end{gather}
$$
which is the Cauchy form of the remainder.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
