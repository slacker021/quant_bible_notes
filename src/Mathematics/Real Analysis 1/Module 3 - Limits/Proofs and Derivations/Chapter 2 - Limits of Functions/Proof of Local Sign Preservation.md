---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $f: X \to \mathbb{R}$ satisfy $\lim_{\mathcal{B}} f(x) = A \in \mathbb{R}$.

First, assume that $A > 0$. Define the positive error tolerance:
$$\begin{gather}
\varepsilon := \frac{A}{2} > 0 \tag{1}
\end{gather}$$
By definition of the limit over a base, there exists an element $B \in \mathcal{B}$ such that for all $x \in B$:
$$\begin{gather} \vert{}f(x) - A| < \frac{A}{2} \iff -\frac{A}{2} < f(x) - A < \frac{A}{2} \tag{2}
\end{gather}$$
Adding $A$ across the inequality chain of step 2 yields:
$$\begin{gather} f(x) > A - \frac{A}{2} = \frac{A}{2} > 0 \quad \forall x \in B \tag{3} \end{gather}$$
Second, assume that $A < 0$. Define the positive error tolerance:
$$\begin{gather} \varepsilon := \frac{-A}{2} = \frac{\vert{}A\vert{}}{2} > 0 \tag{4} \end{gather}$$
There exists an element $B \in \mathcal{B}$ such that for all $x \in B$:
$$\begin{gather} \vert{}f(x) - A\vert{} < -\frac{A}{2} \iff \frac{A}{2} < f(x) - A < -\frac{A}{2} \tag{5} \end{gather}$$
Adding $A$ across step 5 yields:
$$\begin{gather} f(x) < A - \frac{A}{2} = \frac{A}{2} < 0 \quad \forall x \in B \tag{6} \end{gather}$$
Finally, suppose $A \neq 0$. Combining step 3 and step 6 establishes that for both $A > 0$ and $A < 0$, there exists an element $B \in \mathcal{B}$ such that:
$$\begin{gather} \vert{}f(x)\vert{} > \frac{\vert{}A\vert{}}{2} > 0 \quad \forall x \in B \tag{7} \end{gather}$$
Step 7 proves that $f$ is strictly separated from zero ultimately over the base $\mathcal{B}$.
$$\begin{gather} \textbf{Q.E.D.} \end{gather}$$