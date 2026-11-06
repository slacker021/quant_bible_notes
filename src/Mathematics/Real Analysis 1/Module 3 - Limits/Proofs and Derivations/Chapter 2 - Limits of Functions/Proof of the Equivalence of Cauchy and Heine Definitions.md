---
dg-publish: true
---
Let $f: E \to \mathbb{R}$ and let $a \in E'$ be an accumulation point of $E$. Let $A \in \mathbb{R}$.

**Necessity ($\implies$ Cauchy implies Heine):**
Assume that the Cauchy functional limit holds:
$$\begin{gather} \lim_{E \ni x \to a} f(x) = A \tag{1} \end{gather}$$
Let $\{x_n\}_{n=1}^\infty$ be an arbitrary sequence of points in $E \setminus \{a\}$ such that $\lim_{n \to \infty} x_n = a$.

Let $\varepsilon > 0$ be given. By virtue of step 1, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$\begin{gather} 0 < \vert{}x - a\vert{} < \delta \implies \vert{}f(x) - A\vert{} < \varepsilon \tag{2} \end{gather}$$
Because $\lim_{n \to \infty} x_n = a$, there exists a natural threshold $N \in \mathbb{N}$ such that for all $n > N$:
$$\begin{gather} \vert{}x_n - a\vert{} < \delta \tag{3} \end{gather}$$
Because $x_n \in E \setminus \{a\}$ for all $n$, it follows that $x_n \in E$ and $\vert{}x_n - a\vert{} > 0$, so step 3 becomes:
$$\begin{gather} 0 < \vert{}x_n - a\vert{} < \delta \quad \forall n > N \tag{4} \end{gather}$$
Applying step 2 to each term $x_n$ satisfying step 4 demonstrates that:
$$\begin{gather} \vert{}f(x_n) - A\vert{} < \varepsilon \quad \forall n > N \tag{5} \end{gather}$$
Because $\varepsilon > 0$ was arbitrary, step 5 proves that the image sequence converges: $\lim_{n \to \infty} f(x_n) = A$.

**Sufficiency ($\impliedby$ Heine implies Cauchy):**
The sufficiency direction is established via proof by contraposition. Assume that the Cauchy condition does not hold for the candidate limit $A$.

The logical negation of step 1 states that there exists an error tolerance $\varepsilon_0 > 0$ such that for every distance $\delta > 0$, there exists at least one point $x \in E$ satisfying $0 < \vert{}x - a\vert{} < \delta$ for which $\vert{}f(x) - A\vert{} \ge \varepsilon_0$.

For each natural number $n \in \mathbb{N}$, instantiate this property with the choice $\delta_n := \frac{1}{n} > 0$. By the Axiom of Countable Choice, there exists a corresponding point $x_n \in E$ such that:
$$\begin{gather} 0 < \vert{}x_n - a\vert{} < \frac{1}{n} \quad \text{and} \quad \vert{}f(x_n) - A\vert{} \ge \varepsilon_0 \tag{6} \end{gather}$$
From the left-hand inequality of step 6, $x_n \in E \setminus \{a\}$ for all $n \in \mathbb{N}$. Furthermore, because $\lim_{n \to \infty} \frac{1}{n} = 0$, the Squeeze Theorem applied to $0 < \vert{}x_n - a\vert{} < \frac{1}{n}$ guarantees that:
$$\begin{gather} \lim_{n \to \infty} x_n = a \tag{7} \end{gather}$$
However, the right-hand condition of step 6 establishes that the distance between $f(x_n)$ and $A$ remains bounded below by $\varepsilon_0 > 0$ for all $n \in \mathbb{N}$. Consequently:
$$\begin{gather} \lim_{n \to \infty} f(x_n) \neq A \tag{8} \end{gather}$$
Thus, there exists a sequence $\{x_n\} \subset E \setminus \{a\}$ converging to $a$ whose image sequence does not converge to $A$, violating the Heine criterion. By contraposition, the Heine condition implies the Cauchy condition.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$