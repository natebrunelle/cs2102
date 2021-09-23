---
title: Group Activity 1 | Entailment
...

# Introduce Your Group!

The first thing you're going to do is break up into a group of either 3 or 4. We will use $G$ to refer to the set of members in your group. Fill in the members of $G$ on your worksheet.

Next you're going to identify a set $F$ to make this statement true: 

$\forall x \in G. \forall y \in G. \exists f \in F. (x \neq y) \land A(x,f) \land A(y,f)$

Where $A(a,b)$: fun fact $b$ is true of group member $a$. 

In other words, for each pair of members of your group, find a fact that both members have in common. Fill in the members of $F$ on your worksheet, then identify which two members share each fact.


# What is Entailment?

So far when discussing proofs we've been showing that two statements are logically equivalent to one another. Sometimes when proving things we actually want to *draw conclusions* from statements. For example, consider the that the following statements are True:
 
- Nathan is not tall
- If Nathan is not good at basketball then Nathan is not good at football
- If Nathan is good at basketball then Nathan is tall.

From these statements, we are able to conclude that Nathan is not good at football through logical entailment as follows:

1. Considering the statement "Nathan is not tall" in the context of the statement "If Nathan is good at basketball then Nathan is tall" allows us to conclude that "Nathan is not good at basketball"
1. From our conclusion that "Nathan is not good at basketball", the statement "If Nathan is not good at basketball then Nathan is not good at football" allows us to finally conclude that "Nathan is not good at football".

How are we able to conclude this? When using entailments, I find it most helpful to think of it as answers to questions of the form "presuming some statement is true, what other statement must also be true?" Let's think formally about what we can conclude if we presume that both of "Nathan is not tall" and "If Nathan is good at basketball then Nathan is tall" are True. To begin, we translate these statements into propositions. If these are our atomic propositions:

- $T$: Nathan is tall
- $B$: Nathan is good at basketball
- $F$: Nathan is good at football

Then we can represent each of our original statements as the following compound propositions:

- $\lnot T$
- $\lnot B \rightarrow \lnot F$
- $B\rightarrow T$

Let's now look at a truth table for $\lnot T$ and $B\rightarrow T$:


    $B$ $T$ | $\lnot T$ | $B \rightarrow T$
    ----+----------------------
    0 0 |    1      1     1    
    0 1 |    1      1     1    
    1 0 |    1      0     0    
    1 1 |    1      1     1    

