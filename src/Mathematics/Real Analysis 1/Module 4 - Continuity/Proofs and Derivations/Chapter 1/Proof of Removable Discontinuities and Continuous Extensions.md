---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $a \in E \cap E'$. Suppose that the functional limit of $f$ as $x$ approaches $a$ exists finitely:
$$
\begin{gather}
\lim_{E \ni x \to a} f(x) = L \in \mathbb{R} \tag{1}
\end{gather}
$$
where $L \neq f(a)$. Let $\overline{f}: E \to \mathbb{R}$ denote the modified function defined by:
$$
\begin{gather}
\overline{f}(x) := \begin{cases} f(x), & x \in E \setminus \{a\} \\[2mm] L, & x = a \end{cases} \tag{2}
\end{gather}
$$

By the [[Proof of the Commutation of Continuous Mappings with Accumulation Limits]], because $a$ is an accumulation point of the domain ($a \in E \cap E'$), the function $\overline{f}$ is continuous at $a$ if and only if the functional limit of $\overline{f}$ exists and coincides with $\overline{f}(a)$:
$$
\begin{gather}
\lim_{E \ni x \to a} \overline{f}(x) = \overline{f}(a) \tag{3}
\end{gather}
$$

Evaluating $\overline{f}$ at $x = a$ directly from the assignment in step 2 gives:
$$
\begin{gather}
\overline{f}(a) = L \tag{4}
\end{gather}
$$

Now consider the functional limit of $\overline{f}$ as $x \to a$. The evaluation of the limit $\lim_{E \ni x \to a} \overline{f}(x)$ depends solely on the values of the function on the punctured domain $E \setminus \{a\}$. By step 2, for all $x \in E \setminus \{a\}$:
$$
\begin{gather}
\overline{f}(x) = f(x) \tag{5}
\end{gather}
$$

By the [[Proof of the Punctured Neighborhood Identity Principle]], two functions that agree identically on a punctured neighborhood of an accumulation point possess identical limits. Combining step 1 and step 5 yields:
$$
\begin{gather}
\lim_{E \ni x \to a} \overline{f}(x) = \lim_{E \ni x \to a} f(x) = L \tag{6}
\end{gather}
$$

Comparing step 4 and step 6 establishes the limit identity:
$$
\begin{gather}
\lim_{E \ni x \to a} \overline{f}(x) = \overline{f}(a) \tag{7}
\end{gather}
$$

This equality can also be verified directly through the metric criterion. Let an arbitrary error tolerance $\varepsilon > 0$ be given. 

By step 1, there exists a distance $\delta > 0$ such that for all $x \in E$:
$$
\begin{gather}
0 < |x - a| < \delta \implies |f(x) - L| < \varepsilon \tag{8}
\end{gather}
$$

Let $x \in E$ satisfy $|x - a| < \delta$:
* If $x \neq a$, then $0 < |x - a| < \delta$. Because $\overline{f}(x) = f(x)$ and $\overline{f}(a) = L$, applying step 8 yields:
$$
\begin{gather}
|\overline{f}(x) - \overline{f}(a)| = |f(x) - L| < \varepsilon \tag{9}
\end{gather}
$$
* If $x = a$, then $|\overline{f}(x) - \overline{f}(a)| = |\overline{f}(a) - \overline{f}(a)| = 0 < \varepsilon$.

In both cases, $|x - a| < \delta$ guarantees that $|\overline{f}(x) - \overline{f}(a)| < \varepsilon$ for all $x \in E$. 

Consequently, $\overline{f}$ is continuous at $a$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$