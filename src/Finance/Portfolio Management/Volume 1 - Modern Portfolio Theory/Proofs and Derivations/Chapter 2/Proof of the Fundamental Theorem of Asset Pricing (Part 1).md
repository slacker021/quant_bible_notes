---
dg-publish: true
---
The objective of this proof is to demonstrate the existence of a martingale measure $\mathbb{P}^Y$ guarantees the absence of arbitrage. This requires the three structural axioms of price that was established in the start of the second chapter: 
1.  **Inverse Price Symmetry:** $Y_X(t) = \frac{1}{X_Y(t)}$
2. **Change of Numeraire (Transitivity):** $X_Y(t) = X_Z(t) \cdot Z_Y(t)$
3. **Linearity of Asset Combinations:** $P_Z(t) = \sum_{i=0}^N \Delta^i(t) X_Z^i(t)$

###### Step 1: Portfolio Dynamics via Linearity (Axiom 3)
Consider a trading strategy holding quantities $\Delta^i(t)$ of no-arbitrage assets $X^i$ for $i = 0, 1, \dots, N$. Selecting $Y = X^0$ as the reference numeraire, the total portfolio value relative to $Y$ at time $t$ is expressed via [[Chapter 1 - Vector Space of Linear Maps|Linearity]] as:
$$P_Y(t) = \sum_{i=0}^N \Delta^i(t) X_Y^i(t) \tag{1}$$
For a self-financing portfolio, value changes are driven exclusively by shifts in underlying relative asset prices:
$$dP_Y(t) = \sum_{i=1}^N \Delta^i(t) \, dX_Y^i(t) \tag{2}$$
###### Step 2: Inheritance of the [[Chapter 4 - Filtrations and Martingales|Martingale]] Property
If each relative price process $X_Y^i(t)$ is a $\mathbb{P}^Y$-martingale, then by the linearity of conditional expectations and stochastic integration, the self-financing portfolio price process $P_Y(t)$ is likewise a martingale under measure $\mathbb{P}^Y$. Therefore, over the horizon $[0, T]$:
$$\mathbb{E}^{\mathbb{P}^Y} \left[ P_Y(T) \mid \mathcal{F}_0 \right] = P_Y(0) \tag{3}$$

###### Step 3: Proof of Contradiction (Absence of Arbitrage)
Formally, an **arbitrage opportunity** is defined as a self-financing trading strategy starting with zero initial capital ($P_Y(0) = 0$) such that terminal wealth satisfies:

$$P_Y(T) \ge 0 \quad \text{almost surely}, \quad \text{and} \quad \mathbb{P}^Y(P_Y(T) > 0) > 0 \tag{4}$$
Now evaluate the expected terminal value of this candidate arbitrage strategy under measure $\mathbb{P}^Y$: 
- Because $P_Y(t)$ is a $\mathbb{P}^Y$-martingale starting at $P_Y(0) = 0$, it must be that $\mathbb{E}^{\mathbb{P}^Y}[P_Y(T)] = 0$.
- However, if $P_Y(T) \ge 0$ almost surely and is strictly positive with positive probability ($\mathbb{P}^Y(P_Y(T) > 0) > 0$), the expectation must be strictly positive:
	$$\mathbb{E}^{\mathbb{P}^Y}[P_Y(T)] > 0\tag{5}$$
	This yields a direct mathematical contradiction ($0 > 0$). Thus, no arbitrage strategy can exist relative to numeraire $Y$ under measure $\mathbb{P}^Y$

###### Step 4: Frame Invariance via Transitivity and Symmetry (Axioms 1 & 2)
To confirm that the absence of arbitrage is a universal market property independent of reference frame, apply the **Change of Numeraire** relation to evaluate the portfolio under an alternative numeraire $Z$:
$$P_Z(t) = P_Y(t) \cdot Y_Z(t) \tag{6}$$
By **Inverse Price Symmetry**, $Y_Z(t) = \frac{1}{Z_Y(t)}$. Because numeraire assets are strictly positive ($0 < Z_Y(t) < \infty$), $Y_Z(t) > 0$ almost surely at all times. Consequently:
- $P_Y(0) = 0 \iff P_Z(0) = 0 \cdot Y_Z(0) = 0$
- $P_Y(T) \ge 0 \iff P_Z(T) = P_Y(T) \cdot Y_Z(T) \ge 0$

Because the sign of portfolio value is invariant under coordinate transformations, the absence of arbitrage holds universally across all reference assets in the economy. 
$$
\textbf{Q.E.D}
$$