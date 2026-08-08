---
dg-publish: true
---
Let $x \in \mathbb{R}$ satisfy $x \ge -1$, and let $n \in \mathbb{N}$.

# Base Step
Let $n = 1$. Evaluating both sides of the inequality:
$$
(1 + x)^1 = 1 + x \quad \wedge \quad 1 + (1)x = 1 + x \tag{1}
$$
Because both sides are identical, $(1 + x)^1 \ge 1 + (1)x$ holds with equality, establishing the base step.

# Inductive Step
Assume as the inductive hypothesis that the inequality holds for a fixed natural number $k \in \mathbb{N}$:
$$
(1 + x)^k \ge 1 + kx \tag{2}
$$
Because $x \ge -1$, the additive compatibility axiom dictates that $1 + x \ge 0$. Multiplying both sides of step 2 by the non-negative scalar $(1 + x)$ preserves the inequality:
$$
(1 + x)^{k+1} = (1 + x)^k (1 + x) \ge (1 + kx)(1 + x) \tag{3}
$$
Expanding the right-hand side via the distributive law yields: 
$$
(1 + kx)(1 + x) = 1 + x + kx + kx^2 = 1 + (k + 1)x + kx^2 \tag{4}
$$
Because $k \in \mathbb{N}$ satisfies $k \ge 1$ and every square in an ordered field satisfies $x^2 \ge 0$, the product term is non-negative: 
$$
kx^2 \ge 0 \implies 1 + (k + 1)x + kx^2 \ge 1 + (k + 1)x \tag{5}
$$
Applying transitivity across step 3, step 4, and step 5 establishes that: 
$$
(1 + x)^{k+1} \ge 1 + (k + 1)x \tag{6}
$$
By the Principle of Mathematical Induction, $(1 + x)^n \ge 1 + nx$ holds for all $n \in \mathbb{N}$ and all $x \ge -1$.

# Strict Inequality and Equality Characterization
If $x = 0$, then $(1 + 0)^n = 1 = 1 + n(0)$ for all $n \in \mathbb{N}$. If $n = 1$, equality holds identically by step 1.

Now assume that $n \ge 2$, $x \ne 0$, and $x > -1$. For $n = 2$: 
$$
(1 + x)^2 = 1 + 2x + x^2 \tag{7}
$$
Because $x \ne 0$, the square is strictly positive ($x^2 > 0$). Consequently: 
$$
1 + 2x + x^2 > 1 + 2x \implies (1 + x)^2 > 1 + 2x \tag{8}
$$
Proceeding inductively for $k \ge 2$, assuming $(1 + x)^k > 1 + kx$, multiplying by $(1 + x) > 0$ produces
$$
(1 + x)^{k+1} > (1 + kx)(1 + x) = 1 + (k + 1)x + kx^2 \ge 1 + (k + 1)x \tag{9}
$$
Therefore, for all $n > 1$ and $x \ne 0$ with $x > -1$, the strict inequality $(1 + x)^n > 1 + nx$ holds. Equality holds if and only if $n = 1$ or $x = 0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
