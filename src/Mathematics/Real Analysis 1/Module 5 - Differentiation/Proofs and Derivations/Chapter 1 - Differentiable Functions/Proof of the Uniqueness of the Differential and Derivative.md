---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $x_0 \in E \cap E'$. 

Assume that $f$ is differentiable at the point $x_0$. By definition, there exists a real constant $A \in \mathbb{R}$ such that for every displacement $h \in E - x_0 := \{h \in \mathbb{R} \mid x_0 + h \in E\}$, the functional increment admits the decomposition:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A h + \alpha(h) \tag{1}
\end{gather}
$$
where the remainder term $\alpha(h)$ satisfies the asymptotic condition:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(h)}{h} = 0 \tag{2}
\end{gather}
$$
The linear functional $df(x_0): \mathbb{R} \to \mathbb{R}$ is defined by $df(x_0)(h) := A h$.

Suppose there exist two linear functionals $df(x_0)_1, df(x_0)_2 \in \mathcal{L}(\mathbb{R}, \mathbb{R})$ satisfying the definition of the differential at $x_0$. Because every linear functional on $\mathbb{R}$ is uniquely represented by multiplication by a real scalar, there exist constants $A_1, A_2 \in \mathbb{R}$ and corresponding remainder functions $\alpha_1(h), \alpha_2(h)$ defined on $E - x_0$ such that:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A_1 h + \alpha_1(h) \quad \text{with} \quad \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha_1(h)}{h} = 0 \tag{3}
\end{gather}
$$
and
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A_2 h + \alpha_2(h) \quad \text{with} \quad \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha_2(h)}{h} = 0 \tag{4}
\end{gather}
$$

Subtracting the identity of step 4 from the identity of step 3 yields, for every $h \in E - x_0$:
$$
\begin{gather}
(A_1 - A_2) h + \big(\alpha_1(h) - \alpha_2(h)\big) = 0 \tag{5}
\end{gather}
$$

For any non-zero displacement $h \in (E - x_0) \setminus \{0\}$, dividing step 5 by $h$ isolates the scalar difference:
$$
\begin{gather}
A_1 - A_2 = \frac{\alpha_2(h) - \alpha_1(h)}{h} = \frac{\alpha_2(h)}{h} - \frac{\alpha_1(h)}{h} \tag{6}
\end{gather}
$$

Because $x_0$ is an accumulation point of $E$, the value $0$ is an accumulation point of the translated domain $E - x_0$. Taking the limit as $h \to 0$ with $x_0 + h \in E$ on both sides of step 6 and applying the algebraic limit theorem yields:
$$
\begin{gather}
A_1 - A_2 = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \left( \frac{\alpha_2(h)}{h} - \frac{\alpha_1(h)}{h} \right) = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha_2(h)}{h} - \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha_1(h)}{h} = 0 - 0 = 0 \tag{7}
\end{gather}
$$

From step 7, it follows that:
$$
\begin{gather}
A_1 = A_2 \tag{8}
\end{gather}
$$

Because a linear functional $L: \mathbb{R} \to \mathbb{R}$ is completely determined by its evaluation on the unit displacement $h = 1$, namely $L(h) = L(1)h$, and $df(x_0)_1(1) = A_1 = A_2 = df(x_0)_2(1)$, the linear functional $df(x_0)$ is uniquely determined.

Furthermore, the derivative $f'(x_0)$ is defined as the limit of the difference quotient:
$$
\begin{gather}
f'(x_0) := \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{f(x_0 + h) - f(x_0)}{h} \tag{9}
\end{gather}
$$
Because the metric space $\mathbb{R}$ is Hausdorff, limits of functions at accumulation points are unique whenever they exist. Moreover, solving step 1 for the difference quotient reveals:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} = A + \frac{\alpha(h)}{h} \tag{10}
\end{gather}
$$
Taking the limit of step 10 as $h \to 0$ yields $f'(x_0) = A$. Because the scalar coefficient $A$ is uniquely determined by step 8, the derivative $f'(x_0)$ is likewise unique.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$