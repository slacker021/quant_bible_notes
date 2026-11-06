---
dg-publish: true
---
Let $\{x_n\}$ and $\{y_n\}$ be two convergent sequences of real numbers with $\lim_{n \to \infty} x_n = A$ and $\lim_{n \to \infty} y_n = B$, and let $b \in \mathbb{R}$ be a real constant.

---
# Corollary 1
Assume there exists an index $N \in \mathbb{N}$ such that $x_n > y_n$ for all $n > N$.

By definition of the order relation on $\mathbb{R}$, the strict inequality $x_n > y_n$ implies the non-strict inequality: 
$$
\begin{gather}
x_n \ge y_n \quad \forall n > N \tag{1}
\end{gather}
$$
Applying Corollary 2 to step 1 establishes that $A \ge B$.

---
# Corollary 2
Assume there exists an index $N \in \mathbb{N}$ such that $x_n \ge y_n$ for all $n > N$.

Suppose, for the sake of contradiction, that $A < B$. By the [[Proof of Inequalities Involving Limits|Theorem on Inequalities Involving Limits]], the strict inequality $A < B$ guarantees the existence of an index $N^* \in \mathbb{N}$ such that: 
$$
\begin{gather}
x_n < y_n \quad \forall n > N^* \tag{2}
\end{gather}
$$
Define the index $M := \max(N, N^*) + 1 \in \mathbb{N}$. Because $M > N$, the initial hypothesis requires $x_M \ge y_M$. Simultaneously, because $M > N^*$, step 2 requires $x_M < y_M$. Combining both deductions gives: 
$$
\begin{gather}
(x_M \ge y_M) \wedge (x_M < y_M) \tag{3}
\end{gather}
$$
Step 3 directly violates the [[Proof of Consequences of Order Axioms|Law of Trichotomy]]. Therefore, the assumption $A < B$ is false, and trichotomy forces $A \ge B$.

---
# Corollary 3
Assume there exists an index $N \in \mathbb{N}$ such that $x_n > b$ for all $n > N$.

Define the constant sequence $\{y_n\}$ by setting $y_n := b$ for all $n \in \mathbb{N}$. By the [[Proof of the Basic Properties of Limits|basic properties of limits]], $\lim_{n \to \infty} y_n = b$. Applying Corollary 1 to the sequences $\{x_n\}$ and $\{y_n\}$ yields $A \ge b$.

---
# Corollary 4
Assume there exists an index $N \in \mathbb{N}$ such that $x_n \ge b$ for all $n > N$.

Defining the constant sequence $y_n := b$ for all $n \in \mathbb{N}$ (so that $\lim_{n \to \infty} y_n = b$) and applying Corollary 2 directly to $\{x_n\}$ and $\{y_n\}$ establishes that $A \ge b$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
