---
dg-publish: true
---
Let $n \in \mathbb{N}$ with $n \ge 2$, and let $m_1, m_2, \dots, m_n > 0$ be constant point masses in $\mathbb{R}^3$. Let their trajectory curves $\vec{r}_i: I \to \mathbb{R}^3$ be twice differentiable with respect to time $t$ on an open time interval $I \subseteq \mathbb{R}$, with $\vec{r}_i(t) \neq \vec{r}_j(t)$ for all $i \neq j$ and all $t \in I$. 

Assume that the system obeys Newton's gravitational equations of motion:
$$
\begin{gather}
m_i \frac{d^2 \vec{r}_i}{dt^2} = -G \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j), \quad \forall i \in \{1, 2, \dots, n\} \tag{1}
\end{gather}
$$
where $G > 0$ denotes the universal gravitational constant.

Define the kinetic energy $K(t)$ and the potential energy $U(t)$ by:
$$
\begin{gather}
K(t) := \frac{1}{2} \sum_{i=1}^n m_i \left\|\frac{d\vec{r}_i}{dt}\right\|^2 = \frac{1}{2} \sum_{i=1}^n m_i \left(\frac{d\vec{r}_i}{dt} \cdot \frac{d\vec{r}_i}{dt}\right) \tag{2}
\end{gather}
$$
$$
\begin{gather}
U(t) := -\frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|} \tag{3}
\end{gather}
$$

The total mechanical energy of the gravitational system is defined by:
$$
\begin{gather}
E(t) := K(t) + U(t) \tag{4}
\end{gather}
$$

Differentiating the kinetic energy $K(t)$ of step 2 with respect to $t$ using the [[Proof of The Leibniz Product Rule|Leibniz Product Rule]] applied to the Euclidean dot product yields:
$$
\begin{gather}
\frac{d}{dt}\left(\frac{d\vec{r}_i}{dt} \cdot \frac{d\vec{r}_i}{dt}\right) = \frac{d^2 \vec{r}_i}{dt^2} \cdot \frac{d\vec{r}_i}{dt} + \frac{d\vec{r}_i}{dt} \cdot \frac{d^2 \vec{r}_i}{dt^2} = 2 \left(\frac{d\vec{r}_i}{dt} \cdot \frac{d^2 \vec{r}_i}{dt^2}\right) \tag{5}
\end{gather}
$$

Substituting step 5 into the derivative of step 2 gives:
$$
\begin{gather}
\frac{dK}{dt} = \frac{1}{2} \sum_{i=1}^n m_i \left[2 \left(\frac{d\vec{r}_i}{dt} \cdot \frac{d^2 \vec{r}_i}{dt^2}\right)\right] = \sum_{i=1}^n \frac{d\vec{r}_i}{dt} \cdot \left(m_i \frac{d^2 \vec{r}_i}{dt^2}\right) \tag{6}
\end{gather}
$$

Substituting Newton's law of motion from step 1 into step 6 produces:
$$
\begin{gather}
\frac{dK}{dt} = \sum_{i=1}^n \frac{d\vec{r}_i}{dt} \cdot \left[-G \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j)\right] = -G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} \tag{7}
\end{gather}
$$

Now consider the potential energy $U(t)$ in step 3. For any pair of distinct indices $i \neq j$, define the relative displacement vector $\vec{r}_{ij} := \vec{r}_i - \vec{r}_j$ and the scalar distance:
$$
\begin{gather}
r_{ij} := \|\vec{r}_i - \vec{r}_j\| = \sqrt{(\vec{r}_i - \vec{r}_j) \cdot (\vec{r}_i - \vec{r}_j)} \tag{8}
\end{gather}
$$

Differentiating $r_{ij}^2 = (\vec{r}_i - \vec{r}_j) \cdot (\vec{r}_i - \vec{r}_j)$ via the product rule yields:
$$
\begin{gather}
2 r_{ij} \frac{dr_{ij}}{dt} = 2 (\vec{r}_i - \vec{r}_j) \cdot \left(\frac{d\vec{r}_i}{dt} - \frac{d\vec{r}_j}{dt}\right) \implies \frac{dr_{ij}}{dt} = \frac{(\vec{r}_i - \vec{r}_j) \cdot \left(\dfrac{d\vec{r}_i}{dt} - \dfrac{d\vec{r}_j}{dt}\right)}{r_{ij}} \tag{9}
\end{gather}
$$

Applying the [[Proof of The Chain Rule|Chain Rule]] to the reciprocal distance $\frac{1}{r_{ij}}$ using step 9 gives:
$$
\begin{gather}
\frac{d}{dt}\left(\frac{1}{r_{ij}}\right) = -\frac{1}{r_{ij}^2} \frac{dr_{ij}}{dt} = -\frac{(\vec{r}_i - \vec{r}_j) \cdot \left(\dfrac{d\vec{r}_i}{dt} - \dfrac{d\vec{r}_j}{dt}\right)}{r_{ij}^3} \tag{10}
\end{gather}
$$

Differentiating the potential energy function of step 3 with respect to $t$ and substituting step 10 yields:
$$
\begin{gather}
\frac{dU}{dt} = -\frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} m_i m_j \frac{d}{dt}\left(\frac{1}{r_{ij}}\right) = \frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \left(\frac{d\vec{r}_i}{dt} - \frac{d\vec{r}_j}{dt}\right) \tag{11}
\end{gather}
$$

Distributing the inner product in step 11 produces two double sums:
$$
\begin{gather}
\frac{dU}{dt} = \frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} - \frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_j}{dt} \tag{12}
\end{gather}
$$

In the second double summation of step 12, interchanging the summation dummy indices $i$ and $j$ gives:
$$
\begin{gather}
\sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_j}{dt} = \sum_{j=1}^n \sum_{i \neq j} \frac{m_j m_i}{\|\vec{r}_j - \vec{r}_i\|^3} (\vec{r}_j - \vec{r}_i) \cdot \frac{d\vec{r}_i}{dt} \tag{13}
\end{gather}
$$

Because $\|\vec{r}_j - \vec{r}_i\| = \|\vec{r}_i - \vec{r}_j\|$, $m_j m_i = m_i m_j$, and $\vec{r}_j - \vec{r}_i = -(\vec{r}_i - \vec{r}_j)$, step 13 evaluates to:
$$
\begin{gather}
\sum_{j=1}^n \sum_{i \neq j} \frac{m_j m_i}{\|\vec{r}_j - \vec{r}_i\|^3} (\vec{r}_j - \vec{r}_i) \cdot \frac{d\vec{r}_i}{dt} = -\sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} \tag{14}
\end{gather}
$$

Substituting step 14 into the second term of step 12 produces:
$$
\begin{gather}
\frac{dU}{dt} = \frac{1}{2} G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} - \frac{1}{2} G \left[-\sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt}\right] \tag{15}
\end{gather}
$$

Combining the two identical terms in step 15 yields:
$$
\begin{gather}
\frac{dU}{dt} = G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} \tag{16}
\end{gather}
$$

Differentiating the total energy $E(t) = K(t) + U(t)$ by applying the sum rule to step 7 and step 16 yields:
$$
\begin{gather}
\frac{dE}{dt} = \frac{dK}{dt} + \frac{dU}{dt} = -G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} + G \sum_{i=1}^n \sum_{j \neq i} \frac{m_i m_j}{\|\vec{r}_i - \vec{r}_j\|^3} (\vec{r}_i - \vec{r}_j) \cdot \frac{d\vec{r}_i}{dt} = 0 \tag{17}
\end{gather}
$$

Because $\frac{dE}{dt} = 0$ identically on $I$, the total mechanical energy is constant over time: $E(t) \equiv \text{constant}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
