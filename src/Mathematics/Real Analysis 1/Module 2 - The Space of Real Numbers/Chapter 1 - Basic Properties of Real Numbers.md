---
dg-publish: true
---
# The Axiom System and Some General Properties of the Set of Real Numbers
Mathematical theories find application because they allow the transformation of one set of numbers—the initial data or collection of inputs—into another set, representing the intermediate or final objective of computations—which are usually seen as outputs. Thus, numerical-valued functions hold a distinguished position in mathematics and its applications. These functionsform the core subject of classical real analysis. However, a complete description of these functions' properties necessitates a precise definition of the set of real numbers on which they operate.

The concept of numbers is fundamental, yet achieving a rigorous understanding requires abstraction. This chapter aims to construct the universe of real numbers utilized in algebra and analysis in an unambiguous and axiomatic manner.

---
# Definition of the Set of Real Numbers

$$
\begin{gather}
\textbf{Definition: The Set of Real Numbers} \\[5mm]
\text{A set } \mathbb{R} \text{ is called the set of real numbers, and its elements are real numbers,} \\[2mm]
\text{if it satisfies the axioms of addition, multiplication, order, and completeness.}
\end{gather}
$$

In the realm of real numbers, *addition* and *multiplication* form the two fundamental binary operations. Additionally, the realm of real numbers is *ordered* and *complete*. 

>[!danger]+ Intuition: The Continuous Geometric Number Line and Operational Rigor
>In naive arithmetic, real numbers are often conceptualized as *infinite decimal expansions* or points along an unbroken geometric line. While this visual intuition provides geometric comfort, it introduces significant analytical ambiguities when defining operations like multiplication across non-terminating decimals, or formalizing the absence of *infinitesimal* gaps. 
>
>The axiomatic definition reverses this dependency: rather than defining real numbers by what they look like, real analysis characterizes them strictly by how they behave under operational transformations. A system is the real continuum if and only if it functions as a complete ordered field. If an algorithmic simulation or physical measurement space satisfies these axioms, every analytical theorem deduced from them holds with absolute mathematical certainty.

### The Field Axioms
The field axioms establish the algebraic mechanics of addition and multiplication upon $\mathbb{R}$, ensuring that elementary arithmetic operations can be inverted and combined consistently.

##### Axioms of Addition
$$
\begin{gather}
\textbf{Axioms of Addition} \\[5mm]
\text{An operation } +:\mathbb{R} \times \mathbb{R} \rightarrow \mathbb{R}, \text{ which is the operation of addition, is defined, assigning} \\[2mm]
\text{to each ordered pair } (x,y) \text{ of elements } x,y \in \mathbb{R} \text{ a certain element } x + y \in \mathbb{R}, \text{ which is the} \\[2mm]
\text{sum of } x \text{ and } y\text{. This operation satisfies the following conditions:}
\end{gather}
$$
$$
\begin{align}
& \text{1. There is a neutral element or identity element } 0 \text{, such that } \forall x \in \mathbb{R}: \\[3.5mm]
& \qquad x + 0 = 0 + x = x \\[3.5mm]
& \text{2. For every element } x \in \mathbb{R}\text{, there is an element } -x \in \mathbb{R} \text{ such that:} \\[3.5mm]
& \qquad x + (-x) = (-x) + x = 0 \\[3.5mm] 
& \text{3. The operation } + \text{ is associative, that is, } \forall x,y,z \in \mathbb{R}: \\[3.5mm]
& \qquad x + (y + z) = (x + y) + z \\[3.5mm] 
& \text{4. The operation } + \text{ is commutative, that is, } \forall x,y \in \mathbb{R}: \\[3.5mm]
& \qquad x + y = y + x
\end{align}
$$

>[!info]+ Remark: Additive and Abelian Group Structure
>If an operation defined on a set $G$ satisfies conditions 1 through 3, the algebraic structure $(G, +)$ is termed a *group*. If the group operation is addition, it is designated an *additive group*. When condition 4 holds, the group operation is commutative, and $G$ is called an *Abelian group* (named after *Niels Henrik Abel*). Consequently, the four axioms of addition establish that the set of real numbers $\mathbb{R}$ is an additive Abelian group.

>[!danger]+ Intuition: Subtraction as an Inverse Operation
>Subtraction is not an independent primitive operation within the real field. Instead, it is defined as the addition of the unique additive inverse:
>$$
>x - y := x + (-y) \tag{1}
>$$
>This formulation guarantees that the cancellation of quantities across mathematical systems is algebraically identical to translating an element backward along the real continuum by a magnitude matching its additive inverse.

>[!question]+ Application: Conservation Laws and Ledger Invariants
>The additive Abelian group structure $(\mathbb{R}, +)$ underpins all double-entry bookkeeping, multi-period cash accounting, and physical conservation principles. In quantitative finance, consider a portfolio cash ledger across $n$ transaction periods. Let $c_k \in \mathbb{R}$ represent the net cash flow at discrete time $t_k$, where inflows are positive and disbursements are negative:
>
>1. **Associativity:** Allows the portfolio manager to aggregate cash flows over arbitrary reporting windows (e.g., weekly sub-totals versus quarterly totals) without altering the terminal cash balance:
>$$
>(c_1 + c_2) + c_3 = c_1 + (c_2 + c_3) \tag{2}
>$$
>2. **Commutativity:** Guarantees that the net asset value of a clearing account is completely invariant to the order in which execution settlement tickets are ingested by the trade matching engine.
>3. **Additive Inverses:** Form the exact mechanism of risk neutralization and balance sheet reconciliation: to fully offset an exposure liability of $+L$, the risk desk must purchase an asset contract whose payout structure evaluates identically to $-L$, driving the combined systemic exposure $(L + (-L))$ to the neutral identity element $0$.

##### Axioms of Multiplication
$$
\begin{gather}
\textbf{Axioms of Multiplication} \\[5mm]
\text{An operation } \cdot : \mathbb{R} \times \mathbb{R} \rightarrow \mathbb{R}, \text{ which is the operation of multiplication, is defined,} \\[2mm]
\text{assigning to each ordered pair } (x,y) \text{ of elements } x,y \in \mathbb{R} \text{ a certain element } x \cdot y \in \mathbb{R}, \\[2mm]
\text{which is the product of } x \text{ and } y\text{. This operation satisfies the following conditions:}
\end{gather}
$$
$$
\begin{align}
& \text{1. There is a neutral element or identity element } 1 \in \mathbb{R} \setminus \{0\} \text{, such that } \forall x \in \mathbb{R}: \\[3.5mm]
& \qquad x \cdot 1 = 1 \cdot x = x \\[3.5mm]
& \text{2. For every element } x \in \mathbb{R} \setminus \{0\}\text{, there is an element } x^{-1} \in \mathbb{R} \text{, which is the reciprocal } \\[3.5mm] 
& \text{or multiplicative inverse of } x \text{ such that:} \\[3.5mm]
& \qquad x \cdot x^{-1} = x^{-1} \cdot x = 1 \\[3.5mm] 
& \text{3. The operation } \cdot \text{ is associative, that is, } \forall x,y,z \in \mathbb{R}: \\[3.5mm]
& \qquad x \cdot (y \cdot z) = (x \cdot y ) \cdot z \\[3.5mm] 
& \text{4. The operation } \cdot \text{ is commutative, that is, } \forall x,y \in \mathbb{R}: \\[3.5mm]
& \qquad x \cdot y = y \cdot x
\end{align}
$$

>[!info]+ Remark: Multiplicative Group
>Under the operation of multiplication, the set of non-zero real numbers $\mathbb{R} \setminus \{0\}$ forms an Abelian *multiplicative group*, denoted $(\mathbb{R} \setminus \{0\}, \cdot)$. The non-triviality condition $1 \neq 0$ is embedded directly in the specification $1 \in \mathbb{R} \setminus \{0\}$, ensuring the algebraic system does not collapse into a degenerate trivial ring containing only a single element.

>[!danger]+ Intuition: Division as Scaling by Reciprocals
>Similar to subtraction, division is not an independent primitive operation. To divide a real number $x$ by a non-zero real number $y$ is to scale $x$ by the unique multiplicative inverse $y^{-1}$:
>$$
>\frac{x}{y} := x \cdot y^{-1} \tag{3}
>$$
>Because zero possesses no multiplicative inverse, division by zero is strictly undefined within the field of real numbers.

>[!example]- Example: Force as a Relationship Between Mass and Acceleration
>In classical mechanics, the simplest way to model *force*, which may be described as a "push or a pull" done on an object, is expressed in the simple relationship of: 
>$$
>F = m \cdot a \tag{4}
>$$
>In the model described in step 4, $F$ is force, $m$ is the *mass* of the object (which is how much *matter* is packed into it), and $a$ is the *acceleration* (how fast the object changes speed.). While this model is rather simple as it does not account for other external factors, like *wind resistance*, it gives physicists the two main variables that affect the force applied by or to an object. As a convention, most physicists assume the following units of measurement: 
>- $F$ is measured in Newtons or $\text{N}$
>- $m$ is measured in Kilograms or $\text{kg}$
>- $a$ is measured in meters/second$^2$ or $\text{m/s}^2$
>
>As an example, suppose that a Dodge Challenger has a mass of $2,041 \text{ kilograms }$ and is accelerating at about $16.7336011 \text{ meters per second }^2$. The overall force generated by this car is: 
>$$
> \begin{align}
> F & = m \cdot a  \\[2mm]
>  & = 16.7336011 \text{ m/s}^2 \cdot 2,041 \text{ kg} \\[2mm]
>  & \approx 34,153.2798451 \text{ N} \tag{5}
> \end{align}
>$$ 
##### The Connection Between Addition and Multiplication
The algebraic operations of addition and multiplication are linked by the distributive law:
$$
\begin{gather}
\textbf{Axiom: The Connection Between Addition and Multiplication} \\[5mm]
(x + y)z = xz + yz \quad \forall x, y, z \in \mathbb{R}
\end{gather}
$$

>[!info]+ Remark: Commutativity of Multiplication and Fields
>By the commutativity of multiplication, the equality continues to hold if the order of factors is reversed on either side: $z(x + y) = zx + zy$. A set $F$ endowed with two operations satisfying the axioms of addition, multiplication, and distributivity is called a *field*. Thus, the algebraic system $(\mathbb{R}, +, \cdot)$ is a field.

>[!example]- Example: Distributivity in Classical Mechanics
>The interaction between addition and multiplication governed by the distributive law is fundamental to physical modeling. Consider a body of mass $m$ accelerating vertically upward against a uniform gravitational field (such as an elevator cab or a rocket during powered ascent).
>
>According to *Isaac Newton*'s *Second Law of Motion*, the total upward force $F$ required to accelerate the mass at a rate $a$ while overcoming the downward acceleration due to gravity $g$ is formulated as the product of the mass and the total effective acceleration:
>$$
>F = m(g + a) \tag{6}
>$$
>By the distributive axiom, multiplication distributes across addition:
>$$
>m(g + a) = mg + ma \tag{7}
>$$
>This algebraic equivalence demonstrates that computing the net force by first evaluating the total acceleration $(g + a)$ and scaling by the mass $m$ yields the exact same quantity as summing the gravitational force (weight) $F_g = mg$ and the dynamic accelerating force $F_a = ma$. Furthermore, by the commutativity of multiplication, $m(g + a) = (g + a)m$, and by the commutativity of addition, $g + a = a + g$.
>
>To illustrate this with metric units:
>* Mass of the object: $m = 50\text{ kg}$
>* Acceleration due to gravity: $g = 9.8\text{ m/s}^2$
>* Upward acceleration: $a = 2.2\text{ m/s}^2$
>
>**Method 1: Evaluating the combined acceleration first**
>$$
>\begin{align}
>g + a &= 9.8\text{ m/s}^2 + 2.2\text{ m/s}^2 = 12.0\text{ m/s}^2 \\[2mm]
>F &= 50\text{ kg} \cdot 12.0\text{ m/s}^2 = 600\text{ N} \tag{8}
>\end{align}
>$$
>
>**Method 2: Evaluating and summing the separate force components**
>$$
>\begin{align}
>F_g = mg &= 50\text{ kg} \cdot 9.8\text{ m/s}^2 = 490\text{ N} \\[2mm]
>F_a = ma &= 50\text{ kg} \cdot 2.2\text{ m/s}^2 = 110\text{ N} \\[2mm]
>F = mg + ma &= 490\text{ N} + 110\text{ N} = 600\text{ N} \tag{9}
>\end{align}
>$$
>where the derived SI unit of force is the newton ($1\text{ N} = 1\text{ kg}\cdot\text{m/s}^2$). Both calculations produce the identical terminal value of $600\text{ N}$, as guaranteed by the field axioms of the real numbers.

>[!example]- Example: Inverses and Field Structure in Electrical Network Admittance
>In electrical circuit engineering, *Georg Ohm*'s law and *Gustav Kirchhoff*'s circuit laws rely directly on the field structure of $\mathbb{R}$. Consider two electrical resistors connected in parallel across an applied direct current voltage $V$. Let the individual resistances be denoted $R_1, R_2 \in \mathbb{R}_{>0}$, measured in ohms ($\Omega$).
>
>The total equivalent resistance $R_{\text{eq}}$ of two parallel resistors satisfies the reciprocal sum relation:
>$$
>R_{\text{eq}}^{-1} = R_1^{-1} + R_2^{-1} \tag{10}
>$$
>The quantity $G = R^{-1}$ represents electrical conductance, measured in siemens ($\text{S}$). Conductance is the multiplicative inverse of resistance within the field $\mathbb{R}$.
>
>By the axioms of multiplication, because $R_1 \neq 0$ and $R_2 \neq 0$, the conductances $G_1 = R_1^{-1}$ and $G_2 = R_2^{-1}$ exist uniquely. Furthermore, the total equivalent conductance is the field sum:
>$$
>G_{\text{eq}} = G_1 + G_2 \tag{11}
>$$
>To isolate the equivalent resistance $R_{\text{eq}}$, the field inverse is applied to both sides:
>$$
>R_{\text{eq}} = (G_{\text{eq}})^{-1} = (R_1^{-1} + R_2^{-1})^{-1} \tag{12}
>$$
>Using field arithmetic, one can express the reciprocal sum by finding a common denominator via the distributive law and multiplicative units:
>$$
>R_1^{-1} + R_2^{-1} = R_1^{-1}(R_2 \cdot R_2^{-1}) + R_2^{-1}(R_1 \cdot R_1^{-1}) = \frac{R_2 + R_1}{R_1 R_2} \tag{13}
>$$
>Taking the reciprocal yields the standard engineering formula:
>$$
>R_{\text{eq}} = \frac{R_1 R_2}{R_1 + R_2} \tag{14}
>$$
>If $R_1 = 20\ \Omega$ and $R_2 = 30\ \Omega$, then:
>$$
>R_{\text{eq}} = \frac{20 \cdot 30}{20 + 30} = \frac{600}{50} = 12\ \Omega \tag{15}
>$$
>The existence, uniqueness, and consistency of this equivalent resistance depend entirely on the field properties of associativity, distributivity, and reciprocal inverses in $\mathbb{R}$.

---
# Order Axioms
In addition to algebraic operations, elements of $\mathbb{R}$ can be compared in terms of relative magnitude. This comparison is formalized through an ordering relation: 
$$
\begin{gather}
\textbf{Axioms of Ordering} \\[5mm]
\text{Between elements of } \mathbb{R} \text{ there is a binary relation } \le, \text{ meaning that for any ordered} \\[2mm]
\text{pair } (x,y) \in \mathbb{R} \times \mathbb{R}, \text{ one can determine whether } x \le y \text{ holds or not. This relation} \\[2mm]
\text{satisfies the following conditions:}
\end{gather}
$$
$$
\begin{align}
& \text{1. Reflexivity: } \forall x \in \mathbb{R}, \quad x \le x \\[2.5mm]
& \text{2. Antisymmetry: } \forall x, y \in \mathbb{R}, \quad (x \le y) \wedge (y \le x) \implies (x = y) \\[2.5mm]
& \text{3. Transitivity: } \forall x, y, z \in \mathbb{R}, \quad (x \le y) \wedge (y \le z) \implies (x \le z) \\[2.5mm]
& \text{4. Totality (Comparability): } \forall x, y \in \mathbb{R}, \quad (x \le y) \lor (y \le x)
\end{align}
$$

A set equipped with a binary relation satisfying conditions 1 through 3 is called a [[Chapter 3 - Cartesian Products and Relations|partially ordered set]] (poset). If, in addition, condition 4 holds, every pair of elements can be compared, and the set is said to be linearly ordered or totally ordered. Thus, the relation $\le$ defines a total order on $\mathbb{R}$.

The strict inequality $x < y$ is defined as $(x \le y) \wedge (x \ne y)$. The notation $x \ge y$ is logically equivalent to $y \le x$, and $x > y$ is equivalent to $y < x$.

>[!danger]+ Intuition: Total Ordering as Unambiguous State Evaluation
>A partial order permits ambiguity: two states can be mutually incomparable, like vector bundles or multi-criteria preferences. A total order eliminates incomparability entirely. For any two coordinates along the real line, either one strictly precedes the other, or they designate the exact same point. In empirical measurement, total ordering ensures that any physical scalar (temperature, mass, pressure) or financial variable (asset price, yield, portfolio return) can be ranked on a definitive one-dimensional scale.
>

>[!example]- Example: Avenger Versus Exorcist Class Grand Cruisers
>The *Imperium of Mankind* employs many classes of spacefaring vessels for various purposes, ranging from high-volume commerce to infantry transport. Among the classes of vessels is the *Grand Cruisers*, which is considered to be the largest class of space cruisers that can cruise through the Warp. Two notable examples of these cruisers are the *Avenger* and *Exorcist* classes. When it comes to measuring the acceleration of each cruiser, the Imperium of Mankind uses the *Gravity* $(G)$ as a unit of measurement. 
>
>Suppose that $A_{G}$ is the acceleration of the Avenger-class cruiser while $E_{G}$ is the acceleration of the Exorcist-class cruiser. The Imperium states that the Avenger-class has a max acceleration of $2.2 \ Gs$ while the Exorcist-class has a max acceleration of $1.99 \ Gs$. If the axioms of ordering hold, then the relationship between the two accelerations is: 
>$$
>A_{G} > E_{G} \text{ and } E_{G} < A_{G} \tag{16}
>$$
>In other words, the Avenger-class cruiser accelerates faster than the Exorcist-class cruiser. 

>[!question]+ Application: Price-Time Priority and Linear Order in Financial Exchanges
>Modern electronic financial exchanges organize incoming orders inside a Central Limit Order Book (CLOB). To execute transactions deterministically without ambiguity, the matching engine must project all competing trade interests onto a total order.
>
>Let an individual limit order $i$ be characterized by a bid price $p_i \in \mathbb{R}$, an arrival timestamp $t_i \in \mathbb{R}$, and a quantity $q_i \in \mathbb{R}_{>0}$. 
>1. The exchange defines a strict priority relation $\prec$ between competing buy orders:
>$$
>\text{Order } i \prec \text{Order } j \iff (p_i > p_j) \lor \big((p_i = p_j) \wedge (t_i < t_j)\big) \tag{17}
>$$
>2. Transitivity ensures that if order $i$ takes precedence over order $j$, and order $j$ takes precedence over order $k$, order $i$ executes before order $k$.
>3. Antisymmetry and totality ensure that no two non-identical limit tickets can create an execution stalemate. 
>
>The total ordering of $\mathbb{R}$ under $\le$ provides the unambiguous mathematical foundation enabling matching engines to clear transactions in nanoseconds without circular deadlocks.

### The Connection Between Order and Arithmetic Operations
The algebraic structure of the field and its total order relation are coupled through compatibility axioms:

$$
\begin{gather}
\textbf{Axioms: Connection of Order with Addition and Multiplication} \\[5mm]
\text{1. Additive Compatibility: } \forall x, y, z \in \mathbb{R}, \quad (x \le y) \implies (x + z \le y + z) \\[2mm]
\text{2. Multiplicative Compatibility: } \forall x, y \in \mathbb{R}, \quad (0 \le x) \wedge (0 \le y) \implies (0 \le x \cdot y)
\end{gather}
$$

>[!info]+ Remark: Ordered Fields
>A field $F$ endowed with a total order satisfying these two compatibility conditions is called an *ordered field*. Therefore, the algebraic system $(\mathbb{R}, +, \cdot, \le)$ is an ordered field.

>[!example]- Example: Compatibility of Order with Addition and Multiplication in Commodity Trade
>The axioms governing the connection of order with arithmetic operations ensure that elementary economic principles—such as cost aggregation, unit price comparison, and non-negative profit conditions—remain mathematically consistent.
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
>c_A \le s_A \quad \text{and} \quad c_O \le s_O \tag{18}
>$$
>Merchant B contracts to purchase non-negative inventory quantities $q_A \ge 0$ kilograms of apples and $q_O \ge 0$ kilograms of oranges from Merchant A.
>
>##### 1. Compatibility of Order with Multiplication (Scaling by Quantity)
>According to the multiplicative compatibility axiom, the product of non-negative elements remains non-negative:
>$$
>(0 \le x) \wedge (0 \le y) \implies 0 \le x \cdot y \tag{19}
>$$
>Because the markup margin $(s_A - c_A)$ is non-negative and the purchased mass $q_A$ is non-negative, the scaling property ensures that total revenue generated by apples dominates total acquisition cost:
>$$
>\begin{align}
>0 \le s_A - c_A \quad \wedge \quad 0 \le q_A &\implies 0 \le q_A(s_A - c_A) \\[2mm]
>&\implies q_A c_A \le q_A s_A \tag{20}
>\end{align}
>$$
>Applying the identical axiom to the orange inventory:
>$$
>q_O c_O \le q_O s_O \tag{21}
>$$
>This step guarantees that scaling an inequality by a non-negative quantity preserves the direction of the inequality.
>
>##### 2. Compatibility of Order with Addition (Inventory Aggregation)
>According to the additive compatibility axiom:
>$$
>(x \le y) \implies x + z \le y + z \quad \forall x,y,z \in \mathbb{R} \tag{22}
>$$
>A direct consequence of this axiom is the addition of simultaneous inequalities:
>$$
>(x_1 \le y_1) \wedge (x_2 \le y_2) \implies x_1 + x_2 \le y_1 + y_2 \tag{23}
>$$
>Setting $x_1 = q_A c_A$, $y_1 = q_A s_A$, $x_2 = q_O c_O$, and $y_2 = q_O s_O$, the combined expenditure and revenue across both fruit lines satisfy:
>$$
>q_A c_A + q_O c_O \le q_A s_A + q_O s_O \tag{24}
>$$
>Furthermore, suppose Merchant A charges a mandatory flat transportation surcharge $F \ge 0$ (in dollars) that Merchant B absorbs into the purchase cost and transfers to the customer. Adding $F$ to both sides preserves the inequality:
>$$
>(q_A c_A + q_O c_O) + F \le (q_A s_A + q_O s_O) + F \tag{25}
>$$
>Total gross expenditure never exceeds total gross revenue.
>
>##### 3. Numerical Computation with Metric Quantities
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
>\$160.00 &\le \$248.00 \tag{26}
>\end{align}
>$$
>
>**Step 2: Aggregate expenditure and revenue (Addition)**
>Summing the wholesale acquisition outlays paid to Merchant A:
>$$
>\text{Total Fruit Cost} = \$180.00 + \$160.00 = \$340.00 \tag{27}
>$$
>Summing the retail cash inflows received by Merchant B:
>$$
>\text{Total Fruit Revenue} = \$270.00 + \$248.00 = \$518.00 \tag{28}
>$$
>Since $\$180.00 \le \$270.00$ and $\$160.00 \le \$248.00$: 
>$$
>\$340.00 \le \$518.00 \tag{29}
>$$
>
>**Step 3: Inclusion of fixed transaction overhead**
>Adding the flat transport surcharge $F = \$35.00$ to both sides:
>$$
>\begin{align}
>\text{Total Outlay} &= \$340.00 + \$35.00 = \$375.00 \\[2mm]
>\text{Total Inflow} &= \$518.00 + \$35.00 = \$553.00 \\[2mm]
>\$375.00 &\le \$553.00 \tag{30}
>\end{align}
>$$
>The net operating profit realized by Merchant B:
>$$
>\Pi = \$553.00 - \$375.00 = \$178.00 \ge 0 \tag{31}
>$$
>This confirms that under non-negative procurement quantities and non-negative markups, the compatibility axioms of an ordered field guarantee that bilateral trade yields non-negative profit.

>[!example]- Example: Discrete Thermal Gradients and Order Preservation in Thermodynamics
>In the natural sciences, steady-state one-dimensional heat conduction across a homogeneous solid slab of thickness $\Delta x = x_2 - x_1 > 0$ bounded by parallel surfaces at coordinates $x_1 < x_2$ with uniform temperatures $T_1$ and $T_2$ is governed by *Jean-Baptiste Joseph Fourier*'s law of thermal conduction:
>$$
>q = -k \frac{\Delta T}{\Delta x} \tag{32}
>$$
>where $q$ is the conductive heat flux ($\text{W/m}^2$), $k \in \mathbb{R}_{>0}$ is the material's thermal conductivity ($\text{W}/(\text{m}\cdot\text{K})$), and $\Delta T = T_2 - T_1$ is the temperature difference across the slab.
>
>By the compatibility axioms of an ordered field:
>1. Suppose $T_1 > T_2$, meaning the temperature difference satisfies $\Delta T = T_2 - T_1 < 0$.
>2. Because the slab thickness $\Delta x = x_2 - x_1 > 0$ is strictly positive, its reciprocal is strictly positive: $(\Delta x)^{-1} > 0$.
>3. By multiplicative compatibility, the discrete spatial temperature ratio is strictly negative:
>$$
>\frac{\Delta T}{\Delta x} = \Delta T \cdot (\Delta x)^{-1} < 0 \tag{33}
>$$
>4. Thermal conductivity $k$ is an inherently positive physical constant ($k > 0$), meaning $-k < 0$.
>5. Multiplying the negative ratio in step 33 by the negative factor $-k$ yields a strictly positive conductive heat flux:
>$$
>q = -k \left(\frac{\Delta T}{\Delta x}\right) > 0 \tag{34}
>$$
>The compatibility of order with multiplication guarantees that thermal energy flows strictly from higher-temperature regions ($T_1$) toward lower-temperature regions ($T_2$), validating the *Rudolf Clausius* statement of the Second Law of Thermodynamics.

---
# The Axiom of Completeness (Continuity)
The rational numbers $\mathbb{Q}$ satisfy all field and order axioms, forming an ordered field. However, $\mathbb{Q}$ is inadequate for analysis because it contains "holes" or "gaps" (for example, there is no rational number $q \in \mathbb{Q}$ such that $q^2 = 2$). The final axiom of the real numbers guarantees continuity and the absence of gaps.

$$
\begin{gather}
\textbf{Axiom of Completeness (Dedekind Continuity)} \\[5mm]
\text{If } X \text{ and } Y \text{ are non-empty subsets of } \mathbb{R} \text{ such that for every } x \in X \text{ and} \\[2mm]
\text{every } y \in Y \text{ the relation } x \le y \text{ holds, then there exists an element } c \in \mathbb{R} \\[2mm]
\text{such that for all } x \in X \text{ and all } y \in Y: \\[3.5mm]
x \le c \le y
\end{gather}
$$

>[!info]+ Remark: Consistency and Categoricity
>The list of axioms defining the real numbers is now complete. Any set satisfying these axioms is a model of the real numbers. This axiomatic approach leads to two fundamental mathematical questions:
>
>1. **Consistency:** Does there exist a set satisfying all axioms without internal contradictions?
>2. **Categoricity:** Does this axiom system determine the real numbers uniquely?
>
>Uniqueness must be understood up to isomorphism. If two models of the real numbers are constructed independently, say $\mathbb{R}_A$ and $\mathbb{R}_B$, there exists a unique bijective mapping $f: \mathbb{R}_A \to \mathbb{R}_B$ that preserves the arithmetic operations and the order structure:
>$$
>\begin{gather}
>f(x + y) = f(x) + f(y), \\[2mm]
>f(x \cdot y) = f(x) \cdot f(y), \\[2mm]
>x \le y \iff f(x) \le f(y) \tag{35}
>\end{gather}
>$$
>Such a mapping is an *ordered field isomorphism*. Consequently, all models of the real numbers—whether constructed via *Richard Dedekind* cuts of rational numbers or equivalence classes of *Augustin-Louis Cauchy* sequences of rationals—are structurally identical.

>[!danger]+ Intuition: The Continuous Continuum vs. The Punctured Rationals
>The distinction between the rational field $\mathbb{Q}$ and the real field $\mathbb{R}$ is the property of completeness. Consider partitioning $\mathbb{Q}$ into two non-empty sets:
>$$
>X = \{q \in \mathbb{Q} \mid q \le 0 \lor q^2 < 2\}, \qquad Y = \{q \in \mathbb{Q} \mid q > 0 \wedge q^2 > 2\} \tag{36}
>$$
>Every rational in $X$ is strictly smaller than every rational in $Y$. However, within the rational field $\mathbb{Q}$, there exists no rational separating element $c \in \mathbb{Q}$ such that $x \le c \le y$ for all $x \in X, y \in Y$, because such a number would require $c^2 = 2$, which has no solution in $\mathbb{Q}$. The rational number line is filled with missing points. 
>
>The Dedekind completeness axiom guarantees that in $\mathbb{R}$, no such gaps exist. Every separation of sets has at least one real point standing between them. 

---
# General Algebraic Properties of Real Numbers
From the axioms of addition, multiplication, order, and completeness, numerous algebraic properties can be deduced.

$$
\begin{gather}
\textbf{Proposition: Consequences of the Addition Axioms} \\[5mm]
\text{1. The additive neutral element } 0 \text{ is unique.} \\[2mm]
\text{2. For each element } x \in \mathbb{R}, \text{ the additive inverse } -x \text{ is unique.} \\[2mm]
\text{3. For any } a, b \in \mathbb{R}, \text{ the equation } a + x = b \text{ has the unique solution } x = b + (-a) =: b - a.
\end{gather}
$$
(see [[Proof of Consequences of Addition Axioms]])

$$
\begin{gather}
\textbf{Proposition: Consequences of the Multiplication Axioms} \\[5mm]
\text{1. The multiplicative identity element } 1 \text{ is unique.} \\[2mm]
\text{2. For each } x \in \mathbb{R} \setminus \{0\}, \text{ the reciprocal } x^{-1} \text{ is unique.} \\[2mm]
\text{3. For any } a \in \mathbb{R} \setminus \{0\} \text{ and } b \in \mathbb{R}, \text{ the equation } a \cdot x = b \text{ has the unique} \\[2mm]
\text{solution } x = b \cdot a^{-1} =: \frac{b}{a}.
\end{gather}
$$
(see [[Proof of Consequences of Multiplication Axioms]])

$$
\begin{gather}
\textbf{Proposition: Consequences of the Connection Axiom} \\[5mm]
\text{For any elements } x, y \in \mathbb{R}: \\[3.5mm]
\text{1. } x \cdot 0 = 0 \cdot x = 0 \\[2mm]
\text{2. } (x \cdot y = 0) \implies (x = 0) \lor (y = 0) \\[2mm]
\text{3. } -x = (-1) \cdot x \\[2mm]
\text{4. } (-1)(-x) = x \\[2mm]
\text{5. } (-x) \cdot y = -(x \cdot y) \quad \text{and} \quad (-x) \cdot (-y) = x \cdot y
\end{gather}
$$
(see [[Proof of the Consequences of Connection Axioms]])

$$
\begin{gather}
\textbf{Proposition: Consequences of the Order Axioms} \\[5mm]
\text{1. Trichotomy: For any } x, y \in \mathbb{R}, \text{ precisely one of the following relations holds:} \\[2mm]
x < y, \quad x = y, \quad x > y \\[3.5mm]
\text{2. Strict Transitivity: For any } x, y, z \in \mathbb{R}: \\[2mm]
(x < y) \wedge (y \le z) \implies (x < z) \\[2mm]
(x \le y) \wedge (y < z) \implies (x < z)
\end{gather}
$$
(see [[Proof of Consequences of Order Axioms]])

$$
\begin{gather}
\textbf{Proposition: Consequences of Order with Addition and Multiplication} \\[5mm]
\text{For any } x, y, z, w \in \mathbb{R}: \\[3.5mm]
\text{1. } (x < y) \implies (x + z < y + z) \\[2mm]
\text{2. } (0 < x) \implies (-x < 0) \\[2mm]
\text{3. } (x \le y) \wedge (z \le w) \implies (x + z \le y + w) \\[2mm]
\text{4. } (x \le y) \wedge (z < w) \implies (x + z < y + w) \\[2mm]
\text{5. } (0 < x) \wedge (0 < y) \implies (0 < xy) \\[2mm]
\text{6. } (x < 0) \wedge (y < 0) \implies (0 < xy) \\[2mm]
\text{7. } (x < 0) \wedge (0 < y) \implies (xy < 0) \\[2mm]
\text{8. } (x < y) \wedge (0 < z) \implies (xz < yz) \\[2mm]
\text{9. } (x < y) \wedge (z < 0) \implies (yz < xz) \\[2mm]
\text{10. } \forall x \in \mathbb{R} \setminus \{0\}, \quad x^2 > 0 \\[2mm]
\text{11. } 0 < 1 \\[2mm]
\text{12. } (0 < x) \implies (0 < x^{-1}) \\[2mm]
\text{13. } (0 < x) \wedge (x < y) \implies (0 < y^{-1}) \wedge (y^{-1} < x^{-1})
\end{gather}
$$
(see [[Proof of Consequences of Order with Addition and Multiplication]])

>[!danger]+ Intuition: Sign Inversion and Order Reversal
>When an inequality is scaled by a negative number, the ordering direction reverses: $x < y \wedge z < 0 \implies yz < xz$. This reflects the geometry of reflection across the neutral element $0$. Multiplying by a negative scalar combines a scaling factor with an inversion across the origin. Elements situated further to the right on the positive axis are projected further to the left on the negative axis.
>
>Similarly, taking reciprocals of strictly positive quantities reverses their order: $0 < x < y \implies 0 < y^{-1} < x^{-1}$. A larger denominator divides the multiplicative unit $1$ into smaller components.

---
# The Completeness Axiom and Bounds
While the set of real numbers is infinite, specific subsets can be bounded from above, from below, or both.

$$
\begin{gather}
\textbf{Definition: Bounded Sets} \\[5mm]
\text{A set } X \subset \mathbb{R} \text{ is bounded above (respectively, bounded below) if there exists a} \\[2mm]
\text{number } c \in \mathbb{R} \text{ such that } x \le c \text{ (respectively, } c \le x \text{) for all } x \in X. \\[3.5mm]
\text{The number } c \text{ is called an upper bound (majorant) or lower bound (minorant).} \\[2mm]
\text{A set bounded both above and below is called bounded.}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Maximal and Minimal Elements} \\[5mm]
\text{An element } a \in X \text{ is the largest or maximal element (denoted } \max X \text{) if:} \\[3.5mm]
(a = \max X) := (a \in X) \wedge \forall x \in X \, (x \le a) \\[3.5mm]
\text{Similarly, an element } a \in X \text{ is the smallest or minimal element (denoted } \min X \text{) if:} \\[3.5mm]
(a = \min X) := (a \in X) \wedge \forall x \in X \, (a \le x)
\end{gather}
$$

>[!info]+ Remark: Bounded Sets Without Extrema
>A set may be bounded above without possessing a maximal element. Consider the bounded subset of $\mathbb{R}$ defined by:
>$$
>X = \{x \in \mathbb{R} \mid 0 \le x < 1\} \tag{37}
>$$
>The set $X$ has a minimum element, $\min X = 0$, since $0 \in X$ and $0 \le x$ for all $x \in X$.
>
>However, $X$ has no maximum element. The number $1$ is an upper bound for $X$, but $1 \notin X$. Furthermore, for any candidate element $x \in X$, the arithmetic mean:
>$$
>x' = \frac{x + 1}{2} \tag{38}
>$$
>satisfies $x < x' < 1$, which establishes that $x' \in X$ and $x' > x$. Because every element in $X$ is strictly exceeded by another element in $X$, no maximal element can exist in $X$.

To characterize the boundary of bounded sets that lack extrema, analysis introduces the concepts of supremum and infimum:

$$
\begin{gather}
\textbf{Definition: Least Upper Bound and Greatest Lower Bound} \\[5mm]
\text{The least upper bound (supremum) of a set } X \subset \mathbb{R} \text{ bounded above is denoted } \sup X. \\[2mm]
\text{A number } s \in \mathbb{R} \text{ is the supremum of } X \text{ if and only if:} \\[3.5mm]
(s = \sup X) \iff \big(\forall x \in X \, (x \le s)\big) \wedge \big(\forall s' < s \ \exists x' \in X \, (s' < x')\big) \\[5mm]
\text{The greatest lower bound (infimum) of a set } X \subset \mathbb{R} \text{ bounded below is denoted } \inf X. \\[2mm]
\text{A number } i \in \mathbb{R} \text{ is the infimum of } X \text{ if and only if:} \\[3.5mm]
(i = \inf X) \iff \big(\forall x \in X \, (i \le x)\big) \wedge \big(\forall i' > i \ \exists x' \in X \, (x' < i')\big)
\end{gather}
$$

Equivalently, using an arbitrary tolerance $\varepsilon > 0$:
$$
\begin{align}
(s = \sup X) &\iff (\forall x \in X, \, x \le s) \wedge (\forall \varepsilon > 0, \, \exists x' \in X \text{ such that } x' > s - \varepsilon) \tag{39} \\[2mm]
(i = \inf X) &\iff (\forall x \in X, \, i \le x) \wedge (\forall \varepsilon > 0, \, \exists x' \in X \text{ such that } x' < i + \varepsilon) \tag{40}
\end{align}
$$

>[!info]+ Remark: Supremum as the Minimum of Upper Bounds
>Let $M(X) = \{c \in \mathbb{R} \mid \forall x \in X, \, x \le c\}$ denote the set of all upper bounds of $X$. If the set $M(X)$ possesses a minimum element, then:
>$$
>\sup X = \min M(X) = \min \{ c \in \mathbb{R} \mid \forall x \in X, \, x \le c \} \tag{41}
>$$
>Similarly, letting $m(X) = \{c \in \mathbb{R} \mid \forall x \in X, \, c \le x\}$ denote the set of all lower bounds of $X$:
>$$
>\inf X = \max m(X) = \max \{ c \in \mathbb{R} \mid \forall x \in X, \, c \le x \} \tag{42}
>$$
>The existence of these extrema is guaranteed by the following lemmas.

$$
\begin{gather}
\textbf{Lemma: The Least Upper Bound Principle} \\[5mm]
\text{Every non-empty set of real numbers that is bounded above has a unique least upper bound.}
\end{gather}
$$
(see [[Proof of Least Upper Bound Principle]])

$$
\begin{gather}
\textbf{Lemma: The Greatest Lower Bound Principle} \\[5mm]
\text{Every non-empty set of real numbers that is bounded below has a unique greatest lower bound.}
\end{gather}
$$
(see [[Proof of Greatest Lower Bound Principle]])

>[!danger]+ Intuition: Supremum as an Asymptotic Frontier
>The maximum of a set is an internal member ($a \in X$). The supremum is an external boundary point that the set can approach arbitrarily closely from below, even if it never touches it. 
>
>For the bounded set $U = \{x \in \mathbb{R} \mid 0 < x < 1\}$, $\sup U = 1$ and $\inf U = 0$. The supremum functions as an impassable structural barrier:
>1. No element inside the set can surpass $s$.
>2. Any attempt to lower the threshold to $s - \varepsilon$ (for any $\varepsilon > 0$) immediately fails, because the set contains elements $x' \in U$ satisfying $s - \varepsilon < x' \le s$.

>[!example]- Example: Invariants, Natural Bounds, and Absolute Zero in Physics
>In the physical sciences, fundamental laws often establish strict upper or lower bounds on scalar quantities:
>
>1. **Absolute Zero as an Infimum:** In thermodynamics, let $\mathcal{T} \subset \mathbb{R}$ represent the set of all attainable physical temperatures of a macroscopic system, measured in kelvins ($\text{K}$). The Third Law of Thermodynamics establishes that:
>$$
>T > 0\text{ K} \quad \forall T \in \mathcal{T} \tag{43}
>$$
>The set $\mathcal{T}$ is bounded below by $0\text{ K}$. Although experimental cryogenics can refrigerate systems to arbitrarily small positive temperatures $T < \varepsilon$ for any tolerance $\varepsilon > 0$, absolute zero cannot be attained in a finite sequence of thermodynamic operations. Hence:
>$$
>\inf \mathcal{T} = 0\text{ K}, \quad \text{while } \min \mathcal{T} \text{ does not exist.} \tag{44}
>$$
>2. **Speed of Light as a Relativistic Supremum:** In *Albert Einstein*'s special theory of relativity, the magnitude of the velocity $v$ of any massive body belongs to the set $\mathcal{V} = \{v \in \mathbb{R} \mid 0 \le v < c\}$, where $c = 299{,}792{,}458\text{ m/s}$ is the speed of light in vacuum. When a frame moving at speed $u \in \mathcal{V}$ boosts an object at relative speed $w \in \mathcal{V}$, the relativistic composition of velocities is given by the rational field expression:
>$$
>u \oplus w = \frac{u + w}{1 + \frac{uw}{c^2}} \tag{45}
>$$
>Because $0 \le u < c$ and $0 \le w < c$, the compatibility of order with multiplication guarantees $(c - u)(c - w) > 0$, which expands to $c(u + w) < c^2 + uw$, or equivalently $u \oplus w < c$. Thus, no finite composition of sub-luminal boosts can ever attain or exceed $c$, while speeds $v \in \mathcal{V}$ can approach $c - \varepsilon$ for any $\varepsilon > 0$:
>$$
>\sup \mathcal{V} = c, \quad \text{while } \max \mathcal{V} \text{ does not exist.} \tag{46}
>$$

>[!example]- Example: Bid-Ask Reservation Bounds and No-Arbitrage Clearing Prices in Finance
>In quantitative market microstructure and Bilateral Auction Theory, the Axiom of Completeness and the Least Upper Bound / Greatest Lower Bound Principles govern price discovery between competing liquidity providers:
>
>1. **Supremum of Bid Valuations and Infimum of Ask Reservations:** Consider an asset traded across a decentralizeddealer network. Let $B \subset \mathbb{R}$ denote the non-empty set of all buyer bid valuations (prices at which buyers are willing to purchase), and let $A \subset \mathbb{R}$ denote the non-empty set of all seller ask reservation prices (prices at which sellers are willing to sell). In an uncrossed market free of immediate arbitrage opportunities, every bid price is bounded above by every ask price:
>$$
>b \le a \quad \forall b \in B, \ \forall a \in A \tag{47}
>$$
>2. **Best Bid and Best Offer Frontiers:** Because any fixed ask $a_0 \in A$ serves as an upper bound for $B$, the Least Upper Bound Principle guarantees the existence of the unique *best bid* frontier $b^* = \sup B \in \mathbb{R}$. Symmetrically, because any fixed bid $b_0 \in B$ serves as a lower bound for $A$, the Greatest Lower Bound Principle guarantees the existence of the unique *best ask* frontier $a^* = \inf A \in \mathbb{R}$.
>3. **Dedekind Separation and Fair Clearing Prices:** Applying the Axiom of Completeness to the separated sets $B$ and $A$ ensures the existence of at least one equilibrium reference price $p^* \in \mathbb{R}$ separating all buyer bids from all seller asks:
>$$
>\sup B = b^* \le p^* \le a^* = \inf A \tag{48}
>$$
>The non-negative difference $s = a^* - b^* = \inf A - \sup B \ge 0$ defines the market *bid-ask spread*. Whenever $b^* = a^*$, the supremum of buyer valuations coincides with the infimum of seller reservation prices, pinning down a unique frictionless market-clearing price $p^* = b^* = a^*$.
