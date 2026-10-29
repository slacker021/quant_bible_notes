---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $\alpha, \beta: X \to \mathbb{R}$ be infinitesimal functions over $\mathcal{B}$, meaning:
$$
\begin{gather}
\lim_{\mathcal{B}} \alpha(x) = 0 \quad \text{and} \quad \lim_{\mathcal{B}} \beta(x) = 0 \tag{1}
\end{gather}
$$
---
# Proposition 1
Let $\varepsilon > 0$ be given. By step 1, there exists $B_1 \in \mathcal{B}$ such that $|\alpha(x)| < \frac{\varepsilon}{2}$ for all $x \in B_1$, and there exists $B_2 \in \mathcal{B}$ such that $|\beta(x)| < \frac{\varepsilon}{2}$ for all $x \in B_2$.

By filter directedness, there exists $B \in \mathcal{B}$ such that $B \subseteq B_1 \cap B_2$. For all $x \in B$, applying the Triangle Inequality yields:
$$
\begin{gather}
|(\alpha + \beta)(x)| = |\alpha(x) + \beta(x)| \le |\alpha(x)| + |\beta(x)| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon \tag{2}
\end{gather}
$$
Thus, $\lim_{\mathcal{B}} (\alpha + \beta)(x) = 0$, proving that the sum is an infinitesimal over $\mathcal{B}$.

---
# Proposition 2
Let $\varepsilon > 0$ be given. Setting $\varepsilon_0 := \min(1, \varepsilon) > 0$, there exists $B_1 \in \mathcal{B}$ such that $|\alpha(x)| < \sqrt{\varepsilon_0}$ for all $x \in B_1$, and there exists $B_2 \in \mathcal{B}$ such that $|\beta(x)| < \sqrt{\varepsilon_0}$ for all $x \in B_2$.

Choose $B \in \mathcal{B}$ with $B \subseteq B_1 \cap B_2$. For all $x \in B$:
$$
\begin{gather}
|(\alpha \cdot \beta)(x)| = |\alpha(x)| \cdot |\beta(x)| < \sqrt{\varepsilon_0} \cdot \sqrt{\varepsilon_0} = \varepsilon_0 \le \varepsilon \tag{3}
\end{gather}
$$
Thus, $\lim_{\mathcal{B}} (\alpha \cdot \beta)(x) = 0$, proving that the product of two infinitesimals is an infinitesimal.

---
# Proposition 3
Let $\phi: X \to \mathbb{R}$ be an ultimately bounded function over $\mathcal{B}$. By definition, there exist a constant $M > 0$ and an element $B_1 \in \mathcal{B}$ such that:
$$
\begin{gather}
|\phi(x)| \le M \quad \forall x \in B_1 \tag{4}
\end{gather}
$$
Let $\varepsilon > 0$ be given. Because $\lim_{\mathcal{B}} \alpha(x) = 0$, there exists $B_2 \in \mathcal{B}$ such that:
$$
\begin{gather}
|\alpha(x)| < \frac{\varepsilon}{M} \quad \forall x \in B_2 \tag{5}
\end{gather}
$$
Choose $B \in \mathcal{B}$ such that $B \subseteq B_1 \cap B_2$. For all $x \in B$, combining step 4 and step 5 yields:
$$
\begin{gather}
|(\alpha \cdot \phi)(x)| = |\alpha(x)| \cdot |\phi(x)| < \frac{\varepsilon}{M} \cdot M = \varepsilon \tag{6}
\end{gather}
$$
Thus, $\lim_{\mathcal{B}} (\alpha \cdot \phi)(x) = 0$, proving that the product of an infinitesimal and an ultimately bounded function is an infinitesimal.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$