---
dg-publish: true
---
Let $S^1 := \{(u, v) \in \mathbb{R}^2 \mid u^2 + v^2 = 1\}$ be the unit circle in the Euclidean plane. For any $x \in \mathbb{R}$, let $P(x) = (\cos x, \sin x)$ be the terminal point of an oriented arc of length $|x|$ along $S^1$ initiated from $A = (1, 0)$.

---
# Theorem 1
By definition of the circular trigonometric functions, the point $P(x)$ lies on the unit circle $S^1$ for every $x \in \mathbb{R}$.

Substituting the coordinates $u = \cos x$ and $v = \sin x$ into the defining algebraic equation of $S^1$ yields:
$$
\begin{gather}
u^2 + v^2 = 1 \implies \cos^2 x + \sin^2 x = 1 \quad \forall x \in \mathbb{R} \tag{1}
\end{gather}
$$
---
# Theorem 2
Let $x \in \mathbb{R} \setminus \left\{\frac{\pi}{2} + k\pi \ \middle|\ k \in \mathbb{Z}\right\}$, so that $\cos x \neq 0$.

Dividing both sides of the Pythagorean identity in step 1 by the non-zero quantity $\cos^2 x > 0$ yields:
$$
\begin{gather}
\frac{\cos^2 x}{\cos^2 x} + \frac{\sin^2 x}{\cos^2 x} = \frac{1}{\cos^2 x} \tag{2}
\end{gather}
$$
By definition of the tangent and secant functions, $\tan x = \frac{\sin x}{\cos x}$ and $\sec x = \frac{1}{\cos x}$. Substituting these into step 2 gives:
$$
\begin{gather}
1 + \tan^2 x = \sec^2 x \tag{3}
\end{gather}
$$
---
# Theorem 3
Let $x \in \mathbb{R}$. By construction, wrapping an arc of length $|x|$ in the clockwise direction (corresponding to $-x$) produces a point $P(-x) = (\cos(-x), \sin(-x))$ that is the geometric reflection of $P(x) = (\cos x, \sin x)$ across the horizontal Cartesian $u$-axis.

Reflecting an arbitrary point $(u, v)$ across the $u$-axis preserves its horizontal coordinate while negating its vertical coordinate:
$$
\begin{gather}
(u, -v) = (\cos x, -\sin x) \tag{4}
\end{gather}
$$
Equating the coordinates of $P(-x)$ with step 4 yields the parity identities:
$$
\begin{gather}
\cos(-x) = \cos x \quad \text{and} \quad \sin(-x) = -\sin x \tag{5}
\end{gather}
$$
For all $x$ where $\cos x \neq 0$, the quotient definition of the tangent function yields:
$$
\begin{gather}
\tan(-x) = \frac{\sin(-x)}{\cos(-x)} = \frac{-\sin x}{\cos x} = -\tan x \tag{6}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
