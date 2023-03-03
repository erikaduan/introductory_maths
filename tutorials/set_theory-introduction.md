Introduction to set theory
================
Erika Duan
3/3/23

-   <a href="#what-is-a-set" id="toc-what-is-a-set">What is a set?</a>
-   <a href="#working-with-two-or-more-sets"
    id="toc-working-with-two-or-more-sets">Working with two or more sets</a>
-   <a href="#resources" id="toc-resources">Resources</a>

<div>

> **Summary**
>
> This tutorial provides a framework for describing element belonging to
> a set, where a set is a collection of distinct elements. Working with
> sets is a prerequisite for understanding the key properties of
> probability theory.

</div>

# What is a set?

A set is a collection of distinct objects or elements
(![e](https://latex.codecogs.com/svg.latex?e "e")). We reference a set
by listing all its elements. *For example,
![S = \\{cat, \\;mouse, \\;dog \\}](https://latex.codecogs.com/svg.latex?S%20%3D%20%5C%7Bcat%2C%20%5C%3Bmouse%2C%20%5C%3Bdog%20%5C%7D "S = \{cat, \;mouse, \;dog \}")
or
![S = \\{1, 2, 3, 4, 5, 6 \\}](https://latex.codecogs.com/svg.latex?S%20%3D%20%5C%7B1%2C%202%2C%203%2C%204%2C%205%2C%206%20%5C%7D "S = \{1, 2, 3, 4, 5, 6 \}")
to describe all the possible distinct outcomes when we roll a dice and
observe its upper face.*

Set notation:

-   An example of a finite set is
    ![A = \\{1, 3, 5 \\}](https://latex.codecogs.com/svg.latex?A%20%3D%20%5C%7B1%2C%203%2C%205%20%5C%7D "A = \{1, 3, 5 \}").
    A finite set is countable by definition.  
-   An example of a countably infinite set is
    ![B = \\{1, 2, \cdots \\}](https://latex.codecogs.com/svg.latex?B%20%3D%20%5C%7B1%2C%202%2C%20%5Ccdots%20%5C%7D "B = \{1, 2, \cdots \}").
    The set consists of integers which extend fro to infinity.  
-   An example of an uncountably infinite set is
    ![C = (1, 0)](https://latex.codecogs.com/svg.latex?C%20%3D%20%281%2C%200%29 "C = (1, 0)").
    The set is uncountable as it comprises all real numbers between 0
    and 1.  
-   The **null set**
    (![\varnothing](https://latex.codecogs.com/svg.latex?%5Cvarnothing "\varnothing"))
    does not contain any elements and is denoted by
    ![\varnothing = \\{\\}](https://latex.codecogs.com/svg.latex?%5Cvarnothing%20%3D%20%5C%7B%5C%7D "\varnothing = \{\}").  
-   ![S](https://latex.codecogs.com/svg.latex?S "S") is used to denote
    the universal set, which is the set of all objects under
    consideration.  
-   The complement of set
    ![A](https://latex.codecogs.com/svg.latex?A "A") is the set of
    elements which are in
    ![S](https://latex.codecogs.com/svg.latex?S "S") but not in
    ![A](https://latex.codecogs.com/svg.latex?A "A"). This is expressed
    in mathematical notation as
    ![\bar{A} = \\{e : e\in S, e\notin A\\}](https://latex.codecogs.com/svg.latex?%5Cbar%7BA%7D%20%3D%20%5C%7Be%20%3A%20e%5Cin%20S%2C%20e%5Cnotin%20A%5C%7D "\bar{A} = \{e : e\in S, e\notin A\}").  
-   If all elements of set
    ![A](https://latex.codecogs.com/svg.latex?A "A") are also in set
    ![B](https://latex.codecogs.com/svg.latex?B "B"), set
    ![A](https://latex.codecogs.com/svg.latex?A "A") is a subset of set
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

![](../figures/set_theory-set_operations.svg)

<div class="panel-tabset">

## R

R does not have a set data type.

``` r
# Compute inequality in R ------------------------------------------------------
4 <= 4
#> [1] TRUE

4 < 4
#> [1] FALSE

class(4 < 4)
#> [1] "logical"
```

## Python

In Python, inequality statements are also outputted as Boolean values
i.e. `True` or `False`.

``` python
# Compute inequality in Python -------------------------------------------------
4 <= 4
#> True 
```

``` python
type(4 <= 4)
#> <class 'bool'>  
```

## Julia

In Julia, inequality statements are also outputted as Boolean values
i.e. `true` or `false`.

``` julia
# Compute inequality in Julia --------------------------------------------------
4 <= 4
#> true 

typeof(4 <= 4) 
#> true
#> Bool

a = 1
b = 2
c = 3

a < b, a + c < b + c
#> (true, true) 
```

</div>

# Resources

-   [Wikipedia entry](https://en.wikipedia.org/wiki/Algebra_of_sets) on
    set algebra.
