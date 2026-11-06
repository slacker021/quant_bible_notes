---
dg-publish: true
---
Let $f: \mathbb{R} \setminus \{0\} \to \mathbb{R}$ be the reciprocal sine function defined by:
$$
\begin{gather}
f(x) := \sin\left(\frac{1}{x}\right) \tag{1}
\end{gather}
$$

# Proposition 1
The non-existence of the limit as $x \to 0$ is demonstrated using the Heine sequential criterion (from the [[Proof of the Equivalence of Cauchy and Heine Definitions]]). 

Construct two sequences $\{x_n\}_{n=1}^\infty$ and $\{y_n\}_{n=1}^\infty$ of non-zero real numbers:
$$
\begin{gather}
x_n := \frac{1}{\frac{\pi}{2} + 2\pi n}, \qquad y_n := \frac{1}{\pi n}, \quad n \in \mathbb{N} \tag{2}
\end{gather}
$$

For all $n \in \mathbb{N}$, the denominators in step 2 are strictly positive, ensuring that $x_n, y_n \in \mathbb{R} \setminus \{0\}$. Furthermore, because $\lim_{n \to \infty} (\frac{\pi}{2} + 2\pi n) = +\infty$ and $\lim_{n \to \infty} (\pi n) = +\infty$, taking reciprocals yields:
$$
\begin{gather}
\lim_{n \to \infty} x_n = 0 \quad \text{and} \quad \lim_{n \to \infty} y_n = 0 \tag{3}
\end{gather}
$$

Now evaluate $f$ along the terms of the first sequence $\{x_n\}$:
$$
\begin{gather}
f(x_n) = \sin\left(\frac{1}{x_n}\right) = \sin\left(\frac{\pi}{2} + 2\pi n\right) = 1 \quad \forall n \in \mathbb{N} \tag{4}
\end{gather}
$$
Because the sequence of image values in step 4 is identically equal to $1$, its limit is:
$$
\begin{gather}
\lim_{n \to \infty} f(x_n) = 1 \tag{5}
\end{gather}
$$

Concurrently, evaluate $f$ along the terms of the second sequence $\{y_n\}$:
$$
\begin{gather}
f(y_n) = \sin\left(\frac{1}{y_n}\right) = \sin(\pi n) = 0 \quad \forall n \in \mathbb{N} \tag{6}
\end{gather}
$$
Because the sequence of image values in step 6 is identically equal to $0$, its limit is:
$$
\begin{gather}
\lim_{n \to \infty} f(y_n) = 0 \tag{7}
\end{gather}
$$

By the Heine criterion, if the functional limit $\lim_{x \to 0} f(x) = L$ existed, every sequence of non-zero arguments converging to $0$ would produce an image sequence converging to $L$. By the uniqueness of limits in $\mathbb{R}$, step 5 and step 7 would require $L = 1$ and $L = 0$, which is impossible because $1 \neq 0$. 

Consequently, the functional limit does not exist:
$$
\begin{gather}
\lim_{x \to 0} \sin\left(\frac{1}{x}\right) \quad \text{does not exist} \tag{8}
\end{gather}
$$

---
# Proposition 2
Let $c \in \mathbb{R}$ be an arbitrary real number, and consider the extended function $\tilde{f}: \mathbb{R} \to \mathbb{R}$ defined by:
$$
\begin{gather}
\tilde{f}(x) := \begin{cases} \sin\left(\frac{1}{x}\right), & x \in \mathbb{R} \setminus \{0\} \\[2mm] c, & x = 0 \end{cases} \tag{9}
\end{gather}
$$

Because $0$ is an accumulation point of the domain $\mathbb{R}$ ($0 \in \mathbb{R}'$), by the [[Proof of the Commutation of Continuous Mappings with Accumulation Limits]], $\tilde{f}$ is continuous at $0$ if and only if the functional limit exists and equals the assigned functional value:
$$
\begin{gather}
\lim_{x \to 0} \tilde{f}(x) = \tilde{f}(0) = c \tag{10}
\end{gather}
$$

By definition of the functional limit, $\lim_{x \to 0} \tilde{f}(x)$ depends only on the values assumed by $\tilde{f}$ on the punctured domain $\mathbb{R} \setminus \{0\}$. For all $x \neq 0$, step 9 gives $\tilde{f}(x) = f(x)$. 

By the [[Proof of the Punctured Neighborhood Identity Principle]], the limits of $\tilde{f}$ and $f$ at the origin coincide:
$$
\begin{gather}
\lim_{x \to 0} \tilde{f}(x) = \lim_{x \to 0} f(x) \tag{11}
\end{gather}
$$

By step 8 of Proposition 1, the limit $\lim_{x \to 0} f(x)$ does not exist. Consequently, the limit $\lim_{x \to 0} \tilde{f}(x)$ fails to exist as well. 

Because the limit is nonexistent, the equality in step 10 cannot be satisfied for any choice of $c \in \mathbb{R}$. 

Therefore, no value assigned to $\tilde{f}(0)$ can render the function continuous at $x = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$