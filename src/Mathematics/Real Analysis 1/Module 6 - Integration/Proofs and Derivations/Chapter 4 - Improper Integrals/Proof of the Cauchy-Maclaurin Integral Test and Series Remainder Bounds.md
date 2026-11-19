---
dg-publish: true
---
Let $f: [1, \infty) \to [0, \infty)$ be a continuous, monotonically non-increasing function satisfying:
$$
\begin{gather}
1 \le x_1 \le x_2 \implies f(x_1) \ge f(x_2) \ge 0 \tag{1}
\end{gather}
$$
Because $f$ is continuous on $[1, \infty)$, $f \in \mathcal{R}[1, B]$ for every $B \ge 1$.

---
# Part 1 

### Step 1
For each integer $k \in \mathbb{N}$, consider the unit interval $[k, k + 1]$. Because $f$ is monotonically non-increasing by step 1:
$$
\begin{gather}
f(k + 1) \le f(x) \le f(k) \quad \text{for all } x \in [k, k + 1] \tag{2}
\end{gather}
$$

### Step 2
Integrating the compound inequality of step 2 across the interval $[k, k + 1]$, the length of the domain of integration is $(k + 1) - k = 1$. By the order-preserving property of the Riemann integral:
$$
\begin{gather}
\int_k^{k + 1} f(k + 1)\,dx \le \int_k^{k + 1} f(x)\,dx \le \int_k^{k + 1} f(k)\,dx \tag{3}
\end{gather}
$$

Because $f(k + 1)$ and $f(k)$ are constants with respect to $x$:
$$
\begin{gather}
f(k + 1) \le \int_k^{k + 1} f(x)\,dx \le f(k) \tag{4}
\end{gather}
$$

### Step 3
Let $n \ge 2$ be an integer. Summing the chain of inequalities in step 4 across $k = 1, 2, \dots, n - 1$:
$$
\begin{gather}
\sum_{k=1}^{n-1} f(k + 1) \le \sum_{k=1}^{n-1} \int_k^{k + 1} f(x)\,dx \le \sum_{k=1}^{n-1} f(k) \tag{5}
\end{gather}
$$

Define the $n$-th partial sum of the infinite series:
$$
\begin{gather}
S_n := \sum_{k=1}^n f(k) \tag{6}
\end{gather}
$$
and the partial accumulation integral:
$$
\begin{gather}
I_n := \int_1^n f(x)\,dx \tag{7}
\end{gather}
$$

By index re-indexing, the leftmost summation in step 5 evaluates to:
$$
\begin{gather}
\sum_{k=1}^{n-1} f(k + 1) = \sum_{j=2}^n f(j) = S_n - f(1) \tag{8}
\end{gather}
$$

By the interval additivity of the Riemann integral, the center summation in step 5 evaluates to:
$$
\begin{gather}
\sum_{k=1}^{n-1} \int_k^{k + 1} f(x)\,dx = \int_1^n f(x)\,dx = I_n \tag{9}
\end{gather}
$$

The rightmost summation in step 5 evaluates to:
$$
\begin{gather}
\sum_{k=1}^{n-1} f(k) = S_{n-1} = S_n - f(n) \tag{10}
\end{gather}
$$

Substituting step 8, step 9, and step 10 into step 5 yields:
$$
\begin{gather}
S_n - f(1) \le I_n \le S_n - f(n) \tag{11}
\end{gather}
$$

Because $f(n) \ge 0$, step 11 implies $I_n \le S_n$. Furthermore, adding $f(1)$ to the left inequality of step 11 yields $S_n \le I_n + f(1)$. Combining these produces the fundamental sandwich bound:
$$
\begin{gather}
I_n \le S_n \le I_n + f(1) \quad \text{for all } n \ge 2 \tag{12}
\end{gather}
$$

### Step 4
Because $f(k) \ge 0$ for all $k \in \mathbb{N}$, the sequence of partial sums $(S_n)_{n=1}^\infty$ is monotonically non-decreasing:
$$
\begin{gather}
S_{n+1} - S_n = f(n + 1) \ge 0 \implies S_{n+1} \ge S_n \tag{13}
\end{gather}
$$

Similarly, because $f(x) \ge 0$ for all $x \ge 1$, the sequence of partial integrals $(I_n)_{n=1}^\infty$ is monotonically non-decreasing:
$$
\begin{gather}
I_{n+1} - I_n = \int_n^{n+1} f(x)\,dx \ge 0 \implies I_{n+1} \ge I_n \tag{14}
\end{gather}
$$

Two implications are now established:
1. Suppose the improper integral converges to a finite value $I := \int_1^\infty f(x)\,dx = \lim_{B \to \infty} \int_1^B f(x)\,dx$. By the Monotonicity Criterion for Non-Negative Improper Integrals:
$$
\begin{gather}
I_n = \int_1^n f(x)\,dx \le I \quad \text{for all } n \ge 1 \tag{15}
\end{gather}
$$
Applying step 15 to the right-hand inequality of step 12:
$$
\begin{gather}
S_n \le I_n + f(1) \le I + f(1) \quad \text{for all } n \ge 2 \tag{16}
\end{gather}
$$
Because the sequence $(S_n)$ is non-decreasing by step 13 and bounded from above by $I + f(1)$ by step 16, the Monotone Convergence Theorem for real sequences implies that $(S_n)$ converges to a finite limit:
$$
\begin{gather}
S := \lim_{n \to \infty} S_n = \sum_{n=1}^\infty f(n) < \infty \tag{17}
\end{gather}
$$

2. Conversely, suppose the infinite series converges to a finite sum $S := \sum_{n=1}^\infty f(n) < \infty$. By the non-negativity of terms:
$$
\begin{gather}
S_n \le S \quad \text{for all } n \ge 1 \tag{18}
\end{gather}
$$
Applying step 18 to the left-hand inequality of step 12:
$$
\begin{gather}
I_n = \int_1^n f(x)\,dx \le S_n \le S \quad \text{for all } n \ge 2 \tag{19}
\end{gather}
$$
For an arbitrary parameter $B \ge 1$, choose an integer $n \in \mathbb{N}$ such that $n \ge B$. Because $f(x) \ge 0$, interval additivity and positivity imply:
$$
\begin{gather}
\int_1^B f(x)\,dx \le \int_1^n f(x)\,dx = I_n \le S \tag{20}
\end{gather}
$$
Thus, the accumulation function $F(B) = \int_1^B f(x)\,dx$ is bounded from above on $[1, \infty)$ by the finite constant $S$. By the Monotonicity Criterion for Non-Negative Improper Integrals, the improper integral $\int_1^\infty f(x)\,dx$ converges to a finite limit.

3. By contraposition, divergence of the improper integral to $+\infty$ forces divergence of the series to $+\infty$, and divergence of the series forces divergence of the improper integral. This completes the proof of Part 1.

---
# Part 2
Assume that the series converges to the sum $S := \sum_{n=1}^\infty f(n) < \infty$. Let $N \ge 1$ be a fixed integer. The truncation remainder is defined by:
$$
\begin{gather}
R_N := S - S_N = \sum_{k=N+1}^\infty f(k) \tag{21}
\end{gather}
$$

### Step 1
Let $M$ be an integer strictly greater than $N + 1$. Summing the subinterval inequality of step 4 across $k = N + 1, N + 2, \dots, M$:
$$
\begin{gather}
\sum_{k=N+1}^M f(k + 1) \le \sum_{k=N+1}^M \int_k^{k + 1} f(x)\,dx \le \sum_{k=N+1}^M f(k) \tag{22}
\end{gather}
$$

By interval additivity, the center summation in step 22 evaluates to:
$$
\begin{gather}
\sum_{k=N+1}^M \int_k^{k + 1} f(x)\,dx = \int_{N+1}^{M+1} f(x)\,dx \tag{23}
\end{gather}
$$

Substituting step 23 into step 22:
$$
\begin{gather}
\sum_{j=N+2}^{M+1} f(j) \le \int_{N+1}^{M+1} f(x)\,dx \le \sum_{k=N+1}^M f(k) \tag{24}
\end{gather}
$$

From the right-hand inequality of step 24, taking the limit as $M \to \infty$:
$$
\begin{gather}
\int_{N+1}^\infty f(x)\,dx = \lim_{M \to \infty} \int_{N+1}^{M+1} f(x)\,dx \le \lim_{M \to \infty} \sum_{k=N+1}^M f(k) = R_N \tag{25}
\end{gather}
$$
which establishes the lower bound on $R_N$.

To establish the upper bound, shift indices in the left-hand inequality of step 4 by setting $k \mapsto k - 1$:
$$
\begin{gather}
\int_k^{k + 1} f(x)\,dx \le f(k) \implies f(k) \le \int_{k-1}^k f(x)\,dx \tag{26}
\end{gather}
$$

Summing step 26 from $k = N + 1$ to $M$:
$$
\begin{gather}
\sum_{k=N+1}^M f(k) \le \sum_{k=N+1}^M \int_{k-1}^k f(x)\,dx = \int_N^M f(x)\,dx \tag{27}
\end{gather}
$$

Taking the limit as $M \to \infty$ in step 27:
$$
\begin{gather}
R_N = \lim_{M \to \infty} \sum_{k=N+1}^M f(k) \le \lim_{M \to \infty} \int_N^M f(x)\,dx = \int_N^\infty f(x)\,dx \tag{28}
\end{gather}
$$

Combining step 25 and step 28 yields the sharp remainder inequalities:
$$
\begin{gather}
\int_{N+1}^\infty f(x)\,dx \le R_N \le \int_N^\infty f(x)\,dx \tag{29}
\end{gather}
$$
This completes the proof of Part 2.
### Step 2
Consider the harmonic function $f(x) := \frac{1}{x}$, which is strictly decreasing and positive on $[1, \infty)$. For each integer $n \ge 1$, define the sequence of difference terms:
$$
\begin{gather}
d_n := \sum_{k=1}^n \frac{1}{k} - \ln n \tag{30}
\end{gather}
$$

### Step 3
Compute the successive difference $d_n - d_{n+1}$:
$$
\begin{gather}
d_n - d_{n+1} = \left( \sum_{k=1}^n \frac{1}{k} - \ln n \right) - \left( \sum_{k=1}^{n+1} \frac{1}{k} - \ln(n + 1) \right) \tag{31}
\end{gather}
$$

Simplifying step 31:
$$
\begin{gather}
d_n - d_{n+1} = \ln(n + 1) - \ln n - \frac{1}{n + 1} = \int_n^{n+1} \frac{dx}{x} - \frac{1}{n + 1} \tag{32}
\end{gather}
$$

Because $x \mapsto \frac{1}{x}$ is strictly decreasing, for all $x \in (n, n + 1)$:
$$
\begin{gather}
\frac{1}{x} > \frac{1}{n + 1} \tag{33}
\end{gather}
$$

Integrating the strict inequality of step 33 across $[n, n + 1]$:
$$
\begin{gather}
\int_n^{n+1} \frac{dx}{x} > \int_n^{n+1} \frac{1}{n + 1}\,dx = \frac{1}{n + 1} \tag{34}
\end{gather}
$$

Substituting step 34 into step 32 yields:
$$
\begin{gather}
d_n - d_{n+1} > 0 \iff d_{n+1} < d_n \tag{35}
\end{gather}
$$

Thus, the sequence $(d_n)_{n=1}^\infty$ is strictly monotonically decreasing.
### Step 4
To bound $d_n$ from below, write the logarithm as the integral of $1/x$ and decompose across unit subintervals:
$$
\begin{gather}
\ln n = \int_1^n \frac{dx}{x} = \sum_{k=1}^{n-1} \int_k^{k+1} \frac{dx}{x} \tag{36}
\end{gather}
$$

On each subinterval $[k, k + 1]$, the strict inequality $\frac{1}{x} < \frac{1}{k}$ holds for all $x \in (k, k + 1)$. Integrating yields:
$$
\begin{gather}
\int_k^{k+1} \frac{dx}{x} < \int_k^{k+1} \frac{1}{k}\,dx = \frac{1}{k} \tag{37}
\end{gather}
$$

Summing step 37 across $k = 1, 2, \dots, n - 1$:
$$
\begin{gather}
\ln n < \sum_{k=1}^{n-1} \frac{1}{k} = \sum_{k=1}^n \frac{1}{k} - \frac{1}{n} \tag{38}
\end{gather}
$$

Rearranging step 38 by subtracting $\ln n$ from the right-hand side and adding $1/n$:
$$
\begin{gather}
d_n = \sum_{k=1}^n \frac{1}{k} - \ln n > \frac{1}{n} > 0 \tag{39}
\end{gather}
$$

Thus, $d_n > 0$ for all $n \ge 1$. Furthermore, evaluating the initial term:
$$
\begin{gather}
d_1 = \sum_{k=1}^1 \frac{1}{k} - \ln 1 = 1 - 0 = 1 \tag{40}
\end{gather}
$$

Because $(d_n)$ is strictly decreasing by step 35, $d_n \le d_1 = 1$ for all $n \ge 1$. Combining with step 39 gives:
$$
\begin{gather}
0 < d_n \le 1 \quad \text{for all } n \ge 1 \tag{41}
\end{gather}
$$

The sequence $(d_n)_{n=1}^\infty$ is monotonically decreasing and bounded from below by $0$. By the Monotone Convergence Theorem for real sequences, the limit exists in $\mathbb{R}$:
$$
\begin{gather}
\gamma := \lim_{n \to \infty} \left( \sum_{k=1}^n \frac{1}{k} - \ln n \right) \in (0, 1] \tag{42}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
