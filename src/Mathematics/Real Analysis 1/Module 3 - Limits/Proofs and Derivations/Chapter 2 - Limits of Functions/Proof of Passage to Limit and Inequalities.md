---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $f, g, h: X \to \mathbb{R}$.

# Theorem 1
Assume that $\lim_{\mathcal{B}} f(x) = A$ and $\lim_{\mathcal{B}} g(x) = B$, with $A < B$.

Define the positive separation parameter:
$$
\begin{gather}
\varepsilon := \frac{B - A}{2} > 0 \tag{1}
\end{gather}
$$
By definition of the limit over a base, there exists $B_1 \in \mathcal{B}$ such that $|f(x) - A| < \varepsilon$ for all $x \in B_1$, and there exists $B_2 \in \mathcal{B}$ such that $|g(x) - B| < \varepsilon$ for all $x \in B_2$.

Choose $B_0 \in \mathcal{B}$ such that $B_0 \subseteq B_1 \cap B_2$. For all $x \in B_0$:
$$
\begin{gather}
f(x) < A + \varepsilon = A + \frac{B - A}{2} = \frac{A + B}{2} \tag{2}
\end{gather}
$$
and:
$$
\begin{gather}
g(x) > B - \varepsilon = B - \frac{B - A}{2} = \frac{A + B}{2} \tag{3}
\end{gather}
$$
Combining step 2 and step 3 demonstrates that for all $x \in B_0$:
$$
\begin{gather}
f(x) < \frac{A + B}{2} < g(x) \implies f(x) < g(x) \tag{4}
\end{gather}
$$
Because $B_0 \in \mathcal{B}$, the strict inequality $f(x) < g(x)$ holds ultimately over $\mathcal{B}$.

---
# Theorem 2
Assume that $f(x) \le g(x)$ ultimately over $\mathcal{B}$, and that $\lim_{\mathcal{B}} f(x) = A$ and $\lim_{\mathcal{B}} g(x) = B$.

Assume for the purpose of contradiction that $A > B$. By Theorem 1, there exists an element $B_1 \in \mathcal{B}$ on which $g(x) < f(x)$ for all $x \in B_1$. Concurrently, by hypothesis, there exists $B_2 \in \mathcal{B}$ such that $f(x) \le g(x)$ for all $x \in B_2$.

By filter directedness, choose $B \in \mathcal{B}$ with $B \subseteq B_1 \cap B_2 \neq \emptyset$, and pick $x_0 \in B$. Then:
$$
\begin{gather}
f(x_0) \le g(x_0) \quad \text{and} \quad g(x_0) < f(x_0) \tag{5}
\end{gather}
$$
Step 5 produces an impossible contradiction ($f(x_0) < f(x_0)$). Thus, the assumption $A > B$ is false, establishing that $A \le B$.

---
# Theorem 3
Assume that $f(x) \le g(x) \le h(x)$ ultimately over $\mathcal{B}$, and that:
$$
\begin{gather}
\lim_{\mathcal{B}} f(x) = \lim_{\mathcal{B}} h(x) = C \in \mathbb{R} \tag{6}
\end{gather}
$$
Let $\varepsilon > 0$ be given. There exists $B_1 \in \mathcal{B}$ such that $C - \varepsilon < f(x) < C + \varepsilon$ for all $x \in B_1$, and there exists $B_2 \in \mathcal{B}$ such that $C - \varepsilon < h(x) < C + \varepsilon$ for all $x \in B_2$. Concurrently, there exists $B_3 \in \mathcal{B}$ such that $f(x) \le g(x) \le h(x)$ for all $x \in B_3$.

By filter directedness, choose $B \in \mathcal{B}$ such that $B \subseteq B_1 \cap B_2 \cap B_3$. For all $x \in B$:
$$
\begin{gather}
C - \varepsilon < f(x) \le g(x) \le h(x) < C + \varepsilon \implies C - \varepsilon < g(x) < C + \varepsilon \tag{7}
\end{gather}
$$
Step 7 implies that $|g(x) - C| < \varepsilon$ for all $x \in B$. Therefore, $\lim_{\mathcal{B}} g(x) = C$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$