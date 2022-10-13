---
title: Structures
...

This page attempts to provide a summary of all of the discrete structures that will be used in this class.

# Propositional logic

What in programming is called a Boolean expression (i.e., an expression that evaluates to either `true` or `false`) is called a **proposition** in mathematical logic.
When propositions are represented by a symbol, that symbol is almost always a single upper-case letter, optionally with a numeric subscript, like $P$ or $P_{23}$.

There are two logical values and many logical operators;
the three best known operators are shown in the following table
together with various symbols used to represent them.

Concept          Java/C++    Python      This class                      Bitwise    Other
--------        ----------  --------    ---------------------------     ---------   ------
true            `true`      `True`      $\top$ or $1$                   `-1`        T, tautology
false           `false`     `False`     $\bot$ or $0$                   `0`         F, contradiction
not $P$         `!p`        `not p`     $\lnot P$ or $\overline{P}$     `~p`
$P$ and $Q$     `p && q`    `p and q`   $P \land Q$                     `p & q`     $P Q$, $P \cdot Q$
$P$ or $Q$      `p || q`    `p or q`    $P \lor Q$                      `p | q`     $P + Q$

$\lnot$ has higher precedence than $\land$ and $\lor$;
thus $(\lnot P \land Q)$ means $\big((\lnot P) \land Q\big)$ not $\color{darkred} \big(\lnot (P \land Q)\big)$.
It is typical not to define the precedence of $\land$ and $\lor$ compared to one another, and to require parentheses if they both appear together; thus $\color{darkred} (P \land Q \lor R)$ has undefined meaning and must not be written; use $\big((P \land Q) \lor R\big)$ or $\big(P \land (Q \lor R)\big)$ instead.

Because $\land$ and $\lor$ are associative, it does not matter in what order an expression like $(P \land Q \land R)$ is evaluated; it is equivalent to both $\big((P \land Q) \land R\big)$ and $\big(P \land (Q \land R)\big)$.

We also discuss other boolean operators in this class, including $\rightarrow$, $\oplus$, and $\leftrightarrow$,
as well as many properties of and techniques for manipulating logical expressions.

# First-order Logic

A [function] that evaluates to either true or false is called a **predicate**.
The **variables** used in a predicate are almost always represented by a single lower-case letter, optionally with a numeric subscript, like $x$ or $x_{23}$.

:::example
$P(x,y) = (x < y)$ is a predicate.
$P(3, 2)$ is proposition made from that predicate, and is in particular equivalent to $\bot$.
:::

The notation $\forall x \in S \;.\; P(x)$ is read "for all $x$ in $S$, $P(x)$", where $S$ is a [set] and $P$ is a predicate. The full expression is called a **universally quantified** statement and is itself a proposition, which is true if and only if $P(x)$ is true for every $x$ in $S$. If $S$ is empty, $\forall x \in S \;.\; P(x)$ is trivially true.

The notation $\exists x \in S \;.\; P(x)$ is read "there exists some $x$ in $S$ such that $P(x)$", where $S$ is a set and $P$ is a predicate. The full expression is called an **existentially quantified** statement and is itself a proposition, which is true if and only if $P(x)$ is true for at least one $x$ in $S$. If $S$ is empty, $\exists x \in S \;.\; P(x)$ is trivially false.

A variable defined by a quantifier is considered to be **bound** from the period following the quantifier until the end of the expression, or until the end of the parenthetical in which the quantifier appeared;
that portion of the expression is called the variable's **scope**.
A variable must not be bound more than once inside the same scope.

A quantifier may omit the set, as $\forall x \;.\; P(x)$; in this usage there is an implicit set, sometimes called the **domain** or the **universe of discourse**, which the variable is assumed to be quantified over. Quantifiers in this form may only be used if the domain is specified or may be inferred from context.

Adjacent quantifiers may be combined with commas as a shorthand, but only if they are the same quantifier; $\forall$ and $\exists$ cannot be combined.

:::example
$\forall x \in A\;.\; \forall y \in B \;.\; P(x,y)$
can also be written 
$\forall x \in A, y \in B\;.\; P(x,y)$

$\forall x \in A\;.\; \forall y \in A \;.\; P(x,y)$
can also be written 
$\forall x,y \in A\;.\; P(x,y)$

$\forall x \in A\;.\; \exists y \in A \;.\; P(x,y)$
cannot be abbreviated further because $\forall$ and $\exists$ are different quantifiers.
:::

Quantifiers have lower precedence than any propositional logic operator.

:::example
The expression
$\forall x \in S \;.\; \exists y \in T\;.\; x \lor y$
means 
$\forall x \in S \;.\; \big(\exists y \in T\;.\; (x \lor y)\big)$
not
$\color{darkred} \big(\forall x \in S \;.\; (\exists y \in T\;.\; x) \lor y\big)$
or
$\color{darkred} \big(\forall x \in S \;.\; (\exists y \in T\;.\; x)\big) \lor y$.
:::

We also discuss the quantifier $\nexists$ and various properties of quantifiers and quantified statements in this class.


# Set

A **set** is a value whose only property is having other values as its **members**.
The most common representation of a set is as its members written between braces.
The members of a set have no position, order, number of times appearing in the set, or any other properties beyond being a member of the set.

The number of distinct members of a set $S$ is called the set's **cardinality** and is denoted $|S|$.
A set with cardinality 1 is sometimes called a **singleton set**.

:::example
The set $\{2,3,5,7\}$ has cardinality 4; its members are $2$, $3$, $5$, and $7$.
This same set can equivalently be written $\{3,7,2,5\}$ or with its members in any other order.

The notation $\{2,2,3\}$ is nonsensical; it asserts $2$ and $3$ are members of the set, which is fine,
but also asserts $2$ is a member of the set twice, which doesn't make sense.
It's a bit like writing 03 instead of 3: $\{2,2,3\}$ means $\{2,3\}$ but is written oddly,
and if we don't have some reason to expect it from context we'd assume it was a typo or other error.
:::

The empty set has no members and is denoted either $\{\}$ or $\emptyset$.
Note that $\emptyset$ (the empty set, also called the null set) is a different symbol than $0$ (zero) or $\phi$ (the Greek letter phi).

The expression $x \in S$ is true if and only if $x$ is a member of $S$ (and thus only if $S$ is a set).
$x \notin S = \lnot(x \in S)$.

A set can be defined based on any [predicate](#function)
using **set-builder notation**:
$\big\{ f(x) \;\big|\; P(x)\big\}$ is the set of all $f(x)$ where $P(x)$ is true.

:::example
$\{ x+2 \;|\; 1 < x \le 2 \}$ is the set of all numbers greater than 3 and no greater than 4.

$x \in \big\{x\;\big|\;P(x)\big\}$ is a long way of writing $P(x)$.

$\big\{x\;\big|\;x \in S\big\}$ is a long way of writing $S$.
:::

The following set operators are defined:

Union
:   $S \cup T = \big\{x \;\big|\; (x \in S) \lor (x \in T)\big\}$

Intersection
:   $S \cap T = \big\{x \;\big|\; (x \in S) \land (x \in T)\big\}$

Set Difference
:   $S \setminus T = \big\{x \;\big|\; (x \in S) \land (x \notin T)\big\}$

The following set-comparison predicates are defined:

Subset
:   $S \subseteq T = \forall x \in S \;.\; x \in T$

Proper Subset
:   $S \subset T = (S \subseteq T) \land (S \ne T)$

Superset
:   $S \supseteq T = T \subseteq S$

Proper Subset
:   $S \supset T = T \subset S$

The **power set** of another set $S$ is the set of all the subsets of $S$.
The *power set* is denoted $\mathcal P(S)$ or pow($S$)
and can also be written $\{ T \;|\; T \subseteq S\}$.

$\big|\mathcal P(S)\big|  = 2^{\big|S\big|}$.

The number of distinct $k$-member subsets of a $n$-member set is denoted $\displaystyle{ n \choose k }$, read "$n$ **choose** $k$", and is equal to $\displaystyle{ n! \over (n-k)! k! }$,
where $x!$ is the [factorial](#summation) of $x$.

:::example
The power set of $\{1,2,3\}$ is 
$\big\{ 
\{\},
\{1\},
\{2\},
\{3\},
\{1,2\},
\{1,3\},
\{2,3\},
\{1,2,3\}
\big\}$, which has $2^3 = 8$ members, each a subset of $\{1,2,3\}$.

The set of two-element subsets of $\{1,2,3,4,5\}$,
which can be formally written as $\Big\{S \;\Big|\; \big(S \subseteq \{1,2,3,4,5\}\big) \land \big(|S| = 2\big)\Big\}$,
has 
$\displaystyle{5 \choose 2} = {5! \over 3! 2!} = {5 \cdot 4 \over 2} = 10$ members
and is
$\big\{
\{1,2\},
\{1,3\},
\{1,4\},
\{1,5\},
\{2,3\},
\{2,4\},
\{2,5\},
\{3,4\},
\{3,5\},
\{4,5\}
\big\}$
:::

# Sequence

A **sequence** or **tuple** is a value which contains zero or more other values inside it, commonly called its **elements** or **items**.
The *elements* of a *sequence* are in a specific order,
and each may appear any number of times.
The most common representation of a sequence is as its elements written in order, left to right, between parentheses.

In computing it is somewhat more common to use the term "sequence" when all of the elements are taken from the same [set]
and "tuple" when they are taken from different sets.
However, this tradition is not universally observed.
We use both terms interchangeably in this course.

The number of elements of a sequence is called the sequence's **length**.
A sequence with length 1 is sometimes called a **singleton sequence**.

:::example
The sequence $(2,1,0,2)$ has length 4.
It is a different sequence than $(0,1,2,2)$.
:::

The empty sequence can be denoted $()$, $\epsilon$, or $\varepsilon$.
Note that $\epsilon$ (Greek letter epsilon, the empty sequence) and $\in$ (the set member-of operator) are distinct symbols. 
The symbols $\epsilon$ and $\varepsilon$ are both lower-case Greek epsilons, just written in two different ways.
Because epsilon is also a common symbol in computing (though not in this class) for "a small nonzero value," it is useful to have two different epsilon symbols to choose from.

A sequence of length 2 is called a **pair**.
A sequence of length 3 is sometimes called a triple, but that term is not commonly used in computing.
There are names for longer sequences too, but they are rarely used.

If two sequences have the same elements but in different order,
they are called **permutations** of one another.
The number of permutations of a sequence
is the factorial of the length of the sequence
divided by the product of the factorials of the number of copies of each value in the sequence.

:::example
The sequence $(2,1,0,2)$ has length 4.
It has $\displaystyle{ {4! \over 2! 1! 1!} = 12}$ permutations:
$(0,1,2,2)$, 
$(0,2,1,2)$,
$(0,2,2,1)$,
$(1,0,2,2)$, 
$(1,2,0,2)$,
$(1,2,2,0)$,
$(2,0,1,2)$, 
$(2,0,2,1)$,
$(2,1,0,2)$,
$(2,1,2,0)$, 
$(2,2,0,1)$, and
$(2,2,1,0)$.

The sequence $\big(1,1,1,\{1\},\{1\},\{1\},\{1\},(),(),(),(),()\big)$
has $\displaystyle{ {12! \over 3! 4! 5!} = 27,720 }$ permutations.
:::

The **Cartesian product** of two sets $S \times T$ is the set of all pairs where the first element comes from $S$ and the second from $T$;
that is, $S \times T = \big\{(s,t) \;\big|\; s \in S \land t \in T\big\}$.
Cartesian product is commonly treated as a variable-arity operator,
such that $S \times T \times U$ is a set of triples
but $(S \times T) \times U$ and $S \times (T \times U)$ are both sets of pairs.

:::example
$\{1,2\} \times \{4,5,6\}$ is $\big\{(1,4),(1,5),(1,6),(2,4),(2,5),(2,6)\big\}$.

$\{1\} \times \{2\} \times \{3\}$ is $\big\{(1,2,3)\big\}$.

$\big(\{1\} \times \{2\}\big) \times \{3\}$ is $\Big\{\big((1,2),3\big)\Big\}$.

$\{1\} \times \big(\{2\} \times \{3\}\big)$ is $\Big\{\big(1,(2,3)\big)\Big\}$.
:::

The **Cartesian power** is defined analogously to the power in mathematics: $S^k = \overbrace{S\times S\times\dots\times S}^{k\text{~}S\text{s}}$.
In other words, $S^k$ is the set of all sequences of length $k$
where all elements of each sequence in the set are members of $S$.

For all finite sets $S$ and $T$, $|S^k| = |S|^k$ and $|S \times T| = |S| \cdot |T|$

The **Kleene star** is the union of all Cartesian powers, $S^* = S^0 \cup S^1 \cup S^2 \cup S^3 \cup \dots$.
In other words, $S^*$ is the set of all sequences where all elements of each sequence in the set are members of $S$.
More formally, $S^* = \big\{x\;\big|\;\exists k \in \mathbb N \;.\; x \in S^k\big\}$.

:::example
$\{1,2\}^4$ contains $(1,1,1,1)$, $(2,2,1,1)$, and 14 other sequences.

$\{1,2\}^*$ contains $()$, $(1,1)$, $(2,2,1,1,2,1,2)$, and infinitely many other sequences.
:::

In most (but not all) contexts, a value and a singletone sequence containing just that value are treated as being equal (i.e. $x = (x)$).
There is no standard way of determining which context is being used.

# Integer

The [set] of all integers is denoted $\mathbb Z$.
It is an **infinite** set, meaning it has infinitely many members.

The set of all non-negative integers is denoted $\mathbb N$.

The set of all positive integers is denoted $\mathbb Z^+$ or $\mathbb N^+$. In general, a superscript $+$ after a set means "only the positive elements" and a superscript $-$ means "only the negative elements".

In computing^[In some other disciplines (not computing), "the natural numbers" refers to $\mathbb Z^+$ instead of $\mathbb Z^+ \cup \{0\}$. In computing if we need to name $\mathbb Z^{+}$ we call it "the positive integers" or "the whole numbers".], **the natural numbers** refers to $\mathbb N$.

An integer $x$ is a **divisor** of an integer $y$ if and only if $y \div x$ is an integer.
**Factor** is a synonym for *divisor*^[Usually. You can find various websites saying various "A factor is like a divisor except *X*" but they don't agree on what the *X* is.].
If $x$ is a *divisor* of $y$, then we say that $y$ is **divisible by** $x$ and $y$ is a **multiple** of $x$.

We can denote the concept "$x$ is a *divisor* of $y$" as "$x|y$", but this notation is unusual in computing because $|$ is already used for so many other concepts (e.g, for absolute values, cardinality, set-builder notation, conditional probability, complex magnitude, determinant, etc).

:::example
$2$ is a divisor of $2102$ because $2102 \div 2 = 1501$, an integer.
$5$ is not a divisor of $2102$ because $2102 \div 5 = 420.4$, which is not an integer.
$-1501$ is a divisor of $2102$ because $2102 \div -1501 = -1$, an integer.

$2102$ is a multiple of both $2$ and $-1501$.
:::

$0$ is not a divisor of any integer, not even itself.
Every other integer is a divisor of $0$.

The **trivial divisors** of any nonzero integer $x$ are $-x$, $-1$, $1$, and $x$.
An integer $x$ is **prime** if it is greater than $1$ and has no non-trivial divisors.

:::example
$2102$ is not prime because it has non-trivial factors, including $2$.

$1051$ is prime because it has no non-trivial factors.

$1$ and $-1051$ also have no non-trivial factors, but neither is prime because neither is not greater than $1$.
:::

The **fundamental theorem of arithmetic** states that every positive integer $x$ has one and only one **prime factorization**, meaning a product of one or more prime numbers equaling $x$.

:::example
The prime factorization of 2102 is $2 \times 1051$
:::

A prime factorization may include the same prime number more than once; the number of times a prime number $p$ appears in the prime factorization of $x$ is called the **multiplicity** of $p$ in that factorization.

:::example
$1280 = 2^8 \times 5$
so in this prime factorization $2$ has multiplicity 8, $5$ has multiplicity 1, and all other primes (3, 7, 11, etc) have multiplicity 0.
:::

The **greatest common divisor** (GCD) of a set of integers is the largest integer that is a divisor of all of the integers in the set.
If the GCD of two integers is 1, then the integers are called **co-prime** or **relatively prime**.

The notation "$x = y \mod q$" means "$x$ and $y$ have the same remainder when divided by $q$",
and can be formally expressed as $\exists a,b,c \in \mathbb Z \;.\; (x = aq+c) \land (y = bq+c)$.

# Rational

Any number that can be constructed by dividing one [integer] by another is called a **rational number**.
The set of all rational numbers is denoted $\mathbb Q$.

Every rational number $q$ can be written as a unique $x \div y$,
where $y$ is a positive integer, $x$ is an integer, and $x$ and $y$ are co-prime.

:::example
$34 / -20$ is a rational number.
It can be written as $\displaystyle{ -17 \over 10}$, where $-17$ and $10$ are co-prime.

$-2012 \div -1501$ is a rational number.
It can be written as $\displaystyle{2 \over 1}$, where $2$ and $1$ are co-prime.

Note that $\displaystyle{x \over y}$ and $x \div y$ and $x / y$ are all equivalent ways to write the same division operation.
:::

There are numbers that are not rational numbers, such as $\pi$,
but which belong to the set of **real** numbers, $\mathbb R$.

$\mathbb R \supset \mathbb Q \supset \mathbb Z \supset \mathbb N$.

The **floor** of any real number $x$, denoted $\lfloor x \rfloor$, is the largest integer that is not larger than $x$.
The **ceiling** of any real number $x$, denoted $\lceil x \rceil$, is the smallest integer that is not smaller than $x$.

:::example
$\lfloor 3\rfloor = \lfloor 3.1\rfloor = \lfloor 3.8\rfloor = 3$

$\lfloor -3.1\rfloor = \lfloor -3.8\rfloor = \lfloor -4\rfloor = -4$

$\lceil 3.1\rceil = \lceil 3.8\rceil = \lceil 4\rceil = 4$

$\lceil -3\rceil = \lceil -3.1\rceil = \lceil -3.8\rceil = -3$
:::

# Function and Relation

A **function** maps a [sequence] (or single value, which is treated as equivalent to a singleton sequence for this purpose) to a value.
It does this in a deterministic, single-valued way;
for example, if $f(2,3,4) = 11$ once, then (for that $f$) $f(2,3,4)$ is only and always 11, never any other value.

Each function is defined with a **domain**, the [set] of sequences to which it may be applied; and a **co-domain**, the set of values it may result in. That function $f$ is defined with domain $D$ and co-domain $C$ can be denoted $f:D\rightarrow C$.

A function need not be defined for all values in its domain, nor be able to produce all values in its co-domain.
If a function is defined with a domain, co-domain, and formula then it is defined only for that subset of the domain where the formula produces a member of the co-domain.
The subset of the co-domain that is mapped to by at least one element of the domain is called the **range** of the function.

:::example
Consider a function $g$ defined as $g:\mathbb Z \times \mathbb Z \rightarrow \mathbb Z$ by the formula $g(x,y) = x \div y$.
The function is defined for $g(12,2) = 6$ but is not defined for the following:

- $g(1,2)$ (because the formula would produce a value not in the co-domain)
- $g(3,0.5)$ (because the value is not in the domain)
- $g(3,0)$ (because the formula is not defined for these values)
:::

A function is called a **predicate** if its co-domain is the set $\{\top,\bot\}$, where $\top$ represents the concept "true" and $\bot$ represents the concept "false".
This is equivalent to the definition of predicate given in [First-Order Logic].

A **relation** is a generalization of a function that allows a single domain value to map to more than one co-domain value.
Each relation can also be defined using

- a predicate indicating which domain + co-domain elements are related
- a set of sequences, called the **graph** of the relation

Note that the relation itself is neither the predicate nor the set, but the predicate and set can express the meaning of the relation.

A *relation* is called **functional** if it is a function; that is, each element of the domain is related to at most one element in co-domain.

:::example
|Function-like|corresponding Predicate|Graph of|Functional?|
|:-|:-|:-|:-:|
|$f(x) = x^2$|$P(x,y) = (y = x^2)$|$\big\{ (x,y) \;\big|\; x^2 = y \big\}$|Yes|
|$f(x) = \pm \sqrt{x}$|$P(x,y) = (y^2 = x)$|$\big\{ (x,y) \;\big|\; x = y^2 \big\}$|No|
:::

A **binary relation** is a relation that resembles a single-argument function or two-argument predicate. Binary relations are by far the most common type of non-functional relation in computing.

Binary relations are often written as a formula defining their predicate, but with a special symbol instead of an equals sign, like $R(x,y): x < y$ or $R(x,y) \Coloneqq x<y$ for the less-than relation.
Many different symbols are used, though typically only one in any given document;
the most common are $:$, $\triangleq$, $\coloneqq$, $\Coloneqq$, and $\overset{\text{def}}{=}$.


There are a large number of vocabulary terms to know about functions and relations.

A *function* $f:D\rightarrow C$ is

- **total** if $f(x)$ is defined for all $x \in D$.
- **partial** means "either total or not total" and is used in contexts where most functions are assumed to be total to identify subcontexts where that assumption does not apply.
- **injective** or **1-to-1** if $f(x) = f(y)$ implies $x = y$.
- **surjective** or **onto** if the *co-domain* is equal to the *range*.
- **bijective**, **invertible**, or a **1-to-1 correspondence** if it is *total* and *injective* and *surjective*.

:::example
For $f : \mathbb Z \rightarrow \mathbb Z$,

- $f(x) = x + 2$ is total, injective, surjective, and bijective
- $f(x) = x \div 2$ is injective and surjective but not total
- $f(x) = x \times 2$ is total and injective but not surjective
- $f(x) = \lfloor x \div 2 \rfloor$ is total and surjective but not injective
:::

A *binary relation* defined by predicate $R(x,y)$ is

- **reflexive** if every $x$ is related to itself; that is, $\forall x\;.\; R(x,x)$
- **irreflexive** if no $x$ is related to itself; that is, $\forall x\;.\; \lnot R(x,x)$
- **transitive** if $\forall x,y,z\;.\; \big(R(x,y) \land R(y,z)\big) \rightarrow R(x,z)$
- **symmetric** if $\forall x,y\;.\; R(x,y) \rightarrow R(y,x)$
- **asymmetric** if $\forall x,y\;.\; R(x,y) \rightarrow \lnot R(y,x)$.
- **antisymmetric** if $\forall x,y\;.\; \big((x \ne y) \land R(x,y)\big) \rightarrow \lnot R(y,x)$

Note that a relation is asymmetric if and only if it is both antisymmetric and irreflexive.
 
Several combinations of the above properties have special names:

- an **equivalence relation** is reflexive, transitive, and symmetric
- a **partial order** is transitive and antisymmetric
    - a **strict** partial order is also irreflexive, implying it is also asymmetric
    - a **non-strict** partial order is also reflexive
    - Note (confusingly) that it is possible for a partial order to be neither strict nor non-strict
- a **total order** is a partial order such that every pair of values is either related or is related in the reverse order; that is, $\forall x,y\;.\; (x \ne y) \rightarrow \big(R(x,y) \lor R(y,x))$.
    - total orders also have strict and non-strict variants.
    - note the overloaded use of the word "total": "total order" is a type of binary relation; "total" is a property of some functions


:::example
For $R(x,y) : \mathbb Z^2 \rightarrow \{\bot,\top\}$,

- $R(x,y) \coloneqq \big(x = y\big)$ is an equivalence relation: that is, reflexive, transitive, and symmetric
- $R(x,y) \coloneqq \big(x < y\big)$ is a strict total order: that is, irreflexive, transitive, antisymmetric, and every pair of values is related in one direction or the other
- $R(x,y) \coloneqq$ "$x$ is a factor of $y$" is a non-strict partial order: that is, reflexive, transitive, and antisymmetric
- $R(x,y) \coloneqq (2x = 3y)$ is antisymmetric but has none of the other above properties
    - it is not reflexive because 2 is not related to 2
    - it is not irreflexive because 0 is related to 0
    - it is not transitive because $R(9,6)$ and $R(6,4)$ but not $R(9,4)$
    - it is antisymmetric because the system of equations $2x=3y$ and $2y=3x$ has only one solution: $x=y=0$
:::

# Summation

The notation $\displaystyle{ \sum_{x \in S} f(x) }$
is called **summation notation**
and means "the sum of all $f(x)$ where $x$ is an element of $S$".

:::example
Let $S = \{0,1,2,4\}$.
Then $\displaystyle{ \sum_{n\in S} 2^n = 2^0 + 2^1 + 2^2 + 2^4 = 23 }$.
:::

By definition, the sum of an empty set is 0.

The notation $\displaystyle{ \sum_{x = a}^{b} f(x) }$
is shorthand for $\displaystyle{ \sum_{x \in S} f(x) }$
where $S = \big\{ x \;\big|\; (x \in \mathbb Z) \land (x \ge a) \land (x \le b) \big\}$.

:::example
$\displaystyle{ \sum_{n=0}^{3} 2^n = 2^0 + 2^1 + 2^2 + 2^3 = 15 }$

$\displaystyle{ \sum_{n=3}^{0} 2^n = 0 }$ because there are no integers $x$ such that both $x\ge 3$ and $x \le 0$.
:::

The notation $\displaystyle{ \prod_{x \in S} }$ and $\displaystyle{ \prod_{x=a}^{b} }$ are defined similarly but as products, not sums, of their elements.
The product of an empty set is defined to be 1.

$n!$ is called the **factorial** of $n$ and is defined to be
$\displaystyle{ \prod_{x=1}^{n} x }$.
Thus, $0! = 1$ because it is the product of an empty set.

# Logarithm

*note: logarithms are not technically part of _discrete_ mathematics, being instead a topic within continuous mathematics. However, they are widely used in computing and not universally understood by entering students, so we'll cover them in this course.*

The logarithm is a family of functions that are the inverses of exponentiation.
It is defined by the following identity:
$$\big(x^y = z\big) \equiv \big(\log_x(z) = y\big)$$
The expression $\log_x(y)$ is read "the log base $x$ of $y$".

Logarithms are defined for all positive bases except 1,
though we almost always assume the base is greater than 1.

For any given base $b > 1$,

- $\log_b : \mathbb R^+ \rightarrow \mathbb R$ is bijective
- $\log_b$ is monotonically increasing; that is $(x > y) \equiv \big(\log_b(x) > \log_b(y)\big)$
    - (note if $0 < b < 1$, $\log_b$ is monotonically decreasing instead)
- $\displaystyle{ \log_b(b^x) = x }$
- $\displaystyle{ b^{\log_b(x)} = x }$
- $\displaystyle{ \log_b(x y) = \log_b(x) + \log_b(y) }$
- $\displaystyle{ \log_b\left(\frac{x}{y}\right) = \log_b(x) - \log_b(y) }$
- $\displaystyle{ \log_b(x^y) = y \log_b(x) }$
- $\displaystyle{ \log_b(x) = \frac{\log_a(x)}{\log_a(b)} }$

Logarithms have many other interesting properties and show up in many areas of computing; the above identities will be sufficient for this class.
