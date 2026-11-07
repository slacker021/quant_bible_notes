---
dg-publish: true
---
### Part 1: First-Order Radioactive Disintegration
Let $N(t) > 0$ denote the population of radioactive nuclei at time $t \ge 0$, obeying the kinetic rate equation:
$$
\begin{gather}
\frac{dN}{dt} = -\lambda N(t), \quad N(0) = N_0 \tag{1}
\end{gather}
$$
where $\lambda > 0$ is the decay constant.

Multiplying the equation of step 1 by the integrating factor $e^{\lambda t}$:
$$
\begin{gather}
e^{\lambda t}\frac{dN}{dt} + \lambda e^{\lambda t} N(t) = 0 \implies \frac{d}{dt}\big( N(t) e^{\lambda t} \big) = 0 \tag{2}
\end{gather}
$$

By the Constancy Criterion:
$$
\begin{gather}
N(t) e^{\lambda t} = C \tag{3}
\end{gather}
$$

At $t = 0$, $C = N_0 e^0 = N_0$. 
Multiplying by $e^{-\lambda t}$:
$$
\begin{gather}
N(t) = N_0 e^{-\lambda t} \tag{4}
\end{gather}
$$

Evaluating the half-life $T_{1/2}$:
$$
\begin{gather}
\frac{N_0}{2} = N_0 e^{-\lambda T_{1/2}} \implies e^{\lambda T_{1/2}} = 2 \implies T_{1/2} = \frac{\ln 2}{\lambda} \tag{5}
\end{gather}
$$

### Part 2: Nuclear Reactor Criticality Kinetics
Let $n(t)$ denote the thermal neutron density in a nuclear reactor core. The rate of change of neutron density accounts for prompt fission production ($\alpha n$), parasitic absorption ($\beta n$), and geometric boundary leakage ($\gamma n$):
$$
\begin{gather}
\frac{dn}{dt} = (\alpha - \beta - \gamma) n(t) \tag{6}
\end{gather}
$$

Define the effective multiplication excess parameter $k_{\text{eff}} := \alpha - \beta - \gamma \in \mathbb{R}$. The equation of step 6 becomes:
$$
\begin{gather}
\frac{dn}{dt} = k_{\text{eff}} n(t), \quad n(0) = n_0 \tag{7}
\end{gather}
$$

Applying the integrating factor $e^{-k_{\text{eff}} t}$:
$$
\begin{gather}
\frac{d}{dt}\big( n(t) e^{-k_{\text{eff}} t} \big) = 0 \implies n(t) = n_0 e^{k_{\text{eff}} t} \tag{8}
\end{gather}
$$

Analyzing the asymptotic behavior as $t \to \infty$:
1. **Subcritical ($k_{\text{eff}} < 0$):** Because $k_{\text{eff}} = -|k_{\text{eff}}| < 0$, $\lim_{t \to \infty} n(t) = n_0 \lim_{t \to \infty} e^{-|k_{\text{eff}}| t} = 0$. The reaction extinguishes exponentially.
2. **Critical ($k_{\text{eff}} = 0$):** $n(t) = n_0 e^0 = n_0 = \text{const}$. Neutron population and thermal power output remain constant over time.
3. **Supercritical ($k_{\text{eff}} > 0$):** $\lim_{t \to \infty} n(t) = \infty$. Neutron density grows without bound, resulting in prompt runaway excursion.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
