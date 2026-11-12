---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be a non-degenerate interval (open, closed, or semi-infinite), and let $f: I \to \mathbb{R}$ be a real-valued mapping. Suppose that $F_1, F_2: I \to \mathbb{R}$ are two primitives of $f$ on $I$.

By definition of a primitive, both $F_1$ and $F_2$ are differentiable at every point of $I$, satisfying:
$$
\begin{gather}
F_1'(x) = f(x) \quad \text{and} \quad F_2'(x) = f(x) \quad \forall x \in I \tag{1}
\end{gather}
$$

Define the auxiliary difference function $H: I \to \mathbb{R}$ by:
$$
\begin{gather}
H(x) := F_1(x) - F_2(x), \quad \forall x \in I \tag{2}
\end{gather}
$$

---
# Proposition 1 
Because $F_1$ and $F_2$ are differentiable on $I$, the linearity of differentiation establishes that $H$ is differentiable at every point $x \in I$. Differentiating step 2 and substituting step 1 yields:
$$
\begin{gather}
H'(x) = F_1'(x) - F_2'(x) = f(x) - f(x) = 0 \quad \forall x \in I \tag{3}
\end{gather}
$$

To prove that $H$ is constant on $I$, fix an arbitrary base point $x_0 \in I$, and let $x \in I$ be any other point with $x \neq x_0$. 

Without loss of generality, assume $x_0 < x$ (if $x < x_0$, an identical argument applies by exchanging the roles of $x_0$ and $x$). Because $I$ is an interval, the connected topology of $I$ ensures that the compact subinterval $[x_0, x]$ is entirely contained in $I$:
$$
\begin{gather}
[x_0, x] \subseteq I \tag{4}
\end{gather}
$$

The restriction of $H$ to $[x_0, x]$ satisfies the hypotheses of [[Proof of Lagrange's Finite-Increment Theorem|Lagrange's Mean-Value Theorem]]:
1. $H$ is continuous on $[x_0, x]$ because differentiability on $I$ implies continuity on $I$.
2. $H$ is differentiable on the open interval $(x_0, x)$ because $(x_0, x) \subset I$.

Consequently, there exists an intermediate point $\xi \in (x_0, x)$ such that:
$$
\begin{gather}
\frac{H(x) - H(x_0)}{x - x_0} = H'(\xi) \tag{5}
\end{gather}
$$

By step 3, $H'(t) = 0$ for all $t \in I$. Because $\xi \in (x_0, x) \subset I$, it follows that $H'(\xi) = 0$. Substituting this evaluation into step 5 yields:
$$
\begin{gather}
\frac{H(x) - H(x_0)}{x - x_0} = 0 \implies H(x) - H(x_0) = 0 \implies H(x) = H(x_0) \tag{6}
\end{gather}
$$

Because $x \in I$ was arbitrary, step 6 proves that $H$ assumes the identical constant value $C := H(x_0) \in \mathbb{R}$ across the entire interval $I$. 

Substituting step 2 into this conclusion gives:
$$
\begin{gather}
F_1(x) - F_2(x) = C \quad \forall x \in I \tag{7}
\end{gather}
$$
The uniqueness of this scalar $C$ is immediate: evaluating step 7 at any point $x \in I$ uniquely determines $C = F_1(x) - F_2(x)$.

---
# Proposition 2
To demonstrate that interval connectedness is essential, suppose the domain $E \subset \mathbb{R}$ is a disconnected open set partitioned into a disjoint union of non-empty open connected components:
$$
\begin{gather}
E = \bigcup_{\alpha \in \mathcal{A}} I_\alpha, \quad \text{where } I_\alpha \cap I_\beta = \emptyset \text{ for } \alpha \neq \beta \tag{8}
\end{gather}
$$
and each $I_\alpha$ is an open interval.

If $F_1, F_2: E \to \mathbb{R}$ satisfy $F_1'(x) = F_2'(x) = f(x)$ for all $x \in E$, the auxiliary difference $H = F_1 - F_2$ satisfies $H'(x) = 0$ for all $x \in E$. Applying Proposition 1 independently to each connected component $I_\alpha$ establishes that for each index $\alpha \in \mathcal{A}$, there exists a constant $C_\alpha \in \mathbb{R}$ such that:
$$
\begin{gather}
F_1(x) - F_2(x) = C_\alpha \quad \forall x \in I_\alpha \tag{9}
\end{gather}
$$
When $|\mathcal{A}| \ge 2$, the constants $\{C_\alpha\}_{\alpha \in \mathcal{A}}$ can be chosen independently. The kernel of the differential operator $D$ on $E$ is therefore isomorphic to the product vector space $\mathbb{R}^{|\mathcal{A}|}$ rather than the one-dimensional line $\mathbb{R}$. Thus, global uniqueness up to a single scalar holds if and only if the underlying domain is connected.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
