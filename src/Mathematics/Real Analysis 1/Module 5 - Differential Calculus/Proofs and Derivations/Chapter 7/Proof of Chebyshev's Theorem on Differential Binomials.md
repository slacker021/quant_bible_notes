---
dg-publish: true
---
Consider the differential binomial integral:
$$
\begin{gather}
I = \int x^m (a + b x^n)^p \, dx \quad (a, b \in \mathbb{R} \setminus \{0\}, \ m, n, p \in \mathbb{Q}, \ n \neq 0) \tag{1}
\end{gather}
$$

### Step 1: Initial Substitution
Make the algebraic substitution $z = x^n$. Then $x = z^{1/n}$ and $dx = \frac{1}{n} z^{\frac{1}{n} - 1} dz$. 

Substituting into equation (1):
$$
\begin{gather}
I = \int (z^{1/n})^m (a + b z)^p \left( \frac{1}{n} z^{\frac{1}{n} - 1} \right) dz = \frac{1}{n} \int z^{\frac{m+1}{n} - 1} (a + b z)^p \, dz \tag{2}
\end{gather}
$$

Define the rational parameter:
$$
\begin{gather}
q := \frac{m + 1}{n} - 1 \in \mathbb{Q} \tag{3}
\end{gather}
$$
Equation (2) simplifies to:
$$
\begin{gather}
I = \frac{1}{n} \int z^q (a + b z)^p \, dz \tag{4}
\end{gather}
$$

We analyze the three conditions under which integral (4) rationalizes.

### Case 1: $p \in \mathbb{Z}$
If $p$ is an integer, let $q = \frac{r}{s}$ with $s \in \mathbb{N}$ and $\gcd(r, s) = 1$.

Make the rationalizing substitution $z = u^s$, so that $dz = s u^{s-1} du$ and $z^q = (u^s)^{r/s} = u^r$. 

Integral (4) becomes:
$$
\begin{gather}
I = \frac{s}{n} \int u^r (a + b u^s)^p u^{s-1} \, du = \frac{s}{n} \int u^{r + s - 1} (a + b u^s)^p \, du \tag{5}
\end{gather}
$$

Because $p \in \mathbb{Z}$ and $r, s \in \mathbb{Z}$, the integrand in equation (5) is a rational function of $u$. By the partial fraction theorem, every rational function integrates in elementary functions.

### Case 2: $q \in \mathbb{Z} \iff \frac{m+1}{n} \in \mathbb{Z}$
Suppose $q$ is an integer, and let $p = \frac{\lambda}{\mu}$ with $\mu \in \mathbb{N}$ and $\gcd(\lambda, \mu) = 1$.

Make the substitution $a + b z = u^\mu$. Then $z = \frac{u^\mu - a}{b}$ and $dz = \frac{\mu}{b} u^{\mu - 1} du$.

Integral (4) becomes:
$$
\begin{gather}
I = \frac{\mu}{n b} \int \left( \frac{u^\mu - a}{b} \right)^q u^\lambda u^{\mu - 1} \, du \tag{6}
\end{gather}
$$

Because $q \in \mathbb{Z}$ and $\lambda, \mu \in \mathbb{Z}$, the integrand is a rational function of $u$, integrating in elementary functions.

### Case 3: $q + p \in \mathbb{Z} \iff \frac{m+1}{n} + p \in \mathbb{Z}$
Factor out $z^p$ from $(a + b z)^p$ in integral (4):
$$
\begin{gather}
I = \frac{1}{n} \int z^q \left[ z \left( \frac{a}{z} + b \right) \right]^p dz = \frac{1}{n} \int z^{q+p} \left( a z^{-1} + b \right)^p dz \tag{7}
\end{gather}
$$

Let $p = \frac{\lambda}{\mu}$ with $\mu \in \mathbb{N}$. Make the substitution:
$$
\begin{gather}
a z^{-1} + b = u^\mu \implies \frac{a}{z} = u^\mu - b \implies z = \frac{a}{u^\mu - b} \tag{8}
\end{gather}
$$

Computing the differential:
$$
\begin{gather}
dz = -\frac{a \mu u^{\mu - 1}}{(u^\mu - b)^2} du \tag{9}
\end{gather}
$$

Substituting equations (8) and (9) into equation (7):
$$
\begin{gather}
I = -\frac{a \mu}{n} \int \left( \frac{a}{u^\mu - b} \right)^{q+p} u^\lambda \frac{u^{\mu - 1}}{(u^\mu - b)^2} \, du \tag{10}
\end{gather}
$$

Because $q + p \in \mathbb{Z}$ by hypothesis, every exponent in equation (10) is an integer. Thus, the integrand is a rational function of $u$, which integrates into elementary functions.

Chebyshev (1853) proved using Liouville's theorem on integration in finite terms that if none of these three conditions hold, the differential binomial cannot be expressed in finite elementary terms.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
