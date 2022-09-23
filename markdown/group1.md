---
title: Group Activity 1 | Entailment
...

Read through this guide while completing today's [worksheet](/files/group1.pdf). The guide will direct you on when and how to fill in each box.  

# Introduce Your Group!

The first thing you're going to do is break up into a group of either 3 or 4. We will use $G$ to refer to the set of members in your group.  For **problem 1**, fill in the members of $G$ on your worksheet.

Next, consider the following set and predicates:

- $C$: The set of all courses being taught at UVA this semester
- $N(s,t)$: The predicate "$s$ is in $t$"

For **problem 2**, identify the truth value of each of the following propositions:

a. $\exists c\in C . \forall s \in G. N(s,c)$ 
a. $\forall c\in C . \exists s \in G. N(s,c)$ 
a. $\forall s \in G.\exists c\in C . N(s,c)$
a. $\exists s \in G.\forall c\in C . N(s,c)$


# What is Entailment?

So far when discussing proofs we've been showing that two statements are logically equivalent to one another. Sometimes when proving things, instead of demonstrating things are exactly equal to one another, we actually want to *draw meaningful conclusions* from a collection of facts. For example, suppose that all of the following statements are True:
 
- Nathan is not tall
- If Nathan is not good at basketball then Nathan is not good at football
- If Nathan is good at basketball then Nathan is tall.

From these statements, we are able to conclude that Nathan is not good at football through logical entailment as follows:

1. Considering the statement "Nathan is not tall" in the context of the statement "If Nathan is good at basketball then Nathan is tall" allows us to conclude that "Nathan is not good at basketball"
1. From our conclusion that "Nathan is not good at basketball", the statement "If Nathan is not good at basketball then Nathan is not good at football" allows us to finally conclude that "Nathan is not good at football".

How are we able to conclude this? We'll walk through two different (but equivalent) perspectives on entailment. From each perspective we explore what statements logically follow from other statements.


## Perspective 1: What else needs to be True?

We can think of entailment as answering questions of the form "presuming some statement is true, what other statement can we conclude *must* also be true?" Let's consider what we can conclude if we presume the truth of "*Nathan is not tall*" and "*If Nathan is good at basketball then Nathan is tall*". 

From an intuitive perspective, let's see why the conclusion "*Nathan is not good at basketball*" makes sense. When considering entailments, we start of by assuming that our original statements are absolutely and unquestionably True. In this example, we consider "*Nathan is not tall*" as absolutely and unquestionably True, and also "*If Nathan is good at basketball then Nathan is tall*" as absolutely and unquestionably True. Consider the case where "*Nathan _is_ good at basketball*" is true. Since "*Nathan is not tall*" is unquestionably True, the statement "*If Nathan is good at basketball then Nathan is tall*" becomes False, and so the only possible way for "*Nathan is not tall*" and "*If Nathan is good at basketball then Nathan is tall*" to be simultaneously True is for "*Nathan is not good at basketball*" to be True as well.

Let's now see how this looks with a more formal treatment.
To begin, we translate each statement into a proposition. If these are our atomic propositions:

- $A$: Nathan is tall
- $B$: Nathan is good at basketball
- $C$: Nathan is good at football

Then we can represent each of our original statements as the following compound propositions:

- $\lnot A$
- $\lnot B \rightarrow \lnot C$
- $B\rightarrow A$

Next we'll look at the truth tables these expressions. For **problem 3**, fill out the truth table in your worksheet. 

Now look through your truth table and identify all the rows where both $\lnot A$ and $B \rightarrow A$ are True. By doing this, you're looking at every situation where both of those statements are correct. Notice that in all such rows the value of $B$ is False. This means that in order for both of $\lnot A$ and $B \rightarrow A$ to be True, it's required that $B$ is False (i.e. if $B$ is True then at least one of $B \rightarrow A$ or $\lnot A$ must be False). In other words, from $(B \rightarrow A) \land \lnot A$ we can conclude $\lnot B$, or equivalently $(B \rightarrow A) \land \lnot A$ *entails* $\lnot B$, which we denote as $(B \rightarrow A) \land \lnot A \vdash \lnot B$. This rule is called *Modus Tolens* in our [list of logical entailments](/axioms.html).

To then conclude $\lnot C$ is True, we would look at all rows of the truth table where $\lnot B$ and $\lnot B \rightarrow \lnot C$ are both True, and see that in all cases $\lnot C$ must also be True, and so $( \lnot B \rightarrow \lnot C ) \wedge \lnot B \vdash \lnot C$. For **problem 4**, identify the name of this rule from our [list of logical entailments](/axioms.html).

## Perspective 2: Does this make that True?

Another way to think of entailment is as answering questions of the form "do these statements being true result in this other statement being true?" Again, to consider this formally we'll look at the same propositions as before:

- $\lnot A$
- $\lnot B \rightarrow \lnot C$
- $B\rightarrow A$

This time, though, we'll be building a different truth table to represent this new perspective. Saying that one proposition being True results in another being True is really just asserting something like "If *this* is True then *that* is also True", in other words, it's just an implication! With this second approach, to show $(B \rightarrow A) \land \lnot A \vdash \lnot B$ we would show that "if $B \rightarrow A$ and $\lnot A$ then $\lnot B$". To show such a statement formally we must show $\Big(\big( (B \rightarrow A) \land \lnot A \big)  \rightarrow \lnot B \Big) \equiv \top$.

 For **problem 5**, show that $\Big(\big( (B \rightarrow A) \land \lnot A \big)  \rightarrow \lnot B \Big) \equiv \top$ using either direct proof or Truth tables.

To then conclude $\lnot C$ we need to show $( \lnot B \rightarrow \lnot C ) \wedge \lnot B \vdash \lnot C$ by demonstrating that $\Big( \big( ( \lnot B \rightarrow \lnot C ) \wedge \lnot B \big) \rightarrow \lnot C \Big) \equiv \top$. You are not required to demonstrate this for today's group activity, but it may be of interest for you to do so on your own later.

# Using Entailment

Unlike with logical equivalence, entailment can only be applied in one direction. For example, we can use DeMorgan's law to transform the statement $\lnot P \land \lnot Q$ into $\lnot (P \lor Q)$ and also to transform $\lnot (P \lor Q)$ into $\lnot P \land \lnot Q$. We cannot assume $\lnot B$ and "work backwards" to conclude that $\lnot A$ is True (i.e. we can't guarantee that if Nathan is not good at basketball then Nathan is not tall, as perhaps he instead has poor hand-eye coordination).

Typically when writing proofs we're more concerned with which statements logically follow from others than we are with strict logical equivalence. Entailment relaxes the equivalence requirement and often makes proofs easier and more intuitive.

# Entailment Examples

**Problem 6**: Show that $(A \oplus B) \land B) \vdash \lnot A$ is a valid entailment. We recommend you first consider why it is valid on an intuitive level before formally showing its validity. Fill in your intuitive explanation in your worksheet.

**Problem 7**: First convert each English statement into compound propositions. Then use entailment to identify conclusions you can draw provided all of the following statements are True. Write at least conclusions in your worksheet.

- If Elizabeth is Dancing then she is happy.
- There is a mouse in the house or Elizabeth is happy.
- Elizabeth is sad.

# Cluedo

For **problem 8**, use entailment with the following statements to determine who killed Mr. Body. Identify the murderer in your worksheet.

1. Mr. Body was killed with a candlestick.
1. Either Miss Scarlet or Mrs. White was in the dining room at the time of the murder.
1. If Colonel Mustard was in the kitchen at the time of the murder, then Mr. Green killed Mr. Body with a revolver.
1. If Miss Scarlet was in the dining room at the time of the murder, then Mrs. Peacock killed Mr. Body.
1. If Colonel Mustard was not in the kitchen at the time of the murder, then Mrs. White was not in the dining room at the time of the murder.
1. If Mrs. White was in the dining room at the time of the murder, then Professor Black killed Mr. Body.
1. Either the candlestick was the murder weapon or else the revolver was.

We recommend that you use the following atomic propositions:

- $C$: The candlestick was the murder weapon
- $R$: The revolver was the murder weapon
- $S$: Miss Scarlet was in the Dining Room
- $W$: Mrs. White was in the Dining Room
- $M$: Colonel Mustard was in the Kitchen
- $G$: Mr. Green was the murderer
- $B$: Professor Black was the murderer
- $P$: Mrs. Peacock was the murderer


