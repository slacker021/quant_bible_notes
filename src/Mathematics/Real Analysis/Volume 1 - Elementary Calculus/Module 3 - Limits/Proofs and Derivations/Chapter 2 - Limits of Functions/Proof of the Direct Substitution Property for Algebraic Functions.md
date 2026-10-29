---
dg-publish: true
---
Let $a \in \mathbb{R}$ be an arbitrary real number.

---
# Theorem 1
Let $P(x) = \sum_{k=0}^n c_k x^k$ be a polynomial of degree $n \in \mathbb{N} \cup \{0\}$ with real coefficients $c_k \in \mathbb{R}$.

First, consider the constant function $f_0(x) = c_0$. For any $\varepsilon > 0$ and any $\delta > 0$, $\vert{}f_0(x) - c_0\vert{} = \vert{}c_0 - c_0\vert{} = 0 < \varepsilon$ for all $x \in \mathbb{R}$, which establishes that:
$$\begin{gather} \lim_{x \to a} c_0 = c_0 \tag{1} \end{gather}$$
Second, consider the identity function $f_1(x) = x$. For any $\varepsilon > 0$, setting $\delta := \varepsilon > 0$ guarantees that:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta \implies \vert{}f_1(x) - a\vert{} = \vert{}x - a\vert{} < \varepsilon \implies \lim_{x \to a} x = a \tag{2} \end{gather}$$
By applying the product rule for functional limits inductively to step 2 for any natural power $k \in \mathbb{N}$:
$$\begin{gather} \lim_{x \to a} x^k = \lim_{x \to a} (x \cdot x^{k-1}) = \left(\lim_{x \to a} x\right) \left(\lim_{x \to a} x^{k-1}\right) = a \cdot a^{k-1} = a^k \tag{3} \end{gather}$$
Applying the scalar multiple rule and the sum rule for limits across the finite summation yields:
$$\begin{gather} \lim_{x \to a} P(x) = \lim_{x \to a} \sum_{k=0}^n c_k x^k = \sum_{k=0}^n c_k \lim_{x \to a} x^k = \sum_{k=0}^n c_k a^k = P(a) \tag{4} \end{gather}$$
Thus, the limit of any polynomial at $a$ equals its direct evaluation $P(a)$.

---
# Theorem 2
Let $R(x) = \frac{P(x)}{Q(x)}$ be a rational function, where $P(x)$ and $Q(x)$ are polynomials, and assume that $Q(a) \neq 0$.

By Theorem 1, the limits of the numerator and denominator evaluate to:
$$\begin{gather} \lim_{x \to a} P(x) = P(a) \quad \text{and} \quad \lim_{x \to a} Q(x) = Q(a) \neq 0 \tag{5} \end{gather}$$
By the quotient rule for functional limits, the non-zero limit of the denominator guarantees that:
$$\begin{gather} \lim_{x \to a} R(x) = \lim_{x \to a} \frac{P(x)}{Q(x)} = \frac{\lim_{x \to a} P(x)}{\lim_{x \to a} Q(x)} = \frac{P(a)}{Q(a)} = R(a) \tag{6} \end{gather}$$

---

# Theorem 3
Let $n \in \mathbb{N}$, and let $f(x) = \sqrt[n]{x} = x^{1/n}$ on the domain $E = (0, +\infty)$ (or on $\mathbb{R}$ if $n$ is odd). Let $a > 0$.

For any $x > 0$ and $a > 0$, the algebraic identity for the difference of $n$-th powers yields:
$$\begin{gather} x - a = (\sqrt[n]{x} - \sqrt[n]{a}) \sum_{k=0}^{n-1} (\sqrt[n]{x})^{n-1-k} (\sqrt[n]{a})^k \tag{7} \end{gather}$$
Because $x > 0$ and $a > 0$, every term in the summation of step 7 is strictly positive. Retaining only the final term corresponding to $k = n - 1$ establishes the inequality:
$$\begin{gather} \sum_{k=0}^{n-1} (\sqrt[n]{x})^{n-1-k} (\sqrt[n]{a})^k > (\sqrt[n]{a})^{n-1} = a^{\frac{n-1}{n}} > 0 \tag{8} \end{gather}$$
Dividing step 7 by the positive sum and taking the absolute value yields:
$$\begin{gather} \vert{}\sqrt[n]{x} - \sqrt[n]{a}\vert{} = \frac{\vert{}x - a\vert{}}{\sum_{k=0}^{n-1} (\sqrt[n]{x})^{n-1-k} (\sqrt[n]{a})^k} < \frac{\vert{}x - a\vert{}}{a^{\frac{n-1}{n}}} \tag{9} \end{gather}$$
Let $\varepsilon > 0$ be given. Define the positive distance:
$$\begin{gather} \delta := \min\left(\frac{a}{2}, \ \varepsilon \cdot a^{\frac{n-1}{n}}\right) > 0 \tag{10} \end{gather}$$
For all $x$ satisfying $0 < \vert{}x - a\vert{} < \delta$, it follows from step 9 and step 10 that:
$$\begin{gather} \vert{}\sqrt[n]{x} - \sqrt[n]{a}\vert{} < \frac{\vert{}x - a\vert{}}{a^{\frac{n-1}{n}}} < \frac{\varepsilon \cdot a^{\frac{n-1}{n}}}{a^{\frac{n-1}{n}}} = \varepsilon \tag{11} \end{gather}$$
Thus, $\lim_{x \to a} \sqrt[n]{x} = \sqrt[n]{a}$.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$
