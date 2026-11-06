---
dg-publish: true
---
Let $f: [a, b] \to \mathbb{R}$ be differentiable on $[a, b]$, and suppose $f'(a) < \gamma < f'(b)$ (the reverse inequality is handled identically).

### Step 1: Construction of the Auxiliary Function
Define the auxiliary function $g: [a, b] \to \mathbb{R}$ by:
$$
\begin{gather}
g(x) := f(x) - \gamma x \tag{1}
\end{gather}
$$

Because $f$ is differentiable on $[a, b]$, by Theorem 1.2 $f$ is continuous on $[a, b]$, which implies that $g$ is continuous on the compact interval $[a, b]$ and differentiable on $[a, b]$, with:
$$
\begin{gather}
g'(x) = f'(x) - \gamma \tag{2}
\end{gather}
$$

### Step 2: Evaluating Boundary Derivatives
Evaluate $g'$ at the boundary endpoints:
$$
\begin{gather}
g'(a) = f'(a) - \gamma < 0 \quad (\text{since } f'(a) < \gamma) \tag{3} \\
g'(b) = f'(b) - \gamma > 0 \quad (\text{since } \gamma < f'(b)) \tag{4}
\end{gather}
$$

### Step 3: Location of the Absolute Minimum
By the Weierstrass Extreme Value Theorem (Theorem 2.5 of Module 4), the continuous function $g$ attains an absolute minimum on $[a, b]$ at some point $c \in [a, b]$:
$$
\begin{gather}
g(c) = \min_{x \in [a, b]} g(x) \tag{5}
\end{gather}
$$

We show that $c$ cannot be either boundary point $a$ or $b$:
1. Because $g'(a) < 0$, the right-hand difference quotient satisfies:
$$
\begin{gather}
\lim_{h \to 0^+} \frac{g(a + h) - g(a)}{h} = g'(a) < 0 \tag{6}
\end{gather}
$$
By sign preservation of limits, there exists $h_1 > 0$ such that $g(a + h_1) - g(a) < 0 \implies g(a + h_1) < g(a)$. Therefore, $a$ cannot be the absolute minimum ($c \neq a$).
2. Because $g'(b) > 0$, the left-hand difference quotient satisfies:
$$
\begin{gather}
\lim_{h \to 0^-} \frac{g(b + h) - g(b)}{h} = g'(b) > 0 \tag{7}
\end{gather}
$$
Because $h < 0$, $g(b + h) - g(b) < 0 \implies g(b + h) < g(b)$. Therefore, $b$ cannot be the absolute minimum ($c \neq b$).

### Step 4: Application of Fermat's Lemma
Because $c \neq a$ and $c \neq b$, $c$ is an interior point: $c \in (a, b)$.

Because $g$ attains an absolute (and hence local) minimum at the interior point $c$, by Theorem 3.1 (Fermat's Stationary Point Lemma):
$$
\begin{gather}
g'(c) = 0 \tag{8}
\end{gather}
$$

Substituting equation (2) into equation (8):
$$
\begin{gather}
f'(c) - \gamma = 0 \implies f'(c) = \gamma \tag{9}
\end{gather}
$$

Because $\gamma$ was an arbitrary value between $f'(a)$ and $f'(b)$, $f'$ takes all intermediate values, proving that the direct image $f'(I)$ of any interval $I$ is an interval.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
