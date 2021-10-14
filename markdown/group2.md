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



## Asymmetric

A relation is asymmetric provided that for every pair that are related, their opposite order are *not* related. Using first order logic, for relation $R$ over domain $D$ we define $R$ to be symmetric if $\forall x\in D. \forall y \in D. R(x,y) \rightarrow \lnot R(y,x)$.

**Observe that asymmetric has a different meaning from "not symmetric"**. When expressed in first-order logic, we would write "not symmetric" as $\lnot \forall x\in D. \forall y \in D. R(x,y) \rightarrow R(y,x) \equiv \exists x\in D.\exists y\in D. R(x,y) \land \lnot R(y,x)$, which is not equivalent to the definition of asymmetric. 

## Antisymmetric

## Transitive


Identify the properties (of reflexive, irreflexive, symmetric, asymmetric, antisymmetric, and transitive) that your relation $M$ has (**problem 3**).

# Closure

## Reflexive Closure

## Symmetric Closure

## Transitive Closure

# Ball-Toss Closure Championship




