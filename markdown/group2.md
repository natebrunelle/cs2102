---
title: Group Activity 1 | Closure
...

Put your answers for each problem of this activity in this [worksheet](/files/group2.pdf).

# Introduce Your Team!

The first thing you're going to do is break up into teams of either 4 or 5. We will use $T$ to refer to the set of members in your team. 
Fill in the members of $T$ on your worksheet (**problem 1**).


Next you're going to identify the relation $M$ over the set $T$ where $M(x,y):$ $x$ has the same birth month as $y$.(**problem 2**)



# Properties of relations

We identified several properties of relations in class. We recall those properties here:

## Reflexive

A relation is reflexive if *every* member of the domain of the relation relates to itself. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be reflexive if $\forall x\in D. R(x,x)$.

The following relations (with their domains) are reflexive:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \leq y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x = |y|$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,0), (1,1), (1,2), (2,1), (2,2), (2,3), (3,3), (4,4), (4,0) \big\}$

The following relations (with their domains) are not reflexive:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,1), (1,1), (1,2), (2,1), (2,2), (2,3), (4,4), (4,0) \big\}$

- the empty relation $R = \emptyset$.

## Irreflexive

A relation is irreflexive if *no* member of the domain of the relation relates to itself. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be irreflexive if $\forall x\in D. \lnot R(x,x)$. 

**Observe that irreflexive has a different meaning from "not reflexive"**. When expressed in first-order logic, we would write "not reflexive" as $\lnot \forall x\in D. R(x,x) \equiv \exists x\in D. \lnot R(x,x)$, which is not equivalent to the definition of irreflexive. It is the case that a relation being irreflexive entails that it is not reflexive, but it's important to see that the opposite (not reflexive entails irreflexive) is not true.

The following relations (with their domains) are irreflexive:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \neq |y|$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (1,1), (1,2), (2,1), (2,3), (4,0) \big\}$

- the empty relation $R = \emptyset$.


The following relations (with their domains) are not irreflexive:

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x \neq |y|$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,1), (1,1), (1,2), (2,1), (2,2), (2,3), (4,4), (4,0) \big\}$

Note that there are examples given in this section and the previous that are neither reflexive nor irreflexive.

## Symmetric

A relation is symmetric provided that for every pair that are related, their opposite order are related as well. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be symmetric if $\forall x\in D. \forall y \in D. R(x,y) \rightarrow R(y,x)$.

The following relations (with their domains) are symmetric:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x \neq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,1), (1,2), (2,1), (2,2), (2,3), (3,2), (4,0) \big\}$

- the empty relation $R = \emptyset$.

The following relations (with their domains) are not symmetric:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \leq y$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,1), (1,1), (1,2), (2,1), (2,2), (2,3), (4,4), (4,0) \big\}$

## Asymmetric

A relation is asymmetric provided that for every pair that are related, their opposite order are *not* related. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be asymmetric if $\forall x\in D. \forall y \in D. R(x,y) \rightarrow \lnot R(y,x)$.

**Observe that asymmetric has a different meaning from "not symmetric"**. When expressed in first-order logic, we would write "not symmetric" as $\lnot \forall x\in D. \forall y \in D. R(x,y) \rightarrow R(y,x) \equiv \exists x\in D.\exists y\in D. R(x,y) \land \lnot R(y,x)$, which is not equivalent to the definition of asymmetric. 

The following relations (with their domains) are asymmetric:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (2,3) \big\}$

- the empty relation $R = \emptyset$.

The following relations (with their domains) are not asymmetric:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \leq y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x \neq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (2,3), (3,2) \big\}$

Note that some examples here and in the previous section are neither symmetric nor asymmetric. (The empty relation is actually both, another time it might be wortwhile to think about whether that's the only one).

## Antisymmetric

A relation is anitsymmetric provided that for every non-equal pair that are related, their opposite order are *not* related. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be antisymmetric if $\forall x\in D. \forall y \in D. \big((x \neq y) \land R(x,y)\big) \rightarrow \lnot R(y,x)$.


Something that might be helpful in distinguishing between asymmetric and antisymmetric is that reflexive relations can be antisymmetric, but they cannot be asymmetric.


The following relations (with their domains) are antisymmetric:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \leq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (2,3), (3,3) \big\}$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the empty relation $R = \emptyset$.

The following relations (with their domains) are not antisymmetric:

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x \neq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (2,3), (3,2) \big\}$

## Transitive


A relation is transitive provided that for every two pairs of the form $(a,b)$, $(b,c)$ that are in the relation, the "shortcut" $(a,c)$ are in the relation as well. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be transitive if $\forall x\in D. \forall y \in D. \forall z \in D. \big(R(x,y) \land R(y,z)\big) \rightarrow  R(x,z)$.

The following relations (with their domains) are transitive:

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \lt y$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x \leq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (2,3), (3,3), (1,3) \big\}$

- the relation $R$ over $\mathbb{N}$ where $R(x,y): x = |y|$

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x = |y|$

- the empty relation $R = \emptyset$.

The following relations (with their domains) are not transitive:

- the relation $R$ over $\mathbb{Z}$ where $R(x,y): x \neq y$

- the relation $R$ over $A=\big\{ 0, 1, 2, 3, 4 \big\}$ where $R = \big\{ (0,4), (1,2), (3,3), (2,1) \big\}$




Identify the properties (of reflexive, irreflexive, symmetric, asymmetric, antisymmetric, and transitive) that your relation $M$ has (**problem 3**).

# Closure

We sometimes may come across situations where we have a relation that does not possess a certain property (e.g. it's not reflexive), but we want to modify the relation so that it does. For example, I might have a non-reflexive relation like "city $x$ relates to city $y$ provided there is a direct flight from $x$ to $y$". Unless planes are flying in circles, that relation is most likely going to be irreflexive. If, however, I was interested in the relation "city $x$ relates to city $y$ if someone can in $x$ can get to city $y$ without any layovers", then we might want the latter relation to be reflexive. 

For today's activity we'll be exploring this idea of closure, which means changing relations (specifically adding pairs) in order ensure they have a particular property.

## Reflexive Closure

## Symmetric Closure

## Transitive Closure

# Ball-Toss Closure Championship

## Symmetric Closure

## Reflexive Closure

## Transitive Closure


