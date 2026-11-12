---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an interval, and let $u, v: I \to \mathbb{R}$ be two continuously differentiable functions on $I$, meaning $u, v \in C^1(I)$.

By the definition of continuous differentiability, the derivatives $u': I \to \mathbb{R}$ and $v': I \to \mathbb{R}$ exist and are continuous functions on $I$.

---
# Proposition 1 
Suppose that the product function $u'(x) v(x)$ admits a primitive $W: I \to \mathbb{R}$ on $I$, so that:
$$
\begin{gather}
W'(x) = u'(x) v(x) \quad \forall x \in I \tag{1}
\end{gather}
$$
In indefinite integral notation, this is expressed as:
$$
\begin{gather}
W(x) = \int u'(x) v(x) \, dx \tag{2}
\end{gather}
$$

Consider the product of the two functions $P: I \to \mathbb{R}$ defined by:
$$
\begin{gather}
P(x) := u(x) v(x), \quad \forall x \in I \tag{3}
\end{gather}
$$

Because $u$ and $v$ are differentiable on $I$, the [[Proof of The Leibniz Product Rule|Product Rule of Differential Calculus]] implies that $P$ is differentiable at every point $x \in I$, with derivative:
$$
\begin{gather}
P'(x) = \frac{d}{dx} \big( u(x) v(x) \big) = u'(x) v(x) + u(x) v'(x) \quad \forall x \in I \tag{4}
\end{gather}
$$

Rearranging the terms in step 4 to isolate the term $u(x) v'(x)$ yields:
$$
\begin{gather}
u(x) v'(x) = \frac{d}{dx} \big( u(x) v(x) \big) - u'(x) v(x) \tag{5}
\end{gather}
$$

Now define the candidate primitive function $Q: I \to \mathbb{R}$ by:
$$
\begin{gather}
Q(x) := u(x) v(x) - W(x) \tag{6}
\end{gather}
$$

Because $u(x)v(x)$ and $W(x)$ are differentiable on $I$, the linearity of differentiation ensures that $Q$ is differentiable on $I$. Computing its derivative gives:
$$
\begin{gather}
Q'(x) = \frac{d}{dx}\big(u(x)v(x)\big) - W'(x) \tag{7}
\end{gather}
$$

Substituting step 1 into step 7 yields:
$$
\begin{gather}
Q'(x) = \big( u'(x) v(x) + u(x) v'(x) \big) - u'(x) v(x) = u(x) v'(x) \quad \forall x \in I \tag{8}
\end{gather}
$$

Step 8 demonstrates that $Q$ is an antiderivative of the product $u(x) v'(x)$ on $I$. 

Substituting step 2 and step 6 into this result establishes the integration by parts identity:
$$
\begin{gather}
\int u(x) v'(x) \, dx = u(x) v(x) - \int u'(x) v(x) \, dx \tag{9}
\end{gather}
$$
meaning that the set of primitives on the left corresponds precisely to the difference between the function $u(x)v(x)$ and the set of primitives on the right.

---
# Proposition 2
In terms of differential 1-forms, the total differentials of $u$ and $v$ are:
$$
\begin{gather}
du = u'(x) \, dx \quad \text{and} \quad dv = v'(x) \, dx \tag{10}
\end{gather}
$$
The product rule in differential notation takes the symmetric form:
$$
\begin{gather}
d(uv) = u \, dv + v \, du \tag{11}
\end{gather}
$$
Rearranging and integrating both sides yields:
$$
\begin{gather}
\int u \, dv = uv - \int v \, du \tag{12}
\end{gather}
$$
which expresses the integration by parts rule in coordinate-free differential form.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
