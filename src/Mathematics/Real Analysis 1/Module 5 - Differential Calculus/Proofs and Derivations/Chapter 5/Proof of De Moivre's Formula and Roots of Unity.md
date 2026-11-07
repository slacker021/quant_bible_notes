---
dg-publish: true
---
Let $z = r(\cos\varphi + i\sin\varphi)$ be a non-zero complex number in trigonometric form, with $r = |z| > 0$ and $\varphi \in \mathbb{R}$.

### Part 1: De Moivre's Formula
We prove by induction that for all $n \in \mathbb{N}$:
$$
\begin{gather}
z^n = r^n \big( \cos(n\varphi) + i\sin(n\varphi) \big) \tag{1}
\end{gather}
$$

For $n = 1$, $z^1 = r^1(\cos(1\varphi) + i\sin(1\varphi))$, which holds identically.

Assume equation (1) holds for $n = k$: $z^k = r^k(\cos(k\varphi) + i\sin(k\varphi))$. 
Computing $z^{k+1} = z^k \cdot z$:
$$
\begin{gather}
z^{k+1} = \big[ r^k (\cos(k\varphi) + i\sin(k\varphi)) \big] \cdot \big[ r (\cos\varphi + i\sin\varphi) \big] \tag{2}
\end{gather}
$$

Using complex multiplication:
$$
\begin{gather}
z^{k+1} = r^{k+1} \Big( \big[ \cos(k\varphi)\cos\varphi - \sin(k\varphi)\sin\varphi \big] + i \big[ \sin(k\varphi)\cos\varphi + \cos(k\varphi)\sin\varphi \big] \Big) \tag{3}
\end{gather}
$$

By standard angle addition identities for cosine and sine:
$$
\begin{gather}
\cos(k\varphi)\cos\varphi - \sin(k\varphi)\sin\varphi = \cos((k+1)\varphi) \tag{4} \\
\sin(k\varphi)\cos\varphi + \cos(k\varphi)\sin\varphi = \sin((k+1)\varphi) \tag{5}
\end{gather}
$$

Substituting equations (4) and (5) into equation (3):
$$
\begin{gather}
z^{k+1} = r^{k+1} \big( \cos((k+1)\varphi) + i\sin((k+1)\varphi) \big) \tag{6}
\end{gather}
$$
which completes the induction for $n \in \mathbb{N}$.

For $n = 0$, $z^0 = 1 = r^0(\cos 0 + i\sin 0)$. 

For negative integers $n = -m$ ($m \in \mathbb{N}$):
$$
\begin{gather}
z^{-m} = \frac{1}{z^m} = \frac{1}{r^m(\cos(m\varphi) + i\sin(m\varphi))} = \frac{\cos(m\varphi) - i\sin(m\varphi)}{r^m(\cos^2(m\varphi) + \sin^2(m\varphi))} = r^{-m} \big( \cos(-m\varphi) + i\sin(-m\varphi) \big) \tag{7}
\end{gather}
$$
establishing de Moivre's formula for all $n \in \mathbb{Z}$.

### Part 2: The Roots of Unity and $n$-th Roots
We solve the equation $w^n = z$. Let $w = \rho(\cos\theta + i\sin\theta)$. 

By de Moivre's formula:
$$
\begin{gather}
w^n = \rho^n(\cos(n\theta) + i\sin(n\theta)) = r(\cos\varphi + i\sin\varphi) \tag{8}
\end{gather}
$$

Equating moduli and arguments:
$$
\begin{gather}
\rho^n = r \implies \rho = \sqrt[n]{r} \tag{9} \\
n\theta = \varphi + 2\pi k \implies \theta_k = \frac{\varphi + 2\pi k}{n}, \quad k \in \mathbb{Z} \tag{10}
\end{gather}
$$

For $k = 0, 1, \dots, n - 1$, the angles $\theta_k$ produce $n$ distinct points on the circle of radius $\sqrt[n]{r}$. For any $k \ge n$ or $k < 0$, dividing $k$ by $n$ with remainder shows that $\theta_k$ differs from some $\theta_j$ ($0 \le j < n$) by an integer multiple of $2\pi$, generating identical values of $\cos\theta_k + i\sin\theta_k$. 

Therefore, there exist exactly $n$ distinct roots:
$$
\begin{gather}
w_k = \sqrt[n]{r} \left( \cos\left(\frac{\varphi + 2\pi k}{n}\right) + i\sin\left(\frac{\varphi + 2\pi k}{n}\right) \right), \quad k = 0, 1, \dots, n - 1 \tag{11}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
