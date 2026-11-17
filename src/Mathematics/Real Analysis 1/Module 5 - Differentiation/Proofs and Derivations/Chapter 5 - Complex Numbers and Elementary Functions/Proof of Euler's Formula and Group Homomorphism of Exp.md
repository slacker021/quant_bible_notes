---
dg-publish: true
---
Let the complex exponential mapping $\exp : \mathbb{C} \to \mathbb{C}$ be defined by the everywhere convergent power series:
$$
\begin{gather}
\exp(z) := \sum_{n=0}^\infty \frac{z^n}{n!} \tag{1}
\end{gather}
$$
and let the real cosine and sine functions be defined by their Maclaurin power series:
$$
\begin{gather}
\cos(x) := \sum_{k=0}^\infty \frac{(-1)^k x^{2k}}{(2k)!} \quad \text{and} \quad \sin(x) := \sum_{k=0}^\infty \frac{(-1)^k x^{2k+1}}{(2k+1)!} \tag{2}
\end{gather}
$$
for all $x \in \mathbb{R}$. Let $(\mathbb{C}, +)$ denote the additive group of complex numbers and $(\mathbb{C}^\times, \cdot)$ the multiplicative group of nonzero complex numbers, where $\mathbb{C}^\times := \mathbb{C} \setminus \{0\}$.

---
# Proposition 1
Substitute $z = i \theta$ into the power series definition of step 1:
$$
\begin{gather}
\exp(i \theta) = \sum_{n=0}^\infty \frac{(i \theta)^n}{n!} = \sum_{n=0}^\infty \frac{i^n \theta^n}{n!} \tag{3}
\end{gather}
$$
By [[Proof of Absolute Convergence and Cauchy Product for the Complex Exponential Series|the absolute convergence of the complex exponential series]], the series $\sum_{n=0}^\infty \frac{(i \theta)^n}{n!}$ converges absolutely in $\mathbb{C}$.

Because the series converges absolutely, its terms can be rearranged without altering the sum. Partition the non-negative integers into even indices $n = 2k$ and odd indices $n = 2k+1$ for $k \in \mathbb{N} \cup \{0\}$:
$$
\begin{gather}
\exp(i \theta) = \sum_{k=0}^\infty \frac{i^{2k} \theta^{2k}}{(2k)!} + \sum_{k=0}^\infty \frac{i^{2k+1} \theta^{2k+1}}{(2k+1)!} \tag{4}
\end{gather}
$$
Notice that by definition of the imaginary unit $i^2 = -1$:
$$
\begin{gather}
i^{2k} = (i^2)^k = (-1)^k \tag{5}
\end{gather}
$$
and
$$
\begin{gather}
i^{2k+1} = i^{2k} \cdot i = (-1)^k i \tag{6}
\end{gather}
$$
Substituting step 5 and step 6 into step 4 yields:
$$
\begin{gather}
\exp(i \theta) = \sum_{k=0}^\infty \frac{(-1)^k \theta^{2k}}{(2k)!} + i \sum_{k=0}^\infty \frac{(-1)^k \theta^{2k+1}}{(2k+1)!} \tag{7}
\end{gather}
$$
Recognizing the power series definitions of $\cos(\theta)$ and $\sin(\theta)$ from step 2, step 7 becomes:
$$
\begin{gather}
\exp(i \theta) = \cos(\theta) + i \sin(\theta) \tag{8}
\end{gather}
$$
which establishes Euler's formula.

---
# Proposition 2
By [[Proof of Absolute Convergence and Cauchy Product for the Complex Exponential Series|the Cauchy product theorem for the complex exponential series]], the functional equation holds for all $z_1, z_2 \in \mathbb{C}$:
$$
\begin{gather}
\exp(z_1 + z_2) = \exp(z_1) \exp(z_2) \tag{9}
\end{gather}
$$
Evaluating the series of step 1 at $z = 0$ yields:
$$
\begin{gather}
\exp(0) = \frac{0^0}{0!} + \sum_{n=1}^\infty \frac{0^n}{n!} = 1 + 0 = 1 \tag{10}
\end{gather}
$$
For any $z \in \mathbb{C}$, set $z_1 = z$ and $z_2 = -z$. Applying step 9 and step 10 gives:
$$
\begin{gather}
\exp(z) \exp(-z) = \exp(z + (-z)) = \exp(0) = 1 \tag{11}
\end{gather}
$$
If there existed an element $z_0 \in \mathbb{C}$ such that $\exp(z_0) = 0$, step 11 would imply:
$$
\begin{gather}
0 \cdot \exp(-z_0) = 1 \implies 0 = 1 \tag{12}
\end{gather}
$$
which is a contradiction. Therefore, $\exp(z) \neq 0$ for every $z \in \mathbb{C}$.

Consequently, the image of $\exp$ is contained entirely in $\mathbb{C}^\times = \mathbb{C} \setminus \{0\}$.

Equation 14 establishes that $\exp(z)$ is invertible in the multiplicative group $(\mathbb{C}^\times, \cdot)$, and its multiplicative inverse is:
$$
\begin{gather}
(\exp(z))^{-1} = \exp(-z) \tag{13}
\end{gather}
$$
Because the mapping $\exp : \mathbb{C} \to \mathbb{C}^\times$ preserves group operations:
$$
\begin{gather}
\exp(z_1 + z_2) = \exp(z_1) \cdot \exp(z_2) \tag{14}
\end{gather}
$$
and maps the identity element of $(\mathbb{C}, +)$ to the identity element of $(\mathbb{C}^\times, \cdot)$:
$$
\begin{gather}
\exp(0) = 1 \tag{15}
\end{gather}
$$
it is a group homomorphism from $(\mathbb{C}, +)$ into $(\mathbb{C}^\times, \cdot)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$