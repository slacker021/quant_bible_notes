---
dg-publish: true
---
Let $f: (a, b) \to \mathbb{R}$ be a nondecreasing function on the open interval $(a, b)$, and let $x_0 \in (a, b)$ be an arbitrary interior point.

Define the left-hand sub-domain:
$$
\begin{gather}
E_L := (a, x_0) \subset (a, b) \tag{1}
\end{gather}
$$
Because $f$ is nondecreasing, for every point $x \in E_L$, the ordering $x < x_0$ dictates that:
$$
\begin{gather}
f(x) \le f(x_0) \tag{2}
\end{gather}
$$
Step 2 demonstrates that the functional image set $f(E_L) = \{f(x) \mid x \in (a, x_0)\}$ is bounded above in $\mathbb{R}$ by the finite real constant $f(x_0)$. 

Because $x_0 = \sup E_L$, Theorem 1 of the [[Proof of Criterion for Monotonic Function Limit]] applies directly to $f$ on $E_L$, guaranteeing that the left-hand limit exists as a finite real number and equals the exact supremum:
$$
\begin{gather}
\lim_{x \to x_0^-} f(x) = \sup_{x < x_0} f(x) \le f(x_0) \tag{3}
\end{gather}
$$
Next, define the right-hand sub-domain:
$$
\begin{gather}
E_R := (x_0, b) \subset (a, b) \tag{4}
\end{gather}
$$
Because $f$ is nondecreasing, for every point $x \in E_R$, the ordering $x_0 < x$ dictates that:
$$
\begin{gather}
f(x_0) \le f(x) \tag{5}
\end{gather}
$$
Step 5 demonstrates that the functional image set $f(E_R) = \{f(x) \mid x \in (x_0, b)\}$ is bounded below in $\mathbb{R}$ by $f(x_0)$. 

Because $x_0 = \inf E_R$, Theorem 2 of the [[Proof of Criterion for Monotonic Function Limit]] applies directly to $f$ on $E_R$, guaranteeing that the right-hand limit exists as a finite real number and equals the exact infimum:
$$
\begin{gather}
\lim_{x \to x_0^+} f(x) = \inf_{x > x_0} f(x) \ge f(x_0) \tag{6}
\end{gather}
$$
Combining the inequalities from step 3, step 2, step 5, and step 6 establishes the canonical chain:
$$
\begin{gather}
\lim_{x \to x_0^-} f(x) = \sup_{x < x_0} f(x) \le f(x_0) \le \inf_{x > x_0} f(x) = \lim_{x \to x_0^+} f(x)
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$