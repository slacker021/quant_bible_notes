---
dg-publish: true
---
A real number $x \in \mathbb{R}$ is called a *real algebraic number* if it is a root of a non-constant polynomial equation in one variable with integer coefficients. Any such polynomial $P(x)$ of degree $n \in \mathbb{N}$ takes the form: 
$$
\begin{gather}
P(x) = a_n x^n + a_{n-1} x^{n-1} + \dots + a_1 x + a_0 = 0 \tag{1}
\end{gather}
$$
where $a_0, a_1, \dots, a_n \in \mathbb{Z}$ and the leading coefficient satisfies $a_n \in \mathbb{Z} \setminus \{0\}$.

First, for any countable set $X$ and any at most countable set $Y$, the Cartesian product $X \times Y = \bigcup_{x \in X} (\{x\} \times Y)$ is a countable union of sets $\{x\} \times Y$ each equipotent to $Y$. By the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]], $X \times Y$ is at most countable (and countable whenever $Y$ is non-empty and countable). Because $\mathbb{Z}$ and $\mathbb{Z} \setminus \{0\}$ are countable sets, mathematical induction on the dimension $n \in \mathbb{N}$ establishes that the Cartesian product $(\mathbb{Z} \setminus \{0\}) \times \mathbb{Z}^n$ is countable for every $n \in \mathbb{N}$.

For each fixed degree $n \in \mathbb{N}$, let $\mathcal{P}_n$ denote the set of all polynomials of degree $n$ with integer coefficients. Because each polynomial $P \in \mathcal{P}_n$ in step 1 is uniquely determined by its $(n + 1)$-tuple of coefficients $(a_n, a_{n-1}, \dots, a_0) \in (\mathbb{Z} \setminus \{0\}) \times \mathbb{Z}^n$, the set $\mathcal{P}_n$ is equipotent to $(\mathbb{Z} \setminus \{0\}) \times \mathbb{Z}^n$ and is therefore countable. Consequently, the collection of all non-constant integer-coefficient polynomials:
$$
\begin{gather}
\mathcal{P} := \bigcup_{n=1}^\infty \mathcal{P}_n \tag{2}
\end{gather}
$$
is a countable union of countable sets, which by the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]] is countable.

For each polynomial $P \in \mathcal{P}$ of degree $n \in \mathbb{N}$, let $R(P) := \{ x \in \mathbb{R} \mid P(x) = 0 \}$ denote its set of real roots. Because a polynomial of degree $n \ge 1$ over a field possesses at most $n$ distinct roots, every root set $R(P)$ is finite ($|R(P)| \le n$) and therefore at most countable. The set of all real algebraic numbers $\mathbb{A} \subset \mathbb{R}$ is the union of the real root sets over all $P \in \mathcal{P}$:
$$
\begin{gather}
\mathbb{A} = \bigcup_{P \in \mathcal{P}} R(P) \tag{3}
\end{gather}
$$
Step 3 expresses $\mathbb{A}$ as the union of a countable family of finite sets, which implies that $\mathbb{A}$ is at most countable. Moreover, for every rational number $r = p/q \in \mathbb{Q}$ (with $p \in \mathbb{Z}$ and $q \in \mathbb{N}$), $r$ is the unique root of the degree-$1$ polynomial $P(x) = qx - p \in \mathcal{P}_1$, so $\mathbb{Q} \subset \mathbb{A}$. Because $\mathbb{Q}$ is infinite, $\mathbb{A}$ is countably infinite (countable).

A real number is called *transcendental* if it is not algebraic. The set of real transcendental numbers $\mathbb{T}$ is the complement of $\mathbb{A}$ in $\mathbb{R}$, yielding the disjoint partition:
$$
\begin{gather}
\mathbb{R} = \mathbb{A} \cup \mathbb{T}, \qquad \mathbb{A} \cap \mathbb{T} = \emptyset \tag{4}
\end{gather}
$$
If $\mathbb{T}$ were at most countable, then step 4 would express $\mathbb{R}$ as the union of two at most countable sets, forcing $\mathbb{R}$ to be countable by the [[Proof of the Union of Countable Sets|Proposition on the Union of Countable Sets]]. This directly contradicts the [[Proof of the Uncountability of the Real Numbers|Theorem on the Uncountability of the Real Numbers]]. Thus, $\mathbb{T}$ is uncountable (and in particular non-empty).

Furthermore, because $\mathbb{T}$ is uncountable, it contains a countably infinite subset $S = \{t_1, t_2, t_3, \dots\} \subset \mathbb{T}$. Enumerating the countable set of algebraic numbers as $\mathbb{A} = \{a_1, a_2, a_3, \dots\}$ allows the construction of a mapping $h: \mathbb{R} \to \mathbb{T}$ defined by:
$$
\begin{gather}
h(x) := \begin{cases}
t_{2n - 1} & \text{if } x = a_n \in \mathbb{A} \ \ (n \in \mathbb{N}) \\[2mm]
t_{2n} & \text{if } x = t_n \in S \ \ (n \in \mathbb{N}) \\[2mm]
x & \text{if } x \in \mathbb{T} \setminus S
\end{cases} \tag{5}
\end{gather}
$$
Because $\mathbb{A}$, $S$, and $\mathbb{T} \setminus S$ form a partition of $\mathbb{R}$, and their images $\{t_{2n-1} \mid n \in \mathbb{N}\}$, $\{t_{2n} \mid n \in \mathbb{N}\}$, and $\mathbb{T} \setminus S$ form a partition of $\mathbb{T}$ onto which each branch of step 5 is bijective, $h: \mathbb{R} \to \mathbb{T}$ is a bijection. Therefore, the set of real transcendental numbers $\mathbb{T}$ has the cardinality of the continuum $\mathfrak{c}$.
$$
\begin{gather}
\textbf{Q.E.D.}
\end{gather}
$$
