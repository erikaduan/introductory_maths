Introduction to set theory
================
Erika Duan
3/5/23

-   <a href="#what-is-a-set" id="toc-what-is-a-set">What is a set?</a>
-   <a href="#working-with-two-or-more-sets"
    id="toc-working-with-two-or-more-sets">Working with two or more sets</a>
-   <a href="#set-algebra" id="toc-set-algebra">Set algebra</a>
    -   <a href="#commutative-laws" id="toc-commutative-laws">Commutative
        laws</a>
    -   <a href="#associative-laws" id="toc-associative-laws">Associative
        laws</a>
    -   <a href="#distributive-laws" id="toc-distributive-laws">Distributive
        laws</a>
    -   <a href="#de-morgans-laws" id="toc-de-morgans-laws">De Morgan’s laws</a>
-   <a href="#resources" id="toc-resources">Resources</a>

<div>

> **Summary**
>
> This tutorial provides a framework for describing element belonging to
> a set, where a set is a collection of distinct elements. Working with
> sets is a prerequisite for understanding probability theory.

</div>

# What is a set?

A set is a collection of distinct objects or elements
(![e](https://latex.codecogs.com/svg.latex?e "e")).

We reference a set by listing all its elements. *For example,
![S = \\{cat, \\;mouse, \\;dog \\}](https://latex.codecogs.com/svg.latex?S%20%3D%20%5C%7Bcat%2C%20%5C%3Bmouse%2C%20%5C%3Bdog%20%5C%7D "S = \{cat, \;mouse, \;dog \}")
or
![S = \\{1, 2, 3, 4, 5, 6 \\}](https://latex.codecogs.com/svg.latex?S%20%3D%20%5C%7B1%2C%202%2C%203%2C%204%2C%205%2C%206%20%5C%7D "S = \{1, 2, 3, 4, 5, 6 \}")
to describe all the possible distinct outcomes when we roll a dice and
observe its upper face.*

Set notation:

-   An example of a **finite set** is
    ![A = \\{1, 3, 5 \\}](https://latex.codecogs.com/svg.latex?A%20%3D%20%5C%7B1%2C%203%2C%205%20%5C%7D "A = \{1, 3, 5 \}").
    A finite set is countable by definition.  
-   An example of a **countably infinite set** is
    ![B = \\{1, 2, \cdots \\}](https://latex.codecogs.com/svg.latex?B%20%3D%20%5C%7B1%2C%202%2C%20%5Ccdots%20%5C%7D "B = \{1, 2, \cdots \}").
    The set consists of integers which extend from 1 to infinity.  
-   An example of an **uncountably infinite set** is
    ![C = (1, 0)](https://latex.codecogs.com/svg.latex?C%20%3D%20%281%2C%200%29 "C = (1, 0)").
    The set is uncountable as it comprises all real numbers between 0
    and 1.  
-   The **null set**
    (![\varnothing](https://latex.codecogs.com/svg.latex?%5Cvarnothing "\varnothing"))
    does not contain any elements and is denoted by
    ![\varnothing = \\{\\}](https://latex.codecogs.com/svg.latex?%5Cvarnothing%20%3D%20%5C%7B%5C%7D "\varnothing = \{\}").  
-   The **universal set** is denoted by
    ![S](https://latex.codecogs.com/svg.latex?S "S") and is the set of
    all elements under consideration for a specific scenario.  
-   The **complement** of set
    ![A](https://latex.codecogs.com/svg.latex?A "A") is the set of
    elements which are in
    ![S](https://latex.codecogs.com/svg.latex?S "S") but not in
    ![A](https://latex.codecogs.com/svg.latex?A "A"). This is expressed
    in mathematical notation as
    ![\bar{A} = \\{e : e\in S, e\notin A\\}](https://latex.codecogs.com/svg.latex?%5Cbar%7BA%7D%20%3D%20%5C%7Be%20%3A%20e%5Cin%20S%2C%20e%5Cnotin%20A%5C%7D "\bar{A} = \{e : e\in S, e\notin A\}").  
-   If all elements of set
    ![A](https://latex.codecogs.com/svg.latex?A "A") are also in set
    ![B](https://latex.codecogs.com/svg.latex?B "B"), then
    ![A](https://latex.codecogs.com/svg.latex?A "A") is a **subset** of
    ![B](https://latex.codecogs.com/svg.latex?B "B") and this is denoted
    as
    ![A \subseteq B](https://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20B "A \subseteq B").
    There are only two possibilities when this is true, that the number
    of elements in set A are fewer than those in set B or that set A and
    B contain the same elements.  
-   If
    ![A \subseteq B](https://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20B "A \subseteq B")
    and
    ![B \subseteq A](https://latex.codecogs.com/svg.latex?B%20%5Csubseteq%20A "B \subseteq A"),
    then
    ![A = B](https://latex.codecogs.com/svg.latex?A%20%3D%20B "A = B").

![](../figures/set_theory-set_notations.svg)

# Working with two or more sets

Venn diagrams are useful for conceptually visualising set properties.
However, we still want to use rigorous mathematical proofs when
asserting set properties.

Consider set ![A](https://latex.codecogs.com/svg.latex?A "A") and set
![B](https://latex.codecogs.com/svg.latex?B "B") such that a subset of
elements in ![A](https://latex.codecogs.com/svg.latex?A "A") are also
found in ![B](https://latex.codecogs.com/svg.latex?B "B"):

-   The **intersection** of
    ![A](https://latex.codecogs.com/svg.latex?A "A") and
    ![B](https://latex.codecogs.com/svg.latex?B "B") contains the set of
    elements found in both
    ![A](https://latex.codecogs.com/svg.latex?A "A") and
    ![B](https://latex.codecogs.com/svg.latex?B "B"). This is denoted as
    ![A \cap B = \\{e: e\in A, e \in B \\}](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B%20%3D%20%5C%7Be%3A%20e%5Cin%20A%2C%20e%20%5Cin%20B%20%5C%7D "A \cap B = \{e: e\in A, e \in B \}").  
-   The **union** of ![A](https://latex.codecogs.com/svg.latex?A "A")
    and ![B](https://latex.codecogs.com/svg.latex?B "B") contains the
    set of elements found in
    ![A](https://latex.codecogs.com/svg.latex?A "A") or
    ![B](https://latex.codecogs.com/svg.latex?B "B"). This is denoted as
    ![A \cup B = \\{e: e \in A \\; or \\; e\in B \\}](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20B%20%3D%20%5C%7Be%3A%20e%20%5Cin%20A%20%5C%3B%20or%20%5C%3B%20e%5Cin%20B%20%5C%7D "A \cup B = \{e: e \in A \; or \; e\in B \}").  
-   The set operation
    ![A - B](https://latex.codecogs.com/svg.latex?A%20-%20B "A - B")
    contains the set of elements found in
    ![A](https://latex.codecogs.com/svg.latex?A "A") that are not found
    in ![B](https://latex.codecogs.com/svg.latex?B "B"). This is
    equivalent to
    ![A \cap \bar B](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20%5Cbar%20B "A \cap \bar B")
    and denoted as
    ![A \cap \bar B = \\{e: e \in A, e \notin B\\}](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20%5Cbar%20B%20%3D%20%5C%7Be%3A%20e%20%5Cin%20A%2C%20e%20%5Cnotin%20B%5C%7D "A \cap \bar B = \{e: e \in A, e \notin B\}").

![](../figures/set_theory-set_operations.svg)

Consider set ![A](https://latex.codecogs.com/svg.latex?A "A") and set
![B](https://latex.codecogs.com/svg.latex?B "B") such that no elements
in ![A](https://latex.codecogs.com/svg.latex?A "A") are found in
![B](https://latex.codecogs.com/svg.latex?B "B"):

-   Sets ![A](https://latex.codecogs.com/svg.latex?A "A") and
    ![B](https://latex.codecogs.com/svg.latex?B "B") are mutually
    exclusive or **disjoint** if
    ![A \cap B = \varnothing](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B%20%3D%20%5Cvarnothing "A \cap B = \varnothing").  
-   Sets ![A](https://latex.codecogs.com/svg.latex?A "A"),
    ![B](https://latex.codecogs.com/svg.latex?B "B") and
    ![C](https://latex.codecogs.com/svg.latex?C "C") are therefore
    disjoint if
    ![A \cap B = A \cap C = B \cap C = \varnothing](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B%20%3D%20A%20%5Ccap%20C%20%3D%20B%20%5Ccap%20C%20%3D%20%5Cvarnothing "A \cap B = A \cap C = B \cap C = \varnothing").

![](../figures/set_theory-disjoint_sets.svg)

<div class="panel-tabset">

## R

In contrast to Python, R does not have a set data type. However, set
operations `union()`, `intersect(x, y)`, `setdiff(x, y)` and
`setequal(x, y)` exist in base R.

``` r
# Perform set operations in R --------------------------------------------------
a = c(1, 2, 3)
b = c(1, 3, 6)

union(a, b)
#> [1] 1 2 3 6  

intersect(a, b)
#> [1] 1 3  

# setdiff(a, b) is equivalent to a - b 
setdiff(a, b)
#> [1] 2

setequal(a, b)
#> [1] FALSE  
```

## Python

In Python, a set is an unordered data type comprising a collection of
distinct data objects. Sets can be created directly using `{1, 2, 3}` or
`set([1, 2, 3])`.

``` python
# Create a set in Python -------------------------------------------------------
list_a = [1, 2, 2, 3]
set_a = set(list_a)

print(set_a)
#> {1, 2, 3}

type(set_a)
#> <class 'set'>  
```

``` python
# Perform set operations in Python ---------------------------------------------
set_b = {1, 3, 6}
type(set_b)
#> <class 'set'>  

set_a.union(set_b)
#> {1, 2, 3, 6}  

set_a.union(set_b) == set_a | set_b
#> True  

set_a.intersection(set_b)
#> {1, 3}  

set_a.intersection(set_b) == set_a & set_b
#> True  

# a.difference(b) is equivalent to a - b  

set_a.difference(set_b)
#> {2}   

set_a - set_b
#> {2}   

# Python also has an ^ operator which returns all elements in A or B but not AB 

set_a.symmetric_difference(set_b)
#> {2, 6}  

set_a.symmetric_difference(set_b) == set_a ^ set_b
#> True  
```

``` python
# Identify disjoint sets in Python ---------------------------------------------
set_c = {8, 9}
set_a.isdisjoint(set_c)
#> True
```

``` python
# Identify subsets in Python ---------------------------------------------------
set_d = {1, 2, 3, 4}  
set_a.issubset(set_d)
#> True 
```

## Julia

In Julia, inequality statements are also outputted as Boolean values
i.e. `true` or `false`.

``` julia
# Create a set in Julia --------------------------------------------------------
a = Set([1, 2, 3]) 
b = Set([1, 3, 6])

typeof(a)
#> Set{Int64}  
print(a)
#> Set([2, 3, 1])  
```

``` julia
# Perform set operations in Julia ----------------------------------------------
print(union(a, b))
#> Set([6, 2, 3, 1])  

print(intersect(a, b))
#> Set([3, 1])   

print(setdiff(a, b))
#> Set([2])  

# symdiff(a, b) is equivalent to a.symmetric_difference(b) in Python
print(symdiff(a, b))
#> Set([6, 2])
```

</div>

# Set algebra

## Commutative laws

The set order has no impact on the union or intersection of two sets.
This is intuitive as changing the set order does not change contents of
each individual set.

-   ![A \cup B = B \cup A](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20B%20%3D%20B%20%5Ccup%20A "A \cup B = B \cup A")  
-   ![A \cap B = B \cap A](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B%20%3D%20B%20%5Ccap%20A "A \cap B = B \cap A")

![](../figures/set_theory-commutative_laws.svg)

## Associative laws

The set order also has no impact when only either an intersection or
union is performed on more than two sets. This is similarly intuitive to
the commutative laws, as introducing extra sets does not change contents
of each individual set.

-   ![A \cup B \cup C = (A \cup B) \cup C = A \cup (B \cup C)](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20B%20%5Ccup%20C%20%3D%20%28A%20%5Ccup%20B%29%20%5Ccup%20C%20%3D%20A%20%5Ccup%20%28B%20%5Ccup%20C%29 "A \cup B \cup C = (A \cup B) \cup C = A \cup (B \cup C)")  
-   ![A \cap B \cup C = (A \cap B) \cap C = A \cup (B \cap C)](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B%20%5Ccup%20C%20%3D%20%28A%20%5Ccap%20B%29%20%5Ccap%20C%20%3D%20A%20%5Ccup%20%28B%20%5Ccap%20C%29 "A \cap B \cup C = (A \cap B) \cap C = A \cup (B \cap C)")

![](../figures/set_theory-associative_laws.svg)

## Distributive laws

The sequence of first performing the set operation inside the
parenthesis matters when both an intersection and union are applied to
multiple sets. This is similar to how the sequence of first performing
the operation inside the parenthesis matters in elementary algebra. *For
example,
![2+(3 \times 4) \neq (2 + 3) \times 4.](https://latex.codecogs.com/svg.latex?2%2B%283%20%5Ctimes%204%29%20%5Cneq%20%282%20%2B%203%29%20%5Ctimes%204. "2+(3 \times 4) \neq (2 + 3) \times 4.")*

-   ![A \cup (B \cap C) \neq (A \cup B) \cap C](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20%28B%20%5Ccap%20C%29%20%5Cneq%20%28A%20%5Ccup%20B%29%20%5Ccap%20C "A \cup (B \cap C) \neq (A \cup B) \cap C")  
-   ![A \cup (B \cap C) = (A \cup B) \cap (A \cup C)](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20%28B%20%5Ccap%20C%29%20%3D%20%28A%20%5Ccup%20B%29%20%5Ccap%20%28A%20%5Ccup%20C%29 "A \cup (B \cap C) = (A \cup B) \cap (A \cup C)")

![](../figures/set_theory-distributive_laws_1.svg)

-   ![A \cap (B \cup C) \neq (A \cap B) \cup C)](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20%28B%20%5Ccup%20C%29%20%5Cneq%20%28A%20%5Ccap%20B%29%20%5Ccup%20C%29 "A \cap (B \cup C) \neq (A \cap B) \cup C)")  
-   ![A \cap (B \cup C) = (A \cap B) \cup (A \cap C)](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20%28B%20%5Ccup%20C%29%20%3D%20%28A%20%5Ccap%20B%29%20%5Ccup%20%28A%20%5Ccap%20C%29 "A \cap (B \cup C) = (A \cap B) \cup (A \cap C)")

![](../figures/set_theory-distributive_laws_2.svg)

## De Morgan’s laws

De Morgan’s law is less intuitive and can be visualised by Venn diagrams
or (more preferably) proven mathematically.

-   ![\overline{A\cup B} = \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccup%20B%7D%20%3D%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "\overline{A\cup B} = \bar A \cap \bar B")

<div>

> **Proof 1**
>
> Suppose that
> ![e \in \overline{A\cup B}](https://latex.codecogs.com/svg.latex?e%20%5Cin%20%5Coverline%7BA%5Ccup%20B%7D "e \in \overline{A\cup B}")  
> Then
> ![e \notin A \cup B](https://latex.codecogs.com/svg.latex?e%20%5Cnotin%20A%20%5Ccup%20B "e \notin A \cup B")  
> ![\implies e \notin A, \\; e \notin B](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cnotin%20A%2C%20%5C%3B%20e%20%5Cnotin%20B "\implies e \notin A, \; e \notin B")  
> ![\implies e \in \bar A, \\; e \in \bar B](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cin%20%5Cbar%20A%2C%20%5C%3B%20e%20%5Cin%20%5Cbar%20B "\implies e \in \bar A, \; e \in \bar B")  
> ![\implies e \in \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cin%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "\implies e \in \bar A \cap \bar B")  
> Therefore,
> ![\overline{A\cup B} \subseteq \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccup%20B%7D%20%5Csubseteq%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "\overline{A\cup B} \subseteq \bar A \cap \bar B")
>
> Similarly, suppose that
> ![e \in \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?e%20%5Cin%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "e \in \bar A \cap \bar B")  
> Then
> ![e \in \bar A, \\; e \in \bar B](https://latex.codecogs.com/svg.latex?e%20%5Cin%20%5Cbar%20A%2C%20%5C%3B%20e%20%5Cin%20%5Cbar%20B "e \in \bar A, \; e \in \bar B")  
> ![\implies e \notin A, \\; e \notin B](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cnotin%20A%2C%20%5C%3B%20e%20%5Cnotin%20B "\implies e \notin A, \; e \notin B")  
> ![\implies e \notin A \cup B](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cnotin%20A%20%5Ccup%20B "\implies e \notin A \cup B")  
> ![\implies e \in \overline{A\cup B}](https://latex.codecogs.com/svg.latex?%5Cimplies%20e%20%5Cin%20%5Coverline%7BA%5Ccup%20B%7D "\implies e \in \overline{A\cup B}")  
> Therefore,
> ![\bar A \cap \bar B \subseteq \overline{A\cup B}](https://latex.codecogs.com/svg.latex?%5Cbar%20A%20%5Ccap%20%5Cbar%20B%20%5Csubseteq%20%5Coverline%7BA%5Ccup%20B%7D "\bar A \cap \bar B \subseteq \overline{A\cup B}")
>
> Therefore,
> ![\overline{A\cup B} = \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccup%20B%7D%20%3D%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "\overline{A\cup B} = \bar A \cap \bar B")

</div>

![](../figures/set_theory-de_morgans_law_1.svg)

-   ![\overline{A\cap B} = {\bar A} \cup {\bar B}](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccap%20B%7D%20%3D%20%7B%5Cbar%20A%7D%20%5Ccup%20%7B%5Cbar%20B%7D "\overline{A\cap B} = {\bar A} \cup {\bar B}")

<div>

> **Proof 2**
>
> From proof 1,
> ![\overline{A\cup B} = \bar A \cap \bar B](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccup%20B%7D%20%3D%20%5Cbar%20A%20%5Ccap%20%5Cbar%20B "\overline{A\cup B} = \bar A \cap \bar B")
>
> If we substitute A with
> ![\bar A](https://latex.codecogs.com/svg.latex?%5Cbar%20A "\bar A")
> and B with
> ![\bar B](https://latex.codecogs.com/svg.latex?%5Cbar%20B "\bar B")  
> ![\implies \overline{\bar A \cup \bar B} = \bar {\bar A} \cap \bar {\bar B}](https://latex.codecogs.com/svg.latex?%5Cimplies%20%5Coverline%7B%5Cbar%20A%20%5Ccup%20%5Cbar%20B%7D%20%3D%20%5Cbar%20%7B%5Cbar%20A%7D%20%5Ccap%20%5Cbar%20%7B%5Cbar%20B%7D "\implies \overline{\bar A \cup \bar B} = \bar {\bar A} \cap \bar {\bar B}")  
> ![\implies \overline{\bar A \cup \bar B} = A \cap B](https://latex.codecogs.com/svg.latex?%5Cimplies%20%5Coverline%7B%5Cbar%20A%20%5Ccup%20%5Cbar%20B%7D%20%3D%20A%20%5Ccap%20B "\implies \overline{\bar A \cup \bar B} = A \cap B")  
> ![\implies {\bar A \cup \bar B} = \overline {A \cap B}](https://latex.codecogs.com/svg.latex?%5Cimplies%20%7B%5Cbar%20A%20%5Ccup%20%5Cbar%20B%7D%20%3D%20%5Coverline%20%7BA%20%5Ccap%20B%7D "\implies {\bar A \cup \bar B} = \overline {A \cap B}")
>
> Therefore,
> ![\overline{A\cap B} = {\bar A} \cup {\bar B}](https://latex.codecogs.com/svg.latex?%5Coverline%7BA%5Ccap%20B%7D%20%3D%20%7B%5Cbar%20A%7D%20%5Ccup%20%7B%5Cbar%20B%7D "\overline{A\cap B} = {\bar A} \cup {\bar B}")

</div>

![](../figures/set_theory-de_morgans_law_2.svg)

# Resources

-   [Wikipedia entry](https://en.wikipedia.org/wiki/Algebra_of_sets) on
    set algebra.  
-   A [guide](https://realpython.com/python-sets/) on Python set
    operations from Real Python.  
-   A [guide](https://www.geeksforgeeks.org/sets-in-julia/) on Julia set
    operations from GeeksforGeeks.
