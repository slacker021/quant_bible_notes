---
dg-publish: true
---
Let $\Gamma \subset \mathbb{R}^2$ be a smooth plane curve. In an open neighborhood of a point $P \in \Gamma$, let $\Gamma$ be parametrized by a continuously differentiable mapping $\vec{r}: I \to \mathbb{R}^2$ defined on an open interval $I \subseteq \mathbb{R}$ containing $t_0$, such that:
$$
\begin{gather}
\vec{r}(t) = \big(x(t), y(t)\big), \qquad P = \vec{r}(t_0), \qquad \text{and} \qquad \vec{r}\,'(t_0) \neq \vec{0} \tag{1}
\end{gather}
$$

For any non-zero parameter increment $h \neq 0$ with $t_0 + h \in I$, let $Q(h) := \vec{r}(t_0 + h)$ denote a distinct neighboring point on the curve. The secant chord vector connecting $P$ and $Q(h)$, normalized by the increment $h$, is given by:
$$
\begin{gather}
\vec{v}(h) := \frac{\vec{r}(t_0 + h) - \vec{r}(t_0)}{h} \tag{2}
\end{gather}
$$
As $h \to 0$, the chord vector converges in the Euclidean norm topology of $\mathbb{R}^2$ to the tangent vector:
$$
\begin{gather}
\lim_{h \to 0} \vec{v}(h) = \vec{r}\,'(t_0) = \big(x'(t_0), y'(t_0)\big) \tag{3}
\end{gather}
$$
The geometric tangent line $\mathcal{T}_P$ to the curve $\Gamma$ at $P$ is the one-dimensional affine subspace of $\mathbb{R}^2$ spanned by $\vec{r}\,'(t_0)$ and anchored at $P$:
$$
\begin{gather}
\mathcal{T}_P := \big\{ \vec{r}(t_0) + \lambda \vec{r}\,'(t_0) \ \big|\ \lambda \in \mathbb{R} \big\} \tag{4}
\end{gather}
$$

Consider an arbitrary rigid coordinate transformation $\Phi: \mathbb{R}^2 \to \mathbb{R}^2$ composed of an orthogonal rotation (or reflection) and a spatial translation:
$$
\begin{gather}
\Phi(\vec{w}) := \mathbf{R} \vec{w} + \vec{b} \tag{5}
\end{gather}
$$
where $\vec{b} \in \mathbb{R}^2$ is a constant translation vector, and $\mathbf{R} \in \mathrm{O}(2)$ is an orthogonal $2 \times 2$ matrix satisfying:
$$
\begin{gather}
\mathbf{R}^T \mathbf{R} = \mathbf{I} \tag{6}
\end{gather}
$$

Under the transformation $\Phi$, the curve $\Gamma$ maps to the transformed curve $\tilde{\Gamma} := \Phi(\Gamma)$, parametrized by:
$$
\begin{gather}
\tilde{\vec{r}}(t) := \Phi(\vec{r}(t)) = \mathbf{R}\vec{r}(t) + \vec{b} \tag{7}
\end{gather}
$$
The anchor point $P$ transforms to:
$$
\begin{gather}
\tilde{P} := \Phi(P) = \mathbf{R}\vec{r}(t_0) + \vec{b} = \tilde{\vec{r}}(t_0) \tag{8}
\end{gather}
$$

Construct the transformed secant chord vector for the curve $\tilde{\Gamma}$:
$$
\begin{gather}
\tilde{\vec{v}}(h) := \frac{\tilde{\vec{r}}(t_0 + h) - \tilde{\vec{r}}(t_0)}{h} \tag{9}
\end{gather}
$$
Substituting the representation of step 7 into step 9 yields:
$$
\begin{gather}
\tilde{\vec{v}}(h) = \frac{\big(\mathbf{R}\vec{r}(t_0 + h) + \vec{b}\big) - \big(\mathbf{R}\vec{r}(t_0) + \vec{b}\big)}{h} = \frac{\mathbf{R}\big(\vec{r}(t_0 + h) - \vec{r}(t_0)\big)}{h} = \mathbf{R} \vec{v}(h) \tag{10}
\end{gather}
$$

Because the matrix multiplication $\vec{w} \mapsto \mathbf{R}\vec{w}$ is a linear mapping on a finite-dimensional space, it is continuous. Consequently, taking the limit as $h \to 0$ commutes with the action of $\mathbf{R}$:
$$
\begin{gather}
\tilde{\vec{r}}\,'(t_0) = \lim_{h \to 0} \tilde{\vec{v}}(h) = \lim_{h \to 0} \big(\mathbf{R} \vec{v}(h)\big) = \mathbf{R} \left( \lim_{h \to 0} \vec{v}(h) \right) = \mathbf{R} \vec{r}\,'(t_0) \tag{11}
\end{gather}
$$
Because $\mathbf{R}$ is orthogonal, its determinant is $\det(\mathbf{R}) = \pm 1 \neq 0$, which ensures that $\mathbf{R}$ is an isomorphism. Because $\vec{r}\,'(t_0) \neq \vec{0}$, it follows that $\tilde{\vec{r}}\,'(t_0) = \mathbf{R}\vec{r}\,'(t_0) \neq \vec{0}$.

The geometric tangent line to the transformed curve $\tilde{\Gamma}$ at the point $\tilde{P}$ is defined by:
$$
\begin{gather}
\mathcal{T}_{\tilde{P}} := \big\{ \tilde{\vec{r}}(t_0) + \lambda \tilde{\vec{r}}\,'(t_0) \ \big|\ \lambda \in \mathbb{R} \big\} \tag{12}
\end{gather}
$$
Substituting step 8 and step 11 into step 12 yields:
$$
\begin{gather}
\mathcal{T}_{\tilde{P}} = \big\{ (\mathbf{R}\vec{r}(t_0) + \vec{b}) + \lambda \mathbf{R}\vec{r}\,'(t_0) \ \big|\ \lambda \in \mathbb{R} \big\} = \big\{ \mathbf{R}\big(\vec{r}(t_0) + \lambda \vec{r}\,'(t_0)\big) + \vec{b} \ \big|\ \lambda \in \mathbb{R} \big\} \tag{13}
\end{gather}
$$
Comparing step 13 with the definition of the original tangent line $\mathcal{T}_P$ in step 4 demonstrates that:
$$
\begin{gather}
\mathcal{T}_{\tilde{P}} = \Phi(\mathcal{T}_P) \tag{14}
\end{gather}
$$
Step 14 confirms that the tangent line transforms covariantly under the rigid transformation $\Phi$.

To demonstrate that geometric contact of order at least one is preserved, evaluate the Euclidean distance between the curve and its linear approximation. For any increment $h$, the deviation in the transformed coordinates is:
$$
\begin{gather}
\tilde{\vec{\delta}}(h) := \tilde{\vec{r}}(t_0 + h) - \big(\tilde{\vec{r}}(t_0) + h \tilde{\vec{r}}\,'(t_0)\big) \tag{15}
\end{gather}
$$
Substituting step 7, step 8, and step 11 into step 15 gives:
$$
\begin{gather}
\tilde{\vec{\delta}}(h) = \big(\mathbf{R}\vec{r}(t_0 + h) + \vec{b}\big) - \big(\mathbf{R}\vec{r}(t_0) + \vec{b} + h \mathbf{R}\vec{r}\,'(t_0)\big) = \mathbf{R}\big(\vec{r}(t_0 + h) - \vec{r}(t_0) - h \vec{r}\,'(t_0)\big) = \mathbf{R}\vec{\delta}(h) \tag{16}
\end{gather}
$$
where $\vec{\delta}(h) := \vec{r}(t_0 + h) - \vec{r}(t_0) - h\vec{r}\,'(t_0)$ is the deviation vector in the original coordinates.

Because $\mathbf{R}$ is an orthogonal matrix, it preserves the Euclidean norm:
$$
\begin{gather}
\|\mathbf{R}\vec{u}\|^2 = (\mathbf{R}\vec{u})^T (\mathbf{R}\vec{u}) = \vec{u}^T \mathbf{R}^T \mathbf{R} \vec{u} = \vec{u}^T \mathbf{I} \vec{u} = \|\vec{u}\|^2 \implies \|\mathbf{R}\vec{u}\| = \|\vec{u}\| \tag{17}
\end{gather}
$$
Applying step 17 to step 16 yields:
$$
\begin{gather}
\|\tilde{\vec{\delta}}(h)\| = \|\mathbf{R}\vec{\delta}(h)\| = \|\vec{\delta}(h)\| \tag{18}
\end{gather}
$$
Dividing step 18 by $|h| > 0$ and evaluating the limit as $h \to 0$ reveals:
$$
\begin{gather}
\lim_{h \to 0} \frac{\|\tilde{\vec{\delta}}(h)\|}{|h|} = \lim_{h \to 0} \frac{\|\vec{\delta}(h)\|}{|h|} = 0 \tag{19}
\end{gather}
$$
Because the normalized deviation in step 19 collapses to zero, the transformed line achieves contact of order at least one with the transformed curve, preserving the geometric contact property independently of the chosen Cartesian frame.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$