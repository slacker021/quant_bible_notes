---
dg-publish: true
---
Let $-\infty \le a < b \le +\infty$, let $(a, b) \subset \mathbb{R}$ be an open interval, and let $f: (a, b) \to \mathbb{R}$ be a twice differentiable function on $(a, b)$.

---
# Proposition 1
By virtue of [[Proof of First-Order Monotonicity Characterization of Convexity|The First-Order Monotonicity Characterization of Convexity]], the function $f$ is convex on $(a, b)$ if and only if its first derivative $f'$ is non-decreasing on $(a, b)$:
$$
\begin{gather}
f \text{ is convex on } (a, b) \iff f' \text{ is non-decreasing on } (a, b) \tag{1}
\end{gather}
$$

Because $f$ is twice differentiable on $(a, b)$, the derivative $f'$ is itself a differentiable function on $(a, b)$ whose derivative is $(f')'(x) = f''(x)$.

Applying [[Proof of Differential Criteria for Interval Monotonicity|Proposition 2 of Differential Criteria for Interval Monotonicity]] to the differentiable function $f'$ establishes that $f'$ is non-decreasing on $(a, b)$ if and only if its derivative is non-negative everywhere:
$$
\begin{gather}
f' \text{ is non-decreasing on } (a, b) \iff \forall x \in (a, b), \ f''(x) \ge 0 \tag{2}
\end{gather}
$$

Combining the equivalence of step 1 with the equivalence of step 2 proves that:
$$
\begin{gather}
f \text{ is convex on } (a, b) \iff \forall x \in (a, b), \ f''(x) \ge 0 \tag{3}
\end{gather}
$$

---
# Proposition 2
Suppose that $f''(x) > 0$ for all $x \in $(a, b).

Applying [[Proof of Differential Criteria for Interval Monotonicity|Proposition 1 of Differential Criteria for Interval Monotonicity]] to the differentiable function $f'$ demonstrates that a strictly positive derivative $(f')'(x) = f''(x) > 0$ across $(a, b)$ implies that $f'$ is strictly increasing on $(a, b)$:
$$
\begin{gather}
(\forall x \in (a, b), \ f''(x) > 0) \implies f' \text{ is strictly increasing on } (a, b) \tag{4}
\end{gather}
$$

By virtue of [[Proof of First-Order Monotonicity Characterization of Convexity|Proposition 2 of First-Order Monotonicity Characterization of Convexity]], a differentiable function whose first derivative is strictly increasing on $(a, b)$ is strictly convex on $(a, b)$:
$$
\begin{gather}
f' \text{ is strictly increasing on } (a, b) \implies f \text{ is strictly convex on } (a, b) \tag{5}
\end{gather}
$$

Chaining step 4 and step 5 establishes that:
$$
\begin{gather}
(\forall x \in (a, b), \ f''(x) > 0) \implies f \text{ is strictly convex on } (a, b) \tag{6}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
