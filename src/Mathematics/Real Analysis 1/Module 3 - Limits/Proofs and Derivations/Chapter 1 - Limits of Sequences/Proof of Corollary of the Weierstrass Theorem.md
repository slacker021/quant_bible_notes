---
dg-publish: true
---
# Corollary 1
Consider the sequence $y_n := \sqrt[n]{n} = n^{1/n}$ for $n \in \mathbb{N}$. Because $n \ge 1$ for all $n \in \mathbb{N}$, it follows that $y_n \ge 1$, ensuring that $\{y_n\}$ is bounded below by $1$.

It is established in the [[Derivation of Euler's Number e|derivation of Euler's number]] that the sequence $\left\{\left(1 + \frac{1}{n}\right)^n\right\}$ is strictly increasing and bounded above by $3$:
$$
\begin{gather}
\left(1 + \frac{1}{n}\right)^n < 3 \quad \forall n \in \mathbb{N} \tag{1}
\end{gather}
$$
Consequently, for every natural number $n \ge 3$, step 1 implies: 
$$
\begin{gather}
n \ge 3 > \left(1 + \frac{1}{n}\right)^n = \left(\frac{n + 1}{n}\right)^n = \frac{(n + 1)^n}{n^n} \tag{2}
\end{gather}
$$
Multiplying both sides of step 2 by $n^n > 0$ and taking the $n(n + 1)$-th root of both positive sides yields: 
$$
\begin{gather}
n^{n+1} > (n + 1)^n \iff n^{\frac{1}{n}} > (n + 1)^{\frac{1}{n+1}} \iff y_n > y_{n+1} \quad \forall n \ge 3 \tag{3}
\end{gather}
$$
Thus, for all $n \ge 3$, the sequence $\{y_n\}$ is strictly decreasing and bounded below by $1$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], $\{y_n\}$ converges to a finite real limit $L \ge 1$.

To evaluate $L$, consider the even-indexed subsequence $y_{2n} = \sqrt[2n]{2n}$. Because $\{y_n\}$ converges to $L$, every subsequence of $\{y_n\}$ converges to $L$. Rewriting $y_{2n}$ algebraically gives: 
$$
\begin{gather}
y_{2n} = (2n)^{\frac{1}{2n}} = 2^{\frac{1}{2n}} \cdot n^{\frac{1}{2n}} = \sqrt{\sqrt[n]{2}} \cdot \sqrt{y_n} \tag{4}
\end{gather}
$$
Passing to the limit as $n \to \infty$ on both sides of step 4 and applying the [[Proof of Arithmetic Operations Involving Limits|arithmetic properties of limits]] together with the limit $\lim_{n \to \infty} \sqrt[n]{2} = 1$ (established in Corollary 2) yields: 
$$
\begin{gather}
L = \sqrt{1} \cdot \sqrt{L} = \sqrt{L} \tag{5}
\end{gather}
$$
Squaring both sides of step 5 produces $L^2 = L \iff L(L - 1) = 0$. Because $L \ge 1$, the root $L = 0$ is rejected, leaving $L = 1$. Therefore, $\lim_{n \to \infty} \sqrt[n]{n} = 1$.

---
# Corollary 2
Let $a > 0$ be an arbitrary positive real constant, and consider the sequence $x_n := \sqrt[n]{a} = a^{1/n}$ for $n \in \mathbb{N}$. By trichotomy on $a > 0$, three exhaustive cases arise:

**Case 1 ($a > 1$):** Because $a > 1$, $x_n = a^{1/n} > 1$ for all $n \in \mathbb{N}$. Furthermore, because rational powers with base $a > 1$ are strictly increasing in the exponent and $\frac{1}{n} > \frac{1}{n+1}$, it follows that: 
$$
\begin{gather}
x_n = a^{\frac{1}{n}} > a^{\frac{1}{n+1}} = x_{n+1} \quad \forall n \in \mathbb{N} \tag{6}
\end{gather}
$$
Thus, $\{x_n\}$ is strictly decreasing and bounded below by $1$. By the [[Proof of Weierstrass Theorem on Monotonic Sequences|Weierstrass Theorem on Monotonic Sequences]], $\{x_n\}$ converges to a finite real limit $L \ge 1$. Extracting the even-indexed subsequence $x_{2n} = \sqrt[2n]{a}$, which also converges to $L$, yields: 
$$
\begin{gather}
x_{2n} = \left(a^{\frac{1}{n}}\right)^{\frac{1}{2}} = \sqrt{x_n} \tag{7}
\end{gather}
$$
Taking the limit as $n \to \infty$ on both sides of step 7 gives $L = \sqrt{L} \implies L(L - 1) = 0$. Because $L \ge 1$, it follows that $L = 1$. Thus, $\lim_{n \to \infty} \sqrt[n]{a} = 1$ for all $a > 1$.

**Case 2 ($a = 1$):** Here $x_n = \sqrt[n]{1} = 1$ for all $n \in \mathbb{N}$. Because $\{x_n\}$ is a constant sequence, $\lim_{n \to \infty} \sqrt[n]{1} = 1$.

**Case 3 ($0 < a < 1$):** Define the reciprocal constant $b := \frac{1}{a} > 1$. Applying Case 1 to $b > 1$ establishes that $\lim_{n \to \infty} \sqrt[n]{b} = 1 \neq 0$. By the [[Proof of Arithmetic Operations Involving Limits|quotient rule for limits]]: 
$$
\begin{gather}
\lim_{n \to \infty} \sqrt[n]{a} = \lim_{n \to \infty} \frac{1}{\sqrt[n]{b}} = \frac{1}{\lim_{n \to \infty} \sqrt[n]{b}} = \frac{1}{1} = 1 \tag{8}
\end{gather}
$$
Combining all three cases proves that $\lim_{n \to \infty} \sqrt[n]{a} = 1$ for every constant $a > 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
