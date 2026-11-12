---
dg-publish: true
---
Let $\alpha, \beta \in \mathbb{R}$ be arbitrary real numbers, and let the real trigonometric functions $\cos : \mathbb{R} \to \mathbb{R}$ and $\sin : \mathbb{R} \to \mathbb{R}$ be defined by their relations to the complex exponential mapping $\exp : \mathbb{C} \to \mathbb{C}^\times$ through [[Proof of Euler's Formula and Group Homomorphism of Exp|Euler's formula]]:
$$
\begin{gather}
\exp(i \theta) = \cos(\theta) + i \sin(\theta) \tag{1}
\end{gather}
$$
for all $\theta \in \mathbb{R}$, satisfying the group homomorphism property:
$$
\begin{gather}
\exp(i(\alpha + \beta)) = \exp(i \alpha) \exp(i \beta) \tag{2}
\end{gather}
$$

---
# Proposition 1
For any real numbers $\alpha, \beta \in \mathbb{R}$, the addition formulas for cosine and sine hold:
$$
\begin{gather}
\cos(\alpha + \beta) = \cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta) \tag{3}
\end{gather}
$$
and
$$
\begin{gather}
\sin(\alpha + \beta) = \sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta) \tag{4}
\end{gather}
$$

Applying Euler's formula of step 1 to the sum $\theta = \alpha + \beta$ gives:
$$
\begin{gather}
\exp(i(\alpha + \beta)) = \cos(\alpha + \beta) + i \sin(\alpha + \beta) \tag{5}
\end{gather}
$$
On the other hand, applying the group homomorphism property of step 2 to the left side of step 5 gives:
$$
\begin{gather}
\exp(i(\alpha + \beta)) = \exp(i \alpha) \exp(i \beta) \tag{6}
\end{gather}
$$
Applying Euler's formula individually to each factor on the right side of step 6 yields:
$$
\begin{gather}
\exp(i \alpha) = \cos(\alpha) + i \sin(\alpha) \tag{7}
\end{gather}
$$
and
$$
\begin{gather}
\exp(i \beta) = \cos(\beta) + i \sin(\beta) \tag{8}
\end{gather}
$$
Multiplying the expressions in step 7 and step 8 according to the field multiplication rules of $\mathbb{C}$:
$$
\begin{gather}
\exp(i \alpha) \exp(i \beta) = \big(\cos(\alpha) + i \sin(\alpha)\big)\big(\cos(\beta) + i \sin(\beta)\big) \tag{9}
\end{gather}
$$
Expanding the product on the right side of step 9:
$$
\begin{gather}
\big(\cos(\alpha)\cos(\beta) + i^2 \sin(\alpha)\sin(\beta)\big) + i \big(\sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta)\big) \tag{10}
\end{gather}
$$
Because $i^2 = -1$, step 10 simplifies to:
$$
\begin{gather}
\big(\cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta)\big) + i \big(\sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta)\big) \tag{11}
\end{gather}
$$
Equating step 5 and step 11:
$$
\begin{gather}
\cos(\alpha + \beta) + i \sin(\alpha + \beta) = \big(\cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta)\big) + i \big(\sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta)\big) \tag{12}
\end{gather}
$$
Because two complex numbers are equal if and only if their real and imaginary parts are independently equal, extracting the real part of both sides of step 12 yields:
$$
\begin{gather}
\cos(\alpha + \beta) = \cos(\alpha)\cos(\beta) - \sin(\alpha)\sin(\beta) \tag{13}
\end{gather}
$$
and extracting the imaginary part yields:
$$
\begin{gather}
\sin(\alpha + \beta) = \sin(\alpha)\cos(\beta) + \cos(\alpha)\sin(\beta) \tag{14}
\end{gather}
$$

---
# Proposition 2
For any real numbers $\alpha, \beta \in \mathbb{R}$, the subtraction formulas hold:
$$
\begin{gather}
\cos(\alpha - \beta) = \cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta) \tag{15}
\end{gather}
$$
and
$$
\begin{gather}
\sin(\alpha - \beta) = \sin(\alpha)\cos(\beta) - \cos(\alpha)\sin(\beta) \tag{16}
\end{gather}
$$
Moreover, the Pythagorean identity $\cos^2(\alpha) + \sin^2(\alpha) = 1$ holds for all $\alpha \in \mathbb{R}$.

Recall from the power series definitions that $\cos$ is an even function and $\sin$ is an odd function:
$$
\begin{gather}
\cos(-\beta) = \cos(\beta) \quad \text{and} \quad \sin(-\beta) = -\sin(\beta) \tag{17}
\end{gather}
$$
Substituting $-\beta$ in place of $\beta$ in step 13 and step 14 yields:
$$
\begin{gather}
\cos(\alpha - \beta) = \cos(\alpha)\cos(-\beta) - \sin(\alpha)\sin(-\beta) = \cos(\alpha)\cos(\beta) + \sin(\alpha)\sin(\beta) \tag{18}
\end{gather}
$$
and
$$
\begin{gather}
\sin(\alpha - \beta) = \sin(\alpha)\cos(-\beta) + \cos(\alpha)\sin(-\beta) = \sin(\alpha)\cos(\beta) - \cos(\alpha)\sin(\beta) \tag{19}
\end{gather}
$$
Setting $\beta = \alpha$ in step 18:
$$
\begin{gather}
\cos(\alpha - \alpha) = \cos(0) = \cos^2(\alpha) + \sin^2(\alpha) \tag{20}
\end{gather}
$$
Since $\cos(0) = 1$, step 20 establishes:
$$
\begin{gather}
\cos^2(\alpha) + \sin^2(\alpha) = 1 \tag{21}
\end{gather}
$$
for every $\alpha \in \mathbb{R}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$