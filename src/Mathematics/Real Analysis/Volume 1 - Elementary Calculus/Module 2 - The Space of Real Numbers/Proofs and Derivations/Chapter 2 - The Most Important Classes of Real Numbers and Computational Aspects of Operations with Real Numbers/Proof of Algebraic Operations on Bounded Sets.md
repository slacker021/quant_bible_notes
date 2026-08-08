---
dg-publish: true
---
Let $A, B \subset \mathbb{R}$ be non-empty bounded subsets of the real numbers. The Minkowski sum is defined as $A + B := \{a + b \mid a \in A, b \in B\}$, and the Minkowski product is defined as $A \cdot B := \{a \cdot b \mid a \in A, b \in B\}$.

--------------------------------------------------------------------------------
# Proposition 1
### Supremum of the Minkowski Sum
Denote $M_A := \sup A$ and $M_B := \sup B$. By the definition of an upper bound: 
$$
\forall a \in A, \quad a \le M_A \tag{1}
$$
$$
\forall b \in B, \quad b \le M_B \tag{2}
$$
Adding these inequalities via the additive compatibility axiom yields: 
$$
a + b \le M_A + M_B \quad \forall a \in A, \, \forall b \in B \tag{3}
$$
Step 3 demonstrates that $M_A + M_B$ is an upper bound for $A + B$. Consequently, $\sup(A + B)$ exists in $\mathbb{R}$ and satisfies: 
$$
\sup(A + B) \le M_A + M_B \tag{4}
$$
To establish the reverse inequality, fix an arbitrary tolerance $\varepsilon > 0$. By the analytical characterization of the supremum, the quantities $M_A - \frac{\varepsilon}{2}$ and $M_B - \frac{\varepsilon}{2}$ fail to be upper bounds for $A$ and $B$, respectively. Therefore, there exist witness elements $a_\varepsilon \in A$ and $b_\varepsilon \in B$ such that: 
$$
a_\varepsilon > M_A - \frac{\varepsilon}{2} \quad \wedge \quad b_\varepsilon > M_B - \frac{\varepsilon}{2} \tag{5}
$$
Summing the inequalities in step 5 produces an element $(a_\varepsilon + b_\varepsilon) \in A + B$ satisfying: 
$$
a_\varepsilon + b_\varepsilon > (M_A + M_B) - \varepsilon \tag{6}
$$
Because $a_\varepsilon + b_\varepsilon \le \sup(A + B)$, step 6 implies that: 
$$
\sup(A + B) > (M_A + M_B) - \varepsilon \tag{7}
$$
Because step 4 and step 7 hold for every $\varepsilon > 0$, it follows that: 
$$
\sup(A + B) = M_A + M_B = \sup A + \sup B \tag{8}
$$

### Infimum of the Minkowski Sum
Denote $m_A := \inf A$ and $m_B := \inf B$. By the definition of a lower bound: 
$$
a \ge m_A \quad \wedge \quad b \ge m_B \quad \forall a \in A, \, \forall b \in B \tag{9}
$$
Summing these bounds gives $a + b \ge m_A + m_B$, proving that $m_A + m_B$ is a lower bound for $A + B$. Hence:
$$
\inf(A + B) \ge m_A + m_B \tag{10}
$$
For any $\varepsilon > 0$, there exist witness elements $a_\varepsilon' \in A$ and $b_\varepsilon' \in B$ such that $a_\varepsilon' < m_A + \frac{\varepsilon}{2}$ and $b_\varepsilon' < m_B + \frac{\varepsilon}{2}$. Summing these inequalities yields:
$$
a_\varepsilon' + b_\varepsilon' < (m_A + m_B) + \varepsilon \tag{11}
$$
Because $\inf(A + B) \le a_\varepsilon' + b_\varepsilon'$, step 11 establishes that $\inf(A + B) < (m_A + m_B) + \varepsilon$ for all $\varepsilon > 0$, forcing: 
$$
\inf(A + B) = m_A + m_B = \inf A + \inf B \tag{12}
$$

--------------------------------------------------------------------------------
# Proposition 2
Let $A, B \subset \mathbb{R}_{\ge 0}$ be non-empty bounded sets of non-negative real numbers.

### Supremum of the Minkowski Product
Denote $M_A := \sup A$ and $M_B := \sup B$. Because $A, B \subset \mathbb{R}_{\ge 0}$, it follows that $M_A \ge 0$ and $M_B \ge 0$. For all $a \in A$ and $b \in B$, the relations $0 \le a \le M_A$ and $0 \le b \le M_B$ hold. By multiplicative compatibility:
$$
a \cdot b \le M_A \cdot M_B \quad \forall a \in A, \, \forall b \in B \tag{13}
$$
Thus, $M_A M_B$ is an upper bound for $A \cdot B$, establishing that: 
$$
\sup(A \cdot B) \le M_A \cdot M_B \tag{14}
$$
If $M_A = 0$ or $M_B = 0$, then $A = \{0\}$ or $B = \{0\}$, which implies $A \cdot B = \{0\}$ and $\sup(A \cdot B) = 0 = M_A M_B$. 

Suppose instead that $M_A > 0$ and $M_B > 0$. Fix an arbitrary $\varepsilon > 0$ and choose $\delta > 0$ satisfying: 
$$
\delta < \min \left\{ M_A, \, M_B, \, \frac{\varepsilon}{M_A + M_B} \right\} \tag{15}
$$
By definition of the supremum, there exist elements $a_\delta \in A$ and $b_\delta \in B$ such that $a_\delta > M_A - \delta > 0$ and $b_\delta > M_B - \delta > 0$. Multiplying these positive inequalities yields: 
$$
a_\delta \cdot b_\delta > (M_A - \delta)(M_B - \delta) = M_A M_B - \delta(M_A + M_B) + \delta^2 \tag{16}
$$
Because $\delta^2 > 0$ and $\delta(M_A + M_B) < \varepsilon$ by step 15, step 16 establishes that: 
$$
\sup(A \cdot B) \ge a_\delta \cdot b_\delta > M_A M_B - \varepsilon \tag{17}
$$
Because step 14 and step 17 hold for all $\varepsilon > 0$, it follows that: 
$$
\sup(A \cdot B) = (\sup A) \cdot (\sup B) \tag{18}
$$

### Infimum of the Minkowski Product
Denote $m_A := \inf A \ge 0$ and $m_B := \inf B \ge 0$. For all $a \in A$ and $b \in B$, the product satisfies $a \cdot b \ge m_A \cdot m_B$, proving: 
$$
\inf(A \cdot B) \ge m_A \cdot m_B \tag{19}
$$
Fix an arbitrary $\varepsilon > 0$ and select $\delta > 0$ such that $\delta(m_A + m_B + \delta) < \varepsilon$. There exist $a_\delta \in A$ and $b_\delta \in B$ satisfying $a_\delta < m_A + \delta$ and $b_\delta < m_B + \delta$. Their product satisfies: 
$$
a_\delta \cdot b_\delta < (m_A + \delta)(m_B + \delta) = m_A m_B + \delta(m_A + m_B + \delta) < m_A m_B + \varepsilon \tag{20}
$$
Because $\inf(A \cdot B) \le a_\delta \cdot b_\delta$, step 20 proves that $\inf(A \cdot B) < m_A m_B + \varepsilon$ for all $\varepsilon > 0$. Combining this with step 19 yields: 
$$
\inf(A \cdot B) = (\inf A) \cdot (\inf B) \tag{21}
$$
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
