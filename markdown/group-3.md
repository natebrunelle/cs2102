---
title: Group Activity 3 | Well-Ordering, Induction, Recursion
...

Put your answers for each problem of this activity in this [worksheet](/files/group3.pdf).

# Introduce Your Team!

Give the names of all members of your group. Put a star next to a group member's name if that person is struggling with course enrollment for Spring 2022. (**problem 1**).

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

## Comparing the strategies

It turns out that proofs by induction and proofs by contradiction using well-ordering are very closely related to one another (and in a very formal sense they are logically equivalent to one another). To get a vague idea for why, we can first of all look at the most important components of each proof. For a proof my contradiction using well-ordering, we need to show $\neg P(n) \rightarrow \neg P(n-1)$, or equivalently $\neg P(n+1) \rightarrow \neg P(n)$. For a proof by induction we need to show $P(n)\rightarrow P(n+1)$. These two statements are logically equivalent to one another. Show this using logical equivalences (**Problem 2**).

These proofs techniques are equivalent in that you can transform any proof by contradiction using well-ordering into a proof by induction by showing using the demonstration that $0\notin C$ as your proof of the base case $P(0)$, then using your proof that $\neg P(n) \rightarrow \neg P(n-1)$ as your inductive case since it is equivalent to $P(n)\rightarrow P(n+1)$. 

You can similarly transform any proof by induction into a proof by contradiction by well ordering by using your proof that the base case ($P(0)$) holds to show $0 \notin C$, and then using your proof that $P(n)\rightarrow P(n+1)$ in your inductive step as the proof of the logically equivalent statement $\neg P(n) \rightarrow \neg P(n-1)$. Everything else in these proof strategies are just structural pieces that will be the same among *all* proofs that use the respective strategy!

To see this transformation, consider the following proofs that $\neg P(n) \rightarrow \neg P(n-1)$ (that might be part of a proof by contradiction using well-ordering) and that $P(n)\rightarrow P(n+1)$ (that might be the inductive case in a proof by induction). Briefly explain how we transformed the first proof into the second (**Problem 3**).


{.example ...}$\neg P(n) \rightarrow \neg P(n-1)$

:::proof
Suppose $\neg P(n)$, i.e., $\Sigma_{i=0}^{n} i \neq \frac{n(n+1)}{2}$. By algebra, we therefore have:  
$\Sigma_{i=0}^{n} i \neq \frac{n(n+1)}{2}$  
$n+ \Sigma_{i=0}^{n-1} i \neq \frac{n(n+1)}{2}$  
$\Sigma_{i=0}^{n-1} i \neq \frac{n(n+1)}{2}-n$  
$\Sigma_{i=0}^{n-1} i \neq \frac{n(n+1)}{2}-\frac{2n}{2}$  
$\Sigma_{i=0}^{n-1} i \neq \frac{n(n+1)-2n}{2}$  
$\Sigma_{i=0}^{n-1} i \neq \frac{n(n+1-2)}{2}$  
$\Sigma_{i=0}^{n-1} i \neq \frac{n(n-1)}{2}$  
$\Sigma_{i=0}^{n-1} i \neq \frac{(n-1)(n+1-1)}{2}$  
:::
{/}

{.example ...}$P(n)\rightarrow P(n+1)$

:::proof
Suppose $P(n)$, i.e. $\Sigma_{i=0}^{n} i \neq \frac{n(n+1)}{2}$. Let $n=m-1$. By algebra, we therefore have:  
$\Sigma_{i=0}^{n} i = \frac{n(n+1)}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{(m-1)(m+1-1)}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{m(m-1)}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{m(m+1-2)}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{m(m+1)-2m}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{m(m+1)}{2}-\frac{2m}{2}$  
$\Sigma_{i=0}^{m-1} i = \frac{m(m+1)}{2}-m$  
$m+ \Sigma_{i=0}^{m-1} i = \frac{m(m+1)}{2}$  
$\Sigma_{i=0}^{m} i = \frac{m(m+1)}{2}$  
$\Sigma_{i=0}^{n+1} i = \frac{(n+1)(n+1+1)}{2}$  
:::
{/}

# Proving Properties of Programs

We've probably gone on long enough in this course without applying things we've learned directly to something discernable as computer science, so let's apply induction and well-ordering to code! It's very often the case that you can use these proof strategies to prove things about code. We'll look at two applications: code correctness ("How can we show that a function returns the right answer?") and code termination ("How can we show that our program is not stuck in an infinite loop?").

## Code Termination

To prove that a function terminates, it's typically easiest to do this via proof by contradiction using well-ordering. We'll work together to show that the following code (which happens to computes greatest common divisors, though that's not obvious) is guaranteed to halt for any natural numbers given as input.

{.example ...}
Consider this code for finding the greatest common divisor of two natural numbers:

<table><tr><th>Python</th><th>Java</th></tr><tr><td valign="top">
```python
def gcd(x,y):
    if y == 0:
        return x
    r = x % y
    return gcd(y,r)
        
```                          
</td><td valign="top">
```Java
int gcd(int x, int y){
    if (y == 0){
        return x;
    }
    int r = x % y;
    return gcd(y,r);
}
```
</td></tr></table>
{/}

To prove that this code always terminates using well-ordering, we first need to identify a predicate $P$ so that we can state a theorem of form $\forall n\in \mathbb{N}. P(n)$. In this case we'll define $P(n)$: "The program terminates for $y=n$". We won't give the entire proof here, but we'll together prove the most important pieces. To begin, show that $P(0)$ is true (**Problem 4**).

Finally, to show that this program will terminate, we need to show that if there is some natural number $n$ for which the function does not terminate, then there must be some smaller natural number $m$ for which it doesn't terminate as well[^1]. Explain how we know this is the case (**Problem 5**).

[^1]: Note that this is slightly different from how we derived a contradiction above. Before we said we wanted to show $\neg P(n)\rightarrow \neg P(n-1)$. The contradiction will actually still work if we show $\neg P(n)$ implies $P(m)$ for any choice of $m \lt n$.

Make sure everyone in your group understands why these two together would allow us to conclude that the code always terminates.

## Code Correctness

To show that code always produces the correct answer, we will more often use induction. We'll prove that the code below correctly finds the maximum value in a list of natural numbers.

{.example ...}
Consider this code for finding the maximum item in a list of natural numbers:

<table><tr><th>Python</th><th>Java</th></tr><tr><td valign="top">
```python
def find_max(my_list):
    m = 0
    for i in my_list:
        if i > m:
            m = i
    return m
```                          
</td><td valign="top">
```Java
int find_max(int[] my_list){
    int m = 0;
    for (int i : my_list){
        if (i > m){
          m=i;
        }
    }
    return y;
}
```
</td></tr></table>
{/}

To prove that this code always terminates using induction, we first need to identify a predicate $P$ so that we can state a theorem of form $\forall n\in \mathbb{N}. P(n)$. In this case we'll define $P(n)$: "after looking at the $n$th element in the list, $m$ is equal to the maximum of those elements". To begin, show a base case that $P(1)$ is true (**Problem 6**).

Next show the inductive step, the $P(n)\rightarrow P(n+1)$ (**Problem 7**). 

Make sure everyone in your group understands why these two together would allow us to conclude that the code correctly finds the maximum of the list.

# Tower of Hanoi

According to ancient legend, somewhere in Hanoi there is a temple in Hanoi, and in this temple there are 3 pillars and 64 disks. Each disk is a unique diameter, has a hole through the middle, and are placed in a stack over the first pillar. This stack is arranged so that the largest disc is at the bottom and the smallest is at the top (and all other disks are similarly ordered by diameter in between). A group of monks are tasked with moving all 64 disks from the first pillar to the third. The challenge is, though, that the monks can only move one disk at a time and no disk may ever be atop a disk smaller than it. If the monks can move one disk per second, how long will it take for them to move all of the disks?

You have a set of 4 disks (or if you're completing this at home, make 4 disks of unique diameter, pancakes sound good). With your group, determine the number of moves it will take for the monks to move a stack of 4 disks (**Problem 8**). To do this, I recommend first considering the number of moves that will be required to move a stack of 1 disk, then 2 disks, then 3, and finally 4.

Next, guess a formula that would represent the number of moves required for the monks to move $n$ disks (**Problem 9**).

Finally, use induction to show that your answer for Problem 9 is correct (**Problem 10**). Here's a hint for how you might do this. The number of moves required to move all $n$ disks is going to be the number of moves required to move $n-1$ disks (to free the largest disk), plus one (to move the largest disk), plust the number of moves required to move $n-1$ disks again (to put all disks back atop the largest). In other words, the number of moves required should match the return value of the following function.

{.example ...}
A function which computes the number of moves required to move a stack of n disks

<table><tr><th>Python</th><th>Java</th></tr><tr><td valign="top">
```python
def hanoi(n):
    if n == 1:
        return 1
    return 2*hanoi(n-1)+1
```                          
</td><td valign="top">
```Java
int hanoi(int n){
    if (n == 1){
        return 1;
    }
    return 2*hanoi(n-1)+1;
}
```
</td></tr></table>
{/}

