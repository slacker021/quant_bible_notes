---
dg-publish: true
---
Let $I \subseteq \mathbb{R}$ be an arbitrary interval, and let $f: I \to \mathbb{R}$ be continuous on $I$. 

Suppose $c \in \text{int}(I)$ is the unique critical number of $f$ in $I$, and suppose $f$ has a local minimum at $c$.

We must prove that for all $x \in I \setminus \{c\}$:
$$
\begin{gather}
f(c) < f(x) \tag{1}
\end{gather}
$$

### Step 1: Proof by Contradiction
Suppose for contradiction that there exists some point $x_1 \in I$ with $x_1 \neq c$ such that:
$$
\begin{gather}
f(x_1) \le f(c) \tag{2}
\end{gather}
$$

Assume without loss of generality that $x_1 > c$ (the argument for $x_1 < c$ is identical).

### Step 2: Isolating the Local Minimum
Because $c$ is a local minimum, there exists $\delta > 0$ such that $[c, c + \delta] \subset I$ and:
$$
\begin{gather}
f(c) \le f(x) \quad \forall x \in [c, c + \delta] \tag{3}
\end{gather}
$$

Choose $\delta$ sufficiently small such that $c + \delta < x_1$. 

If $f(c + \delta) = f(c)$, then by Rolle's Theorem applied to $f$ on $[c, c + \delta]$, there would exist $\xi \in (c, c + \delta)$ with $f'(\xi) = 0$, producing a second critical number $\xi \neq c$, which contradicts uniqueness. Therefore:
$$
\begin{gather}
f(c) < f(c + \delta) \tag{4}
\end{gather}
$$

### Step 3: Application of the Extreme Value Theorem
Consider the compact subinterval $[c + \delta, x_1] \subset I$.

Because $f$ is continuous on $[c + \delta, x_1]$, by the Weierstrass Extreme Value Theorem (Module 4), $f$ attains an absolute minimum on $[c + \delta, x_1]$ at some point $x^* \in [c + \delta, x_1]$:
$$
\begin{gather}
f(x^*) = \min_{x \in [c + \delta, x_1]} f(x) \tag{5}
\end{gather}
$$

By the assumption that $f(x_1) \le f(c)$, $f(x_1) \le f(c)$. By the inequality of step 4, $f(c) < f(c + \delta)$. Therefore:
$$
\begin{gather}
f(x_1) < f(c + \delta) \tag{6}
\end{gather}
$$

Because $f(x^*) \le f(x_1) < f(c + \delta)$, the absolute minimum $x^*$ cannot be the left endpoint $c + \delta$:
$$
\begin{gather}
x^* \neq c + \delta \tag{7}
\end{gather}
$$

### Step 4: Existence of a Second Critical Point
There are two possibilities for $x^*$:
- **Subcase A ($x^* \in (c + \delta, x_1)$ is an interior point):**
  Because $x^*$ is an interior minimum of $f$ on $[c + \delta, x_1]$, by Fermat's Stationary Point Lemma $x^*$ is a critical number of $f$ ($f'(x^*) = 0$ or undefined). Because $x^* > c + \delta > c$, $x^*$ is distinct from $c$, directly contradicting the uniqueness of the critical number.
- **Subcase B ($x^* = x_1$):**
  If $x_1$ is an interior point of $I$, then $f(x_1) \le f(c) < f(c + \delta)$. 
  Consider the interval $[c, x_1]$. By the Weierstrass Extreme Value Theorem on $[c, x_1]$, $f$ attains an absolute maximum on $[c, x_1]$ at some point $x_{\max}$.
  Because $f(c + \delta) > f(c) \ge f(x_1)$, the maximum value $f(x_{\max}) \ge f(c + \delta) > f(c)$ and $f(x_{\max}) > f(x_1)$.
  Therefore, $x_{\max} \notin \{c, x_1\}$, which forces $x_{\max} \in (c, x_1)$ to be an interior local maximum!
  By Fermat's Lemma, $x_{\max}$ is a critical number. Because $x_{\max} \in (c, x_1)$, $x_{\max} \neq c$, which again contradicts uniqueness.

In all cases, a contradiction is reached. Therefore, $f(x) > f(c)$ for all $x \in I \setminus \{c\}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
