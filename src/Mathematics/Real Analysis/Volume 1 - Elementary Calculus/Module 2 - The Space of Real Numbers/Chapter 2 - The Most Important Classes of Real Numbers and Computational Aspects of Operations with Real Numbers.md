---
dg-publish: true
---
# The Most Important Classes of Real Numbers and Computational Aspects of Operations with Real Numbers
Having established the axiomatic foundation of the real numbers as a complete ordered field, the investigation turns toward isolating the fundamental number classes residing within $\mathbb{R}$. While the continuum of real numbers is uncountably infinite, a select hierarchy of subsets—the *natural numbers* $\mathbb{N}$, the *integers* $\mathbb{Z}$, and the *rational* numbers $\mathbb{Q}$—forms the structural scaffolding for discrete arithmetic, numerical computation, and continuous modeling. 

Constructing these classes directly from the field and completeness axioms reveals how discrete counting structures and continuous geometries emerge from a single unified system.

---
# The Natural Numbers and the Principle of Induction
Within axiomatic set theory and analysis, the concept of an *inductive set* captures the mechanics of sequential progression and discrete accumulation. In the context of the real field $\mathbb{R}$, an inductive set is a collection containing unity that is closed under the operation of adding the identity element $1$:
$$
\begin{gather}
\textbf{Definition: Inductive Set} \\[5mm]
\text{A subset } X \subseteq \mathbb{R} \text{ is called an inductive set if it satisfies the following two conditions:} \\[3.5mm]
\text{1. Base Inclusion: } 1 \in X \\[2mm]
\text{2. Inductive Closure: } \forall x \in X, \quad (x + 1) \in X
\end{gather}
$$

>[!example]- Example: Inductive Subsets of the Real Numbers
>The entire set of real numbers $\mathbb{R}$, the set of non-negative real numbers $\mathbb{R}_{\ge 0}$, and the set of real numbers bounded below by unity $[1, \infty)$ all satisfy the definition of an inductive set. 
>
>Furthermore, the intersection of any arbitrary non-empty family of inductive sets $\{X_\alpha\}_{\alpha \in A}$ remains an inductive set. If an element $x$ belongs to the intersection $X = \bigcap_{\alpha \in A} X_\alpha$, it belongs to every constituent set $X_\alpha$. Because each $X_\alpha$ is inductive, $1 \in X_\alpha$ for all $\alpha \in A$, ensuring $1 \in X$. Concurrently, $(x + 1) \in X_\alpha$ for every $\alpha \in A$, which guarantees that $(x + 1) \in X$:
>$$
>\left( x \in \bigcap_{\alpha \in A} X_\alpha \right) \implies \left( \forall \alpha \in A, \, x \in X_\alpha \right) \implies \left( \forall \alpha \in A, \, (x + 1) \in X_\alpha \right) \implies \left( (x + 1) \in \bigcap_{\alpha \in A} X_\alpha \right) \tag{1}
>$$

To isolate the discrete counting numbers from the continuous expanse of $\mathbb{R}$, analysis extracts the minimal inductive core of the real line:
$$
\begin{gather}
\textbf{Definition: The Set of Natural Numbers} \\[5mm]
\text{The set of natural numbers, denoted by } \mathbb{N}, \text{ is the minimal inductive subset of } \mathbb{R}. \\[2mm]
\text{Formally, } \mathbb{N} \text{ is defined as the intersection of all inductive subsets of } \mathbb{R}: \\[3.5mm]
\mathbb{N} := \bigcap \{ X \subseteq \mathbb{R} \mid X \text{ is an inductive set} \}
\end{gather}
$$

>[!info]+ Remark: The Role of Zero in $\mathbb{N}$
>In foundational mathematical logic, theoretical computer science, and von Neumann ordinal arithmetic, $0 = \emptyset$ is included as the minimal element of the natural numbers. In classical mathematical analysis, however, the convention initiated by *Peano* and *Dedekind* designates $1$ as the first natural number. The union $\mathbb{N}_0 := \mathbb{N} \cup \{0\}$ is termed the set of non-negative integers or whole numbers.

Because $\mathbb{N}$ is constructed as the intersection of all inductive sets, no proper subset of $\mathbb{N}$ can be inductive. This minimality principle yields the primary engine of discrete proof in mathematics:
$$
\begin{gather}
\textbf{Theorem: The Principle of Induction} \\[5mm]
\text{Let } E \subseteq \mathbb{N} \text{ be a subset of the natural numbers satisfying:} \\[3.5mm]
\text{1. Base Step: } 1 \in E \\[2mm]
\text{2. Induction Step: } \forall n \in \mathbb{N}, \quad (n \in E) \implies (n + 1 \in E) \\[3.5mm]
\text{Then the subset } E \text{ encompasses the entirety of the natural numbers: } E = \mathbb{N}.
\end{gather}
$$
(see [[Proof that Induction Works]])

>[!danger]+ Intuition: The Domino Effect and Infinite Verification
>Induction provides a rigorous mechanism for verifying infinitely many propositions in a finite number of logical steps. It is analogous to an infinite row of standing dominoes labeled $1, 2, 3, \dots$:
>1. The base step establishes that the first domino falls ($1 \in E$).
>2. The induction step establishes that the spatial separation between adjacent dominoes is uniform, guaranteeing that if the $k$-th domino falls, it must strike and topple the $(k+1)$-th domino ($k \in E \implies k + 1 \in E$).
>
>Because the initial impulse is verified and the transmission mechanism is unbroken across all indices, the entire infinite chain collapses. Induction translates recursive generation into deductive certainty.

Applying the Principle of Mathematical Induction establishes the fundamental algebraic and order-theoretic properties of $\mathbb{N}$:
$$
\begin{align}
& \textbf{Proposition: Properties of Natural Numbers} \\[5mm]
& \hspace{0.2 in} \text{The set of natural numbers } \mathbb{N} \text{ satisfies the following structural properties:} \\[3.5mm]
& \hspace{0.2 in} \text{1. Algebraic Closure: } \forall m, n \in \mathbb{N}, \quad (m + n) \in \mathbb{N} \quad \wedge \quad (m \cdot n) \in \mathbb{N} \\[2mm]
& \hspace{0.2 in} \text{2. Predecessor Existence: } \forall n \in \mathbb{N} \setminus \{1\}, \quad (n - 1) \in \mathbb{N} \\[2mm]
& \hspace{0.2 in} \text{3. Discrete Successor Bound: } \forall n \in \mathbb{N}, \quad \min \{ x \in \mathbb{N} \mid n < x \} = n + 1 \\[2mm]
& \hspace{0.2 in} \text{4. Gap Property: } \forall m, n \in \mathbb{N}, \quad (n < m) \implies (n + 1 \le m) \\[2mm]
& \hspace{0.2 in} \text{5. Immediate Successor: } \text{There exists no natural number } k \in \mathbb{N} \text{ such that } n < k < n + 1 \\[2mm]
& \hspace{0.2 in} \text{6. Immediate Predecessor: } \forall n \in \mathbb{N} \setminus \{1\}, \text{ there exists no } k \in \mathbb{N} \text{ such that } n - 1 < k < n \\[2mm]
& \hspace{0.2 in} \text{7. Well-Ordering Principle: } \text{Every non-empty subset } S \subseteq \mathbb{N} \text{ contains a unique minimal element:} \\[2mm]
& \hspace{0.6 in} \forall S \subseteq \mathbb{N} \ (S \ne \emptyset \implies \exists! m \in S \ \forall s \in S \, (m \le s))
\end{align}
$$
(see [[Proof of the Properties of Natural Numbers]])

>[!question]+ Application: Loop Invariants and Correctness of Recursive Algorithms
>In theoretical computer science and quantitative software engineering, mathematical induction is the mathematical foundation for proving algorithmic correctness. Consider an iterative search or sorting algorithm (such as *Insertion Sort* or *Binary Search*) operating on an *array* of size $n$:
>
>1. **Initialization (Base Case):** The algorithm establishes a specific state invariant prior to the first iteration of the execution loop ($k = 1$).
>2. **Maintenance (Inductive Step):** Proving that if the invariant holds true before the $k$-th execution step, the algorithmic transformation preserves the invariant prior to the $(k+1)$-th step.
>3. **Termination:** When the loop terminates after $N$ discrete cycles, the inductive invariant guarantees that the final state satisfies the terminal contract (e.g., that an array is sorted or an optimal portfolio weight is resolved).
>
>Furthermore, the Well-Ordering Principle guarantees the termination of recursive routines. By defining a strictly decreasing integer variant function $f: \text{State} \to \mathbb{N}$, each recursive call reduces the variant ($f(s_{k+1}) < f(s_k)$). Because every non-empty subset of $\mathbb{N}$ has a minimal element, the algorithm cannot execute an infinite descent, guaranteeing that the procedure halts in finite time.

---
# Rational and Irrational Numbers

### The Integers
While $\mathbb{N}$ is closed under addition and multiplication, it lacks closure under subtraction. It contains neither the additive neutral element $0$ nor the additive inverse $-n$ for any $n \in \mathbb{N}$. Adjoining these elements constructs the set of *integers*:
$$
\begin{gather}
\textbf{Definition: The Set of Integers} \\[5mm]
\text{The set of integers, denoted by } \mathbb{Z}, \text{ is the union of the natural numbers } \mathbb{N}, \\[2mm]
\text{the set of their additive inverses } -\mathbb{N} := \{-n \mid n \in \mathbb{N}\}, \text{ and the neutral element } \{0\}: \\[3.5mm]
\mathbb{Z} := (-\mathbb{N}) \cup \{0\} \cup \mathbb{N}
\end{gather}
$$

$$
\begin{gather}
\textbf{Proposition: Algebraic Closure and Group Structure of the Integers} \\[5mm]
\text{1. The set } \mathbb{Z} \text{ is closed under addition, subtraction, and multiplication:} \\[2mm]
\forall m, n \in \mathbb{Z}, \quad (m + n) \in \mathbb{Z}, \quad (m - n) \in \mathbb{Z}, \quad (m \cdot n) \in \mathbb{Z} \\[3.5mm]
\text{2. Under addition, the algebraic structure } (\mathbb{Z}, +) \text{ forms an Abelian group.} \\[2mm]
\text{3. Under multiplication, } (\mathbb{Z} \setminus \{0\}, \cdot) \text{ does not form a group, because multiplicative} \\[2mm]
\text{inverses do not exist in } \mathbb{Z} \text{ for any elements other than } 1 \text{ and } -1.
\end{gather}
$$
(see [[Proof that Integer Operations Yield Integers]] and [[Proof of When Integers are Abelian]])

>[!info]+ Remark: Divisibility and Multiples
>Let $m, n \in \mathbb{Z}$ with $n \ne 0$. The integer $n$ is said to *divide* $m$ (denoted $n \mid m$) if there exists an integer $k \in \mathbb{Z}$ such that $m = k \cdot n$. In this case, $m$ is called a *multiple* of $n$, and $n$ is a *divisor* of $m$. If no such integer $k$ exists, $n$ does not divide $m$, denoted $n \nmid m$.

The study of divisibility within $\mathbb{N}$ isolates the irreducible multiplicative atoms of arithmetic:
$$
\begin{gather}
\textbf{Definition: Prime and Composite Numbers} \\[5mm]
\text{A natural number } p \in \mathbb{N} \setminus \{1\} \text{ is called prime if its only divisors in } \mathbb{N} \text{ are } 1 \text{ and } p. \\[2mm]
\text{An integer } n \in \mathbb{N} \setminus \{1\} \text{ that is not prime is called composite.}
\end{gather}
$$

$$
\begin{gather}
\textbf{Theorem: Fundamental Theorem of Arithmetic} \\[5mm]
\text{Every natural number } n > 1 \text{ admits a factorization into a product of prime numbers:} \\[3.5mm]
n = p_1 \cdot p_2 \cdots p_k = \prod_{j=1}^k p_j \\[3.5mm]
\text{Moreover, this representation is unique up to the permutation of the prime factors.}
\end{gather}
$$
(see [[Proof of the Fundamental Theorem of Arithmetic]])

>[!info]+ Remark: Coprime Integers
>Two integers $m, n \in \mathbb{Z}$ are called *relatively prime* (or *coprime*) if their greatest common divisor is unity: $\gcd(m, n) = 1$. Equivalently, their only common divisors in $\mathbb{Z}$ are $1$ and $-1$.

$$
\begin{gather}
\textbf{Lemma: Euclid's Lemma} \\[5mm]
\text{Let } a, b \in \mathbb{Z} \text{ and let } p \in \mathbb{N} \text{ be a prime number. If } p \mid (a \cdot b), \\[2mm]
\text{then } p \mid a \quad \lor \quad p \mid b. \\[3.5mm]
\text{In particular, if } a \text{ and } b \text{ are coprime and } p \mid (a \cdot b), \text{ then } p \text{ divides exactly one of the factors.}
\end{gather}
$$
(see [[Proof of Euclid's Lemma]])

### The Rational Numbers
Because $\mathbb{Z} \setminus \{0\}$ lacks multiplicative inverses, division cannot be performed freely within the ring of integers. Constructing multiplicative inverses for all non-zero elements yields the field of *rational numbers*:
$$
\begin{gather}
\textbf{Definition: The Set of Rational Numbers} \\[5mm]
\text{Real numbers expressible as the quotient of an integer by a non-zero integer are called} \\[2mm]
\text{rational numbers. The set of all rational numbers is denoted by } \mathbb{Q}: \\[3.5mm]
\mathbb{Q} := \left\{ \frac{m}{n} \in \mathbb{R} \ \middle|\ m \in \mathbb{Z}, \ n \in \mathbb{Z} \setminus \{0\} \right\}
\end{gather}
$$

Under the field operations inherited from $\mathbb{R}$, the system $(\mathbb{Q}, +, \cdot, \le)$ forms an ordered field. It contains the additive and multiplicative identities ($0, 1 \in \mathbb{Q}$), closed under addition, subtraction, multiplication, and division by non-zero elements.

##### Equivalence and Canonical Reduction of Fractions
An ordered pair $(m, n) \in \mathbb{Z} \times (\mathbb{Z} \setminus \{0\})$ defines a rational number $q = m \cdot n^{-1}$, yet this representation is not unique. Multiplying both numerator and denominator by a non-zero integer $k \in \mathbb{Z} \setminus \{0\}$ leaves the real value invariant. By the field axioms:
$$
(m \cdot k)(n \cdot k)^{-1} = (m \cdot k)(k^{-1} \cdot n^{-1}) = m \cdot (k \cdot k^{-1}) \cdot n^{-1} = m \cdot n^{-1} \tag{2}
$$

Two pairs $(m_1, n_1)$ and $(m_2, n_2)$ designate the identical rational scalar if and only if cross-multiplication holds:
$$
\frac{m_1}{n_1} = \frac{m_2}{n_2} \iff m_1 n_2 = m_2 n_1 \tag{3}
$$

By factoring out the greatest common divisor $d = \gcd(m, n)$, every rational number $q \in \mathbb{Q}$ admits a *canonical representation*:
$$
q = \frac{p}{q_0}, \quad \text{where } p \in \mathbb{Z}, \ q_0 \in \mathbb{N}, \ \text{and } \gcd(|p|, q_0) = 1 \tag{4}
$$
By Euclid's lemma, this canonical fractional form is unique.

---
# Irrational Numbers
Although $\mathbb{Q}$ is an ordered field, it fails to capture the entire geometric continuum of $\mathbb{R}$. There exist points on the real line that cannot be expressed as the ratio of two integers.

$$
\begin{gather}
\textbf{Definition: The Set of Irrational Numbers} \\[5mm]
\text{Real numbers that do not belong to the set of rational numbers } \mathbb{Q} \text{ are called} \\[2mm]
\text{irrational numbers. The set of irrational numbers is denoted by } \mathbb{R} \setminus \mathbb{Q} \text{ (or } \mathbb{I}\text{).}
\end{gather}
$$

The historical demonstration of the incompleteness of $\mathbb{Q}$ arises from the diagonal of a unit square:
$$
\begin{gather}
\textbf{Proposition: Existence and Irrationality of the Square Root of Two} \\[5mm]
\text{There exists a unique positive real number } s \in \mathbb{R}_{>0} \text{ satisfying } s^2 = 2, \\[2mm]
\text{denoted by } \sqrt{2}. \text{ This number is irrational: } \sqrt{2} \notin \mathbb{Q}.
\end{gather}
$$
(see [[Proof that the Square Root of 2 is Irrational]])

>[!danger]+ Intuition: Incommensurability and the Pythagorean Crisis
>The discovery that $\sqrt{2} \notin \mathbb{Q}$ represented a foundational crisis in Pythagorean mathematics. The Pythagoreans believed that all spatial relationships in the physical universe could be expressed through *commensurability*—that given any two line segments, there exists a common microscopic unit length $u$ such that both segments are integer multiples of $u$.
>
>For the unit square, if the side has length $1$ and the diagonal has length $s$, commensurability requires the existence of integers $p, q \in \mathbb{N}$ such that $s = p/q$. The algebraic deduction that $(p/q)^2 = 2$ forces $p$ and $q$ to be simultaneously even and coprime—a logical contradiction. Geometrically, no subdivision of the unit segment, no matter how fine, can ever measure the diagonal without leaving a remainder. The rational numbers constitute a discontinuous "dust" riddled with gaps; the real continuum $\mathbb{R}$ completes these gaps.

>[!info]+ Remark: Algebraic versus Transcendental Numbers
>Real numbers can be classified based on their relationship to polynomial equations:
>1. **Algebraic Numbers ($\mathbb{A}$):** A real number $x \in \mathbb{R}$ is algebraic if it is a root of a non-zero polynomial with integer coefficients:
>$$
>a_n x^n + a_{n-1} x^{n-1} + \dots + a_1 x + a_0 = 0, \quad a_j \in \mathbb{Z}, \ a_n \ne 0 \tag{5}
>$$
>Every rational number $m/n$ is algebraic ($n x - m = 0$). Radicals such as $\sqrt{2}$ ($x^2 - 2 = 0$) and $\sqrt[3]{5}$ ($x^3 - 5 = 0$) are algebraic irrationals.
>2. **Transcendental Numbers:** A real number that is not algebraic is called transcendental. Fundamental mathematical constants such as $\pi \approx 3.14159\dots$ and $e \approx 2.71828\dots$ are transcendental. While the algebraic numbers $\mathbb{A}$ are countably infinite, the transcendental numbers constitute an uncountably infinite majority of $\mathbb{R}$.

---
# The Principle of Archimedes
How are the discrete subsets $\mathbb{N}$ and $\mathbb{Z}$ distributed across the continuous real line? The bridge connecting the order structure of the integers to the completeness of $\mathbb{R}$ is the *Principle of Archimedes*. 
$$
\begin{align}
& \textbf{Proposition: Bounding Properties of } \mathbb{N} \text{ and } \mathbb{Z} \\[5mm]
& \hspace{0.2 in} \text{The subsets } \mathbb{N} \text{ and } \mathbb{Z} \text{ satisfy the following extremal properties within } \mathbb{R}: \\[3.5mm]
& \hspace{0.2 in} \text{1. Upper Bound Realization in } \mathbb{N}: \text{ Every non-empty subset } S \subseteq \mathbb{N} \text{ that is bounded above} \\[2mm]
& \hspace{0.5 in} \text{contains a maximal element: } \exists m \in S \ \forall s \in S \, (s \le m). \\[2mm]
& \hspace{0.2 in} \text{2. Unboundedness of } \mathbb{N}: \text{ The set of natural numbers } \mathbb{N} \text{ is not bounded above in } \mathbb{R}. \\[2mm]
& \hspace{0.2 in} \text{3. Upper Bound Realization in } \mathbb{Z}: \text{ Every non-empty subset of } \mathbb{Z} \text{ that is bounded above possesses a maximum.} \\[2mm]
& \hspace{0.2 in} \text{4. Lower Bound Realization in } \mathbb{Z}: \text{ Every non-empty subset of } \mathbb{Z} \text{ that is bounded below possesses a minimum.} \\[2mm]
& \hspace{0.2 in} \text{5. Unboundedness of } \mathbb{Z}: \text{ The set of integers } \mathbb{Z} \text{ is unbounded both above and below in } \mathbb{R}.
\end{align}
$$
(see [[Proof of the Bounds in the Natural Numbers and Integers]])

Because $\mathbb{Z}$ is unbounded in both directions and every bounded subset of $\mathbb{Z}$ achieves its extrema, any real number can be bracketed between consecutive integer multiples of an arbitrary positive step size $h$:

$$
\begin{gather}
\textbf{Theorem: The Principle of Archimedes} \\[5mm]
\text{For any fixed positive step size } h \in \mathbb{R}_{>0} \text{ and any arbitrary real number } x \in \mathbb{R}, \\[2mm]
\text{there exists a unique integer } k \in \mathbb{Z} \text{ such that:} \\[3.5mm]
(k - 1)h \le x < kh
\end{gather}
$$
(see [[Proof of the Principle of Archimedes]])

>[!danger]+ Intuition: The Absence of Infinitesimals and Universal Measurement
>The Archimedean property asserts that no matter how small a positive step size $h > 0$ is chosen, and no matter how large a distance $x \in \mathbb{R}$ is specified, accumulating sufficiently many steps of size $h$ will eventually exceed $x$. 
>
>In physical terms, one can measure an astronomical distance using a microscopic ruler, provided the ruler is applied a sufficient number of times. Analytically, this eliminates the possibility of non-zero "infinitesimal" real numbers: there is no positive real number that remains smaller than $1/n$ for all $n \in \mathbb{N}$.

The Principle of Archimedes generates four corollaries that govern analytical limits and density:
$$
\begin{align}
& \textbf{Proposition: Corollaries to Archimedes' Principle} \\[5mm]
& \hspace{0.2 in} \text{The Archimedean property of } \mathbb{R} \text{ guarantees the following analytical properties:} \\[3.5mm]
& \hspace{0.2 in} \text{1. Infinitesimal Avoidance: } \forall \varepsilon \in \mathbb{R}_{>0}, \ \exists n \in \mathbb{N} \text{ such that } 0 < \frac{1}{n} < \varepsilon. \\[2mm]
& \hspace{0.2 in} \text{2. Uniqueness of Zero Limit: } \forall x \in \mathbb{R}_{\ge 0}, \quad \left( \forall n \in \mathbb{N}, \ x < \frac{1}{n} \right) \implies x = 0. \\[2mm]
& \hspace{0.2 in} \text{3. Density of Rational Numbers: } \forall a, b \in \mathbb{R} \text{ with } a < b, \ \exists r \in \mathbb{Q} \text{ such that } a < r < b. \\[2mm]
& \hspace{0.2 in} \text{4. Integer Floor and Fractional Decomposition: } \forall x \in \mathbb{R}, \ \exists! k \in \mathbb{Z} \text{ such that } k \le x < k + 1. \\[2mm]
& \hspace{0.5 in} \text{The integer } \lfloor x \rfloor := k \text{ is the floor (integer part) of } x, \text{ and } \{x\} := x - \lfloor x \rfloor \in [0, 1) \text{ is its fractional part.}
\end{align}
$$
(see [[Proof of Archimedean Corollaries]])

>[!question]+ Application: Binomial Recombining Trees and Continuous Limits in Asset Pricing
>In quantitative finance, the Archimedean property governs the convergence of discrete-time models to continuous-time asset dynamics. In the Cox-Ross-Rubinstein (CRR) binomial model, the trading horizon $[0, T]$ is partitioned into $n$ discrete subintervals of length $\Delta t = T/n$. Over each interval, the asset price transitions by an up-factor $u_n = e^{\sigma \sqrt{\Delta t}}$ or a down-factor $d_n = e^{-\sigma \sqrt{\Delta t}}$.
>
>By Corollary 1 of Archimedes' Principle, choosing $n$ sufficiently large drives the time-step $\Delta t = T/n$ below any arbitrary threshold $\varepsilon > 0$. The price lattice at step $n$ generates a discrete distribution across $n + 1$ terminal states
>$$
>S_n(T) = S_0 \, u_n^k \, d_n^{n-k} = S_0 \, e^{\sigma \sqrt{T/n}(2k - n)}, \quad k \in \{0, 1, \dots, n\} \tag{6}
>$$
>Density (Corollary 3) ensures that as $n \to \infty$, the discrete rational lattice points penetrate every open interval of the continuous log-normal distribution. Under the Central Limit Theorem, the discrete martingale expectation converges to the continuous *Black-Scholes-Merton* expectation
>$$
>\lim_{n \to \infty} (1 + r \Delta t)^{-n} \, \mathbb{E}^{\mathbb{Q}}_n \left[ (S_n(T) - K)^+ \right] = e^{-rT} \, \mathbb{E}^{\mathbb{Q}} \left[ (S(T) - K)^+ \right] \tag{7}
>$$
>Without the Archimedean property, the time grid could not be refined to zero, preventing discrete financial engineering from approximating continuous stochastic processes.

---
# Geometric Interpretation and Computations

### The Real Line and Coordinate Geometry
Modeling $\mathbb{R}$ as an unbroken straight line $\mathbb{L}$ establishes a bridge between continuous geometry and formal analysis. By the axioms of Euclidean geometry, there exists an order-preserving bijective mapping $f: \mathbb{L} \to \mathbb{R}$ that pairs each geometric point $P \in \mathbb{L}$ with a unique coordinate $x = f(P) \in \mathbb{R}$.

Fixing an arbitrary reference point $P_0 \in \mathbb{L}$ as the origin ($f(P_0) = 0$) and a second distinct point $P_1 \in \mathbb{L}$ as the unit point ($f(P_1) = 1$) establishes a coordinate axis. Repeatedly applying the unit translation vector $\vec{T} = \vec{P_0 P_1}$ and its inverse generates the geometric lattice of integer coordinates $P_m$ corresponding to $m \in \mathbb{Z}$.

To locate rational coordinates $m/n \in \mathbb{Q}$ geometrically, classical planar geometry deploys the intercept theorem:
$$
\begin{gather}
\textbf{Thales' Intercept Theorem: } \\[5mm]
\text{If two intersecting lines are intercepted by a pair of parallel lines, then the ratios of the} \\[2mm]
\text{corresponding segments intercepted on one line are equal to the ratios on the other line.}
\end{gather}
$$
(see [[Proof of Thales' Theorem]])

Applying Thales' theorem partitions the unit interval $[P_0, P_1]$ into $n$ congruent segments of length $1/n$; translating these subintervals along $\mathbb{L}$ constructs the point corresponding to every rational coordinate $m/n \in \mathbb{Q}$.

For points whose distance from the origin is incommensurable with the unit segment, every point $P \in \mathbb{L}$ induces a Dedekind partition of $\mathbb{Q}$ into two disjoint sets:
$$
X = \{q \in \mathbb{Q} \mid q \le f(P)\}, \qquad Y = \{q \in \mathbb{Q} \mid q > f(P)\} \tag{8}
$$
Because $x \le y$ for all $x \in X$ and $y \in Y$, the Completeness Axiom guarantees a real number $c \in \mathbb{R}$ such that $x \le c \le y$. Because $\mathbb{Q}$ is dense in $\mathbb{R}$, $\sup X = \inf Y = c = f(P)$, uniquely assigning an irrational coordinate to every remaining point on $\mathbb{L}$. The real line contains no geometric gaps.

### Intervals, Neighborhoods, and Metric Distance
The geometric model formalizes the standard *topological* subsets of $\mathbb{R}$:
$$
\begin{gather}
\textbf{Definition: Numerical Intervals} \\[5mm]
\text{For real numbers } a, b \in \mathbb{R} \text{ with } a \le b, \text{ the bounded intervals determined by } a \text{ and } b \text{ are:} \\[3.5mm]
\text{Open Interval: } (a, b) := \{x \in \mathbb{R} \mid a < x < b\} \\[2mm]
\text{Closed Interval: } [a, b] := \{x \in \mathbb{R} \mid a \le x \le b\} \\[2mm]
\text{Half-Open Intervals: } (a, b] := \{x \in \mathbb{R} \mid a < x \le b\} \quad \text{and} \quad [a, b) := \{x \in \mathbb{R} \mid a \le x < b\} \\[3.5mm]
\text{The length (measure) of any interval } I \text{ with endpoints } a \text{ and } b \text{ is } |I| := b - a.
\end{gather}
$$

>[!info]+ Remark: Alternative Reversed-Bracket Notation
>In French and Bourbaki mathematical literature, open and half-open intervals are often denoted using reversed brackets:
>$$
>]a, b[ \, := (a, b), \qquad [a, b[ \, := [a, b), \qquad ]a, b] \, := (a, b] \tag{9}
>$$
>This repository adheres to standard international ISO notation $(a, b)$, reserving brackets exclusively for closed boundaries.

$$
\begin{gather}
\textbf{Definition: Neighborhood of a Point} \\[5mm]
\text{Any open interval containing a point } x \in \mathbb{R} \text{ is called a neighborhood of } x. \\[2mm]
\text{For any radius } \delta \in \mathbb{R}_{>0}, \text{ the symmetric open interval } (x - \delta, x + \delta) \text{ of length } 2\delta \\[2mm]
\text{centered at } x \text{ is called the } \delta\text{-neighborhood of } x, \text{ denoted } U_\delta(x): \\[3.5mm]
U_\delta(x) := \{y \in \mathbb{R} \mid |y - x| < \delta\}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Absolute Value and Metric Distance} \\[5mm]
\text{The absolute value of a real number } x \in \mathbb{R}, \text{ denoted by } |x|, \text{ is defined as:} \\[3.5mm]
|x| := \begin{cases} x, & \text{if } x \ge 0 \\ -x, & \text{if } x < 0 \end{cases} \\[3.5mm]
\text{The metric distance between two points } x, y \in \mathbb{R} \text{ is defined as } d(x, y) := |x - y|.
\end{gather}
$$

The metric distance satisfies three properties:
1. Positivity: $d(x, y) \ge 0$, and $d(x, y) = 0 \iff x = y$.
2. Symmetry: $d(x, y) = d(y, x)$.
3. Triangle Inequality: $d(x, z) \le d(x, y) + d(y, z)$ for all $x, y, z \in \mathbb{R}$.

$$
\begin{gather}
\textbf{Proposition: The Triangle Inequality} \\[5mm]
\text{For any real numbers } x, y \in \mathbb{R}: \\[3.5mm]
\text{1. Standard Form: } |x + y| \le |x| + |y| \\[2mm]
\text{2. Difference Form: } |x - y| \le |x| + |y| \\[2mm]
\text{3. Reverse Triangle Inequality: } \big| |x| - |y| \big| \le |x - y| \\[3.5mm]
\text{In the standard form, equality holds if and only if } x \text{ and } y \text{ share the same sign } (x \cdot y \ge 0).
\end{gather}
$$
(see [[Proof of the Triangle Inequality]])

---
# Errors in Computations
In empirical sciences, numerical analysis, and quantitative finance, continuous real quantities cannot be represented with infinite precision; they are approximated by finite rational numbers or floating-point registers: 
$$
\begin{gather}
\textbf{Definition: Absolute and Relative Error} \\[5mm]
\text{Let } x \in \mathbb{R} \text{ denote an exact value and let } \tilde{x} \in \mathbb{R} \text{ denote an approximation of } x. \\[3.5mm]
\text{Absolute Error: } \Delta(\tilde{x}) := |x - \tilde{x}| \\[2mm]
\text{Relative Error: } \delta(\tilde{x}) := \frac{\Delta(\tilde{x})}{|\tilde{x}|} = \frac{|x - \tilde{x}|}{|\tilde{x}|} \quad (\text{for } \tilde{x} \ne 0)
\end{gather}
$$

Because the exact value $x$ is typically unknown, the exact errors $\Delta(\tilde{x})$ and $\delta(\tilde{x})$ are inaccessible. Instead, scientific routines establish known upper bounds $\Delta$ and $\delta$ such that
$$
\Delta(\tilde{x}) \le \Delta \quad \text{and} \quad \delta(\tilde{x}) \le \delta \tag{10}
$$
These majorants are called the *limiting absolute error* and *limiting relative error*. Writing $x = \tilde{x} \pm \Delta$ signifies that $x \in [\tilde{x} - \Delta, \tilde{x} + \Delta]$.

>[!example]- Example: Precision in Fundamental Physical Constants
>Empirical measurements of physical constants are reported with limiting absolute errors reflecting instrument resolution:
>* **Newtonian Gravitational Constant:** $G = (6.67430 \pm 0.00015) \cdot 10^{-11}\text{ m}^3/(\text{kg}\cdot\text{s}^2)$ ($\delta \approx 2.2 \cdot 10^{-5}$)
>* **Speed of Light in Vacuum:** $c = 299\,792\,458\text{ m/s}$ (Exact by definition of the SI meter; $\Delta = 0, \delta = 0$)
>* **Planck Constant:** $h = 6.62607015 \cdot 10^{-34}\text{ J}\cdot\text{s}$ (Exact by international SI standard)
>* **Elementary Charge:** $e = 1.602176634 \cdot 10^{-19}\text{ C}$ (Exact by definition)
>* **Electron Rest Mass:** $m_e = (9.1093837015 \pm 0.0000000028) \cdot 10^{-31}\text{ kg}$ ($\delta \approx 3.1 \cdot 10^{-10}$)

When arithmetic operations combine approximate inputs, error bounds propagate according to the field properties of $\mathbb{R}$:
$$
\begin{gather}
\textbf{Proposition: Propagation of Absolute Errors} \\[5mm]
\text{Let } \tilde{x} \text{ and } \tilde{y} \text{ be approximations of } x \text{ and } y \text{ with absolute errors } \Delta(\tilde{x}) \text{ and } \Delta(\tilde{y}). \text{ Then:} \\[3.5mm]
\Delta(\tilde{x} \pm \tilde{y}) \le \Delta(\tilde{x}) + \Delta(\tilde{y}) \\[2mm]
\Delta(\tilde{x} \cdot \tilde{y}) \le |\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x}) + \Delta(\tilde{x})\Delta(\tilde{y}) \\[2mm]
\Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \le \frac{|\tilde{y}|\Delta(\tilde{x}) + |\tilde{x}|\Delta(\tilde{y})}{\tilde{y}^2 (1 - \delta(\tilde{y}))} \quad (\text{provided } \tilde{y} \ne 0 \text{ and } \delta(\tilde{y}) < 1)
\end{gather}
$$
(see [[Proof of Error Propagation Methods]])

>[!info]+ Remark: Propagation of Relative Errors and Numerical Instabilities
>Dividing the absolute error bounds by the magnitude of the approximate output yields the relative error propagation bounds:
>$$
>\begin{align}
>\delta(\tilde{x} \pm \tilde{y}) &\le \frac{\Delta(\tilde{x}) + \Delta(\tilde{y})}{|\tilde{x} \pm \tilde{y}|} \tag{11} \\[2mm]
>\delta(\tilde{x} \cdot \tilde{y}) &\le \delta(\tilde{x}) + \delta(\tilde{y}) + \delta(\tilde{x})\delta(\tilde{y}) \tag{12} \\[2mm]
>\delta\left(\frac{\tilde{x}}{\tilde{y}}\right) &\le \frac{\delta(\tilde{x}) + \delta(\tilde{y})}{1 - \delta(\tilde{y})} \tag{13}
>\end{align}
>$$
>When the relative errors are small ($\delta(\tilde{x}), \delta(\tilde{y}) \ll 1$), second-order terms satisfy $\delta(\tilde{x})\delta(\tilde{y}) \approx 0$ and $1 - \delta(\tilde{y}) \approx 1$, yielding the linearized first-order approximations:
>$$
>\delta(\tilde{x} \cdot \tilde{y}) \approx \delta(\tilde{x}) + \delta(\tilde{y}), \qquad \delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \approx \delta(\tilde{x}) + \delta(\tilde{y}) \tag{14}
>$$
>The exact bounds in step 11 through step 13 expose two major sources of numerical failure in scientific software:
>1. **Catastrophic Cancellation:** In step 11, if $\tilde{x} \approx \tilde{y}$ and subtraction is performed (or $\tilde{x} \approx -\tilde{y}$ and addition is performed), the denominator $|\tilde{x} \pm \tilde{y}|$ approaches zero while the numerator remains non-zero. The relative error explodes, destroying all significant digits.
>2. **Ill-Conditioned Division:** In step 13, dividing by an approximate divisor $\tilde{y}$ whose relative uncertainty approaches unity ($\delta(\tilde{y}) \to 1$) causes the error bound to diverge to infinity.

---
# Application: Positional Computation Systems
While the decimal system (base $10$) is standard for human computation, digital architectures operate in binary (base $2$), octal (base $8$), or hexadecimal (base $16$). The Principle of Archimedes guarantees that any positive real number can be represented and approximated to arbitrary precision in any natural base $q \in \mathbb{N} \setminus \{1\}$.

$$
\begin{gather}
\textbf{Lemma: Base Order Bounds} \\[5mm]
\text{For any natural base } q \in \mathbb{N} \text{ with } q > 1 \text{ and any positive real number } x \in \mathbb{R}_{>0}, \\[2mm]
\text{there exists a unique integer } p \in \mathbb{Z} \text{ such that:} \\[3.5mm]
q^p \le x < q^{p+1}
\end{gather}
$$
(see [[Proof of Positional Computational System]])

$$
\begin{gather}
\textbf{Definition: Order of a Real Number in Base } q \\[5mm]
\text{The unique integer } p \in \mathbb{Z} \text{ satisfying } q^p \le x < q^{p+1} \text{ is called} \\[2mm]
\text{the order (or exponent) of the number } x \text{ in the base } q.
\end{gather}
$$

### The $q$-ary Digit Extraction Algorithm
Applying the Principle of Archimedes to $x$ with step size $h = q^p$ determines a unique integer $\alpha_p \in \{1, 2, \dots, q - 1\}$ such that
$$
\alpha_p q^p \le x < (\alpha_p + 1)q^p = \alpha_p q^p + q^p \tag{15}
$$
The remainder $x - \alpha_p q^p$ belongs to the interval $[0, q^p)$. Applying Archimedes' Principle to this remainder with step size $h = q^{p-1}$ uniquely determines $\alpha_{p-1} \in \{0, 1, \dots, q - 1\}$ such that
$$
\alpha_p q^p + \alpha_{p-1} q^{p-1} \le x < \alpha_p q^p + \alpha_{p-1} q^{p-1} + q^{p-1} \tag{16}
$$

Proceeding inductively for $n$ steps generates a finite sequence of digits $\alpha_p, \alpha_{p-1}, \dots, \alpha_{p-n} \in \{0, 1, \dots, q - 1\}$ with $\alpha_p \ne 0$, producing a monotonic sequence of lower rational approximations:
$$
r_n := \sum_{j=0}^n \alpha_{p-j} q^{p-j} \tag{17}
$$
(see [[Proof of the Lower Rational Approximation Sequence]]) satisfying the error bounds:
$$
r_n \le x < r_n + \frac{1}{q^{n-p}} \tag{18}
$$

>[!info]+ Remark: Uniqueness of Positional Expansions and Exclusion of Infinite $(q-1)$ Tails
>By virtue of the strict upper inequality in step 20, the digit extraction algorithm can never produce an expansion terminating in an infinite sequence of maximum digits ($\alpha_{p-n} = q - 1$ for all $n > k$). If $\alpha_{p-j} = q - 1$ for all $j \in \{k + 1, \dots, n\}$, summing the geometric series yields
>$$
>r_n = r_k + \sum_{j=k+1}^n (q - 1)q^{p-j} = r_k + \frac{1}{q^{k-p}} - \frac{1}{q^{n-p}} \tag{19}
>$$
>Substituting step 21 into step 20 would require
>$$
>0 < r_k + \frac{1}{q^{k-p}} - x \le \frac{1}{q^{n-p}} \quad \forall n > k \tag{20}
>$$
>By Corollary 2 of Archimedes' Principle, no strictly positive quantity can remain bounded above by $q^{-(n-p)}$ for all $n > k$, which is a contradiction.
>
>Conversely, if a formal $q$-ary digit sequence contains digits smaller than $q - 1$ at arbitrarily large ranks, the nested approximations satisfy
>$$
>r_0 \le r_1 \le \dots \le r_n \le \dots < r_n + \frac{1}{q^{n-p}} \le \dots \le r_0 + \frac{1}{q^{-p}} \tag{21}
>$$
>By the Completeness Axiom, the unique real number represented by the expansion is $x := \sup_{n} r_n = \inf_{n} (r_n + q^{-(n-p)})$.

>[!question]+ Application: IEEE 754 Floating-Point Standard and Machine Epsilon
>In modern digital microprocessors, floating-point numbers are represented in binary ($q = 2$) adhering to the IEEE 754 standard. A non-zero real number $x$ is stored in a normalized binary format:
>$$
>x = (-1)^s \cdot (1.b_1 b_2 \dots b_m)_2 \cdot 2^{e - B} \tag{22}
>$$
>where $s \in \{0, 1\}$ is the sign *bit*, $e \in \mathbb{N}_0$ is the *biased exponent*, $B$ is the *exponent bias*, and $m$ is the *mantissa* bit width ($m = 23$ for single precision `Float32`, $m = 52$ for double precision `Float64`).
>
>Because the mantissa is truncated to $m$ bits, real numbers with non-terminating binary expansions cannot be represented exactly. Even simple decimal fractions like $0.1_{(10)} = 0.0001100110011\dots_{(2)}$ incur representation error. The upper bound on relative rounding error is given by *machine epsilon*:
>$$
>\varepsilon_{\text{mach}} := 2^{-m} \quad (\varepsilon_{\text{mach}} \approx 2.22 \cdot 10^{-16} \text{ for Float64}) \tag{23}
>$$
>In large-scale quantitative simulations—such as pricing complex path-dependent contracts over millions of discrete time increments—accumulated machine epsilon errors drift the simulation path unless compensated by numerically stable summation routines (e.g., Kahan compensated summation).

---
# Additional Useful Facts

$$
\begin{gather}
\textbf{Theorem: Isomorphism and Categoricity of } \mathbb{R} \\[5mm]
\text{Any two complete linearly ordered fields } (\mathbb{R}, +, \cdot, \le) \text{ and } (\mathbb{R}', +', \cdot', \le') \\[2mm]
\text{are isomorphic via a unique order-preserving field isomorphism.}
\end{gather}
$$
(see [[Proof of Isomorphism and Categoricity in the Real Numbers]])

This theorem establishes the categorical uniqueness of the real numbers: all analytical constructions of the continuum—whether via Dedekind cuts or Cauchy sequences of rationals—are structurally identical up to a unique isomorphism.

$$
\begin{gather}
\textbf{Theorem: Dedekind's Cut Principle and Completeness Equivalence} \\[5mm]
\text{In an ordered field } \mathbb{F}, \text{ the Least Upper Bound Axiom holds if and only if for every partition} \\[2mm]
\text{of } \mathbb{F} \text{ into two non-empty disjoint subsets } X \text{ and } Y \text{ satisfying } x \le y \text{ for all } x \in X, y \in Y, \\[2mm]
\text{there exists a unique cut element } c \in \mathbb{F} \text{ such that } x \le c \le y \text{ for all } x \in X \text{ and } y \in Y.
\end{gather}
$$
(see [[Proof of Dedekind's Cut Theorem and Complete Equivalence]])

$$
\begin{gather}
\textbf{Proposition: Monotonicity and Ordering of Extrema} \\[5mm]
\text{Let } A, B \subset \mathbb{R} \text{ be non-empty bounded subsets of } \mathbb{R}. \text{ If } A \subseteq B, \text{ then:} \\[3.5mm]
\sup A \le \sup B \quad \text{and} \quad \inf A \ge \inf B \\[3.5mm]
\text{Furthermore, if } X, Y \subset \mathbb{R} \text{ are non-empty subsets such that } x \le y \text{ for all } x \in X \text{ and } y \in Y, \text{ then:} \\[3.5mm]
\sup X \le \inf Y \\[3.5mm]
\text{If, in addition, } \forall \varepsilon > 0 \ \exists x \in X, y \in Y \text{ such that } y - x < \varepsilon, \text{ then } \sup X = \inf Y.
\end{gather}
$$
(see [[Proof of Monotonicity and Ordering of Extrema]])

$$
\begin{gather}
\textbf{Proposition: Algebraic Operations on Bounded Sets (Minkowski Sum and Product)} \\[5mm]
\text{For non-empty bounded subsets } A, B \subset \mathbb{R}, \text{ define the Minkowski sum } A + B := \{a + b \mid a \in A, b \in B\} \\[2mm]
\text{and the Minkowski product } A \cdot B := \{a \cdot b \mid a \in A, b \in B\}. \text{ Then:} \\[3.5mm]
\sup(A + B) = \sup A + \sup B \quad \text{and} \quad \inf(A + B) = \inf A + \inf B \\[3.5mm]
\text{If } A \text{ and } B \text{ consist exclusively of non-negative real numbers } (A, B \subset \mathbb{R}_{\ge 0}), \text{ then:} \\[3.5mm]
\sup(A \cdot B) = (\sup A) \cdot (\sup B) \quad \text{and} \quad \inf(A \cdot B) = (\inf A) \cdot (\inf B)
\end{gather}
$$
(see [[Proof of Algebraic Operations on Bounded Sets]])

>[!example]- Example: Tolerance Stack-Up in Mechanical Engineering as Minkowski Sums
>In precision mechanical manufacturing, physical parts are fabricated within allowable dimensional tolerance intervals. Consider the assembly of three components mounted sequentially along a linear shaft:
>* Part A length: $L_A \in [10.00 - 0.05, 10.00 + 0.05] = [9.95, 10.05]\text{ mm}$
>* Part B length: $L_B \in [25.00 - 0.10, 25.00 + 0.10] = [24.90, 25.10]\text{ mm}$
>* Part C length: $L_C \in [15.00 - 0.08, 15.00 + 0.08] = [14.92, 15.08]\text{ mm}$
>
>The total assembly length $L_{\text{total}}$ is the Minkowski sum of the individual tolerance intervals:
>$$
>L_{\text{total}} = L_A + L_B + L_C \tag{24}
>$$
>Applying the Minkowski supremum and infimum properties:
>$$
>\begin{align}
>\sup(L_{\text{total}}) &= \sup L_A + \sup L_B + \sup L_C = 10.05 + 25.10 + 15.08 = 50.23\text{ mm} \\[2mm]
>\inf(L_{\text{total}}) &= \inf L_A + \inf L_B + \inf L_C = 9.95 + 24.90 + 14.92 = 49.77\text{ mm} \tag{25}
>\end{align}
>$$
>The total worst-case dimensional clearance interval is $[49.77, 50.23]\text{ mm}$, with total tolerance stack-up equal to the sum of the individual absolute tolerances: $0.05 + 0.10 + 0.08 = 0.23\text{ mm}$.

$$
\begin{gather}
\textbf{Proposition: Bernoulli's Inequality} \\[5mm]
\text{For every real number } x \in \mathbb{R} \text{ with } x \ge -1 \text{ and every natural number } n \in \mathbb{N}, \\[3.5mm]
(1 + x)^n \ge 1 + nx \\[3.5mm]
\text{If } n > 1 \text{ and } x \ne 0 \text{ with } x > -1, \text{ the inequality is strict: } (1 + x)^n > 1 + nx.
\end{gather}
$$
(see [[Proof of Bernoulli's Inequality]])

>[!question]+ Application: Compound Interest, Simple Interest, and the Compounding Premium
>In quantitative finance and the economics of capital formation, Bernoulli's inequality formalizes the mathematical difference between compound interest and simple interest.
>
>Let $P_0$ represent an initial capital investment deployed over $n \in \mathbb{N}$ periods at a periodic rate of return $r > 0$ (so $r > -1$ holds trivially):
>1. **Simple Interest (Linear Return):** The accrued capital without reinvestment of earnings grows linearly:
>$$
>V_{\text{simple}}(n) = P_0 (1 + n r) \tag{26}
>$$
>2. **Compound Interest (Exponential Return):** Reinvesting all periodic cash flows compounds capital multiplicatively:
>$$
>V_{\text{compound}}(n) = P_0 (1 + r)^n \tag{27}
>$$
>
>Setting $x = r$ in Bernoulli's inequality demonstrates that
>$$
>(1 + r)^n \ge 1 + nr \implies V_{\text{compound}}(n) \ge V_{\text{simple}}(n) \tag{28}
>$$
>For any investment horizon spanning more than one period ($n \ge 2$) and non-zero yield ($r > 0$), the inequality is strict:
>$$
>V_{\text{compound}}(n) > V_{\text{simple}}(n) \tag{29}
>$$
>The difference $P_0 \left[ (1 + r)^n - (1 + nr) \right] > 0$ represents the *compounding premium* generated by the accumulation of interest on prior interest, illustrating why the time value of money compounds exponentially over extended investment horizons.

$$
\begin{align}
& \textbf{Proposition: Existence of Unique } n\textbf{-th Roots and Rational Exponentiation} \\[5mm]
& \hspace{0.2 in} \text{For any } n \in \mathbb{N} \text{ and any } a \in \mathbb{R}_{>0}, \text{ the polynomial equation } x^n = a \text{ admits a unique positive root:} \\[3.5mm]
& \hspace{0.6 in} x = \sqrt[n]{a} =: a^{1/n} \\[3.5mm]
& \hspace{0.2 in} \text{Furthermore, for all } a, b \in \mathbb{R}_{>0}, \ m, n \in \mathbb{N}, \text{ and } r_1, r_2 \in \mathbb{Q}, \text{ the following operational laws hold:} \\[3.5mm]
& \hspace{0.2 in} \text{1. Root Products and Nesting: } \sqrt[n]{ab} = \sqrt[n]{a} \cdot \sqrt[n]{b} \quad \wedge \quad \sqrt[n]{\sqrt[m]{a}} = \sqrt[nm]{a} \\[2mm]
& \hspace{0.2 in} \text{2. Fractional Power Consistency: } (a^{1/n})^m = (a^m)^{1/n} =: a^{m/n} \quad \wedge \quad a^{1/n} \cdot a^{1/m} = a^{\frac{1}{n} + \frac{1}{m}} \\[2mm]
& \hspace{0.2 in} \text{3. Rational Power Laws: } a^{r_1} \cdot a^{r_2} = a^{r_1 + r_2}, \quad (a^{r_1})^{r_2} = a^{r_1 r_2}, \quad (ab)^{r_1} = a^{r_1} b^{r_1}
\end{align}
$$
(see [[Proof of the Rules of Rational Expressions]])

$$
\begin{gather}
\textbf{Proposition: Non-Archimedean Ordered Fields} \\[5mm]
\text{The field of rational functions } \mathbb{Q}(x) \text{ equipped with the ordering defined by the sign of the} \\[2mm]
\text{leading coefficient at highest degree forms a linearly ordered field that is non-Archimedean.}
\end{gather}
$$
(see [[Proof of Non-Archimedean Ordering Fields]])

$$
\begin{gather}
\textbf{Lemma: Von Neumann Ordinal Embeddings} \\[5mm]
\text{The set-theoretic successor operation } x^+ := x \cup \{x\} \text{ on von Neumann ordinals} \\[2mm]
\text{satisfies strict injectivity and the well-ordering principle under set membership } \in.
\end{gather}
$$
(see [[Proof of Von-Neumann Ordinal Embeddings]])

$$
\begin{gather}
\textbf{Lemma: The Euclidean Algorithm and Bézout's Identity} \\[5mm]
\text{Let } m, n \in \mathbb{N} \text{ with } m \ge n. \text{ If } n \mid m, \text{ the greatest common divisor is } \gcd(m, n) = n. \\[2mm]
\text{Otherwise, } d = \gcd(m, n) \text{ is computed in finitely many steps via successive divisions with} \\[2mm]
\text{strictly decreasing non-negative remainders:} \\[3.5mm]
m = q_1 n + r_1 \quad (0 < r_1 < n) \\[2mm]
n = q_2 r_1 + r_2 \quad (0 < r_2 < r_1) \\[2mm]
r_1 = q_3 r_2 + r_3 \quad (0 < r_3 < r_2) \\[2mm]
\vdots \\[2mm]
r_{k-2} = q_k r_{k-1} + r_k \quad (0 < r_k < r_{k-1}) \\[2mm]
r_{k-1} = q_{k+1} r_k + 0 \\[3.5mm]
\text{The last non-zero remainder is the greatest common divisor: } d = r_k. \text{ Consequently, there exist} \\[2mm]
\text{integers } u, v \in \mathbb{Z} \text{ such that } um + vn = d. \text{ In particular, } \gcd(m, n) = 1 \iff \exists u, v \in \mathbb{Z} \ (um + vn = 1).
\end{gather}
$$
(see [[Proof that Euclid's Algorithm Works]])

>[!question]+ Application: Modular Multiplicative Inverses and RSA Cryptography
>In financial transaction networks and distributed cryptographic protocols (such as blockchain execution and institutional bank messaging), secure communication relies on asymmetric RSA cryptography.
>
>Let $p$ and $q$ be distinct large prime numbers, with modulus $n = pq$ and Euler totient $\varphi(n) = (p - 1)(q - 1)$. An encryption exponent $e$ is selected such that $\gcd(e, \varphi(n)) = 1$. Computing the corresponding private decryption key $d$ requires finding the modular multiplicative inverse:
>$$
>e \cdot d \equiv 1 \pmod{\varphi(n)} \tag{30}
>$$
>Because $\gcd(e, \varphi(n)) = 1$, Bézout's identity guarantees the existence of integers $d, k \in \mathbb{Z}$ such that:
>$$
>d \cdot e + k \cdot \varphi(n) = 1 \tag{31}
>$$
>The Extended Euclidean Algorithm computes the integer $d$ in logarithmic time $\mathcal{O}(\log(\varphi(n)))$. The arithmetic of the Euclidean algorithm is the operational mechanism enabling the generation of public-private key pairs protecting global financial clearing networks.

$$
\begin{gather}
\textbf{Lemma: Properties of Order-Preserving Field Homomorphisms} \\[5mm]
\text{Any non-trivial order-preserving ring homomorphism } f: \mathbb{R} \to \mathbb{R}' \text{ between complete ordered fields} \\[2mm]
\text{maps } 0 \mapsto 0' \text{ and } 1 \mapsto 1', \text{ preserves positive rationals, and restricts to an order isomorphism on } \mathbb{Q}.
\end{gather}
$$
(see [[Proof of Properties of Order-Preserving Homomorphisms]])
