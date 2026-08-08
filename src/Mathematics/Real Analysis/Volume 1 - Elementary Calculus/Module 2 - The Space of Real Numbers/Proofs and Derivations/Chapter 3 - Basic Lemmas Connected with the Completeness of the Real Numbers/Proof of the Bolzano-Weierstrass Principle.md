---
dg-publish: true
---
Let $X \subseteq \mathbb{R}$ be a bounded infinite subset of the real numbers. Because $X$ is bounded both from below and from above, there exist real numbers $a, b \in \mathbb{R}$ with $a < b$ such that $X$ is entirely contained within the closed and bounded interval $I := [a, b]$:
$$
\begin{gather}
X \subseteq I = [a, b] \tag{1}
\end{gather}
$$
Suppose, for the sake of contradiction, that $X$ possesses no limit point in $\mathbb{R}$. Under this assumption, no point $x \in I$ can be a limit point of $X$. By the definition of a limit point, for every point $x \in I$, there exists an open neighborhood $U(x)$ of $x$ that contains at most finitely many points of $X$:
$$
\begin{gather}
\forall x \in I, \quad \exists U(x) = (x - \varepsilon_x, x + \varepsilon_x) \quad \text{such that} \quad |U(x) \cap X| < \infty \tag{2}
\end{gather}
$$
Because each point $x \in I$ belongs to its own neighborhood $U(x)$, the collection of all such open intervals $\{U(x)\}_{x \in I}$ forms an open cover of the closed and bounded interval $I$:
$$
\begin{gather}
I = [a, b] \subseteq \bigcup_{x \in I} U(x) \tag{3}
\end{gather}
$$
By the Borel-Lebesgue Principle (see [[Proof of the Borel-Lebesgue Principle]]), the open cover in step 3 contains a finite subcover. That is, there exists a finite subset of points $\{x_1, x_2, \dots, x_n\} \subseteq I$ whose corresponding open neighborhoods cover $I$. Combining step 1 with this finite subcover yields:
$$
\begin{gather}
X \subseteq I \subseteq \bigcup_{i=1}^n U(x_i) \implies X = X \cap \left(\bigcup_{i=1}^n U(x_i)\right) = \bigcup_{i=1}^n \left(U(x_i) \cap X\right) \tag{4}
\end{gather}
$$
By step 2, each intersection $U(x_i) \cap X$ for $i \in \{1, 2, \dots, n\}$ contains at most finitely many elements of $X$. Because a finite union of finite sets is necessarily finite, step 4 implies that $X$ is a finite set. This directly contradicts the initial hypothesis that $X$ is an infinite subset of $\mathbb{R}$. Therefore, $X$ must possess at least one limit point in $I \subseteq \mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
