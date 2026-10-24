---
dg-publish: true
---
Having established the axiomatic foundation of the real numbers, the investigation now turns toward isolating the fundamental subsets residing within $\mathbb{R}$. While the continuum of real numbers is vast, a select hierarchy of subsets forms the structural scaffolding for computation, measurement, and quantitative modeling. Constructing these classes directly from the field and completeness axioms reveals how discrete arithmetic and continuous geometry emerge from a single unified framework.

---
# The Natural Numbers and the Principle of Induction
Within set theory, the notion of an *inductive set* captures the mechanics of sequential progression. In the context of real analysis, an inductive set is a nonempty subset of $\mathbb{R}$ closed under the operation of adding unity:

$$
\begin{gather}
\textbf{Definition: Inductive Set} \\[5mm]
\text{A subset } X \subset \mathbb{R} \text{ is called an inductive set if, for every element } x \in X, \\[2mm]
\text{the successor element } x + 1 \text{ also belongs to } X.
\end{gather}
$$

>[!example]- Example: Inductive Subsets of the Real Numbers
>The entire set of real numbers $\mathbb{R}$ and the set of strictly positive real numbers $\mathbb{R}_+$ both satisfy the definition of an inductive set. Furthermore, the intersection of any arbitrary family of inductive sets $\{X_\alpha\}_{\alpha \in A}$, provided it is nonempty, remains inductive. If an element $x$ belongs to the intersection $X = \bigcap_{\alpha \in A} X_\alpha$, it belongs to every constituent set $X_\alpha$, which guarantees that $x + 1$ also resides in every $X_\alpha$:
>$$
>\begin{gather}
>\left( x \in X = \bigcap_{\alpha \in A} X_\alpha \right) \implies \left( \forall \alpha \in A \ (x \in X_\alpha) \right) \implies \\[2mm]
>\left( \forall \alpha \in A \ ((x + 1) \in X_\alpha) \right) \implies \left( (x + 1) \in \bigcap_{\alpha \in A} X_\alpha = X \right) \tag{1}
>\end{gather}
>$$

How does one isolate the purely discrete counting numbers from the continuous expanse of $\mathbb{R}$? By taking the intersection of all inductive sets containing the multiplicative identity $1$, one extracts the minimal inductive core of the real line—the *natural numbers*:

$$
\begin{gather}
\textbf{Definition: The Set of Natural Numbers} \\[5mm]
\text{The set of natural numbers, denoted } \mathbb{N}, \text{ is the smallest inductive subset of } \mathbb{R} \\[2mm]
\text{containing the number } 1. \text{ Formally, } \mathbb{N} \text{ is the intersection of all inductive sets containing } 1.
\end{gather}
$$

>[!info]+ Remark: The Role of Zero in $\mathbb{N}$
>In foundational set theory and theoretical computer science, it is common practice to include $0$ as the initial element of the natural numbers, defining the set as the smallest inductive set containing $0$. However, these notes adhere to the classical analytical convention where $1$ is the minimal element of $\mathbb{N}$. The union $\mathbb{N} \cup \{0\}$ shall instead be referred to as the set of *whole numbers*.

Because $\mathbb{N}$ is constructed as the minimal inductive set containing $1$, any subset of $\mathbb{N}$ that shares this inductive property must encompass the entirety of $\mathbb{N}$. This structural truth yields one of the most essential proof techniques in mathematics:
$$
\begin{gather}
\textbf{Theorem: The Principle of Mathematical Induction} \\[5mm]
\text{If a subset } E \subset \mathbb{N} \text{ satisfies the conditions } 1 \in E \text{ and } (x \in E \implies (x + 1) \in E), \\[2mm]
\text{then the subset } E \text{ is identical to } \mathbb{N}.
\end{gather}
$$
(see [[Proof that Induction Works|proof]])

Applying the principle of induction establishes the fundamental arithmetic and ordering properties of the natural numbers:
$$
\begin{align}
& \textbf{Proposition: Properties of Natural Numbers} \\[5mm]
& \hspace{0.5 in} \text{The elements of } \mathbb{N} \text{ satisfy the following structural properties:} \\[3.5mm]
& \hspace{0.5 in} 1. \ \text{For any } m, n \in \mathbb{N}, \text{ both the sum } m + n \text{ and the product } m \cdot n \text{ belong to } \mathbb{N}. \\[2mm]
& \hspace{0.5 in} 2. \ (n \in \mathbb{N}) \wedge (n \ne 1) \implies (n - 1) \in \mathbb{N}. \\[2mm]
& \hspace{0.5 in} 3. \ \text{For any } n \in \mathbb{N}, \text{ the set } \{x \in \mathbb{N} \mid n < x\} \text{ possesses a minimal element } \min\{x \in \mathbb{N} \mid n < x\} = n + 1. \\[2mm]
& \hspace{0.5 in} 4. \ (m, n \in \mathbb{N}) \wedge (n < m) \implies (n + 1 \le m). \\[2mm]
& \hspace{0.5 in} 5. \ \text{For any } n \in \mathbb{N}, \text{ the element } n + 1 \text{ is the immediate successor of } n \text{ in } \mathbb{N}. \\[2mm]
& \hspace{0.5 in} 6. \ \text{For any } n \in \mathbb{N} \text{ with } n \ne 1, \text{ the element } n - 1 \text{ is the immediate predecessor of } n \text{ in } \mathbb{N}. \\[2mm]
& \hspace{0.5 in} 7. \ \text{Every nonempty subset of } \mathbb{N} \text{ possesses a unique minimal element (Well-Ordering Principle).}
\end{align}
$$
(see [[Proof of the Properties of Natural Numbers|proof]])

---
# Rational and Irrational Numbers

### Prelude to Rational Numbers: The Integers
While $\mathbb{N}$ is closed under addition and multiplication, it lacks closure under subtraction because it contains neither the additive identity $0$ nor additive inverses. Adjoining these elements to the natural numbers constructs the set of *integers*:
$$
\begin{gather}
\textbf{Definition: The Set of Integers} \\[5mm]
\text{The set of integers, denoted } \mathbb{Z}, \text{ is the union of the natural numbers } \mathbb{N}, \\[2mm]
\text{the set of their additive inverses } -\mathbb{N} := \{-n \mid n \in \mathbb{N}\}, \text{ and the neutral element } \{0\}.
\end{gather}
$$

Closure under arithmetic operations extends naturally from $\mathbb{N}$ to $\mathbb{Z}$:
$$
\begin{gather}
\textbf{Proposition: Algebraic Closure of the Integers} \\[5mm]
\text{The set of integers } \mathbb{Z} \text{ is closed under addition, subtraction, and multiplication.} \\[2mm]
\text{That is, for any } m, n \in \mathbb{Z}, \text{ the quantities } m + n, \ m - n, \text{ and } m \cdot n \text{ belong to } \mathbb{Z}.
\end{gather}
$$
(see [[Proof that Integer Operations Yield Integers|proof]])

This algebraic closure defines the group-theoretic structure of $\mathbb{Z}$ within the real field:
$$
\begin{gather}
\textbf{Proposition: Group Structure of the Integers} \\[5mm]
\text{The set } \mathbb{Z} \text{ forms an abelian group with respect to addition. Conversely, neither } \mathbb{Z} \text{ nor } \mathbb{Z} \setminus \{0\} \\[2mm]
\text{forms a group with respect to multiplication, as the multiplicative inverse } n^{-1} \text{ of an integer } n \in \mathbb{Z} \\[2mm]
\text{does not reside in } \mathbb{Z} \text{ except when } n = 1 \text{ or } n = -1.
\end{gather}
$$
(see [[Proof of When Integers are Abelian|proof]])

>[!info]+ Remark: Divisibility
>For two integers $m, n \in \mathbb{Z}$ with $n \ne 0$, if the quotient $k = m \cdot n^{-1}$ belongs to $\mathbb{Z}$ (meaning $m = k \cdot n$), then $m$ is called a *multiple* of $n$, and $n$ is said to *divide* $m$. This divisibility relation is denoted by $n \mid m$.

The study of divisibility within $\mathbb{N}$ isolates the irreducible building blocks of arithmetic:
$$
\begin{gather}
\textbf{Definition: Prime Numbers} \\[5mm]
\text{A natural number } p \in \mathbb{N} \text{ strictly greater than } 1 \text{ is called prime if its only} \\[2mm]
\text{divisors within } \mathbb{N} \text{ are } 1 \text{ and } p \text{ itself.}
\end{gather}
$$

Prime numbers govern the multiplicative decomposition of all natural numbers greater than unity:
$$
\begin{gather}
\textbf{Theorem: Fundamental Theorem of Arithmetic} \\[5mm]
\text{Every natural number } n > 1 \text{ can be represented as a product of prime numbers} \\[3.5mm]
n = p_1 \cdot p_2 \cdots p_k \\[3.5mm]
\text{Moreover, this prime factorization is unique up to the ordering of the factors.}
\end{gather}
$$
(see [[Proof of the Fundamental Theorem of Arithmetic|proof]])

>[!info]+ Remark: Relatively Prime Integers
>Two integers $m, n \in \mathbb{Z}$ are said to be *relatively prime* (or *coprime*) if their only common divisors in $\mathbb{Z}$ are $1$ and $-1$.

A vital consequence of unique prime factorization is Euclid's lemma regarding prime divisibility of products:
$$
\begin{gather}
\textbf{Lemma: Euclid's Lemma} \\[5mm]
\text{If the product } m \cdot n \text{ of two integers } m, n \in \mathbb{Z} \text{ is divisible by a prime number } p, \\[2mm]
\text{then at least one of the factors } m \text{ or } n \text{ is divisible by } p. \text{ In particular, if } m \text{ and } n \text{ are} \\[2mm]
\text{relatively prime and } p \mid (m \cdot n), \text{ then } p \text{ divides exactly one of the two integers.}
\end{gather}
$$
(see [[Proof of the Fundamental Theorem of Arithmetic|proof]])

### Rational Numbers
Because $\mathbb{Z} \setminus \{0\}$ fails to contain multiplicative inverses, dividing one integer by another generally produces a quantity outside $\mathbb{Z}$. Restoring multiplicative closure requires constructing the set of *rational numbers*:
$$
\begin{gather}
\textbf{Definition: The Set of Rational Numbers} \\[5mm]
\text{Real numbers expressible in the form } m \cdot n^{-1} \text{ (written equivalently as } m/n \text{ or } \frac{m}{n}\text{),} \\[2mm]
\text{where } m, n \in \mathbb{Z} \text{ and } n \ne 0, \text{ are called rational numbers. The set of all rational numbers is denoted } \mathbb{Q}.
\end{gather}
$$

>[!info]+ Remark: Quotients and Fractions
>In the rational expression $q = m/n$, the integer $m$ is termed the *numerator* and the non-zero integer $n$ is termed the *denominator*. The expression $m/n$ is referred to as the *quotient* of $m$ by $n$, or as a *rational fraction*.

##### Equivalence and Reduction of Rational Fractions
An ordered pair of integers $(m, n)$ with $n \ne 0$ uniquely determines a rational number $q = m \cdot n^{-1}$, yet distinct ordered pairs can represent the exact same real value. Specifically, multiplying both the numerator and denominator by a non-zero integer $k \in \mathbb{Z}$ preserves the value of the fraction. By the field axioms of $\mathbb{R}$, $(n \cdot k)(k^{-1} \cdot n^{-1}) = 1$, which implies $(n \cdot k)^{-1} = k^{-1} \cdot n^{-1}$. Consequently,
$$
\begin{gather}
(m \cdot k)(n \cdot k)^{-1} = (m \cdot k)(k^{-1} \cdot n^{-1}) = m \cdot n^{-1} \tag{2}
\end{gather}
$$

Conversely, suppose two pairs $(m_1, n_1)$ and $(m_2, n_2)$ define the same rational number, meaning $m_1 \cdot n_1^{-1} = m_2 \cdot n_2^{-1}$, or equivalently $m_1 n_2 = m_2 n_1$. If the pair $(m_1, n_1)$ has been reduced by factoring out common divisors so that $m_1$ and $n_1$ are relatively prime, Euclid's lemma dictates that $n_1$ must divide $n_2$. Thus, there exists an integer $k \in \mathbb{Z}$ such that $n_2 = k n_1$ and $m_2 = k m_1$. 

Therefore, two ordered pairs $(m_1, n_1)$ and $(m_2, n_2)$ represent the same rational number if and only if they are proportional, and every rational number admits a canonical representation as a ratio of relatively prime integers.

---
# Irrational Numbers
Although $\mathbb{Q}$ forms an ordered subfield of $\mathbb{R}$, it does not exhaust the points of the real line. Certain geometric lengths and algebraic roots cannot be expressed as the ratio of two integers, necessitating the classification of *irrational numbers*:

$$
\begin{gather}
\textbf{Definition: The Set of Irrational Numbers} \\[5mm]
\text{Real numbers that do not belong to the set of rational numbers } \mathbb{Q} \text{ are called irrational numbers.} \\[2mm]
\text{The set of irrational numbers is denoted by } \mathbb{R} \setminus \mathbb{Q} \text{ (or } \mathbb{I}\text{).}
\end{gather}
$$

The classical witness to the incompleteness of $\mathbb{Q}$—first discovered by the Pythagoreans when measuring the diagonal of a unit square—is the square root of two:

$$
\begin{gather}
\textbf{Proposition: Existence of Irrational Numbers} \\[5mm]
\text{There exists a unique positive real number } s \in \mathbb{R} \text{ satisfying } s^2 = 2, \\[2mm]
\text{denoted } \sqrt{2}, \text{ and this number does not belong to } \mathbb{Q}.
\end{gather}
$$
(see [[Proof that the Square Root of 2 is Irrational|proof]])

>[!info]+ Remark: Algebraic and Transcendental Numbers
>Real numbers can also be partitioned according to their relationship with polynomial equations. A number $x \in \mathbb{R}$ is called *algebraic* if it is a root of a non-zero polynomial equation with rational (or equivalently, integer) coefficients:
>$$
>\begin{gather}
>a_0 x^n + a_1 x^{n-1} + \dots + a_{n-1} x + a_n = 0 \tag{3}
>\end{gather}
>$$
>Every rational number $m/n$ is algebraic (being the root of $nx - m = 0$), as are radicals such as $\sqrt{2}$ (a root of $x^2 - 2 = 0$). Real numbers that are not roots of any polynomial with rational coefficients are called *transcendental*.

---
# The Principle of Archimedes
How do the discrete subsets $\mathbb{N}$, $\mathbb{Z}$, and $\mathbb{Q}$ distribute themselves across the continuous expanse of $\mathbb{R}$? The bridge connecting the order structure of these subsets to the completeness axiom of $\mathbb{R}$ is the *Principle of Archimedes*.
>[!info]+ Remark: Axiomatic Status of the Archimedean Property
>In certain alternative constructions of analysis, the Principle of Archimedes is postulated as an independent axiom. Within this repository, however, it is derived as a theorem directly from the Least Upper Bound (Completeness) Axiom.

Establishing the Principle of Archimedes first requires characterizing how upper and lower bounds behave within $\mathbb{N}$ and $\mathbb{Z}$:
$$
\begin{align}
& \textbf{Proposition: Bounds in } \mathbb{N} \text{ and } \mathbb{Z} \\[5mm]
& \hspace{0.5 in} \text{The sets } \mathbb{N} \text{ and } \mathbb{Z} \text{ satisfy the following bounding properties in } \mathbb{R}\text{:} \\[3.5mm]
& \hspace{0.5 in} 1. \ \text{Every nonempty subset of } \mathbb{N} \text{ that is bounded above possesses a maximal element.} \\[2mm]
& \hspace{0.5 in} 2. \ \text{The set of natural numbers } \mathbb{N} \text{ is not bounded above in } \mathbb{R}. \\[2mm]
& \hspace{0.5 in} 3. \ \text{Every nonempty subset of } \mathbb{Z} \text{ that is bounded above possesses a maximal element.} \\[2mm]
& \hspace{0.5 in} 4. \ \text{Every nonempty subset of } \mathbb{Z} \text{ that is bounded below possesses a minimal element.} \\[2mm]
& \hspace{0.5 in} 5. \ \text{The set of integers } \mathbb{Z} \text{ is unbounded both above and below in } \mathbb{R}.
\end{align}
$$
(see [[Proof of the Bounds in the Natural Numbers and Integers|proof]])

Because $\mathbb{Z}$ is unbounded in both directions and every bounded subset of $\mathbb{Z}$ achieves its extrema, any real number can be bracketed between consecutive integer multiples of an arbitrary positive step size $h$:
$$
\begin{gather}
\textbf{Theorem: The Principle of Archimedes} \\[5mm]
\text{For any fixed positive real number } h > 0 \text{ and any arbitrary real number } x \in \mathbb{R}, \\[2mm]
\text{there exists a unique integer } k \in \mathbb{Z} \text{ such that } (k - 1)h \le x < kh.
\end{gather}
$$
(see [[Proof of the Principle of Archimedes|proof]])

The Principle of Archimedes yields four foundational corollaries that govern limiting behavior, infinitesimal bounds, and the density of the rational numbers within $\mathbb{R}$:
$$
\begin{align}
& \textbf{Proposition: Corollaries to Archimedes' Principle} \\[5mm]
& \hspace{0.5 in} \text{The Archimedean structure of } \mathbb{R} \text{ guarantees the following properties:} \\[3.5mm]
& \hspace{0.5 in} 1. \ \text{For any } \varepsilon > 0, \text{ there exists a natural number } n \in \mathbb{N} \text{ such that } 0 < \frac{1}{n} < \varepsilon. \\[2mm]
& \hspace{0.5 in} 2. \ \text{If a real number } x \ge 0 \text{ satisfies } x < \frac{1}{n} \text{ for all } n \in \mathbb{N}, \text{ then } x = 0. \\[2mm]
& \hspace{0.5 in} 3. \ \text{Between any two distinct real numbers } a < b, \text{ there exists a rational number } r \in \mathbb{Q} \text{ such that } a < r < b. \\[2mm]
& \hspace{0.5 in} 4. \ \text{For any } x \in \mathbb{R}, \text{ there exists a unique integer } k \in \mathbb{Z} \text{ satisfying } k \le x < k + 1, \text{ where } \\[2mm]
& \hspace{0.7 in} [x] := k \text{ denotes the integer part (floor) of } x \text{ and } \{x\} := x - [x] \in [0, 1[ \text{ denotes its fractional part.}
\end{align}
$$
(see [[Proof of Archimedian Corollaries|proof]])

---
# Geometric Interpretation and Computations

### The Real Line and Coordinate Mapping
While axiomatic definitions provide logical rigor, modeling $\mathbb{R}$ geometrically as a continuous straight line $\mathbb{L}$ offers indispensable spatial intuition. By the axioms of Euclidean geometry, there exists a bijective mapping $f: \mathbb{L} \to \mathbb{R}$ pairing each geometric point $x \in \mathbb{L}$ with a unique real number $f(x)$, termed its *coordinate*. This bijection links the algebraic addition of real numbers to rigid parallel translations of the line: for any translation $T: \mathbb{L} \to \mathbb{L}$, there exists a constant displacement $t \in \mathbb{R}$ such that $f(T(x)) = f(x) + t$ for all $x \in \mathbb{L}$.

Fixing a reference point $x_0 \in \mathbb{L}$ as the origin ($f(x_0) = 0$) and a second distinct point $x_1 \in \mathbb{L}$ as the unit point ($f(x_1) = 1$) completely determines the coordinate axis. Orienting the ray from $x_0$ through $x_1$ from left to right establishes the positive direction. Repeatedly applying the unit translation $T$ (where $T(x_0) = x_1$) and its inverse $T^{-1}$ generates the geometric lattice of all integer coordinates $x_m = T^m(x_0)$ corresponding to $m \in \mathbb{Z}$.

To locate rational coordinates geometrically, one subdivides the unit segment into $n$ congruent parts using classical planar geometry:
$$
\begin{gather}
\textbf{Theorem: Thales' Theorem} \\[5mm]
\text{If a line is drawn parallel to one side of a triangle such that it intersects the other} \\[2mm]
\text{two sides at distinct points, it divides those two sides in the exact same ratio.}
\end{gather}
$$
(see [[Proof of Thales' Theorem|proof]])

Applying Thales' theorem partitions the unit interval into $n$ equal subintervals of length $1/n$; translating these subintervals along $\mathbb{L}$ constructs the point corresponding to every rational number $m/n \in \mathbb{Q}$.

What about points on $\mathbb{L}$ whose distances from the origin are incommensurable with the unit segment? Every point on $\mathbb{L}$ partitions the line into two rays, inducing a *Dedekind cut* of the rational numbers $\mathbb{Q}$ into two nonempty disjoint subsets: $X$ (rational coordinates to the left of the point) and $Y$ (rational coordinates to the right). Because $x \le y$ for all $x \in X$ and $y \in Y$, the Axiom of Completeness guarantees a real number $c \in \mathbb{R}$ satisfying $x \le c \le y$. Moreover, because $\mathbb{Q}$ is dense in $\mathbb{R}$ (Corollary 3 of Archimedes' Principle), no gap can exist between $\sup X$ and $\inf Y$; if $\sup X < \inf Y$, a rational number would lie strictly between them, belonging neither to $X$ nor to $Y$. Thus, $\sup X = \inf Y = c$, uniquely assigning an irrational coordinate to every remaining point on $\mathbb{L}$ and confirming that the real line possesses no gaps.

### Intervals, Neighborhoods, and Metric Structure
This geometric model motivates the standard topological and metric terminology on $\mathbb{R}$:
$$
\begin{gather}
\textbf{Definition: Numerical Intervals} \\[5mm]
\text{For real numbers } a, b \in \mathbb{R} \text{ with } a \le b, \text{ the fundamental intervals determined by endpoints } a \text{ and } b \text{ are:} \\[3.5mm]
\text{Open Interval: } ]a, b[ := \{x \in \mathbb{R} \mid a < x < b\} \\[2mm]
\text{Closed Interval: } [a, b] := \{x \in \mathbb{R} \mid a \le x \le b\} \\[2mm]
\text{Half-Open Intervals: } ]a, b] := \{x \in \mathbb{R} \mid a < x \le b\} \quad \text{and} \quad [a, b[ := \{x \in \mathbb{R} \mid a \le x < b\} \\[3.5mm]
\text{The length (or measure) of any interval } I \text{ with endpoints } a \text{ and } b \text{ is defined as } |I| := b - a.
\end{gather}
$$

>[!info]+ Remark: Unbounded Set Notation
>When a numerical set $X \subset \mathbb{R}$ is not bounded above, one writes $\sup X = +\infty$ (read "positive infinity"). Similarly, if $X$ is not bounded below, one writes $\inf X = -\infty$ (read "negative infinity").

Local analysis around a specific point relies on open intervals containing that point:
$$
\begin{gather}
\textbf{Definition: Neighborhood of a Point} \\[5mm]
\text{Any open interval containing a point } x \in \mathbb{R} \text{ is called a neighborhood of } x. \\[2mm]
\text{For any radius } \delta > 0, \text{ the symmetric open interval } ]x - \delta, x + \delta[ \text{ of length } 2\delta \\[2mm]
\text{centered at } x \text{ is called the } \delta\text{-neighborhood of } x.
\end{gather}
$$

To quantify the geometric distance between arbitrary points $x, y \in \mathbb{R}$ without specifying their relative order on the line, one introduces the absolute value function:
$$
\begin{gather}
\textbf{Definition: Absolute Value and Distance} \\[5mm]
\text{The absolute value of a real number } x \in \mathbb{R}, \text{ denoted } |x|, \text{ is defined as:} \\[3.5mm]
|x| := \begin{cases} x & \text{if } x \ge 0 \\ -x & \text{if } x < 0 \end{cases} \\[3.5mm]
\text{The metric distance between two points } x, y \in \mathbb{R} \text{ is defined as } d(x, y) := |x - y|.
\end{gather}
$$

The distance function $d(x, y) = |x - y|$ is strictly non-negative, vanishes if and only if $x = y$, and is symmetric ($|x - y| = |y - x|$). Furthermore, for any intermediate point $z \in \mathbb{R}$, the distance satisfies $|x - y| \le |x - z| + |z - y|$, which follows directly from the fundamental inequality governing absolute values:
$$
\begin{gather}
\textbf{Proposition: The Triangle Inequality} \\[5mm]
\text{For any real numbers } x, y \in \mathbb{R}, \text{ the absolute value of their sum satisfies:} \\[3.5mm]
|x + y| \le |x| + |y| \\[3.5mm]
\text{Equality holds if and only if } x \text{ and } y \text{ share the same sign (both non-negative or both non-positive).}
\end{gather}
$$
(see [[Proof of the Triangle Inequality|proof]])

---
# Errors in Computations
In empirical sciences and quantitative finance, physical measurements and numerical routines rarely yield exact real numbers; instead, they produce rational approximations. Conceptually, an exact real number $x \in \mathbb{R}$ can be viewed as the limit of a sequence of increasingly precise rational approximations. However, before operating on sequences of approximations, one must establish rigorous bounds on how approximation errors behave under elementary arithmetic operations.
$$
\begin{gather}
\textbf{Definition: Absolute and Relative Error} \\[5mm]
\text{Let } x \in \mathbb{R} \text{ be an exact quantity and } \tilde{x} \in \mathbb{R} \text{ be an approximation of } x. \\[3.5mm]
\text{Absolute Error: } \Delta(\tilde{x}) := |x - \tilde{x}| \\[2mm]
\text{Relative Error: } \delta(\tilde{x}) := \frac{\Delta(\tilde{x})}{|\tilde{x}|} = \frac{|x - \tilde{x}|}{|\tilde{x}|} \quad (\text{for } \tilde{x} \ne 0)
\end{gather}
$$

Because the true value $x$ is generally unknown in empirical settings, the exact errors $\Delta(\tilde{x})$ and $\delta(\tilde{x})$ are likewise unknown. Instead, an analyst works with known upper bounds $\Delta$ and $\delta$ satisfying $\Delta(\tilde{x}) \le \Delta$ and $\delta(\tilde{x}) \le \delta$. In applied contexts, these upper bounds $\Delta$ and $\delta$ are themselves referred to as the *limiting absolute* and *relative errors*.

>[!info]+ Remark: Confidence Interval Notation for Errors
>Writing $x = \tilde{x} \pm \Delta$ signifies that the true value $x$ is guaranteed to reside within the closed interval $[\tilde{x} - \Delta, \tilde{x} + \Delta]$, or equivalently, $\tilde{x} - \Delta \le x \le \tilde{x} + \Delta$.

>[!example]- Example: Precision in Fundamental Physical Constants
>Empirical measurements in the physical sciences are expressed in the form $x = \tilde{x} \pm \Delta$ because instrumental resolution is finite and achieving extreme precision is often economically or physically prohibitive. Consider the following historical benchmark measurements of physical constants:
>- **Gravitational Constant:** $G = (6.67259 \pm 0.00085) \cdot 10^{-11}\text{ N}\cdot\text{m}^2/\text{kg}^2$ (Relative error: $\delta \approx 1.3 \cdot 10^{-4}$)
>- **Speed of Light in Vacuum:** $c = 299\,792\,458\text{ m/s}$ (Exact by definition of the meter; $\delta = 0$)
>- **Planck's Constant:** $h = (6.6260755 \pm 0.0000040) \cdot 10^{-34}\text{ J}\cdot\text{s}$ (Relative error: $\delta \approx 6.0 \cdot 10^{-7}$)
>- **Elementary Charge:** $e = (1.60217733 \pm 0.00000049) \cdot 10^{-19}\text{ C}$ (Relative error: $\delta \approx 3.1 \cdot 10^{-7}$)
>- **Electron Rest Mass:** $m_e = (9.1093897 \pm 0.0000054) \cdot 10^{-31}\text{ kg}$ (Relative error: $\delta \approx 5.9 \cdot 10^{-7}$)

When arithmetic operations are performed on approximate quantities $\tilde{x}$ and $\tilde{y}$, the resulting uncertainties compound according to the following propagation bounds:
$$
\begin{gather}
\textbf{Proposition: Propagation of Absolute Errors} \\[5mm]
\text{Let } \tilde{x} \text{ and } \tilde{y} \text{ be approximations of } x \text{ and } y \text{ with absolute errors } \Delta(\tilde{x}) \text{ and } \Delta(\tilde{y}). \text{ Then:} \\[3.5mm]
\Delta(\tilde{x} \pm \tilde{y}) \le \Delta(\tilde{x}) + \Delta(\tilde{y}) \\[2mm]
\Delta(\tilde{x} \cdot \tilde{y}) \le |\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x}) + \Delta(\tilde{x})\Delta(\tilde{y}) \\[2mm]
\Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \le \frac{|\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x})}{\tilde{y}^2 (1 - \delta(\tilde{y}))} \quad (\text{provided } \tilde{y} \ne 0 \text{ and } \delta(\tilde{y}) < 1)
\end{gather}
$$
(see [[Proof of Error Propagation Methods|proof]])

>[!info]+ Remark: Propagation of Relative Errors and Numerical Instability
>Dividing the absolute error bounds by the magnitude of the corresponding approximate results yields the exact upper bounds for relative error propagation:
>$$
>\begin{gather}
>\delta(\tilde{x} \pm \tilde{y}) \le \frac{\Delta(\tilde{x}) + \Delta(\tilde{y})}{|\tilde{x} \pm \tilde{y}|} \\[2mm]
>\delta(\tilde{x} \cdot \tilde{y}) \le \delta(\tilde{x}) + \delta(\tilde{y}) + \delta(\tilde{x})\delta(\tilde{y}) \\[2mm]
>\delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \le \frac{\delta(\tilde{x}) + \delta(\tilde{y})}{1 - \delta(\tilde{y})} \tag{4}
>\end{gather}
>$$
>When the approximations are highly precise ($\delta(\tilde{x}), \delta(\tilde{y}) \ll 1$), higher-order terms satisfy $\delta(\tilde{x})\delta(\tilde{y}) \approx 0$ and $1 - \delta(\tilde{y}) \approx 1$, yielding the linearized first-order approximations commonly used in engineering and numerical analysis:
>$$
>\begin{gather}
>\Delta(\tilde{x} \cdot \tilde{y}) \approx |\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x}) \quad \text{and} \quad \Delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \approx \frac{|\tilde{x}|\Delta(\tilde{y}) + |\tilde{y}|\Delta(\tilde{x})}{\tilde{y}^2} \\[2mm]
>\delta(\tilde{x} \cdot \tilde{y}) \approx \delta(\tilde{x}) + \delta(\tilde{y}) \quad \text{and} \quad \delta\left(\frac{\tilde{x}}{\tilde{y}}\right) \approx \delta(\tilde{x}) + \delta(\tilde{y}) \tag{5}
>\end{gather}
>$$
>The exact bounds in step 4 expose two critical sources of numerical instability in scientific computing:
>1. **Catastrophic Cancellation:** In the first inequality of step 4, if $\tilde{x}$ and $\tilde{y}$ are nearly equal in magnitude and subtracted (or opposite in sign and added), the denominator $|\tilde{x} \pm \tilde{y}|$ approaches zero, causing the relative error $\delta(\tilde{x} \pm \tilde{y})$ to explode.
>2. **Ill-Conditioned Division:** In the quotient bound, dividing by a quantity $\tilde{y}$ near zero or with poor relative precision ($\delta(\tilde{y}) \to 1$) amplifies both the absolute and relative errors dramatically.

>[!question]- Application: Signal Amplification and Measurement Aggregation
>Suppose an individual measures their height using an instrument with an absolute precision bound of $\Delta = 0.5\text{ cm}$. A first measurement barefoot yields $H_1 = (200.0 \pm 0.5)\text{ cm}$, and a second measurement standing on a single sheet of paper yields $H_2 = (199.8 \pm 0.5)\text{ cm}$. Attempting to deduce the thickness of the paper via direct subtraction $H_2 - H_1$ is futile: the combined absolute error bound is $0.5 + 0.5 = 1.0\text{ cm}$, yielding $(-0.2 \pm 1.0)\text{ cm}$ and indicating only that the sheet is at most $0.8\text{ cm}$ thick—a classic manifestation of catastrophic cancellation where measurement noise completely swamps the signal.
>
>Suppose instead that the same crude instrument ($\Delta = 0.5\text{ cm}$) is used to measure a stack of $1\,000$ identical sheets of paper, yielding a total thickness of $L = (20.0 \pm 0.5)\text{ cm}$. Dividing by the exact integer $1\,000$ scales both the estimate and the absolute error bound linearly, revealing the thickness of a single sheet to be $(0.0200 \pm 0.0005)\text{ cm}$, or $(0.200 \pm 0.005)\text{ mm}$. By aggregating $N = 1\,000$ observations before dividing, the relative error is compressed to $\delta = 0.005 / 0.200 = 0.025$ ($2.5\%$). This principle—coherent signal accumulation relative to bounded or uncorrelated noise—forms the mathematical basis for extracting weak periodic signals from white noise in quantitative time-series analysis.

---
# Application: Positional Computation System
Although the decimal system (base $10$) is the cultural standard for human arithmetic, modern computing architectures rely on alternative positional bases—most notably binary (base $2$), octal (base $8$), and hexadecimal (base $16$). The Principle of Archimedes guarantees that any positive real number can be systematically encoded and approximated to arbitrary precision in any integer base $q > 1$.
$$
\begin{gather}
\textbf{Lemma: Base Order Bounds} \\[5mm]
\text{For any fixed natural base } q \in \mathbb{N} \text{ with } q > 1 \text{ and any positive real number } x > 0, \\[2mm]
\text{there exists a unique integer } p \in \mathbb{Z} \text{ such that } q^p \le x < q^{p+1}.
\end{gather}
$$
(see [[Proof of the Positional Computational System|proof]])

For a fixed base $q > 1$ and an arbitrary $x > 0$, this lemma isolates the leading power of $q$ bounding $x$ from below:
$$
\begin{gather}
q^p \le x < q^{p+1} \tag{6}
\end{gather}
$$

$$
\begin{gather}
\textbf{Definition: Order of a Real Number in Base } q \\[5mm]
\text{The unique integer } p \in \mathbb{Z} \text{ satisfying the inequality of step 6 is called} \\[2mm]
\text{the order (or exponent) of the number } x \text{ in the base } q.
\end{gather}
$$

Applying the Principle of Archimedes to $x$ with step size $h = q^p$ yields a unique integer $\alpha_p$ satisfying
$$
\begin{gather}
\alpha_p q^p \le x < (\alpha_p + 1)q^p = \alpha_p q^p + q^p \tag{7}
\end{gather}
$$

Combining step 6 and step 7 restricts the leading digit to $\alpha_p \in \{1, 2, \dots, q - 1\}$. Next, applying the Principle of Archimedes to the remainder $x - \alpha_p q^p \in [0, q^p[$ with step size $h = q^{p-1}$ determines a unique digit $\alpha_{p-1} \in \{0, 1, \dots, q - 1\}$ such that
$$
\begin{gather}
\alpha_p q^p + \alpha_{p-1} q^{p-1} \le x < \alpha_p q^p + \alpha_{p-1} q^{p-1} + q^{p-1} \tag{8}
\end{gather}
$$

Proceeding inductively for $n$ steps generates a finite sequence of digits $\alpha_p, \alpha_{p-1}, \dots, \alpha_{p-n} \in \{0, 1, \dots, q - 1\}$ (with $\alpha_p \ne 0$) satisfying
$$
\begin{gather}
\alpha_p q^p + \alpha_{p-1} q^{p-1} + \dots + \alpha_{p-n} q^{p-n} \le x < \alpha_p q^p + \alpha_{p-1} q^{p-1} + \dots + \alpha_{p-n} q^{p-n} + q^{p-n} \tag{9}
\end{gather}
$$

Applying the Principle of Archimedes once more with step size $q^{p-n-1}$ uniquely determines $\alpha_{p-n-1} \in \{0, 1, \dots, q - 1\}$ such that
$$
\begin{gather}
\sum_{j=0}^{n+1} \alpha_{p-j} q^{p-j} \le x < \sum_{j=0}^{n+1} \alpha_{p-j} q^{p-j} + q^{p-n-1} \tag{10}
\end{gather}
$$

This recursive algorithm associates each positive real number $x > 0$ with an infinite sequence of digits $\{\alpha_{p-n}\}_{n=0}^\infty$ and a corresponding monotonic sequence of lower rational approximations:
$$
\begin{gather}
r_n := \alpha_p q^p + \alpha_{p-1} q^{p-1} + \dots + \alpha_{p-n} q^{p-n} = \sum_{j=0}^n \alpha_{p-j} q^{p-j} \tag{11}
\end{gather}
$$

satisfying the tight error bound:
$$
\begin{gather}
r_n \le x < r_n + \frac{1}{q^{n-p}} \tag{12}
\end{gather}
$$
(see [[Proof of Step 11|proof]])

To encode both the digit sequence $\{\alpha_{p-n}\}$ and the order $p$ into a single symbolic string, a radix point (period or comma) is inserted immediately after the units digit $\alpha_0$ when $p \ge 0$ (yielding $\alpha_p \alpha_{p-1} \dots \alpha_0 . \alpha_{-1} \alpha_{-2} \dots$). When $p < 0$, one prefixes $|p|$ zeros to the left of $\alpha_p$ and places the radix point immediately after the first zero (yielding $0 . 0 \dots 0 \alpha_p \alpha_{p-1} \dots$).

>[!example]- Example: Decimal and Binary Positional Expansions
>In the standard decimal system ($q = 10$), positional notation encodes powers of $10$:
>$$
>\begin{gather}
>123.45_{(10)} := 1 \cdot 10^2 + 2 \cdot 10^1 + 3 \cdot 10^0 + 4 \cdot 10^{-1} + 5 \cdot 10^{-2} \tag{13}
>\end{gather}
>$$
>For a number of negative order ($p = -3$), leading zeros mark the displacement from the radix point:
>$$
>\begin{gather}
>0.00123_{(10)} := 1 \cdot 10^{-3} + 2 \cdot 10^{-4} + 3 \cdot 10^{-5} \tag{14}
>\end{gather}
>$$
>In the binary system ($q = 2$), the alphabet is restricted to $\{0, 1\}$, and each rank represents a power of $2$:
>$$
>\begin{gather}
>1000.001_{(2)} := 1 \cdot 2^3 + 0 \cdot 2^2 + 0 \cdot 2^1 + 0 \cdot 2^0 + 0 \cdot 2^{-1} + 0 \cdot 2^{-2} + 1 \cdot 2^{-3} \tag{15}
>\end{gather}
>$$

>[!info]- Remark: Uniqueness of $q$-ary Expansions and the Exclusion of Trailing $(q-1)$ Tails
>By virtue of the strict upper inequality in step 12, the extraction algorithm can never produce a digit sequence in which $\alpha_{p-n} = q - 1$ for all $n > k$. Indeed, if $\alpha_{p-j} = q - 1$ for every $j \in \{k + 1, \dots, n\}$, the geometric sum identity yields
>$$
>\begin{gather}
>r_n = r_k + \sum_{j=k+1}^n (q - 1)q^{p-j} = r_k + \frac{1}{q^{k-p}} - \frac{1}{q^{n-p}} \tag{16}
>\end{gather}
>$$
>Substituting step 16 into step 12 would require that for all $n > k$,
>$$
>\begin{gather}
>r_k + \frac{1}{q^{k-p}} - \frac{1}{q^{n-p}} \le x < r_k + \frac{1}{q^{k-p}} \implies 0 < r_k + \frac{1}{q^{k-p}} - x \le \frac{1}{q^{n-p}} \tag{17}
>\end{gather}
>$$
>By Corollary 2 of the Principle of Archimedes, no strictly positive quantity can be bounded above by $q^{-(n-p)}$ for all $n > k$, yielding a contradiction.
>
>Conversely, if a formal $q$-ary symbol $\alpha_p \dots \alpha_0 . \alpha_{-1} \dots$ contains digits smaller than $q - 1$ at arbitrarily large indices, then for any step $k$ there exists $n > k$ where at least one intermediate digit is at most $q - 2$, ensuring that
>$$
>\begin{gather}
>r_n < r_k + \frac{1}{q^{k-p}} - \frac{1}{q^{n-p}} \iff r_n + \frac{1}{q^{n-p}} < r_k + \frac{1}{q^{k-p}} \tag{18}
>\end{gather}
>$$
>Consequently, the lower and upper approximations form a nested hierarchy of bounds:
>$$
>\begin{gather}
>r_0 \le r_1 \le \dots \le r_n \le \dots < r_n + \frac{1}{q^{n-p}} \le \dots \le r_1 + \frac{1}{q^{1-p}} \le r_0 + \frac{1}{q^{-p}} \tag{19}
>\end{gather}
>$$
>By the Axiom of Completeness, setting $x := \sup_{n} r_n = \inf_{n} (r_n + q^{-(n-p)})$ recovers the unique real number $x > 0$ whose algorithmic $q$-ary expansion matches the given symbol.

Extending this mapping by assigning $0.00\dots$ to $0$ and prefixing a minus sign ($-$) to the expansion of $|x|$ for $x < 0$ establishes a bijective correspondence between $\mathbb{R}$ and the set of admissible $q$-ary positional representations. The individual numbers $\alpha_k \in \{0, 1, \dots, q - 1\}$ are called the *digits* of the representation, and the index of each digit relative to the radix point is termed its *rank*.

>[!question]+ Application: Digital Computer Arithmetic and Floating-Point Architecture
>Digital microprocessors implement arithmetic using the binary positional system ($q = 2$), mapping the digits $0$ and $1$ to low and high voltage states, while higher-level memory addressing frequently employs octal ($q = 8$) or hexadecimal ($q = 16$) notation as compact human-readable representations of binary words. Under the IEEE 754 floating-point standard, a real number $x$ is stored in memory by encoding its sign bit, its shifted binary order $p$ (the *exponent*), and a finite truncation of its leading binary digits $\alpha_{p-1}\dots\alpha_{p-m}$ (the *mantissa* or *significand*). Because hardware registers hold only a finite number of bits $m$, numbers with infinite binary expansions—including simple decimal fractions such as $0.1_{(10)} = 0.0001100110011\dots_{(2)}$—incur an unavoidable representation error bounded by step 12, known in numerical analysis as *machine epsilon*.

---
# Additional Useful Facts

$$
\begin{gather}
\textbf{Theorem: Isomorphism and Categoricity of } \mathbb{R} \\[5mm]
\text{Any two complete linearly ordered fields } (\mathbb{R}, +, \cdot, \le) \text{ and } (\mathbb{R}', +', \cdot', \le') \\[2mm]
\text{are isomorphic via a unique order-preserving field isomorphism.}
\end{gather}
$$
(see [[Proof of Isomorphism and Categoricity in the Real Numbers|proof]])
This theorem establishes the categorical closure of the axiomatic definition of $\mathbb{R}$. Regardless of whether the real numbers are constructed via Cauchy sequences of rationals, Dedekind cuts, or infinite decimal expansions, all realizations of a complete ordered field are structurally identical up to a unique isomorphism.
$$
\begin{gather}
\textbf{Theorem: Dedekind's Cut Principle and Completeness Equivalence} \\[5mm]
\text{In an ordered field } \mathbb{F}, \text{ the Least Upper Bound Axiom holds if and only if for every partition} \\[2mm]
\text{of } \mathbb{F} \text{ into two nonempty disjoint subsets } X \text{ and } Y \text{ satisfying } x \le y \text{ for all } x \in X, y \in Y, \\[2mm]
\text{there exists a unique cut element } c \in \mathbb{F} \text{ such that } x \le c \le y \text{ for all } x \in X \text{ and } y \in Y.
\end{gather}
$$
(see [[Proof of Dedekind's Cut Theorem and Complete Equivalence|proof]])
Dedekind's principle provides an equivalent geometric formulation of completeness, characterizing the continuity of the real line through the absence of gaps in any order-preserving partition.
$$
\begin{gather}
\textbf{Proposition: Monotonicity and Ordering of Extrema} \\[5mm]
\text{Let } A, B \subset \mathbb{R} \text{ be nonempty bounded subsets of } \mathbb{R}. \text{ If } A \subset B, \text{ then:} \\[3.5mm]
\sup A \le \sup B \quad \text{and} \quad \inf A \ge \inf B \\[3.5mm]
\text{Furthermore, if } X, Y \subset \mathbb{R} \text{ are nonempty sets such that } x \le y \text{ for all } x \in X \text{ and } y \in Y, \text{ then} \\[3.5mm]
\sup X \le \inf Y \\[3.5mm]
\text{If, in addition, } X \cup Y = \mathbb{R} \text{ (or } \forall \varepsilon > 0 \ \exists x \in X, y \in Y \text{ with } y - x < \varepsilon\text{), then } \sup X = \inf Y.
\end{gather}
$$
(see [[Proof of Monotonicity and Ordering of Extrema|proof]])
These inequalities govern the behavior of suprema and infima under set inclusion and order separation, serving as a workhorse for bounding approximations and integral partitions.

$$
\begin{gather}
\textbf{Proposition: Algebraic Operations on Bounded Sets} \\[5mm]
\text{For nonempty bounded subsets } A, B \subset \mathbb{R}, \text{ define the Minkowski sum } A + B := \{a + b \mid a \in A, b \in B\} \\[2mm]
\text{and the Minkowski product } A \cdot B := \{a \cdot b \mid a \in A, b \in B\}. \text{ Then:} \\[3.5mm]
\sup(A + B) = \sup A + \sup B \quad \text{and} \quad \inf(A + B) = \inf A + \inf B \\[3.5mm]
\text{If } A \text{ and } B \text{ consist exclusively of non-negative real numbers } (A, B \subset \mathbb{R}_{\ge 0}), \text{ then:} \\[3.5mm]
\sup(A \cdot B) = (\sup A) \cdot (\sup B) \quad \text{and} \quad \inf(A \cdot B) = (\inf A) \cdot (\inf B)
\end{gather}
$$
These identities establish the calculus of extrema over Minkowski set sums and products, which are utilized extensively in variational analysis and functional optimization.

$$
\begin{gather}
\textbf{Proposition: Bernoulli's Inequality} \\[5mm]
\text{For every real number } x > -1 \text{ and every natural number } n \in \mathbb{N}, \\[3.5mm]
(1 + x)^n \ge 1 + nx \\[3.5mm]
\text{Equality holds if and only if } n = 1 \text{ or } x = 0.
\end{gather}
$$
(see [[Proof of Bernoulli's Inequality|proof]])

$$
\begin{align}
& \textbf{Proposition: Existence of Unique } n\textbf{-th Roots and Rational Exponentiation} \\[5mm]
& \hspace{0.5 in} \text{For any } n \in \mathbb{N} \text{ and any } a > 0, \text{ the equation } x^n = a \text{ admits a unique positive root } x = \sqrt[n]{a} =: a^{1/n}. \\[2mm]
& \hspace{0.5 in} \text{Furthermore, for all } a, b > 0, \ m, n \in \mathbb{N}, \text{ and } r_1, r_2 \in \mathbb{Q}, \text{ the following laws hold:} \\[3.5mm]
& \hspace{0.5 in} 1. \ \sqrt[n]{ab} = \sqrt[n]{a} \cdot \sqrt[n]{b} \quad \text{and} \quad \sqrt[n]{\sqrt[m]{a}} = \sqrt[nm]{a}. \\[2mm]
& \hspace{0.5 in} 2. \ (a^{1/n})^m = (a^m)^{1/n} =: a^{m/n} \quad \text{and} \quad a^{1/n} \cdot a^{1/m} = a^{\frac{1}{n} + \frac{1}{m}}. \\[2mm]
& \hspace{0.5 in} 3. \ a^{r_1} \cdot a^{r_2} = a^{r_1 + r_2}, \quad (a^{r_1})^{r_2} = a^{r_1 r_2}, \quad \text{and} \quad (ab)^{r_1} = a^{r_1} b^{r_1}.
\end{align}
$$
(see [[Proof of the Rules of Rational Expressions|proof]])
This proposition extends integer exponentiation to all rational exponents $r \in \mathbb{Q}$, providing the algebraic foundation required to define continuous exponential functions on $\mathbb{R}$.

$$
\begin{gather}
\textbf{Proposition: Non-Archimedean Ordered Fields} \\[5mm]
\text{The field of rational functions } \mathbb{Q}(x) \text{ equipped with the ordering defined by positive leading} \\[2mm]
\text{coefficients at highest degree forms a linearly ordered field that is non-Archimedean.}
\end{gather}
$$
(see [[Proof of Non-Archimedean Ordering Fields|proof]])

$$
\begin{gather}
\textbf{Lemma: Von Neumann Ordinal Embeddings} \\[5mm]
\text{The set-theoretic successor operation } x^+ := x \cup \{x\} \text{ on Von Neumann ordinals} \\[2mm]
\text{satisfies strict injectivity and the well-ordering minimal element principle under set inclusion.}
\end{gather}
$$
(see [[Proof of Von-Neumann Ordinal Embeddings|proof]])

$$
\begin{gather}
\textbf{Lemma: The Euclidean Algorithm and Bézout's Identity} \\[5mm]
\text{Let } m, n \in \mathbb{N} \text{ with } m > n. \text{ Their greatest common divisor } d = \gcd(m, n) \in \mathbb{N} \text{ can be computed} \\[2mm]
\text{in finitely many steps via successive divisions with strictly decreasing non-negative remainders:} \\[3.5mm]
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
(see [[Proof that Euclid's Algorithm Works|proof]])

$$
\begin{gather}
\textbf{Lemma: Properties of Order-Preserving Field Homomorphisms} \\[5mm]
\text{Any non-trivial order-preserving ring homomorphism } f: \mathbb{R} \to \mathbb{R}' \text{ between complete ordered fields} \\[2mm]
\text{maps } 0 \mapsto 0' \text{ and } 1 \mapsto 1', \text{ preserves positive rationals, and restricts to an order isomorphism on } \mathbb{Q}.
\end{gather}
$$
(see [[Proof of Properties of Order-Preserving Homomorphisms|proof]])
