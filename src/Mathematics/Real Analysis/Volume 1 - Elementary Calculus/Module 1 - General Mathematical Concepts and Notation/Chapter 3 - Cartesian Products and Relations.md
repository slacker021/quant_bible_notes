---
dg-publish: true
---
# Ordered Pairs and the Cartesian Product
For any two sets $A$ and $B$, a new set can be formed and denoted as $\{A,B \} = \{B,A \}$, representing an *unordered pair* of sets. This collection contains exactly two elements if $A \neq B$ and collapses to a single element if $A = B$. To inject directional orientation into set theory, the framework of the *ordered pair* must be established: 
$$
\begin{gather}
\textbf{Definition: Ordered Pair} \\[5mm]
\text{If } x \in X \text{ and } y \in Y, \text{ the ordered pair } (x,y) \text{ is the set defined by } \\[3.5mm]
(x,y) := \{\{ x \}, \{ x,y\} \}
\end{gather}
$$
The construction of the ordered pair represents a direct application of the [[Chapter 2 - Elementary Set Theory|Axiom of Pairing]]: 
- Applying the axiom to the elements $x$ and $x$ yields the singleton set $\{x\}$.
- Applying the axiom to the elements $x$ and $y$ yields the doubleton set $\{x, y\}$. 
- Applying the axiom a third time to the two resulting sets, $\{x\}$ and $\{x, y\}$, yields the Kuratowski ordered pair structure $\{\{x\}, \{x, y\}\}$.

This definition enforces algebraic directionality, satisfying the structural contract of ordered coordinates: 
$$
\begin{gather}
\textbf{Theorem: Fundamental Contract of Ordered Coordinates} \\[5mm]
(x, y) = (u,v) \iff (x = u) \wedge (y = v)
\end{gather}
$$
(see [[Proof of the Fundamental Contract of Ordered Coordinates|proof]])

Once the internal structure of an individual pair is formalized, the master universal set comprising all possible coordinate pairs can be constructed: 
$$
\begin{gather}
\textbf{Definition: Cartesian Product} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. The Cartesian Product of } X \text{ and } Y \text{ is the set}  \\[2mm]
\text{comprising all ordered pairs } (x,y) \text{ such that } x \in X \text{ and } y \in Y. \text{ Symbolically: } \\[3.5mm]
X \times Y := \{(x,y) \mid x \in X \wedge y \in Y \} = \{z \mid \exists x \in X, \exists y \in Y \text{ such that } z = (x,y) \}
\end{gather}
$$

It follows from this definition that, in general, the Cartesian product is non-commutative ($X \times Y \neq Y \times X$). Commutative equality is preserved if and only if $(X = Y) \lor (X = \emptyset) \lor (Y = \emptyset)$. In the special case where a set is crossed with itself, the shorthand notation $X \times X = X^2$ is deployed.

To rigorously justify the existence of the Cartesian product without relying on geometric intuition, the framework of the *Power Set* must be introduced:
$$
\begin{gather}
\textbf{Definition: Power Set} \\[5mm]
\text{Let } X \text{ be a set. The power set of } X, \text{ denoted as } \mathcal{P}(X) \text{ or } 2^X, \text{ is the set comprising } \\[2mm]
\text{all possible subsets of } X. \text{ Symbolically: } \\[3.5mm]
\mathcal{P}(X) := \{A \mid A \subset X \}
\end{gather}
$$
The existence of the power set is explicitly guaranteed by the fifth Zermelo-Fraenkel axiom. The power set framework provides the necessary bounding universe for the Cartesian product. If $x \in X$ and $y \in Y$, the Axiom of Pairing ensures that $\{x\}$ and $\{x,y\}$ are subsets of the universal union $X \cup Y$, rendering them elements of the power set $\mathcal{P}(X \cup Y)$. 

Consequently, the ordered pair itself functions as a subset of $\mathcal{P}(X \cup Y)$, forcing it to be a legal element of the double power set: $(x, y) \in \mathcal{P}(\mathcal{P}(X \cup Y))$. By invoking the Axiom Schema of Separation, the Cartesian product is formalized as a strictly bounded subset of this validated universe: 
$$X \times Y = \{ z \in \mathcal{P}(\mathcal{P}(X \cup Y)) \mid \exists x \in X, \exists y \in Y \text{ such that } z = (x, y) \} \tag{1}$$

>[!example]- Example: Geometric Interpretations of Different Types of Cartesian Products
>The following are geometric interpretations based on Cartesian Products. If $X \times Y$ is the set of all ordered pairs $(x,y)$ such that $x \in X \wedge y \in Y$, then these structures can be visualized through classic spatial dimensions: 
>**1. The product of two line segments:** Let $I_1 = [a, b]$ and $I_2 = [c, d]$ represent two bounded intervals on the real line $\mathbb{R}$. Their Cartesian product $I_1 \times I_2$ defines a bounded, solid rectangle embedded in the 2D plane $\mathbb{R}^2$, bounded by the vertical lines $x=a, x=b$ and horizontal lines $y=c, y=d$.
>**2. The product of two lines:** The Cartesian product $\mathbb{R} \times \mathbb{R}$ maps every pair of real numbers across two infinite dimensions. This yields the entire infinite 2D continuous space known as the Cartesian plane $\mathbb{R}^2$. 
>**3. The product of a line and a circle:** Let the line be represented by $\mathbb{R}$ and the circle by the 1-sphere $S^1$. The product $\mathbb{R} \times S^1$ matches each point along an infinite axis to a periodic circular path. Geometrically, this forms an infinitely long hollow cylindrical surface in 3D space.
>**4. The product of a line and a disk:** Replacing the hollow circle from the previous part with a filled 2D closed disk $D$, the product $\mathbb{R} \times D$ extends this filled circular area infinitely along a linear path. This creates an infinite solid cylinder.
>**5. The product of two circles:** The product of two circles: The product $S^1 \times S^1$ joins two independent periodic dimensions, creating the standard 2-torus ($T^2$). Visually, this is the hollow surface of a geometric doughnut.
>**6. The product of a circle and a disk:** By tracking the product of a circle $S^1$ and a filled disk $D$, the interior region is fully filled along the circular trajectory. This creates a solid torus—a solid 3D doughnut.

---
# Relations
The establishment of the Cartesian product allows for the formalization of connections between independent spaces:
$$
\begin{gather}
\textbf{Definition: Binary Relation} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. A binary relation } \mathcal{R} \text{ from } X \text{ to } Y \text{ is defined as any arbitrary } \\[2mm]
\text{subset of their Cartesian product. Symbolically: } \\[3.5mm]
\mathcal{R} \subset X \times Y \\[3.5mm] 
\text{The set } X \text{ designates the domain of the relation, while the set } Y \text{ designates the codomain.} \\[2mm]
\text{If the ordered pair } (x,y) \in \mathcal{R}, \text{ membership is denoted by the relational notation } x \mathcal{R} y.  \\[2mm]
\text{If } X = Y, \text{ the subset } \mathcal{R} \subset X^2 \text{ is referred to as a relation on } X. 
\end{gather}
$$

Because a relation is fundamentally a set of ordered pairs, all previously established algebraic laws governing set unions, intersections, and complements apply to relations universally. 

When analyzing a relation confined to a single set $X$, distinct structural properties manifest depending on the algebraic constraints imposed on the coordinate pairs. The first major structural class is the *equivalence relation*, which formalizes the conceptual notion of "sameness" or classification without requiring absolute identity: 
$$
\begin{gather}
\textbf{Definition: Equivalence Relation} \\[5mm]
\text{A relation } \mathcal{R} \text{ on a set } X \text{ is an equivalence relation if and only if the following } \\[2mm]
\text{three structural conditions are satisfied simultaneously for all } x, y, z \in X: \\[3.5mm]
\text{1. Reflexivity: } \forall x \in X \, (x \mathcal{R}x)  \\[2mm]
\text{2. Symmetry: } \forall x,y \in X \, (x\mathcal{R}y \implies y\mathcal{R}x)  \\[2mm]
\text{3. Transitivity: } \forall x, y,z \in X \, ((x\mathcal{R}y \wedge y \mathcal{R}z) \implies x\mathcal{R}z) 
\end{gather}
$$

Equivalence relations possess the unique property of clustering elements together based on shared characteristics. For any fixed element $x \in X$, the collection of all elements related to $x$ under $\mathcal{R}$ forms a distinct subset known as an *equivalence class*:
$$
\begin{gather}
\textbf{Definition: Equivalence Class} \\[5mm]
\text{For any fixed element } x \in X, \text{ the collection of all elements related to } x \\[2mm]
\text{under the equivalence relation } \mathcal{R} \text{ forms a distinct subset denoted as:} \\[3.5mm]
[x] := \{ y \in X \mid y\mathcal{R}x \}
\end{gather}
$$

While an equivalence relation offers an internal, element-wise mechanism for identifying shared properties, the structural organization of a space can be analyzed from a macro-topological perspective through the framework of *partitions*:
$$
\begin{gather}
\textbf{Definition: Partition of a Set} \\[5mm]
\text{Let } X \text{ be a non-empty set. A family } \mathcal{P} \text{ of subsets of } X \text{ is designated a partition of } \\[2mm]
X \text{ if and only if the following three conditions are satisfied:} \\[3.5mm]
\text{1. Non-emptiness: } \forall A \in \mathcal{P} \ (A \neq \emptyset) \\[2mm]
\text{2. Pairwise Disjointness: } \forall A, B \in \mathcal{P} \ (A \neq B \implies A \cap B = \emptyset) \\[2mm]
\text{3. Collective Exhaustiveness: } \bigcup_{A \in \mathcal{P}} A = X 
\end{gather}
$$

The concepts of an equivalence relation and a set-theoretic partition are fundamentally dual vantage points of the same structural reality. This relationship is formalized by the Fundamental Theorem of Equivalence Relations, which demonstrates that any equivalence relation $\mathcal{R}$ on a set $X$ uniquely partitions that set into a collection of pairwise disjoint equivalence classes, forming the quotient set $X / \mathcal{R}$. Conversely, any raw partition $\mathcal{P}$ of a set uniquely induces a corresponding equivalence relation by declaring two elements related if and only if they inhabit the same partition subset.

### Order Relations
*Ordering Relations* are rules used to compare, rank, or sort elements within a set. There're two types of order relations that are heavily used in real analysis: *Partial Order* and *Total (Linear) Order*. 
$$
\begin{gather}
\textbf{Definition: Partial Order} \\[5mm]
\text{A binary relation } \mathcal{R} \text{ is a partial order if and only if it is: } \\[3.5mm]
\text{1. Reflexive } (x \mathcal{R} x) \\[2mm]
\text{2. Transitivity } ( x \mathcal{R} y \wedge y \mathcal{R} z \implies x \mathcal{R} z ) \\[2mm]
\text{2. Antisymmetric } (x\mathcal{R}y \wedge y\mathcal{R}x \implies x = y) \\[3.5mm]
\text{If a set is paired with a partial order, then it is a poset, where some elements} \\[2mm]
\text{may be incomparable.}
\end{gather}
$$
The concept of *comparability* is critical in real analysis since it is built on the architecture of *inequalities*. The concept of comparability is introduced in the following axiom: 
$$
\begin{gather}
\textbf{Axiom: Principle of Comparability} \\[5mm]
\text{If } X^2 \subset \mathcal{R} \text{ and } x \in X \wedge y \in Y,  \\[2mm]
\text{then } \forall x \in X \wedge \forall y \in X (x \mathcal{R} y \lor y \mathcal{R} x)
\end{gather}
$$
This axiom can be used to construct a new type of order, an order where every single pair of elements in the universe can be explicitly compared with one another: 
$$
\begin{gather}
\textbf{Definition: Total (Linear) Order} \\[5mm]
\text{This is a stricter partial order that satisfies the  principle of comparability,} \\[2mm]
\text{guaranteeing that every single pair of elements in the universe can be explicitly compared. }
\end{gather}
$$
> [!info]+ Remark: 
> The standard inequality operator, which is $\geq$ or $\le$, is the definitive archetype of a total order, which is used in the realm of real numbers $\mathbb{R}$. 

---
# Useful Properties of Cartesian Products
The various definitions from this chapter can be used to construct several useful facts that expand the field of set theory:
$$
\begin{gather}
\textbf{Theorem:} \\[5mm]
\text{If } X \text{ and } Y \text{ are two sets, then } X \times Y = \emptyset \iff X = \emptyset \lor Y = \emptyset
\end{gather}
$$
(See [[Proof of the First Useful Property of Cartesian Products|proof]])
$$
\begin{gather}
\textbf{Theorem:} \\[5mm]
\text{If } X \times Y \neq \emptyset, \text{ then } A \times B \subset X \times Y \iff A \subset X \wedge B \subset Y
\end{gather}
$$
(See [[Proof of the Second Useful Property of Cartesian Products|proof]])
$$
\begin{gather}
\textbf{Theorem:} \\[5mm]
\text{Let } X,Y,Z \text{ be arbitrary sets. Then the following equality holds: } \\[3.5mm]
(X \times Y) \cup (Z \times Y) = (X \cup Z) \times Y
\end{gather}
$$
(See [[Proof of the Third Useful Property of Cartesian Products|proof]])
$$
\begin{gather}
\textbf{Theorem: } \\[5mm]
(X \times Y) \cap (X' \times Y') = (X \cap X') \times (Y \cap Y')
\end{gather}
$$
(See [[Proof of the Fourth Useful Property of Cartesian Products|proof]])