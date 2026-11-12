---
dg-publish: true
---
Let $\Omega \subseteq \mathbb{C}$ be a connected open domain in the complex plane, and let $f, g: \Omega \to \mathbb{C}$ be analytic functions on $\Omega$ (meaning that around every point $w \in \Omega$, both functions admit convergent power series expansions). 

Suppose the coincidence set:
$$
\begin{gather}
E := \{z \in \Omega : f(z) = g(z)\} \tag{1}
\end{gather}
$$
contains an accumulation point $z_0 \in \Omega$ (that is, $z_0 \in E \cap E'$).

Define the difference function $h: \Omega \to \mathbb{C}$ by:
$$
\begin{gather}
h(z) := f(z) - g(z) \tag{2}
\end{gather}
$$
Then $h$ is analytic on $\Omega$, and the zero set $Z(h) := \{z \in \Omega : h(z) = 0\}$ is identical to the coincidence set $E$. Under the stated hypothesis, $z_0 \in Z(h)$ is a limit point of zeros: there exists a sequence of distinct points $(z_k)_{k=1}^\infty \subset Z(h) \setminus \{z_0\}$ such that $\lim_{k \to \infty} z_k = z_0$.

The goal is to prove that $h(z) = 0$ for all $z \in \Omega$, which implies that $f(z) = g(z)$ identically across the entire domain $\Omega$.

**Vanishing of the Local Taylor Coefficients:**
Since $h$ is analytic at $z_0$, there exists an open disk $B(z_0, r) \subset \Omega$ with $r > 0$ on which $h$ is represented by a convergent power series:
$$
\begin{gather}
h(z) = \sum_{n=0}^\infty c_n (z - z_0)^n, \quad \forall z \in B(z_0, r) \tag{3}
\end{gather}
$$
Suppose, for the sake of contradiction, that not all coefficients $c_n$ vanish. 

Then there exists a smallest non-negative integer $m \in \mathbb{N} \cup \{0\}$ such that $c_m \neq 0$:
$$
\begin{gather}
m := \min \{n \in \mathbb{N} \cup \{0\} : c_n \neq 0\} \tag{4}
\end{gather}
$$
If $m = 0$, then $h(z_0) = c_0 \neq 0$. However, since $z_0 = \lim_{k \to \infty} z_k$ and $h(z_k) = 0$ for all $k$, the continuity of $h$ implies:
$$
\begin{gather}
h(z_0) = \lim_{k \to \infty} h(z_k) = 0 \tag{5}
\end{gather}
$$
which gives $c_0 = 0$. Hence $m \geq 1$.

Factor the power $(z - z_0)^m$ out of the series in step 3:
$$
\begin{gather}
h(z) = (z - z_0)^m \sum_{k=0}^\infty c_{m+k} (z - z_0)^k = (z - z_0)^m \psi(z) \tag{6}
\end{gather}
$$
where the auxiliary function $\psi: B(z_0, r) \to \mathbb{C}$ is defined by:
$$
\begin{gather}
\psi(z) := \sum_{k=0}^\infty c_{m+k} (z - z_0)^k = c_m + c_{m+1}(z - z_0) + c_{m+2}(z - z_0)^2 + \cdots \tag{7}
\end{gather}
$$
By the properties of power series, $\psi$ is continuous on $B(z_0, r)$, and its value at the center is:
$$
\begin{gather}
\psi(z_0) = c_m \neq 0 \tag{8}
\end{gather}
$$
Because $\psi$ is continuous and $\psi(z_0) \neq 0$, by the persistence of sign/modulus for continuous mappings, there exists a radius $\delta \in (0, r)$ such that:
$$
\begin{gather}
|\psi(z)| > \frac{|c_m|}{2} > 0, \quad \forall z \in B(z_0, \delta) \tag{9}
\end{gather}
$$
Now inspect the zero structure of $h(z)$ in the punctured neighborhood $B^*(z_0, \delta) := B(z_0, \delta) \setminus \{z_0\}$. 

For every $z \in B^*(z_0, \delta)$, $|z - z_0| > 0$ and $|\psi(z)| > 0$. Taking the modulus in step 6:
$$
\begin{gather}
|h(z)| = |z - z_0|^m |\psi(z)| \geq |z - z_0|^m \frac{|c_m|}{2} > 0 \tag{10}
\end{gather}
$$
Step 10 proves that $h(z) \neq 0$ for every $z \in B^*(z_0, \delta)$. That is, $z_0$ is an isolated zero of $h$.

However, this directly contradicts the initial assumption that $z_0$ is an accumulation point of zeros of $h$, since every open ball $B(z_0, \delta)$ must contain at least one point $z_k \neq z_0$ with $h(z_k) = 0$. 

This contradiction refutes the existence of a minimal index $m$ with $c_m \neq 0$. Consequently:
$$
\begin{gather}
c_n = 0, \quad \forall n \in \mathbb{N} \cup \{0\} \tag{11}
\end{gather}
$$
Substituting step 11 into step 3 demonstrates that $h(z) = 0$ identically for all $z \in B(z_0, r)$.

**Global Propagation via Domain Connectedness:**
To extend the vanishing of $h$ from the local neighborhood $B(z_0, r)$ to the entirety of the connected domain $\Omega$, partition $\Omega$ into topological subsets. 

Let $A$ denote the set of accumulation points of $Z(h)$ in $\Omega$:
$$
\begin{gather}
A := \{z \in \Omega : z \text{ is an accumulation point of } Z(h)\} = Z(h)' \cap \Omega \tag{12}
\end{gather}
$$
The set $A$ is non-empty because $z_0 \in A$. 

1. **$A$ is open in $\Omega$:**
Let $w \in A$. By the local vanishing established above (steps 3 through 11 applied at $w$ instead of $z_0$), there exists a radius $r_w > 0$ such that $B(w, r_w) \subset \Omega$ and $h(z) = 0$ for all $z \in B(w, r_w)$. 

Every point in $B(w, r_w)$ is surrounded by other zeros of $h$, and is therefore an accumulation point of $Z(h)$. Hence, $B(w, r_w) \subseteq A$. Because every point $w \in A$ has an open ball contained within $A$, $A$ is an open subset of $\Omega$.

2. **$A$ is closed in $\Omega$:**
Let $(w_j)_{j=1}^\infty$ be a sequence in $A$ converging to a point $w^* \in \Omega$. Since each $w_j$ is an accumulation point of $Z(h)$, and $Z(h)$ is closed in $\Omega$ by the continuity of $h$, it follows that $w_j \in Z(h)$ for all $j$. 

By continuity of $h$:
$$
\begin{gather}
h(w^*) = \lim_{j \to \infty} h(w_j) = 0 \tag{13}
\end{gather}
$$
Furthermore, in every neighborhood $U$ of $w^*$, there exists $w_j \in U$ for sufficiently large $j$. Since $w_j \in A$, the neighborhood $U$ contains infinitely many zeros of $h$. 

Therefore, $w^*$ is an accumulation point of $Z(h)$, which means $w^* \in A$. Hence, $A$ contains all its limit points in $\Omega$, establishing that $A$ is closed in the subspace topology of $\Omega$.

3. **Conclusion by Connectedness:**
The set $A \subseteq \Omega$ is both open and closed (clopen) in $\Omega$, and $A$ is non-empty since $z_0 \in A$. 

By the topological definition of connectedness, the only clopen subsets of the connected space $\Omega$ are the empty set $\emptyset$ and the entire space $\Omega$ itself. 

Therefore:
$$
\begin{gather}
A = \Omega \tag{14}
\end{gather}
$$
Because $A \subseteq Z(h) \subseteq \Omega$, step 14 implies that $Z(h) = \Omega$. 

Consequently, $h(z) = 0$ for every $z \in \Omega$, which establishes the desired identity:
$$
\begin{gather}
f(z) = g(z), \quad \forall z \in \Omega \tag{15}
\end{gather}
$$
$$
\textbf{Q.E.D}
$$