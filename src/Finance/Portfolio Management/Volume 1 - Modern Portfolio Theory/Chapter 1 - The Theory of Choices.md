---
dg-publish: true
---
# Making Decisions Under Certainty
Finance is fundamentally the art and science of making decisions regarding fiscal matters. While there are numerous types of decisions in finance, most of these decisions have certain elements in common: 
- Delineation of alternatives within the investable universe
- Selection criteria for choosing among those alternatives
- The solution of the problem
Furthermore, individual solutions can be aggregated to describe *equilibrium* in the economy: 
$$
\begin{gather}
\textbf{Definition: Equilibrium} \\[5mm]
\text{An economic state in which supply and demand for a } \\[2mm]
\text{given good or service are in balance. }
\end{gather}
$$

### The Opportunity Set
The simplest way to model making decisions under uncertainty is through the *opportunity set*, which takes into account the following factors when making financial decisions: 
- The time periods that the investor is operating in 
- The product or service the investor wants to consume
- The combination of products or services the investor can consume at any moment
Although the opportunity set may be visualized as simple plots on a two-dimensional grid, it may be more dynamic to graph these as [[Chapter 1 - Vector Space of Linear Maps|linear]] [[Chapter 4 - Functions and Cardinality|functions]] that are drawn across the grid. This system of representation takes preferences over bundles and assigns each bundle a single number, where higher numbers represent more preferred bundles: 
$$
\begin{gather}
\textbf{Definition: Utility Function} \\[5mm]
\text{Let } X \text{ denote the consumption space or choice set, } \\[2mm]
\text{which is typically a non-empty subset of the Euclidean Space, } \\[2mm]
X \subseteq \mathbb{R}^n_{+}. \text{ Let } \succsim \text{represent a binary } \text{preference relation over the set } X,  \\[2mm]
\text{which satisfies the fundamental axioms of completeness and transitivity}.  \\[2mm]
\text{A mapping } u:X \rightarrow \mathbb{R} \text{ is defined as the utility function representing } \\[2mm]
\text{representing the prefernce relation } \succsim \text{ if and only if }, \text{ for all choice bundles } x,y \in X:  \\[2mm]
u(x) \geq u(y) \iff x \succsim y \\[3.5mm]

\text{Furthermore, if } f:\mathbb{R} \rightarrow \mathbb{R} \text{ is a strictly increasing monotonic transformation such that } \\[2mm]
\frac{df(u)}{du} > 0,  \\[2mm]
 
\text{then the composite function } v(x) = f(u(x)) \text{ constitutes an equivalent utility function } \\[2mm]
\text{representing the identical preference architecture. Geometrically, the preimage of a constant } \\[2mm]
\text{utility level } k \in \mathbb{R } \text{ is defined by the level set }  \\[3.5mm]
 \\
I_{k} = \{ x \in X \ | \ u(x) = k \} \\[2mm]
\text{delineates the individual's indifference curve within the choice space.}
\end{gather}
$$
(see [[Chapter 1 - Basic Properties of Real Numbers|axiom of completeness]], [[Chapter 1 - Limits of Sequences|limit of monotonic sequences]], [[Chapter 2 - Limits of Functions|limit of a function]],  and [[Chapter 4 - Study of Functions Using Methods of Differential Calculus|differential calculus]] for more information) 

In other words, the utility function takes in two or more arguments, which are the specific quantities of each good consumed. Each output of the function, represents a certain amount of *utility*, which is the level of satisfaction or happiness obtained from this particular bundle. The higher the utility, the higher the satisfaction the investor has from that specific bundle. 

> [!example]-  Example: Lending and Borrowing Money
> Assume that an investor can lend and borrow money at $5$ percent and have an income of $20,000$ in each of two periods. Furthermore, they have an initial wealth of $50,000$. The opportunity set can be modeled by first designating variables to each entity in the economy:
> $$
> \begin{align}
> w_{i} & = \text{initial wealth of } 50,000 \\[2mm]
> p_{1} & = \text{period 1 income of } 20,000  \\[2mm]
> p_{2} & = \text{period 2 income of } 20,000 \\[2mm]
> r & = \text{lending or borrowing rate of } 5 \% \tag{1}
> \end{align}
> $$
> The investor has many combinations of options to choose. The three main options they can choose are
> - $A:$ The investor can save all income, as well as the initial capital, in the first period, which would have them earn $3500$ in interest by the second period. Once the second period begins, they've $93,500$ to spend. 
> - $B:$ The investor can opt to save nothing and consume $20,000$ of income and $50,000$ of their initial capital, in the first period. By the second period, the investor earns $20,000$ in income. In total, the investor spends $90,000$
> - $C:$ The investor can opt to consume $20,000$ of income and $50,000$ of initial capital in the first period. Furthermore, the investor decides to borrow $20,000$ at a cost of $5 \%$ interest at the same period. By the first period's end, the investor'll have consumed $89,047.6191$. Because they borrowed against the future, they have nothing to spend in the second period. 
>   The opportunity set can be visualized as
>![[lending_and_borrowing.png]]
> In the figure above, the utility function takes the form of the function $u(x_{1},x_{2}) = -1.05x + 93.5$, which shows the whole range of possible combinations of consumption the investor can make. 
### Indifference Curves
Although the investor has many choices to make concerning the combination of two (or more) assets, not all those combinations are made equal. If there are one or two outputs of the function that are said to yield the same level of utility. Determining the bundle combinations that yield the same level of satisfaction can be done with *indifference curves*. The curves are "indifferent" because it is assumed that everywhere along the same curve, the investor is assumed to be equally satisfied: 
$$
\begin{gather}
\textbf{Definition: Indifference Curve} \\[5mm]
\text{An indifference curve is the level or countour set of a } \\[2mm]
\text{real-valued preference function } u:X \rightarrow \mathbb{R} \text{ defined} \\[2mm]
\text{over a choice set } X \subseteq \mathbb{R}_{+}^n.  \\[3.5mm] 

\text{Let } \succsim \text{be a continuous, weak preference ordering over the consumption space } X \\[2mm]
\text{represented by a continuous utility function } u(x). \text{ For a fixed, } \\[2mm]
\text{arbitrary level of utility } k \in \text{lm}(u) \subseteq \mathbb{R}, \text{the } \\[2mm]
\text{indifference set (curve) } \mathcal{I}_k \text{ associated with index }k \text{ is the preimage of } k \text{ under } u:  \\[3.5mm]

\mathcal{I}_k = u^{-1}(\{k\}) = \{ x \in X \mid u(x) = k \}
\end{gather}
$$
(see [[Chapter 1 - Definition of Continuity at a Point|definition of continuity]] and [[Chapter 2 - Differentiation of Multivariate Functions|multivariate derivatives]] for more information)

The indifference curves and opportunity set represent the tools necessary for the investor to reach a solution. The optimum pattern for the investor is determined by the point at which a number of the set of indifference curves is tangent to the opportunity set. The investor ought to select the bundle corresponding to the point of tangency between the budget line and an indifference curve, rather than a curve that intersects the utility line at two points or a curve that does not intersect the line at all. When an indifference curve crosses a linear budget line at one point, this one point represents the option the investor is most satisfied with. 

An indifference curve that crosses the utility line twice suboptimal because the investor has two choices. This means the investor shall have to decide as to what they deem to be more optimal, which defeats the purpose of this framework. On the contrary, an indifference curve that does not intersect the utility line at all represents decisions that do not even fit into the investor's constraints. 

> [!example]- Example: Purchasing Candy
> Rose is walking down an unfamiliar street one day, and she comes across an old-fashioned candy store. They have red hots, which cost $0.01$ for five pieces, and rock candy, which costs $0.01$ for a single piece. She decides to purchase some for herself and friends, but realizes that she only has $1$ to spend.  
> 
> The opportunity set can be modeled by first designating variables to each factor Rose has to take into consideration when purchasing the candies: 
> $$
>\begin{align}
> w_{i} & = \text{Rose's money, which is } 1 \\
> h & = \text{Red hots, which costs } 0.01 \text{ for five pieces} \\
> r & = \text{Rock candy, which costs } 0.01 \text{ for a single piece} \tag{2}
\end{align}
> $$
> 
> Rose has many options to choose from. As an example, these are three options: 
> - $A:$ Rose purchases $500$ red hots and zero pieces of rock candy.
> - $B:$ Rose purchases $250$ red hots and $50$ pieces of rock candy. 
> - $C:$ Rose purchases zero red hots and $100$ pieces of rock candy. 
>   
>   This opportunity set and its corresponding indifference curves can be visualized as
>![[candy_for_rose.png]]
> Rose can select consumption pattern 1 or 2, given that both intersect the utility line. However, consumption pattern 1 crosses the utility line twice, which implies that the second point of intersection of indifference curve 1 undersatisfies Rose. Indifference curve 2, on the other hand, represents the precise boundary where the Rose maximizes her satisfaction. Lastly, indifference curve 3 represents decisions that're beyond Rose's budget.  

> [!example]- Example: Patrick Visits the Krusty Krab
> Patrick decides to visit the Krusty Krab to try out their new Krusty pizza. He decides to bring $10.00$ dollars to spend with him. Upon arriving at the Krusty Krab, Squidward informs Patrick that a single slice of pizza is $2.00$ dollars while a single Krabby Patty is $2.50$ dollars. 
> 
> Patrick's opportunity set can be constructed by first describing three decisions, among the many bundles, that he can make:
> $A:$ Patrick orders five slices of pizza but has no Krabby Patties to consume. This means all ten dollars he came with are spent. 
> $B:$ Patrick orders two and a half half slices of pizza for five dollars and two Krabby Patties for five dollars. This leaves a single dollar unspent. 
> $C:$ Patrick orders four Krabby Patties for ten dollars but have no pizza to consume. This means all ten dollars he came with are consumed. 
> This can be graphically modeled as
>![[patrick_orders.png]]

