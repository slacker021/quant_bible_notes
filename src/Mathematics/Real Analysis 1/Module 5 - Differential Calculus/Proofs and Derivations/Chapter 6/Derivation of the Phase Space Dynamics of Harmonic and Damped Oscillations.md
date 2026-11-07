---
dg-publish: true
---
Consider the second-order homogeneous linear differential equation with constant real coefficients describing a damped harmonic oscillator:
$$
\begin{gather}
\ddot{x}(t) + 2\gamma \dot{x}(t) + \omega_0^2 x(t) = 0 \quad (\gamma > 0, \ \omega_0 > 0) \tag{1}
\end{gather}
$$

### Step 1: The Characteristic Algebraic Equation
Seeking exponential solutions of the form $x(t) = e^{\lambda t}$ for $\lambda \in \mathbb{C}$:
$$
\begin{gather}
\dot{x}(t) = \lambda e^{\lambda t}, \quad \ddot{x}(t) = \lambda^2 e^{\lambda t} \tag{2}
\end{gather}
$$

Substituting into the equation of step 1:
$$
\begin{gather}
(\lambda^2 + 2\gamma \lambda + \omega_0^2) e^{\lambda t} = 0 \tag{3}
\end{gather}
$$

Because $e^{\lambda t} \neq 0$, $\lambda$ must satisfy the quadratic characteristic equation:
$$
\begin{gather}
\lambda^2 + 2\gamma \lambda + \omega_0^2 = 0 \tag{4}
\end{gather}
$$

By the quadratic formula:
$$
\begin{gather}
\lambda_{1, 2} = -\gamma \pm \sqrt{\gamma^2 - \omega_0^2} \tag{5}
\end{gather}
$$

### Step 2: Underdamped Dynamics ($\gamma < \omega_0$)
When damping is weak, $\gamma^2 - \omega_0^2 < 0$. Define the modified angular frequency $\omega := \sqrt{\omega_0^2 - \gamma^2} > 0$. The characteristic roots are complex conjugates:
$$
\begin{gather}
\lambda_{1, 2} = -\gamma \pm i\omega \tag{6}
\end{gather}
$$

The general complex solution is:
$$
\begin{gather}
x_{\mathbb{C}}(t) = c_1 e^{(-\gamma + i\omega)t} + c_2 e^{(-\gamma - i\omega)t} = e^{-\gamma t} \big( c_1 e^{i\omega t} + c_2 e^{-i\omega t} \big) \tag{7}
\end{gather}
$$

Applying Euler's formula, $e^{\pm i\omega t} = \cos(\omega t) \pm i\sin(\omega t)$. Restricting to real-valued solutions yields the equivalent harmonic amplitude-phase representation:
$$
\begin{gather}
x(t) = A e^{-\gamma t} \cos(\omega t + \varphi_0) \tag{8}
\end{gather}
$$
where $A \ge 0$ and $\varphi_0 \in (-\pi, \pi]$ are determined by initial conditions $(x(0), \dot{x}(0))$. The trajectory describes a decaying sinusoidal oscillation with envelope $\pm A e^{-\gamma t} \to 0$.

### Step 3: Critically Damped Dynamics ($\gamma = \omega_0$)
When $\gamma = \omega_0$, the discriminant vanishes, yielding a repeated real root $\lambda = -\gamma$. 

One solution is $x_1(t) = e^{-\gamma t}$. Using the reduction of order method, set $x_2(t) = v(t) e^{-\gamma t}$. Substituting into the equation of step 1 yields $\ddot{v}(t) = 0 \implies v(t) = t$. Thus:
$$
\begin{gather}
x(t) = (C_1 + C_2 t) e^{-\gamma t} \tag{9}
\end{gather}
$$
The trajectory crosses the equilibrium point at most once before decaying exponentially to zero without sustained oscillation.

### Step 4: Overdamped Dynamics ($\gamma > \omega_0$)
When damping is strong, $\gamma^2 - \omega_0^2 > 0$. The roots are real and distinct:
$$
\begin{gather}
\lambda_1 = -\gamma + \sqrt{\gamma^2 - \omega_0^2} < 0, \quad \lambda_2 = -\gamma - \sqrt{\gamma^2 - \omega_0^2} < 0 \tag{10}
\end{gather}
$$
Because both roots are strictly negative, the general solution:
$$
\begin{gather}
x(t) = C_1 e^{\lambda_1 t} + C_2 e^{\lambda_2 t} \tag{11}
\end{gather}
$$
decays monotonically to zero as $t \to \infty$, dominated asymptotically by the slower decay mode $e^{\lambda_1 t}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
