---
dg-publish: true
---
# The Axiom System and Some General Properties of the Set of Real Numbers

Mathematical theories find application because they allow the transformation of one set of numbers—the initial data or collection of inputs—into another set, representing the intermediate or final objective of computations—which are usually seen as outputs. Thus, numerical-valued functions hold a distinguished position in mathematics and its applications. These functions, specifically differentiable ones, form the core subject of classical real analysis. However, a complete description of these functions' properties necessitates a precise definition of the set of real numbers on which they operate.

The concept of numbers is fundamental, yet achieving a rigorous understanding requires abstraction. This chapter aims to construct the universe of real numbers that are utilized in basic algebra and arithmetic, but in an unambiguous fashion. 

---
# Definition of the Set of Real Numbers

$$\begin{gather} \textbf{Definition: The Set of Real Numbers} \\[5mm] \text{A set } \mathbb{R} \text{ is called the set of real numbers, and its elements are real numbers,} \\ \text{if it satisfies the axioms of addition, multiplication, order, and completeness.} \end{gather}$$

In the realm of real numbers, *addition* and *multiplication* form the two basic operations that can be performed on the numbers. 

### The Field Axioms
The *field axioms* of the real numbers are a set of fundamental rules that provide the essential properties of arithmetic involving addition and subtraction, where both addition and multiplication fall under. 
##### Axioms of Addition
$$
\begin{gather}
\textbf{Axioms of Addition} \\[5mm]
\text{An operation } \\[2.5mm] +:\mathbb{R} \times \mathbb{R} \rightarrow \mathbb{R}, \\[2.5mm] \text{which is the operation of addition, is defined, assigning to each} 
\text{ordered pair } (x,y) \\ \text{ of elements } x,y \in \mathbb{R} \text{ a certain element } x + y \in \mathbb{R}\text{, which is the sum of } x \text{ and } y\text{.} \\
\text{This operation satisfies the following conditions: }
\end{gather}
$$
$$
\begin{align}
& \text{1. There is a neutral element or identity element } 0 \text{, which is zero, such that } \forall x \in \mathbb{R}: \\[2.5mm]
& \qquad x + 0 = 0 + x = x \\[2.5mm]
& \text{2. For every element } x \in \mathbb{R}\text{, there is an element } -x \in \mathbb{R} \text{ such that } \\[2.5mm]
& \qquad x + (-x) = (-x) + x = 0 \\[2.5mm] 
& \text{3. The operation } + \text{ is associative, that is, } \forall x,y,z \in \mathbb{R}: \\[2.5mm]
& \qquad x + (y + z) = (x + y) + z \\[2.5mm] 
& \text{4. The operation } + \text{ is commutative, that is, } \forall x,y \in \mathbb{R}: \\[2.5mm]
& \qquad x + y = y + x
\end{align}
$$

>[!info]+ Remark: Additive and Abelian Group 
>If an operation is defined on a set $G$ satisfying axioms 1–3, this is described as a *group structure* that is defined on $G$ or that $G$ is a group. If the operation is called addition, the group is an *additive group*. If it is also known that the operation is commutative, that is, condition 4 holds, the group is *commutative* or *Abelian*. Therefore, the four basic rules of addition assert that $\mathbb{R}$ is an additive Abelian group. 

>[!danger]+ Intuition: Subtraction
>Subtraction is merely a unique case of addition involving the addition of negative numbers:
>$$x - y := x + (-y) \tag{1}$$

##### Axioms of Multiplication
$$
\begin{gather}
\textbf{Axioms of Multiplication} \\[5mm]
\text{An operation } \\[2.5mm]
\cdot : \mathbb{R} \times \mathbb{R} \rightarrow \mathbb{R},  \\[2.5mm]
\text{which is the operation of multiplication, is defined, assigning to each ordered } \\
\text{pair } (x,y) \text{ of elements } x \text{ and } y \text{ of } \mathbb{R} \text{ a certain element } x \cdot y \in \mathbb{R}, \text{ which is the } \\
\text{product of } x \text{ and } y\text{. This operation satisfies the following conditions: }
\end{gather}
$$
$$
\begin{align}
& \text{1. There is a neutral element or identity element } 1 \in \mathbb{R} \setminus \{0\} \text{, which is one, such that } \forall x \in \mathbb{R}: \\[2.5mm]
& \qquad x \cdot 1 = 1 \cdot x = x \\[2.5mm]
& \text{2. For every element } x \in \mathbb{R} \setminus \{0\}\text{, there is an element } x^{-1} \in \mathbb{R} \text{, which is the reciprocal } \\[2.5mm] 
& \text{or multiplicative inverse of } x \text{ such that } \\[2.5mm]
& \qquad x \cdot x^{-1} = x^{-1} \cdot x = 1 \\[2.5mm] 
& \text{3. The operation } \cdot \text{ is associative, that is, } \forall x,y,z \in \mathbb{R}: \\[2.5mm]
& \qquad x \cdot (y \cdot z) = (x \cdot y ) \cdot z \\[2.5mm] 
& \text{4. The operation } \cdot \text{ is commutative, that is, } \forall x,y \in \mathbb{R}: \\[2.5mm]
& \qquad x \cdot y = y \cdot x \\[2.5mm]
& \text{5. The identity elements are non-trivial:} \\[2.5mm]
& \qquad 1 \ne 0
\end{align}
$$

>[!info]+ Remark: Multiplicative Group
>With respect to the operation of multiplication, the set of non-zero real numbers $\mathbb{R} \setminus \{0\}$, as one can verify, is a *multiplicative group*. 

>[!danger]+ Intuition: Division
>Similar to the case of subtraction, division is not an independent operation. To divide a real number $x$ by a non-zero real number $y$ is simply to multiply $x$ by the reciprocal $y^{-1}$:
>$$\frac{x}{y} := x \cdot y^{-1} \tag{2}$$

##### The Connection Between Addition and Multiplication
Addition and multiplication can be combined to perform more complex computations. The fundamental combined operation is the rule of multiplication being *distributive* with respect to addition:
$$
\begin{gather}
\textbf{Axiom: The Connection Between Addition and} \\
\textbf{Multiplication} \\[5mm]
(x + y)z = xz + yz \quad \forall x, y, z \in \mathbb{R}
\end{gather}
$$

>[!info]+ Remark: Commutativity of Multiplication
>By the commutativity of multiplication, this equality continues to hold if the order of the factors is reversed on either side. If two operations satisfying these axioms are defined on a set $G$, then $G$ is a *field*. 

>[!example]- Example: Distributivity in Classical Mechanics
>The interaction between addition and multiplication governed by the distributive law is fundamental to physical modeling. Consider a body of mass $m$ accelerating vertically upward against a uniform gravitational field (such as an elevator cab or a rocket during powered ascent).
>
>According to *Newton's Second Law of Motion*, the total upward force $F$ required to accelerate the mass at a rate $a$ while overcoming the downward acceleration due to gravity $g$ is formulated as the product of the mass and the total effective acceleration:
>$$
>\begin{gather}
>F = m(g + a) \tag{3}
>\end{gather}
>$$
>By the distributive axiom, multiplication distributes across addition:
>$$
>\begin{gather}
>m(g + a) = mg + ma \tag{4}
>\end{gather}
>$$
>This algebraic equivalence demonstrates that computing the net force by first evaluating the total acceleration $(g + a)$ and scaling by the mass $m$ yields the exact same quantity as summing the gravitational force (weight) $F_g = mg$ and the dynamic accelerating force $F_a = ma$. Furthermore, by the commutativity of multiplication, $m(g + a) = (g + a)m$, and by the commutativity of addition, $g + a = a + g$.
>
>To illustrate this with concrete metric units:
>* Mass of the object: $m = 50\text{ kg}$
>* Acceleration due to gravity: $g = 9.8\text{ m/s}^2$
>* Upward acceleration: $a = 2.2\text{ m/s}^2$
>
>**Method 1: Evaluating the combined acceleration first**
>$$
>\begin{align}
>g + a &= 9.8\text{ m/s}^2 + 2.2\text{ m/s}^2 = 12.0\text{ m/s}^2 \\[2mm]
>F &= 50\text{ kg} \cdot 12.0\text{ m/s}^2 = 600\text{ N} \tag{5}
>\end{align}
>$$
>
>**Method 2: Evaluating and summing the separate force components**
>$$
>\begin{align}
>F_g = mg &= 50\text{ kg} \cdot 9.8\text{ m/s}^2 = 490\text{ N} \\[2mm]
>F_a = ma &= 50\text{ kg} \cdot 2.2\text{ m/s}^2 = 110\text{ N} \\[2mm]
>F = mg + ma &= 490\text{ N} + 110\text{ N} = 600\text{ N} \tag{6}
>\end{align}
>$$
>where the derived SI unit of force is the newton ($1\text{ N} = 1\text{ kg}\cdot\text{m/s}^2$). Both calculations produce the identical terminal value of $600\text{ N}$, as guaranteed by the field axioms of the real numbers.

### Order Axioms
In addition to the basic operations of multiplication and addition, two values or expressions can be compared in terms of their relative magnitude. This involves the use of an ordering system, which gives rise to inequalities. Inequalities are based on the *Order Axioms*:
$$
\begin{gather}
\textbf{Axioms of Ordering: } \\[5mm]
\text{Between elements of } \mathbb{R} \text{ there is a relation } \leq, \text{ that is, for elements }  \\
x,y \in \mathbb{R} \text{ one can determine whether } x \leq y \text{ or not. For this to be true, } \\
\text{the following conditions must hold: }
\end{gather}
$$
$$
\begin{align}
\text{1. } & \forall x \in \mathbb{R} \ (x \leq x) \\
\text{2. } & (x \le y) \wedge (y \le x) \implies (x = y) \\
\text{3. } & (x \le y) \wedge (y \le z) \implies (x \le z) \\
\text{4. } & \forall x \in \mathbb{R} \ \forall y \in \mathbb{R} \ ((x \le y) \lor (y \le x))
\end{align}
$$
This relation $\leq$ on $\mathbb{R}$ is an *inequality*. A set on which there is a relation between pairs of elements satisfying Axioms 1–3 is *partially ordered*. If in addition Axiom 4 holds, that is, any two elements are comparable, then the set is *linearly ordered* (or *totally ordered*). Therefore, the set of real numbers is linearly ordered by the relation of inequality between elements. 

### The Connection Between Order and the Arithmetic Operations
The algebraic operations of addition and multiplication are linked to the order relation by the following compatibility axioms:
$$
\begin{gather}
\textbf{Axioms: Connection of Order with Addition and Multiplication} \\[5mm]
\text{1. } \forall x, y, z \in \mathbb{R}, \quad (x \le y) \implies (x + z \le y + z) \\[2.5mm]
\text{2. } \forall x, y \in \mathbb{R}, \quad (0 \le x) \wedge (0 \le y) \implies (0 \le x \cdot y)
\end{gather}
$$

>[!info]+ Remark: Ordered Field
>A field endowed with a total order satisfying these two compatibility conditions is called an *ordered field*. Thus, the set of real numbers $\mathbb{R}$ is an ordered field.

### The Axiom of Completeness (Continuity)
The final axiom of real numbers deals with *continuity*, which implies the absence of "gaps" or "holes" in the field of real numbers:
$$
\begin{gather}
\textbf{Axiom of Completeness (Dedekind Continuity): } \\[5mm]
\text{If } X \text{ and } Y \text{ are non-empty subsets of } \mathbb{R} \text{ having the property } \\
\text{that } x \leq y \text{ for all } x \in X \text{ and all } y \in Y\text{, then there exists } c \in \mathbb{R} \\
\text{such that } x \leq c \leq y \text{ for all } x \in X \text{ and all } y \in Y.
\end{gather}
$$

>[!info]+ Remark: Consistency and Categoricity 
>The list of axioms such that any set on which these axioms hold can be considered a concrete realization or model of the real numbers is now complete. This definition requires no prior knowledge about numbers. However, there is always the question of how it is to be determined that these axioms are consistent. After all, these principles are assumed to be true without proof. 
> 
>Someone who never learned how to count or measure line segments, or even knew the concept of numbers altogether, would view these axioms as arbitrary. This leads to two questions in relation to any abstract system of axioms: 
>1. Are these axioms consistent? That is, does there exist a set satisfying all the conditions just listed? This is the problem of consistency of the axioms.
>2. Does the given system of axioms determine the mathematical object uniquely? That is, as the logicians would say, is the axiom system categorical?
>
>Here, uniqueness must be understood as follows: If two people $A$ and $B$ construct models independently, say of number systems $\mathbb{R}_{A}$ and $\mathbb{R}_{B}$, satisfying the axioms, then a bijective correspondence can be established between the systems $\mathbb{R}_{A}$ and $\mathbb{R}_{B}$, say $f : \mathbb{R}_{A} \rightarrow \mathbb{R}_{B}$, preserving the arithmetic operations and the order, that is, 
>$$
>\begin{gather}
>f(x + y) = f(x) + f(y), \\
>f(x \cdot y) = f(x) \cdot f(y), \\
>x \leq y \iff f(x) \leq f(y).
>\end{gather}
>$$
>In this case, from the mathematical point of view, $\mathbb{R}_{A}$ and $\mathbb{R}_{B}$ are merely distinct but equally valid realizations of the real numbers. For example, $\mathbb{R}_{A}$ might be the set of infinite decimal fractions and $\mathbb{R}_{B}$ the set of points on the real number line. Such realizations are *isomorphic* and the mapping $f$ is an *isomorphism*. The result of this mathematical activity is not about any particular realization, but about each model in the class of isomorphic models of the given axiom system. The rest of this module will not focus on discussing the questions posed above, but instead confine itself to giving informative answers to them. 

>[!example]- Example: Compatibility of Order with Addition and Multiplication in Commodity Trade
>The axioms governing the connection of order with the arithmetic operations ensure that elementary economic principles—such as cost aggregation, unit price comparison, and non-negative profit conditions—remain mathematically consistent.
>
>Consider a commercial transaction between two market participants:
>* **Merchant A** operates as a wholesale orchard distributor.
>* **Merchant B** operates as a retail fruit vendor.
>
>Merchant B negotiates the procurement and sale of two fruit commodities: apples ($A$) and oranges ($O$). Let the unit wholesale purchase prices offered by Merchant A and the corresponding unit retail selling prices set by Merchant B be denoted as follows (expressed in dollars per kilogram, $\$ /\text{kg}$):
>* Wholesale purchase prices from Merchant A: $c_A$ and $c_O$
>* Retail selling prices charged by Merchant B: $s_A$ and $s_O$
>
>Assume that for each commodity, Merchant B maintains an individual price markup such that the retail selling price is greater than or equal to the wholesale procurement price:
>$$
>\begin{gather}
>c_A \le s_A \quad \text{and} \quad c_O \le s_O
>\end{gather}
>$$
>
>Merchant B contracts to purchase non-negative inventory quantities $q_A \ge 0$ kilograms of apples and $q_O \ge 0$ kilograms of oranges from Merchant A.
>
>##### 1. Compatibility of Order with Multiplication (Scaling by Quantity)
>According to the multiplicative compatibility axiom, the product of non-negative elements remains non-negative:
>$$
>\begin{gather}
>(0 \le x) \wedge (0 \le y) \implies 0 \le x \cdot y
>\end{gather}
>$$
>Because the markup margin $(s_A - c_A)$ is non-negative and the purchased mass $q_A$ is non-negative, the scaling property ensures that the total revenue generated by apples dominates total acquisition cost:
>$$
>\begin{align}
>0 \le s_A - c_A \quad \wedge \quad 0 \le q_A &\implies 0 \le q_A(s_A - c_A) \\[2mm]
>&\implies q_A c_A \le q_A s_A
>\end{align}
>$$
>Applying the identical axiom to the orange inventory:
>$$
>\begin{gather}
>q_O c_O \le q_O s_O
>\end{gather}
>$$
>This step guarantees that scaling an inequality by a non-negative quantity preserves the direction of the inequality.
>
>---
>
>##### 2. Compatibility of Order with Addition (Inventory Aggregation)
>According to the additive compatibility axiom:
>$$
>\begin{gather}
>(x \le y) \implies x + z \le y + z \quad \forall x,y,z \in \mathbb{R}
>\end{gather}
>$$
>A direct consequence of this axiom is the addition of simultaneous inequalities:
>$$
>\begin{gather}
>(x_1 \le y_1) \wedge (x_2 \le y_2) \implies x_1 + x_2 \le y_1 + y_2
>\end{gather}
>$$
>Setting $x_1 = q_A c_A$, $y_1 = q_A s_A$, $x_2 = q_O c_O$, and $y_2 = q_O s_O$, the combined expenditure and revenue across both fruit lines satisfy:
>$$
>\begin{gather}
>q_A c_A + q_O c_O \le q_A s_A + q_O s_O
>\end{gather}
>$$
>Furthermore, suppose Merchant A charges a mandatory flat transportation surcharge $F \ge 0$ (in dollars) that Merchant B absorbs into the purchase cost and transfers to the customer. Adding $F$ to both sides preserves the inequality:
>$$
>\begin{gather}
>(q_A c_A + q_O c_O) + F \le (q_A s_A + q_O s_O) + F
>\end{gather}
>$$
>Total gross expenditure never exceeds total gross revenue.
>
>---
>
>##### 3. Numerical Computation with Concrete Metric Quantities
>Let the transaction parameters between Merchant A and Merchant B be defined as follows:
>* **Apple inventory:** $q_A = 120\text{ kg}$, wholesale cost $c_A = \$1.50 /\text{kg}$, retail price $s_A = \$2.25 /\text{kg}$
>* **Orange inventory:** $q_O = 80\text{ kg}$, wholesale cost $c_O = \$2.00 /\text{kg}$, retail price $s_O = \$3.10 /\text{kg}$
>* **Fixed delivery fee:** $F = \$35.00$
>
>**Step 1: Commodity-level scaling (Multiplication)**
>$$
>\begin{align}
>\text{Apple Wholesale Cost:} \quad q_A c_A &= 120\text{ kg} \cdot \$1.50 /\text{kg} = \$180.00 \\[2mm]
>\text{Apple Retail Revenue:} \quad q_A s_A &= 120\text{ kg} \cdot \$2.25 /\text{kg} = \$270.00 \\[2mm]
>\$180.00 &\le \$270.00 \\[4mm]
>\text{Orange Wholesale Cost:} \quad q_O c_O &= 80\text{ kg} \cdot \$2.00 /\text{kg} = \$160.00 \\[2mm]
>\text{Orange Retail Revenue:} \quad q_O s_O &= 80\text{ kg} \cdot \$3.10 /\text{kg} = \$248.00 \\[2mm]
>\$160.00 &\le \$248.00
>\end{align}
>$$
>
>**Step 2: Aggregate expenditure and revenue (Addition)**
>Summing the wholesale acquisition outlays paid to Merchant A:
>$$
>\begin{gather}
>\text{Total Fruit Cost} = \$180.00 + \$160.00 = \$340.00
>\end{gather}
>$$
>Summing the retail cash inflows received by Merchant B:
>$$
>\begin{gather}
>\text{Total Fruit Revenue} = \$270.00 + \$248.00 = \$518.00
>\end{gather}
>$$
>Since $\$180.00 \le \$270.00$ and $\$160.00 \le \$248.00$:
>$$
>\begin{gather}
>\$340.00 \le \$518.00
>\end{gather}
>$$
>
>**Step 3: Inclusion of fixed transaction overhead**
>Adding the flat transport surcharge $F = \$35.00$ to both sides:
>$$
>\begin{align}
>\text{Total Outlay} &= \$340.00 + \$35.00 = \$375.00 \\[2mm]
>\text{Total Inflow} &= \$518.00 + \$35.00 = \$553.00 \\[2mm]
>\$375.00 &\le \$553.00
>\end{align}
>$$
>The net operating profit realized by Merchant B:
>$$
>\begin{gather}
>\Pi = \$553.00 - \$375.00 = \$178.00 \ge 0
>\end{gather}
>$$
>This confirms that under non-negative procurement quantities and non-negative markups, the compatibility axioms of an ordered field guarantee that bilateral trade yields non-negative profit.

---
# General Algebraic Properties of Real Numbers
Now that the axioms of addition, multiplication, order, and continuity have been established, useful facts can be deduced from these axioms that enable easier computation of real numbers. Beginning with useful facts for addition: 
$$\begin{gather} \textbf{Proposition: Consequences of the Addition Axioms} \\[5mm] \text{1. There is only one zero in the set of real numbers.} \\ \text{2. Each element of the set of real numbers has a unique negative.} \\ \text{3. In the set } \mathbb{R}, \text{ the equation } a + x = b \text{ has the unique solution } x = b + (-a) =: b - a. \end{gather}$$
(see [[Proof of Consequences of Addition Axioms|proof]])

$$\begin{gather} \textbf{Proposition: Consequences of the Multiplication Axioms} \\[5mm] \text{1. There is only one multiplicative unit (one) in the real numbers.} \\ \text{2. For each } x \ne 0, \text{ there is only one reciprocal } x^{-1}. \\ \text{3. For } a \in \mathbb{R} \setminus \{0\}, \text{ the equation } a \cdot x = b \text{ has the unique solution } x = b \cdot a^{-1} =: \frac{b}{a}. \end{gather}$$
(see [[Proof of Consequences of Multiplication Axioms|proof]])

$$\begin{gather} \textbf{Proposition: Consequences of the Connection Axiom} \\[5mm] \text{For any } x, y \in \mathbb{R}: \\ \text{1. } x \cdot 0 = 0 \cdot x = 0. \\ \text{2. } (x \cdot y = 0) \implies (x = 0) \lor (y = 0). \\ \text{3. } -x = (-1) \cdot x. \\ \text{4. } (-1)(-x) = x. \\ \text{5. } (-x) \cdot y = -(x \cdot y) \text{ and } (-x) \cdot (-y) = x \cdot y. \end{gather}$$
(see [[Proof of Consequences of Order Axioms|proof]])

$$\begin{gather} \textbf{Proposition: Consequences of the Order Axioms} \\[5mm] \text{Strict inequality } x < y \text{ denotes } (x \le y) \wedge (x \ne y). \\ \text{1. For any } x, y \in \mathbb{R}, \text{ precisely one relation holds: } x < y, \, x = y, \, x > y. \\ \text{2. For any } x, y, z \in \mathbb{R}: \\ (x < y) \wedge (y \le z) \implies (x < z), \\ (x \le y) \wedge (y < z) \implies (x < z). \end{gather}$$
(see [[Proof of Consequences of Order Axioms|proof]])

$$\begin{gather} \textbf{Proposition: Consequences of Order with Addition and Multiplication} \\[5mm] \text{For any } x, y, z, w \in \mathbb{R}: \\ \text{1. } (x < y) \implies (x + z < y + z) \\ \text{2. } (0 < x) \implies (-x < 0) \\ \text{3. } (x \le y) \wedge (z \le w) \implies (x + z \le y + w) \\ \text{4. } (x \le y) \wedge (z < w) \implies (x + z < y + w) \\ \text{5. } (0 < x) \wedge (0 < y) \implies (0 < xy) \\ \text{6. } (x < 0) \wedge (y < 0) \implies (0 < xy) \\ \text{7. } (x < 0) \wedge (0 < y) \implies (xy < 0) \\ \text{8. } (x < y) \wedge (0 < z) \implies (xz < yz) \\ \text{9. } (x < y) \wedge (z < 0) \implies (yz < xz) \\ \text{10. } 0 < 1 \\ \text{11. } (0 < x) \implies (0 < x^{-1}) \\ \text{12. } (0 < x) \wedge (x < y) \implies (0 < y^{-1}) \wedge (y^{-1} < x^{-1}) \end{gather}$$
(see [[Proof of Consequences of Order with Addition and Multiplication|proof]])

---
# The Completeness Axiom and Bounds
While the set of real numbers is infinite, it is nonetheless possible to construct subsets of it that are bounded. Such subsets may be finite or uncountably infinite (such as closed intervals). This is the principle of *bounding*: 
$$
\begin{gather}  
\textbf{Definition: Bounded Sets} \\[5mm]
\text{A set } X \subset \mathbb{R} \text{ is bounded above (respectively, bounded below) if there} \\ \text{exists a number } c \in \mathbb{R} \text{ such that } x \le c \text{ (respectively, } c \le x \text{) for all } x \in X. \\ \text{The number } c \text{ is called an upper bound (majorant) or lower bound (minorant).} \\ \text{A set bounded both above and below is called bounded.} 
\end{gather}
$$
Intuitively, the concept of bounded sets implies that some of them have a "largest" or "least" element that bounds the subset from above or below. This calls for the description of a *minimal* or *maximal* element that bounds said subset:
$$
\begin{gather}  
\textbf{Definition: Maximal and Minimal Elements} \\[5mm] 
\text{An element } a \in X \text{ is the largest or maximal element (} \max X \text{) if } x \le a \text{ for all } x \in X: \\[2.5mm] (a = \max X) := (a \in X) \wedge \forall x \in X \, (x \le a). \\[2.5mm] \text{Similarly, for the minimal element (} \min X \text{):} \\[2.5mm] (a = \min X) := (a \in X) \wedge \forall x \in X \, (a \le x). 
\end{gather}
$$

>[!info]+ Remark: Maximal and Minimal Elements
>Not every bounded set has a maximal or minimal element. For example, the half-open interval $X = \{x \in \mathbb{R} \mid 0 \le x < 1\}$ has no maximum. While it has a minimum of $0$, it has no maximum. The value $1$ is an upper bound, but $1 \notin X$. Furthermore, for any candidate element $x \in X$, the midpoint $x' = \frac{x + 1}{2}$ satisfies $x < x' < 1$, which proves that $x' \in X$ and $x' > x$. Because every element in $X$ is strictly exceeded by another element in $X$, no maximum element can exist within $X$.

$$
\begin{gather}
\textbf{Definition: Least Upper Bound and Greatest Lower Bound} \\[5mm]
\text{The least upper bound (supremum) of a set } X \text{ bounded above is denoted } \sup X: \\[2.5mm]
(s = \sup X) := \forall x \in X \, (x \le s) \wedge \forall s' < s \ \exists x' \in X \, (s' < x'). \\[2.5mm]
\text{The greatest lower bound (infimum) of a set } X \text{ bounded below is denoted } \inf X: \\[2.5mm]
(i = \inf X) := \forall x \in X \, (i \le x) \wedge \forall i' > i \ \exists x' \in X \, (x' < i').
\end{gather}
$$
The notation used for defining the least upper bound and greatest lower bound is somewhat verbose. This calls for a more concise formulation in terms of the extrema of the sets of bounds:
$$
\begin{gather}
\textbf{Definition: Least Upper and Greatest Lower Bound (Concise Version)} \\[5mm]
\sup X := \min \{ c \in \mathbb{R} \mid \forall x \in X \, (x \le c) \} \\[2.5mm]
\inf X := \max \{ c \in \mathbb{R} \mid \forall x \in X \, (c \le x) \}
\end{gather}
$$
Given that not every set has a minimal or maximal element, the definitions provided for the least upper bound and greatest lower bound require justification. This justification is provided in the following lemma:
$$
\begin{gather}
\textbf{Lemma: The Least Upper Bound Principle} \\[5mm]
\text{Every non-empty set of real numbers that is bounded from above has a} \\
\text{unique least upper bound.}
\end{gather}
$$
(see [[Proof of Least Upper Bound Principle|proof]])

Naturally, the existence and uniqueness of the greatest lower bound of a non-empty set of numbers that is bounded from below is analogous: 
$$
\begin{gather} 
\textbf{Lemma: The Greatest Lower Bound Principle} \\[5mm]
\text{Every non-empty set of real numbers that is bounded from below has a} \\
\text{unique greatest lower bound.}
\end{gather}
$$
(see [[Proof of Greatest Lower Bound Principle|proof]])