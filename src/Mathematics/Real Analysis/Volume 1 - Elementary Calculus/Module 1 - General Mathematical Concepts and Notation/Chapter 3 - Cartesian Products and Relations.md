---
dg-publish: true
---
# Ordered Pairs and the Cartesian Product
For any two sets $A$ and $B$, an unordered collection can be constructed and denoted as $\{A, B\} = \{B, A\}$, representing an unordered pair of sets. This collection contains exactly two distinct elements if $A \neq B$, and collapses to a singleton set if $A = B$. While unordered pairs suffice for symmetric set operations, mathematical analysis requires directional orientation to model functions, coordinate geometries, and sequential processes. To inject directionality into set theory, the framework of the *ordered pair* must be established: 
$$
\begin{gather}
\textbf{Definition: Ordered Pair (Kuratowski)} \\[5mm]
\text{Let } x \text{ and } y \text{ be mathematical objects. The ordered pair } (x, y) \text{ is the} \\[2mm]
\text{set defined by the asymmetric nested collection:} \\[3.5mm]
(x, y) := \{\{x\}, \{x, y\}\}
\end{gather}
$$

The formal construction of the ordered pair represents a threefold application of the Axiom of Pairing:
- Applying the axiom to the elements $x$ and $x$ yields the singleton set $\{x\}$.
- Applying the axiom to the elements $x$ and $y$ yields the doubleton set $\{x, y\}$.
- Applying the axiom to the resulting sets $\{x\}$ and $\{x, y\}$ yields the *Kuratowski* structure $\{\{x\}, \{x, y\}\}$.

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

The Cartesian product is fundamentally non-commutative: $X \times Y \neq Y \times X$ in general. Commutative equality is preserved if and only if $(X = Y) \lor (X = \emptyset) \lor (Y = \emptyset)$. When a set is crossed with itself, the shorthand notation $X \times X =: X^2$ is deployed.

>[!danger]+ Intuition: The Directional Encryption of Coordinates
>In ordinary set theory, brackets signify unranked membership: $\{x, y\}$ is identical to $\{y, x\}$. To establish an ordered coordinate system without adding ad-hoc primitives to set theory, *Kazimierz Kuratowski* devised an internal encryption scheme: the first coordinate is distinguished by being placed inside a dedicated singleton set $\{x\}$, while both coordinates are placed inside the accompanying doubleton $\{x, y\}$. 
>
>An intuitive and applied way of thinking about this is with how geographical maps (the thing that people use to know where they are) work. A two-dimensional map may contains streets, landmarks, and a compass for direction. However, the reader of the map may want a useful way to remember the location of a specific place on the map. Cartographers do this by providing geographic coordinates. In a two-dimensional map, the *x-coordinate* provides the location of a place relative to the horizontal axis and the *y-coordinate* provides the location of a place relative to the vertical axis. As an example, the local fire station can be found in coordinates $(-122,235)$. 

To rigorously justify the set-theoretic existence of the Cartesian product without relying on geometric intuition, the framework of the *Power Set* must be utilized:
$$
\begin{gather}
\textbf{Definition: Power Set} \\[5mm]
\text{Let } X \text{ be an arbitrary set. The power set of } X, \text{ denoted as } \mathcal{P}(X) \text{ or } 2^X, \text{ is the set} \\[2mm]
\text{comprising all possible subsets of } X: \\[3.5mm]
\mathcal{P}(X) := \{A \mid A \subseteq X\}
\end{gather}
$$
The existence of the power set is guaranteed by the Axiom of the Power Set in Zermelo-Fraenkel set theory. This construct provides the necessary bounding universe for the Cartesian product. If $x \in X$ and $y \in Y$, then both $x$ and $y$ are members of the union $X \cup Y$. Consequently, the singleton $\{x\}$ and the doubleton $\{x, y\}$ are subsets of $X \cup Y$, which establishes that $\{x\} \in \mathcal{P}(X \cup Y)$ and $\{x, y\} \in \mathcal{P}(X \cup Y)$.

Because the Kuratowski pair $(x, y) = \{\{x\}, \{x, y\}\}$ is a collection whose elements belong to $\mathcal{P}(X \cup Y)$, the pair itself is a subset of $\mathcal{P}(X \cup Y)$, which renders the ordered pair an element of the double power set: $(x, y) \in \mathcal{P}(\mathcal{P}(X \cup Y))$. Invoking the Principle of Separation, the Cartesian product is formalized as a validated subset of this overarching universe:
$$
\begin{gather}
X \times Y := \{z \in \mathcal{P}(\mathcal{P}(X \cup Y)) \mid \exists x \in X, \exists y \in Y \text{ such that } z = (x, y)\} \tag{1}
\end{gather}
$$

>[!example]- Example: Geometric Interpretations of Cartesian Products
>If $X \times Y$ denotes the set of all ordered pairs $(x, y)$ such that $x \in X$ and $y \in Y$, these structures can be visualized through classical geometric configurations:
>1. **The product of two line segments:** Let $I_1 = [a, b]$ and $I_2 = [c, d]$ represent two bounded closed intervals on the real line $\mathbb{R}$. Their Cartesian product $I_1 \times I_2$ defines a bounded, solid rectangle embedded in the plane $\mathbb{R}^2$, bounded by the lines $x = a$, $x = b$, $y = c$, and $y = d$.
>2. **The product of two lines:** The Cartesian product $\mathbb{R} \times \mathbb{R}$ maps every pair of real numbers across two infinite orthogonal dimensions, generating the continuous two-dimensional Cartesian plane $\mathbb{R}^2$.
>3. **The product of a line and a circle:** Let the line be represented by $\mathbb{R}$ and the circle by the 1-sphere $S^1$. The product $\mathbb{R} \times S^1$ associates each point along an infinite axis with a periodic circular path, generating an infinitely long hollow cylindrical surface in three-dimensional space $\mathbb{R}^3$.
>4. **The product of a line and a disk:** Replacing the hollow circle with a filled closed unit disk $D$, the product $\mathbb{R} \times D$ extends the planar disk continuously along the linear real axis, forming an infinite solid cylinder.
>5. **The product of two circles:** The product $S^1 \times S^1$ couples two independent periodic dimensions, constructing the standard 2-torus ($T^2$). Geometrically, this manifests as the hollow boundary surface of a torus.
>6. **The product of a circle and a disk:** Taking the product of a circle $S^1$ and a filled disk $D$, the interior disk region is swept along the closed circular trajectory, forming a solid 3D torus.

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
\textbf{Fundamental Theorem of Equivalence Relations: } \\[5mm]
\text{Let } X \text{ be a non-empty set.} \\[2mm]
\text{1. If } \mathcal{R} \text{ is an equivalence relation on } X, \text{ the family of equivalence classes} \\[2mm]
X / \mathcal{R} := \{[x] \mid x \in X\} \text{ forms a valid partition of } X. \\[3.5mm]
\text{2. Conversely, any partition } \mathcal{P} \text{ of } X \text{ induces a unique equivalence relation } \mathcal{R}_{\mathcal{P}} \\[2mm]
\text{defined by: } x \mathcal{R}_{\mathcal{P}} y \iff \exists A \in \mathcal{P} \text{ such that } (x \in A \wedge y \in A).
\end{gather}
$$
(see [[Proof of the Fundamental Theorem of Equivalence Relations]])

>[!question]+ Application: Quotient Spaces as No-Arbitrage Pricing Classes and Information Filtrations
>Equivalence relations filter out irrelevant micro-attributes to focus on structural invariants:
>- **The Law of One Price as a Quotient Space:** Consider the infinite space of synthetic derivative contracts. Two cash flow streams $A$ and $B$ are defined as equivalent ($A \sim B$) if their payouts match across all future states of nature. Under the no-arbitrage condition, every contract inside an equivalence class $[A]$ must command the identical initial price. The quotient set $X / \sim$ collapses thousands of redundant replication strategies into single fundamental price points.
>- **Partitions as Information Atoms:** In stochastic analysis, a partition models the information available to an investor at time $t$. In a multi-period binomial tree, the sample space of paths $\Omega$ is partitioned into sets of trajectories that share identical historical observations up to $t$. As time advances, incoming market data splits these partition subsets into finer components, modeling the unfolding filtration $\mathcal{F}_t$.

### Order Relations
Order relations provide mathematical rules for ranking, comparing, and sorting elements within a set. There are two primary categories of order relations utilized extensively in analytical mathematics and decision theory: *Partial Orders* and *Total (Linear) Orders*.
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

A set $X$ equipped with a partial order $\mathcal{R}$ is designated a *partially ordered set*, or *poset*, denoted $(X, \mathcal{R})$ or $(X, \le)$. Within a poset, two distinct elements $x, y \in X$ may be *incomparable*, meaning that neither $x \mathcal{R} y$ nor $y \mathcal{R} x$ holds.

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

>[!info]+ Remark: The Canonical Total Order on Real Numbers
>The standard numerical inequality operator $\le$ on $\mathbb{R}$ represents the definitive archetype of a total order: for any real numbers $a, b \in \mathbb{R}$, either $a \le b$ or $b \le a$ holds unconditionally.

>[!question]+ Application: Pareto Efficiency versus Scalar Utility in Portfolio Ranking
>The distinction between partial and total orders governs the mathematics of economic choice:
>- **The Partial Order of Pareto Dominance:** In modern portfolio theory, risk-return dominance forms a partial order. Portfolio $A$ dominates Portfolio $B$ if $E[R_A] \ge E[R_B]$ and $\sigma_A \le \sigma_B$, with at least one strict inequality. However, two distinct portfolios situated along the Markowitz efficient frontier (e.g., a low-risk/low-return money market portfolio versus a high-risk/high-return tech equity portfolio) are mutually incomparable under Pareto dominance. Neither dominates the other.
>- **The Total Order of Utility Functions:** Because an allocator cannot execute an incomparable decision, the partial order must be collapsed into a total linear order. This is achieved by introducing a scalar utility function $U(w) = E[R] - \frac{1}{2}\lambda \sigma^2$ or a reward-to-risk ratio (such as the Sharpe ratio). This mapping projects multi-dimensional trade-offs onto the real continuum $(\mathbb{R}, \le)$, enabling every candidate portfolio to be ranked.

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
\text{Let } X \times Y \neq \emptyset. \text{ Then for any sets } A \text{ and } B: \\[3.5mm]
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