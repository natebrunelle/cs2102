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

Super informally, the idea of this proof strategy is to say "Any time the theorem was false there must have been a prior time it was false as well, so there was no opportunity for it to start being false".

## Proof by Induction

If you recall from class, the Principle of Induction states "if $P(0)$ is true, and $P(n)\rightarrow P(n+1)$ for all natural numbers $n$, then $P(m)$ is true for all natural numbers $m$. The general template for how we use this idea to construct a proof that $\forall x\in \mathbb{N}. P(x)$ is as follows (though this may change slightly in some cases):

1. Begin by showing our base case, i.e. show that $P(0)$ is true.
2. Show the inductive case: $\forall n \in \mathbb{N}. P(n)\rightarrow P(n+1)$. This is typically done by:
3. Assume $P(n)$ is true for an arbitrary $n$.
4. By using the definition of $P$, show that it must also be the case that $P(n)$ is true.
5. Conclude by the Principle of Induction that $\forall n\in \mathbb{N}.P(n)$.

Note that more often (and more generally) induction is used to show $\forall x\in \big\{n \big| (y\in \mathbb{N})\wedge (y\geq b)\big\}. P(x)$ (i.e. that $P(x)$ is true for all natural numbers great than $b$) by instead doing the following:

1. Begin by showing our base case, i.e. show that $P(b)$ is true.
2. Show the inductive case: $\forall n \in \big\{y \big| (y\in \mathbb{N})\wedge (y\geq b)\big\}. P(n)\rightarrow P(n+1)$. This is typically done by:
3. Assume $P(n)$ is true for an arbitrary $n$.
4. By using the definition of $P$, show that it must also be the case that $P(n)$ is true.
5. Conclude by the Principle of Induction that $\forall x\in \big\{n \big| (y\in \mathbb{N})\wedge (y\geq b)\big\}. P(x)$.


Super informally, the idea of this proof strategy is to say "The theorem is true because once it's started being true it can't stop, and here where it starts being true".

# Proving Properties of Programs

# Recursion

# Towers of Hanoi
