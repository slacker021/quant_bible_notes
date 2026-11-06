---
dg-publish: true
---
# Functional Relations
In the mathematical sciences, a special category of binary relation plays an indispensable role: the *functional relation*, universally designated as a *function* or *mapping*. A function is a binary relation from a source set to a target set that satisfies an explicit unique-existence constraint on its coordinate pairs. Building directly upon the relational architecture established in [[Chapter 3 - Cartesian Products and Relations|Chapter 3]], functions are formalized within [[Chapter 2 - Naive Set Theory|axiomatic set theory]] as follows:
$$
\begin{gather}
\textbf{Definition: Function (Mapping)} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. A function } f \text{ from } X \text{ to } Y, \text{ denoted as } f: X \to Y, \\[2mm]
\text{is a binary relation } f \subseteq X \times Y \text{ satisfying the following two conditions:} \\[3.5mm]
\text{1. Left-Totality (Existence): } \forall x \in X \, \exists y \in Y \, ((x, y) \in f) \\[2mm]
\text{2. Single-Valuedness (Uniqueness): } \forall x \in X \,  \ \forall y_1, y_2 \in Y \, (((x, y_1) \in f \wedge (x, y_2) \in f) \implies y_1 = y_2)
\end{gather}
$$

These two conditions are synthesized concisely via the unique existential quantifier:
$$
\begin{gather}
\forall x \in X \, \exists! y \in Y \, ((x, y) \in f) \tag{1}
\end{gather}
$$

For any coordinate pair $(x, y) \in f$, the unique element $y \in Y$ is designated as the *value* of the function $f$ at the argument $x$, expressed through standard functional notation as $y = f(x)$.

>[!danger]+ Intuition: Functions as Machines
>A clever way of thinking about functions is that they are machines that take stuff in and crank out an output. Whatever is in the machine that creates such output is usually abstracted, but may be inspected should the viewer want to know the gears running in it. For example, a meat grinder takes in fresh and uncut meat, which is then pulverized into ground meat that is more easily digested. 
>
>The key thing to remember is that the mapping between an input and output is governed by some sort of property or condition. 

For any mapping $f: X \to Y$:
1. The set $X$ is designated the **domain** of the function, denoted $\operatorname{dom}(f) = X$.
2. The set $Y$ is designated the **codomain** of the function, denoted $\operatorname{codom}(f) = Y$.

The codomain represents the space of all possible target values. It is critical to recognize that not every element in the codomain is necessarily mapped to by an element in the domain. The actual set of outputs produced by the mapping forms a validated subset of the codomain, termed the *range* or *image*:
$$
\begin{gather}
\textbf{Definition: Range (Image) of a Function} \\[5mm]
\text{For a mapping } f: X \to Y, \text{ the range (or image) of } f, \text{ denoted } \operatorname{ran}(f) \text{ or } \operatorname{im}(f), \\[2mm]
\text{is the subset of the codomain consisting of all realized outputs:} \\[3.5mm]
\operatorname{ran}(f) := \{y \in Y \mid \exists x \in X \, (y = f(x))\} \subseteq Y
\end{gather}
$$

The action of a function generalizes naturally to entire subsets of the domain and codomain:
$$
\begin{gather}
\textbf{Definition: Direct Image and Preimage of Subsets} \\[5mm]
\text{Let } f: X \to Y \text{ be a mapping. If } A \subseteq X, \text{ the direct image of } A \text{ under } f \text{ is:} \\[3.5mm]
f(A) := \{y \in Y \mid \exists x \in A \, (y = f(x))\} \subseteq Y \\[5mm]
\text{Conversely, if } B' \subseteq Y, \text{ the preimage (or inverse image) of } B' \text{ under } f \text{ is:} \\[3.5mm]
f^{-1}(B') := \{x \in X \mid f(x) \in B'\} \subseteq X
\end{gather}
$$

---
# Classifications of Mappings
To analyze how structural properties, geometries, and dimensions are preserved between distinct spaces, functions are classified based on the distribution and uniqueness of their coordinate pairings across the domain and codomain:
$$
\begin{gather}
\textbf{Definition: Injection (One-to-One)} \\[5mm]
\text{A mapping } f: X \to Y \text{ is an injection if and only if distinct arguments} \\[2mm]
\text{in the domain map to distinct values in the codomain:} \\[3.5mm]
\forall x_1, x_2 \in X \, (x_1 \neq x_2 \implies f(x_1) \neq f(x_2))
\end{gather}
$$

By contraposition, injectivity is equivalently characterized by:
$$
\begin{gather}
\forall x_1, x_2 \in X \, (f(x_1) = f(x_2) \implies x_1 = x_2) \tag{2}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Surjection (Onto)} \\[5mm]
\text{A mapping } f: X \to Y \text{ is a surjection if and only if the range is} \\[2mm]
\text{identically equal to the codomain:} \\[3.5mm]
\operatorname{ran}(f) = Y \iff \forall y \in Y \, \exists x \in X \, (f(x) = y)
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Bijection (One-to-One Correspondence)} \\[5mm]
\text{A mapping } f: X \to Y \text{ is a bijection if and only if it is simultaneously} \\[2mm]
\text{injective and surjective:} \\[3.5mm]
(\forall x_1, x_2 \in X \, (f(x_1) = f(x_2) \implies x_1 = x_2)) \wedge (\forall y \in Y \, \exists x \in X \, (f(x) = y))
\end{gather}
$$

Bijective mappings establish a one-to-one correspondence between sets, enabling the formal definition of the pointwise inverse function:
$$
\begin{gather}
\textbf{Definition: Inverse Mapping} \\[5mm]
\text{Let } f: X \to Y \text{ be a bijection. The inverse mapping of } f, \text{ denoted as } \\[2mm]
f^{-1}: Y \to X, \text{ is the binary relation defined by:} \\[3.5mm]
f^{-1} := \{(y, x) \in Y \times X \mid (x, y) \in f\}
\end{gather}
$$

Because $f$ is surjective, every $y \in Y$ appears as the first coordinate of at least one pair in $f^{-1}$. Because $f$ is injective, each $y \in Y$ appears in at most one pair. Consequently, $f^{-1}: Y \to X$ is a valid function satisfying:
$$
\begin{gather}
f^{-1}(y) = x \iff f(x) = y \tag{3}
\end{gather}
$$

>[!warning]+ Warning: Inverse Function versus Preimage Operator
>The notation $f^{-1}$ carries two distinct mathematical meanings that must never be conflated:
>1. The **preimage operator** $f^{-1}: \mathcal{P}(Y) \to \mathcal{P}(X)$ maps subsets of the codomain to subsets of the domain. It is universally well-defined for *every* function, requiring no special properties of $f$.
>2. The **inverse mapping** $f^{-1}: Y \to X$ is an actual pointwise function that exists if and only if $f$ is a bijection.

>[!danger]+ Intuition: Inverse Functions
>The inverse of a function, [[Proof of the Existence of Inverse Mappings|assuming it exists]], effectively reverses the original mapping—meaning that the range of the original function serves as the domain of the inverse, while the domain of the original function serves as the range of the inverse. 
>
>Returning to the meat grinder analogy, suppose that engineers construct a hypothetical reversal machine capable of reassembling ground meat back into the exact cut of whole meat from which it originated. Such a reversal machine exists if and only if every distinct input cut produces a distinct ground output (injectivity) and every target state in the output bin comes from an actual cut (surjectivity).

>[!example]- Example: Set-Theoretic and Structural Mappings
>1. **Set Complementation as a Bijective Involution:** For an ambient set $M$, the complementation operator $C_M: \mathcal{P}(M) \to \mathcal{P}(M)$ assigning $A \mapsto M \setminus A$ satisfies the [[Proof of Elementary Lemma of Set Complementation|double complementation identity]] $C_M(C_M(A)) = A$. Because every subset $B \in \mathcal{P}(M)$ is the image of $A = C_M(B)$ and distinct subsets possess distinct complements, $C_M$ is a bijection that serves as its own inverse ($C_M^{-1} = C_M$).
>2. **Canonical Coordinate Projections:** On a Cartesian product $X_1 \times X_2$, the first-coordinate projection $\operatorname{pr}_1: X_1 \times X_2 \to X_1$ defined by $(x_1, x_2) \mapsto x_1$ is surjective whenever $X_2 \neq \emptyset$. However, whenever $X_2$ contains at least two distinct elements $b_1 \neq b_2$, the ordered pairs $(x_1, b_1)$ and $(x_1, b_2)$ are distinct by the [[Proof of the Fundamental Contract of Ordered Coordinates|Fundamental Contract of Ordered Coordinates]] yet map to the identical image $\operatorname{pr}_1(x_1, b_1) = x_1 = \operatorname{pr}_1(x_1, b_2)$, rendering $\operatorname{pr}_1$ non-injective.
>3. **The Diagonal Embedding:** For any set $X$, the diagonal mapping $\Delta: X \to X \times X$ defined by $x \mapsto (x, x)$ is unconditionally injective, because $\Delta(x_1) = \Delta(x_2) \implies (x_1, x_1) = (x_2, x_2) \implies x_1 = x_2$. Whenever $X$ contains at least two distinct elements $a \neq b$, the off-diagonal pair $(a, b) \in X \times X$ does not belong to $\operatorname{ran}(\Delta)$, so $\Delta$ is not surjective.
>4. **Characteristic (Indicator) Mappings on a Binary Alphabet:** Let $M$ be an ambient set, let $E \subseteq M$, and let $\{0, 1\}$ be a two-element status alphabet ($0 \neq 1$). The *characteristic function* (or *indicator function*) $\chi_E: M \to \{0, 1\}$ is defined by:
>$$
>\begin{gather}
>\chi_E(x) := \begin{cases} 1, & x \in E \\ 0, & x \in M \setminus E \end{cases} \tag{4}
>\end{gather}
>$$
>By step 4, the preimage $\chi_E^{-1}(\{1\}) = \{x \in M \mid \chi_E(x) = 1\} = E$ recovers the subset $E$ uniquely, while $\chi_E^{-1}(\{0\}) = M \setminus E = C_M(E)$.
>5. **Quotient Canonical Projection:** Let $\mathcal{R}$ be an equivalence relation on a non-empty set $X$, and let $X / \mathcal{R} = \{[x] \mid x \in X\}$ denote the quotient set established in [[Chapter 3 - Cartesian Products and Relations|Chapter 3]]. The canonical projection $\pi: X \to X / \mathcal{R}$ defined by $\pi(x) := [x]$ is surjective by definition of $X / \mathcal{R}$, and is injective if and only if every equivalence class is a singleton ($\forall x, y \in X, \, x \mathcal{R} y \implies x = y$).
>6. **Pointwise Evaluation Mapping:** Let $\mathcal{F}(X; Y)$ denote the family of all mappings from a non-empty set $X$ into a set $Y$. For a fixed anchor element $x_0 \in X$, the evaluation mapping $\operatorname{ev}_{x_0}: \mathcal{F}(X; Y) \to Y$ defined by $\operatorname{ev}_{x_0}(f) := f(x_0)$ is surjective onto $Y$ (since for every $y \in Y$, the constant mapping $c_y(x) := y$ satisfies $\operatorname{ev}_{x_0}(c_y) = y$), but fails to be injective whenever $X$ contains an element $x_1 \neq x_0$ and $Y$ contains at least two distinct elements.

---
# Composite Functions
When operations execute sequentially, functions can be chained together via composition:
$$
\begin{gather}
\textbf{Definition: Composition of Mappings} \\[5mm]
\text{Let } f: X \to Y \text{ and } g: Y \to Z \text{ be mappings. The composition } g \circ f: X \to Z \\[2mm]
\text{is the mapping defined set-theoretically by the relation:} \\[3.5mm]
g \circ f := \{(x, z) \in X \times Z \mid \exists y \in Y \, ((x, y) \in f \wedge (y, z) \in g)\}
\end{gather}
$$

Evaluating this composition pointwise yields the standard operational formula:
$$
\begin{gather}
(g \circ f)(x) := g(f(x)) \tag{5}
\end{gather}
$$

Function composition satisfies the associative property:
$$
\begin{gather}
\textbf{Theorem: Associativity of Composite Functions} \\[5mm]
\text{Let } f: X \to Y, \text{ } g: Y \to Z, \text{ and } h: Z \to W \text{ be mappings. Then:} \\[3.5mm]
h \circ (g \circ f) = (h \circ g) \circ f
\end{gather}
$$
(see [[Proof of the Associative Property of Composite Functions]])

>[!question]+ Application: Composition as Multi-Stage Execution Pipelines
>Function composition models sequential quantitative pipelines: raw market ticks ($X$) pass through feature extraction $f$ into clean factor signals ($Y$), which pass through portfolio optimizer $g$ into target allocations ($Z$). 
>
>The associativity of composition, $h \circ (g \circ f) = (h \circ g) \circ f$, guarantees that system pipelines can be modularized without side effects: an engineering team can encapsulate the data transformations $(g \circ f)$ into a single module before connecting it to execution $h$, or combine optimization and order routing $(h \circ g)$ first, with absolute mathematical equivalence.

---
# Set Cardinality and Cantor's Framework
The formalization of bijective mappings allows for the rigorous comparison of the relative sizes of arbitrary sets without relying on numerical counting. This framework is grounded in Cantor's *principle of equipotence*:
$$
\begin{gather}
\textbf{Definition: Equipotence (Equinumerosity)} \\[5mm]
\text{Two sets } X \text{ and } Y \text{ are equipotent, denoted } X \sim Y \text{ or } |X| = |Y|, \\[2mm]
\text{if and only if there exists a bijective mapping } f: X \to Y.
\end{gather}
$$

### Equipotence as an Equivalence Relation
Let $\mathcal{S}$ be any family of sets. The equipotence relation $\sim$ is an equivalence relation on $\mathcal{S}$, satisfying the three defining conditions from [[Chapter 3 - Cartesian Products and Relations|Chapter 3]]:
- **Reflexivity:** For any set $X$, the *identity mapping* $\operatorname{id}_X: X \to X$ defined by $\operatorname{id}_X(x) := x$ is a bijection, establishing $X \sim X$.
- **Symmetry:** If $X \sim Y$, there exists a bijection $f: X \to Y$. Its inverse $f^{-1}: Y \to X$ is also a bijection, establishing $Y \sim X$.
- **Transitivity:** If $X \sim Y$ and $Y \sim Z$, there exist bijections $f: X \to Y$ and $g: Y \to Z$. The composite mapping $g \circ f: X \to Z$ is a bijection, establishing $X \sim Z$.

Consequently, equipotence partitions any collection of sets into equivalence classes. Each equivalence class represents a distinct *cardinal number* (or *cardinality*).

### Cardinality Dominance and Cantor's Theorem
Even when two sets are not equipotent, injective mappings establish a relative hierarchy of size between sets:
1. **Weak Cardinality Dominance ($|X| \le |Y|$):** The cardinality of $X$ is less than or equal to the cardinality of $Y$, denoted $|X| \le |Y|$, if and only if there exists an injective mapping $f: X \to Y$ (meaning $X$ is equipotent to a subset of $Y$).
2. **Strict Cardinality Dominance ($|X| < |Y|$):** The cardinality of $X$ is strictly less than the cardinality of $Y$, denoted $|X| < |Y|$, if and only if $|X| \le |Y|$ and $X$ is not equipotent to $Y$ ($|X| \neq |Y|$, so no bijection exists between $X$ and $Y$).

Once the fundamental classes of numbers are constructed in Module 2, this framework classifies sets into finite, countable, and uncountable hierarchies. At the purely set-theoretic level, Cantor's Theorem establishes that taking the power set strictly increases cardinality, ensuring that no largest cardinal number can exist:
$$
\begin{gather}
\textbf{Cantor's Theorem:} \\[5mm]
\text{For every set } X, \text{ the cardinality of } X \text{ is strictly less than the} \\[2mm]
\text{cardinality of its power set } \mathcal{P}(X): \\[3.5mm]
|X| < |\mathcal{P}(X)|
\end{gather}
$$
(see [[Proof of Cantor's Theorem]])

---
# Useful Properties of Functions
From the foundational definitions of mappings, images, and preimages, several structural properties governing subset operations are established.

$$
\begin{gather}
\textbf{Proposition: Properties of the Direct Image} \\[5mm]
\text{Let } f: X \to Y \text{ and let } A, B \subseteq X. \text{ Then:} \\[3.5mm]
\text{1. Monotonicity: } A \subseteq B \implies f(A) \subseteq f(B) \\[2mm]
\text{2. Non-emptiness Preservation: } A \neq \emptyset \implies f(A) \neq \emptyset \\[2mm]
\text{3. Intersection Sub-distributivity: } f(A \cap B) \subseteq f(A) \cap f(B) \\[2mm]
\text{4. Union Distributivity: } f(A \cup B) = f(A) \cup f(B)
\end{gather}
$$
(see [[Proof of Properties of the Direct Image]])

>[!info]+ Remark: Failure of Direct Image Intersection Equality
>In the third sub-proposition of the properties of the direct image, equality does not hold in general: $f(A \cap B) \neq f(A) \cap f(B)$. If two distinct elements $a \in A \setminus B$ and $b \in B \setminus A$ map to the same target value $f(a) = f(b) = y$, then $y \in f(A) \cap f(B)$ while $A \cap B = \emptyset$, meaning $f(A \cap B) = \emptyset$. Equality is restored if and only if $f$ is injective.

In contrast to direct images, preimages commute with Boolean set operations:
$$
\begin{gather}
\textbf{Lemma: Fundamental Boolean Properties of Preimages} \\[5mm]
\text{Let } f: X \to Y \text{ and let } A', B' \subseteq Y. \text{ Then:} \\[3.5mm]
\text{1. Monotonicity: } A' \subseteq B' \implies f^{-1}(A') \subseteq f^{-1}(B') \\[2mm]
\text{2. Intersection Preservation: } f^{-1}(A' \cap B') = f^{-1}(A') \cap f^{-1}(B') \\[2mm]
\text{3. Union Preservation: } f^{-1}(A' \cup B') = f^{-1}(A') \cup f^{-1}(B')
\end{gather}
$$
(see [[Proof of Fundamental Boolean Properties of Preimages]])

Preimages also preserve set differences and complementation:
$$
\begin{gather}
\textbf{Proposition: Preimages of Differences and Complements} \\[5mm]
\text{Let } f: X \to Y. \text{ Then for any subsets } A', B' \subseteq Y: \\[3.5mm]
\text{1. Set Difference: } f^{-1}(A' \setminus B') = f^{-1}(A') \setminus f^{-1}(B') \\[2mm]
\text{2. Complementation: } f^{-1}(C_Y(A')) = C_X(f^{-1}(A'))
\end{gather}
$$
(see [[Proof of Preimages of Differences and Complements]])

The interaction between direct images and preimages satisfies cancellation bounds:
$$
\begin{gather}
\textbf{Proposition: Composition of Image and Preimage Operators} \\[5mm]
\text{Let } f: X \to Y. \text{ Then for any } A \subseteq X \text{ and any } B' \subseteq Y: \\[3.5mm]
\text{1. Expansion Bound: } A \subseteq f^{-1}(f(A)) \\[2mm]
\text{2. Contraction Bound: } f(f^{-1}(B')) \subseteq B'
\end{gather}
$$
(see [[Proof of Composition of Image and Preimage Operators]])

The exact attainment of these bounds characterizes surjectivity and bijectivity:
$$
\begin{gather}
\textbf{Proposition: Image-Preimage Criteria for Surjectivity and Bijectivity} \\[5mm]
\text{Let } f: X \to Y. \text{ Then:} \\[3.5mm]
\text{1. } f \text{ is surjective } \iff \forall B' \subseteq Y \, (f(f^{-1}(B')) = B') \\[2mm]
\text{2. } f \text{ is bijective } \iff (\forall A \subseteq X \, (f^{-1}(f(A)) = A)) \wedge (\forall B' \subseteq Y \, (f(f^{-1}(B')) = B'))
\end{gather}
$$
(see [[Proof of Image-Preimage Criteria for Surjectivity and Bijectivity]])

Finally, injectivity is characterized by five equivalent set-theoretic identities:
$$
\begin{gather}
\textbf{Theorem: Equivalent Characterizations of Injectivity} \\[5mm]
\text{Let } f: X \to Y \text{ be a mapping. The following statements are logically equivalent:} \\[3.5mm]
\text{1. } f \text{ is injective.} \\[2mm]
\text{2. } \forall A \subseteq X \, (f^{-1}(f(A)) = A). \\[2mm]
\text{3. } \forall A, B \subseteq X \, (f(A \cap B) = f(A) \cap f(B)). \\[2mm]
\text{4. } \forall A, B \subseteq X \, (A \cap B = \emptyset \implies f(A) \cap f(B) = \emptyset). \\[2mm]
\text{5. } \forall A, B \subseteq X \, (B \subseteq A \implies f(A \setminus B) = f(A) \setminus f(B)).
\end{gather}
$$
(see [[Proof of Equivalent Characterizations of Injectivity]])
