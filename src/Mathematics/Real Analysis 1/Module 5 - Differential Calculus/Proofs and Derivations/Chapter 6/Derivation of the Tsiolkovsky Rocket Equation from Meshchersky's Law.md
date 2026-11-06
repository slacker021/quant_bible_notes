---
dg-publish: true
---
Consider a rocket moving in field-free space ($F_{\text{ext}} = 0$). By Meshchersky's equation (derived from momentum conservation):
$$
\begin{gather}
m(t)\frac{dv}{dt} + u\frac{dm}{dt} = 0 \tag{1}
\end{gather}
$$
where $m(t) > 0$ is the rocket mass, $v(t)$ is its forward velocity, and $u > 0$ is the constant relative speed of the exhaust gases directed backwards.

### Step 1: Separation of Variables
Rearranging equation (1):
$$
\begin{gather}
m(t)\frac{dv}{dt} = -u \frac{dm}{dt} \tag{2}
\end{gather}
$$

Because $m(t) > 0$, divide both sides by $m(t)$:
$$
\begin{gather}
\frac{dv}{dt} = -u \frac{1}{m(t)} \frac{dm}{dt} = -u \frac{d}{dt}\big(\ln m(t)\big) \tag{3}
\end{gather}
$$

### Step 2: Integration via the Fundamental Corollary of Lagrange
Move all terms to one side:
$$
\begin{gather}
\frac{d}{dt}\big( v(t) + u \ln m(t) \big) = 0 \tag{4}
\end{gather}
$$

By Theorem 3.5 (The Constancy Criterion, proven from Lagrange's Mean Value Theorem), a function whose derivative vanishes identically on a time interval is constant:
$$
\begin{gather}
v(t) + u \ln m(t) = C \tag{5}
\end{gather}
$$

### Step 3: Imposition of Initial Conditions
At the initial launch time $t = 0$, $v(0) = v_0$ and $m(0) = m_0$. 
Evaluating equation (5) at $t = 0$:
$$
\begin{gather}
C = v_0 + u \ln m_0 \tag{6}
\end{gather}
$$

Substituting $C$ back into equation (5):
$$
\begin{gather}
v(t) + u \ln m(t) = v_0 + u \ln m_0 \tag{7}
\end{gather}
$$

Solving for $v(t)$:
$$
\begin{gather}
v(t) = v_0 + u \big( \ln m_0 - \ln m(t) \big) = v_0 + u \ln\left( \frac{m_0}{m(t)} \right) \tag{8}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
