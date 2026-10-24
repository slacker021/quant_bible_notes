---
dg-publish: true
---
*Real Analysis* is fundamentally concerned with constructing *calculus* and other topics involving real numbers by providing a rigorous and unambiguous theoretical basis. In constructing the various topics concerned with the study of real numbers, a convention for developing complex abstract ideas is needed. These conventions use the following: *Axioms, Definitions, Lemmas, Propositions, and Theorems.* These are the fundamental building blocks of modern analytical mathematics. 

---
# The Five Fundamental Mathematical Statements
### Axioms 
Axioms are starting propositions that're taken as true without the need to prove them. These are assumptions meant to act as starting points for the formation of new branches of mathematics. Without axioms, a newly-minted system of mathematics cannot be formed. The lack of axioms would result in circular arguments that lead to nowhere. 
### Definitions
A definition assigns a precise and unambiguous meaning to a term, symbol, or object. These are not true nor false but act as a convention for communicating rigorous ideas. When convenient, introducing the definition of something can be done using $:=$, which means "equality by definition." If $A$ is a new piece of notation with an unknown meaning while $B$ is an old piece of notation with a known meaning, $A:=B$ denotes that $A$ means $B$. Similarly, abbreviations for expressions already defined can be used with $=:$. If $A$ is a long expression with many concepts and $B$ is an abbreviation for that expression, then $A =: B$ means that $B$ is shorthand for $A$.
### Lemmas
A lemma is a minor idea or truth that has been proven to be true using the appropriate axioms and definitions. However, lemmas are not considered to be very useful on their own and are usually used to support a proposition or theorem. Lemmas can also be proven using previously established theorems and propositions. 
### Proposition
A proposition is a statement that has been proven true under specific assumptions but is less useful or impactful as a theorem. These are useful and important but aren't considered to provide deeper insight to the subject matter. 
### Theorems
A theorem is a statement that has been proven true and is considered to be very important, holding numerous major implications for the rest of the field it helps define. It usually uses multiple definitions and lemmas into a conclusion that provides deep insight into the structure of the system trying to be defined. 

### Corollary
A *corollary* is a fact that quickly and easily follows from an already-proven statement. 

### Logical Connectives
However, these basic statements on their own require *logical connectives* for them to be chained into more complex statements. Furthermore, symbols allow for compound statements to be more concise. These logical connectives are meant to connect *atomic propositions*, which are basic declarative statements in formal logic that express a complete idea. These atomic propositions are either *true* or *false*. Suppose that $A$, $B$, and $C$ are three atomic propositions, where each one can either be true or false. With these statements, the following are the five basic symbols of mathematical logic which can be used on them: $\neg, \wedge, \lor, \implies, \iff$. Furthermore, each logical connective can be associated with a *truth table* to indicate its truth or falsehood depending on the truth of the statements $A, B$, and $C$. 
##### Negation ($\neg$)
This means "not" and is meant to negate the truth value of a statement. If $A$ is true, then $\neg A$ means that $A$ is not true or $A$ is false. The truth table for this is as follows:

| $A$      | True  | False |
| -------- | ----- | ----- |
| $\neg A$ | False | True  |

##### Conjunction ($\wedge$)
This means "and" or "but" and requires all statements chained together to hold true for the *compound proposition*, which is a more complex proposition made up of two or more atomic propositions. The truth table for this is as follows:

| $A$   | $B$   | $A \wedge B$ |
| ----- | ----- | ------------ |
| True  | True  | True         |
| True  | False | False        |
| False | True  | False        |
| False | False | False        |
A special property of the conjunction is that the order at which the atomic propositions are specified will not alter the fundamental truth of the compound proposition. This means that $A \wedge B = B \wedge A$. This property extends to use of parentheses to group propositions, where $(A \wedge B) \wedge C = A \wedge (B \wedge C).$
##### Disjunction
This means "or" and is meant to act as an inclusive "or" where at least one of the statements in the disjunction needs to hold true for the compound proposition to hold true. The truth table for this is as follows:

| $A$   | $B$   | $A \lor B$ |
| ----- | ----- | ---------- |
| True  | True  | True       |
| True  | False | True       |
| False | True  | True       |
| False | False | False      |
Like with the conjunction, the order at which the statements are mentioned in a disjunction does not matter, nor does the use of parentheses to group specific parts of the disjunction alter its fundamental truth. 
##### Implication 
An implication is a compound proposition where a *premise*, which hold the *assumptions*, leads to a result, which is the *conclusion*. This usually takes the form of an "if-then" statement. The truth table for this is as follows:

| $A$   | $B$   | $A \implies B$ |
| ----- | ----- | -------------- |
| True  | True  | True           |
| True  | False | False          |
| False | True  | True           |
| False | False | True           |
##### Biconditional
This is a two-directional implication where it is true if and only if both statements are true. Thus, $A \iff B$ means that both $A \implies B$ and $B \implies A$ must be true simultaneously. The relation $A \iff B$ can be read in the following ways: 
- $A$ is necessary and sufficient for $B$. 
- $A$ holds when $B$ holds, and only then. 
- $A$ if and only if $B$. 
- $A$ is equivalent to $B$. 

---
# Proofs
When it comes to showing that a lemma, proposition, or theorem is true when its premises are true, these must be proven. When proving a proposition, the proposition usually takes the form of $A \implies B$, where $A$ is the assumption and $B$ is the conclusion. A proof may be considered a convincing argument that shows why a certain claim backed by certain assumptions holds true. It is impossible to show, at least in the context of mathematical sciences, that a certain claim holds true even if one were to show many examples that demonstrate its truth. Instead, a single argument must be provided. 
### Direct Proof
The proof of a proposition usually involves constructing a chain of arguments $A \implies C_{1} \implies \dots \implies C_{n} \implies  B$, where each element of the argument is either an axiom or proposition that has already been shown to be true. In the context of direct proofs, an important rule to take note of is the *classical rule of inference:* If $A$ is true and $A \implies B$ is true, then $B$ is also true. This is the most common way of demonstrating that a certain claim holds true. 
### Proof by Contradiction
There are cases where directly proving something is true is difficult. Another way to show that something is true is to assume that the conclusion is false, which is then followed by an explanation as to why it cannot be false. 
### Proof by the Contrapositive
An alternative to directly proving something is to assume to negate both the premise and conclusion, where they are then swapped in the implication. Thus, the contrapositive of $A \implies B$ is $\neg B \implies \neg A.$ This works because both the implication and its contrapositive are logically equivalent. 
### Useful Relations
Below are five simple but useful relations used in mathematical reasoning:
1. $\neg(A \wedge B) \iff \neg A \lor \neg B$. 
2. $\neg(A \lor B) \iff \neg A \wedge \neg B$. 
3. $(A \implies B) \iff (\neg B \implies \neg A)$
4. $(A \implies B) \iff (\neg A \lor B)$
5. $\neg(A \implies B) \iff (A \wedge \neg B)$

The truth tables of the following relations provide a quick look as to what statements are logically equivalent: 

| $A$   | $B$   | $\neg(A \wedge B)$ | $\neg A \lor \neg B$ | $\neg (A \lor B)$ | $\neg A \wedge \neg B$ | $A \implies B$ | $\neg B \implies \neg A$ |
| ----- | ----- | ------------------ | -------------------- | ----------------- | ---------------------- | -------------- | ------------------------ |
| True  | True  | False              | False                | False             | False                  | True           | True                     |
| True  | False | True               | True                 | False             | False                  | False          | False                    |
| False | True  | True               | True                 | False             | False                  | True           | True                     |
| False | False | True               | True                 | True              | True                   | True           | True                     |

| $\neg A \lor B$ | $\neg(A \implies B)$ | $A \wedge \neg B$ |
| --------------- | -------------------- | ----------------- |
| True            | False                | False             |
| False           | True                 | True              |
| True            | False                | False             |
| True            | False                | False             |
