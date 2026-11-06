---
dg-publish: true
---
Let a body of mass $m$ fall vertically under gravity ($g > 0$) from rest ($v(0) = 0$).

### Part 1: Linear Drag (Stokes Regime)
Newton's second law is:
$$
\begin{gather}
m \frac{dv}{dt} = mg - k_1 v \implies \frac{dv}{dt} = g - \frac{k_1}{m}v \tag{1}
\end{gather}
$$
Define the terminal velocity $v_\infty := \frac{mg}{k_1}$. Equation (1) becomes:
$$
\begin{gather}
\frac{dv}{dt} = -\frac{k_1}{m}(v - v_\infty) \tag{2}
\end{gather}
$$

Dividing by $v - v_\infty \neq 0$:
$$
\begin{gather}
\frac{1}{v - v_\infty}\frac{dv}{dt} = \frac{d}{dt}\big(\ln |v - v_\infty|\big) = -\frac{k_1}{m} \tag{3}
\end{gather}
$$

Integrating from 0 to $t$:
$$
\begin{gather}
\ln\left( \frac{v_\infty - v(t)}{v_\infty} \right) = -\frac{k_1}{m} t \tag{4}
\end{gather}
$$

Exponentiating:
$$
\begin{gather}
\frac{v_\infty - v(t)}{v_\infty} = e^{-\frac{k_1}{m} t} \implies v(t) = v_\infty \left( 1 - e^{-\frac{k_1}{m} t} \right) \tag{5}
\end{gather}
$$

### Part 2: Quadratic Aerodynamic Drag (Newton Regime)
Newton's second law is:
$$
\begin{gather}
m \frac{dv}{dt} = mg - k_2 v^2 \tag{6}
\end{gather}
$$

Define the quadratic terminal velocity $v_\infty := \sqrt{\frac{mg}{k_2}}$. Then $k_2 = \frac{mg}{v_\infty^2}$, and:
$$
\begin{gather}
m \frac{dv}{dt} = mg\left( 1 - \frac{v^2}{v_\infty^2} \right) \implies \frac{dv}{dt} = g\left( 1 - \frac{v^2}{v_\infty^2} \right) \tag{7}
\end{gather}
$$

Separating variables:
$$
\begin{gather}
\frac{dv}{1 - \frac{v^2}{v_\infty^2}} = g \, dt \implies \frac{v_\infty}{2} \left( \frac{1}{v_\infty - v} + \frac{1}{v_\infty + v} \right) dv = g \, dt \tag{8}
\end{gather}
$$

Integrating both sides from $v = 0$ to $v(t)$:
$$
\begin{gather}
\frac{v_\infty}{2} \ln\left( \frac{v_\infty + v(t)}{v_\infty - v(t)} \right) = gt \tag{9}
\end{gather}
$$

By definition of the inverse hyperbolic tangent $\text{artanh}(x) = \frac{1}{2}\ln\left(\frac{1+x}{1-x}\right)$ (Chapter 2, Table 2.1):
$$
\begin{gather}
\text{artanh}\left(\frac{v(t)}{v_\infty}\right) = \frac{gt}{v_\infty} \tag{10}
\end{gather}
$$

Applying the hyperbolic tangent mapping:
$$
\begin{gather}
v(t) = v_\infty \tanh\left( \frac{gt}{v_\infty} \right) \tag{11}
\end{gather}
$$
Because $\lim_{t \to \infty} \tanh(t) = 1$, $v(t) \to v_\infty$ asymptotically.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
