---
dg-publish: true
---
Let $\mathcal{B}$ be a filter base on a set $X$, and let $f: X \to \mathbb{R}$.

---
# Theorem 1
Assume that $f(x) = c$ ultimately over $\mathcal{B}$.

By definition of an ultimate property, there exists an element $B_0 \in \mathcal{B}$ such that $f(x) = c$ for all $x \in B_0$. Let $\varepsilon > 0$ be arbitrary. For all $x \in B_0$:
$$\begin{gather} \vert{}f(x) - c\vert{} = \vert{}c - c\vert{} = 0 < \varepsilon \tag{1} \end{gather}$$
Because $B_0 \in \mathcal{B}$, step 1 satisfies the definition of a limit over a base, establishing that $\lim_{\mathcal{B}} f(x) = c$.

---
# Theorem 2
Assume that $f$ possesses a finite limit over the base $\mathcal{B}$, denoted $\lim_{\mathcal{B}} f(x) = A \in \mathbb{R}$.

Instantiating the definition of the limit over a base with $\varepsilon = 1 > 0$ guarantees the existence of an element $B_1 \in \mathcal{B}$ such that:
$$\begin{gather} \vert{}f(x) - A\vert{} < 1 \quad \forall x \in B_1 \tag{2} \end{gather}$$
Applying the Reverse Triangle Inequality to step 2 yields:
$$\begin{gather} \vert{}f(x)\vert{} - \vert{}A\vert{} \le \vert{}f(x) - A\vert{} < 1 \implies \vert{}f(x)\vert{} < \vert{}A\vert{} + 1 \quad \forall x \in B_1 \tag{3} \end{gather}$$
Defining the positive real constant $C := \vert{}A\vert{} + 1 > 0$, step 3 proves that $\vert{}f(x)\vert{} \le C$ for all $x \in B_1$. Because $B_1 \in \mathcal{B}$, the function $f$ is ultimately bounded over $\mathcal{B}$.

---
# Theorem 3
Assume for the purpose of contradiction that $f$ converges simultaneously to two distinct limits $A_1, A_2 \in \mathbb{R}$ over $\mathcal{B}$, with $A_1 \neq A_2$.

Define the positive error tolerance:
$$\begin{gather} \varepsilon := \frac{\vert{}A_1 - A_2\vert{}}{2} > 0 \tag{4} \end{gather}$$
Because $\lim_{\mathcal{B}} f(x) = A_1$, there exists an element $B_1 \in \mathcal{B}$ such that:
$$\begin{gather} \vert{}f(x) - A_1\vert{} < \varepsilon \quad \forall x \in B_1 \tag{5} \end{gather}$$
Because $\lim_{\mathcal{B}} f(x) = A_2$, there exists an element $B_2 \in \mathcal{B}$ such that:
$$\begin{gather} \vert{}f(x) - A_2\vert{} < \varepsilon \quad \forall x \in B_2 \tag{6} \end{gather}$$
By the defining axioms of a filter base, there exists an element $B \in \mathcal{B}$ such that $B \subseteq B_1 \cap B_2$, and $B \neq \emptyset$. Choose an arbitrary point $x_0 \in B$.

Because $x_0 \in B_1$ and $x_0 \in B_2$, applying the Triangle Inequality yields:
$$\begin{gather} \vert{}A_1 - A_2\vert{} = \vert{}(A_1 - f(x_0)) + (f(x_0) - A_2)\vert{} \le \vert{}f(x_0) - A_1\vert{} + \vert{}f(x_0) - A_2\vert{} \tag{7} \end{gather}$$
Substituting step 5 and step 6 into step 7 gives:
$$\begin{gather} \vert{}A_1 - A_2\vert{} < \varepsilon + \varepsilon = 2\varepsilon \tag{8} \end{gather}$$
By virtue of step 4, $2\varepsilon = \vert{}A_1 - A_2\vert{}$, so step 8 implies:
$$\begin{gather} \vert{}A_1 - A_2\vert{} < \vert{}A_1 - A_2\vert{} \tag{9} \end{gather}$$
The inequality of step 9 is a strict contradiction. Therefore, the assumption $A_1 \neq A_2$ is false, and the limit over $\mathcal{B}$ is unique.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$