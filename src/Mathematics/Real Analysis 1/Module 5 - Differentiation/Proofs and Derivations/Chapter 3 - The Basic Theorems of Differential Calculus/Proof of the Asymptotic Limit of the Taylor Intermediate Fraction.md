---
dg-publish: true
---
Let $f$ have continuous derivatives up to order $(n + 2)$ in an open neighborhood $U(x_0)$ of $x_0 \in \mathbb{R}$, and suppose that the $(n + 2)$-th derivative at the center is non-zero:
$$
\begin{gather}
f^{(n+2)}(x_0) \neq 0 \tag{1}
\end{gather}
$$

Let $x \in U(x_0) \setminus \{x_0\}$, and define the non-zero displacement $h := x - x_0 \neq 0$. By definition, the Taylor remainder of order $n$ associated with the Taylor polynomial $P_n(x_0; x)$ is:
$$
\begin{gather}
r_n(x_0; x) := f(x) - \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} h^k \tag{2}
\end{gather}
$$

By virtue of [[Proof of Lagrange's Form of the Taylor Remainder|Lagrange's Form of the Taylor Remainder]], there exists a parameter $\theta(x) \in (0, 1)$ such that:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}\big(x_0 + \theta(x) h\big)}{(n + 1)!} h^{n+1} \tag{3}
\end{gather}
$$

Because $f \in C^{n+2}(U(x_0))$, the derivative function $g(t) := f^{(n+1)}(t)$ is continuously differentiable on $U(x_0)$, with derivative $g'(t) = f^{(n+2)}(t)$. Applying the first-order Taylor expansion with Peano remainder to $g$ at the point $x_0$:
$$
\begin{gather}
g(x_0 + \Delta) = g(x_0) + g'(x_0) \Delta + o(\Delta) \quad \text{as } \Delta \to 0 \tag{4}
\end{gather}
$$
Setting $\Delta := \theta(x) h$, because $\theta(x) \in (0, 1)$, the displacement satisfies $|\Delta| < |h|$. As $h \to 0$, $\Delta \to 0$, and step 4 yields:
$$
\begin{gather}
f^{(n+1)}\big(x_0 + \theta(x) h\big) = f^{(n+1)}(x_0) + f^{(n+2)}(x_0) \theta(x) h + o(h) \tag{5}
\end{gather}
$$

Substituting step 5 into the remainder formula of step 3:
$$
\begin{gather}
r_n(x_0; x) = \frac{1}{(n + 1)!} \left(f^{(n+1)}(x_0) + f^{(n+2)}(x_0) \theta(x) h + o(h)\right) h^{n+1} \tag{6}
\end{gather}
$$
Distributing $h^{n+1}$ across the terms in step 6:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1} + \frac{f^{(n+2)}(x_0)}{(n + 1)!} \theta(x) h^{n+2} + o(h^{n+2}) \tag{7}
\end{gather}
$$

On the other hand, expanding the function $f(x) = f(x_0 + h)$ to order $(n + 1)$ with Peano remainder via [[Proof of the Local Taylor Formula with Peano Remainder|The Local Taylor Formula with Peano Remainder]]:
$$
\begin{gather}
f(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} h^k + \frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1} + \frac{f^{(n+2)}(x_0)}{(n + 2)!} h^{n+2} + o(h^{n+2}) \tag{8}
\end{gather}
$$
Subtracting the $n$-th degree Taylor polynomial $\sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!} h^k$ from step 8 isolates the remainder $r_n(x_0; x)$:
$$
\begin{gather}
r_n(x_0; x) = \frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1} + \frac{f^{(n+2)}(x_0)}{(n + 2)!} h^{n+2} + o(h^{n+2}) \tag{9}
\end{gather}
$$

Equating the two analytical expressions for $r_n(x_0; x)$ from step 7 and step 9:
$$
\begin{gather}
\frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1} + \frac{f^{(n+2)}(x_0)}{(n + 1)!} \theta(x) h^{n+2} + o(h^{n+2}) = \frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1} + \frac{f^{(n+2)}(x_0)}{(n + 2)!} h^{n+2} + o(h^{n+2}) \tag{10}
\end{gather}
$$

Subtracting the identical leading term $\frac{f^{(n+1)}(x_0)}{(n + 1)!} h^{n+1}$ from both sides of step 10:
$$
\begin{gather}
\frac{f^{(n+2)}(x_0)}{(n + 1)!} \theta(x) h^{n+2} + o(h^{n+2}) = \frac{f^{(n+2)}(x_0)}{(n + 2)!} h^{n+2} + o(h^{n+2}) \tag{11}
\end{gather}
$$

Dividing step 11 by the non-zero monomial $h^{n+2}$:
$$
\begin{gather}
\frac{f^{(n+2)}(x_0)}{(n + 1)!} \theta(x) + o(1) = \frac{f^{(n+2)}(x_0)}{(n + 2)!} + o(1) \tag{12}
\end{gather}
$$

Taking the limit in step 12 as $h \to 0$ (which corresponds to $x \to x_0$):
$$
\begin{gather}
\frac{f^{(n+2)}(x_0)}{(n + 1)!} \lim_{x \to x_0} \theta(x) = \frac{f^{(n+2)}(x_0)}{(n + 2)!} \tag{13}
\end{gather}
$$

Because $f^{(n+2)}(x_0) \neq 0$ by step 1, dividing both sides of step 13 by $f^{(n+2)}(x_0)$ yields:
$$
\begin{gather}
\frac{1}{(n + 1)!} \lim_{x \to x_0} \theta(x) = \frac{1}{(n + 2)!} \tag{14}
\end{gather}
$$

Multiplying step 14 by $(n + 1)!$ produces the final asymptotic limit:
$$
\begin{gather}
\lim_{x \to x_0} \theta(x) = \frac{(n + 1)!}{(n + 2)!} = \frac{(n + 1)!}{(n + 2)(n + 1)!} = \frac{1}{n + 2} \tag{15}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$