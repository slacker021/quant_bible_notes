---
dg-publish: true
---
# The Concept of a Set
Set theory serves as the structural foundation of modern mathematical sciences. From the construction of the real number continuum to the formulation of measure spaces, probability theory, and functional analysis, mathematical objects are formally defined as sets endowed with specific operational structures.

The initial intuitive formulation of a set, credited to *Georg Cantor*, provides an accessible starting point:
$$
\begin{gather}
\textbf{Definition: The Naive Concept of a Set} \\[5mm]
\text{A set is an unordered collection of definite distinct objects of perception or thought.} \\[2mm]
\text{A set is completely and uniquely determined by the elements that belong to it.}
\end{gather}
$$

>[!info]+ Remark: Starting Somewhere
>The reader may wonder as to the level of rigor and ambiguity present in the naive definition of a set, which is valid because an overly naive and intuitive definition may leave logical gaps that lead to the reader misinterpreting its definition and subsequence properties. A more rigorous and less ambiguous definition can be constructed but doing so is far beyond the scope of this repository's treatment of real analysis. Nevertheless, more properties of sets may be explored by the reader in other aspects of the mathematical sciences.
>
>An example of a definition that may be open to interpretation is what constitutes a soup. One may argue that soup is a dish that is of liquid consistency, is made with the combination of various ingredients, and is usually served hot. This is a definition many would agree with, yet others may immediately raise questions or provide examples that challenge this definition: 
>- Is cereal a soup? It is of liquid consistency and is made of various ingredients mixed together. However, it is not hot and is usually served cold.
>- *Borscht* is a famous European dish that is made from beets. On the surface, it seems like a soup. However, this is traditionally served cold. 
>
>With these questions in mind, what is a soup? Are there exceptions that should be considered soups? Perhaps the definition of a soup should be more precise and unambiguous so as to reduce the chances of an edge case occurring that makes it difficult to determine whether something qualifies for a soup.

If $x$ is an object and $P$ is a *unary predicate*—a property or condition—the expression $P(x)$ asserts that $x$ satisfies property $P$. In naive set theory, the collection of all objects satisfying property $P$ is denoted by:
$$
\begin{gather}
\{x \mid P(x)\} \tag{1}
\end{gather}
$$

The objects comprising a set are termed its *elements* or *members*. If a set is finite, it may be presented by an explicit enumeration of its elements, written as $\{x_1, x_2, \dots, x_n\}$. Conventional synonyms for the word *set* include:
- *Collection*
- *Family* (frequently used when the elements themselves are sets)
- *Totality*
- *Class* (reserved in formal axiomatic systems for collections broader than sets)

>[!danger]+ Intuition: Naive Comprehension and the Need for Axiomatic Restraint
>Cantor's intuitive definition assumes unrestricted comprehension: that any conceivable property $P(x)$ automatically defines a valid set. In unconstrained settings, this assumption collapses into severe logical contradictions, most notably Russell's Paradox. 
>
>Consider the property of a set not being a member of itself: $P(x) := (x \notin x)$. If one forms the collection $R := \{x \mid x \notin x\}$, one is forced to ask whether $R \in R$:
>- If $R \in R$, then by definition $R$ must satisfy the condition of membership, meaning $R \notin R$, a contradiction.
>- If $R \notin R$, then $R$ satisfies the defining property, requiring that $R \in R$, equally a contradiction.
>
>In algorithmic database design, an analogous defect occurs when a query is permitted to reference an unbounded, self-referential domain without constraint (such as an execution rule that acts upon all rules that do not trigger themselves). To establish a solid foundation for analysis, mathematics requires an axiomatic framework, such as *Zermelo-Fraenkel set theory*, that forbids unrestricted comprehension. In this formal framework, sets cannot be conjured from arbitrary verbal definitions; they can only be constructed from existing sets through bounded operations.

>[!example]+ Example: Simple Sets
>Below are examples of simple sets in day-to-day life:
>- In standard canonical scriptures of Christianity, the set of all wives of Adam contains Eve. Symbolically, this is represented as:
>  $$
>  \text{Set of all wives of Adam } = \{ \text{Eve} \} \tag{2}
>  $$
>- All US presidents who have served. 
>- The set of all people who attended the local concert:
> $$
>  \text{Who attended the concert } = \{\text{Jeffrey, Mark, Samantha}  \} \tag{3}
>  $$

### The Inclusion Relation
Mathematical set theory utilizes standardized relational symbols to express belonging, containment, and quantification:
- The expression $x \in X$ asserts that object $x$ is an element of set $X$. Conversely, $x \notin X$ asserts that $x$ is not an element of set $X$.
- Formal propositions deploy the universal quantifier $\forall$ ("for all", "for every", or "for each") and the existential quantifier $\exists$ ("there exists" or "there is at least one").
- Two sets $A$ and $B$ are defined to be **equal** ($A = B$) if and only if they possess identical elements:
$$
\begin{gather}
(A = B) \iff \forall x ((x \in A) \iff (x \in B)) \tag{4}
\end{gather}
$$
- Set $A$ is a **subset** of set $B$, denoted $A \subseteq B$ (or $A \subset B$), if every element of $A$ is also an element of $B$:
$$
\begin{gather}
(A \subseteq B) \iff \forall x ((x \in A) \implies (x \in B)) \tag{5}
\end{gather}
$$
- If $A \subseteq B$ and $A \neq B$, then $A$ is designated a *proper subset* of $B$, denoted $A \subsetneq B$. When $A \subseteq B$, set $B$ is termed the **superset** of $A$.
- From step 4 and step 5, two sets are equal if and only if mutual inclusion holds:
$$
\begin{gather}
(A = B) \iff (A \subseteq B) \wedge (B \subseteq A) \tag{6}
\end{gather}
$$
- The unique set containing no elements is designated the **empty set**, denoted $\emptyset$. It can be formally defined using any self-contradictory property, such as:
$$
\begin{gather}
\emptyset := \{x \in M \mid x \neq x\} \tag{7}
\end{gather}
$$

>[!question]+ Application: Inclusion as Filtering and Portfolio Composition
>Set equality is governed entirely by content rather than label or order. In portfolio management, a fund's holdings are invariant to the order in which execution tickets are generated; if Portfolio $A$ and Portfolio $B$ contain identical securities in identical quantities, they are the identical economic vehicle. 
>
>The relation $A \subseteq B$ reflects an investment mandate restriction: the investable universe of high-grade corporate debt ($A$) is a subset of the broader global fixed-income universe ($B$). Equality is verified by establishing mutual containment: proving that every asset satisfying criterion $A$ satisfies criterion $B$, and vice versa.

---
# Basic Set Operations
Given an overarching universal domain or ambient set $M$, new sets can be derived from existing subsets $A, B \subseteq M$ through three elementary Boolean operations: *union, intersection,* and *difference*:
$$
\begin{gather}
\textbf{Definition: Set Union} \\[5mm]
\text{The union of subsets } A \text{ and } B \text{ is the set of elements in } M \text{ that belong} \\[2mm]
\text{to at least one of the sets } A \text{ or } B. \text{ This is formally denoted as:} \\[3.5mm]
A \cup B := \{x \in M \mid (x \in A) \lor (x \in B)\}
\\[5mm]

\textbf{Definition: Set Intersection} \\[5mm]
\text{The intersection of subsets } A \text{ and } B \text{ is the set of elements in } M \text{ that belong} \\[2mm]
\text{simultaneously to both } A \text{ and } B. \text{ This is formally denoted as:} \\[3.5mm]
A \cap B := \{x \in M \mid (x \in A) \wedge (x \in B)\}
\\[5mm]

\textbf{Definition: Set Difference} \\[5mm]
\text{The difference of } A \text{ and } B \text{ (the relative complement of } B \text{ in } A\text{) is the set of} \\[2mm]
\text{elements belonging to } A \text{ that do not belong to } B. \text{ This is formally denoted as:} \\[3.5mm]
A \setminus B := \{x \in M \mid (x \in A) \wedge (x \notin B)\}
\end{gather}
$$
When the relative difference is taken with respect to the entire ambient set $M$, the resulting set is termed the absolute complement of $A$ with respect to $M$:
$$
\begin{gather}
\textbf{Definition: Set Complement} \\[5mm]
\text{Let } A \subseteq M. \text{ The complement of } A \text{ in } M \text{ consists of all elements in } M \\[2mm]
\text{that do not belong to } A. \text{ This is denoted as } C_M(A), \text{ } M \setminus A, \text{ or } A^c: \\[3.5mm]
C_M(A) := \{x \in M \mid x \notin A\}
\end{gather}
$$

>[!question]+ Application: Boolean Logic Mapped to Sample Spaces and Market States
>Set operations correspond directly to the basic logical connectives:
>- **Union ($A \cup B$):** Corresponds to the logical disjunction $\lor$. In financial econometrics, if state $A$ denotes a domestic sovereign default and state $B$ denotes a banking liquidity crisis, $A \cup B$ encompasses all scenario paths where at least one systemic crisis materializes.
>- **Intersection ($A \cap B$):** Corresponds to the logical conjunction $\wedge$. This isolates the compound shock: the market regime where sovereign default and banking liquidity collapse occur concurrently.
>- **Difference ($A \setminus B$) and Complement ($A^c$):** Corresponds to conditional exclusion and negation $\neg$. The complement $A^c$ encompasses all benign macroeconomic states where sovereign default is avoided. The algebra of sets is the exact mathematical grammar utilized in probability theory to construct $\sigma$-algebras of observable events.

>[!example]- Example: Pizza Preferences
>Let $C$ be the set of people who are interested in having pizza for dinner. However, they only have two options they can pick: Pepperoni, denoted as $B$, and Hawaiian, denoted as $A$. Therefore, $A$ represents the set of people who want pepperoni while $B$ denotes the set of people who want Hawaiian. Suppose that there are ten people who will be participating in tonight's dinner:
>$$
>C = \{  \text{Abel, Bart, Cain, Dan, Eve, Frank, Gerry, Harry, Iris, Jules} \} \tag{8}
>$$
>Suppose that Abel, Bart, and Cain prefer Pepperoni—while Dan, Eve, Frank, and Gerry prefer Hawaiian. Further suppose that Harry, Iris, and Jules are fine with either. The sets, when expanded:
>$$
>\begin{align}
>A = \{\text{Abel, Bart, Cain}  \} \\[2mm]
>B = \{ \text{Dan, Eve, Frank, Gerry} \} \\[2mm]
> A \cap B = \{ \text{Harry, Iris, Jules} \} \tag{9}
>\end{align}
>$$
>Now, suppose that the party was expanded to twenty people. Assume the original group $C$ remains the same but is now part of a bigger group $D$ that contains all twenty people. However, the other ten people have unknown identities. It could be said that $C$ is a proper subset of $D$ or that $C \subseteq D$. Additionally, anyone who is not part of the original group but is part of the overall family is $C_{D}$. If one wanted to denote anyone not part of the original group without mentioning any overall family, they may denote it as $C'$

---
# Fundamental Axioms of Set Theory
To provide an unambiguous foundation for real analysis, modern mathematics operates within the axiomatic framework established by *Ernst Zermelo* and *Adolf Fraenkel*, known as the *Zermelo-Fraenkel (ZF)* axioms, augmented by the *Axiom of Choice (ZFC).* These axioms govern set existence and set formation without circular definitions:
$$
\begin{gather}
\textbf{Axiom: The Principle of Extensionality} \\[5mm]
\text{Two sets } A \text{ and } B \text{ are equal if and only if they possess identical elements:} \\[3.5mm]
\forall x ((x \in A) \iff (x \in B)) \implies A = B
\\[5mm]

\textbf{Axiom: The Principle of Separation (Axiom of Subsets)} \\[5mm]
\text{To any set } A \text{ and any well-formed predicate } P(x), \text{ there corresponds a set } B \\[2mm]
\text{consisting precisely of those elements of } A \text{ that satisfy property } P: \\[3.5mm]
B = \{x \in A \mid P(x)\}
\end{gather}
$$

The Principle of Separation resolves the paradoxes of naive set theory: a property $P$ cannot create a set from the entire universe of mathematical objects; it can only extract a subset from an already existing set $A$.

A direct and immediate consequence of the Axiom of Separation is that the empty set is a subset of every set:
$$
\begin{gather}
\textbf{Proposition: The Empty Set as a Universal Subset} \\[5mm]
\text{Let } X \text{ be any set, and let } \emptyset \text{ denote the empty set. Then } \emptyset \subseteq X.
\end{gather}
$$
(see the [[Proof that the Empty Set is the Subset of Any Set|vacuous proof]] for more information on how this uses the [[Chapter 1 - Basic Rules of Logic|one of the basic rules of logic]].)

The formal demonstration of the empty set being a universal subset follows directly from vacuous truth in material implication: the condition $\forall x (x \in \emptyset \implies x \in X)$ is universally true because the antecedent $x \in \emptyset$ is false for all $x$.

$$
\begin{gather}
\textbf{Axiom: The Principle of the Union} \\[5mm]
\text{For any family of sets } \mathcal{M}, \text{ there exists a set } \bigcup \mathcal{M} \text{ whose elements are precisely} \\[2mm]
\text{those objects that belong to at least one member set of } \mathcal{M}: \\[3.5mm]
x \in \bigcup \mathcal{M} \iff \exists X ((X \in \mathcal{M}) \wedge (x \in X))
\end{gather}
$$

By combining the axiom of separation with the axiom of union, the arbitrary intersection of a nonempty family of sets $\mathcal{M}$ is rigorously defined as:
$$
\begin{gather}
\bigcap \mathcal{M} := \left\{x \in \bigcup \mathcal{M} \ \middle|\ \forall X ((X \in \mathcal{M}) \implies (x \in X))\right\} \tag{6}
\end{gather}
$$

$$
\begin{gather}
\textbf{Axiom: The Principle of Pairing} \\[5mm]
\text{For any two sets } X \text{ and } Y, \text{ there exists a set } Z \text{ whose elements are strictly } X \text{ and } Y: \\[3.5mm]
Z = \{X, Y\} \\[3.5mm]
\text{If } X = Y, \text{ the resulting collection is the singleton set } \{X\}.
\\[5mm]

\textbf{Axiom: The Principle of the Power Set} \\[5mm]
\text{For any set } X, \text{ there exists a set } \mathcal{P}(X), \text{ termed the power set of } X, \\[2mm]
\text{whose elements are all possible subsets of } X, \text{ and no other objects:} \\[3.5mm]
Y \in \mathcal{P}(X) \iff Y \subseteq X
\end{gather}
$$

To construct the infinite sequence of numbers underpinning continuous analysis, foundational set theory introduces the concept of set succession:
$$
\begin{gather}
\textbf{Definition: Successor Set} \\[5mm]
\text{For any set } X, \text{ the successor set } X^+ \text{ is constructed by adjoining the singleton } \{X\} \text{ to } X: \\[3.5mm]
X^+ := X \cup \{X\}
\\[5mm]

\textbf{Definition: Inductive Set} \\[5mm]
\text{A set } S \text{ is inductive if the empty set belongs to } S, \text{ and the successor of every} \\[2mm]
\text{element in } S \text{ also belongs to } S: \\[3.5mm]
(\emptyset \in S) \wedge (\forall X (X \in S \implies X^+ \in S))
\end{gather}
$$

$$
\begin{gather}
\textbf{Axiom: The Principle of Infinity} \\[5mm]
\text{There exists an inductive set.}
\end{gather}
$$

The axiom of infinity guarantees the existence of an infinite set, allowing for the construction of the natural numbers $\mathbb{N}$ via finite ordinals ($\emptyset =: 0$, $\emptyset^+ = \{0\} =: 1$, $1^+ = \{0, 1\} =: 2$, and so forth).

$$
\begin{gather}
\textbf{Axiom: The Principle of Replacement} \\[5mm]
\text{Let } \mathcal{F}(x, y) \text{ be a functional predicate such that for every } x \in X, \text{ there exists a unique} \\[2mm]
\text{object } y \text{ satisfying } \mathcal{F}(x, y). \text{ Then the collection of image values } \{y \mid \exists x \in X \, \mathcal{F}(x, y)\} \text{ is a set.}
\end{gather}
$$

>[!info]+ Remark: Operational Scope of Replacement
>The Axiom of Replacement guarantees that mapping a set across a functional relation yields another set rather than an unmanageable proper class. While essential for establishing transfinite ordinals in higher mathematical logic, basic real analysis can be constructed relying primarily on the first six axioms. In other words, the principle of replacement shall not be used in the construction of the first two volumes of real analysis. 

 These seven axioms, together with the *Axiom of Regularity*—which forbids circular membership cycles such as $x \in x$—constitute the Zermelo-Fraenkel (ZF) system. To complete the architecture required for modern functional analysis, an independent postulate is introduced:
$$
\begin{gather}
\textbf{Axiom: The Principle of Choice (Axiom of Choice)} \\[5mm]
\text{For any family } \mathcal{F} \text{ of nonempty, pairwise disjoint sets, there exists a set } C \\[2mm]
\text{such that for every set } X \in \mathcal{F}, \text{ the intersection } X \cap C \text{ contains exactly one element.}
\end{gather}
$$

Equivalently, the *Axiom of Choice* states that for any arbitrary collection of nonempty sets, there exists a choice function $f$ that selects an element from each set, even in the absence of an explicit algorithmic selection rule.

---
# Useful Properties of Set Algebra
From these foundational axioms, algebraic laws govern the interaction of unions, intersections, and complements. 

De Morgan's Laws establish that complementation inverts conjunctions and disjunctions:
$$
\begin{gather}
\textbf{Proposition: De Morgan's Laws of Set Complements} \\[5mm]
\text{Let } M \text{ be an ambient set and let } A, B \subseteq M. \text{ Then:} \\[3.5mm]
C_M(A \cup B) = C_M(A) \cap C_M(B) \\[2.5mm]
C_M(A \cap B) = C_M(A) \cup C_M(B)
\end{gather}
$$
(See [[Proof of de Morgan's Laws of Set Complements]])

Distributivity governs the interaction between unions and intersections:
$$
\begin{gather}
\textbf{Proposition: Distributive Laws of Set Operations} \\[5mm]
\text{Let } A, B, \text{ and } C \text{ be arbitrary sets. Then:} \\[3.5mm]
A \cap (B \cup C) = (A \cap B) \cup (A \cap C) \\[2.5mm]
A \cup (B \cap C) = (A \cup B) \cap (A \cup C)
\end{gather}
$$
(See [[Proof of the Distributive Laws of Intersection and Union]])

The behavior of subsets under complementation satisfies duality principles:
$$
\begin{gather}
\textbf{Lemma: Fundamental Properties of Complementation} \\[5mm]
\text{Let } A, B, \text{ and } S \text{ be subsets of an ambient set } M. \text{ Then:} \\[3.5mm]
(A \subseteq S) \wedge (B \subseteq S) \iff (A \cup B) \subseteq S \\[2.5mm]
(A \subseteq B) \iff (C_M(B) \subseteq C_M(A)) \\[2.5mm]
C_M(C_M(A)) = A
\end{gather}
$$
(See [[Proof of Elementary Lemma of Set Complementation]])

>[!question]+ Application: De Morgan's Duality in Multi-Factor Risk Boundaries
>De Morgan's Laws describe the mathematics of system compliance versus failure:
>- **Breaching a Composite Risk Threshold:** Suppose a trading desk is required to maintain leverage below a set ceiling ($A$) and portfolio Value-at-Risk below a mandate ($B$). Safe operation requires satisfying both conditions simultaneously: $A \cap B$. A risk violation occurs in the complement:
>$$
>C_M(A \cap B) = C_M(A) \cup C_M(B)
>$$
>To enter distress, the desk does not need to violate both constraints; failing at least one condition ($C_M(A)$ or $C_M(B)$) immediately triggers a systemic breach.
>- **Preserving the Inclusion Order under Complementation:** The second relation in Lemma 1 demonstrates order-reversal: if high-yield debt ($A$) is a subset of corporate debt ($B$), then non-corporate assets ($C_M(B)$) are necessarily a subset of non-high-yield assets ($C_M(A)$). Eliminating a broad category automatically excludes all of its subdivisions.
