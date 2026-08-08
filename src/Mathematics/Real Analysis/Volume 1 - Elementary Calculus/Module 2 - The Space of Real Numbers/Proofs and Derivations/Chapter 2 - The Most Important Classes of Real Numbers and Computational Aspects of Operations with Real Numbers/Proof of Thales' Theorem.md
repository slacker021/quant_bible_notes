---
dg-publish: true
---
Let $\triangle ABC$ be a non-degenerate triangle in the Euclidean plane. Let $D$ be an interior point on the side segment $\overline{AB}$, and let $E$ be an interior point on the side segment $\overline{AC}$, such that the line segment $\overline{DE}$ is parallel to the base $\overline{BC}$.

# Ratio of Triangle Areas with Shared Altitudes
Construct the line segments $\overline{BE}$ and $\overline{CD}$. Drop a perpendicular altitude from vertex $E$ to the line containing $\overline{AB}$, denoting its foot by $N$, such that $h_E = |\overline{EN}|$. Concurrently, drop a perpendicular altitude from vertex $D$ to the line containing $\overline{AC}$, denoting its foot by $M$, such that $h_D = |\overline{DM}|$.

Because triangles $\triangle ADE$ and $\triangle BDE$ share the common altitude $h_E$ perpendicular to the collinear base segments $\overline{AD}$ and $\overline{DB}$:
$$
\frac{\operatorname{Area}(\triangle ADE)}{\operatorname{Area}(\triangle BDE)} = \frac{\frac{1}{2} |\overline{AD}| \cdot h_E}{\frac{1}{2} |\overline{DB}| \cdot h_E} = \frac{|\overline{AD}|}{|\overline{DB}|} \tag{1}
$$
Similarly, because triangles $\triangle ADE$ and $\triangle CDE$ share the common altitude $h_D$ perpendicular to the collinear base segments $\overline{AE}$ and $\overline{EC}$:
$$
\frac{\operatorname{Area}(\triangle ADE)}{\operatorname{Area}(\triangle CDE)} = \frac{\frac{1}{2} |\overline{AE}| \cdot h_D}{\frac{1}{2} |\overline{EC}| \cdot h_D} = \frac{|\overline{AE}|}{|\overline{EC}|} \tag{2}
$$

# Equivalence of Base Triangles
Consider triangles $\triangle BDE$ and $\triangle CDE$. Both triangles share the identical base segment $\overline{DE}$. Because the segment $\overline{DE}$ is parallel to the line $\overline{BC}$, the perpendicular distance from vertex $B$ to the line containing $\overline{DE}$ equals the perpendicular distance from vertex $C$ to the line containing $\overline{DE}$. 

Consequently, both triangles possess identical altitudes relative to the common base $\overline{DE}$:
$$
\operatorname{Area}(\triangle BDE) = \operatorname{Area}(\triangle CDE) \tag{3}
$$

# Ratio Synthesis
Substituting step 3 into step 1 and step 2 equates the denominators of the left-hand ratios:
$$
\frac{|\overline{AD}|}{|\overline{DB}|} = \frac{|\overline{AE}|}{|\overline{EC}|} \tag{4}
$$
Adding unity to both sides of step 4 yields:
$$
\frac{|\overline{AD}| + |\overline{DB}|}{|\overline{DB}|} = \frac{|\overline{AE}| + |\overline{EC}|}{|\overline{EC}|} \implies \frac{|\overline{AB}|}{|\overline{DB}|} = \frac{|\overline{AC}|}{|\overline{EC}|} \tag{5}
$$
Inverting the ratios in step 4 and adding unity demonstrates that:
$$
\frac{|\overline{AB}|}{|\overline{AD}|} = \frac{|\overline{AC}|}{|\overline{AE}|} \tag{6}
$$
Therefore, a line parallel to one side of a triangle divides the remaining two sides in the identical ratio.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
