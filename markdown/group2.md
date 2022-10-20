---
title: Group Activity 2 | Closure
...

Put your answers for each problem of this activity in this [worksheet](/files/group2.pdf).

# Introduce Your Team!

The first thing you're going to do is break up into teams of either 4 or 5. We will use $T$ to refer to the set of members in your team. Introduce yourselves to your team members, then for **problem 1** fill in the members of $T$ on your worksheet. Select someone to read the next section aloud.

## Read This Aloud


Together we're going to create a relation $P$ over the set $T$. I'm going to count to three. Once I get to three everyone in the group (including myself) is going to point at one person in the group (another person or themselves). Once you point at someone, keep pointing at that person. We will use the pointing to define the relation $P(x,y):$ Person $x$ pointed at Person $y$. 

1, 2, 3, POINT!

I will now write down the the relation $P(x,y):$ Person $x$ pointed at Person $y$ for **problem 2**.

Finally, for **problem 3** we will together identify the properties that the relation $P$ satisfies.


# Closure

We sometimes may come across situations where we have a relation that does not possess a certain property (e.g. it's not reflexive), but we want to modify the relation so that it does. For example, I might have a non-reflexive relation like "city $x$ relates to city $y$ provided there is a direct flight from $x$ to $y$". Unless planes are flying in circles, that relation is most likely going to be irreflexive. If, however, I was interested in the relation "city $x$ relates to city $y$ if someone can in $x$ can get to city $y$ without any layovers", then we might want the latter relation to be reflexive. 

For today's activity we'll be exploring this idea of *closure*, which means changing relations (specifically adding pairs) in order ensure they have a particular property.

## Reflexive Closure

The *reflexive closure* of a relation is defined to be the smallest superset of a that relation that is reflexive. In other words, to perform the reflexive closure we want to add the fewest pairs required to make it reflexive. In this case, the pairs we need to add in are just all of the elements from our relation's domain paired with themselves. **Using first order logic, we can define the reflexive closure of relation $R$ over domain $D$ to be $R \cup \big\{ (x,x) | x\in D \big\}$.**

To see how this works, let's consider an example relation $R = \big\{ (0,0), (0,1), (0,2), (1,2), (1,5), (2,2), (2,3), (3,4), (4,3), (4,4), (5,5) \big\}$ over the domain $\{0, 1, 2, 3, 4, 5\}$. Note that $R$ is not reflexive, as to be reflexive we'd need to satisfy $\forall x\in D. (x,x)\in R$. In this case, we're missing $(1,1)$ and $(3,3)$. To make the smallest additions necessary to $R$ to make it reflexive, we therefore add in $(1,1)$ and $(3,3)$, and so the reflexive closure of $R$ is $\big\{ (0,0), (0,1), (0,2), (1,2), (1,1), (1,5), (2,2), (2,3), (3,3), (3,4), (4,3), (4,4), (5,5) \big\}$.

Here are some more examples of reflexive closures:

- The reflexive closure of the $\lt$ relation over $\mathbb{Z}$ is the $\leq$ relation

- The reflexive closure of the $\neq$ relation over $\mathbb{Z}$ will be $\mathbb{Z}^2$ (the relation where everything relates to everything else). 

- The reflexive closure the empty relation (where nothing relates to anything else) over domain $D$ is exactly $\big\{ (x,x) | x\in D \big\}$.

- The reflexive closure of any relation $R$ that is already reflexive is just that same relation $R$.


For **problem 4**, write out the reflexive closure of $P$.

## Symmetric Closure

The *symmetric closure* of a relation is defined to be the smallest superset of a that relation that is symmetric. In other words, to perform the symmetric closure we want to add the fewest pairs required to make it symmetric. In this case, the pairs we need to add in are just the reverses of all pairs already in the relation. **Using first order logic, we can define the symmetric closure of relation $R$ over domain $D$ to be $R \cup \big\{ (x,y) | (y,x)\in R \}$.**

To see how this works, let's consider the same example relation from before, $R = \big\{ (0,0), (0,1), (0,2), (1,2), (1,5), (2,2), (2,3), (3,4), (4,3), (4,4), (5,5) \big\}$ over the domain $\{0, 1, 2, 3, 4, 5\}$. Note that $R$ is not symmetric, as to be symmetric we'd need to satisfy $\forall x\in D.\forall y\in D. (x,y)\in R \rightarrow (y,x)\in R$. In this case, we're missing $(1,0)$, $(2,0)$, $(2,1)$, $(5,1)$, $(3,2)$, and $(4,3)$, since those are all missing opposites of pairs that belong to $R$. To make the smallest additions necessary to $R$ to make it reflexive, we therefore add in exactly those pairs, and so the summetric closure of $R$ is $\big\{ (0,0), (0,1), (1,0), (0,2), (2,0), (1,2), (2,1), (1,1), (1,5), (5,1), (2,2), (2,3), (3,2), (3,3), (3,4), (4,3), (4,4), (5,5) \big\}$

Here are some more examples of symmetric closures:

- The symmetric closure of the $\lt$ relation over $\mathbb{Z}$ is the $\neq$ relation

- The symmetric closure of the $\leq$ relation over $\mathbb{Z}$ will be $\mathbb{Z}^2$ (the relation where everything relates to everything else). 

- The symmetric closure of any relation $R$ that is already symmetric is just that same relation $R$.

- The symmetric closure the empty relation (where nothing relates to anything else) is just the empty relation (since it is already symmetric).

- The symmetric closure of the relation $L(x,y):$ "person $x$'s hands are on person $y$'s shoulers" might be "person $x$ and person $y$ are adjacent in the [Conga line](https://en.wikipedia.org/wiki/Conga_line)".

For **problem 5**, write out the symmetric closure of $P$.

## Transitive Closure

The *transitive closure* of a relation is defined to be the smallest superset of a that relation that is transitive. In other words, to perform the transitive closure we want to add the fewest pairs required to make it transitive. Transitive closures are much trickier than either reflexive or symmetric closures. Let's see why.


Consider the same example relation as before: $R = \big\{ (0,0), (0,1), (0,2), (1,2), (1,5), (2,2), (2,3), (3,4), (4,3), (4,4), (5,5) \big\}$ over the domain $\{0, 1, 2, 3, 4, 5\}$. To be transitive we need to satisfy $\forall x \in D. \forall y \in D. \forall z \in D. \big( (x,y)\in R \land (y,z)\in R\big) \rightarrow (x,z)\in R$. We can see that $R$ is not transitive as we're missing:

- $(0,5)$ (needed since we have $(0,1)$ and $(1,5)$)
- $(0,3)$ (needed since we have $(0,2)$ and $(2,3)$)
- $(1,3)$ (needed since we have $(1,2)$ and $(2,3)$)
- $(2,4)$ (needed since we have $(2,3)$ and $(3,4)$)
- $(3,3)$ (needed since we have $(3,4)$ and $(4,3)$)

So just as before, let's add in these 5 pairs to our relation, resulting in the new relation $R_2 = \big\{ (0,0), (0,1), (0,2), (0,3), (0,5), (1,2), (1,3), (1,5), (2,2), (2,3), (2,4), (3,3), (3,4), (4,3), (4,4), (5,5) \big\}$

However, notice that this new relation $R_2$ *still* isn't transitive, as we now have $(0,2)$ and $(2,4)$ but not $(0,4)$! The challenge we have is that completing all "transitive triples" can introduce new relations that create new incomplete "transitive triples", and so we need to keep going until the result is finally transitive. Next we're going to add:

- $(0,4)$ (needed since we have $(0,2)$ and $(2,4)$)
- $(1,4)$ (needed since we have $(1,2)$ and $(2,4)$)

Giving us $R_3 = \big\{ (0,0), (0,1), (0,2), (0,3), (0,4), (0,5), (1,2), (1,3), (1,4), (1,5), (2,2), (2,3), (2,4), (3,3), (3,4), (4,3), (4,4), (5,5) \big\}$, which is *finally* transitive, and therefore is the transitive closure of our original relation $R$.

In this case it took us 2 rounds of adding new pairs, but this gets even worse when we have an infinite domain. Consider the relation $P(x,y): x=y+1$ over the domain $\mathbb{Z}$. When we try and take the transitive closure of $P$, we'll need to add in $(0,2)$ since we previously had $P(0,1)$ and $P(1,2)$. Next we'll need to add $(0,3)$ since we had $P(0,2)$ and $P(2,3)$. Then we'll need to add $(0,4)$ since we had $P(0,3)$ and $P(3,4)$. Hopefully you can see the pattern, and notice that the transitive closure of $P$ is going to end up being the $\lt$ relation, but it's going to require an infinite number of steps to get there. Because of the possibility of needing an infinite number of steps, **it's actually impossible to write out a definition of transitive closure using first order logic!**


Here are some more examples of transitive closures:

- The transitive closure of the relation $P(x,y):x=y+1$ over $\mathbb{Z}$ is the $\lt$ relation

- The transitive closure of the relation $P(x,y):x=y-1$ over $\mathbb{Z}$ is the $\gt$ relation

- The transitive closure of the relation $P(x,y):$ "$x$ is a parent of $y$" over the set of all people is the relation "$x$ is an ancestor of $y$"

- The transitive closure of the $\neq$ relation over $\mathbb{Z}$ will be $\mathbb{Z}^2$. 

- The transitive closure of any relation $R$ that is already transitive is just that same relation $R$.

- The transitive closure the empty relation is just the empty relation (since it is already transitive).

- The transitive closure the $\lt$ relation is just the $\lt$ relation (since it is already transitive).

- The transitive closure of the relation $L(x,y):$ "person $x$'s hands are on person $y$'s shoulers" might be "person $x$ is behind person $y$ in the Conga line".

For **problem 6**, write out the transitive closure of $P$.

# University Hiring Puzzle

To get more experience with closures, we're going to give you a couple of challnge problems. For these challenge problems you will do the following:

1. Answer problems 3-6 with your team
1. Once you're done, find another team to verify that your solutions are correct
1. Solve problem 8 with your team.

The puzzles involve producing symmetric, reflexive, and transitive closures using the following relation. The domain of this relation is going to be the set of universities $\{ UVA, VT, VCU, ODU, JMU \}$. Which universities relate to each other depends on whether alumns from each university work at the same company and the year that person graduated.

We'll define a relation as follows: 

$R(m,n)$: An alumn of university $m$ works at the same company as a more recent graduate of university $n$.

$R(m,n):$ an employee of some company graduated from University $m$ before an a coworker at the same company graduated from University $n$.

For example, if a 1984 UVA grad and a 1996 VT grad work at the same company, then we say that UVA relates to VT, i.e. $R(UVA,VT)\equiv \top$.

For example, Suppose the following companies have the following employees:

![](files/universities_setup.png){ width=70% }

Which results in the relation $C = \big\{ (yellow,blue), (yellow, green), (green, blue), (purple, purple), (yellow, purple), (green, purple), (green, yellow), (green, green) \big\}$. (The first 3 pairs come from bin 1, then next 4 from bin 2, the last from bin 3.)

## Round 1: Reflexive Closure

To prepare for round 1 of the tournament, we will figure out how to add balls to bins to produce the Reflexive closure of the relation $C$ above. To start with, we'll first identify the pairs we need to add in order to make $C$ reflexive. Write down the missing pairs on your worksheet (**problem 3**).

Next add balls (with their numbers) to the bins in order to add those pairs, and only those pairs, to $C$. That is, add balls to bins so that the new relation is the reflexive closure of $C$ (**problem 4**). We were able to do this by adding 4 balls.

The 4 competitors will face off, tasked with numbering and tossing balls into bins to match this solution with the fewest throws possible.

## Round 2: Symmetric Closure

To prepare for round 1 of the tournament, we will figure out how to add balls to bins to produce the Symmetric closure of the original relation $C$ above (before we computed the reflexive closure). To start with, we'll first identify the pairs we need to add in order to make $C$ symmetric. Write down the missing pairs on your worksheet (**problem 5**).

Next add balls (with their numbers) to the bins in order to add those pairs, and only those pairs, to $C$. That is, add balls to bins so that the new relation is the symmetric closure of $C$ (**problem 6**). We were able to do this by adding 2 balls.

The 2 victors from Round 1 will face off, tasked with numbering and tossing balls into bins to match this solution with the fewest throws possible.


## Round 3: Transitive Closure

The victor for round 2 will face off with the professor to produce the transitive closure of the relation produced by this arrangement:

![](files/universities_setup_2.png){ width=70% }

that is $C=\big\{ (yellow, blue), (blue, purple), (purple, red), (red, green) \big\}$

As a class, we will determine how to number and add balls in order to produce the transitive closure of this new relation $C$ (**problem 7**).

# Appendix: Properties of relations

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

