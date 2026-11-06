---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $f: I \to \mathbb{R}$ be continuous on $I$. 

Define the image set:
$$
\begin{gather}
J := f(I) = \{f(x) \in \mathbb{R} \mid x \in I\} \tag{1}
\end{gather}
$$

If $f$ is a constant function, then $J = \{c\}$ for some $c \in \mathbb{R}$, which is a degenerate interval consisting of a single point. 

Assume, therefore, that $J$ contains at least two distinct points. 

Recall that a subset $J \subseteq \mathbb{R}$ is an interval if and only if it possesses the intermediate-point property:
$$
\begin{gather}
\forall y_1, y_2 \in J \ \big(y_1 < y_2 \implies [y_1, y_2] \subseteq J\big) \tag{2}
\end{gather}
$$

Let $y_1, y_2 \in J$ with $y_1 < y_2$, and let $\gamma$ be an arbitrary element satisfying:
$$
\begin{gather}
y_1 < \gamma < y_2 \tag{3}
\end{gather}
$$

Because $y_1, y_2 \in J = f(I)$, there exist points $x_1, x_2 \in I$ such that:
$$
\begin{gather}
f(x_1) = y_1 \quad \text{and} \quad f(x_2) = y_2 \tag{4}
\end{gather}
$$

Because $y_1 \ne y_2$, it follows that $x_1 \ne x_2$. Define the closed interval:
$$
\begin{gather}
I_{12} := [\min(x_1, x_2), \max(x_1, x_2)] \tag{5}
\end{gather}
$$

Because $I$ is an interval and $x_1, x_2 \in I$, the subset $I_{12}$ is contained within $I$:
$$
\begin{gather}
I_{12} \subseteq I \tag{6}
\end{gather}
$$

Because $f$ is continuous on $I$, the restriction of $f$ to $I_{12}$ is continuous. 

By step 3 and step 4, the real number $\gamma$ lies strictly between $f(x_1)$ and $f(x_2)$. 

Applying the [[Proof of the Darboux Intermediate-Value Theorem]] to $f$ on $I_{12}$ guarantees the existence of a point $c$ in the interior of $I_{12}$ such that:
$$
\begin{gather}
f(c) = \gamma \tag{7}
\end{gather}
$$

By step 6, $c \in I_{12} \subseteq I$. It follows directly from step 1 and step 7 that:
$$
\begin{gather}
\gamma = f(c) \in f(I) = J \tag{8}
\end{gather}
$$

Because $\gamma$ was arbitrary in $(y_1, y_2)$, the open interval $(y_1, y_2)$ is a subset of $J$. Since $y_1, y_2 \in J$ by assumption, the entire closed segment $[y_1, y_2] \subseteq J$. 

Thus, $J$ satisfies the intermediate-point property of step 2, proving that $f(I)$ is an interval.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
