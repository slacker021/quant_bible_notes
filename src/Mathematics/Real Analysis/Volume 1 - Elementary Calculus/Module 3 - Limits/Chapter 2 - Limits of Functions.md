---
dg-publish: true
---
# Fundamentals of Functional Limits
The formalization of the limit of a function translates the intuitive concept of local approximation into rigorous metric and topological constraints. The properties of the limits of functions are analogous to that of the [[Chapter 1 - Limits of Sequences|limits of sequences]]. Like the limits of sequences, it is crucial for formalizing the behavior of various operators and phenomena used in higher levels of analysis. Ergo, both limits of sequences and limits of functions serve as the basis for Calculus. 

It was after the invention of Calculus, which took place some time after the 17th century, that a free development of the subject took place in the 18th century. Mathematicians like the Bernoulli brothers and Euler were focused on exploiting the new-found powers of limits, without much regard to the validity of their proofs. It would be in the 19th century when the landscape of mathematics was flipped on its head, being characterized by a new age of rigor. This movement was characterized by a return to the abstract foundations of mathematics, being spearheaded by *Augustin Louis-Cauchy*. A former military engineer who later became a mathematics professor in Paris, Cauchy took the definition of a limit that was provided by *Isaac Newton* and made it more precise. 

The reader may think of this particular chapter as paying homage to that era of mathematical discovery. Therefore, this may be the most important chapter in this volume of Real Analysis. The reader is encouraged give plenty of attention to this page as the concept of a limit is rather difficult to understand at first glance. 

### The Limit Point Precondition
Prior to evaluating the limiting behavior of a function at a point, the underlying domain must permit an infinite sequence of distinct points to approach the target value arbitrarily closely. If this topological condition fails, the concept of a limit becomes mathematically vacuous: 
$$
\begin{gather} \textbf{Definition: Limit Point (Accumulation Point) of a Domain} \\[5mm] \text{Let } E \subseteq \mathbb{R}. \text{ A point } a \in \mathbb{R} \text{ is called a limit point (or accumulation point) of } E, \\[2mm] \text{denoted } a \in E', \text{ if every open neighborhood of } a \text{ contains at least one point of } E \text{ distinct from } a\text{:} \\[3.5mm] \forall \delta > 0, \quad \mathring{U}_\delta(a) \cap E \neq \emptyset \\[3.5mm] \text{where } \mathring{U}_\delta(a) := (a - \delta, a + \delta) \setminus \{a\} \text{ denotes the punctured (deleted) } \delta\text{-neighborhood of } a. \end{gather}
$$

It is only with the definition of a *limit point* that the actual definition of a limit, which is based on the *Caucy Criterion* mentioned in the last chapter, can be provided:
$$
\begin{gather} \textbf{Definition: The Limit of a Function (Cauchy Criterion)} \\[5mm] \text{Let } f: E \to \mathbb{R} \text{ be a real-valued function, and let } a \in E' \text{ be an accumulation point of } E. \\[2mm] \text{The function } f \text{ tends to a real limit } A \in \mathbb{R} \text{ as } x \text{ tends to } a \text{ within } E, \text{ denoted} \\[3.5mm] \lim_{E \ni x \to a} f(x) = A \quad (\text{or simply } \lim_{x \to a} f(x) = A), \\[3.5mm] \text{if for every positive error tolerance } \varepsilon > 0, \text{ there exists a corresponding distance } \delta > 0 \text{ such that} \\[2mm] \text{for all } x \in E, \text{ the condition } 0 < |x - a| < \delta \text{ strictly guarantees that } |f(x) - A| < \varepsilon\text{:} \\[3.5mm] \forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(0 < |x - a| < \delta \implies |f(x) - A| < \varepsilon\big). \\[3.5mm] \text{Topologically, for every neighborhood } V(A) \text{ of } A, \text{ there exists a punctured neighborhood } \mathring{U}_E(a) \\[2mm] \text{such that the direct functional image satisfies } f(\mathring{U}_E(a)) \subseteq V(A). \end{gather}
$$

>[!danger]+ Intuition: Punctured Neighborhoods and the Elimination of Vacuous Truth
>The requirement that $a$ be an accumulation point ($a \in E'$) is indispensable. If $a$ were an isolated point of $E$, there would exist some radius $\delta_0 > 0$ such that $\mathring{U}_{\delta_0}(a) \cap E = \emptyset$. Under that failure, the antecedent $0 < |x - a| < \delta_0$ would be universally false for all $x \in E$, rendering the implication vacuously true for *any arbitrary real number* $A \in \mathbb{R}$. Enforcing $a \in E'$ guarantees that the punctured neighborhood contains actual points of $E$, preserving the uniqueness of the limit. Furthermore, the definition explicitly evaluates the behavior of $f(x)$ on the punctured domain $\mathring{U}_E(a)$; the value of $f(a)$, or whether $f$ is even defined at $a$, exerts zero influence on the existence or value of the limit.

$$
\begin{gather} \textbf{Lemma: The Punctured Neighborhood Identity Principle} \\[5mm] \text{Let } f, g: E \to \mathbb{R} \text{ and let } a \in E'. \text{ If there exists a radius } \delta_0 > 0 \text{ such that} \\[3.5mm] f(x) = g(x) \quad \forall x \in \mathring{U}_{\delta_0}(a) \cap E, \tag{1} \\[3.5mm] \text{then } \lim_{E \ni x \to a} f(x) \text{ exists if and only if } \lim_{E \ni x \to a} g(x) \text{ exists, in which case:} \\[3.5mm] \lim_{E \ni x \to a} f(x) = \lim_{E \ni x \to a} g(x). \end{gather}
$$
(see [[Proof of the Punctured Neighborhood Identity Principle]])

$$
\begin{gather} \textbf{Theorem: Direct Substitution Property for Algebraic Functions} \\[5mm] \text{1. If } P(x) = \sum_{k=0}^n c_k x^k \text{ is a polynomial, then for any } a \in \mathbb{R}\text{:} \\[3.5mm] \lim_{x \to a} P(x) = P(a). \\[3.5mm] \text{2. If } R(x) = \frac{P(x)}{Q(x)} \text{ is a rational function and } Q(a) \neq 0, \text{ then:} \\[3.5mm] \lim_{x \to a} R(x) = \frac{P(a)}{Q(a)} = R(a). \\[3.5mm] \text{3. For any natural root } n \in \mathbb{N}, \text{ if } a > 0 \text{ (or } a \in \mathbb{R} \text{ when } n \text{ is odd):} \\[3.5mm] \lim_{x \to a} \sqrt[n]{x} = \sqrt[n]{a}. \end{gather}
$$
(see [[Proof of the Direct Substitution Property for Algebraic Functions]])

>[!info]+ Remark: Direct Substitution Shall Come First
>When evaluating the limit of a function, *direct substitution* shall be the very first method of evaluation that is performed. It is a rather simple method, after all, that does not take much effort to execute. Do this before trying out other means of functional limit evaluation. 

>[!example]- Example: Indeterminate Cancellation in Difference Quotients
>Evaluating the limit of $f(x) = \frac{x^2 - 9}{x - 3}$ as $x \to 3$ yields the indeterminate form $\frac{0}{0}$. The function $f$ is undefined at $x = 3$. However, for any $x \in \mathring{U}_1(3) = (2, 4) \setminus \{3\}$, the algebraic factorization yields:
>$$ f(x) = \frac{(x - 3)(x + 3)}{x - 3} = x + 3 =: g(x). \tag{2} $$
>Because $f(x) = g(x)$ for all $x \neq 3$, the Punctured Neighborhood Identity Principle and the Direct Substitution Property establish that:
>$$ \lim_{x \to 3} \frac{x^2 - 9}{x - 3} = \lim_{x \to 3} (x + 3) = 3 + 3 = 6. \tag{3} $$

---
# Directional and Infinite Limits
The definition of a limit of a function, to be more precise, needs to be evaluated from two "sides"—one from the left and another at the right. The existence of the limit of a function, assuming each side exists and has the identical numerical value, is a combination of both sides:
$$
\begin{gather} \textbf{Definition: One-Sided Limits} \\[5mm] \text{1. Left-Hand Limit: Let } a \text{ be a limit point of } E \cap (-\infty, a). \text{ Then } \lim_{x \to a^-} f(x) = A \iff \\[3.5mm] \forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(a - \delta < x < a \implies |f(x) - A| < \varepsilon\big). \\[3.5mm] \text{2. Right-Hand Limit: Let } a \text{ be a limit point of } E \cap (a, +\infty). \text{ Then } \lim_{x \to a^+} f(x) = A \iff \\[3.5mm] \forall \varepsilon > 0, \ \exists \delta > 0, \ \forall x \in E \ \big(a < x < a + \delta \implies |f(x) - A| < \varepsilon\big). \end{gather}
$$
It should be noted that it is possible for one side of the limit to exist but the other to not. However, this would mean that the two-sided limit definition will not hold:
$$
\begin{gather} \textbf{Theorem: The Two-Sided and One-Sided Limit Equivalence} \\[5mm] \text{Let } a \text{ be an accumulation point of both } E \cap (-\infty, a) \text{ and } E \cap (a, +\infty). \\[2mm] \text{A function } f: E \to \mathbb{R} \text{ possesses a two-sided limit } \lim_{x \to a} f(x) = A \text{ if and only if} \\[2mm] \text{both directional limits exist and coincide with } A\text{:} \\[3.5mm] \lim_{x \to a} f(x) = A \iff \left(\lim_{x \to a^-} f(x) = A \quad \wedge \quad \lim_{x \to a^+} f(x) = A\right). \end{gather}
$$
(see [[Proof of the Equivalence of Two-Sided and One-Sided Limits]])

Like with the limits of sequences, it is possible to evaluate the asymptotic behavior of a function should the limit become arbitrarily larger or smaller:
$$
\begin{gather} \textbf{Definition: Limits at Infinity} \\[5mm] \text{1. Positive Infinity: If } E \text{ is unbounded above, } \lim_{x \to +\infty} f(x) = A \iff \\[3.5mm] \forall \varepsilon > 0, \ \exists M \in \mathbb{R}, \ \forall x \in E \ \big(x > M \implies |f(x) - A| < \varepsilon\big). \\[3.5mm] \text{2. Negative Infinity: If } E \text{ is unbounded below, } \lim_{x \to -\infty} f(x) = A \iff \\[3.5mm] \forall \varepsilon > 0, \ \exists M \in \mathbb{R}, \ \forall x \in E \ \big(x < M \implies |f(x) - A| < \varepsilon\big). \\[3.5mm] \text{3. Unsigned Infinity: If } E \text{ is unbounded in magnitude, } \lim_{x \to \infty} f(x) = A \iff \\[3.5mm] \forall \varepsilon > 0, \ \exists M \in \mathbb{R}, \ \forall x \in E \ \big(|x| > M \implies |f(x) - A| < \varepsilon\big). \end{gather}
$$

Another thing that makes the limits of functions comparable to the limits of sequences is that they may not exist but the behavior grows infinitely large. Although non-existent, its behavior can still be studied:
$$
\begin{gather} \textbf{Definition: Infinite Limits (Functional Divergence)} \\[5mm] \text{Let } a \in E'. \text{ The function } f \text{ diverges to positive infinity, negative infinity, or unsigned infinity:} \\[3.5mm] \lim_{x \to a} f(x) = +\infty \iff \forall C \in \mathbb{R}, \ \exists \delta > 0, \ \forall x \in E \ \big(0 < |x - a| < \delta \implies f(x) > C\big). \\[3.5mm] \lim_{x \to a} f(x) = -\infty \iff \forall C \in \mathbb{R}, \ \exists \delta > 0, \ \forall x \in E \ \big(0 < |x - a| < \delta \implies f(x) < C\big). \\[3.5mm] \lim_{x \to a} f(x) = \infty \iff \forall C \in \mathbb{R}, \ \exists \delta > 0, \ \forall x \in E \ \big(0 < |x - a| < \delta \implies |f(x)| > C\big). \end{gather}
$$

An immediate application of the aforementioned facts is the *limit ratio rule*, which is useful for testing a rational function: 
$$
\begin{gather} \textbf{Proposition: The Infinite Limit Ratio Rule} \\[5mm] \text{Let } a \in E'. \text{ If } \lim_{x \to a} f(x) = c > 0 \text{ and } \lim_{x \to a} g(x) = 0 \text{ with } g(x) > 0 \text{ for all } x \in \mathring{U}_E(a), \text{ then:} \\[3.5mm] \lim_{x \to a} \frac{f(x)}{g(x)} = +\infty. \end{gather}
$$
(see [[Proof of the Infinite Limit Ratio Rule]])

>[!question]+ Application: Càdlàg Asset Price Paths, Stopping Times, and Barrier Options
>In continuous-time stochastic finance, price trajectories of jump-diffusion models (such as Merton's model) or Lévy processes cannot be modeled as continuous functions. Instead, they belong to the space of *càdlàg* functions (an acronym for the French *continu à droite, limite à gauche*):
>$$ S(t) = \lim_{s \to t^+} S(s) \quad \text{and} \quad S(t^-) := \lim_{s \to t^-} S(s) \ \text{exists.} \tag{4} $$
>The instantaneous jump magnitude is quantified precisely by the difference between the directional limits: $\Delta S(t) := S(t) - S(t^-)$. In down-and-out barrier options, the first hitting time $\tau_B = \inf\{t \ge 0 \mid S(t) \le B\}$ is a stopping time whose boundary valuation depends on whether the barrier was breached continuously through geometric diffusion ($\lim_{t \to \tau_B} S(t) = B$) or bypassed discontinuously via a discrete downward jump ($S(\tau_B^-) > B \ge S(\tau_B)$).

---
# Heine-Cauchy Equivalence
The topological characterization of limits via metric neighborhoods admits an equivalent formulation through sequential sampling, linking functional limits directly to the sequential convergence theory developed in Chapter 1:
$$
\begin{gather} \textbf{Proposition: Equivalence of Cauchy and Heine Definitions} \\[5mm] \text{Let } f: E \to \mathbb{R} \text{ and let } a \in E'. \text{ The Cauchy relation } \lim_{E \ni x \to a} f(x) = A \text{ holds if and only if} \\[2mm] \text{for every sequence } \{x_n\}_{n=1}^\infty \text{ of points } x_n \in E \setminus \{a\} \text{ converging to } a \text{ as } n \to \infty, \\[2mm] \text{the corresponding image sequence } \{f(x_n)\}_{n=1}^\infty \text{ converges to } A\text{:} \\[3.5mm] \lim_{E \ni x \to a} f(x) = A \iff \Big(\forall \{x_n\} \subset E \setminus \{a\}, \ \lim_{n \to \infty} x_n = a \implies \lim_{n \to \infty} f(x_n) = A\Big). \end{gather}
$$
(see [[Proof of the Equivalence of Cauchy and Heine Definitions]])

>[!danger]+ Intuition: Sequential Probes of Continuous Topologies
>The Heine criterion conceptualizes the limit as an exhaustive interrogation of the function by all possible discrete sequences. To prove that a limit exists via Heine requires showing that every admissible sequence yields the identical target value $A$. Conversely, the Heine criterion serves as the most powerful analytical tool to prove that a limit *does not exist*: one need only construct two sequences $\{x_n\}$ and $\{y_n\}$ converging to $a$ such that $\lim_{n \to \infty} f(x_n) \neq \lim_{n \to \infty} f(y_n)$, or exhibit a single sequence $\{x_n\}$ along which $\{f(x_n)\}$ oscillates without a limit.

---
# Limits Over an Arbitrary Base
The concepts of two-sided limits, directional limits, limits at infinity, and sequential limits can be derived simultaneously through the topological theory of *filter bases*. This *Bourbaki-Zoric*h architectural abstraction proves theorems on uniqueness, boundedness, arithmetic, and order preservation once and for all over an abstract base $\mathcal{B}$, eliminating redundant proofs across specialized limiting domains:
$$
\begin{gather} \textbf{Definition: Filter Base} \\[5mm] \text{A family } \mathcal{B} \text{ of non-empty subsets of a set } X \text{ forms a filter base (or simply base) in } X \text{ if:} \\[3.5mm] \text{1. Non-emptiness: } \forall B \in \mathcal{B}, \quad B \neq \emptyset. \\[2mm] \text{2. Filter Directedness: } \forall B_1, B_2 \in \mathcal{B}, \quad \exists B \in \mathcal{B} \text{ such that } B \subseteq B_1 \cap B_2. \end{gather}
$$

The canonical mathematical limits correspond to explicit realizations of filter bases in $\mathbb{R}$:
* Punctured neighborhood base: $\mathcal{B}(a) := \{\mathring{U}_\delta(a) \cap E \mid \delta > 0\}$ corresponds to $x \to a$.
* Right-hand base: $\mathcal{B}(a^+) := \{(a, a + \delta) \cap E \mid \delta > 0\}$ corresponds to $x \to a^+$.
* Left-hand base: $\mathcal{B}(a^-) := \{(a - \delta, a) \cap E \mid \delta > 0\}$ corresponds to $x \to a^-$.
* Base of infinity: $\mathcal{B}(+\infty) := \{(d, +\infty) \cap E \mid d \in \mathbb{R}\}$ corresponds to $x \to +\infty$.
* Sequence base: $\mathcal{B}(\mathbb{N}) := \{\{k \in \mathbb{N} \mid k > n\} \mid n \in \mathbb{N}\}$ corresponds to $n \to \infty$.

$$
\begin{gather} \textbf{Definition: Limit over a Base} \\[5mm] \text{A number } A \in \mathbb{R} \text{ is the limit of the function } f: X \to \mathbb{R} \text{ over the base } \mathcal{B}, \text{ denoted} \\[3.5mm] \lim_{\mathcal{B}} f(x) = A, \\[3.5mm] \text{if for every neighborhood } V(A) \text{ of } A, \text{ there exists an element } B \in \mathcal{B} \text{ such that } f(B) \subseteq V(A)\text{:} \\[3.5mm] \forall \varepsilon > 0, \ \exists B \in \mathcal{B}, \ \forall x \in B \ \big(|f(x) - A| < \varepsilon\big). \end{gather}
$$

$$
\begin{gather} \textbf{Definition: Ultimate Properties over a Base} \\[5mm] \text{A property } P(x) \text{ holds ultimately over a base } \mathcal{B} \text{ if there exists an element } B \in \mathcal{B} \\[2mm] \text{such that } P(x) \text{ holds for all } x \in B. \end{gather}
$$

$$
\begin{gather} \textbf{Definition: Boundedness and Infinitesimals over a Base} \\[5mm] \text{1. A function } f: X \to \mathbb{R} \text{ is ultimately bounded over } \mathcal{B} \text{ if there exist a constant } C > 0 \\[2mm] \text{and an element } B \in \mathcal{B} \text{ such that } |f(x)| \le C \text{ for all } x \in B. \\[3.5mm] \text{2. A function } \alpha: X \to \mathbb{R} \text{ is an infinitesimal over } \mathcal{B} \text{ if } \lim_{\mathcal{B}} \alpha(x) = 0. \end{gather}
$$

$$
\begin{gather} \textbf{Theorem: General Properties of Limits over a Base} \\[5mm] \text{1. Ultimately Constant Functions: If } f(x) = c \text{ ultimately over } \mathcal{B}, \text{ then } \lim_{\mathcal{B}} f(x) = c. \\[2mm] \text{2. Ultimate Boundedness: If } \lim_{\mathcal{B}} f(x) = A \in \mathbb{R}, \text{ then } f \text{ is ultimately bounded over } \mathcal{B}. \\[2mm] \text{3. Uniqueness of the Limit: A convergent function cannot possess two distinct limits over } \mathcal{B}. \end{gather}
$$
(see [[Proof of General Limit Properties]])

$$
\begin{gather} \textbf{Lemma: Local Sign Preservation and Separation from Zero} \\[5mm] \text{Let } \lim_{\mathcal{B}} f(x) = A. \text{ If } A > 0 \text{ (respectively, } A < 0\text{), then there exists an element } B \in \mathcal{B} \\[2mm] \text{such that for all } x \in B\text{:} \\[3.5mm] f(x) > \frac{A}{2} > 0 \quad \left(\text{respectively, } f(x) < \frac{A}{2} < 0\right). \\[3.5mm] \text{Consequently, if } A \neq 0, \text{ the function } f \text{ is strictly separated from zero ultimately over } \mathcal{B}\text{:} \\[3.5mm] \exists B \in \mathcal{B}, \ \forall x \in B, \quad |f(x)| > \frac{|A|}{2} > 0. \end{gather}
$$
(see [[Proof of Local Sign Preservation]])

$$
\begin{gather} \textbf{Proposition: Operations on Infinitesimals} \\[5mm] \text{1. The sum of a finite number of infinitesimal functions over } \mathcal{B} \text{ is an infinitesimal over } \mathcal{B}. \\[2mm] \text{2. The product of two infinitesimal functions over } \mathcal{B} \text{ is an infinitesimal over } \mathcal{B}. \\[2mm] \text{3. The product of an infinitesimal function and an ultimately bounded function over } \mathcal{B} \\[2mm] \text{is an infinitesimal function over } \mathcal{B}. \end{gather}
$$
(see [[Proof of Operations on Infinitesimals]])

$$
\begin{gather} \textbf{Proposition: The Bounded-Infinitesimal Product Law} \\[5mm] \text{If } \lim_{\mathcal{B}} f(x) = 0 \text{ and } g(x) \text{ is ultimately bounded over } \mathcal{B} \ \big(|g(x)| \le M \ \forall x \in B\big), \text{ then:} \\[3.5mm] \lim_{\mathcal{B}} \big(f(x) \cdot g(x)\big) = 0. \end{gather}
$$
(see [[Proof of the Bounded-Infinitesimal Product Law]])

> [!info]+ Remark: Infinitesimal Deviation Representation
> The analytical statement $\lim_{\mathcal{B}} f(x) = A$ is mathematically equivalent to asserting that $f(x) = A + \alpha(x)$ ultimately over $\mathcal{B}$, where $\alpha(x)$ is an infinitesimal function over $\mathcal{B}$. This decomposition separates a function into its deterministic asymptotic state $A$ and its vanishing stochastic or deterministic error term $\alpha(x)$.

$$
\begin{gather} \textbf{Theorem: Arithmetic Operations on Limits over a Base} \\[5mm] \text{If } \lim_{\mathcal{B}} f(x) = A \ \text{ and } \ \lim_{\mathcal{B}} g(x) = B, \text{ then:} \\[3.5mm] 1. \quad \lim_{\mathcal{B}} (f + g)(x) = A + B \\[2.5mm] 2. \quad \lim_{\mathcal{B}} (f \cdot g)(x) = A \cdot B \\[2.5mm] 3. \quad \lim_{\mathcal{B}} \left(\frac{f}{g}\right)(x) = \frac{A}{B}, \quad \text{provided } B \neq 0. \end{gather}
$$
(see [[Proof of Arithmetic Operations on Limits]])

---
# Order Structure, Inequalities, and Limit Existence Criteria
Metric limits interact monotonically with the algebraic order axioms of the real numbers, providing bounding squeeze mechanics and intrinsic convergence criteria.

$$
\begin{gather} \textbf{Theorem: Passage to the Limit and Inequalities over a Base} \\[5mm] \text{1. Preservation of Strict Inequalities: If } \lim_{\mathcal{B}} f(x) = A \text{ and } \lim_{\mathcal{B}} g(x) = B \text{ with } A < B, \\[2mm] \text{then there exists an element } B_0 \in \mathcal{B} \text{ such that } f(x) < g(x) \text{ for all } x \in B_0. \\[3.5mm] \text{2. Preservation of Non-Strict Inequalities: If } f(x) \le g(x) \text{ ultimately over } \mathcal{B}, \\[2mm] \text{and both limits exist, then strictly } \lim_{\mathcal{B}} f(x) \le \lim_{\mathcal{B}} g(x). \\[3.5mm] \text{3. The Squeeze Theorem: If } f(x) \le g(x) \le h(x) \text{ ultimately over } \mathcal{B}, \\[2mm] \text{and } \lim_{\mathcal{B}} f(x) = \lim_{\mathcal{B}} h(x) = C, \text{ then } \lim_{\mathcal{B}} g(x) \text{ exists and } \lim_{\mathcal{B}} g(x) = C. \end{gather}
$$
(see [[Proof of Passage to Limit and Inequalities]])

>[!example]- Example: Bounded Oscillatory Squeezing
>Consider the function $g(x) = x^2 \sin\left(\frac{1}{x}\right)$ on the domain $E = \mathbb{R} \setminus \{0\}$ as $x \to 0$. Because $-1 \le \sin\left(\frac{1}{x}\right) \le 1$ for all $x \neq 0$, multiplying by $x^2 > 0$ yields:
>$$ -x^2 \le x^2 \sin\left(\frac{1}{x}\right) \le x^2 \tag{5} $$
>Because $\lim_{x \to 0} (-x^2) = 0$ and $\lim_{x \to 0} x^2 = 0$, the Squeeze Theorem (or the Bounded-Infinitesimal Product Law with $f(x) = x^2$ and bounded $h(x) = \sin(1/x)$) immediately guarantees:
>$$ \lim_{x \to 0} x^2 \sin\left(\frac{1}{x}\right) = 0. \tag{6} $$

$$
\begin{gather} \textbf{Definition: Oscillation of a Function} \\[5mm] \text{The oscillation of a function } f: X \to \mathbb{R} \text{ on a subset } E \subseteq X \text{ is defined by:} \\[3.5mm] \omega(f, E) := \sup_{x_1, x_2 \in E} |f(x_1) - f(x_2)|. \end{gather}
$$

$$
\begin{gather} \textbf{Theorem: Cauchy Criterion for the Existence of a Limit over a Base} \\[5mm] \text{A function } f: X \to \mathbb{R} \text{ possesses a finite limit over the base } \mathcal{B} \text{ if and only if} \\[2mm] \text{for every } \varepsilon > 0, \text{ there exists an element } B \in \mathcal{B} \text{ on which the oscillation is less than } \varepsilon\text{:} \\[3.5mm] \lim_{\mathcal{B}} f(x) = A \in \mathbb{R} \iff \forall \varepsilon > 0, \ \exists B \in \mathcal{B}, \quad \omega(f, B) < \varepsilon. \end{gather}
$$
(see [[Proof of the Cauchy Criterion for the Existence of a Limit]])

$$
\begin{gather} \textbf{Theorem: The Limit of a Composite Function over Filter Bases} \\[5mm] \text{Let } \mathcal{B}_X \text{ be a base in } X, \text{ and let } \mathcal{B}_Y \text{ be a base in } Y. \\[2mm] \text{Let } f: X \to Y \text{ be a mapping such that for every } B_Y \in \mathcal{B}_Y, \text{ there exists } B_X \in \mathcal{B}_X \\[2mm] \text{satisfying the forward inclusion } f(B_X) \subseteq B_Y. \\[3.5mm] \text{If } g: Y \to \mathbb{R} \text{ possesses a limit over the base } \mathcal{B}_Y, \text{ then the composite function } (g \circ f): X \to \mathbb{R} \\[2mm] \text{is defined ultimately over } \mathcal{B}_X, \text{ possesses a limit over } \mathcal{B}_X, \text{ and satisfies:} \\[3.5mm] \lim_{\mathcal{B}_X} (g \circ f)(x) = \lim_{\mathcal{B}_Y} g(y). \end{gather}
$$
(see [[Proof of Limit of a Composite Function]])

$$
\begin{gather} \textbf{Corollary: Metric Composite Limit Criterion} \\[5mm] \text{Let } \lim_{x \to a} f(x) = b \text{ and } \lim_{y \to b} g(y) = c. \text{ Then } \lim_{x \to a} g(f(x)) = c \text{ holds provided that} \\[2mm] \text{at least one of the following two conditions is satisfied:} \\[3.5mm] \text{Condition 1 (Continuity): } g \text{ is continuous at } b, \text{ meaning } g(b) = c = \lim_{y \to b} g(y). \\[2mm] \text{Condition 2 (Punctured Neighborhood Avoidance): } \exists \delta_0 > 0, \ \forall x \in \mathring{U}_{\delta_0}(a) \cap E, \quad f(x) \neq b. \end{gather}
$$
(see [[Proof of Metric Composite Limit Criterion]])

>[!warning]+ Warning: The Outer Discontinuity Fallacy in Composite Limits
>If Condition 1 and Condition 2 both fail, the metric composite limit $\lim_{x \to a} g(f(x))$ can fail to equal $c$. Consider $f(x) \equiv 0$ and $g(y) = 0$ for $y \neq 0$ with $g(0) = 1$. Then $\lim_{x \to 0} f(x) = 0$ and $\lim_{y \to 0} g(y) = 0$. However, because $f(x) = 0$ identically, $g(f(x)) = g(0) = 1$ for all $x$, yielding:
>$$ \lim_{x \to 0} g(f(x)) = 1 \neq 0 = \lim_{y \to 0} g(y). \tag{7} $$
>The base-theoretic formulation avoids this trap because the filter base mapping condition $f(B_X) \subseteq B_Y$ explicitly prevents the image from collapsing onto excluded points of the target base.

Like with the limits of sequences, the use of the [[Chapter 1 - Basic Properties of Real Numbers|ordering]] can be used to compare the behavior of various functions when evaluated via a specific input $x$:
$$
\begin{gather} \textbf{Definition: Monotonicity of Numerical Functions} \\[5mm] \text{A function } f: E \to \mathbb{R} \text{ defined on an ordered set } E \subseteq \mathbb{R} \text{ is classified as:} \\[3.5mm] \text{1. Strictly Increasing: } \forall x_1, x_2 \in E, \quad x_1 < x_2 \implies f(x_1) < f(x_2). \\[2mm] \text{2. Nondecreasing: } \forall x_1, x_2 \in E, \quad x_1 < x_2 \implies f(x_1) \le f(x_2). \\[2mm] \text{3. Strictly Decreasing: } \forall x_1, x_2 \in E, \quad x_1 < x_2 \implies f(x_1) > f(x_2). \\[2mm] \text{4. Nonincreasing: } \forall x_1, x_2 \in E, \quad x_1 < x_2 \implies f(x_1) \ge f(x_2). \end{gather}
$$

$$
\begin{gather} \textbf{Theorem: Criterion for the Limit of a Monotonic Function} \\[5mm] \text{Let } f: E \to \mathbb{R} \text{ be a nondecreasing function on } E \subseteq \mathbb{R}. \\[3.5mm] \text{1. Upper Boundary: If } \sup E \in E', \text{ then } \lim_{E \ni x \to \sup E} f(x) \text{ exists if and only if } f \text{ is bounded} \\[2mm] \text{above on } E, \text{ in which case the limit equals the exact supremum:} \\[3.5mm] \lim_{E \ni x \to \sup E} f(x) = \sup_{x \in E} f(x). \\[3.5mm] \text{If } f \text{ is unbounded above on } E, \text{ then } \lim_{E \ni x \to \sup E} f(x) = +\infty. \\[3.5mm] \text{2. Lower Boundary: If } \inf E \in E', \text{ then } \lim_{E \ni x \to \inf E} f(x) \text{ exists if and only if } f \text{ is bounded} \\[2mm] \text{below on } E, \text{ in which case the limit equals the exact infimum:} \\[3.5mm] \lim_{E \ni x \to \inf E} f(x) = \inf_{x \in E} f(x). \\[3.5mm] \text{If } f \text{ is unbounded below on } E, \text{ then } \lim_{E \ni x \to \inf E} f(x) = -\infty. \end{gather}
$$
(see [[Proof of Criterion for Monotonic Function Limit]])

$$
\begin{gather} \textbf{Corollary: Existence of One-Sided Limits for Monotonic Functions} \\[5mm] \text{Let } f: (a, b) \to \mathbb{R} \text{ be a nondecreasing function. For every point } x_0 \in (a, b), \\[2mm] \text{both one-sided limits exist as finite real numbers and satisfy the canonical ordering:} \\[3.5mm] \lim_{x \to x_0^-} f(x) = \sup_{x < x_0} f(x) \le f(x_0) \le \inf_{x > x_0} f(x) = \lim_{x \to x_0^+} f(x). \end{gather}
$$
(see [[Proof of One-Sided Existence for Monotonic Functions]])

---

# Geometric Foundations and Fundamental Transcendental Limits
To establish the First Fundamental Limit without circular analytical dependencies, the circular trigonometric functions $\sin x$, $\cos x$, and $\tan x$ must be defined directly via the geometry of the Euclidean plane.

### Geometric Construction of the Trigonometric Functions
Let $\mathbb{R}^2$ be the two-dimensional Euclidean plane equipped with the standard inner product and metric distance. The unit circle $S^1$ is the set of points situated at unit distance from the origin:
$$ S^1 := \{(u, v) \in \mathbb{R}^2 \mid u^2 + v^2 = 1\}. \tag{8} $$
Let $A = (1, 0)$ denote the initial reference vertex. For any real number $x \in \mathbb{R}$, wrap an oriented path of arc length $|x|$ along $S^1$ beginning at $A$, directed counterclockwise if $x > 0$ and clockwise if $x < 0$. The terminal endpoint of this path defines a unique geometric point $P(x) \in S^1$.

The circular functions are defined directly as the Cartesian coordinates of this terminal point:
$$ P(x) =: \big(\cos x, \ \sin x\big). \tag{9} $$
The tangent function is defined on the domain $\{x \in \mathbb{R} \mid \cos x \neq 0\}$ as the quotient:
$$ \tan x := \frac{\sin x}{\cos x}. \tag{10} $$

$$
\begin{gather} \textbf{Theorem: Fundamental Geometric Identities of Trigonometry} \\[5mm] \text{1. The Pythagorean Identity: For every } x \in \mathbb{R}\text{:} \\[3.5mm] \cos^2 x + \sin^2 x = 1. \\[3.5mm] \text{2. Secant-Tangent Identity: For all } x \in \mathbb{R} \setminus \left\{\frac{\pi}{2} + k\pi \ \middle|\ k \in \mathbb{Z}\right\}\text{:} \\[3.5mm] 1 + \tan^2 x = \frac{1}{\cos^2 x} =: \sec^2 x. \\[3.5mm] \text{3. Parity Identities: For all } x \in \mathbb{R}\text{:} \\[3.5mm] \cos(-x) = \cos x \quad (\text{even}), \qquad \sin(-x) = -\sin x \quad (\text{odd}), \qquad \tan(-x) = -\tan x \quad (\text{odd}). \end{gather}
$$
(see [[Proof of Fundamental Geometric Trigonometric Identities]])

This can be visualized and derived geometrically: 
![[unit_circle.png]]