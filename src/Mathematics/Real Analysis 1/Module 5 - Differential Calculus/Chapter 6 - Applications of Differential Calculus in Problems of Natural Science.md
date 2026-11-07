---
dg-publish: true
---
# Applications of Differential Calculus in Problems of Natural Science

Differential calculus was forged in the seventeenth and eighteenth centuries primarily to decipher the dynamical laws of nature. In the physical sciences, fundamental balance principles—conservation of momentum, mass continuity, hydrostatic equilibrium, and energy conservation—are formulated not as algebraic equations connecting states, but as differential relations connecting instantaneous rates of change.

Following Vladimir Zorich's pedagogical framework, this chapter presents **six canonical physical systems**, exploring each in extensive detail through a standardized analytical structure:
1. Physical formulation and coordinate definition.
2. Deductive derivation of the governing differential equation.
3. Analytical solution using single-variable differential calculus.
4. Asymptotic analysis and qualitative phase dynamics.

---

# Example 1: Motion of a Body of Variable Mass (The Rocket Equation)

### Physical System and Variable Definitions
Consider a rocket launched vertically or traversing field-free space. The total mass $m(t)$ of the vehicle decreases continuously over time as chemical propellants combust and exhaust gases are expelled at high velocity. 

Let:
- $m(t) > 0$ denote the instantaneous mass of the rocket at time $t$.
- $v(t)$ denote the instantaneous velocity of the rocket relative to a fixed inertial frame.
- $u > 0$ denote the constant speed of the exhaust gas relative to the rocket engine nozzle, directed opposite to the vehicle's motion.

```easy-tikz
title $\text{Conservation of Momentum in Variable Mass Rocket Propulsion}$
xlabel $x$
ylabel $y$
show x from 0 to 8 and y from 0 to 4
axes on the edges
size 10 x 5
draw a rectangle from (4.0, 1.2) to (6.5, 2.8), in teal, very thick, filled in teal, opacity 0.15
draw a segment from (6.5, 1.2) to (7.5, 2.0), in teal, very thick
draw a segment from (6.5, 2.8) to (7.5, 2.0), in teal, very thick
draw a rectangle from (1.5, 1.6) to (2.5, 2.4), in orange, thick, filled in orange, opacity 0.3
draw a segment from (6.0, 2.0) to (7.8, 2.0), in black, thick, with an arrow at (7.8, 2.0)
draw a segment from (1.5, 2.0) to (0.5, 2.0), in red, thick, with an arrow at (0.5, 2.0)
write "$\text{Rocket } m(t)$" at (5.2, 2.0), in teal, center
write "$v(t) + \Delta v$" at (7.5, 2.3), in black, right
write "$\Delta m_{\text{exhaust}}$" at (2.0, 2.0), in orange, center
write "$v - u$" at (0.4, 2.0), in red, left
```

### Derivation of the Meshchersky Differential Equation
Consider the change in total linear momentum of the closed physical system (rocket plus expelled exhaust mass $\Delta m_e = -\Delta m > 0$) over an infinitesimal time increment $\Delta t$:
$$P(t) = m(t)v(t) \tag{1}$$
$$P(t + \Delta t) = (m + \Delta m)(v + \Delta v) + (-\Delta m)(v - u) \tag{2}$$

Expanding equation (2) and computing the increment $\Delta P$:
$$\Delta P = m \Delta v + v \Delta m + \Delta m \Delta v - v \Delta m + u \Delta m = m \Delta v + u \Delta m + \mathcal{O}((\Delta t)^2) \tag{3}$$

Dividing by $\Delta t$ and taking the limit as $\Delta t \to 0$:
$$\frac{dP}{dt} = m(t)\frac{dv}{dt} + u\frac{dm}{dt} \tag{4}$$

In the presence of an external external force $F_{\text{ext}}$ (such as gravity $F_g = -m(t)g$):
$$m(t)\frac{dv}{dt} + u\frac{dm}{dt} = F_{\text{ext}} \tag{5}$$
Equation (5) is **Meshchersky's equation** for the dynamics of a point mass of variable mass.

$$\begin{gather}
\textbf{Proposition: The Tsiolkovsky Rocket Equation} \\[5mm]
\text{In field-free space } (F_{\text{ext}} = 0), \text{ the velocity of a rocket with initial mass } m_0 \text{ and burnout mass } m(t) \text{ satisfies:} \\[3.5mm]
v(t) = v_0 + u \ln\left( \frac{m_0}{m(t)} \right).
\end{gather}$$
(see [[Derivation of the Tsiolkovsky Rocket Equation from Meshchersky's Law]])

---

# Example 2: The Barometric Formula

### Hydrostatic Equilibrium in the Atmosphere
Consider a vertical column of air in the Earth's atmosphere. Let $p(h)$ denote the atmospheric pressure at altitude $h \ge 0$, and let $\rho(h)$ denote the air density.

Consider a thin horizontal layer of gas of cross-sectional area $A$ bounded between altitudes $h$ and $h + \Delta h$. The upward force on the bottom face is $p(h)A$, while the downward force on the top face is $p(h + \Delta h)A$. The weight of the trapped air mass is $\Delta W = \rho(h) g A \Delta h$.

For the air column to be in static equilibrium, the sum of forces must vanish:
$$p(h)A - p(h + \Delta h)A - \rho(h)g A \Delta h = 0 \tag{6}$$

Dividing by $A \Delta h$ and taking the limit as $\Delta h \to 0$ yields the **fundamental hydrostatic differential equation**:
$$\frac{dp}{dh} = -\rho(h) g \tag{7}$$

### Equation of State
By the ideal gas law, pressure, density, and temperature $T$ satisfy:
$$p = \frac{\rho}{\mu} R T \implies \rho = \frac{\mu p}{R T} \tag{8}$$
where $\mu$ is the molar mass of air and $R$ is the universal gas constant. 

Substituting equation (8) into equation (7) produces the separable differential equation:
$$\frac{dp}{dh} = -\frac{\mu g}{R T(h)} p(h) \tag{9}$$

$$\begin{gather}
\textbf{Proposition: Isothermal and Polytropic Barometric Formulas} \\[5mm]
\begin{align}
\text{1. Isothermal Atmosphere } (T(h) \equiv T_0)\text{:} \quad &p(h) = p_0 \exp\left( -\frac{\mu g}{R T_0} h \right). \\[3mm]
\text{2. Non-Isothermal Atmosphere } (T(h) = T_0 - \gamma h)\text{:} \quad &p(h) = p_0 \left( 1 - \frac{\gamma}{T_0} h \right)^{\frac{\mu g}{R\gamma}}.
\end{align}
\end{gather}$$
(see [[Derivation of the Isothermal and Non-Isothermal Barometric Formulas]])

---

# Example 3: Radioactive Decay, Chain Reactions, and Nuclear Reactors

### First-Order Disintegration Kinetics
Let $N(t)$ denote the number of radioactive nuclei present in an ore sample at time $t$. The probability of any individual nucleus decaying in an infinitesimal time window $[t, t + \Delta t]$ is a constant $\lambda \Delta t + o(\Delta t)$, where $\lambda > 0$ is the decay constant.

Over the increment $\Delta t$, the expected change in nuclei is $\Delta N = -\lambda N(t) \Delta t + o(\Delta t)$. In the limit $\Delta t \to 0$:
$$\frac{dN}{dt} = -\lambda N(t) \tag{10}$$

Integrating equation (10) establishes the exponential decay law:
$$N(t) = N_0 e^{-\lambda t} \tag{11}$$
The half-life $T_{1/2}$ is the time required for half the sample to disintegrate:
$$N(T_{1/2}) = \frac{N_0}{2} \implies T_{1/2} = \frac{\ln 2}{\lambda} \tag{12}$$

### Nuclear Fission Reactor Criticality
In a nuclear fission chain reaction, let $n(t)$ denote the neutron density inside a reactor core. Neutrons are produced by fission at a rate proportional to $n(t)$ ($\alpha n$), absorbed by control materials ($\beta n$), and leak through the reactor boundary ($\gamma n$):
$$\frac{dn}{dt} = (\alpha - \beta - \gamma) n(t) = k_{\text{eff}} n(t) \tag{13}$$

$$\begin{gather}
\textbf{Proposition: The Criticality Condition of a Nuclear Reactor} \\[5mm]
\begin{align}
k_{\text{eff}} < 0 \implies &n(t) = n_0 e^{-|k_{\text{eff}}|t} \to 0 \quad (\text{Subcritical: reaction terminates}), \\[2mm]
k_{\text{eff}} = 0 \implies &n(t) \equiv n_0 \quad (\text{Critical: stationary sustained power generation}), \\[2mm]
k_{\text{eff}} > 0 \implies &n(t) = n_0 e^{k_{\text{eff}}t} \to \infty \quad (\text{Supercritical: runaway exponential explosion}).
\end{align}
\end{gather}$$
(see [[Derivation of the Radioactive Decay Law and Nuclear Reactor Criticality]])

---

# Example 4: Falling Bodies in the Atmosphere

### The Equation of Motion Under Drag Forces
Consider a body of mass $m$ falling vertically downward through the atmosphere under gravity. Taking the downward vertical axis as positive, Newton's second law reads:
$$m \frac{dv}{dt} = mg - F_{\text{drag}}(v) \tag{14}$$

Depending on the Reynolds number, atmospheric resistance is governed by two physical regimes:
1. **Linear Drag (Stokes regime)**: $F_{\text{drag}} = k_1 v$ (valid for small particles or high viscosity).
2. **Quadratic Aerodynamic Drag (Newton regime)**: $F_{\text{drag}} = k_2 v^2$ (valid for macroscopic bodies and parachutists).

$$\begin{gather}
\textbf{Proposition: Trajectories Under Atmospheric Drag} \\[5mm]
\begin{align}
\text{1. Linear Drag } \left(m \dot{v} = mg - k_1 v\right)\text{:} \quad &v(t) = v_\infty \left( 1 - e^{-\frac{k_1}{m} t} \right), \quad \text{where } v_\infty = \frac{mg}{k_1}. \\[3mm]
\text{2. Quadratic Drag } \left(m \dot{v} = mg - k_2 v^2\right)\text{:} \quad &v(t) = v_\infty \tanh\left( \frac{gt}{v_\infty} \right), \quad \text{where } v_\infty = \sqrt{\frac{mg}{k_2}}.
\end{align}
\end{gather}$$
(see [[Derivation of the Trajectories of Falling Bodies Under Linear and Quadratic Drag]])

In both regimes, as $t \to \infty$, the acceleration vanishes ($\dot{v} \to 0$), and the velocity converges monotonically to the asymptotic **terminal velocity** $v_\infty$.

---

# Example 5: The Number $e$ and the Exponential Differential Equation Revisited

### Characterization of the Exponential Function
In Module 2, the number $e$ was defined as the limit of the sequence $\left(1 + \frac{1}{n}\right)^n$. We now characterize the function $f(x) = e^{\alpha x}$ dynamically as the unique solution to the initial value problem:
$$y'(x) = \alpha y(x), \quad y(0) = y_0 \tag{15}$$

$$\begin{gather}
\textbf{Theorem: Uniqueness of the Exponential Growth Operator} \\[5mm]
\text{Let } \alpha \in \mathbb{R} \text{ and } y_0 \in \mathbb{R}. \text{ The only differentiable function } f: \mathbb{R} \to \mathbb{R} \text{ satisfying:} \\[3.5mm]
f'(x) = \alpha f(x) \quad \forall x \in \mathbb{R}, \quad \text{with } f(0) = y_0, \\[3.5mm]
\text{is the function } f(x) = y_0 e^{\alpha x}.
\end{gather}$$
(see [[Proof of the Uniqueness and Existence of the Exponential Differential Equation Solution]])

### The Euler Polygonal Approximations
Discretize the interval $[0, x]$ into $n$ uniform steps of size $h = \frac{x}{n}$. Replacing the derivative in equation (15) with the forward finite difference:
$$\frac{y_{k+1} - y_k}{h} = \alpha y_k \implies y_{k+1} = (1 + \alpha h) y_k = \left( 1 + \frac{\alpha x}{n} \right) y_k \tag{16}$$
Iterating $n$ steps from $y_0$:
$$y_n = y_0 \left( 1 + \frac{\alpha x}{n} \right)^n \tag{17}$$
Taking the limit as $n \to \infty$:
$$y(x) = \lim_{n \to \infty} y_0 \left( 1 + \frac{\alpha x}{n} \right)^n = y_0 e^{\alpha x} \tag{18}$$
recovering the fundamental exponential limit from Module 2 as the continuum limit of Euler polygonal integration.

---

# Example 6: Oscillations (Harmonic and Damped Dynamics)

### The Classical Harmonic Oscillator
Consider a particle of mass $m$ attached to a linear spring with spring constant $k > 0$. By Hooke's law, the restoring force is $F = -kx$. Newton's second law yields:
$$m \ddot{x} + kx = 0 \implies \ddot{x} + \omega_0^2 x = 0, \quad \text{where } \omega_0 = \sqrt{\frac{k}{m}} \tag{19}$$

Multiplying equation (19) by $\dot{x}$ reveals the exact derivative of total mechanical energy:
$$\dot{x} \ddot{x} + \omega_0^2 x \dot{x} = 0 \implies \frac{d}{dt}\left[ \frac{1}{2}m\dot{x}^2 + \frac{1}{2}k x^2 \right] = 0 \tag{20}$$
proving that the total mechanical energy $E = \frac{1}{2}m v^2 + \frac{1}{2}k x^2$ is an invariant of motion.

### Damped Oscillations and Phase Space Regimes
In the presence of viscous friction $F_{\text{friction}} = -2m\gamma \dot{x}$ ($\gamma > 0$):
$$\ddot{x} + 2\gamma \dot{x} + \omega_0^2 x = 0 \tag{21}$$

Seeking solutions of the form $x(t) = e^{\lambda t}$, the characteristic algebraic equation in $\mathbb{C}$ is:
$$\lambda^2 + 2\gamma \lambda + \omega_0^2 = 0 \implies \lambda_{1, 2} = -\gamma \pm \sqrt{\gamma^2 - \omega_0^2} \tag{22}$$

$$\begin{gather}
\textbf{Proposition: Classification of Damped Oscillatory Regimes} \\[5mm]
\begin{align}
\text{1. Underdamped } (\gamma < \omega_0)\text{:} \quad &x(t) = A e^{-\gamma t} \cos(\omega t + \varphi_0), \quad \omega = \sqrt{\omega_0^2 - \gamma^2} \\[2mm]
&\text{(Damped quasi-periodic oscillation converging to 0).} \\[3mm]
\text{2. Critically Damped } (\gamma = \omega_0)\text{:} \quad &x(t) = (C_1 + C_2 t) e^{-\gamma t} \\[2mm]
&\text{(Fastest non-oscillatory return to equilibrium).} \\[3mm]
\text{3. Overdamped } (\gamma > \omega_0)\text{:} \quad &x(t) = C_1 e^{\lambda_1 t} + C_2 e^{\lambda_2 t} \quad (\lambda_1, \lambda_2 < 0) \\[2mm]
&\text{(Sluggish exponential decay dominated by the smaller exponent).}
\end{align}
\end{gather}$$
(see [[Derivation of the Phase Space Dynamics of Harmonic and Damped Oscillations]])
