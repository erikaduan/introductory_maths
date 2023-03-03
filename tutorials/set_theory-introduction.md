Introduction to set theory
================
Erika Duan
3/3/23

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
(![e](https://latex.codecogs.com/svg.latex?e "e")). We reference a set
by listing all its elements.  
*For example,
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

# Identify disjoint sets in Python ---------------------------------------------
set_a.isdisjoint(set_b)
#> False

# Identify subsets in Python ---------------------------------------------------
set_c = {1, 2, 3, 4}  
set_a.issubset(set_c)
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

## Associative laws

## Distributive laws

## De Morgan’s laws

# Resources

-   [Wikipedia entry](https://en.wikipedia.org/wiki/Algebra_of_sets) on
    set algebra.  
-   A [guide](https://realpython.com/python-sets/) on Python set
    operations from Real Python.  
-   A [guide](https://www.geeksforgeeks.org/sets-in-julia/) on Julia set
    operations from GeeksforGeeks.
