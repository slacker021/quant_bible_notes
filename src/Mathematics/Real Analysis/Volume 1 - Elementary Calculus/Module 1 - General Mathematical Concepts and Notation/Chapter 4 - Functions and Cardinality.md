---
dg-publish: true
---
# Functional Relations
It is in this chapter that a special type of [[Chapter 3 - Cartesian Products and Relations|relation]] is introduced: The *functional* relation. This is fundamental in mathematics and other branches of the formal sciences. A functional relation, which can simply be referred to as a *function*, is a binary relation that satisfies a unique-existence constraint on its coordinate pairs. By building directly on the relational infrastructure introduced in [[Chapter 3 - Cartesian Products and Relations|chapter 3]], they can be integrated cleanly into [[Chapter 2 - Elementary Set Theory|set theory]]: 
$$
\begin{gather}
\textbf{Definition: Function (Mapping)} \\[5mm]
\text{Let } X \text{ and } Y \text{ be sets. A function } f \text{ from X to Y}, \text{ denoted as } \\[2mm]
f:X \rightarrow Y, \text{ is a binary relation } f \subset X \times Y \text{ that has the folllowing constraint: } \\[3.5mm]
\forall x \in X \ \exists y \in Y ((x,y) \in f)
\end{gather}
$$

> [!danger]+ Intuition: Functions as a Machine
> It helps to think of a function as a "machine" or transformation that takes in an input and leads to an output. The input is transformed through a series of instructions that gets it to its destination. For any given coordinate $(x,y) \in f$, the unique element $y$ is designated as the value of the function $f$ at the argument $x$, denoted by the functional notation $y = f(x)$. 

In the case of the function $f:X \rightarrow Y$, it has two sets, where one is mapped to the other: 
1. The set $X$ is the domain of the function, which is denoted as $\text{dom}(f)$. 
2. The set $Y$ is the codomain of the function, which is denoted as $\text{codom}(f)$. 
It is important to note that $Y$ is the set of all possible outputs, where some elements in the codomain may not be mapped to an element in the domain. Furthermore, a relation is only a function if no single element in the domain maps to two or more elements in the codomain. 

There is a special subset of the codomain known as the *range*, which is the subset of the codomain that has each element mapped to at least one element in the domain: 
$$
\begin{gather}
\textbf{Definition: Range of a Function} \\[5mm]
\text{For a function } f:X \rightarrow Y, \text{ the range of } f \text{ is the set defined by } \\[3.5mm]
\text{ran}(f) := \{ y \in Y \mid \exists x \in X \, (y = f(x)) \}
\end{gather}
$$
The range is also known as the *image* of the function. The behavior of a function can be generalized to act on entire subsets of the domain and codomain. If $A \subset X$, then the image of $A$ under $f$ is the subset $f(A) \subset Y$, which can be defined as
$$
 f(A) := \{y \in Y \ | \ \exists x \in A (y = f(x)) \} \tag{1}	
$$
### Classifications of Mappings
To analyze how distinct spaces correspond to one another, functions are classified based on the density and uniqueness of their coordinate distribution across the domain and codomain. Special types of mappings can be constructed using **definitions 1 and 2**. 

$$
\begin{gather}
\textbf{Definition: Injection (One-to-One)} \\[5mm]
\text{A mapping } f:X \rightarrow Y \text{ is an injection if and only if each element in its domain} \\[2mm]
\text{is mapped to exactly one element in its codomain (and vice versa). Symbolically: } \\[3.5mm]
\forall x_{1} \forall x_{2} \in X (f(x_{1}) = f(x_{2}) \implies x_{1} = x_{2})
\end{gather}
$$

>[!info]+ Remark: 
>In other words, an injective function maps every distinct input to a unique output. In an injection, no two different inputs produce the same output. 

$$
\begin{gather}
\textbf{Definition: Surjection (Onto)} \\[5mm]
\text{A mapping } f:X \rightarrow Y \text{ is a surjection if any only if the range is identically } \\[2mm]
\text{equal to the codomain. Symbolically: } \\[3.5mm]
\forall y \in Y \ \exists x \in X (f(x) = y) \iff \text{ran}(f) = Y
\end{gather}
$$

> [!info]+ Remark: 
> Additionally, a surjective function has every element in its codomain mapped to at least one element in the domain. 

$$
\begin{gather}
\textbf{Definition: Bijection (One-to-One Correspondence)} \\[5mm]
\text{A mapping } f:X \rightarrow Y \text{ is a bijection if and only if it's both} \\ \text{surjective and injective. Symbolically: }  \\[3.5mm]
(\forall x_1, x_2 \in X \, (f(x_1) = f(x_2) \implies x_1 = x_2)) \wedge (\forall y \in Y \, \exists x \in X \, (f(x) = y))
\end{gather}
$$

Bijective functions enable the existence of *inverse mappings*: 
$$
\begin{gather}
\textbf{Definition: Inverse Mappings } \\[5mm]
\text{Let } f:X \rightarrow Y \text{ be a bijective mapping. The inverse mapping } \\[2mm]
\text{ of } f, \text{ denoted as } f^{-1} : Y \rightarrow X, \text{ is the binary relation defined by } \\[3.5mm]
f^{-1} := \{ (y, x) \in Y \times X \mid (x, y) \in f \}
\end{gather}
$$

(see [[Proof of the Existence of Inverse Mappings|proof]]) 

Because the source mapping $f$ is surjective, the domain of $f^{-1}$ is guaranteed to be the entirety of $Y$. Because $f$ is injective, the relation $f^{-1}$ satisfies the uniqueness constraint of Definition 1, establishing $f^{-1}$ as a valid function mapping $Y \to X$ such that $f^{-1}(y) = x \iff f(x) = y$. The inverse of a function is also known as its *preimage*. 

> [!danger]+ Intuition: Inverse Functions Undo the Original
> A clever way to think about the inverse of a function $f$ is that it "undoes" what the original function does.

> [!example]- Example: Different Types of Functions
> The following below are examples of functional relations. Furthermore, some of these can be classified into injective, surjective, or bijective functions:
>1. The formulae $l = 2 \pi r$ and $V = \frac{4}{3} \pi r^3$ establish functional relationships between the circumference $l$ of a circle and its radius $r$, as well as the volume $V$ of a ball and its radius $r$. Both formulae provide a particular function $f:\mathbb{R}_{+} \rightarrow \mathbb{R}_{+}$ defined on the set of positive real numbers in the same set. In functional notation, these take the form of $c(r) = 2 \pi r$, which is the circle's circumference, and $V(r) = \frac{4}{3}\pi r^3$, which is the circle's volume. The circumference function $c(r)$ and volume $v(r)$ function are both bijective mappings because each input for both functions has a unique output, as well as each function's range being equal to their codomains. 
>2. Let $c:X \rightarrow \mathbb{R}$ be the function that assigns each coordinate system $x \in X$ the value of $c(x)$ the speed of light in *vacuo* measured using those coordinates. The function $c:X \rightarrow \mathbb{R}$ is constant, where for any value $x \in X$, it has the value $c$. This is a fundamental experimental fact, where the speed of light is a constant 299,792,458 meters per second. As a function, it's neither injective nor surjective because the only element in the range is the constant speed while its codomain is the set of real numbers, and each element in its domain is mapped to only one element in its domain. 
>3. The mapping $G:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ (the direct product $\mathbb{R}^2 = \mathbb{R} \times \mathbb{R} = \mathbb{R}_{t} \times \mathbb{R}_{x}$ of the time axis $\mathbb{R}_{t}$ and spatial axis $\mathbb{R}_{x}$) into itself is defined by the formulae $x' = x - vt$ and $t' = t$, is the classical Galilean transformation from one inertial coordinate system $(x,t)$ to another system $(x',t')$ that is in motion relative to the first at speed $v$. The same purpose is served by the mapping $L:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ defined by the relations
>	$$x' = \frac{x - vt}{1 - \left( \frac{v}{c} \right)^2} \tag{2} $$
>and 
>	$$t' = \frac{t - (\frac{v}{c^2})x}{\sqrt{1 - (\frac{v}{c})^2 }} \tag{3} $$
>Both transforms are bijective since each input maps to a distinct output, and the codomain and range of both are equal. 
>4. The *projection* $X_{1} \times X_{2} \rightarrow X_{1}$ defined by the correspondence $(x_{1},x_{2}) \in X_{1} \times X_{2} \mapsto x_{1} \in X_{1}$ is a function. The second projection $\text{pr}_{2}:X_{1} \times X_{2}$ is defined similarly. Both functions are surjective assuming $X_{2} \neq \emptyset$. 
>5. Let $\mathcal{P}(M)$ be the set of subsets of the set $M$. To each set $A \in \mathcal{P}(M)$, the set $C_{M}(A) \subset \mathcal{P}(M)$ is assigned, that is, to complement to $A$ in $M$. The mapping $C_{M}: \mathcal{P}(M) \rightarrow \mathcal{P}(M)$ is obtained. This mapping is a bijection. 
>6. Let $E \subset M$. The real-valued function $χE: M \rightarrow \mathbb{R}$ is defined on the set $M$ by the conditions $(χE (x) = 1 \text{ if } x ∈ E) ∧ (χE (x) = 0 \text{ if } x ∈ C_{M} E)$is called the characteristic function of the set E. This function is neither injective nor surjective. 
>7. Let $M(X; Y)$ be the set of mappings of the set $X$ into the set $Y$ and $x_0$ a fixed element of $X$. To any function $f \in M(X; Y)$, the value $f(x_{0}) \in Y$ is assigned at element $x_{0}$. This relation defines a function $F: M(X; Y) \rightarrow Y$. In particular, if $Y = \mathbb{R}$, that is, $Y$ is the set of real numbers, then to each function $f:X \rightarrow \mathbb{R}$ the function $F:M(X; \mathbb{R})$ assigns the number $F(f) = f(x_{0})$. Thus, $F$ is a function defined on functions. This class of functions is called *functionals*. The first function is surjective while the second one is neither. 
>8. Let $\Gamma$ be the set of curves lying on a surface and joining two given points on the surface. To each curve $\gamma \in \Gamma$ one can assign its length. The function $F: \Gamma \rightarrow \mathbb{R}$ can then be obtained, which is used to assign the shortest curve, or as it's called, the *geodesic* between two given points on the surface. This function is bijective. 
>9. Consider the set $M(\mathbb{R}; \mathbb{R})$ of real-valued functions defined on the entire real line $\mathbb{R}$. After fixing a number $a \in \mathbb{R}$, each function is assigned $f \in M(\mathbb{R}; \mathbb{R})$ that function $f_{a} \in M(\mathbb{R}; \mathbb{R})$ connected with the relation $f_{a}(x) = f(x + a)$. The function $f_{a}(x)$ is usually called the *translate* or *shift* of the function $f$ by $a$. The mapping $A:M(\mathbb{R};\mathbb{R}) \rightarrow M(\mathbb{R}; \mathbb{R})$ that arises in this way is called the *translation* of *shift operator*. This operator $A$ is defined on functions and its values are also functions $f_{a} = A(f)$. This is a bijective function. 
>10. The position of a particle in space is determined by an ordered triple of numbers $(x,y,z)$ called its spatial coordinates. The set of all such ordered triples can be thought of as the direct product $\mathbb{R} \times \mathbb{R} \times \mathbb{R} = \mathbb{R}^3$ of the three real lines $\mathbb{R}$. A particle in motion is located at some point of the space $\mathbb{R}^3$ having coordinates $(x(t), y(t),z(t))$ at each instant $t$ of time. Thus, the motion of a particle can be interpreted as a mapping $\gamma:\mathbb{R} \rightarrow \mathbb{R}^3$, where $\mathbb{R}$ is the time axis and $\mathbb{R}^3$ is the three-dimensional space. If a system consists of $n$ particles, its configuration is defined by the position of each of the particles, that is, it's defined by an ordered set $(x_{1}, y_{1},z_{1};x_{2}, y_{2}, z_{2};\dots x_{n},y_{n},z_{n})$ consisting of $3n$ numbers. The set of all such ordered sets is called the *configuration space* of the system of $n$ particles. Consequently, the configuration space of system of $n$ particles can be interpreted as the direct product $\mathbb{R}^3 \times \mathbb{R}^3 \times \dots \times \mathbb{R}^3 = \mathbb{R}^{3n}$ of $n$ copies of $\mathbb{R}^{3}$. To the motion of a system of $n$ particles there corresponds a mapping $\gamma:\mathbb{R} \rightarrow \mathbb{R}^{3n}$ of the time axis into the configuration space of the system. This function is neither surjective nor injective. 
>11. The potential energy $U$ of a mechanical system is connected with the mutual positions of the particles of the system, that is, it's determined by the configuration that the system has. Let $Q$ be the set of possible of possible configurations of a system. This is a certain subset of the configuration space of the system. To each position $q \in Q$ there corresponds a certain value $U(q)$ of the potential energy of the system. Thus the potential energy is a function $U:Q \rightarrow \mathbb{R}$ is defined on a subset $Q$ of the configuration space with values in the domain $\mathbb{R}$ of real numbers. This function is neither injective nor surjective. 
>12. The kinetic energy $K$ of a system of $n$ material particles depends on their velocities. The total mechanical energy of the system $E$, defined as $E = K + U$, that is, the sum of the kinetic and potential energies, thus depends on both the configuration $q$ of the system and the set of velocities $v$ of its particles. Like the configuration $q$ of the particles in space, the set of velocities $v$, which consists of $n$ three-dimensional vectors, can be defined as an ordered set of $3n$ numbers. The ordered pairs $(q,v)$ corresponding to the states of the system form a subset $\Phi$ in the direct product $\mathbb{R}^{3n} \times \mathbb{R}^{3n} = \mathbb{R}^{6n}$, called the *phase* space of the system of $n$ particles (to be distinguished form the configuration space $\mathbb{R}^{3n}$). The total mechanical energy of the system is therefore a function $E:\Phi \rightarrow \mathbb{R}$ defined on the subset $\Phi$ of the phase space $\mathbb{R}^{6n}$ and assuming values in the domain $\mathbb{R}$ of real numbers. In particular, if the system is isolated, that is, no external forces are acting on it, then by the law of the conservation of energy, at each point of the set $\Phi$ of states of the system the function $E$ will have the same value $E_{0} \in \mathbb{R}$. This is neither an injective nor surjective function. 

---
# Composite Functions
When functions act sequentially, their operations can be chained together: 
$$
\begin{gather} \textbf{Definition: Composition of Mappings} \\[5mm] \text{Let } f: X \to Y \text{ and } g: Y \to Z \text{ be mappings. The composition } g \circ f: X \to Z \\ \text{is the mapping defined set-theoretically by the relation:} \\[3.5mm] g \circ f := \{ (x, z) \in X \times Z \mid \exists y \in Y \, ((x, y) \in f \wedge (y, z) \in g) \} \end{gather}
$$
Evaluating this composition pointwise yields the standard identity
$$
(g \circ f)(x) := f(f(x)) \tag{2}
$$
In the case of three functions being chained together, a useful rule can be inferred: 
$$
\begin{gather}
\textbf{Theorem: Associative Property of Composite Functions} \\[5mm]
\text{If } f: X \to Y, g: Y \rightarrow Z, \text{ and } h: Z \rightarrow W, \text{ then } \\[2mm]
h \circ (g \circ f) = (h \circ g) \circ f
\end{gather}
$$
(See [[Proof of the Associative Property of Composite Functions|proof]])

---
# Set Cardinality and Cantor's Framework
The formalization of bijections enables the comparison of the "sizes" of sets without having to manually count the amount of elements in the set. In fact, manually counting infinite sets is impossible. This framework is built on the Cantorian principle of equipotence:
$$
\begin{gather}
\textbf{Definition: Equipotence (Equinumerosity)} \\[5mm]
\text{Two sets } X \text{ and } Y \text{are equipotent, denoted as } X \sim Y \text{ or } \\[2mm]
|X| = |Y|, \text{ if and only if } \text{ there exists a bijective mapping } f:X \rightarrow Y. 
\end{gather}
$$
### Equipotence as an Equivalence Relation
Let $\mathcal{S}$ be any family of sets. The equipotence relation $\sim$ is an equivalence relation on $\mathcal{S}$ because it satisfies the standard triad of relational constraints:
- **Reflexivity:** For any set $X$, the identity mapping $\operatorname{id}_X: X \to X$ defined by $\operatorname{id}_X(x) = x$ is trivially bijective, establishing $X \sim X$.
- **Symmetry:** If $X \sim Y$, there exists a bijection $f: X \to Y$. The inverse mapping $f^{-1}: Y \to X$ is verified to be a bijection, establishing $Y \sim X$.
- **Transitivity:** If $X \sim Y$ and $Y \sim Z$, there exist bijections $f: X \to Y$ and $g: Y \to Z$. The composition $g \circ f: X \to Z$ is a bijection, establishing $X \sim Z$.

Consequently, the equipotence relation partitions any family of sets into equivalence classes, where each class represents a distinct *cardinal number* (or *cardinality*).
### Finite, Countable, and Uncountable Sets

Using the natural numbers $\mathbb{N} := \{1,2,3, \dots \}$ as a reference, sets as classified into distinct cardinal regimes: 
1. *Finite Sets*: A set $X$ is finite if any only if $X = \emptyset$ or there exists some $n \in \mathbb{N}$ such that $X \sim \{1, 2, \dots, n\}$. The cardinality of a finite set is denoted by its natural number count. 
2. *Infinite Sets*: A set is infinite if and only if it is not finite.
3. *Countably Infinite (Denumerable) Sets*: A set $X$ is countably infinite if and only if it shares the exact same cardinality as the natural numbers. Symbolically: $X \sim \mathbb{N}$. This cardinality is denoted by the transfinite symbol $\aleph_0$ (aleph-null).
4. *Countable Sets*: A set is countable if and only if it is finite or countably infinite.
5. *Uncountable Sets:* An infinite set is uncountable if and only if it is not countable.

An important implication is *Cantor's Theorem*, which establishes that there's no maximum cardinal number; The cardinality of any power set is strictly greater than the cardinality of its parent set: 
$$
\begin{gather} \textbf{Cantor's Theorem: } \\[5mm] \text{For any arbitrary set } X, \text{ the cardinality of } X \text{ is strictly less than the} \\[2mm] \text{cardinality of its power set } \mathcal{P}(X). \text{ Symbolically: } |X| < |\mathcal{P}(X)| \end{gather}
$$
(see [[Proof of Cantor's Theorem|proof]])

---
# Useful Facts about Functions
The various theorems and definitions can be used to derive the following useful facts for determining the properties of functions in various contexts. 
Let $f: X \rightarrow Y$ be a mapping from $X$ to $Y$. If $A$ and $B$ are subsets of $X$, then the following theorems hold true: 
$$
\begin{gather}
\textbf{Proposition: } \\[5mm]
\text{1. } A \subset B \implies f(A) \subset f(B) \neq A \subset B \\[2mm]
\text{2. } A \neq \emptyset \implies f(A) \ne \emptyset \\[2mm]
\text{3. } f(A \cap B) \subset f(A) \cap f(B) \\[2mm]
\text{4. } f(A \cup B) = f(A) \cup f(B)
\end{gather}
$$
(see [[Proof of Proposition 1 of Useful Facts about Functions|proof]])
$$
\begin{gather} 
\textbf{Lemma: } \\[5mm]
\text{If } A' \text{ and } B' \text{ are subsets of } Y, \text{ then } \\[3.5mm]
\text{1. } A' \subset B' \implies f^{-1}(A') \subset f^{-1}(B') \\[2mm]
\text{2. } f^{-1} (A' \cap B') = f^{-1} (A') \cap f^{-1} (B) \\[2mm]
\text{3. } f^{-1} (A' \cup B') = f^{-1}(A') \cup f^{-1}(B')
\end{gather}
$$
(see [[Proof of Lemma of Useful Facts about Functions|proof]])
$$
\begin{gather}
\textbf{Proposition: } \\[5mm]
\text{If } B' \subset A' \subset Y, \text{ then } \\[3.5mm]
\text{1. } f^{-1}(A' \backslash B') = f^{-1}(A') \backslash f^{-1}(B') \\[2mm]
\text{2. } f^{-1} (C_{Y}A') = C_{X}f^{-1}(A')
\end{gather}
$$
(see [[Proof of Proposition 2 of Useful Facts about Functions|proof]])
$$
\begin{gather}
\textbf{Proposition: } \\[5mm]
\text{For any } A \subset X \text{ and } B' \subset X \\[3.5mm]
\text{1. } A \subset f^{-1}(f(A)) \\[2mm]
\text{2. } f(f^{-1}(B')) \subset B'   
\end{gather}
$$
(see [[Proof of Proposition 3 of Useful Facts about Functions|proof]])
$$
\begin{gather}
\textbf{Proposition: } \\[5mm]
\text{1. } f:X \rightarrow Y \text{ is surjective if and only if } f(f^{-1}(B')) = B' \text{ for every set } B' \subset Y. \\[2mm]
\text{2. Bijective if and only if } f^{-1}(f(A)) = A \wedge f(f^{-1}(B')) = B' 
\end{gather}
$$
(see [[Proof of Proposition 4 of Useful Facts about Functions|proof]])
$$
\begin{gather}
\textbf{Proposition: } \\[5mm]
\text{The following statements about }  f:X \rightarrow Y \text{ are equivalent: }  \\[3.5mm]
\text{1. } f \text{ is injective} \\[2mm]
\text{2. } f^{-1}(f(A)) = A \text{ for every } A \subset X \\[3.5mm] 
\text{The three propositions below only hold if } f \text{ is injective: } \\[3.5mm]
\text{3. } f(A \cap B) = f(A) \cap f(B) \text{ for any two subsets } A \text{ and } B \text{ of } X.  \\[2mm]
\text{4. } f(A) \cap f(B) = \emptyset \iff A \cap B = \emptyset \\[2mm]
\text{5. }  f(A \ \backslash \ B) = f(A) \ \backslash  \ f(B) \text{ whenever } B \subset A \subset X
\end{gather}
$$
(see [[Proof of Proposition 5 of Useful Facts about Functions|proof]])


