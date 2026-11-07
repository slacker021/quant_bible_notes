---
dg-publish: true
---
Let the parabola be defined in Cartesian coordinates by the equation $y = f(x) = \frac{x^2}{2p}$, where $p > 0$. The focus of this parabola is located at $F = \left(0, \frac{p}{2}\right)$, and its directrix is the horizontal line $y = -\frac{p}{2}$.

Let $P_0 = (x_0, y_0) = \left(x_0, \frac{x_0^2}{2p}\right)$ with $x_0 \neq 0$ be an arbitrary point on the parabola. 

### Step 1: The Tangent Line Equation
Differentiating $f(x)$ at $x_0$:
$$
\begin{gather}
f'(x_0) = \lim_{h \to 0} \frac{\frac{(x_0 + h)^2}{2p} - \frac{x_0^2}{2p}}{h} = \lim_{h \to 0} \frac{2x_0 h + h^2}{2p h} = \frac{x_0}{p} \tag{1}
\end{gather}
$$

The tangent line $T$ passing through $P_0$ has slope $m = \frac{x_0}{p}$ and equation:
$$
\begin{gather}
y - y_0 = \frac{x_0}{p}(x - x_0) \tag{2}
\end{gather}
$$

Setting $x = 0$ in the equation of step 2, the $y$-intercept of the tangent line $T$ at the point $Q = (0, y_Q)$ is:
$$
\begin{gather}
y_Q = y_0 - \frac{x_0^2}{p} = \frac{x_0^2}{2p} - \frac{x_0^2}{p} = -\frac{x_0^2}{2p} = -y_0 \tag{3}
\end{gather}
$$

### Step 2: Distance Geometry and Rhombus Formation
Calculate the distance from the focus $F = \left(0, \frac{p}{2}\right)$ to the $y$-intercept $Q = (0, -y_0)$:
$$
\begin{gather}
|FQ| = \frac{p}{2} - (-y_0) = y_0 + \frac{p}{2} \tag{4}
\end{gather}
$$

Now calculate the Euclidean distance from the focus $F$ to the point $P_0 = (x_0, y_0)$:
$$
\begin{gather}
|FP_0| = \sqrt{(x_0 - 0)^2 + \left(y_0 - \frac{p}{2}\right)^2} = \sqrt{x_0^2 + y_0^2 - p y_0 + \frac{p^2}{4}} \tag{5}
\end{gather}
$$

Because $P_0$ lies on the parabola, $x_0^2 = 2p y_0$. Substituting this identity into the equation of step 5:
$$
\begin{gather}
|FP_0| = \sqrt{2p y_0 + y_0^2 - p y_0 + \frac{p^2}{4}} = \sqrt{y_0^2 + p y_0 + \frac{p^2}{4}} = \sqrt{\left(y_0 + \frac{p}{2}\right)^2} = y_0 + \frac{p}{2} \tag{6}
\end{gather}
$$

Comparing the equations of step 4 and step 6 establishes that:
$$
\begin{gather}
|FQ| = |FP_0| \tag{7}
\end{gather}
$$

### Step 3: Equality of Reflection Angles
The equation of step 7 proves that the triangle $\triangle F Q P_0$ is isosceles with base $Q P_0$. Consequently, the base angles are equal:
$$
\begin{gather}
\angle F Q P_0 = \angle F P_0 Q \tag{8}
\end{gather}
$$

Consider a vertical ray parallel to the axis of symmetry arriving from above at $P_0$, described by the vertical line $x = x_0$. Let $V$ be a point on this vertical line with $y_V > y_0$. The vertical line $x = x_0$ is parallel to the $y$-axis (the line containing $F$ and $Q$). 

Because the vertical ray $V P_0$ and the $y$-axis are parallel lines intersected by the transversal tangent line $T$ (the segment $Q P_0$), alternate interior angles are equal:
$$
\begin{gather}
\angle V P_0 T_{\text{ext}} = \angle F Q P_0 \tag{9}
\end{gather}
$$
where $\angle V P_0 T_{\text{ext}}$ denotes the angle made by the incoming vertical ray with the tangent line.

Combining the equations of step 8 and step 9:
$$
\begin{gather}
\angle V P_0 T_{\text{ext}} = \angle F P_0 Q \tag{10}
\end{gather}
$$

The equation of step 10 establishes that the angle of incidence between the incoming vertical ray and the tangent line equals the angle of reflection between the tangent line and the reflected focal ray $P_0 F$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
