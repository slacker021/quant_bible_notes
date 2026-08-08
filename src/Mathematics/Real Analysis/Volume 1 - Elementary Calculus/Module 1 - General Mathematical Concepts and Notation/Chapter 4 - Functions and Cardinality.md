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
\text{2. Single-Valuedness (Uniqueness): } \forall x \in X \, \forall y_1, y_2 \in Y \, (((x, y_1) \in f \wedge (x, y_2) \in f) \implies y_1 = y_2)
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

>[!warning]+ Warning: Inverse Function versus Preimage Operator
>The notation $f^{-1}$ carries two distinct mathematical meanings that must never be conflated:
>1. The **preimage operator** $f^{-1}: \mathcal{P}(Y) \to \mathcal{P}(X)$ maps subsets of the codomain to subsets of the domain. It is universally well-defined for *every* function, requiring no special properties of $f$.
>2. The **inverse mapping** $f^{-1}: Y \to X$ is an actual pointwise function that exists if and only if $f$ is a bijection.

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

>[!danger]+ Intuition: Inverse Functions
>The inverse of the function, [[Proof of the Existence of Inverse Mappings|assuming it exists]], effectively undoes the original function—which means that the range of the original function is the domain of the inverse while the range of the original function is the domain of the inverse. 
>
>Going back to the meat grinder example, suppose that scientists invent a machine that is able to take ground meat and turn it back into the whole meat. Thus, the reverse-meat grinder would turn ground beef into a whole chunk of steak. 

>[!example]- Example: Mathematical and Physical Functional Relations
>1. **Geometric Scaling:** The equations $L(r) = 2\pi r$ and $V(r) = \frac{4}{3}\pi r^3$ define mappings from the positive real numbers to themselves: $L, V: \mathbb{R}_{>0} \to \mathbb{R}_{>0}$. Both functions are strictly monotonically increasing, rendering them injective. Furthermore, because their limits tend to $0$ as $r \to 0$ and to $\infty$ as $r \to \infty$, the intermediate value theorem guarantees that their range is $\mathbb{R}_{>0}$, establishing that both mappings are bijections.
>2. **Universal Physical Constants:** Let $c: X \to \mathbb{R}$ assign to each physical measurement framework $x \in X$ the speed of light in *vacuo*. The mapping is constant: $\forall x \in X \, (c(x) = 299{,}792{,}458\text{ m/s})$. This mapping is neither injective (all reference frames yield the identical value) nor surjective onto $\mathbb{R}$ (the range consists of a single point).
>3. **Spacetime Transformations:** The Galilean transformation $G: \mathbb{R}^2 \to \mathbb{R}^2$ on spacetime coordinates $(x, t)$ defined by $x' = x - vt$ and $t' = t$ is a linear bijection with an inverse given by $x = x' + vt'$ and $t = t'$. Similarly, the relativistic Lorentz transformation $L: \mathbb{R}^2 \to \mathbb{R}^2$ for relative velocity $|v| < c$ defined by:
>$$x' = \frac{x - vt}{\sqrt{1 - \left(\frac{v}{c}\right)^2}}, \qquad t' = \frac{t - \left(\frac{v}{c^2}\right)x}{\sqrt{1 - \left(\frac{v}{c}\right)^2}}$$
>is a continuous linear bijection with an inverse obtained by reversing the sign of velocity $v$.
>4. **Coordinate Projections:** The canonical projection $\operatorname{pr}_1: X_1 \times X_2 \to X_1$ defined by $(x_1, x_2) \mapsto x_1$ is surjective provided $X_2 \neq \emptyset$. However, it is not injective whenever $X_2$ contains two or more distinct elements.
>5. **Set Complementation:** For an ambient set $M$, the complementation operator $C_M: \mathcal{P}(M) \to \mathcal{P}(M)$ assigning $A \mapsto M \setminus A$ is an involution ($C_M(C_M(A)) = A$). Because it serves as its own inverse, $C_M$ is a bijection.
>6. **Characteristic (Indicator) Functions:** For a subset $E \subseteq M$, the characteristic function $\chi_E: M \to \mathbb{R}$ is defined by:
>$$\chi_E(x) := \begin{cases} 1, & x \in E \\ 0, & x \in M \setminus E \end{cases}$$
>Unless $M$ has cardinality at most 2, $\chi_E$ is neither injective nor surjective onto $\mathbb{R}$.
>7. **Evaluation Functionals:** Let $M(X; Y)$ denote the space of all functions mapping $X$ into $Y$. For a fixed $x_0 \in X$, the evaluation mapping $\operatorname{ev}_{x_0}: M(X; Y) \to Y$ is defined by $\operatorname{ev}_{x_0}(f) := f(x_0)$. When $Y = \mathbb{R}$, this functional is surjective but non-injective, mapping an infinite-dimensional function space to a single scalar.
>8. **Arc-Length Functional:** Let $\Gamma$ denote the collection of smooth curves connecting two fixed endpoints on a Riemannian manifold. The arc-length functional $L: \Gamma \to \mathbb{R}$ assigns to each curve $\gamma \in \Gamma$ its geometric length. This functional is neither injective (infinitely many distinct curves possess identical lengths) nor surjective onto $\mathbb{R}$ (lengths are bounded below by the geodesic distance).
>9. **Shift Operators:** On the function space $M(\mathbb{R}; \mathbb{R})$, fixing $a \in \mathbb{R}$ defines the shift operator $T_a: M(\mathbb{R}; \mathbb{R}) \to M(\mathbb{R}; \mathbb{R})$ by $(T_a f)(x) := f(x + a)$. The operator $T_a$ is a bijection whose inverse is $T_{-a}$.
>10. **Phase Space Trajectories:** In classical mechanics, the state of an $n$-particle system is represented by its configuration coordinates $q \in \mathbb{R}^{3n}$ and velocity vectors $v \in \mathbb{R}^{3n}$, forming the $6n$-dimensional phase space $\Phi = \mathbb{R}^{6n}$. The temporal evolution of the system is a mapping $\gamma: \mathbb{R} \to \mathbb{R}^{6n}$. The Hamiltonian total energy $H: \Phi \to \mathbb{R}$ maps the phase space to energy levels. For an isolated conservative system, $H(\gamma(t)) = E_0$ is constant along trajectories, rendering the restriction of energy to a trajectory neither injective nor surjective.

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
(g \circ f)(x) := g(f(x)) \tag{4}
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
The formalization of bijective mappings allows for the rigorous comparison of the sizes of infinite sets without relying on counting. This framework is grounded in Georg Cantor's *principle of equipotence*:
$$
\begin{gather}
\textbf{Definition: Equipotence (Equinumerosity)} \\[5mm]
\text{Two sets } X \text{ and } Y \text{ are equipotent, denoted } X \sim Y \text{ or } |X| = |Y|, \\[2mm]
\text{if and only if there exists a bijective mapping } f: X \to Y.
\end{gather}
$$

### Equipotence as an Equivalence Relation
Let $\mathcal{S}$ be any family of sets. The equipotence relation $\sim$ is an equivalence relation on $\mathcal{S}$, satisfying the three defining axioms:
- **Reflexivity:** For any set $X$, the identity mapping $\operatorname{id}_X: X \to X$ defined by $\operatorname{id}_X(x) = x$ is a bijection, establishing $X \sim X$.
- **Symmetry:** If $X \sim Y$, there exists a bijection $f: X \to Y$. Its inverse $f^{-1}: Y \to X$ is also a bijection, establishing $Y \sim X$.
- **Transitivity:** If $X \sim Y$ and $Y \sim Z$, there exist bijections $f: X \to Y$ and $g: Y \to Z$. The composite mapping $g \circ f: X \to Z$ is a bijection, establishing $X \sim Z$.

Consequently, equipotence partitions any collection of sets into equivalence classes. Each equivalence class represents a distinct *cardinal number* (or *cardinality*).

### Finite, Countable, and Uncountable Sets
Using the natural numbers $\mathbb{N} := \{1, 2, 3, \dots\}$ as a foundational benchmark, sets are classified into distinct cardinal regimes:
1. **Finite Sets:** A set $X$ is finite if and only if $X = \emptyset$ or there exists some $n \in \mathbb{N}$ such that $X \sim \{1, 2, \dots, n\}$. Its cardinality is denoted $|X| = n$.
2. **Infinite Sets:** A set is infinite if and only if it is not finite.
3. **Countably Infinite (Denumerable) Sets:** A set $X$ is countably infinite if and only if it is equipotent to the natural numbers: $X \sim \mathbb{N}$. Its cardinality is designated by the transfinite symbol $\aleph_0$ (aleph-null).
4. **Countable Sets:** A set is countable if and only if it is finite or countably infinite ($|X| \le \aleph_0$).
5. **Uncountable Sets:** An infinite set is uncountable if and only if it is not countable ($|X| > \aleph_0$).

Cantor's diagonal argument demonstrates that the real continuum $\mathbb{R}$ is uncountable ($|\mathbb{R}| = \mathfrak{c} = 2^{\aleph_0} > \aleph_0$). Furthermore, *Cantor's Theorem* establishes that there is no largest cardinal number:
$$
\begin{gather}
\textbf{Cantor's Theorem: } \\[5mm]
\text{For every set } X, \text{ the cardinality of } X \text{ is strictly less than the} \\[2mm]
\text{cardinality of its power set } \mathcal{P}(X): \\[3.5mm]
|X| < |\mathcal{P}(X)|
\end{gather}
$$
(see [[Proof of Cantor's Theorem]])

---
# Useful Properties of Functions
From the foundational definitions of mappings, images, and preimages, several structural properties governing subset operations are established.

Let $f: X \to Y$ be an arbitrary mapping, and let $A, B \subseteq X$:
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
\text{2. Intersection Commutativity: } f^{-1}(A' \cap B') = f^{-1}(A') \cap f^{-1}(B') \\[2mm]
\text{3. Union Commutativity: } f^{-1}(A' \cup B') = f^{-1}(A') \cup f^{-1}(B')
\end{gather}
$$
(see [[Proof of Lemma of Useful Facts about Functions]])

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
