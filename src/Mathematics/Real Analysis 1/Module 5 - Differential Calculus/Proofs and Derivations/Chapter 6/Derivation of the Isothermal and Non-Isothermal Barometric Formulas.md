---
dg-publish: true
---
By hydrostatic equilibrium in the gravitational field of the Earth, the atmospheric pressure $p(h)$ at altitude $h \ge 0$ satisfies:
$$
\begin{gather}
\frac{dp}{dh} = -\rho(h) g \tag{1}
\end{gather}
$$

By the ideal gas equation of state, density is $\rho = \frac{\mu p}{R T(h)}$, where $\mu$ is the molar mass of air and $R$ is the gas constant:
$$
\begin{gather}
\frac{dp}{dh} = -\frac{\mu g}{R T(h)} p(h) \tag{2}
\end{gather}
$$

Because $p(h) > 0$, dividing by $p(h)$:
$$
\begin{gather}
\frac{1}{p} \frac{dp}{dh} = \frac{d}{dh}\big(\ln p(h)\big) = -\frac{\mu g}{R T(h)} \tag{3}
\end{gather}
$$

### Part 1: Isothermal Atmosphere ($T(h) \equiv T_0$)
If temperature is constant across all altitudes, equation (3) becomes:
$$
\begin{gather}
\frac{d}{dh}\big(\ln p(h)\big) = -\frac{\mu g}{R T_0} \tag{4}
\end{gather}
$$

Integrating both sides with respect to $h$:
$$
\begin{gather}
\ln p(h) - \ln p(0) = -\frac{\mu g}{R T_0} h \tag{5}
\end{gather}
$$

Setting $p_0 = p(0)$ and exponentiating:
$$
\begin{gather}
p(h) = p_0 \exp\left( -\frac{\mu g}{R T_0} h \right) \tag{6}
\end{gather}
$$

### Part 2: Non-Isothermal Atmosphere with Linear Temperature Lapse Rate
In the troposphere, temperature decreases linearly with altitude:
$$
\begin{gather}
T(h) = T_0 - \gamma h \quad (\gamma > 0) \tag{7}
\end{gather}
$$

Substituting equation (7) into equation (3):
$$
\begin{gather}
\frac{d}{dh}\big(\ln p(h)\big) = -\frac{\mu g}{R(T_0 - \gamma h)} \tag{8}
\end{gather}
$$

Recognizing the derivative on the right-hand side:
$$
\begin{gather}
\frac{d}{dh} \left[ \frac{\mu g}{R\gamma} \ln(T_0 - \gamma h) \right] = \frac{\mu g}{R\gamma} \frac{-\gamma}{T_0 - \gamma h} = -\frac{\mu g}{R(T_0 - \gamma h)} \tag{9}
\end{gather}
$$

Therefore:
$$
\begin{gather}
\frac{d}{dh} \left[ \ln p(h) - \frac{\mu g}{R\gamma} \ln(T_0 - \gamma h) \right] = 0 \tag{10}
\end{gather}
$$

By Theorem 3.5 (The Constancy Criterion):
$$
\begin{gather}
\ln p(h) - \frac{\mu g}{R\gamma} \ln(T_0 - \gamma h) = C \tag{11}
\end{gather}
$$

At $h = 0$, $C = \ln p_0 - \frac{\mu g}{R\gamma} \ln T_0$. 

Substituting $C$ back into equation (11):
$$
\begin{gather}
\ln\left(\frac{p(h)}{p_0}\right) = \frac{\mu g}{R\gamma} \big( \ln(T_0 - \gamma h) - \ln T_0 \big) = \frac{\mu g}{R\gamma} \ln\left( 1 - \frac{\gamma}{T_0} h \right) \tag{12}
\end{gather}
$$

Exponentiating equation (12):
$$
\begin{gather}
p(h) = p_0 \left( 1 - \frac{\gamma}{T_0} h \right)^{\frac{\mu g}{R\gamma}} \tag{13}
\end{gather}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
