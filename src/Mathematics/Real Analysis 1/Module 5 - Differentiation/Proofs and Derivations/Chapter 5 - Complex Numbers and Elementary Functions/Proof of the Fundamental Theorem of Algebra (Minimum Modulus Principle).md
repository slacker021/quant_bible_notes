---
dg-publish: true
---
Let $P: \mathbb{C} \to \mathbb{C}$ be a non-constant polynomial with complex coefficients of degree $n \geq 1$:
$$
\begin{gather}
P(z) = a_n z^n + a_{n-1} z^{n-1} + \cdots + a_1 z + a_0, \quad a_n \neq 0 \tag{1}
\end{gather}
$$
The Fundamental Theorem of Algebra asserts that there exists at least one complex number $z^* \in \mathbb{C}$ such that $P(z^*) = 0$. 

The proof proceeds in two major steps: first, establishing that the continuous real-valued modulus function $|P(z)|$ attains a global minimum on $\mathbb{C}$ through coercivity and compactness; second, demonstrating via the Minimum Modulus Principle (in the style of Argand) that if $|P(z^*)| > 0$, one can strictly decrease the modulus, thereby showing that the global minimum value must be identically zero.

**Existence of a Global Minimum (Coercivity and Compactness):**
Factor the leading term $a_n z^n$ out of $P(z)$ for $z \neq 0$:
$$
\begin{gather}
P(z) = a_n z^n \left( 1 + \frac{a_{n-1}}{a_n z} + \frac{a_{n-2}}{a_n z^2} + \cdots + \frac{a_0}{a_n z^n} \right) \tag{2}
\end{gather}
$$
Taking the complex modulus and applying the reverse triangle inequality $|1 + w| \geq 1 - |w|$:
$$
\begin{gather}
|P(z)| \geq |a_n| |z|^n \left( 1 - \sum_{k=1}^n \left| \frac{a_{n-k}}{a_n} \right| \frac{1}{|z|^k} \right) \tag{3}
\end{gather}
$$
Define $M := \sum_{k=1}^n \left| \frac{a_{n-k}}{a_n} \right|$. For all $z \in \mathbb{C}$ satisfying $|z| \geq \max\{1, 2M\}$, the sum satisfies:
$$
\begin{gather}
\sum_{k=1}^n \left| \frac{a_{n-k}}{a_n} \right| \frac{1}{|z|^k} \leq \frac{1}{|z|} \sum_{k=1}^n \left| \frac{a_{n-k}}{a_n} \right| = \frac{M}{|z|} \leq \frac{1}{2} \tag{4}
\end{gather}
$$
Substituting step 4 into step 3 yields:
$$
\begin{gather}
|P(z)| \geq \frac{1}{2} |a_n| |z|^n \tag{5}
\end{gather}
$$
valid for all $|z| \geq R_0 := \max\{1, 2M\}$. Since $n \geq 1$ and $|a_n| > 0$, step 5 shows that $|P(z)| \to \infty$ as $|z| \to \infty$. That is, the polynomial modulus function is *coercive*.

In particular, consider the value of $|P(0)| = |a_0|$. By step 5, one can choose a radius $R > R_0$ sufficiently large such that:
$$
\begin{gather}
\frac{1}{2} |a_n| R^n > |a_0| = |P(0)| \tag{6}
\end{gather}
$$
For every $z$ outside the closed disk $\overline{B}(0, R) := \{z \in \mathbb{C} : |z| \leq R\}$, step 5 and step 6 ensure:
$$
\begin{gather}
|P(z)| > |P(0)| \tag{7}
\end{gather}
$$
The closed disk $\overline{B}(0, R)$ is closed and bounded in $\mathbb{C} \cong \mathbb{R}^2$, and therefore compact by the Heine-Borel theorem. 

Since $P$ is a polynomial, the mapping $z \mapsto |P(z)|$ is continuous on $\mathbb{C}$. By the Extreme Value Theorem (Weierstrass theorem), $|P(z)|$ attains a minimum on $\overline{B}(0, R)$ at some point $z^* \in \overline{B}(0, R)$:
$$
\begin{gather}
|P(z^*)| = \inf_{z \in \overline{B}(0, R)} |P(z)| \tag{8}
\end{gather}
$$
Since $0 \in \overline{B}(0, R)$, step 8 guarantees that $|P(z^*)| \leq |P(0)|$. Combining this with step 7 shows that for all $z \notin \overline{B}(0, R)$:
$$
\begin{gather}
|P(z)| > |P(0)| \geq |P(z^*)| \tag{9}
\end{gather}
$$
Therefore, $z^*$ is a *global minimum* of $|P(z)|$ on the entire complex plane $\mathbb{C}$:
$$
\begin{gather}
|P(z^*)| \leq |P(z)|, \quad \forall z \in \mathbb{C} \tag{10}
\end{gather}
$$

**The Minimum Modulus Principle and Argand's Construction:**
Suppose, for the sake of contradiction, that $P(z^*) \neq 0$, so $|P(z^*)| > 0$.

Expand $P(z)$ in powers of $(z - z^*)$ using the Taylor expansion of polynomials about $z^*$:
$$
\begin{gather}
P(z^* + h) = P(z^*) + c_1 h + c_2 h^2 + \cdots + c_n h^n \tag{11}
\end{gather}
$$
where $c_k = \frac{P^{(k)}(z^*)}{k!}$. Because $P$ is non-constant of degree $n$, not all coefficients $c_1, \dots, c_n$ can be zero (in fact, $c_n = a_n \neq 0$). 

Let $k \in \{1, 2, \dots, n\}$ be the smallest integer such that $c_k \neq 0$:
$$
\begin{gather}
k := \min \{j \in \{1, \dots, n\} : c_j \neq 0\} \tag{12}
\end{gather}
$$
Then step 11 can be written as:
$$
\begin{gather}
P(z^* + h) = P(z^*) + c_k h^k + h^{k+1} Q(h) \tag{13}
\end{gather}
$$
where $Q(h) := \sum_{j=k+1}^n c_j h^{j-(k+1)}$ is a polynomial in $h$ (with $Q(h) \equiv 0$ if $k = n$).

Factor out the non-zero quantity $P(z^*)$:
$$
\begin{gather}
P(z^* + h) = P(z^*) \left[ 1 + \frac{c_k}{P(z^*)} h^k + \frac{h^{k+1} Q(h)}{P(z^*)} \right] \tag{14}
\end{gather}
$$
Express the non-zero complex ratio $\frac{c_k}{P(z^*)}$ in polar form:
$$
\begin{gather}
\frac{c_k}{P(z^*)} = r_0 e^{i \alpha}, \quad r_0 = \left| \frac{c_k}{P(z^*)} \right| > 0, \quad \alpha \in \mathbb{R} \tag{15}
\end{gather}
$$
To make the term $\frac{c_k}{P(z^*)} h^k$ real and negative, choose the argument of $h$ such that $\alpha + k \arg(h) \equiv \pi \pmod{2\pi}$. Specifically, set:
$$
\begin{gather}
\theta := \frac{\pi - \alpha}{k} \tag{16}
\end{gather}
$$
For any positive real parameter $t > 0$, choose the increment $h$ to be:
$$
\begin{gather}
h(t) := t e^{i \theta} \tag{17}
\end{gather}
$$
Then the $k$-th power becomes:
$$
\begin{gather}
h(t)^k = t^k e^{i k \theta} = t^k e^{i (\pi - \alpha)} = - t^k e^{-i \alpha} \tag{18}
\end{gather}
$$
Substituting step 18 and step 15 into the lead term in brackets in step 14 yields:
$$
\begin{gather}
\frac{c_k}{P(z^*)} h(t)^k = \left( r_0 e^{i \alpha} \right) \left( - t^k e^{-i \alpha} \right) = - r_0 t^k \tag{19}
\end{gather}
$$
Substituting step 19 into step 14:
$$
\begin{gather}
P(z^* + h(t)) = P(z^*) \left[ 1 - r_0 t^k + t^{k+1} R(t) \right] \tag{20}
\end{gather}
$$
where $R(t) := \frac{e^{i(k+1)\theta} Q(t e^{i\theta})}{P(z^*)}$. 

Since $Q$ is a polynomial, there exists a constant $C > 0$ such that $|R(t)| \leq C$ for all $t \in [0, 1]$.

Now restrict $t > 0$ to satisfy $t < 1$ and $r_0 t^k < 1$. Then $1 - r_0 t^k > 0$. Taking the modulus in step 20 and applying the triangle inequality:
$$
\begin{gather}
|P(z^* + h(t))| = |P(z^*)| \left| (1 - r_0 t^k) + t^{k+1} R(t) \right| \leq |P(z^*)| \left[ 1 - r_0 t^k + t^{k+1} |R(t)| \right] \tag{21}
\end{gather}
$$
Using $|R(t)| \leq C$, step 21 simplifies to:
$$
\begin{gather}
|P(z^* + h(t))| \leq |P(z^*)| \left[ 1 - r_0 t^k + C t^{k+1} \right] = |P(z^*)| \left[ 1 - t^k (r_0 - C t) \right] \tag{22}
\end{gather}
$$
Since $r_0 > 0$ is a fixed positive constant, one can choose $t > 0$ strictly small enough such that:
$$
\begin{gather}
0 < t < \min \left\{ 1, \left( \frac{1}{r_0} \right)^{1/k}, \frac{r_0}{2C} \right\} \tag{23}
\end{gather}
$$
For any such choice of $t$, the factor satisfies $r_0 - C t > \frac{r_0}{2} > 0$. Consequently:
$$
\begin{gather}
1 - t^k (r_0 - C t) < 1 - \frac{r_0}{2} t^k < 1 \tag{24}
\end{gather}
$$
Substituting step 24 into step 22 yields:
$$
\begin{gather}
|P(z^* + h(t))| \leq |P(z^*)| \left( 1 - \frac{r_0}{2} t^k \right) < |P(z^*)| \tag{25}
\end{gather}
$$
Step 25 identifies a complex point $z_1 := z^* + h(t) \in \mathbb{C}$ at which the polynomial modulus is strictly smaller than $|P(z^*)|$:
$$
\begin{gather}
|P(z_1)| < |P(z^*)| \tag{26}
\end{gather}
$$
Step 26 directly contradicts step 10, which asserted that $z^*$ is a global minimum of $|P(z)|$ on all of $\mathbb{C}$.

This contradiction refutes the assumption that $|P(z^*)| > 0$. 

Therefore, it must be the case that:
$$
\begin{gather}
|P(z^*)| = 0 \implies P(z^*) = 0 \tag{27}
\end{gather}
$$
proving that $P(z)$ has at least one root $z^* \in \mathbb{C}$.
$$
\textbf{Q.E.D}
$$