---
dg-publish: true
---
# Countable Sets
The formalization of equipotence enables the rigorous comparison of the cardinalities, or "sizes," of infinite sets. Using the set of natural numbers $\mathbb{N} := \{1, 2, 3, \dots\}$ as the foundational benchmark, it is possible to categorize infinite subsets of the real numbers $\mathbb{R}$ into distinct cardinal regimes. The most elementary class of infinite sets consists of those whose elements can be enumerated sequentially:
$$
\begin{gather}
\textbf{Definition: Countable Set} \\[5mm]
\text{A set } X \text{ is called countable (or countably infinite) if it is equipotent to the set of natural numbers } \mathbb{N}. \\[2mm]
\text{Equivalently, there exists a bijective mapping } f: \mathbb{N} \to X, \text{ allowing the} \\[2mm]
\text{elements of } X \text{ to be indexed as an infinite sequence } x_1, x_2, \dots, x_n, \dots. \\[3.5mm]
\text{A set that is either finite or countably infinite is called at most countable.}
\end{gather}
$$
Operating on countable and at most countable sets yields several foundational closure properties under standard set-theoretic operations:
$$
\begin{gather}
\textbf{Proposition: Subsets of Countable Sets} \\[5mm]
\text{Every subset of a countable set is at most countable} \\[2mm]
\text{(that is, any subset of a countable set is either finite or countably infinite).}
\end{gather}
$$
(see [[Proof of the Subsets of Countable Sets]])

$$
\begin{gather}
\textbf{Proposition: Union of Countable Sets} \\[5mm]
\text{The union of a nonempty finite or countable family of at most countable sets is at most countable.} \\[2mm]
\text{In particular, the union of a nonempty finite or countable family of countable sets is a countable set.}
\end{gather}
$$
(see [[Proof of the Union of Countable Sets]])

Applying the Proposition on the Union of Countable Sets, it can be demonstrated that the set of rational numbers is countable. Although the rational numbers are topologically dense across the entire real number line, their cardinal quantity remains strictly bound to the countable infinity of the natural numbers:
$$
\begin{gather}
\textbf{Theorem: Countability of the Rational Numbers} \\[5mm]
\text{The set of all rational numbers } \mathbb{Q} \text{ is countable.}
\end{gather}
$$
(see [[Proof of the Countability of the Rational Numbers]])

---
# Uncountable Sets and the Cardinality of the Continuum
Given that both the set of integers $\mathbb{Z}$ and the dense set of rational numbers $\mathbb{Q}$ are countable, it is natural to ask whether every infinite set is countable. Georg Cantor resolved this inquiry in 1874 by proving that the continuum of real numbers cannot be enumerated, later formalizing the famous diagonal argument in 1891. There exist infinite sets whose cardinality is strictly greater than the countable infinity of the natural numbers:
$$
\begin{gather}
\textbf{Theorem: Uncountability of the Real Numbers (Cantor's Diagonal Argument)} \\[5mm]
\text{The set of real numbers } \mathbb{R} \text{ is uncountable.} \\[2mm]
\text{Specifically, neither the open interval } (0, 1) \text{ nor the closed interval } [0, 1] \text{ can be placed} \\[2mm]
\text{in a bijective correspondence with the set of natural numbers } \mathbb{N}.
\end{gather}
$$
(see [[Proof of the Uncountability of the Real Numbers]])

Cantor's theorem forces the recognition of a hierarchy of distinct infinities. To classify sets that share this higher order of infinity with the real number line—including every non-degenerate open interval $(a, b)$ and closed interval $[a, b]$—a specific cardinal designation is introduced:
$$
\begin{gather}
\textbf{Definition: Cardinality of the Continuum} \\[5mm]
\text{Any set that is equipotent to the set of real numbers } \mathbb{R} \text{ (or equivalently, to } (0, 1) \text{ or } [0, 1]\text{)} \\[2mm]
\text{is said to have the cardinality of the continuum, denoted by the symbol } \mathfrak{c}.
\end{gather}
$$
Because the set of all real numbers $\mathbb{R}$ has the cardinality of the continuum $\mathfrak{c}$, whereas the subset of rational numbers $\mathbb{Q} \subset \mathbb{R}$ is merely countable, it follows that the vast majority of points on the real number line are irrational:
$$
\begin{gather}
\textbf{Corollary: Uncountability of the Irrational Numbers} \\[5mm]
\text{The set of irrational numbers } \mathbb{R} \setminus \mathbb{Q} \text{ has the cardinality of the continuum } \mathfrak{c} \\[2mm]
\text{and is therefore uncountable.}
\end{gather}
$$
(see [[Proof of the Uncountability of the Irrational Numbers]])

> [!danger]+ Intuition: Topological Density Versus Cardinality
> The *topological* density of a set does not dictate its *cardinal* size. By the corollaries to the Principle of Archimedes, between any two distinct real numbers $a < b$, no matter how close, there lies at least one rational number. Yet, despite this ubiquitous density, the infinity of irrational numbers is strictly larger than the infinity of rational numbers. If a point is selected uniformly at random from the continuous interval $[0, 1]$, the probability of selecting a rational number is precisely zero. Measure-theoretically and cardinally, the real line is populated almost entirely by irrational numbers.

An even more striking classification arises when distinguishing real numbers by their algebraic structure. A real number is called *algebraic* if it is a root of a non-constant polynomial with integer coefficients (such as $\frac{3}{4}$ or $\sqrt{2}$), and *transcendental* otherwise (such as $e$ or $\pi$). Because the set of all polynomials with integer coefficients is countable, and each non-zero polynomial possesses only finitely many roots, the algebraic numbers form a countable union of finite sets:
$$
\begin{gather}
\textbf{Proposition: Countability of Algebraic Numbers} \\[5mm]
\text{The set of all real algebraic numbers } \mathbb{A} \subset \mathbb{R} \text{ (real roots of non-constant} \\[2mm]
\text{polynomial equations with integer coefficients) is countable.}
\end{gather}
$$
(see [[Proof of the Countability of the Algebraic Numbers]])

Although proving that a specific constant is transcendental requires delicate analytical machinery, Cantor's cardinal arithmetic proves the existence—and preponderance—of transcendental numbers purely from set-theoretic principles:
$$
\begin{gather}
\textbf{Corollary: Cardinality of Transcendental Numbers} \\[5mm]
\text{The set of real transcendental numbers } \mathbb{T} := \mathbb{R} \setminus \mathbb{A} \text{ is non-empty,} \\[2mm]
\text{possesses the cardinality of the continuum } \mathfrak{c}, \text{ and is therefore uncountable.}
\end{gather}
$$
(see [[Proof of the Existence of Transcendental Numbers]])

> [!question]+ Application: Discrete Asset Lattices Versus Continuous Sample Spaces
> The cardinal distinction between countable and continuum infinities marks the boundary between discrete-time and continuous-time financial models:
> 1. **Discrete State Spaces:** In discrete models (such as the Cox-Ross-Rubinstein binomial tree), the collection of possible asset price paths over any finite or countably infinite sequence of trading periods is at most countable. Probabilities can be assigned directly to individual trajectories $\omega \in \Omega$ via elementary discrete distributions where $\sum_{\omega} \mathbb{P}(\{\omega\}) = 1$.
> 2. **The Continuum of Continuous-Time Paths:** In continuous-time frameworks (such as geometric Brownian motion in the Black-Scholes-Merton model), the sample space $\Omega = C([0, T], \mathbb{R})$ of continuous price paths has cardinality exceeding $\mathfrak{c}$. On such uncountable spaces, the probability of realizing any single predetermined path is identically zero: $\mathbb{P}(\{\omega\}) = 0$. Consequently, probability cannot be computed by summing point probabilities. Financial engineering must instead rely on measure theory, constructing consistent probability measures on $\sigma$-algebras of cylinder sets via Kolmogorov's Extension Theorem.

>[!example]- Example: Hilbert's Hotel and the Mechanics of Countable Equipotence
>To illustrate the counterintuitive nature of infinite cardinalities, the German mathematician David Hilbert proposed a thought experiment concerning a hypothetical establishment known as **Hilbert's Hotel**. Unlike a conventional hotel with a finite capacity $N \in \mathbb{N}$, Hilbert's Hotel contains a countably infinite collection of rooms indexed sequentially by the natural numbers:
>$$
>\mathbb{N} := \{1, 2, 3, \dots\} \tag{1}
>$$
>Suppose that every room in the hotel is currently occupied, such that the set of seated guests is in bijective correspondence with $\mathbb{N}$. In a finite setting, the *Dirichlet Pigeonhole Principle* dictates that an occupied capacity admits no additional guests without causing collisions. In the transfinite regime, however, the hotel can accommodate new arrivals through systematic re-indexing: 
>
>##### Case I: Accommodating a Finite Number of New Guests
>Suppose a single new traveler arrives seeking lodging. Although the hotel contains no vacant rooms, the manager executes a coordinate translation by instructing each resident in room $n$ to relocate to room $n + 1$:
>$$
>f: \mathbb{N} \to \mathbb{N} \setminus \{1\}, \qquad f(n) := n + 1 \tag{2}
>$$
>Because $f$ is a bijection between $\mathbb{N}$ and the proper subset $\{2, 3, 4, \dots\}$, all existing occupants remain housed while room $1$ is vacated to accommodate the newcomer. More generally, if a finite party of $k \in \mathbb{N}$ travelers arrives, the manager executes the shift $f_k(n) := n + k$, vacating the finite subset $\{1, 2, \dots, k\}$. This demonstrates the transfinite cardinal identity:
>$$
>k + \aleph_0 = \aleph_0, \qquad \forall k \in \mathbb{N} \tag{3}
>$$
>
>##### Case II: Accommodating Countably Many New Guests
>Now suppose that a countably infinite queue of new guests arrives, denoted by the indexed set $G := \{g_1, g_2, g_3, \dots\}$. The manager can accommodate the entire infinite collection simultaneously by instructing the occupant of room $n$ to relocate to room $2n$:
>$$
>f: \mathbb{N} \to 2\mathbb{N}, \qquad f(n) := 2n \tag{4}
>$$
>The mapping $f$ is a bijection from the set of natural numbers onto the set of even natural numbers $2\mathbb{N} := \{2, 4, 6, \dots\}$. This operation leaves the infinite complement of odd-numbered rooms vacant:
>$$
>\mathbb{N} \setminus 2\mathbb{N} = 2\mathbb{N} - 1 = \{1, 3, 5, \dots\} \tag{5}
>$$
>Assigning each newcomer $g_k \in G$ to room $2k - 1$ establishes a second bijection $g: \mathbb{N} \to 2\mathbb{N} - 1$. Both the original occupants and the infinite newcomers are accommodated with zero room-sharing, confirming the cardinal arithmetic property:
>$$
>\aleph_0 + \aleph_0 = \aleph_0 \tag{6}
>$$
>
>##### Case III: Accommodating a Countable Family of Countable Groups
>Suppose that a countably infinite convoy of buses arrives, indexed by $b \in \mathbb{N}$, where each bus contains a countably infinite sequence of passengers indexed by $s \in \mathbb{N}$. The set of all incoming arrivals is represented by the Cartesian product $\mathbb{N} \times \mathbb{N}$.
>
>To reallocate rooms, the manager first clears the necessary space by shifting the current occupants from room $n$ to room $2n$, reserving all odd-numbered rooms. The set of vacant rooms is equipotent to $\mathbb{N}$. The problem then reduces to establishing an injection from the Cartesian product $\mathbb{N} \times \mathbb{N}$ into the available rooms. This can be achieved through two canonical methods:
>
>1. **Cantor's Polynomial Pairing Function:**  
>   The mapping $\pi: \mathbb{N} \times \mathbb{N} \to \mathbb{N}$ defined by
>   $$
>   \pi(b, s) := \frac{(b + s - 1)(b + s - 2)}{2} + b \tag{7}
>   $$
>   is a proven bijection. Interleaving this pairing with the available odd rooms assigns passenger $(b, s)$ to room $2\pi(b, s) - 1$.
>
>2. **Prime Factorization Encoding:**  
>   Alternatively, assigning passenger $(b, s)$ to room $p_b^s$, where $p_b$ is the $b$-th odd prime number ($3, 5, 7, 11, \dots$), utilizes the Fundamental Theorem of Arithmetic. By uniqueness of prime factorizations, no two passengers are assigned the same room, leaving even-numbered rooms and non-prime-power rooms entirely available.
>
>Both constructions verify that a countable union of countable sets remains countable:
>$$
>\aleph_0 \cdot \aleph_0 = |\mathbb{N} \times \mathbb{N}| = \aleph_0 \tag{8}
>$$
>
>##### The Boundary of Infinite Capacity: The Uncountable Continuum
>The capacity of Hilbert’s Hotel is fundamentally constrained by its countable index set $\mathbb{N}$. If an **uncountably infinite** collection of guests arrives—such as a bus transporting all real numbers $x \in (0, 1)$, or an infinite sequence of coin tosses $\omega \in \{H, T\}^\infty$—the hotel cannot accommodate them. 
>
>By Cantor’s Diagonal Argument, the cardinality of the continuum is strictly greater than aleph-null:
>$$
>\mathfrak{c} = 2^{\aleph_0} > \aleph_0 \tag{9}
>$$
>No injective mapping from $(0, 1)$ or $\mathcal{P}(\mathbb{N})$ into $\mathbb{N}$ can exist. Regardless of the rearrangement scheme implemented by the manager, an uncountably infinite collection of travelers will permanently remain without a room.
>
>##### Set-Theoretic and Quantitative Implications
>Hilbert's thought experiment exemplifies a **veridical paradox**—a proposition that appears counterintuitive under everyday finite intuition yet withstands rigorous formal proof. Within foundational analysis, this behavior serves as the defining characteristic of infinite systems:
>
>* **Dedekind Infinity:** A set $X$ is infinite in the sense of Dedekind if and only if it is equipotent to a proper subset of itself:
>  $$
>  \exists A \subsetneq X \quad \text{such that} \quad |A| = |X| \tag{10}
>  $$

