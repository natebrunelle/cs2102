---
title: Logic Rules
...

# Equivalences

Two expressions are equivalent if they have the same truth valuation regardless of 

## Simplifications

Simplifications have the property that they make expressions smaller, with fewer operators and propositions.
They are equivalences so they also work backwards (i.e. making expressions larger), a process sometimes called "introduction", as in "we can introduce a double negation"

The first five are big and worth memorizing

 long                    simplified                 Name of rule
----------------------  ------------------------    ----------------------------
$\lnot \lnot P$         $P$                         double negation
$\lnot \top$            $\bot$                      definition of $\bot$
$P \land \bot$          $\bot$
$P \land \top$          $P$
$P \lor \bot$           $P$
$P \lor \top$           $\top$

and the rest are either less commonly useful or can be derived from the five above rules

| Operands |$\rightarrow$|$\leftrightarrow$|$\oplus$   |$\land$ |$\lor$  |
|:--------:|:-----------:|:---------------:|:---------:|:------:|:------:|
| $P$ op $P$       | $\top$    | $\top$    | $\bot$    | $P$    | $P$    |
| $P$ op $\lnot P$ | $\lnot P$ | $\bot$    | $\top$    | $\bot$ | $\top$ |
| $\lnot P$ op $P$ | $P$       | $\bot$    | $\top$    | $\bot$ | $\top$ |
| $\top$ op $P$    | $P$       | $P$       | $\lnot P$ | $P$    | $\top$ |
| $P$ op $\top$    | $\top$    | $P$       | $\lnot P$ | $P$    | $\top$ |
| $\bot$ op $P$    | $\top$    | $\lnot P$ | $P$       | $\bot$ | $P$    |
| $P$ op $\bot$    | $\lnot P$ | $\lnot P$ | $P$       | $\bot$ | $P$    |

## Associative and Commutative properties

A binary operator is commutative if its operands can be swapped without changing the meaning of the operation.
A binary operator is associative if a pair of them can be re-parenthesized without changing the meaning of their joint operation.

|Operator|Associativity|Commutativity|
|:------:|:-----------:|:-----------:|
|$\lnot$ |*not a binary operator*|*not a binary operator*|
|$\land$ |$(P \land Q) \land R \equiv P \land (Q \land R)$|$P \land Q \equiv Q \land P$|
|$\lor$ |$(P \lor Q) \lor R \equiv P \lor (Q \lor R)$|$P \lor Q \equiv Q \lor P$|
|$\oplus$ |$(P \oplus Q) \oplus R \equiv P \oplus (Q \oplus R)$|$P \oplus Q \equiv Q \oplus P$|
|$\rightarrow$|*not associative*|*not commutative*|
|$\leftrightarrow$|$(P \leftrightarrow Q) \leftrightarrow R \equiv P \leftrightarrow (Q \leftrightarrow R)$|$P \leftrightarrow Q \equiv Q \leftrightarrow P$|

Note that mixing associative operators does not create mutual associativity; for example $(P \land Q) \lor R$ is *not* equivalent to $P \land (Q \lor R)$.

When several associative operators are used, it is common to write them without parentheses;
for example, writing "$P \lor Q \lor R \lor S$" instead of "$P \lor \big(Q \lor (R \lor S)\big)$"

Parentheses can be changed in two ways:
either as allowed by associativity,
or because they are redundant and do not change the order of operations.
An example of redundant parentheses (i.e., not requiring associativity to change) are those around $P$ in the expression $(P) \rightarrow Q$,
which can be re-written as $P \rightarrow Q$ or $(((P \rightarrow ((Q)))))$ or any other parenthesization desired.

## Other equivalences

Of the other rules here, the first several are worth memorizing

 form 1                  form 2                                         Name of rule
----------------------  -------------------------------                 ----------------------------
$A \rightarrow B$       $\lnot A \lor B$                                definition of implication
$A \land (B \lor C)$    $(A \land B) \lor (A \land C)$                  Distributive law
$A \lor (B \land C)$    $(A \lor B) \land (A \lor C)$                   Distributive law
$(A \land B) \lor C$    $(A \lor C) \land (B \lor C)$                   Distributive law
$(A \lor B) \land C$    $(A \land C) \lor (B \land C)$                  Distributive law
$\lnot (A \land B)$     $(\lnot A \lor \lnot B)$                      De Morgan's law
$\lnot (A \lor B)$      $(\lnot A \land \lnot B)$                     De Morgan's law
$(A \leftrightarrow B)$ $(A \rightarrow B) \land (B \rightarrow A)$     definition of bimplication
$(A \oplus B)$          $(A \lor B) \land \lnot (A \land B)$            definition of exclusive or

and the rest are either less commonly useful or can be derived easily from other worth-memorizing rules

 form 1                      form 2                             Name of rule
----------------------      ---------------------------------   ----------------------------
$A \oplus B$                $\lnot (A \leftrightarrow B)$       
$A \leftrightarrow B$       $\lnot (A \oplus B)$                xnor
$P \rightarrow (A \lor Q)$  $(P \land \lnot A) \rightarrow Q$

# Entailments

## Logical entailment

Given                                                       Entails                         Name
-------------------------------------------------------     -----------------------------   --------------------
$\bot$                                                      ${x}$
                                                            ${\top}$
                                                            ${A \lor \lnot A}$              excluded middle
$A \land B$                                                 ${A}$
$A$ and $B$                                                 ${A \land B}$
$A$                                                         ${A \lor B}$
$A \lor B$ and $\lnot B$                                    ${A}$                           disjuctive syllogism
$A \rightarrow B$ and $B \rightarrow C$                     ${A \rightarrow C}$             hypothetical syllogism; transitivity of implication
$A \rightarrow B$ and $A$                                   ${B}$                           modus ponens
$A \rightarrow B$ and $\lnot B$                             ${\lnot A}$                     modus tolens
$A \leftrightarrow B$                                       ${A \rightarrow B}$
${A \rightarrow C}$, ${B \rightarrow C}$, and ${A \lor B}$  ${C}$
${A \rightarrow B}$, ${C \rightarrow D}$, and ${A \lor C}$  ${B \lor D}$
$A \rightarrow B$                                           ${A \rightarrow (A \land B)}$
$\lnot(A \land B)$, $A$                                     ${\lnot B}$

## Assume-and-prove entailment

A proof that assumes $A$ and derives $B$ entails that $A \rightarrow B$. This is commonly used in the inductive step of a proof by induction.

$$\begin{matrix}
& A \vdash B\\
\therefore & A \rightarrow B
\end{matrix}$$

A proof that assumes $A$ and derives $\bot$ entails that $\lnot A$. This is called "proof by contradiction" or "indirect proof."

$$\begin{matrix}
& A \vdash \bot\\
\therefore & \lnot A
\end{matrix}$$

A proof $x \in S \vdash P(x)$ entails $\forall x \in S \;.\; P(x)$. This is called "universal instantiation".

$$\begin{matrix}
& x \in S \vdash P(x)\\
\therefore & \forall x \in S \;.\; P(x)
\end{matrix}$$

If $P(x)$ and $x$ is some specific member of $S$, that entails $\exists x \in S \;.\; P(x)$. This is called "existential instantiation".

$$\begin{matrix}
& x \in S\\
& P(x)\\
\therefore & \exists x \in S \;.\; P(x)
\end{matrix}$$


## Set entailment

Given                                                       Entails
-------------------------------------------------------     -----------------------------
$P(x)$ and $x \in S$                                        $\exists x \in S \;.\; P(x)$
$\forall x \in S \;.\; P(x)$ and $T \subseteq S$            $\forall x \in T \;.\; P(x)$
$\exists x \in S \;.\; P(x)$ and $T \supseteq S$            $\exists x \in T \;.\; P(x)$
$\forall x \in S \;.\; P(x)$ and $S \neq \emptyset$         $\exists x \in S \;.\; P(x)$
$|S| \neq |T|$                                              $S \neq T$
$|S| < |T|$                                                 $S \not \supseteq T$
$\exists x \in S \;.\; P(x)$                                $S \neq \emptyset$


## Qualified entailments

Given                             Entails                                                               Names
--------------------------------  -----------------------------                                         ------
$\forall x \in S \;.\; P(x)$      $P(s)$, for any $s \in S$ we care to pick                             universal instantiation
$\exists x \in S \;.\; P(x)$      $s \in S \land P(s)$ where $s$ is an otherwise-undefined new variable existential instantiation 
$s \in S \vdash P(s)$             $\forall x \in S \;.\; P(x)$                                          universal generalization
$P(s) \land s \in S$              $\exists x \in S \;.\; P(x)$                                          existential generalization

These also all have versions that use a defined domain instead of set membership.
Universal generalization is sometimes called "skolemization."


# Mathematical Identities

The following are all true for all real numbers where both sides of the equals sign are defined:

- $\displaystyle \log_a(a^x) = x$
- $\displaystyle a^{\log_a(x)} = x$
- $\displaystyle \log_a(x y) = \log_a(x) + \log_a(y)$
- $\displaystyle \log_a\left(\frac{x}{y}\right) = \log_a(x) - \log_a(y)$
- $\displaystyle \log_a(x^y) = y \log_a(x)$
- $\displaystyle \log_a(x) = \frac{\log_b(x)}{\log_b(a)}$
- $\displaystyle \log_{a^b}(x) = b^{-1}\log_a(x)$

The following are also true:

- $(a \in \mathbb Z) \land (a > 1) \vDash (a$ has at least two factors$)$
- $(a \in \mathbb Z) \land (a > 1) \land (a$ has exactly two factors$) \equiv (a$ is prime$)$
- Each integer greater than 1 has exactly one prime factorization

