---
title: Group Activity 3 | Well-Ordering, Induction, Recursion
...

Put your answers for each problem of this activity in this [worksheet](/files/group3.pdf).

# Introduce Your Team!

 (**problem 1**).

# Induction and Well-Ordering

Over the last two weeks we have discussed two ways of proving theorems like $\forall x\in \mathbb{N}. P(x)$ -- proof by induction and proof by contradiction using Well-Ordering. During this week's group activity we will explore the relationship between these two strategies, and apply them to some new situations.




## Proof by Contradiction Using Well-Ordering

If you recall from class, the Well-Ordering Principle states "Every non-empty subset of the Natural numbers has a least element". The general template for how we use this idea to construct a proof that $\forall x\in \mathbb{N}. P(x)$ is as follows (though this may change slightly in some cases):

1. Begin by assuming the negation of our theorem toward reaching a contradiction. That is, assume $\lnot\big(\forall x\in \mathbb{N}. P(x)\big)\equiv \big( \exists x \in \mathbb{N}. \neg P(x)\big)$. In English, this states that if it isn't the case that $P(x)$ holds for all natural numbers, then some natural number will be a counterexample.
2. Define a set of counterexamples. That is, define $C = \big\{ x | (x\in \mathbb{N}) \wedge \neg P(x) \big\}$. 
3. Our assumption in step 1 means that $C \neq \emptyset$.
4. Our definition of $C$ in step 2 guarantees $C\subseteq \mathbb{N}$ and our observation in step 3 states that $C\neq \emptyset$, therefore the Well-ordering Principle must apply to $C$. This allows us to conclude that $C$ has a least member.
5. We show that $0\notin C$ by showing $P(0)$.
6. We show $\forall n\in \mathbb{N}\setminus \{0\}. (n\in C) \rightarrow (n-1 \in C)$.
7. We observe that steps 4, 5, and 6 together form a contradiction, since every member of $C$ (except 0) has a member of $C$ smaller than it, the only way to have a smallest member is for that to be 0, which showed was not a member of $C$.
8. This contradiction requires therefore that $C=\emptyset$, or equivalently that $\forall x\in \mathbb{N}. P(x)$.



## Proof by Induction




# Proving Properties of Programs

# Recursion

# Towers of Hanoi
