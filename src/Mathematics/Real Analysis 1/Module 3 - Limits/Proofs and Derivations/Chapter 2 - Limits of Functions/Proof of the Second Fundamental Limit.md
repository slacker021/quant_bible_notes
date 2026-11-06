---
dg-publish: true
---
Let $e \in \mathbb{R}$ denote Euler's number, defined in the [[Derivation of Euler's Number e]] as the finite limit of the strictly increasing, bounded sequence of real numbers:
$$
\begin{gather}
e := \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n \tag{1}
\end{gather}
$$

# Theorem 1
The continuous compounding function $f(x) := \left(1 + \frac{1}{x}\right)^x$ converges to Euler's number $e$ over the base of unsigned infinity:
$$
\begin{gather}
\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e \tag{2}
\end{gather}
$$
First, consider the directional limit along positive infinity ($x \to +\infty$). Let $x \in \mathbb{R}$ with $x > 1$, and let $n := \lfloor x \rfloor \in \mathbb{N}$ denote the integer floor of $x$. By definition of the floor function, $n$ satisfies the bounding relation:
$$
\begin{gather}
n \le x < n + 1 \tag{3}
\end{gather}
$$
with $n \ge 1$ because $x > 1$. Taking the reciprocals of all terms in step 3 reverses the directional inequalities:
$$
\begin{gather}
\frac{1}{n + 1} < \frac{1}{x} \le \frac{1}{n} \tag{4}
\end{gather}
$$
Adding $1$ across step 4 yields:
$$
\begin{gather}
1 < 1 + \frac{1}{n + 1} < 1 + \frac{1}{x} \le 1 + \frac{1}{n} \tag{5}
\end{gather}
$$
Because the bases in step 5 are strictly greater than $1$, raising a strictly smaller base to the strictly smaller exponent $n \le x$ and a larger base to the strictly larger exponent $x < n + 1$ produces the squeeze inequality:
$$
\begin{gather}
\left(1 + \frac{1}{n + 1}\right)^n < \left(1 + \frac{1}{x}\right)^x < \left(1 + \frac{1}{n}\right)^{n + 1} \tag{6}
\end{gather}
$$
Now examine the asymptotic convergence of the discrete bounding sequences in step 6 as $n \to \infty$:
For the lower bounding sequence, rewrite the expression as:
$$
\begin{gather}
\left(1 + \frac{1}{n + 1}\right)^n = \frac{\left(1 + \frac{1}{n + 1}\right)^{n + 1}}{1 + \frac{1}{n + 1}} \tag{7}
\end{gather}
$$
As $n \to \infty$, the index $k := n + 1 \to \infty$. By step 1, $\lim_{k \to \infty} \left(1 + \frac{1}{k}\right)^k = e$, while $\lim_{n \to \infty} \left(1 + \frac{1}{n + 1}\right) = 1 + 0 = 1$. Applying the quotient rule for limits of sequences from the [[Proof of Arithmetic Operations Involving Limits]] to step 7 gives:
$$
\begin{gather}
\lim_{n \to \infty} \left(1 + \frac{1}{n + 1}\right)^n = \frac{\lim_{n \to \infty} \left(1 + \frac{1}{n + 1}\right)^{n + 1}}{\lim_{n \to \infty} \left(1 + \frac{1}{n + 1}\right)} = \frac{e}{1} = e \tag{8}
\end{gather}
$$
For the upper bounding sequence, decompose the exponent as:
$$
\begin{gather}
\left(1 + \frac{1}{n}\right)^{n + 1} = \left(1 + \frac{1}{n}\right)^n \cdot \left(1 + \frac{1}{n}\right) \tag{9}
\end{gather}
$$
By step 1, $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$, while $\lim_{n \to \infty} \left(1 + \frac{1}{n}\right) = 1 + 0 = 1$. Applying the product rule for limits of sequences from the [[Proof of Arithmetic Operations Involving Limits]] to step 9 gives:
$$
\begin{gather}
\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^{n + 1} = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n \cdot \lim_{n \to \infty} \left(1 + \frac{1}{n}\right) = e \cdot 1 = e \tag{10}
\end{gather}
$$
Let $\varepsilon > 0$ be an arbitrary positive error tolerance. By step 8 and step 10, there exists an integer $N_1 \in \mathbb{N}$ such that for all $n > N_1$:
$$
\begin{gather}
e - \varepsilon < \left(1 + \frac{1}{n + 1}\right)^n < e + \varepsilon \tag{11}
\end{gather}
$$
and there exists an integer $N_2 \in \mathbb{N}$ such that for all $n > N_2$:
$$
\begin{gather}
e - \varepsilon < \left(1 + \frac{1}{n}\right)^{n + 1} < e + \varepsilon \tag{12}
\end{gather}
$$
Define the natural threshold $N := \max(N_1, N_2)$, and set the positive real cutoff $M_1 := N + 1 > 0$. For every real number $x > M_1$, the integer floor satisfies $n = \lfloor x \rfloor \ge \lfloor M_1 \rfloor = N + 1 > N$. Combining the bounds of step 6, step 11, and step 12 yields:
$$
\begin{gather}
e - \varepsilon < \left(1 + \frac{1}{n + 1}\right)^n < \left(1 + \frac{1}{x}\right)^x < \left(1 + \frac{1}{n}\right)^{n + 1} < e + \varepsilon \tag{13}
\end{gather}
$$
Consequently, for every $x > M_1$:
$$
\begin{gather}
\left|\left(1 + \frac{1}{x}\right)^x - e\right| < \varepsilon \tag{14}
\end{gather}
$$
Because $\varepsilon > 0$ was chosen arbitrarily, step 14 satisfies the definition of the limit at positive infinity:
$$
\begin{gather}
\lim_{x \to +\infty} \left(1 + \frac{1}{x}\right)^x = e \tag{15}
\end{gather}
$$
Second, consider the directional limit along negative infinity ($x \to -\infty$). Let $x \in \mathbb{R}$ satisfy $x < -1$. Introduce the coordinate transformation:
$$
\begin{gather}
y := -(x + 1) = -x - 1 \iff x = -(y + 1) \tag{16}
\end{gather}
$$
Because $x < -1$, the transformed variable satisfies $y > 0$. As $x \to -\infty$, $y \to +\infty$. Express the base $1 + \frac{1}{x}$ in terms of $y$:
$$
\begin{gather}
1 + \frac{1}{x} = 1 - \frac{1}{y + 1} = \frac{y + 1 - 1}{y + 1} = \frac{y}{y + 1} \tag{17}
\end{gather}
$$
Raising step 17 to the exponent $x = -(y + 1)$ gives:
$$
\begin{gather}
\left(1 + \frac{1}{x}\right)^x = \left(\frac{y}{y + 1}\right)^{-(y + 1)} = \left(\frac{y + 1}{y}\right)^{y + 1} = \left(1 + \frac{1}{y}\right)^{y + 1} \tag{18}
\end{gather}
$$
Factoring the expression on the right-hand side of step 18 gives:
$$
\begin{gather}
\left(1 + \frac{1}{y}\right)^{y + 1} = \left(1 + \frac{1}{y}\right)^y \cdot \left(1 + \frac{1}{y}\right) \tag{19}
\end{gather}
$$
As $x \to -\infty$, the variable $y = -x - 1 \to +\infty$. By step 15, the first factor converges to $e$:
$$
\begin{gather}
\lim_{y \to +\infty} \left(1 + \frac{1}{y}\right)^y = e \tag{20}
\end{gather}
$$
while the second factor satisfies:
$$
\begin{gather}
\lim_{y \to +\infty} \left(1 + \frac{1}{y}\right) = 1 + 0 = 1 \tag{21}
\end{gather}
$$
Applying Theorem 2 of the [[Proof of Arithmetic Operations on Limits]] and the [[Proof of Limit of a Composite Function]] across the mapping $y(x) = -x - 1$ produces:
$$
\begin{gather}
\lim_{x \to -\infty} \left(1 + \frac{1}{x}\right)^x = \lim_{y \to +\infty} \left[\left(1 + \frac{1}{y}\right)^y \cdot \left(1 + \frac{1}{y}\right)\right] = e \cdot 1 = e \tag{22}
\end{gather}
$$
Third, consider the unsigned limit at infinity ($x \to \infty$). Let $\varepsilon > 0$ be given. By step 14, there exists $M_1 > 0$ such that $x > M_1 \implies \left|\left(1 + \frac{1}{x}\right)^x - e\right| < \varepsilon$. By step 22 and the definition of the limit at negative infinity, there exists $M_2 < 0$ such that $x < M_2 \implies \left|\left(1 + \frac{1}{x}\right)^x - e\right| < \varepsilon$. Define the positive magnitude cutoff:
$$
\begin{gather}
M := \max(M_1, |M_2|) > 0 \tag{23}
\end{gather}
$$
For every $x \in \mathbb{R}$ satisfying $|x| > M$, either $x > M \ge M_1$ or $x < -M \le M_2$. In both cases:
$$
\begin{gather}
\left|\left(1 + \frac{1}{x}\right)^x - e\right| < \varepsilon \quad \forall |x| > M \tag{24}
\end{gather}
$$
By Definition 3 of Limits at Infinity, step 24 establishes that:
$$
\begin{gather}
\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e \tag{25}
\end{gather}
$$

---
# Theorem 2
The infinitesimal compounding limit satisfies:
$$
\begin{gather}
\lim_{t \to 0} (1 + t)^{1/t} = e \tag{26}
\end{gather}
$$
Consider the punctured domain $E := \mathbb{R} \setminus \{0\}$, and define the reciprocal coordinate mapping $h: E \to \mathbb{R}$ by:
$$
\begin{gather}
h(t) := \frac{1}{t} \tag{27}
\end{gather}
$$
Under the substitution $x = h(t) = \frac{1}{t}$, the expression $(1 + t)^{1/t}$ is the composite function:
$$
\begin{gather}
g(t) := (f \circ h)(t) = f(h(t)) = \left(1 + \frac{1}{h(t)}\right)^{h(t)} = (1 + t)^{1/t} \tag{28}
\end{gather}
$$
where $f(x) := \left(1 + \frac{1}{x}\right)^x$.

To establish the two-sided limit $\lim_{t \to 0} (1 + t)^{1/t} = e$, examine the one-sided directional limits:
First, as $t \to 0^+$, $t > 0$, so $h(t) = \frac{1}{t} > 0$. For any positive bound $K > 0$, setting $\delta_1 := \frac{1}{K} > 0$ ensures that for all $t \in (0, \delta_1)$:
$$
\begin{gather}
0 < t < \delta_1 \implies h(t) = \frac{1}{t} > \frac{1}{\delta_1} = K \tag{29}
\end{gather}
$$
which demonstrates that $\lim_{t \to 0^+} h(t) = +\infty$. Applying the [[Proof of Limit of a Composite Function]] across the base mapping $h((0, \delta_1)) \subseteq (K, +\infty)$ and combining this with step 15 yields:
$$
\begin{gather}
\lim_{t \to 0^+} (1 + t)^{1/t} = \lim_{x \to +\infty} \left(1 + \frac{1}{x}\right)^x = e \tag{30}
\end{gather}
$$
Second, as $t \to 0^-$, $t < 0$, so $h(t) = \frac{1}{t} < 0$. For any negative bound $K < 0$, setting $\delta_2 := \frac{1}{|K|} > 0$ ensures that for all $t \in (-\delta_2, 0)$:
$$
\begin{gather}
-\delta_2 < t < 0 \implies h(t) = \frac{1}{t} < -\frac{1}{\delta_2} = -|K| = K \tag{31}
\end{gather}
$$
which demonstrates that $\lim_{t \to 0^-} h(t) = -\infty$. Applying the [[Proof of Limit of a Composite Function]] across the base mapping $h((-\delta_2, 0)) \subseteq (-\infty, K)$ and combining this with step 22 yields:
$$
\begin{gather}
\lim_{t \to 0^-} (1 + t)^{1/t} = \lim_{x \to -\infty} \left(1 + \frac{1}{x}\right)^x = e \tag{32}
\end{gather}
$$
Because both one-sided directional limits exist and agree identically with $e$, the [[Proof of the Equivalence of Two-Sided and One-Sided Limits]] guarantees that the two-sided limit exists and equals $e$:
$$
\begin{gather}
\lim_{t \to 0} (1 + t)^{1/t} = e \tag{33}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
