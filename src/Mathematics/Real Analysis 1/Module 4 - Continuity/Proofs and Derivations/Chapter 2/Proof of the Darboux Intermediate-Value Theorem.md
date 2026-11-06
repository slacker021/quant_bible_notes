---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $f: I \to \mathbb{R}$ be continuous on $I$. 

Let $a, b \in I$ with $a < b$, and suppose $f(a) \ne f(b)$. Let $\gamma \in \mathbb{R}$ be an arbitrary real value strictly situated between $f(a)$ and $f(b)$. 

This condition translates to one of two mutually exclusive orderings:
$$
\begin{gather}
f(a) < \gamma < f(b) \quad \text{or} \quad f(b) < \gamma < f(a) \tag{1}
\end{gather}
$$

Define an auxiliary function $g: [a, b] \to \mathbb{R}$ by shifting $f$ by the constant $\gamma$:
$$
\begin{gather}
g(x) := f(x) - \gamma \tag{2}
\end{gather}
$$

Because $f$ is continuous on $[a, b]$ and constant functions are continuous everywhere, the difference $g$ is continuous on $[a, b]$ by the algebraic properties established in [[Proof of Preservation of Continuity under Algebraic Field Operations]].

Evaluate the auxiliary function $g$ at the boundary endpoints:
$$
\begin{gather}
g(a) = f(a) - \gamma \quad \text{and} \quad g(b) = f(b) - \gamma \tag{3}
\end{gather}
$$

Under the first ordering of step 1 ($f(a) < \gamma < f(b)$):
$$
\begin{gather}
g(a) = f(a) - \gamma < 0 \quad \text{and} \quad g(b) = f(b) - \gamma > 0 \tag{4}
\end{gather}
$$

Under the second ordering of step 1 ($f(b) < \gamma < f(a)$):
$$
\begin{gather}
g(a) = f(a) - \gamma > 0 \quad \text{and} \quad g(b) = f(b) - \gamma < 0 \tag{5}
\end{gather}
$$

In either case, the endpoint values have opposite signs:
$$
\begin{gather}
g(a) \cdot g(b) < 0 \tag{6}
\end{gather}
$$

Applying the [[Proof of the Bolzano-Cauchy Zero Theorem]] to the continuous function $g$ on $[a, b]$ guarantees the existence of at least one interior point $c \in (a, b)$ such that:
$$
\begin{gather}
g(c) = 0 \tag{7}
\end{gather}
$$

Substituting the definition of $g$ from step 2 into step 7:
$$
\begin{gather}
f(c) - \gamma = 0 \iff f(c) = \gamma \tag{8}
\end{gather}
$$

Because $a, b \in I$ and $I$ is an interval, $(a, b) \subset I$, which implies $c \in I$. 

This confirms that the continuous mapping $f$ attains the intermediate value $\gamma$ on the interval $(a, b)$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
