---
dg-publish: true
---
Let $r > 0$, let the domain $I := (-r, r)$ be a symmetric open interval centered at the origin, and let $f: (-r, r) \to \mathbb{R}$ be a function possessing derivatives up to order $n \ge 1$ at $x_0 = 0$.

# Proposition 1
Assume that $f$ is an even function on $(-r, r)$, satisfying the symmetry identity:
$$
\begin{gather}
f(-x) = f(x), \quad \forall x \in (-r, r) \tag{1}
\end{gather}
$$

By virtue of [[Proof of Parity Alternation Under Differentiation|Parity Alternation Under Differentiation]], differentiating an even function reverses parity, producing an odd function, while differentiating an odd function produces an even function. By mathematical induction on the derivative order $m \le n$:
$$
\begin{gather}
f^{(m)}(-x) = (-1)^m f^{(m)}(x), \quad \forall x \in (-r, r) \tag{2}
\end{gather}
$$

Let $m = 2k + 1 \le n$ be an arbitrary odd integer. Substituting $m = 2k + 1$ into step 2:
$$
\begin{gather}
f^{(2k+1)}(-x) = (-1)^{2k+1} f^{(2k+1)}(x) = -f^{(2k+1)}(x) \tag{3}
\end{gather}
$$
Evaluating step 3 at the origin $x = 0$:
$$
\begin{gather}
f^{(2k+1)}(0) = -f^{(2k+1)}(0) \tag{4}
\end{gather}
$$
Adding $f^{(2k+1)}(0)$ to both sides of step 4:
$$
\begin{gather}
2 f^{(2k+1)}(0) = 0 \implies f^{(2k+1)}(0) = 0 \tag{5}
\end{gather}
$$

By [[Proof of the Local Taylor Formula with Peano Remainder|The Local Taylor Formula]], the Taylor polynomial of degree $n$ centered at $x_0 = 0$ is:
$$
\begin{gather}
P_n(0; x) = \sum_{m=0}^n \frac{f^{(m)}(0)}{m!} x^m \tag{6}
\end{gather}
$$
Splitting the sum in step 6 into even and odd indices:
$$
\begin{gather}
P_n(0; x) = \sum_{0 \le 2k \le n} \frac{f^{(2k)}(0)}{(2k)!} x^{2k} + \sum_{0 \le 2k+1 \le n} \frac{f^{(2k+1)}(0)}{(2k+1)!} x^{2k+1} \tag{7}
\end{gather}
$$
By step 5, every odd-order derivative coefficient in the second summation of step 7 vanishes:
$$
\begin{gather}
\frac{f^{(2k+1)}(0)}{(2k+1)!} = 0, \quad \forall 2k + 1 \le n \tag{8}
\end{gather}
$$
Consequently, step 7 simplifies to:
$$
\begin{gather}
P_n(0; x) = \sum_{k=0}^{\lfloor n/2 \rfloor} \frac{f^{(2k)}(0)}{(2k)!} x^{2k} \tag{9}
\end{gather}
$$
which contains exclusively even powers of $x$.

---
# Proposition 2
Assume that $f$ is an odd function on $(-r, r)$, satisfying the anti-symmetry identity:
$$
\begin{gather}
f(-x) = -f(x), \quad \forall x \in (-r, r) \tag{10}
\end{gather}
$$

By [[Proof of Parity Alternation Under Differentiation|Parity Alternation Under Differentiation]], differentiating an odd function produces an even function. By induction on $m \le n$:
$$
\begin{gather}
f^{(m)}(-x) = (-1)^{m+1} f^{(m)}(x), \quad \forall x \in (-r, r) \tag{11}
\end{gather}
$$

Let $m = 2k \le n$ be an arbitrary even integer. Substituting $m = 2k$ into step 11:
$$
\begin{gather}
f^{(2k)}(-x) = (-1)^{2k+1} f^{(2k)}(x) = -f^{(2k)}(x) \tag{12}
\end{gather}
$$
Evaluating step 12 at the origin $x = 0$:
$$
\begin{gather}
f^{(2k)}(0) = -f^{(2k)}(0) \tag{13}
\end{gather}
$$
Adding $f^{(2k)}(0)$ to both sides of step 13:
$$
\begin{gather}
2 f^{(2k)}(0) = 0 \implies f^{(2k)}(0) = 0 \tag{14}
\end{gather}
$$

Evaluating the Taylor polynomial of degree $n$ centered at $x_0 = 0$:
$$
\begin{gather}
P_n(0; x) = \sum_{0 \le 2k \le n} \frac{f^{(2k)}(0)}{(2k)!} x^{2k} + \sum_{0 \le 2k+1 \le n} \frac{f^{(2k+1)}(0)}{(2k+1)!} x^{2k+1} \tag{15}
\end{gather}
$$
By step 14, every even-order derivative coefficient in the first summation of step 15 vanishes:
$$
\begin{gather}
\frac{f^{(2k)}(0)}{(2k)!} = 0, \quad \forall 2k \le n \tag{16}
\end{gather}
$$
Consequently, step 15 simplifies to:
$$
\begin{gather}
P_n(0; x) = \sum_{k=0}^{\lfloor (n-1)/2 \rfloor} \frac{f^{(2k+1)}(0)}{(2k+1)!} x^{2k+1} \tag{17}
\end{gather}
$$
which contains exclusively odd powers of $x$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$