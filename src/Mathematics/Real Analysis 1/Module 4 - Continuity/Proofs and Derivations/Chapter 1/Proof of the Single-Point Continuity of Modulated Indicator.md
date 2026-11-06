---
dg-publish: true
---
Let the modulated indicator function $f: \mathbb{R} \to \mathbb{R}$ be defined by:
$$
\begin{gather}
f(x) := x \cdot \mathbf{1}_{\mathbb{Q}}(x) = \begin{cases} x, & x \in \mathbb{Q} \\ 0, & x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \tag{1}
\end{gather}
$$

# Proposition 1
Evaluating $f$ at the origin $x = 0$ yields:
$$
\begin{gather}
f(0) = 0 \cdot \mathbf{1}_{\mathbb{Q}}(0) = 0 \cdot 1 = 0 \tag{2}
\end{gather}
$$

For every real number $x \in \mathbb{R}$, the absolute value of $f(x)$ is bounded above by $|x|$:
$$
\begin{gather}
|f(x)| = \begin{cases} |x|, & x \in \mathbb{Q} \\ 0, & x \in \mathbb{R} \setminus \mathbb{Q} \end{cases} \implies 0 \le |f(x)| \le |x| \tag{3}
\end{gather}
$$

Let an arbitrary positive tolerance $\varepsilon > 0$ be given. 

Set the control parameter:
$$
\begin{gather}
\delta := \varepsilon > 0 \tag{4}
\end{gather}
$$

Let $x \in \mathbb{R}$ satisfy $|x - 0| < \delta$. Applying the majorization bound of step 3 together with step 2 and step 4 gives:
$$
\begin{gather}
|f(x) - f(0)| = |f(x)| \le |x| < \delta = \varepsilon \tag{5}
\end{gather}
$$

Because $\varepsilon > 0$ was arbitrarily chosen, step 5 proves that $f$ is continuous at the point $x = 0$.

---
# Proposition 2
Let $a \in \mathbb{R} \setminus \{0\}$ be an arbitrary non-zero real number. Because $a \neq 0$, the absolute value $|a|$ is strictly positive. 

Fix the error tolerance:
$$
\begin{gather}
\varepsilon_0 := \frac{|a|}{2} > 0 \tag{6}
\end{gather}
$$

Let $\delta > 0$ be an arbitrary distance. Define the constrained radius:
$$
\begin{gather}
\delta' := \min\left(\delta, \frac{|a|}{2}\right) > 0 \tag{7}
\end{gather}
$$

There are two mutually exclusive cases:
* Case 1: $a \in \mathbb{Q} \setminus \{0\}$. By step 1, $f(a) = a \neq 0$. By the density of the irrational numbers in $\mathbb{R}$, there exists an irrational number $\xi \in \mathbb{R} \setminus \mathbb{Q}$ such that:
$$
\begin{gather}
|\xi - a| < \delta' \le \delta \tag{8}
\end{gather}
$$
Because $\xi$ is irrational, step 1 gives $f(\xi) = 0$. Evaluating the absolute difference:
$$
\begin{gather}
|f(\xi) - f(a)| = |0 - a| = |a| > \frac{|a|}{2} = \varepsilon_0 \tag{9}
\end{gather}
$$

* Case 2: $a \in (\mathbb{R} \setminus \mathbb{Q}) \setminus \{0\}$. By step 1, $f(a) = 0$. By the density of the rational numbers in $\mathbb{R}$, there exists a rational number $r \in \mathbb{Q}$ such that:
$$
\begin{gather}
|r - a| < \delta' \le \delta \tag{10}
\end{gather}
$$
Because $r$ is rational, step 1 gives $f(r) = r$. By the reverse triangle inequality (from the [[Proof of the Triangle Inequality]]):
$$
\begin{gather}
|r| = |a + (r - a)| \ge |a| - |r - a| > |a| - \delta' \ge |a| - \frac{|a|}{2} = \frac{|a|}{2} \tag{11}
\end{gather}
$$
Evaluating the functional deviation at $r$:
$$
\begin{gather}
|f(r) - f(a)| = |r - 0| = |r| > \frac{|a|}{2} = \varepsilon_0 \tag{12}
\end{gather}
$$

In both cases, for every distance $\delta > 0$, there exists a point $x \in \mathbb{R}$ satisfying $|x - a| < \delta$ for which $|f(x) - f(a)| \ge \varepsilon_0$. 

Consequently, $f$ is discontinuous at $a$. Because $a \in \mathbb{R} \setminus \{0\}$ was arbitrary, $f$ is discontinuous at every non-zero point of the real line.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$