---
dg-publish: true
---
# Corollary 1
Let $\{x_n\}$ be a sequence of real numbers with inferior limit $l := \liminf_{n \to \infty} x_n$ and superior limit $L := \limsup_{n \to \infty} x_n$ in the extended real line $\mathbb{R} \cup \{-\infty, +\infty\}$. For each $n \in \mathbb{N}$, denote the tail infimum by $i_n := \inf_{k \ge n} x_k$ and the tail supremum by $s_n := \sup_{k \ge n} x_k$.

**Necessity:**
Assume that $\lim_{n \to \infty} x_n = A$, where $A \in \mathbb{R} \cup \{-\infty, +\infty\}$. By definition of sequence convergence (or divergence to $\pm\infty$), every subsequence of $\{x_n\}$ converges (or tends) to $A$. By the [[Proof that the Inferior (Superior) Limit is the Smallest (Largest) of its Partial Limits|Partial Limits Proposition]], both $l$ and $L$ are partial limits of $\{x_n\}$, meaning there exist subsequences converging (or tending) to $l$ and $L$, respectively. By uniqueness of subsequential limits, it follows that:
$$
\begin{gather}
l = L = A \tag{1}
\end{gather}
$$

**Sufficiency:**
Conversely, assume that $l = L = A$ for some $A \in \mathbb{R} \cup \{-\infty, +\infty\}$. By definition of the infimum and supremum over the tail $\{x_k \mid k \ge n\}$, every term $x_n$ satisfies:
$$
\begin{gather}
i_n \le x_n \le s_n \quad \forall n \in \mathbb{N} \tag{2}
\end{gather}
$$
Evaluating the three cases for $A$:

**Case 1 ($A \in \mathbb{R}$ is finite):** Because $\lim_{n \to \infty} i_n = l = A \in \mathbb{R}$ and $\lim_{n \to \infty} s_n = L = A \in \mathbb{R}$, applying the [[Proof of Inequalities Involving Limits|Squeeze Theorem]] directly to step 2 yields $\lim_{n \to \infty} x_n = A$.

**Case 2 ($A = +\infty$):** Because $l = \lim_{n \to \infty} i_n = +\infty$, for every real constant $c \in \mathbb{R}$ there exists an index $N \in \mathbb{N}$ such that $i_n > c$ for all $n > N$. By step 2, $x_n \ge i_n > c$ for all $n > N$, proving that $x_n \to +\infty$.

**Case 3 ($A = -\infty$):** Because $L = \lim_{n \to \infty} s_n = -\infty$, for every real constant $c \in \mathbb{R}$ there exists an index $N \in \mathbb{N}$ such that $s_n < c$ for all $n > N$. By step 2, $x_n \le s_n < c$ for all $n > N$, proving that $x_n \to -\infty$.

---
# Corollary 2
Let $\{x_n\}$ be a sequence of real numbers, and let $A \in \mathbb{R}$.

**Necessity:**
Assume that $\{x_n\}$ converges to a finite real number $A \in \mathbb{R}$, and let $\{x_{n_k}\}_{k=1}^\infty$ be an arbitrary subsequence of $\{x_n\}$. Let $\varepsilon > 0$ be given.

By definition of convergence, there exists an index $N \in \mathbb{N}$ such that $|x_n - A| < \varepsilon$ for all $n > N$. Because $n_1 < n_2 < \dots < n_k < \dots$ is a strictly increasing sequence of natural numbers, induction establishes that $n_k \ge k$ for all $k \in \mathbb{N}$. Consequently, for all $k > N$, it holds that $n_k \ge k > N$, which implies:
$$
\begin{gather}
|x_{n_k} - A| < \varepsilon \quad \forall k > N \tag{3}
\end{gather}
$$
Thus, every subsequence $\{x_{n_k}\}$ converges to the identical limit $A$.

**Sufficiency:**
Conversely, assume that every subsequence of $\{x_n\}$ converges to a finite real limit $A \in \mathbb{R}$.

First, observe that $\{x_n\}$ must be bounded in $\mathbb{R}$. If $\{x_n\}$ were unbounded, the [[Proof that a Convergent Subsequence or Subsequence Tending to Infinity Can be Constructed From a Sequence of Real Numbers|Lemma on Subsequences and Infinity]] would guarantee the existence of a subsequence tending to $+\infty$ or $-\infty$, contradicting the hypothesis that every subsequence converges to a finite limit.

Because $\{x_n\}$ is bounded, its inferior limit $l$ and superior limit $L$ are both finite real numbers. Suppose, for the sake of contradiction, that $l \neq L$. By the Partial Limits Proposition, there exists a subsequence $\{x_{n_k}\}$ converging to $l$ and a subsequence $\{x_{m_k}\}$ converging to $L$. By hypothesis, every subsequence of $\{x_n\}$ must converge to the same limit $A$, forcing $l = A$ and $L = A$, so that $l = L$. By Corollary 1, the parent sequence $\{x_n\}$ converges to $A$.

---
# Corollary 3
First, consider the restricted Bolzano-Weierstrass Lemma for a bounded real sequence $\{x_n\}$. Because $\{x_n\}$ is bounded, there exist finite real constants $m, M \in \mathbb{R}$ such that $m \le x_n \le M$ for all $n \in \mathbb{N}$. The tail bounds satisfy $m \le i_n \le s_n \le M$ for all $n \in \mathbb{N}$, ensuring that both $l = \liminf_{n \to \infty} x_n$ and $L = \limsup_{n \to \infty} x_n$ exist as finite real numbers:
$$
\begin{gather}
m \le l \le L \le M \tag{4}
\end{gather}
$$
By the Partial Limits Proposition, $l$ and $L$ are partial limits of $\{x_n\}$. By definition of a partial limit, there exists at least one subsequence converging to the finite real number $L$ (and at least one converging to $l$), proving that every bounded sequence contains a convergent subsequence.

Second, consider the general lemma for an arbitrary sequence $\{x_n\}$ of real numbers. If $\{x_n\}$ is bounded, it contains a convergent subsequence by the restricted argument above. If $\{x_n\}$ is unbounded, then $\{x_n\}$ is either unbounded above (in which case $L = \limsup_{n \to \infty} x_n = +\infty$) or unbounded below (in which case $l = \liminf_{n \to \infty} x_n = -\infty$). Because $L$ and $l$ are partial limits in the extended real line $\mathbb{R} \cup \{-\infty, +\infty\}$, there exists a subsequence tending to $+\infty$ or $-\infty$ (and hence tending to unsigned infinity $\infty$).
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
