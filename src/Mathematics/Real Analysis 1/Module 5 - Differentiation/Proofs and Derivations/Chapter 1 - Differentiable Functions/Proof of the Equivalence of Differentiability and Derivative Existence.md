---
dg-publish: true
---
Let $E \subseteq \mathbb{R}$, let $f: E \to \mathbb{R}$, and let $x_0 \in E \cap E'$. 

Because $x_0$ is an accumulation point of $E$, the origin $0$ is an accumulation point of the shifted set of increments $E - x_0 := \{h \in \mathbb{R} \mid x_0 + h \in E\}$. 

**Necessity (Assertion 1 implies Assertion 2):**
Assume that assertion 1 holds: the function $f$ is differentiable at the point $x_0$ with differential $df(x_0)(h) = A(x_0)h$ for some real scalar $A(x_0) \in \mathbb{R}$.

By the definition of pointwise differentiability, the functional increment $\Delta f(x_0; h) := f(x_0 + h) - f(x_0)$ admits the representation:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A(x_0) h + \alpha(x_0; h) \tag{1}
\end{gather}
$$
for all $h \in E - x_0$, where the remainder term $\alpha(x_0; h)$ satisfies:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(x_0; h)}{h} = 0 \tag{2}
\end{gather}
$$

For any non-zero displacement $h \in (E - x_0) \setminus \{0\}$, dividing step 1 by $h$ produces:
$$
\begin{gather}
\frac{f(x_0 + h) - f(x_0)}{h} = A(x_0) + \frac{\alpha(x_0; h)}{h} \tag{3}
\end{gather}
$$

Taking the limit as $h \to 0$ with $x_0 + h \in E$ on both sides of step 3 and invoking the algebraic limit theorem gives:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{f(x_0 + h) - f(x_0)}{h} = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \left( A(x_0) + \frac{\alpha(x_0; h)}{h} \right) = A(x_0) + \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(x_0; h)}{h} \tag{4}
\end{gather}
$$

Substituting the asymptotic condition of step 2 into step 4 yields:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{f(x_0 + h) - f(x_0)}{h} = A(x_0) + 0 = A(x_0) \tag{5}
\end{gather}
$$

By definition, the limit of the difference quotient is the derivative $f'(x_0)$. Step 5 demonstrates that this limit exists as a finite real number, which establishes assertion 2, while simultaneously demonstrating that:
$$
\begin{gather}
f'(x_0) = A(x_0) \tag{6}
\end{gather}
$$

**Sufficiency (Assertion 2 implies Assertion 1):**
Conversely, assume that assertion 2 holds: the finite derivative $f'(x_0) \in \mathbb{R}$ exists as a real limit:
$$
\begin{gather}
f'(x_0) = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{f(x_0 + h) - f(x_0)}{h} \tag{7}
\end{gather}
$$

Define the candidate scalar coefficient by:
$$
\begin{gather}
A(x_0) := f'(x_0) \in \mathbb{R} \tag{8}
\end{gather}
$$
and for each displacement $h \in E - x_0$, define the auxiliary remainder function:
$$
\begin{gather}
\alpha(x_0; h) := f(x_0 + h) - f(x_0) - A(x_0) h \tag{9}
\end{gather}
$$

Rearranging the terms in step 9 immediately produces the linear decomposition:
$$
\begin{gather}
f(x_0 + h) - f(x_0) = A(x_0) h + \alpha(x_0; h) \tag{10}
\end{gather}
$$

To confirm that $f$ is differentiable at $x_0$ with differential $df(x_0)(h) = A(x_0)h$, it remains to verify that $\alpha(x_0; h) = o(h)$ as $h \to 0$. For any $h \in (E - x_0) \setminus \{0\}$, dividing step 9 by $h$ yields:
$$
\begin{gather}
\frac{\alpha(x_0; h)}{h} = \frac{f(x_0 + h) - f(x_0)}{h} - A(x_0) \tag{11}
\end{gather}
$$

Evaluating the limit as $h \to 0$ with $x_0 + h \in E$ across step 11 and applying step 7 and step 8 yields:
$$
\begin{gather}
\lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{\alpha(x_0; h)}{h} = \lim_{\substack{h \to 0 \\ x_0 + h \in E}} \frac{f(x_0 + h) - f(x_0)}{h} - A(x_0) = f'(x_0) - A(x_0) = f'(x_0) - f'(x_0) = 0 \tag{12}
\end{gather}
$$

Step 12 confirms that the remainder $\alpha(x_0; h)$ is of order $o(h)$. Thus, the function $f$ is differentiable at $x_0$ with linear coefficient $A(x_0) = f'(x_0)$. 

Because the differential of the identity function satisfies $dx(h) = h$, the linear functional identity:
$$
\begin{gather}
df(x_0)(h) = A(x_0) h = f'(x_0) h = f'(x_0) dx(h) \tag{13}
\end{gather}
$$
holds for all $h \in \mathbb{R}$, which establishes the operational relationship:
$$
\begin{gather}
df(x_0) = f'(x_0) dx \tag{14}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$