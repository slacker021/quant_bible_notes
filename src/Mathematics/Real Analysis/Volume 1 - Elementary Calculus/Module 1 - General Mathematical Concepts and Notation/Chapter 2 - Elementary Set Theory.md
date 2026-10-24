---
dg-publish: true
---
# The Concept of a Set
*Set Theory* is considered to be one of the most foundational topics in mathematics such that nearly everything in mathematics can be described using this. To start off this foundational topic requires a simple and intuitive definition of what a *set* is:
$$
\begin{gather}
\textbf{Definition: The Concept of a Set} \\[5mm]
\text{A set is an unordered collection of definite and perfectly distinguishable objects. } \\[2mm]
\text{A set is unambiguously determined by the collection of objects that comprise it,} \\[2mm]
\text{where any property defines the set of objects having that property.}
\end{gather}
$$
If $x$ is an object, $P$ is a *property*, and $P(x)$ denotes the assertion that $x$ has property $P$, then the class of objects having the property $P$ is denoted $\{x \ | \ P(x) \}$ . The objects that belong to a set are called *elements* $x_{1} \dots x_{n}$ and is denoted as $\{x_{1}\dots x_{n}\}$. Synonyms for a set include but are not limited to
- *family*
- *totality*
- *collection*
- *class*
### The Inclusion Relation
When it comes to defining sets, the notation below serves as the primary notation used: 
- The statement $x \in X$ is used to denote that $x$ is an element of the set $X$ while $x \notin X$ denotes that it is not an element of the set $X$. 
- When statements about sets are written, the two most frequent logical operators used are $\exists$, which means "there exists" or "there is", and $\forall$, which means "every, for all, or each."
- If two sets $A$ and $B$ have exactly the same elements, then they are equivalent, which is denoted as $A = B$.  In symbolic form, this translates to $\forall x((x \in A) \iff (x \in B))$. If two sets have exactly the same elements, then the sets $A$ and $B$ are considered to be the same sets. 
- If every element of $A$ is an element of $B$, then $A$ is a subset of $B$, which is denoted as $A \subset B$. If $A \subset B$ but $A \neq B$, then the inclusion of $A \subset B$ is *strict* or that $A$ is a *proper subset* of B, which can be abbreviated as $A \subsetneq B$. Therefore, it can be concluded that $(A = B) \iff (A \subset B) \wedge (B \subset A)$. Additionally, $B$ is said to be the *superset* of $A$. 
- If $M$ is a set, any property $P$ distinguishes $P$ in $M$ the subset $\{x \in M |P(x) \}$. 
- If $P$ is taken as a property that no elements of the set $M$ have, for example, $P(x):=(x \neq x)$, then the set $\emptyset = \{x \in M | x \neq x \}$ is used to denote a set with no elements. This serves as the *empty subset* of $M$. 
---
# Basic Set Operations
There are three basic operations that can be performed on sets are the *union, intersection, and difference.* These three operations can be used on two or more sets to form an entirely new set. If $A$ and $B$ are subsets of a set $M$, then
$$
\begin{gather}
\textbf{Definition: Set Union} \\[5mm]
\text{The union of } A \text{ and } B \text{ is the set that consists of the elements of } M  \\[2mm]
\text{that belong to at least one of the sets } A \text{ and } B. \text{ This is denoted as } \\[2mm]
A \cup B := \{x \in M | (x \in A ) \lor ( x \in B) \} 
\\[5mm]

\textbf{Definition: Set Intersection} \\[5mm]
\text{The intersection of } A \text{ and } B \text{ is the set that consists of elements of M that both } \\[2mm]
A \text{ and } B \text{ have in common. This is denoted as } \\[3.5mm]
A \cap B = \{ x \in M | (x \in A) \wedge (x \in B) \} 
\\[5mm]

\textbf{Definition: Set Difference} \\[5mm]
\text{The difference between } A \text{ and } B \text{ is the set consisting of elements that}  \\[2mm]
\text{ consisting of the elements of } A \text{ that do not belong to B. This is denoted as } \\[3.5mm]
A \backslash B = \{x \in M | (x \in A) \wedge (x \notin B) \}
\end{gather}
$$

There is also a special case of the set difference that is *referred to as the complement*: 
$$
\begin{gather}
\textbf{Definition: Set Complement} \\[5mm]
\text{The difference between the set } M \text{ and one of its subsets } A  \\[2mm]
\text{is the complement of } A \text{ in } M, \text{ which is denoted as } C_{M}(A). \\[2mm]
\text{Using definition 4, this is denoted as } \\[3.5mm]
M \backslash A = \{x \in M | x \in M \wedge x \notin A \}
\end{gather}
$$
The complement of the set $A$ can also be denoted as $A'$ 

---
# Fundamental Axioms of Set Theory
The formation of real analysis requires a starting point, with the axioms of set theory providing the basis for the rest of the real space. While it is possible to cruise through real analysis without a rigorous foundation of set theory, fundamental axioms help in eliminating the ambiguity that comes with defining such a foundational part of mathematics. The purpose of these axioms is to provide the formal properties of sets and illustrate the simplest consequences of those axioms. 
$$
\begin{gather}
\textbf{Axiom: The Principle of Extensionality} \\[5mm]
\text{Sets } A \text{ and } B \text{ are equal if and only if they have } \\[2mm]
\text{ the same elements. For } A = B \text{ to be established, it } \\[2mm]
\text{ must be verified that } \forall x ((x \in A) \iff (x \in B)).
\\[5mm]

\textbf{Axiom: The Principle of Separation: } \\[5mm]
\text{To any set } A \text{ and any property } P \text{ there corresponds a set } B \text{ whose } \\[2mm]
\text{elements are those elements of } A \text{, and only those, having property } P. \text{ Therefore, if } \\[2mm]
A \text{ is a set, then } B = \{x \in A| P(x) \} \text{ is also a set.}
\end{gather}
$$
**Axiom 2** is used very frequently in mathematical constructions when selecting from a set the subset consisting of the elements having some property. One property of sets that is immediately obvious from **axiom 2** is the empty set being a subset of every set: 
$$
\begin{gather}
\textbf{Proposition: Empty Set as a Subset of a Set} \\[5mm]
\text{If } X \text{ is any set and } \emptyset \text{ is an empty set, then } \emptyset \text{ is a subset of } X. 
\end{gather}
$$
(See [[Proof that the Empty Set is the Subset of Any Set|proof]]) In addition to **proposition 1**, **axioms 1 and 2** that the object that results from set operations is also a set. 
$$
\begin{gather}
\textbf{Axiom: Union of a Set} \\[5mm]
\text{For any set } M \text{ whose elements are sets, there is a set }  \\[2mm]
\bigcup M \text{, which is the union of } M, \text{ consisting of those elements and only } \\[2mm]
\text{those that belong to some element of } M. \text{Thus, a union of sets is a set and } \\[2mm]
x \in \bigcup M \iff \exists X ((X \in M) \wedge (x \in X) )
\end{gather}
$$
A much easier way to frame the **third axiom** is to describe it as the "family of sets" instead of a "set whose elements are sets." The axiom of separation and union axiom can also be used to formally define the intersection of the set $M$ (or family of sets) as the set
$$
\bigcap M := \left\{ x \in \bigcup M | \forall X ((X \in M) \implies (x \in X))  \right\} \tag{1}
$$
$$
\begin{gather}
\textbf{Axiom: Principle of Pairing} \\[5mm]
\text{For any sets } X \text{ and } Y \text{, there is a set whose elements are only } X \text{ and } Y.  \\[2mm]
\text{This set is denoted as } Z = \{ X, Y\}, \text{ and has two elements if } X \neq Y.  \\[2mm]
\text{If } X \text{ and } Y \text{ are equivalent, then } Z \text{ only has one element. } \\[5mm]
 
\textbf{Axiom: Principle of the Power Set } \\[5mm]
\text{For any set } X, \text{ there is a set } \mathcal{P}(X) \text{ that has each subset of X as an element. } \\[2mm]
\text{However, this set does not have any other elements. }
\end{gather}
$$
The next axiom requires the introduction of a *successor of a set:*
$$
\begin{gather}
\textbf{Definition: Successor Set} \\[5mm]
\text{The successor of a set } X \text{ is } X^+ := X \cup \{ X \}, \text{ where the } \\[2mm]
\text{one-element set } \{ X \} \text{ is adjoined to } X. 
\end{gather}
$$
Furthermore, 
$$
\begin{gather}
\textbf{Definition: Inductive Set} \\[5mm]
\text{A set is inductive if the empty set is one of its elements and the successor } \\[2mm]
\text{of each of its elements also belong to it.}
\end{gather}
$$
The definition of the successor set and inductive set are used to form the **seventh axiom:**
$$
\begin{gather}
\textbf{Axiom: Principle of Infinity} \\[5mm]
\text{Inductive sets exists.}
\end{gather}
$$ 
$$
\begin{gather}
\textbf{Axiom: Principle of Replacement}  \\[5mm]
\text{Let } \mathcal{F}(x,y) \text{ be a formula such that for every } x_{0} \text{ in the set } X \text{ there is a unique object } y_{0}  \\[2mm]
\text{such that } \mathcal{F}(x_{0}, y_{0}) \text{ is true. Then the objects } y \text{ for which there is an element } x \in X  \\[2mm]
\text{ such that } \mathcal{F}(x, y) \text{ is true form a set. }  
\end{gather}
$$
> [!info]+ Remark: 
> This axiom of replacement is not used in the construction of real analysis, but may see uses elsewhere. 

**Axioms 1 to 7** constitute the *Zermelo-Frankael* axioms that underpin formal set theory. In addition to the seven foundational axioms of set theory, an additional axiom (which happens to be independent from the previous seven) is added. The following axiom, as opposed to **axiom 7**, is used frequently in real analysis:
$$
\begin{gather}
\textbf{Axiom: Principle of Choice} \\[5mm]
\text{For any family of nonempty and mutually nonintersecting sets, there exists } \\[2mm]
\text{ a set } C \text{ such that for every set } X \text{ in the family } X \cap C \text{ consists of exactly one element.}
\end{gather}
$$
In other words, from each set of the family, exactly one representative can be chosen in such a way that the representatives chosen form a set $C$. 

---
# Useful Facts of Set Theory
With the numerous axioms, definitions, and symbols that have been defined, several useful facts can be derived from these atomic concepts. These facts prove useful in more complex topics. The first useful fact involves *de Morgan's Law of Set Complements:*
$$
\begin{gather}
\textbf{Proposition: de Morgan's Law of Set Complements} \\[5mm]
\text{For any subsets } A, B \subset M:  \\[3.5mm]
C_{M}(A \cup B) = C_{M}(A) \cap C_{M}(B) \\[2mm]
C_{M}(A \cap B) = C_{M}(A) \cup C_{M}(B)
\end{gather}
$$
(see [[Proof of de Morgan's Laws of Set Complements|proof]])
Another useful law refers to the *distributive nature of set operations:*
$$
\begin{gather}
\textbf{Proposition: Distributive Laws of Intersection and Union: } \\[5mm]
\text{For any subsets } A,B,C \subset M:  \\[3.5mm]
A \cap (B \cup C) = (A \cap B) \cup (A \cap C) \\[2mm]
A \cup (B \cap C) = (A \cup B) \cap (A \cup C)
\end{gather}
$$
(see [[Proof of the Distributive Laws of Intersection and Union|proof]])
Last but not the least, the complement in particular has a unique set of rules:
$$
\begin{gather}
\textbf{Lemma: Elementary Lemma of Set Complementation}  \\[5mm]
\text{For any subsets } A,B,C \subset M:  \\[3.5mm]
(A \subset C) \wedge (B \subset C) \iff (A \cup B) \subset C \\[2mm]
(A \subset B) \iff (C_{M}B \subset C_{M}A) \\[2mm]
C_{M}(C_{M}A) = A
\end{gather}
$$
(see [[Proof of Elementary Lemma of Set Complementation|proof]])
