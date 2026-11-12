---
dg-publish: true
---
Let $x_0 \in \mathbb{R}$ be an anchor point, let $n \in \mathbb{N} \cup \{0\}$, and let $(\alpha_0, \alpha_1, \dots, \alpha_n) \in \mathbb{R}^{n+1}$ be an arbitrary sequence of real coefficients.

**Existence of the Interpolating Polynomial:**
Define the polynomial function $P_n: \mathbb{R} \to \mathbb{R}$ explicitly by the Taylor expansion centered at $x_0$:
$$
\begin{gather}
P_n(x) := \sum_{j=0}^n \frac{\alpha_j}{j!} (x - x_0)^j \tag{1}
\end{gather}
$$

Because $P_n$ is a finite linear combination of monomials $(x - x_0)^j$ with $0 \le j \le n$, $P_n$ is a polynomial of degree at most $n$.

Let $k \in \{0, 1, \dots, n\}$ be an arbitrary index. Differentiating $P_n(x)$ to order $k$ using the [[Proof of The Linearity of Differentiation|Linearity of Differentiation]] gives:
$$
\begin{gather}
P_n^{(k)}(x) = \sum_{j=0}^n \frac{\alpha_j}{j!} \frac{d^k}{dx^k}\big[(x - x_0)^j\big] \tag{2}
\end{gather}
$$

Evaluating the $k$-th derivative of the monomial $(x - x_0)^j$ yields:
$$
\begin{gather}
\frac{d^k}{dx^k}\big[(x - x_0)^j\big] = \begin{cases} 0 & \text{if } j < k \\[2mm] \dfrac{j!}{(j - k)!} (x - x_0)^{j - k} & \text{if } j \ge k \end{cases} \tag{3}
\end{gather}
$$

Substituting step 3 into step 2 eliminates all summands with $j < k$, truncating the lower index of the summation:
$$
\begin{gather}
P_n^{(k)}(x) = \sum_{j=k}^n \frac{\alpha_j}{j!} \left[\frac{j!}{(j - k)!} (x - x_0)^{j - k}\right] = \sum_{j=k}^n \frac{\alpha_j}{(j - k)!} (x - x_0)^{j - k} \tag{4}
\end{gather}
$$

Evaluating step 4 at the anchor point $x = x_0$ produces:
$$
\begin{gather}
P_n^{(k)}(x_0) = \frac{\alpha_k}{(k - k)!} (x_0 - x_0)^0 + \sum_{j=k+1}^n \frac{\alpha_j}{(j - k)!} (x_0 - x_0)^{j - k} \tag{5}
\end{gather}
$$

Because $(x_0 - x_0)^{j - k} = 0^{j - k} = 0$ for all $j \ge k + 1$, and $(x_0 - x_0)^0 = 1$ with $0! = 1$, all terms in the summation vanish identically except for $j = k$:
$$
\begin{gather}
P_n^{(k)}(x_0) = \frac{\alpha_k}{0!} \cdot 1 + 0 = \alpha_k \tag{6}
\end{gather}
$$

Because step 6 holds for each $k \in \{0, 1, \dots, n\}$, the polynomial $P_n$ satisfies the jet interpolation conditions.

**Uniqueness of the Interpolating Polynomial:**
Suppose that $Q_n(x)$ is another polynomial of degree at most $n$ that satisfies the identical jet coordinates at $x_0$:
$$
\begin{gather}
Q_n^{(k)}(x_0) = \alpha_k, \quad \forall k \in \{0, 1, \dots, n\} \tag{7}
\end{gather}
$$

Define the difference polynomial $R_n: \mathbb{R} \to \mathbb{R}$ by:
$$
\begin{gather}
R_n(x) := P_n(x) - Q_n(x) \tag{8}
\end{gather}
$$

Because $P_n$ and $Q_n$ are polynomials of degree at most $n$, their difference $R_n$ is also a polynomial of degree at most $n$. Expressing $R_n(x)$ in powers of $(x - x_0)$ yields:
$$
\begin{gather}
R_n(x) = \sum_{j=0}^n c_j (x - x_0)^j \tag{9}
\end{gather}
$$
for some uniquely determined coefficients $(c_0, c_1, \dots, c_n) \in \mathbb{R}^{n+1}$.

Differentiating step 9 to order $k \in \{0, 1, \dots, n\}$ and evaluating at $x = x_0$ yields:
$$
\begin{gather}
R_n^{(k)}(x_0) = k! \, c_k \tag{10}
\end{gather}
$$

On the other hand, differentiating step 8 via linearity and applying step 6 and step 7 gives:
$$
\begin{gather}
R_n^{(k)}(x_0) = P_n^{(k)}(x_0) - Q_n^{(k)}(x_0) = \alpha_k - \alpha_k = 0 \tag{11}
\end{gather}
$$

Equating step 10 and step 11 reveals:
$$
\begin{gather}
k! \, c_k = 0 \implies c_k = 0, \quad \forall k \in \{0, 1, \dots, n\} \tag{12}
\end{gather}
$$

Because every coefficient $c_k = 0$, step 9 confirms that $R_n(x) \equiv 0$ on $\mathbb{R}$, which implies:
$$
\begin{gather}
P_n(x) \equiv Q_n(x) \tag{13}
\end{gather}
$$

Thus, the polynomial $P_n(x)$ is uniquely determined.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
