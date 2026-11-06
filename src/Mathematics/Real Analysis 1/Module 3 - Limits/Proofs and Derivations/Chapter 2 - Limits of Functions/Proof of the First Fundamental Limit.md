---
dg-publish: true
---
Let $S^1 := \{(u, v) \in \mathbb{R}^2 \mid u^2 + v^2 = 1\}$ be the unit circle in the Euclidean plane centered at the origin $O(0, 0)$. Let $A = (1, 0)$ denote the initial reference point on the Cartesian $u$-axis. For any angle $x \in \mathbb{R}$, wrapping an oriented path of arc length $|x|$ along $S^1$ from $A$ defines the terminal point $P(x) = (\cos x, \sin x)$, with $\tan x = \frac{\sin x}{\cos x}$ defined on $\{x \in \mathbb{R} \mid \cos x \neq 0\}$, as constructed in the [[Proof of Fundamental Geometric Trigonometric Identities]].

Let $x \in \left(0, \frac{\pi}{2}\right)$ be an arbitrary angle in radians. The terminal point $P = (\cos x, \sin x)$ lies in the first open quadrant of $S^1$. The ray originating from $O$ passing through $P$ intersects the vertical tangent line $u = 1$ to the circle at $A(1, 0)$ at the point:
$$
\begin{gather}
T := (1, \tan x) \tag{1}
\end{gather}
$$
because the collinearity of $O(0,0)$, $P(\cos x, \sin x)$, and $T(1, v)$ requires $\frac{v}{1} = \frac{\sin x}{\cos x} = \tan x$.

Consider the three nested geometric figures formed on the Cartesian plane:
1. The inscribed triangle $\triangle OAP$, possessing base $OA = 1$ and vertical altitude $\sin x$:
$$
\begin{gather}
\text{Area}(\triangle OAP) = \frac{1}{2} \cdot OA \cdot \sin x = \frac{1}{2}\sin x \tag{2}
\end{gather}
$$
2. The circular sector $OAP$ of the unit circle, subtending an arc of length $x$ with radius $r = 1$:
$$
\begin{gather}
\text{Area}(\text{sector } OAP) = \frac{1}{2} r^2 x = \frac{1}{2} x \tag{3}
\end{gather}
$$
3. The circumscribed right-angled triangle $\triangle OAT$, possessing base $OA = 1$ and vertical altitude $AT = \tan x$:
$$
\begin{gather}
\text{Area}(\triangle OAT) = \frac{1}{2} \cdot OA \cdot AT = \frac{1}{2} \tan x \tag{4}
\end{gather}
$$
Because the triangle $\triangle OAP$ is strictly contained within the circular sector $OAP$, and the circular sector $OAP$ is strictly contained within the right-angled triangle $\triangle OAT$, the monotonicity of the Euclidean planar area measure dictates the strict double inequality:
$$
\begin{gather}
\text{Area}(\triangle OAP) < \text{Area}(\text{sector } OAP) < \text{Area}(\triangle OAT) \tag{5}
\end{gather}
$$
Substituting step 2, step 3, and step 4 into step 5 yields:
$$
\begin{gather}
\frac{1}{2}\sin x < \frac{1}{2}x < \frac{1}{2}\tan x \tag{6}
\end{gather}
$$
Multiplying step 6 across by $2$ and noting that $\sin x > 0$ for all $x \in \left(0, \frac{\pi}{2}\right)$ yields:
$$
\begin{gather}
0 < \sin x < x < \tan x \tag{7}
\end{gather}
$$
Because $\sin x > 0$ on $\left(0, \frac{\pi}{2}\right)$, dividing step 7 by $\sin x$ preserves the strict ordering:
$$
\begin{gather}
1 < \frac{x}{\sin x} < \frac{\tan x}{\sin x} = \frac{1}{\cos x} \tag{8}
\end{gather}
$$
Because all three terms in step 8 are strictly positive real numbers, inverting each term reverses the directional inequalities:
$$
\begin{gather}
\cos x < \frac{\sin x}{x} < 1 \quad \forall x \in \left(0, \frac{\pi}{2}\right) \tag{9}
\end{gather}
$$
Now let $x \in \left(-\frac{\pi}{2}, 0\right)$, which implies that $-x \in \left(0, \frac{\pi}{2}\right)$. By Theorem 3 of the [[Proof of Fundamental Geometric Trigonometric Identities]], the cosine function is even ($\cos(-x) = \cos x$) and the sine function is odd ($\sin(-x) = -\sin x$). Evaluating the ratio at $-x$ gives:
$$
\begin{gather}
\frac{\sin(-x)}{-x} = \frac{-\sin x}{-x} = \frac{\sin x}{x} \tag{10}
\end{gather}
$$
Applying the inequality of step 9 to the positive angle $-x \in \left(0, \frac{\pi}{2}\right)$ and substituting the parity relations produces:
$$
\begin{gather}
\cos(-x) < \frac{\sin(-x)}{-x} < 1 \implies \cos x < \frac{\sin x}{x} < 1 \quad \forall x \in \left(-\frac{\pi}{2}, 0\right) \tag{11}
\end{gather}
$$
Combining step 9 and step 11 establishes that the bounding inequality holds across the entire punctured symmetric neighborhood $\mathring{U}_{\pi/2}(0) = \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \setminus \{0\}$:
$$
\begin{gather}
\cos x < \frac{\sin x}{x} < 1 \quad \forall x \in \left(-\frac{\pi}{2}, \frac{\pi}{2}\right) \setminus \{0\} \tag{12}
\end{gather}
$$
To evaluate the limit of the lower bounding function $\cos x$ as $x \to 0$, consider the Euclidean distance squared between $A(1, 0)$ and $P(\cos x, \sin x)$. By the Pythagorean distance formula:
$$
\begin{gather}
|AP|^2 = (1 - \cos x)^2 + \sin^2 x = 1 - 2\cos x + (\cos^2 x + \sin^2 x) = 2 - 2\cos x = 2(1 - \cos x) \tag{13}
\end{gather}
$$
Simultaneously, the chord $AP$ forms the base of an isosceles triangle with legs of unit length and vertex angle $|x|$. Bisecting this angle produces two right triangles with opposite sides of length $\sin\left|\frac{x}{2}\right|$, which establishes the chord length:
$$
\begin{gather}
|AP| = 2\sin\left|\frac{x}{2}\right| \implies |AP|^2 = 4\sin^2\left(\frac{x}{2}\right) \tag{14}
\end{gather}
$$
Equating step 13 and step 14 yields the half-angle identity:
$$
\begin{gather}
1 - \cos x = 2\sin^2\left(\frac{x}{2}\right) \tag{15}
\end{gather}
$$
For any $x \in \mathring{U}_{\pi/2}(0)$, the halved argument satisfies $0 < \left|\frac{x}{2}\right| < \frac{\pi}{4} < \frac{\pi}{2}$. Applying the strict upper bound of step 7 to $\left|\frac{x}{2}\right|$ demonstrates that $0 < \sin\left|\frac{x}{2}\right| < \left|\frac{x}{2}\right|$, which implies:
$$
\begin{gather}
\sin^2\left(\frac{x}{2}\right) < \frac{x^2}{4} \tag{16}
\end{gather}
$$
Substituting step 16 into step 15 yields:
$$
\begin{gather}
0 < 1 - \cos x < 2 \cdot \frac{x^2}{4} = \frac{x^2}{2} \tag{17}
\end{gather}
$$
Rearranging step 17 and incorporating the universal bound $\cos x \le 1$ from the unit circle equation provides the quadratic squeeze for all $x \in \mathring{U}_{\pi/2}(0)$:
$$
\begin{gather}
1 - \frac{x^2}{2} < \cos x \le 1 \tag{18}
\end{gather}
$$
By the [[Proof of the Direct Substitution Property for Algebraic Functions]], the limit of the polynomial lower bound is:
$$
\begin{gather}
\lim_{x \to 0} \left(1 - \frac{x^2}{2}\right) = 1 - 0 = 1 \tag{19}
\end{gather}
$$
Because $\lim_{x \to 0} 1 = 1$, applying Theorem 3 of the [[Proof of Passage to Limit and Inequalities]] (The Squeeze Theorem) to step 18 proves that:
$$
\begin{gather}
\lim_{x \to 0} \cos x = 1 \tag{20}
\end{gather}
$$
Returning to the fundamental bounding inequality in step 12:
$$
\begin{gather}
\cos x < \frac{\sin x}{x} < 1 \quad \forall x \in \mathring{U}_{\pi/2}(0) \tag{21}
\end{gather}
$$
By step 20, $\lim_{x \to 0} \cos x = 1$, and the upper bounding constant function satisfies $\lim_{x \to 0} 1 = 1$. Because both outer bounding functions converge to $1$ over the punctured neighborhood base $\mathring{U}_{\pi/2}(0)$, Theorem 3 of the [[Proof of Passage to Limit and Inequalities]] (The Squeeze Theorem) establishes that:
$$
\begin{gather}
\lim_{x \to 0} \frac{\sin x}{x} = 1 \tag{22}
\end{gather}
$$
By virtue of the [[Proof of the Equivalence of Two-Sided and One-Sided Limits]], the one-sided directional limits exist and agree identically:
$$
\begin{gather}
\lim_{x \to 0^+} \frac{\sin x}{x} = \lim_{x \to 0^-} \frac{\sin x}{x} = 1 \tag{23}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
