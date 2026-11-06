---
dg-publish: true
---
# Ordered Pairs and the Cartesian Product
For any two sets $A$ and $B$, an unordered collection can be constructed and denoted as $\{A, B\} = \{B, A\}$, representing an unordered pair of sets. This collection contains exactly two distinct elements if $A \neq B$, and collapses to a *singleton* set if $A = B$. While unordered pairs suffice for symmetric set operations, real analysis requires directional orientation to model functions, coordinate geometries, and sequential processes. To inject directionality into set theory, the framework of the *ordered pair* must be established: 
$$
\begin{gather}
\textbf{Definition: Ordered Pair (Kuratowski)} \\[5mm]
\text{Let } x \text{ and } y \text{ be mathematical objects. The ordered pair } (x, y) \text{ is the} \\[2mm]
\text{set defined by the asymmetric nested collection:} \\[3.5mm]
(x, y) := \{\{x\}, \{x, y\}\}
\end{gather}
$$

The formal construction of the ordered pair represents a threefold application of the [[Chapter 2 - Naive Set Theory|Axiom of Pairing]]:
- Applying the axiom to the elements $x$ and $x$ yields the singleton set $\{x\}$.
- Applying the axiom to the elements $x$ and $y$ yields the doubleton set $\{x, y\}$.
- Applying the axiom to the resulting sets $\{x\}$ and $\{x, y\}$ yields the structure $\{\{x\}, \{x, y\}\}$ introduced by *Kazimierz Kuratowski*.

This definition enforces algebraic directionality, satisfying the defining characteristic of ordered coordinates:
$$
\begin{gather}
\textbf{Theorem: Fundamental Contract of Ordered Coordinates} \\[5mm]
(x, y) = (u, v) \iff (x = u) \wedge (y = v)
\end{gather}
$$
(see [[Proof of the Fundamental Contract of Ordered Coordinates]])

Once the internal architecture of an individual ordered pair is formalized, the master set comprising all possible coordinate combinations between two spaces can be constructed:
$$
\begin{gather}
\textbf{Definition: Cartesian Product} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. The Cartesian product of } X \text{ and } Y \text{ is the set} \\[2mm]
\text{comprising all ordered pairs } (x, y) \text{ such that } x \in X \text{ and } y \in Y: \\[3.5mm]
X \times Y := \{(x, y) \mid x \in X \wedge y \in Y\} = \{z \mid \exists x \in X, \exists y \in Y \text{ such that } z = (x, y)\}
\end{gather}
$$

The *Cartesian* product (named after *René Descartes*) is fundamentally non-commutative: $X \times Y \neq Y \times X$ in general. Commutative equality is preserved if and only if $(X = Y) \lor (X = \emptyset) \lor (Y = \emptyset)$. When a set is crossed with itself, the shorthand notation $X \times X =: X^2$ is deployed.

>[!danger]+ Intuition: The Directional Encryption of Coordinates
>In ordinary set theory, brackets signify unranked membership: $\{x, y\}$ is identical to $\{y, x\}$. To establish an ordered coordinate system without adding ad-hoc primitives to set theory, Kuratowski devised an internal encryption scheme: the first coordinate is distinguished by being placed inside a dedicated singleton set $\{x\}$, while both coordinates are placed inside the accompanying doubleton $\{x, y\}$. 
>
>An intuitive and applied way of thinking about this is with how geographical maps work. A two-dimensional map may contain streets, landmarks, and a compass for direction. However, the reader of the map requires a precise convention to specify the location of a particular place on the map. Cartographers achieve this by providing ordered geographic coordinates: the *x-coordinate* specifies the horizontal position and the *y-coordinate* specifies the vertical position, so that reversing the pair designates an entirely different location.

To rigorously justify the set-theoretic existence of the Cartesian product without relying on unrestricted comprehension, the *power set* $\mathcal{P}(X) := \{A \mid A \subseteq X\}$ guaranteed by the [[Chapter 2 - Naive Set Theory|Axiom of the Power Set]] in Zermelo-Fraenkel set theory is utilized. This construct provides the necessary bounding universe for the Cartesian product. If $x \in X$ and $y \in Y$, then both $x$ and $y$ are members of the union $X \cup Y$. Consequently, the singleton $\{x\}$ and the doubleton $\{x, y\}$ are subsets of $X \cup Y$, which establishes that $\{x\} \in \mathcal{P}(X \cup Y)$ and $\{x, y\} \in \mathcal{P}(X \cup Y)$.

Because the Kuratowski pair $(x, y) = \{\{x\}, \{x, y\}\}$ is a collection whose elements belong to $\mathcal{P}(X \cup Y)$, the pair itself is a subset of $\mathcal{P}(X \cup Y)$, which renders the ordered pair an element of the iterated power set: $(x, y) \in \mathcal{P}(\mathcal{P}(X \cup Y))$. Invoking the Principle of Separation, the Cartesian product is formalized as a validated subset of this overarching universe:
$$
\begin{gather}
X \times Y := \{z \in \mathcal{P}(\mathcal{P}(X \cup Y)) \mid \exists x \in X, \exists y \in Y \text{ such that } z = (x, y)\} \tag{1}
\end{gather}
$$

>[!example]- Example: Discrete State Grids and Non-Commutativity of Cartesian Products
>Consider an automated execution controller whose operational state is determined by two discrete registers: an execution mode drawn from $X = \{\text{Passive}, \text{Aggressive}\}$ and a priority tier drawn from $Y = \{\text{Low}, \text{High}, \text{Critical}\}$.
>1. **Forward Product ($X \times Y$):** Every element of $X \times Y$ is an ordered pair whose first coordinate is an execution mode and whose second coordinate is a priority tier:
>$$
>\begin{gather}
>X \times Y = \left\{
>\begin{aligned}
>&(\text{Passive}, \text{Low}), (\text{Passive}, \text{High}), (\text{Passive}, \text{Critical}), \\
>&(\text{Aggressive}, \text{Low}), (\text{Aggressive}, \text{High}), (\text{Aggressive}, \text{Critical})
>\end{aligned}
>\right\} \tag{2}
>\end{gather}
>$$
>2. **Reverse Product ($Y \times X$):** Reversing the order of the factor sets reverses the coordinate positions in every pair:
>$$
>\begin{gather}
>Y \times X = \left\{
>\begin{aligned}
>&(\text{Low}, \text{Passive}), (\text{High}, \text{Passive}), (\text{Critical}, \text{Passive}), \\
>&(\text{Low}, \text{Aggressive}), (\text{High}, \text{Aggressive}), (\text{Critical}, \text{Aggressive})
>\end{aligned}
>\right\} \tag{3}
>\end{gather}
>$$
>By the Fundamental Contract of Ordered Coordinates, $(\text{Passive}, \text{Low}) \neq (\text{Low}, \text{Passive})$. Because $X$ and $Y$ are disjoint, step 2 and step 3 share no common elements: $(X \times Y) \cap (Y \times X) = \emptyset$, illustrating why $X \times Y \neq Y \times X$.

---
# Relations
With the Cartesian product established, relationships between distinct sets can be formalized mathematically:
$$
\begin{gather}
\textbf{Definition: Binary Relation} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. A binary relation } \mathcal{R} \text{ from } X \text{ to } Y \text{ is an arbitrary} \\[2mm]
\text{subset of their Cartesian product: } \mathcal{R} \subseteq X \times Y. \\[3.5mm]
\text{The set } X \text{ represents the source set, and } Y \text{ represents the target set.} \\[2mm]
\text{The active domain and range of the relation are defined respectively as:} \\[3.5mm]
\operatorname{dom}(\mathcal{R}) := \{x \in X \mid \exists y \in Y \text{ such that } (x, y) \in \mathcal{R}\} \subseteq X \\[2mm]
\operatorname{ran}(\mathcal{R}) := \{y \in Y \mid \exists x \in X \text{ such that } (x, y) \in \mathcal{R}\} \subseteq Y \\[3.5mm]
\text{If } (x, y) \in \mathcal{R}, \text{ relational notation is expressed as } x \mathcal{R} y. \\[2mm]
\text{If } X = Y, \text{ the subset } \mathcal{R} \subseteq X^2 \text{ is designated a binary relation on } X.
\end{gather}
$$

Because a relation is fundamentally a set of ordered pairs, all algebraic properties governing set unions, intersections, and complements apply directly to relations.

When examining a relation defined on a single space $X$, distinct structural properties emerge depending on the algebraic constraints imposed upon the coordinate pairs. The first major structural category is the *equivalence relation*, which formalizes the conceptual notion of qualitative classification or indistinguishability:
$$
\begin{gather}
\textbf{Definition: Equivalence Relation} \\[5mm]
\text{A binary relation } \mathcal{R} \text{ on a set } X \text{ is an equivalence relation if and only if} \\[2mm]
\text{the following three structural conditions hold for all } x, y, z \in X: \\[3.5mm]
\text{1. Reflexivity: } \forall x \in X \, (x \mathcal{R} x) \\[2mm]
\text{2. Symmetry: } \forall x, y \in X \, (x \mathcal{R} y \implies y \mathcal{R} x) \\[2mm]
\text{3. Transitivity: } \forall x, y, z \in X \, ((x \mathcal{R} y \wedge y \mathcal{R} z) \implies x \mathcal{R} z)
\end{gather}
$$

Equivalence relations cluster elements into disjoint subsets based on shared relational invariant properties:
$$
\begin{gather}
\textbf{Definition: Equivalence Class} \\[5mm]
\text{Let } \mathcal{R} \text{ be an equivalence relation on a set } X. \text{ For any fixed element } x \in X, \\[2mm]
\text{the equivalence class of } x, \text{ denoted } [x], \text{ is the subset of all elements related to } x: \\[3.5mm]
[x] := \{y \in X \mid y \mathcal{R} x\}
\end{gather}
$$

The space can also be analyzed from a macro-structural viewpoint through set-theoretic partitions:
$$
\begin{gather}
\textbf{Definition: Partition of a Set} \\[5mm]
\text{Let } X \text{ be a non-empty set. A family } \mathcal{P} \text{ of subsets of } X \text{ is designated a partition of } X \\[2mm]
\text{if and only if the following three conditions are satisfied:} \\[3.5mm]
\text{1. Non-emptiness: } \forall A \in \mathcal{P} \, (A \neq \emptyset) \\[2mm]
\text{2. Pairwise Disjointness: } \forall A, B \in \mathcal{P} \, (A \neq B \implies A \cap B = \emptyset) \\[2mm]
\text{3. Collective Exhaustiveness: } \bigcup_{A \in \mathcal{P}} A = X
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Fundamental Theorem of Equivalence Relations} \\[5mm]
\text{Let } X \text{ be a non-empty set.} \\[2mm]
\text{1. If } \mathcal{R} \text{ is an equivalence relation on } X, \text{ the family of equivalence classes} \\[2mm]
X / \mathcal{R} := \{[x] \mid x \in X\} \text{ forms a valid partition of } X. \\[3.5mm]
\text{2. Conversely, any partition } \mathcal{P} \text{ of } X \text{ induces a unique equivalence relation } \mathcal{R}_{\mathcal{P}} \\[2mm]
\text{defined by: } x \mathcal{R}_{\mathcal{P}} y \iff \exists A \in \mathcal{P} \text{ such that } (x \in A \wedge y \in A).
\end{gather}
$$
(see [[Proof of the Fundamental Theorem of Equivalence Relations]])

>[!question]+ Application: Quotient Spaces in State Aggregation and Payoff Equivalence
>Equivalence relations filter out irrelevant micro-attributes to isolate structural invariants:
>- **Fungibility and Payoff Equivalence Classes:** Consider a finite universe $X$ of financial contracts evaluated across a finite set of terminal states of nature. Two contracts $A, B \in X$ are defined as equivalent ($A \mathcal{R} B$) if and only if they deliver the exact same contractual obligation in every state. Reflexivity, symmetry, and transitivity hold directly from logical equality. The quotient set $X / \mathcal{R}$ groups redundant synthetic structures into disjoint equivalence classes $[A]$ of economically indistinguishable instruments.
>- **Partitions as Observational Granularity:** In discrete system monitoring, a sensor array partitions the underlying state space $X$ into pairwise disjoint blocks $\mathcal{P} = \{A_1, A_2, \dots, A_k\}$, where two states $x, y \in X$ belong to the same block $A_i$ if and only if they trigger identical sensor readings ($x \mathcal{R}_{\mathcal{P}} y$). Adding a new diagnostic sensor refines the partition by splitting each block $A_i$ into smaller disjoint subsets, increasing observational resolution.

### Order Relations
Order relations provide mathematical rules for ranking, comparing, and sorting elements within a set. There are two primary categories of order relations utilized extensively in analytical mathematics and decision theory: *partial orders* and *total (linear) orders*.
$$
\begin{gather}
\textbf{Definition: Partial Order} \\[5mm]
\text{A binary relation } \mathcal{R} \text{ on a set } X \text{ is a partial order if and only if} \\[2mm]
\text{the following three conditions hold for all } x, y, z \in X: \\[3.5mm]
\text{1. Reflexivity: } \forall x \in X \, (x \mathcal{R} x) \\[2mm]
\text{2. Antisymmetry: } \forall x, y \in X \, ((x \mathcal{R} y \wedge y \mathcal{R} x) \implies x = y) \\[2mm]
\text{3. Transitivity: } \forall x, y, z \in X \, ((x \mathcal{R} y \wedge y \mathcal{R} z) \implies x \mathcal{R} z)
\end{gather}
$$

A set $X$ equipped with a partial order $\mathcal{R}$ is designated a *partially ordered set*, or *poset*, denoted $(X, \mathcal{R})$ or $(X, \preceq)$. Within a poset, two distinct elements $x, y \in X$ may be *incomparable*, meaning that neither $x \mathcal{R} y$ nor $y \mathcal{R} x$ holds.

To achieve an environment where every pair of elements can be ranked, a relation must satisfy the condition of comparability:
$$
\begin{gather}
\textbf{Definition: Totality (Comparability)} \\[5mm]
\text{A binary relation } \mathcal{R} \text{ on a set } X \text{ satisfies totality (or comparability) if and only if:} \\[3.5mm]
\forall x, y \in X \, (x \mathcal{R} y \lor y \mathcal{R} x)
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Total (Linear) Order} \\[5mm]
\text{A binary relation } \mathcal{R} \text{ on a set } X \text{ is a total order (or linear order) if it is a} \\[2mm]
\text{partial order that satisfies totality across all pairs in } X.
\end{gather}
$$

>[!info]+ Remark: The Power Set Inclusion Poset
>For any ambient set $M$ containing at least two distinct elements $a \neq b$, the power set $\mathcal{P}(M)$ equipped with the subset inclusion relation $\subseteq$ from [[Chapter 2 - Naive Set Theory|Chapter 2]] forms a canonical partial order $(\mathcal{P}(M), \subseteq)$:
>- **Reflexivity:** $A \subseteq A$ for every $A \in \mathcal{P}(M)$.
>- **Antisymmetry:** $(A \subseteq B) \wedge (B \subseteq A) \implies A = B$ by the Principle of Extensionality.
>- **Transitivity:** $(A \subseteq B) \wedge (B \subseteq C) \implies A \subseteq C$.
>
>However, $(\mathcal{P}(M), \subseteq)$ is not a total order: the singleton subsets $\{a\}$ and $\{b\}$ satisfy neither $\{a\} \subseteq \{b\}$ nor $\{b\} \subseteq \{a\}$, rendering them mutually incomparable.

>[!question]+ Application: Componentwise Dominance versus Lexicographic Priority in Multi-Criteria Selection
>The structural distinction between partial and total orders governs multi-criteria decision systems:
>- **The Partial Order of Componentwise Dominance:** Suppose candidate system configurations are represented by ordered pairs $(x_1, x_2) \in X_1 \times X_2$, where $(X_1, \preceq_1)$ and $(X_2, \preceq_2)$ are linearly ordered rating scales (for example, reliability tier and throughput tier). Under the product order, configuration $(a_1, a_2)$ is dominated by $(b_1, b_2)$ if and only if $(a_1 \preceq_1 b_1) \wedge (a_2 \preceq_2 b_2)$. This relation is a partial order on $X_1 \times X_2$, because a configuration with higher reliability but lower throughput is incomparable to one with lower reliability and higher throughput.
>- **The Total Order of Lexicographic Priority:** When an automated router must select a single winning configuration without ties or incomparability, it imposes a *lexicographic order* $\preceq_{\text{lex}}$ on $X_1 \times X_2$:
>$$
>\begin{gather}
>(a_1, a_2) \preceq_{\text{lex}} (b_1, b_2) \iff (a_1 \neq b_1 \wedge a_1 \preceq_1 b_1) \lor (a_1 = b_1 \wedge a_2 \preceq_2 b_2) \tag{4}
>\end{gather}
>$$
>By step 4, every pair of coordinate tuples in $X_1 \times X_2$ becomes comparable, transforming the multi-attribute product space into a totally ordered set.

---
# Useful Properties of Cartesian Products
From the foundational definitions of the Cartesian product and Boolean set operations, several structural identities are established:
$$
\begin{gather}
\textbf{Theorem: Empty Product Identity} \\[5mm]
\text{Let } X \text{ and } Y \text{ be arbitrary sets. Then:} \\[3.5mm]
X \times Y = \emptyset \iff (X = \emptyset) \lor (Y = \emptyset)
\end{gather}
$$
(see [[Proof of the Empty Product Identity]])

$$
\begin{gather}
\textbf{Theorem: Inclusion of Cartesian Products} \\[5mm]
\text{Let } A, B, X, \text{ and } Y \text{ be non-empty sets. Then:} \\[3.5mm]
A \times B \subseteq X \times Y \iff (A \subseteq X) \wedge (B \subseteq Y)
\end{gather}
$$
(see [[Proof of the Inclusion of Cartesian Products]])

$$
\begin{gather}
\textbf{Theorem: Left-Distributivity of Cartesian Products over Unions} \\[5mm]
\text{Let } X, Y, \text{ and } Z \text{ be arbitrary sets. Then:} \\[3.5mm]
(X \times Y) \cup (Z \times Y) = (X \cup Z) \times Y
\end{gather}
$$
(see [[Proof of the Left-Distributivity of Cartesian Products Over Unions]]) 

$$
\begin{gather}
\textbf{Theorem: Distributivity of Cartesian Products over Intersections} \\[5mm]
\text{Let } X, Y, X', \text{ and } Y' \text{ be arbitrary sets. Then:} \\[3.5mm]
(X \times Y) \cap (X' \times Y') = (X \cap X') \times (Y \cap Y')
\end{gather}
$$
(see [[Proof of the Distributivity of Cartesian Products Over Intersections]])