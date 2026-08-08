---
dg-publish: true
---
# Prelude: Epicenter of the Mathematical Universe
Mathematical sciences are a collection of *deductive* enterprises of knowledge that begin with very basic assumptions, which are then used to build more complex facts. They are fundamentally abstract sciences that see universal use across various applied sciences. Therefore, these enterprises are treated with respect by learners who go to listen to arguments focused on constructing order and truth independent of empirical observation. 

It was *Lomonosov* who claimed that mathematics leads the mind into order while *Galilei* claimed that "The great book of nature is written in the language of Mathematics". There is even the claim that a branch of science contains as much of science as there is mathematics inside of it. These points of view, while strong and somewhat high-and-mighty, are sharp observations that extol the importance of deductive inference in various disciplines not located within the mathematical sciences. Perhaps it may not be such  a far-fetched conclusion to posit that mathematics is the *queen of the sciences*. 

There are many ways to construct a coherent mathematical universe, with various researchers in the past having used differing assumptions and methods to come to the same conclusion. In the case of this repository, it is *Real Analysis* that is chosen as the starting point of the mathematical universe that provides the foundation for the rest of the other topics. It offers an excellent blend of *rigor* that ensures minimal abstraction and ambiguity while more easily reaching contemporary topics without the need to over-define. Real Analysis forms the crucial bedrock of *calculus*, *linear algebra*, *probability theory*, *statistics*, *computer science*, and many other abstract and quantitative modes of inquiry. Thus, real analysis holds a special place in this repository of mathematical knowledge. 

Whether the reader parsing through these notes is a researcher of the natural sciences, formal sciences, social sciences, enginering, humanities, or some other background, the author hopes that these notes may provide an accessible starting point for anyone looking to approach quantitative research from a zero-abstraction perspective.

---
# Fundamental Mathematical Statements and Conventions
### Axioms 
*Axioms* are starting propositions that are taken as true without proof. These assumptions act as starting points for the formation of new branches of mathematics. Without axioms, a newly minted system of mathematics cannot be formed. The lack of axioms results in circular arguments that lead to nowhere: 
$$\begin{gather} \textbf{Axiom: Foundational Postulate} \\ \text{An axiom is a self-evident or conventionally accepted starting proposition} \\ \text{that is assumed to be true without proof within a formal deductive system.} \end{gather}$$

>[!danger]+ Intuition: The Bedrock of the Architectural Framework
>In an architectural framework, axioms represent the foundational bedrock and the physical laws governing the building site. They are non-negotiable boundaries that must be accepted before any structural design can take place. Attempting to build an analytical mathematical system without axioms is analogous to constructing a skyscraper without securing the bedrock: every subsequent calculation lacks grounding and is vulnerable to collapse.
>
>Although axioms are accepted without proof or considered self-evident, there is still a lot of debate within the mathematical sciences as to how "low one may go" when it comes to determining what should be considered an axiom. If too many axioms are considered, there is the risk of contradictions emerging within the framework. On the contrary, attempting to prove everything nonstop will lead to nonsensical circular arguments.  
>
>It is perhaps unsurprising that an axiom in one framework is considered a provable fact in another. 

### Definitions
A *definition* assigns a precise and unambiguous meaning to a term, symbol, or object. Definitions are linguistic conventions that establish shared clarity rather than mathematical assertions possessing empirical truth values. When convenient, introducing the definition of a mathematical entity can be executed using $:=$, which denotes "equality by definition." If $A$ is a new piece of notation with an unassigned meaning while $B$ is an established expression with a known meaning, $A := B$ denotes that $A$ is defined by $B$. Similarly, abbreviations for expressions already defined can be established using $=:$. If $A$ is an extended expression and $B$ is an abbreviation for that expression, then $A =: B$ denotes that $B$ serves as shorthand for $A$:
$$\begin{gather} \textbf{Definition: Equality by Definition} \\ \text{Let } B \text{ be an established mathematical entity or expression.} \\ \text{The assignment } A := B \text{ establishes that the new symbol } A \text{ is defined by } B. \\ \text{Conversely, } A =: B \text{ assigns the concise shorthand symbol } B \text{ to represent } A. \end{gather}$$

>[!danger]+ Intuition: The Shared Blueprint Vocabulary
>A definition functions as the standardized blueprint vocabulary shared among engineers and researchers. A definition cannot be true or false; rather, it is either operationally useful or cumbersome. Agreeing in advance that a specific symbol designates a specific mathematical relation prevents catastrophic ambiguities during execution, ensuring that all subsequent structural proofs proceed from a universally understood lexicon.
>
>Additionally, the way something is defined has consequences for later definitions that are constructed with said thing. It is important that a formal enterprise of knowledge be consistent with the notations, definitions, and other conventions present in its initial formation.

### Lemmas
A *lemma* is a minor or auxiliary statement that has been formally proven to be true using established axioms, definitions, or preceding propositions. While a lemma is rarely celebrated on its own merits, it serves as an indispensable stepping stone or technical catalyst used to establish a more interesting fact:
>[!danger]+ Intuition: Scaffolding and Intermediate Brackets
>In constructing an archway, one requires temporary scaffolding, specialized brackets, and targeted supports. Lemmas serve as this intermediate scaffolding. They break an otherwise overwhelming, monolithic proof into modular, manageable components. Once the larger archway (the theorem) is locked into place, the supporting lemma has completed its purpose, having carried the intermediate logical weight.

### Propositions
A *proposition* is a mathematical statement that has been proven true under specific assumptions, holding genuine importance within a specific subfield. Propositions establish reliable and localized truths that detail the structural behavior of a mathematical system without necessarily shifting the entire paradigm of the discipline. 

>[!danger]+ Intuition: The Interior Partitions
>Propositions are the sturdy interior walls. They structure and organize the operational living space of the mathematical domain. They are vital for everyday functionality and stability, even if they do not anchor the overarching skyline of the discipline.
>
>Most useful facts within the mathematical sciences fit under this classification.

### Theorems
A theorem is a major statement that has been proven true and is considered of paramount importance, carrying profound implications for the discipline it helps define. A theorem typically synthesizes multiple definitions, axioms, and supporting lemmas into a cohesive conclusion that provides deep insight into the structure of the system under study.

>[!danger]+ Intuition: The Load-Bearing Master Arches
>Theorems are the monumental, load-bearing arches and master structural milestones of mathematics. Proving a theorem permanently expands the conceptual skyline of the field, enabling researchers to build entire new floors of analytical theory upon its foundation.

### Corollaries
A corollary is a mathematical statement that follows naturally, immediately, and with minimal additional argumentation from an established theorem or proposition.

>[!danger]+ Intuition: The Panoramic Sightlines
>A corollary represents an immediate panoramic vista that opens up effortlessly the moment a major archway is completed. Because the heavy lifting of the proof was already accomplished in establishing the parent theorem, the corollary emerges as an immediate, elegant consequence of that structural breakthrough.

---
# Logical Connectives
Mathematical statements require logical connectives to be linked into compound propositions. Symbols allow complex chains of reasoning to be expressed with conciseness and precision. In formal propositional logic, these connectives operate on *atomic propositions*, which are declarative statements expressing a complete, unambiguous idea. Every atomic proposition is assumed to be either *true* or *false*, strictly adhering to the *principle of bivalence*.

Suppose that $A$, $B$, and $C$ are atomic propositions. Propositional logic utilizes five primary connectives: *negation ($\neg$), conjunction ($\wedge$), disjunction ($\lor$), implication ($\implies$), and the biconditional ($\iff$)*. The operational behavior of each connective is completely characterized by its corresponding *truth table*: 

### Negation ($\neg$)
The negation connective signifies "not" and inverts the truth value of a proposition. If proposition $A$ is true, its negation $\neg A$ is false; conversely, if $A$ is false, $\neg A$ is true. The truth table for negation is defined as follows:

| $A$ | $\neg A$ |
| :---: | :---: |
| True | False |
| False | True |

### Conjunction ($\wedge$)
The conjunction connective signifies "and" and requires every constituent proposition to be true for the resulting compound proposition to evaluate to true. If any component proposition is false, the entire conjunction is false. The truth table for conjunction is defined as follows:

| $A$ | $B$ | $A \wedge B$ |
| :---: | :---: | :---: |
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | False |

Conjunction satisfies the *commutative and associative properties of logical equivalence*:
$$\begin{gather} (A \wedge B) \iff (B \wedge A) \tag{1} \end{gather}$$
$$\begin{gather} ((A \wedge B) \wedge C) \iff (A \wedge (B \wedge C)) \tag{2} \end{gather}$$

The *relation* of step 1 establishes that the order in which atomic propositions are specified does not alter the fundamental truth of the compound proposition. The relation of step 2 extends this property to grouping via parentheses.

### Disjunction ($\lor$)
The disjunction connective signifies "or" and operates as an *inclusive or*. A disjunctive compound proposition evaluates to true if at least one of its constituent propositions is true, including the case where both are true simultaneously. The disjunction evaluates to false if and only if both constituent propositions are false. The truth table for disjunction is defined as follows:

| $A$ | $B$ | $A \lor B$ |
| :---: | :---: | :---: |
| True | True | True |
| True | False | True |
| False | True | True |
| False | False | False |

Similar to conjunction, disjunction satisfies both commutativity and associativity:
$$\begin{gather} (A \lor B) \iff (B \lor A) \tag{3} \end{gather}$$
$$\begin{gather} ((A \lor B) \lor C) \iff (A \lor (B \lor C)) \tag{4} \end{gather}$$

>[!warning]+ Warning: Inclusive Union versus Colloquial Selection
>In ordinary speech, "or" often denotes mutual exclusivity (for example, "the contract provides cash or equity"). In formal mathematical analysis, disjunction defaults to the inclusive union. The statement $A \lor B$ does not penalize the state wherein both conditions hold concurrently. In quantitative risk modeling, requiring an asset to satisfy the criterion "volatility below 10% or Sharpe ratio above 1.5" naturally includes an asset that satisfies both metrics simultaneously.

### Implication ($\implies$)
An implication is a compound proposition connecting an antecedent (or premise) $A$ to a consequent (or conclusion) $B$, typically structured as an "if-then" statement ($A \implies B$). An implication evaluates to false if and only if the premise $A$ is true while the conclusion $B$ is false. If the premise $A$ is false, the implication evaluates to true regardless of the truth value of $B$, a condition known as *vacuous truth*. The truth table for implication is defined as follows:

| $A$ | $B$ | $A \implies B$ |
| :---: | :---: | :---: |
| True | True | True |
| True | False | False |
| False | True | True |
| False | False | True |

>[!danger]+ Intuition: The Enforceable Contractual Covenant
>The counterintuitive concept of vacuous truth (wherein a false premise renders the implication true) becomes intuitive when viewed as an enforceable legal covenant. Consider the contractual promise: "If quarterly corporate revenue exceeds ten million dollars ($A$), then an executive performance bonus will be disbursed ($B$)."
>- If revenue exceeds ten million dollars ($A$ is True) and the bonus is disbursed ($B$ is True), the contractual covenant is fulfilled (True).
>- If revenue exceeds ten million dollars ($A$ is True) but the bonus is withheld ($B$ is False), the contractual covenant is breached (False).
>- If revenue fails to reach ten million dollars ($A$ is False), the condition triggering the obligation was never met. The agreement has not been broken, regardless of whether a discretionary bonus is granted or withheld. Hence, the implication remains unbroken (True).

### Biconditional ($\iff$)
A biconditional is a two-directional implication that evaluates to true if and only if both component propositions share the identical truth value (that is, when both are true or when both are false). The expression $A \iff B$ asserts that $A \implies B$ and $B \implies A$ hold simultaneously. The truth table for the biconditional is defined as follows:

| $A$ | $B$ | $A \iff B$ |
| :---: | :---: | :---: |
| True | True | True |
| True | False | False |
| False | True | False |
| False | False | True |

The relation $A \iff B$ can be expressed through several equivalent linguistic conventions:
- $A$ is necessary and sufficient for $B$.
- $A$ holds if and only if $B$ holds.
- $A$ holds when $B$ holds, and only then.
- $A$ is logically equivalent to $B$.

>[!danger]+ Intuition: Structural Equilibrium and Informational Mirrors
>The biconditional establishes an informational mirror between two propositions. Neither proposition can deviate from the truth status of the other; they rise and fall in lockstep. To assert that $A \iff B$ is to state that possessing the truth value of $A$ confers complete informational knowledge regarding $B$, and vice versa.

---
# Proofs
To demonstrate that a mathematical claim is true when its premises are satisfied, a formal proof must be constructed. Mathematical propositions frequently take the conditional form $A \implies B$, where $A$ denotes the set of assumptions and $B$ denotes the conclusion. A proof is a rigorous, deductive argument that establishes why a claim holds universally under the specified assumptions. 

In the mathematical sciences, an empirical collection of affirmative examples—no matter how extensive—can never establish the truth of a universal claim. A single counterexample immediately disproves a conjecture, whereas establishing a universal truth requires a deductive proof that links established premises to the final conclusion through unbroken rules of logical inference.

### Direct Proof
A direct proof establishes the conditional statement $A \implies B$ by constructing a finite deductive chain:
$$\begin{gather} A \implies C_{1} \implies C_{2} \implies \dots \implies C_{n} \implies B \tag{5} \end{gather}$$
where the premise $A$ is assumed to be true, and each intermediate deduction $C_k$ is derived using an axiom, a definition, or a previously verified proposition. 

The primary logical rule governing direct proof is the classical rule of inference known as *Modus Ponens*:
$$\begin{gather} \textbf{Rule of Inference: Modus Ponens} \\ \text{If proposition } A \text{ is true, and the conditional statement } A \implies B \text{ is true,} \\ \text{then proposition } B \text{ is necessarily true.} \end{gather}$$

>[!danger]+ Intuition: Marching Forward Along the Paved Highway
>A direct proof corresponds to marching forward along a paved highway. The analyst departs from origin $A$ (the known assumptions) and advances systematically from milestone to milestone, where each step represents a verified lemma or axiom, until arriving at destination $B$ (the desired theorem).

### Proof by Contradiction
When establishing a direct deductive chain from $A$ to $B$ is analytically difficult, one may employ a proof by contradiction (*reductio ad absurdum*). To establish that $A \implies B$ is true, one assumes as a joint hypothesis that the premise $A$ is true and that the conclusion is false ($\neg B$). Deductive reasoning is then pursued from this joint premise $(A \wedge \neg B)$ until an impossible contradiction arises—such as deducing both a proposition $C$ and its negation $\neg C$ simultaneously ($C \wedge \neg C$), or contradicting an established foundational axiom. 

Because a valid chain of logical deductions cannot generate a falsehood from true premises, the initial hypothesis that $B$ could be false must be rejected, confirming that $B$ holds whenever $A$ holds.

>[!danger]+ Intuition: Collapsing the Alternate Universe
>A proof by contradiction is analogous to constructing a hypothetical alternate universe wherein the premise $A$ holds, yet one deliberately steers away from destination $B$ by asserting $\neg B$. The analyst follows the mechanical consequences of this detour until the alternate universe fractures into an absurd logical impossibility (such as deducing that $0 = 1$). Because reality cannot be self-contradictory, the detour away from $B$ was untenable from the outset, proving that $B$ is inescapable.

### Proof by the Contrapositive
An established alternative to a direct proof is proof by the contrapositive. Rather than proving $A \implies B$ directly, one negates both the premise and the conclusion, and reverses their order in the conditional statement:
$$\begin{gather} \neg B \implies \neg A \tag{6} \end{gather}$$
This strategy is mathematically valid because any conditional statement is logically equivalent to its contrapositive:
$$\begin{gather} (A \implies B) \iff (\neg B \implies \neg A) \tag{7} \end{gather}$$
In execution, one assumes that the conclusion $B$ is false ($\neg B$) and demonstrates through direct deductive inference that the premise $A$ must necessarily be false ($\neg A$).

>[!danger]+ Intuition: The Rearview Mirror Perspective
>A contrapositive proof observes the original highway through a rearview mirror. If an observer finds themselves anywhere other than destination $B$ (that is, $\neg B$), it is structurally impossible for them to have departed from starting point $A$ (that is, $\neg A$). Proving that absent destinations imply absent origins proves the forward journey with equal mathematical certainty.

### Useful Relations

Five fundamental equivalences frequently deployed in deduction are listed below:
1. $\neg(A \wedge B) \iff (\neg A \lor \neg B)$ (De Morgan's First Law)
2. $\neg(A \lor B) \iff (\neg A \wedge \neg B)$ (De Morgan's Second Law)
3. $(A \implies B) \iff (\neg B \implies \neg A)$ (Law of Contraposition)
4. $(A \implies B) \iff (\neg A \lor B)$ (Material Implication Equivalence)
5. $\neg(A \implies B) \iff (A \wedge \neg B)$ (Negation of Implication)

>[!danger]+ Intuition: De Morgan's Duality in Risk Assessment
>De Morgan's laws govern how joint and selective conditions fail under negation:
>- **Failing a Conjunctive Contract:** To breach an agreement requiring both sufficient capital and regulatory approval ($A \wedge B$), an institution only needs to lack at least one of those requirements ($\neg A \lor \neg B$).
>- **Failing a Disjunctive Umbrella:** To fall outside a safety net that covers either domestic equities or sovereign bonds ($A \lor B$), an asset must be neither a domestic equity nor a sovereign bond ($\neg A \wedge \neg B$).

The following consolidated truth table confirms the logical equivalence of these fundamental relations by demonstrating that corresponding columns exhibit identical truth values across all truth assignments of $A$ and $B$:

| $A$ | $B$ | $\neg(A \wedge B)$ | $\neg A \lor \neg B$ | $\neg(A \lor B)$ | $\neg A \wedge \neg B$ | $A \implies B$ | $\neg B \implies \neg A$ | $\neg A \lor B$ | $\neg(A \implies B)$ | $A \wedge \neg B$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| True | True | False | False | False | False | True | True | True | False | False |
| True | False | True | True | False | False | False | False | False | True | True |
| False | True | True | True | False | False | True | True | True | False | False |
| False | False | True | True | True | True | True | True | True | False | False |

>[!question]+ Application: Digital Computers
>Many view digital computers as black boxes given the myriads of components packed into such a tiny space. Such a view is not unfounded, and even the most brilliant of computer engineers cannot fully explain literally every single operation taking place within digital computers today. However, a closer inspection (and somewhat reductionist view) of digital computer architecture reveals them to be glorified switches that are based on boolean algebra. Computer circuits are constructed from *logic gates*, which output a $1$ (true or positive) or $0$ (false or negative) based on the inputs entered. 
>
>The most common types of logic gates used in digital computer architecture are *AND, OR, NOT, NAND, NOR, XOR,* and *XNOR*. The first five gates mentioned follow the same logic as the aforementioned truth tables, so no need to show the truth tables for these ones. However, the XOR and XNOR gates are unique because these are exclusive. Unlike standard OR and NOR logic, which are inclusive, the outputs for these are (for two electrical charges $A$ and $B$):
>- **XOR:** 
>	1. If $A$ is $1$ but $B$ is $0$, then the output is $1$. 
>	2. If $A$ is $0$ but $B$ is $1$, then the output is $1$. 
>	3. If both $A$ and $B$ are $0$, then the output is $0$. 
>	4. If both $A$ and $B$ are $1$, then the output is $0$. This is the defining difference between this and a regular OR gate. 
>- **XNOR:**
>	1. If $A$ is $1$ but $B$ is $0$, then the output is $0$. 
>	2. If $A$ is $0$ but $B$ is $1$, then the output is $0$. 
>	3. If both $A$ and $B$ are both $0$, then the output is $1$. 
>	4. If both $A$ and $B$ are both $1$, then the output is $1$. 

