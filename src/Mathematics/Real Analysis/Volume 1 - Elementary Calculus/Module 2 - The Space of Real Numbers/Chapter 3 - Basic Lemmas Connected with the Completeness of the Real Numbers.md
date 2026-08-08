---
dg-publish: true
---
# Basic Lemmas Connected with Completeness
In the study of real analysis, the [[Chapter 1 - Basic Properties of Real Numbers|Axiom of Completeness]] separates the set of real numbers $\mathbb{R}$ from the set of rational numbers $\mathbb{Q}$. It is the foundational principle that guarantees the real number line has no "gaps" or "holes." While Dedekind's Cut Principle and the Supremum and Infimum Principles establish this continuity algebraically and order-theoretically, this underlying reality can also be formulated in several geometrically and topologically intuitive ways.

These alternative formulations are cited as the *basic lemmas of completeness*. In classical analysis, these lemmas serve as the operational machinery for proving the most critical theorems of differential and integral calculus.

---
# The Nested Interval Lemma (Cauchy-Cantor Principle)
A foundational application of the natural numbers $\mathbb{N}$ and their inductive structure arises in the formalization of *sequences*:
$$
\begin{gather}
\textbf{Definition: Sequence} \\[5mm]
\text{A function } f : \mathbb{N} \rightarrow X \text{ of a natural-number argument is called a sequence,} \\[2mm]
\text{or more specifically, a sequence of elements of the set } X.
\end{gather}
$$
When the elements of the set $X$ are closed numerical intervals in $\mathbb{R}$, a sequence of intervals can be ordered by set inclusion so that each successive interval is contained within its predecessor:
$$
\begin{gather}
\textbf{Definition: Sequence of Nested Intervals} \\[5mm]
\text{A sequence of closed intervals } I_1, I_2, \dots, I_n, \dots \text{ is called nested if} \\[3.5mm]
I_1 \supset I_2 \supset \dots \supset I_n \supset I_{n+1} \supset \dots \\[3.5mm]
\text{Symbolically, if } I_n = [a_n, b_n], \text{ then for all } n \in \mathbb{N}\text{:} \\[3.5mm]
a_n \le a_{n+1} \le b_{n+1} \le b_n
\end{gather}
$$
With the definitions of sequences and nested intervals in place, the first fundamental lemma of completeness can be formulated. Geometrically, these intervals contract as the index $n$ increases. The completeness of the real numbers guarantees that a nested sequence of closed intervals must contract around at least one common real point:
$$
\begin{gather}
\textbf{Lemma: The Cauchy-Cantor Principle (Nested Interval Lemma)} \\[5mm]
\text{For any sequence of nested closed intervals } I_1 \supset I_2 \supset \dots \supset I_n \supset \dots, \\[2mm]
\text{there exists at least one point } c \in \mathbb{R} \text{ that belongs to all of them.} \\[3.5mm]
\bigcap_{n=1}^\infty I_n \neq \emptyset \\[3.5mm]
\text{If, moreover, for any } \varepsilon > 0 \text{ there exists an interval } I_n \text{ whose length} \\[2mm]
|I_n| = b_n - a_n \text{ is strictly less than } \varepsilon, \text{ then the common point } c \text{ is unique.}
\end{gather}
$$
(see [[Proof of the Cauchy-Cantor Principle|proof]])

> [!danger]+ Intuition: Closed vs. Open Intervals
> It is crucial that the intervals in the Cauchy-Cantor Principle are *closed*. If one considers a nested sequence of *open* intervals, such as $I_n = ]0, 1/n[$, the intersection $\bigcap_{n=1}^\infty ]0, 1/n[$ is empty. Indeed, $0 \notin ]0, 1/n[$ by definition, and for any $x > 0$, the [[Chapter 2 - The Most Important Classes of Real Numbers and Computational Aspects of Operations with Real Numbers|Principle of Archimedes]] guarantees a natural number $n \in \mathbb{N}$ such that $0 < 1/n < x$, excluding $x$ from $I_n$. The endpoints must be included to capture the limiting boundary.

---
# The Finite Covering Lemma (Borel-Lebesgue Principle)
The second major lemma transitions from examining chains of nested intervals to analyzing how a closed and bounded interval can be covered by families of open sets, introducing the topological concept of *compactness* in $\mathbb{R}$:
$$
\begin{gather}
\textbf{Definition: Cover and Subcover} \\[5mm]
\text{A system } S = \{X\} \text{ of sets } X \text{ is said to cover a set } Y \text{ if } Y \subset \bigcup_{X \in S} X, \\[2mm]
\text{that is, if every element } y \in Y \text{ belongs to at least one of the sets } X \text{ in the system } S. \\[3.5mm]
\text{A subset } S' \subset S \text{ of a cover } S \text{ of } Y \text{ is called a subcover of } Y \text{ if } S' \text{ itself covers } Y. \\[2mm]
\text{If every set } U \in S \text{ is an open interval, then } S \text{ is called an open cover of } Y.
\end{gather}
$$

$$
\begin{gather}
\textbf{Lemma: The Borel-Lebesgue Principle} \\[5mm]
\text{Every open cover of a closed and bounded interval } [a, b] \text{ contains a finite subcover.} \\[2mm]
\text{That is, if } [a, b] \subset \bigcup_{\alpha \in A} U_\alpha, \text{ where each } U_\alpha \text{ is an open interval, then there exists} \\[2mm]
\text{a finite subset of indices } \{\alpha_1, \alpha_2, \dots, \alpha_n\} \subset A \text{ such that} \\[3.5mm]
[a, b] \subset \bigcup_{i=1}^n U_{\alpha_i}
\end{gather}
$$
(see [[Proof of the Borel-Lebesgue Principle|proof]])

> [!info]+ Remark: Necessity of Boundedness and Closedness
> For the Borel-Lebesgue Principle to hold, the interval must be both *closed* and *bounded*. For example, the open interval $]0, 1[$ is covered by the infinite family of open intervals $]1/n, 1[$ for $n \in \mathbb{N} \setminus \{1\}$, yet no finite subfamily can cover the entirety of $]0, 1[$. Similarly, the unbounded closed ray $[1, \infty[$ is covered by the open intervals $]0, n[$ for $n \in \mathbb{N}$, but admits no finite subcover.

---
# The Limit Point Lemma (Bolzano-Weierstrass Principle)
The third major lemma characterizes how infinitely many points must accumulate when confined within a bounded spatial domain of $\mathbb{R}$. Formulating this principle requires the topological concept of a *neighborhood* and a *limit point*:
$$
\begin{gather}
\textbf{Definition: Neighborhood and Limit Point} \\[5mm]
\text{An open interval } ]a, b[ \text{ containing a point } p \in \mathbb{R} \text{ is called a neighborhood of } p. \\[2mm]
\text{For any } \varepsilon > 0, \text{ the open interval } U_\varepsilon(p) := ]p - \varepsilon, p + \varepsilon[ = \{x \in \mathbb{R} \mid |x - p| < \varepsilon\} \\[2mm]
\text{is the } \varepsilon\text{-neighborhood of } p, \text{ and } \mathring{U}_\varepsilon(p) := U_\varepsilon(p) \setminus \{p\} \text{ is the deleted } \varepsilon\text{-neighborhood of } p. \\[3.5mm]
\text{A point } p \in \mathbb{R} \text{ is a limit point (or accumulation point) of a set } X \subset \mathbb{R} \text{ if every} \\[2mm]
\text{neighborhood of } p \text{ contains infinitely many points of } X. \text{ Equivalently, } p \text{ is a limit point} \\[2mm]
\text{of } X \text{ if every deleted } \varepsilon\text{-neighborhood } \mathring{U}_\varepsilon(p) \text{ contains at least one point of } X.
\end{gather}
$$

$$
\begin{gather}
\textbf{Lemma: The Bolzano-Weierstrass Principle} \\[5mm]
\text{Every bounded infinite subset } X \text{ of the real numbers } \mathbb{R} \\[2mm]
\text{possesses at least one limit point in } \mathbb{R}.
\end{gather}
$$
(see [[Proof of the Bolzano-Weierstrass Principle|proof]])

> [!info]+ Remark: Equivalence of the Completeness Lemmas
> The Cauchy-Cantor Principle, the Borel-Lebesgue Principle, and the Bolzano-Weierstrass Principle are inextricably linked. Within the framework of Archimedean ordered fields, each of these three lemmas is logically equivalent to the Axiom of Completeness. If any one of these principles (with the Archimedean property adjoined in the case of Cauchy-Cantor) is adopted as an axiom, the remaining lemmas—along with Dedekind's Cut Principle and the Supremum Principle—can be derived as theorems.

---
# Additional Useful Facts
$$
\begin{gather}
\textbf{Lemma: Intersection of a System of Nested Closed Intervals} \\[5mm]
\text{If } I \text{ is any nonempty system of nested closed intervals in } \mathbb{R}, \text{ then} \\[3.5mm]
\sup\{ a \in \mathbb{R} \mid [a, b] \in I \} =: \alpha \le \beta := \inf\{ b \in \mathbb{R} \mid [a, b] \in I \} \\[3.5mm]
\text{and the intersection of the system is the closed interval } [\alpha, \beta]\text{:} \\[3.5mm]
[\alpha, \beta] = \bigcap_{[a, b] \in I} [a, b]
\end{gather}
$$
(see [[Proof of the Intersection of Nested Closed Intervals]])

$$
\begin{align}
& \textbf{Theorem: Alternative Axiomatic Foundations of Completeness} \\[5mm]
& \hspace{0.5 in} \text{An axiom system for } \mathbb{R} \text{ equivalent to the one established in the first chapter} \\[2mm]
& \hspace{0.5 in} \text{is obtained if the Axiom of Completeness is replaced by any one of the following:} \\[3.5mm]
& \hspace{0.5 in} 1. \ \text{The Least Upper Bound (Supremum) or Greatest Lower Bound (Infimum) Principle.} \\[2mm]
& \hspace{0.5 in} 2. \ \text{The Cauchy-Cantor Principle (together with the Principle of Archimedes).} \\[2mm]
& \hspace{0.5 in} 3. \ \text{The Borel-Lebesgue (Heine-Borel) Principle.} \\[2mm]
& \hspace{0.5 in} 4. \ \text{The Bolzano-Weierstrass Principle.}
\end{align}
$$
(see [[Proof that Different Axioms Can be Used]])

>[!info]+ Remark: Different Paradigms
>It was mentioned in the [[Chapter 1 - Basic Rules of Logic|prelude of the very first chapter of Real Analysis]] that it is possible to construct a coherent and harmonious mathematical universe with different frameworks that lead to mostly the same conclusion. While the different approaches offered by various mathematicians throughout history would be too much to list in this single page, a good example of something being considered a theorem versus it being a self-evident axiom is the [[Proof that Induction Works|principle of induction]]. 
>
>- In standard first-order Peano Arithmetic, induction is an axiom that is provided for the [[Chapter 2 - The Most Important Classes of Real Numbers and Computational Aspects of Operations with Real Numbers|natural numbers]]. This is evident in a branch such as *Number Theory*, where it provides a simple justification for why numerical sequences seemingly go on forever. 
>- In the case of these notes, which uses a simpler and watered-down version of Zermelo-Frankel set theory, the principle of induction must be proven to work by:
>	- The axiom claiming that inductive sets exist.
>	- The axiom of infinity. 
>	- The well-ordering principle
>
>On the surface, the reader may feel that such a detail is useless. After all, researchers within the mathematical sciences remain collaborative in their efforts—with new knowledge being built on already-existing information. This is a valid remark to make, but the reader must also recognize that differing assumptions can lead to different ways of getting the same answer that makes using multiple differing paradigms difficult. 
>
>It it this problem that these notes are attempting to alleviate by having it operate within the same framework. While the notes do not claim to present any novel discoveries, the author and his AI agents still need to synthesize the existing knowledge to fit the framework because failure to do so will easily lead to contradictions and inconsistent notation. Anyone who has gone through a standard university course—whether undergraduate or postgraduate—or anyone who has attempted to teach themselves a mathematical science with disparate textbooks written by different authors will understand the trouble that comes with conflicting frameworks and assumptions. 




