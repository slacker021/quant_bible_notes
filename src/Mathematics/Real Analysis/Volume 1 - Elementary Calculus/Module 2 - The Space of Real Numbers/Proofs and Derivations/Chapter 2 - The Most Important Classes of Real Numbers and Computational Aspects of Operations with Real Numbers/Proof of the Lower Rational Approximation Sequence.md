---
dg-publish: true
---
Let $q \in \mathbb{N}$ with $q > 1$, let $x \in \mathbb{R}_{>0}$, and let $p \in \mathbb{Z}$ be the unique order of $x$ in base $q$, satisfying $q^p \le x < q^{p+1}$.

# Inductive Construction of the Digit Sequence
It is established by mathematical induction that for each $n \in \mathbb{N}_0$, there exists a unique sequence of digits $\{\alpha_{p-j}\}_{j=0}^n \subset \{0, 1, \dots, q - 1\}$ (with $\alpha_p \in \{1, \dots, q - 1\}$) such that the rational sum:
$$
r_n := \sum_{j=0}^n \alpha_{p-j} q^{p-j} \tag{1}
$$
satisfies the double inequality:
$$
r_n \le x < r_n + \frac{1}{q^{n-p}} \tag{2}
$$

### Base Step ($n = 0$)
Applying the Principle of Archimedes to $x$ with step size $h = q^p > 0$ yields a unique integer $\alpha_p \in \mathbb{Z}$ satisfying:
$$
\alpha_p q^p \le x < (\alpha_p + 1)q^p = \alpha_p q^p + q^p \tag{3}
$$
Because $q^p \le x < q^{p+1}$, dividing step 3 by $q^p$ establishes that:
$$
1 \le \alpha_p \le q - 1 \implies \alpha_p \in \{1, 2, \dots, q - 1\} \tag{4}
$$
Defining $r_0 := \alpha_p q^p$, step 3 becomes:
$$
r_0 \le x < r_0 + \frac{1}{q^{-p}} \tag{5}
$$
This verifies step 2 for $n = 0$.

### Inductive Step
Assume as the inductive hypothesis that for a fixed $k \in \mathbb{N}_0$, the digits $\alpha_p, \dots, \alpha_{p-k} \in \{0, \dots, q - 1\}$ have been uniquely determined such that:
$$
r_k \le x < r_k + q^{-(k-p)} \tag{6}
$$
Consider the remainder $\rho_k := x - r_k$. By step 6, $\rho_k \in [0, q^{p-k})$. 

Applying the Principle of Archimedes to $\rho_k$ with step size $h = q^{p-k-1} > 0$ yields a unique integer $\alpha_{p-k-1} \in \mathbb{Z}$ satisfying:
$$
\alpha_{p-k-1} q^{p-k-1} \le x - r_k < (\alpha_{p-k-1} + 1)q^{p-k-1} \tag{7}
$$
Because $0 \le x - r_k < q^{p-k} = q \cdot q^{p-k-1}$, dividing step 7 by $q^{p-k-1}$ demonstrates that:
$$
0 \le \alpha_{p-k-1} < q \implies \alpha_{p-k-1} \in \{0, 1, \dots, q - 1\} \tag{8}
$$
Adding $r_k$ across step 7 and defining $r_{k+1} := r_k + \alpha_{p-k-1} q^{p-(k+1)} = \sum_{j=0}^{k+1} \alpha_{p-j} q^{p-j}$ gives:
$$
r_{k+1} \le x < r_{k+1} + q^{-(k+1-p)} \tag{9}
$$
This establishes the claim for $k + 1$. By the Principle of Mathematical Induction, the sequence $\{r_n\}_{n=0}^\infty$ exists uniquely and satisfies step 2 for all $n \in \mathbb{N}_0$.

# Monotonicity of the Approximation Sequence
For any $n \in \mathbb{N}_0$, the difference between consecutive approximations evaluates to:
$$
r_{n+1} - r_n = \alpha_{p-(n+1)} q^{p-(n+1)} \tag{10}
$$
Because $\alpha_{p-(n+1)} \ge 0$ and $q > 0$, step 10 confirms that $r_{n+1} \ge r_n$ for all $n \in \mathbb{N}_0$. Consequently, $\{r_n\}_{n=0}^\infty$ is a monotonically non-decreasing sequence of lower rational approximations.

$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
