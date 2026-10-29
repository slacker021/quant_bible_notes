---
dg-publish: true
---
Let $\mathcal{B}$ be a base in $X$, and let $f, g: X \to \mathbb{R}$ satisfy:
$$
\begin{gather}
\lim_{\mathcal{B}} f(x) = A \quad \text{and} \quad \lim_{\mathcal{B}} g(x) = B \tag{1}
\end{gather}
$$
By the infinitesimal deviation representation, express $f$ and $g$ as:
$$
\begin{gather}
f(x) = A + \alpha(x) \quad \text{and} \quad g(x) = B + \beta(x) \tag{2}
\end{gather}
$$
where $\lim_{\mathcal{B}} \alpha(x) = 0$ and $\lim_{\mathcal{B}} \beta(x) = 0$.

# Theorem 1
The algebraic sum expands as:
$$
\begin{gather}
(f + g)(x) = (A + \alpha(x)) + (B + \beta(x)) = (A + B) + (\alpha(x) + \beta(x)) \tag{3}
\end{gather}
$$
By Proposition 1 of the [[Proof of Operations on Infinitesimals]], the sum $(\alpha + \beta)(x)$ is an infinitesimal over $\mathcal{B}$. Taking the limit over $\mathcal{B}$ in step 3 yields:
$$
\begin{gather}
\lim_{\mathcal{B}} (f + g)(x) = A + B + \lim_{\mathcal{B}} (\alpha(x) + \beta(x)) = A + B + 0 = A + B \tag{4}
\end{gather}
$$

---
# Theorem 2
The functional product expands as:
$$
\begin{gather}
(f \cdot g)(x) = (A + \alpha(x))(B + \beta(x)) = A \cdot B + A\beta(x) + B\alpha(x) + \alpha(x)\beta(x) \tag{5}
\end{gather}
$$
Because $A$ and $B$ are constants, the functions $A\beta(x)$ and $B\alpha(x)$ are infinitesimals by Proposition 3 of the [[Proof of Operations on Infinitesimals]]. Furthermore, $\alpha(x)\beta(x)$ is an infinitesimal by Proposition 2. 

Because the sum of infinitesimals is an infinitesimal, the composite error:
$$
\begin{gather}
\gamma(x) := A\beta(x) + B\alpha(x) + \alpha(x)\beta(x) \tag{6}
\end{gather}
$$
satisfies $\lim_{\mathcal{B}} \gamma(x) = 0$. Taking the limit over $\mathcal{B}$ in step 5 yields:
$$
\begin{gather}
\lim_{\mathcal{B}} (f \cdot g)(x) = A \cdot B + \lim_{\mathcal{B}} \gamma(x) = A \cdot B \tag{7}
\end{gather}
$$

---
# Theorem 3
Assume $B \neq 0$. It suffices to prove that $\lim_{\mathcal{B}} \frac{1}{g(x)} = \frac{1}{B}$, because the full quotient rule then follows directly from Theorem 2 via $\frac{f}{g} = f \cdot \frac{1}{g}$.

By the [[Proof of Local Sign Preservation]], because $B \neq 0$, there exist an element $B_1 \in \mathcal{B}$ and a positive bound such that:
$$
\begin{gather}
|g(x)| > \frac{|B|}{2} > 0 \iff \frac{1}{|g(x)|} < \frac{2}{|B|} \quad \forall x \in B_1 \tag{8}
\end{gather}
$$
Step 8 proves that $\frac{1}{g(x)}$ is ultimately bounded over $\mathcal{B}$. Now consider the difference:
$$
\begin{gather}
\frac{1}{g(x)} - \frac{1}{B} = \frac{B - g(x)}{B \cdot g(x)} = -\frac{1}{B} \cdot \beta(x) \cdot \frac{1}{g(x)} \tag{9}
\end{gather}
$$
In step 9, $-\frac{1}{B}$ is a constant, $\beta(x)$ is an infinitesimal, and $\frac{1}{g(x)}$ is ultimately bounded. By Proposition 3 of the [[Proof of Operations on Infinitesimals]], their product is an infinitesimal:
$$
\begin{gather}
\lim_{\mathcal{B}} \left(\frac{1}{g(x)} - \frac{1}{B}\right) = 0 \implies \lim_{\mathcal{B}} \frac{1}{g(x)} = \frac{1}{B} \tag{10}
\end{gather}
$$
Applying Theorem 2 to $f(x) \cdot \frac{1}{g(x)}$ concludes the proof:
$$
\begin{gather}
\lim_{\mathcal{B}} \left(\frac{f}{g}\right)(x) = \lim_{\mathcal{B}} \left(f(x) \cdot \frac{1}{g(x)}\right) = A \cdot \frac{1}{B} = \frac{A}{B}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$