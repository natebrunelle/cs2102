---
title: Group Activity 1 | Entailment
...

# Introduce Your Group!

The first thing you're going to do is break up into a group of either 3 or 4. We will use $G$ to refer to the set of members in your group. Fill in the members of $G$ on your worksheet (problem 1).

Next you're going to identify a set $F$ to make this statement true: 

$\forall x \in G. \forall y \in G. \exists f \in F. (x \neq y) \land A(x,f) \land A(y,f)$

Where $A(a,b)$: fun fact $b$ is true of group member $a$. 

In other words, for each pair of members of your group, find a fact that both members have in common. Fill in the members of $F$ on your worksheet, then identify which two members share each fact (problem 2).


# What is Entailment?

So far when discussing proofs we've been showing that two statements are logically equivalent to one another. Sometimes when proving things we actually want to *draw conclusions* from statements. For example, consider the that the following statements are True:
 
- Nathan is not tall
- If Nathan is not good at basketball then Nathan is not good at football
- If Nathan is good at basketball then Nathan is tall.

From these statements, we are able to conclude that Nathan is not good at football through logical entailment as follows:

1. Considering the statement "Nathan is not tall" in the context of the statement "If Nathan is good at basketball then Nathan is tall" allows us to conclude that "Nathan is not good at basketball"
1. From our conclusion that "Nathan is not good at basketball", the statement "If Nathan is not good at basketball then Nathan is not good at football" allows us to finally conclude that "Nathan is not good at football".

How are we able to conclude this? We'll walk through two different (but equivalent) perspectives on entailment. From either perspective we'll be exploring what statements logically follow from what other statements.


## Perspective 1: What else must be True?

We can think of entailment as answering questions of the form "presuming some statement is true, what other statement can we conclude must also be true?" Let's think formally about what we can conclude if we presume that both of "Nathan is not tall" and "If Nathan is good at basketball then Nathan is tall" are True. To begin, we translate these statements into propositions. If these are our atomic propositions:

- $T$: Nathan is tall
- $B$: Nathan is good at basketball
- $F$: Nathan is good at football

Then we can represent each of our original statements as the following compound propositions:

- $\lnot T$
- $\lnot B \rightarrow \lnot F$
- $B\rightarrow T$

Next we'll look at the truth tables these expressions. Fill out the truth table in your worksheet (problem 3). 

Now look through your truth table and identify all the rows where both $\lnot T$ and $B \rightarrow T$ are True. By doing this, you're looking at every situation where both of those statements are correct. Notice that in all such rows the value of $B$ is False. This means that in order for both of $\lnot T$ and $B \rightarrow T$, it's required that $B$ is False (i.e. if $B$ is True then at least one of $B \rightarrow T$ or $\lnot T$ must be False). In other words, from $(B \rightarrow T) \land \lnot T$ we can conclude $\lnot B$, or equivalently $(B \rightarrow T) \land \lnot T$ *entails* $\lnot B$, which we denote as $(B \rightarrow T) \land \lnot T \vdash \lnot B$. 

To then conclude $\lnot F$ we would look at all rows of the truth table where $\lnot B$ and $\lnot B \rightarrow \lnot F$ are both True, and see that in all cases $\lnot F$ must also be True, and so $( \lnot B \rightarrow \lnot F ) \wedge \lnot B \vdash \lnot F$.

## Perspective 2: Does this make that True?

Another way to think of entailment is as answering questions of the form "do these statements being true result in this other statement being true?" Again, to consider this formally we'll look at the same propositions as before:

- $\lnot T$
- $\lnot B \rightarrow \lnot F$
- $B\rightarrow T$

This time, though, we'll be building a different truth table to represent this new perspective. Saying that one proposition being True results in another being True is really just asserting something like "If this is True then that is also True", in other words, it's just an implication! With this second approach, to show $(B \rightarrow T) \land \lnot T \vdash \lnot B$ we would show that "if $B \rightarrow T$ and $\lnot T$ then $\lnot B$". To show such a statement formall we must show $\Big(\big( (B \rightarrow T) \land \lnot T \big)  \rightarrow \lnot B \Big) \equiv \top$.

Show that $\Big(\big( (B \rightarrow T) \land \lnot T \big)  \rightarrow \lnot B \Big) \equiv \top$ using either direct proof or Truth tables (problem 4).

To then conclude $\lnot F$ we need to show $( \lnot B \rightarrow \lnot F ) \wedge \lnot B \vdash \lnot F$ by demonstrating that $\Big( \big( ( \lnot B \rightarrow \lnot F ) \wedge \lnot B \big) \rightarrow \lnot F \Big) \equiv \top$. You are not required to demonstrate this for today's group activity, but it may be of interest for you to do so on your own later.

# Using Entailment

Unlike with logical equivalence, entailment can only be applied in one direction
