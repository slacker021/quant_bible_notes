---
dg-publish: true
---
Let $\mathbb{Q}(x)$ denote the field of rational functions over the rational numbers, defined as the field of fractions of the polynomial ring $\mathbb{Q}[x]$. Every non-zero element $R \in \mathbb{Q}(x) \setminus \{0\}$ can be expressed as:
$$
R(x) = \frac{P(x)}{Q(x)} = \frac{a_m x^m + a_{m-1} x^{m-1} + \dots + a_0}{b_n x^n + b_{n-1} x^{n-1} + \dots + b_0} \tag{1}
$$
where $P, Q \in \mathbb{Q}[x]$ are non-zero polynomials with leading coefficients $a_m \ne 0$ and $b_n \ne 0$.

--------------------------------------------------------------------------------
# Proposition 1
### Definition and Consistency of the Positivity Cone
Define the positivity cone $\mathcal{P} \subset \mathbb{Q}(x)$ by declaring $R(x) > 0$ if and only if the product of the leading coefficients of its numerator and denominator is strictly positive in $\mathbb{Q}$:
$$
R(x) \in \mathcal{P} \iff a_m \cdot b_n > 0 \tag{2}
$$
To verify that this definition is independent of the representative fraction, let $P_1/Q_1 = P_2/Q_2$, meaning $P_1 Q_2 = P_2 Q_1$. Let the leading coefficients be $a^{(1)}, b^{(1)}, a^{(2)}, b^{(2)}$. The equality of polynomials requires $a^{(1)} b^{(2)} = a^{(2)} b^{(1)}$. Multiplying by $b^{(1)} b^{(2)}$ demonstrates that $(a^{(1)} b^{(1)})(b^{(2)})^2 = (a^{(2)} b^{(2)})(b^{(1)})^2$. Because non-zero rational squares are strictly positive, $a^{(1)} b^{(1)}$ and $a^{(2)} b^{(2)}$ share the identical sign, proving consistency.

### Verification of Ordered Field Axioms
1. **Trichotomy:** For any $R(x) \in \mathbb{Q}(x)$, either $P(x) = 0$ (so $R(x) = 0$), $a_m b_n > 0$ (so $R(x) \in \mathcal{P}$), or $a_m b_n < 0$ (so $-R(x) \in \mathcal{P}$). Precisely one condition holds.
2. **Closure under Addition:** Let $R_1 = P_1/Q_1 \in \mathcal{P}$ and $R_2 = P_2/Q_2 \in \mathcal{P}$. Normalizing denominators so that their leading coefficients are positive ($b^{(1)} > 0, b^{(2)} > 0$), it follows from step 2 that $a^{(1)} > 0$ and $a^{(2)} > 0$. The sum evaluates to:
$$
R_1 + R_2 = \frac{P_1 Q_2 + P_2 Q_1}{Q_1 Q_2} \tag{3}
$$
The denominator polynomial $Q_1 Q_2$ has degree $n_1 + n_2$ with leading coefficient $b^{(1)} b^{(2)} > 0$. Let $d_1 = \deg(P_1 Q_2) = m_1 + n_2$ and $d_2 = \deg(P_2 Q_1) = m_2 + n_1$:
* If $d_1 > d_2$, the leading coefficient of the numerator is $a^{(1)} b^{(2)} > 0$.
* If $d_2 > d_1$, the leading coefficient of the numerator is $a^{(2)} b^{(1)} > 0$.
* If $d_1 = d_2$, the leading coefficient is $a^{(1)} b^{(2)} + a^{(2)} b^{(1)} > 0$.

In all cases, the leading coefficient product is strictly positive, confirming that $R_1 + R_2 \in \mathcal{P}$.
3. **Closure under Multiplication:** For $R_1, R_2 \in \mathcal{P}$, the product:
$$
R_1 \cdot R_2 = \frac{P_1 P_2}{Q_1 Q_2} \tag{4}
$$
has leading coefficient product $(a^{(1)} a^{(2)})(b^{(1)} b^{(2)}) = (a^{(1)} b^{(1)})(a^{(2)} b^{(2)}) > 0$. Hence, $R_1 \cdot R_2 \in \mathcal{P}$.

Consequently, $(\mathbb{Q}(x), +, \cdot, \le)$ is a linearly ordered field under the relation $R_1 \le R_2 \iff R_2 - R_1 \in \mathcal{P} \cup \{0\}$.

### Failure of the Archimedean Property
Consider the multiplicative unit $1 = \frac{1}{1} \in \mathcal{P}$ and the polynomial indeterminate $x = \frac{x}{1} \in \mathcal{P}$. For any arbitrary natural number $k \in \mathbb{N}$, evaluate the difference:
$$
x - k \cdot 1 = \frac{x - k}{1} \tag{5}
$$
The numerator polynomial $P(x) = x - k$ has degree $1$ with leading coefficient $a_1 = 1 > 0$, while the denominator $Q(x) = 1$ has degree $0$ with leading coefficient $b_0 = 1 > 0$. Because $a_1 \cdot b_0 = 1 \cdot 1 = 1 > 0$:
$$
x - k \cdot 1 \in \mathcal{P} \iff k \cdot 1 < x \quad \forall k \in \mathbb{N} \tag{6}
$$
Because no integer multiple of the identity element $1$ can ever exceed $x$, the set of natural multiples $\{k \cdot 1 \mid k \in \mathbb{N}\}$ is bounded above by $x$. 

Equivalently, taking reciprocals yields:
$$
0 < \frac{1}{x} < \frac{1}{k} \quad \forall k \in \mathbb{N} \tag{7}
$$
proving that $\frac{1}{x}$ is a strictly positive infinitesimal element. Thus, $\mathbb{Q}(x)$ is a non-Archimedean ordered field.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
