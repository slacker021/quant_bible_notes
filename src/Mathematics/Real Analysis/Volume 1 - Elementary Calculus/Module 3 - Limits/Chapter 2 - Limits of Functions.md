---
dg-publish:
---
# Fundamentals of Functional Limits
The formalization of the limit of a function translates the intuitive concept of approximation into rigorous *topological* and metric constraints. 

$$
\begin{gather} \textbf{Definition: The Limit of a Function ( as denoted by Cauchy)} \\[5mm]  \text{A function } f: E \to \mathbb{R} \text{ tends to } A \text{ as } x \text{ tends to } a, \text{denoted} \lim_{E \ni x \to a} f(x) = A, \text{ if} \\ \forall \varepsilon > 0, \exists \delta > 0 \text{ such that } \forall x \in E, 0 < |x - a| < \delta \implies |f(x) - A| < \varepsilon. \\[2.5mm] \text{Topologically, for every neighborhood } V(A), \text{ there exists a deleted neighborhood} \\ \mathring{U}_E(a) \text{ such that the image } f(\mathring{U}_E(a)) \subset V(A). \end{gather}
$$

$$
\begin{gather} \textbf{Definition: One-Sided Limits and Limits at Infinity} \\[5mm] \text{The limit definitions extend to one-sided approaches and infinite bounds:} \\[2.5mm] \lim_{x \to a-0} f(x) = A \iff \forall \varepsilon > 0, \exists \delta > 0, \forall x \in (a-\delta, a), |f(x) - A| < \varepsilon. \\ \lim_{x \to +\infty} f(x) = A \iff \forall \varepsilon > 0, \exists M \in \mathbb{R}, \forall x > M, |f(x) - A| < \varepsilon. \end{gather}
$$
$$
\begin{gather} \textbf{Proposition: Equivalence of Cauchy and Heine Definitions} \\[5mm] \text{The relation } \lim_{E \ni x \to a} f(x) = A \text{ holds if and only if} \\ \text{for every sequence } {x_n} \text{ of points } x_n \in E \setminus {a} \text{ converging to } a, \\ \text{the sequence } {f(x_n)} \text{ converges to } A. \end{gather}
$$
(see [[Proof of the Equivalence of Cauchy and Heine Definitions|proof]])
### Properties of the Limit
The behavior of functions bounded within specific neighborhoods provides mathematical stability for ensuing analytical operations. 

$$
\begin{gather} \textbf{Definition: Ultimately Constant and Bounded Functions} \\[5mm] \text{1. A function } f: E \to \mathbb{R} \text{ is ultimately constant as } E \ni x \to a \text{ if it remains}  \\   \text{strictly constant in some deleted neighborhood } \mathring{U}_E(a). \\[2.5mm] \text{2. A function is ultimately bounded if there exists } C \in \mathbb{R} \text{ such that } \\ |f(x)| < C \text{ for all } x \text{ within some deleted neighborhood } \mathring{U}_E(a). \end{gather}
$$
$$
\begin{gather} \textbf{Theorem: General Properties of the Limit} \\[5mm] \text{1. An ultimately constant function unconditionally possesses a limit.} \\ \text{2. A function possessing a limit is ultimately bounded.} \\ \text{3. A convergent function cannot possess two distinct limits as } x \to a \text{ (Uniqueness).} \end{gather}
$$
(see [[Proof of General Limit Properties|proof]])

$$
\begin{gather} \textbf{Definition: Infinitesimal Functions} \\[5mm] \text{A function } \alpha: E \to \mathbb{R} \text{ is characterized as infinitesimal as } E \ni x \to a \text{ if}  \lim_{E \ni x \to a} \alpha(x) = 0. \end{gather}
$$

$$
\begin{gather} \textbf{Proposition: Operations on Infinitesimals} \\[5mm] \text{1. The algebraic sum of two infinitesimal functions as } x \to a \text{ is an infinitesimal function.} \\ \text{2. The product of two infinitesimal functions, or the product of an infinitesimal} \\ \text{function and an ultimately bounded function, is an infinitesimal function.} \end{gather}
$$
(see [[Proof of Operations on Infinitesimals|proof]])

> [!info]+ Remark: Infinitesimal Deviation 
> The analytical relation $\lim_{E \ni x \to a} f(x) = A$ is mathematically equivalent to representing the function as $f(x) = A + \alpha(x)$, where $\alpha(x)$ is an infinitesimal function representing the deviation as $x \to a$.

$$
\begin{gather} \textbf{Definition: Arithmetic Operations on Functions} \\[5mm] \text{For numerical-valued functions } f, g: E \to \mathbb{R}, \text{ the sum, product, and quotient are defined as:} \\ (f+g)(x) := f(x) + g(x), \quad (f \cdot g)(x) := f(x) \cdot g(x), \quad \left(\frac{f}{g}\right)(x) := \frac{f(x)}{g(x)} \\ \text{where the quotient strictly requires } g(x) \neq 0 \text{ for all } x \in E. \end{gather}
$$

$$
\begin{gather} \textbf{Theorem: Arithmetic Operations on Limits} \\[5mm] \text{If} \lim_{E \ni x \to a} f(x) = A \ \ \ \text{ and } \lim_{E \ni x \to a} g(x) = B \text{ , then} \\[2.5mm] 1. \ \lim_{x \to a} (f+g)(x) = A+B \\  2. \ \lim_{x \to a} (f \cdot g)(x) = A \cdot B \\ \text{3. Provided } B \neq 0 \text{ and ultimately } g(x) \neq 0,  \lim_{x \to a} \left(\frac{f}{g}\right)(x) = \frac{A}{B}. \end{gather}
$$
(see [[Proof of Arithmetic Operations on Limits|proof]])

$$
\begin{gather} \textbf{Theorem: Passage to the Limit and Inequalities} \\[5mm] \text{1. Preservation of Strict Inequality: If } \lim_{x \to a} f(x) = A \text{ and } \lim_{x \to a} g(x) = B, \text{ with } A < B, \\ \text{there exists a deleted neighborhood of } a \text{ in } E \text{ where strictly } f(x) < g(x). \\ \text{2. Squeeze Theorem: If } f(x) \le g(x) \le h(x) \text{ ultimately as } x \to a, \\ \text{and } \lim_{x \to a} f(x) = \lim_{x \to a} h(x) = C, \text{ then } \lim_{x \to a} g(x) = C. \end{gather}
$$
(see [[Proof of Passage to Limit and Inequalities|proof]])

### Limits Over an Arbitrary Base
The concept of a limit is generalized beyond strict real-number intervals through the topological concept of a filter base, enabling limits over abstract sets and directed environments. 

$$
\begin{gather} \textbf{Definition: Filter Base} \\[5mm] \text{A collection } \mathcal{B} \text{ of subsets } B \subset X \text{ forms a base in } X \text{ if} \\[2.5mm]
\text{1. }  \forall B \in \mathcal{B}, B \neq \emptyset. \\
\text{2. } \forall B_1, B_2 \in \mathcal{B}, \exists B \in \mathcal{B} \text{ such that } B \subset B_1 \cap B_2. 
\end{gather}
$$

$$
\begin{gather} \textbf{Definition: Limit over a Base} \\[5mm] \text{A number } A \in \mathbb{R} \text{ is the limit of } f: X \to \mathbb{R} \text{ over base } \mathcal{B}, \text{ denoted } \lim_{\mathcal{B}} f(x) = A, \\ \text{if for every neighborhood } V(A), \text{ there is an element } B \in \mathcal{B} \text{ such that } f(B) \subset V(A). \end{gather}
$$

$$
\begin{gather} \textbf{Definition: Boundedness and Infinitesimals over a Base} \\[5mm] \text{A function is ultimately bounded over } \mathcal{B} \text{ if there exists } c > 0 \text{ and } B \in \mathcal{B} \\ \text{such that } |f(x)| < c \text{ for all } x \in B. \\ \text{It is characterized as an infinitesimal over } \mathcal{B} \text{ if } \lim_{\mathcal{B}} f(x) = 0. \end{gather}
$$

# Existence of the Limit and Functional Properties
Intrinsic properties of a function, specifically measuring variation and ordering, determine absolute conditions for the existence of limits.

$$
\begin{gather} \textbf{Definition: Oscillation of a Function} \\[5mm] \text{The oscillation of a function } f: X \to \mathbb{R} \text{ on a subset } E \subset X \text{ is calculated as:} \\ \omega(f, E) := \sup_{x_1, x_2 \in E} |f(x_1) - f(x_2)| \end{gather}
$$
$$
\begin{gather} \textbf{Theorem: Cauchy Criterion for the Existence of a Limit} \\[5mm] \text{A function } f: X \to \mathbb{R} \text{ possesses a limit over the base } \mathcal{B} \text{ if and only if} \\ \text{for every } \varepsilon > 0 \text{ there exists } B \in \mathcal{B} \text{ such that } \omega(f, B) < \varepsilon. \end{gather}
$$
(see [[Proof of the Cauchy Criterion for the Existence of a Limit|proof]])

$$
\begin{gather} \textbf{Theorem: The Limit of a Composite Function} \\[5mm] \text{Let } g: Y \to \mathbb{R} \text{ possess a limit over base } \mathcal{B}_Y, \text{ and } f: X \to Y \text{ operate such that} \\ \text{for every } B_Y \in \mathcal{B}_Y, \text{ there exists } B_X \in \mathcal{B}_X \text{ satisfying } f(B_X) \subset B_Y. \text{ Then,} \\ \text{the composite mapping } g \circ f \text{ is defined, possesses a limit over } \mathcal{B}_X, \text{ and:} \\ \lim_{\mathcal{B}_X} (g \circ f)(x) = \lim_{\mathcal{B}_Y} g(y) \end{gather}
$$

$$
\begin{gather} \textbf{Definition: Monotonicity} \\[5mm] \text{A function } f: E \to \mathbb{R} \text{ is classified on } E \text{ as} \\[2.5mm] \text{1. Increasing (Nondecreasing) if } x_1 < x_2 \implies f(x_1) < f(x_2) \quad (f(x_1) \le f(x_2)). \\[2.5mm] \text{2. Decreasing (Nonincreasing) if } x_1 < x_2 \implies f(x_1) > f(x_2) \quad (f(x_1) \ge f(x_2)). \end{gather}
$$
(see [[Proof of Limit of a Composite Function|proof]])

$$
\begin{gather} \textbf{Theorem: Criterion for the Limit of a Monotonic Function} \\[5mm] \text{A necessary and sufficient condition for a nondecreasing function } f: E \to \mathbb{R} \text{ to} \\ \text{possess a limit as } x \to \sup E \text{ is that it be bounded above.} \\ \text{To possess a limit as } x \to \inf E, \text{ it is necessary and sufficient that it be bounded below.} \end{gather}
$$
(see [[Proof of Criterion for Monotonic Function Limit|proof]])

---
# Asymptotic Behavior of Functions

Evaluating limits frequently relies on characterizing the asymptotic behavior of functions relative to one another over a specified base to simplify complex expressions.

$$
\begin{gather} \textbf{Definition: Ultimate Property over a Base} \\[5mm] \text{A specific property or relation holds ultimately over a base } \mathcal{B} \text{ if there} \\ \text{exists an element } B \in \mathcal{B} \text{ on which the property holds universally.} \end{gather}
$$
$$
\begin{gather} \textbf{Definition: Asymptotic Order (Big-O and Little-o)} \\[5mm] 1. \ f =_{\mathcal{B}} O(g) \iff \text{Ultimately over } \mathcal{B}, \exists C > 0 \text{ such that } |f(x)| \le C|g(x)|. \\ f =_{\mathcal{B}} o(g) \iff \text{Ultimately over } \mathcal{B}, f(x) = \alpha(x)g(x), \text{ where } \lim_{\mathcal{B}} \alpha(x) = 0. \end{gather}
$$
$$
\begin{gather} \textbf{Definition: Same Asymptotic Order and Equivalence} \\[5mm] \text{1. Two functions are of the same order, denoted } f \asymp_{\mathcal{B}} g, \text{ if} \\ f =_{\mathcal{B}} O(g) \quad \text{and} \quad g =_{\mathcal{B}} O(f). \\ \text{2. Two functions are asymptotically equivalent, denoted } f \sim_{\mathcal{B}} g, \text{ if} \\[2.5mm] \text{Ultimately over } \mathcal{B}, f(x) = \gamma(x)g(x), \text{ where } \lim_{\mathcal{B}} \gamma(x) = 1. \end{gather}
$$

$$
\begin{gather} \textbf{Proposition: Limit of Equivalent Functions} \\[5mm] \text{If } f \sim_{\mathcal{B}} \tilde{f}, \text{ then } \lim_{\mathcal{B}} f(x)g(x) = \lim_{\mathcal{B}} \tilde{f}(x)g(x), \\ \text{provided that at least one of these limits exists.} \end{gather}
$$
(see [[Proof of Limit of Equivalent Functions|proof]])

