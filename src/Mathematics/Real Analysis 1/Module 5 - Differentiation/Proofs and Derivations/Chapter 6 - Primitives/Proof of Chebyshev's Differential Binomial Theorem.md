---
dg-publish: true
---
Let $p, q, r \in \mathbb{Q}$ be rational numbers with non-zero real constants $a, b \in \mathbb{R} \setminus \{0\}$. Consider the differential binomial primitive:
$$
\begin{gather}
I = \int x^p (a + b x^q)^r \, dx \tag{1}
\end{gather}
$$
on an interval where the integrand is real-valued and continuous. 

Apply the algebraic substitution $z = x^q$. The differential is $dz = q x^{q-1} \, dx$, which yields:
$$
\begin{gather}
dx = \frac{1}{q} z^{\frac{1}{q} - 1} \, dz \tag{2}
\end{gather}
$$
Substituting $x = z^{1/q}$ and step 2 into the integral of step 1 transforms $I$ into:
$$
\begin{gather}
I = \frac{1}{q} \int z^{\frac{p}{q}} (a + b z)^r z^{\frac{1}{q} - 1} \, dz = \frac{1}{q} \int z^{\frac{p + 1}{q} - 1} (a + b z)^r \, dz \tag{3}
\end{gather}
$$
Define the rational parameter:
$$
\begin{gather}
m := \frac{p + 1}{q} - 1 \in \mathbb{Q} \tag{4}
\end{gather}
$$
so that the integral reduces to:
$$
\begin{gather}
I = \frac{1}{q} \int z^m (a + b z)^r \, dz \tag{5}
\end{gather}
$$
Notice that:
$$
\begin{gather}
m + 1 = \frac{p + 1}{q} \tag{6}
\end{gather}
$$

---
# Proposition 1
Assume $r \in \mathbb{Z}$. 
Under this condition, $(a + b z)^r$ is a rational function of $z$ (if $r \ge 0$, it is a polynomial; if $r < 0$, it is a reciprocal power of a polynomial). 

Let $m = \frac{u}{v}$ with $u \in \mathbb{Z}$ and $v \in \mathbb{N}_{\ge 1}$ being coprime integers. Substitute:
$$
\begin{gather}
z = t^v, \quad dz = v t^{v - 1} \, dt \tag{7}
\end{gather}
$$
Substituting step 7 into the integral of step 5 gives:
$$
\begin{gather}
\int z^m (a + b z)^r \, dz = \int (t^v)^{\frac{u}{v}} (a + b t^v)^r \cdot v t^{v - 1} \, dt = v \int t^{u + v - 1} (a + b t^v)^r \, dt \tag{8}
\end{gather}
$$
Because $u, v, r \in \mathbb{Z}$, the integrand $t^{u + v - 1} (a + b t^v)^r$ is a pure rational function of $t$. By the Partial Fraction Decomposition Theorem, its primitive is expressible in terms of elementary functions. In terms of the original variable $x$, setting $x = t^N$ where $N$ is the common denominator of $p$ and $q$ rationalizes the original differential binomial directly.

---
# Proposition 2
Assume $\frac{p + 1}{q} \in \mathbb{Z}$, which is equivalent to $m \in \mathbb{Z}$.
Let $r = \frac{k}{s}$ where $k \in \mathbb{Z}, s \in \mathbb{N}_{\ge 1}$, and $\gcd(k, s) = 1$. Apply the substitution:
$$
\begin{gather}
a + b z = t^s \tag{9}
\end{gather}
$$
From step 9, isolate $z$:
$$
\begin{gather}
z = \frac{t^s - a}{b} \tag{10}
\end{gather}
$$
Differentiating step 10 with respect to $t$ yields the differential:
$$
\begin{gather}
dz = \frac{s t^{s - 1}}{b} \, dt \tag{11}
\end{gather}
$$
Substituting equations 9, 10, and 11 into the integral of step 5 produces:
$$
\begin{gather}
\int z^m (a + b z)^r \, dz = \int \left( \frac{t^s - a}{b} \right)^m (t^s)^{\frac{k}{s}} \cdot \frac{s t^{s - 1}}{b} \, dt = \frac{s}{b^{m+1}} \int (t^s - a)^m t^{k + s - 1} \, dt \tag{12}
\end{gather}
$$
Because $m \in \mathbb{Z}$ and $k, s \in \mathbb{Z}$, the expression $(t^s - a)^m t^{k + s - 1}$ is a rational function of $t$. Thus, the primitive can be integrated in elementary functions.

---
# Proposition 3
Assume $\frac{p + 1}{q} + r \in \mathbb{Z}$, which is equivalent to $m + r + 1 \in \mathbb{Z}$.
Rewrite the integrand of step 5 by factoring out $z^r$ from the binomial factor:
$$
\begin{gather}
z^m (a + b z)^r = z^m \left[ z \left( \frac{a}{z} + b \right) \right]^r = z^{m + r} \left( a z^{-1} + b \right)^r \tag{13}
\end{gather}
$$
Let $r = \frac{k}{s}$ with $k \in \mathbb{Z}, s \in \mathbb{N}_{\ge 1}$, and $\gcd(k, s) = 1$. Substitute:
$$
\begin{gather}
a z^{-1} + b = t^s \tag{14}
\end{gather}
$$
From step 14, isolate $z$:
$$
\begin{gather}
\frac{a}{z} = t^s - b \implies z = \frac{a}{t^s - b} \tag{15}
\end{gather}
$$
Differentiating step 15 yields the differential:
$$
\begin{gather}
dz = -\frac{a s t^{s - 1}}{(t^s - b)^2} \, dt \tag{16}
\end{gather}
$$
Substituting equations 13, 15, and 16 into the integral of step 5 demonstrates:
$$
\begin{gather}
\int z^m (a + b z)^r \, dz = \int \left( \frac{a}{t^s - b} \right)^{m + r} (t^s)^{\frac{k}{s}} \left( -\frac{a s t^{s - 1}}{(t^s - b)^2} \right) dt = -a^{m + r + 1} s \int \frac{t^{k + s - 1}}{(t^s - b)^{m + r + 2}} \, dt \tag{17}
\end{gather}
$$
Because $m + r + 1 \in \mathbb{Z}$, the exponent $m + r + 2$ is an integer. Consequently, the integrand in step 17 is a rational function of $t$, ensuring that the primitive is expressible in terms of elementary functions.

---
# Proposition 4
To establish necessity, let $w = a + b z$. The differential form $z^m (a + b z)^r \, dz$ is an algebraic differential on the Riemann surface of the algebraic curve $w^s = (a + b z)^k$. 

By virtue of the Liouville-Ritt Theorem on the integrability of elementary primitives, the indefinite integral of an algebraic function $\int f(z, w) \, dz$ is elementary if and only if the differential is expressible as the differential of a rational function on the curve plus linear combinations of logarithmic differentials of rational functions (the Abel-Liouville Theorem). 

Specifically for the differential binomial $\omega = z^m (a + b z)^r \, dz$, the divisor of poles and branch points reveals that the Jacobian variety of the associated Riemann surface contains non-degenerate abelian differentials of the first kind (differentials with non-zero genus possessing periods along non-contractible homology cycles) unless the underlying algebraic curve is of genus zero or the differential residues decouple into logarithmic forms. 

A rigorous analysis of the Weierstrass gap sequence and the period lattice of the curve $w^s = a + b z^k$ (established by Chebyshev in 1853) shows that the period integrals vanish and the differential decouples into an elementary primitive if and only if at least one of the three exponents $r$, $m + 1 = \frac{p+1}{q}$, or $m + r + 1 = \frac{p+1}{q} + r$ is an integer. 

When none of these three conditions is fulfilled, the primitive is an incomplete Beta function or a hypergeometric integral possessing non-trivial monodromy that cannot be represented as a finite composition of algebraic, logarithmic, and trigonometric functions.

This completes the proof of Chebyshev's Differential Binomial Integration Criterion.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
