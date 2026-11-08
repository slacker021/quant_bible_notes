---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $x_0 \in E \cap E'$.

Assume that $f$ is differentiable at the point $x_0$. 

By the [[Proof of the Equivalence of Differentiability and Derivative Existence|Equivalence of Differentiability and Derivative Existence]], the derivative $f'(x_0) \in \mathbb{R}$ exists as a finite real limit, and the functional increment $\Delta f(x_0; h) := f(x_0 + h) - f(x_0)$ admits the linear decomposition:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = f'(x_0) h + \alpha(x_0; h) \tag{1}
\end{gather}
$$
for all increments $h \in E - x_0 := \{h \in \mathbb{R} \mid x_0 + h \in E\}$, where the remainder term satisfies:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(x_0; h)}{h} = 0 \tag{2}
\end{gather}
$$

To prove that $f$ is continuous at $x_0$, it suffices to demonstrate that the limit of the functional variation collapses to zero as the displacement $h$ tends to zero:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \big(f(x_0 + h) - f(x_0)\big) = 0 \iff \lim_{\substack{h \to 0 \\ x_0 + h \in E}} f(x_0 + h) = f(x_0) \tag{3}
\end{gather}
$$

Evaluating the limit of the linear term in step 1 using the standard limit properties gives:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \big(f'(x_0) h\big) = f'(x_0) \cdot 0 = 0 \tag{4}
\end{gather}
$$

Furthermore, rewriting the remainder term for non-zero displacements $h \neq 0$ as:
$$
\begin{gather}
\alpha(x_0; h) = \frac{\alpha(x_0; h)}{h} \cdot h \tag{5}
\end{gather}
$$
and evaluating its limit by applying the product rule for limits and the condition of step 2 yields:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \alpha(x_0; h) = \left(\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(x_0; h)}{h}\right) \cdot \left(\lim_{\substack{h \to 0 \\ x_0 + h \in E}} h\right) = 0 \cdot 0 = 0 \tag{6}
\end{gather}
$$

Taking the limit of both sides of step 1 as $h \to 0$ with $x_0 + h \in E$ and applying the sum rule for limits in conjunction with step 4 and step 6 yields:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \big(f(x_0 + h) - f(x_0)\big) = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \big(f'(x_0) h\big) + \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \alpha(x_0; h) = 0 + 0 = 0 \tag{7}
\end{gather}
$$

Setting $x := x_0 + h \in E$, step 7 is equivalent to:
$$
\begin{gather}
\lim_{E \ni x \to x_0} f(x) = f(x_0) \tag{8}
\end{gather}
$$

Because the limit of $f(x)$ as $x$ approaches $x_0$ within the domain $E$ exists and equals $f(x_0)$, the function $f$ is continuous at $x_0$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$