Introduction to algebra
================
Erika Duan
2/26/23

-   <a href="#elementary-algebra" id="toc-elementary-algebra">Elementary
    algebra</a>
-   <a href="#manipulating-inequalities"
    id="toc-manipulating-inequalities">Manipulating inequalities</a>
-   <a href="#simplifying-fractions"
    id="toc-simplifying-fractions">Simplifying fractions</a>
-   <a href="#factorisation" id="toc-factorisation">Factorisation</a>
-   <a href="#resources" id="toc-resources">Resources</a>

<div>

> **Summary**
>
> This tutorial lists some common algebraic tricks, such as
> factorisation and working with inequalities, which are useful for
> solving mathematical problems in later tutorials.

</div>

# Elementary algebra

Elementary algebra is commonly associated with questions like *Solve for
x when
![2x + y = 6](https://latex.codecogs.com/svg.latex?2x%20%2B%20y%20%3D%206 "2x + y = 6").*
It is more useful, however, to think of elementary algebra as a form of
expression that allows us to represent infinitely possible terms using
finite ones.

For example, the terms
![6x + 3y](https://latex.codecogs.com/svg.latex?6x%20%2B%203y "6x + 3y"),
![4x + 2y](https://latex.codecogs.com/svg.latex?4x%20%2B%202y "4x + 2y")
and
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y")
are equivalent and there are theoretically infinite variations of this
expression, with the simplest being
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y").
When we read the term
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y"),
we can intuit that 2 parts of
![x](https://latex.codecogs.com/svg.latex?x "x") and 1 part of
![y](https://latex.codecogs.com/svg.latex?y "y") are always required to
make up a final quantity.

![](../figures/algebra-representation.svg)

An algebraic term can therefore be decomposed into three parts:

-   A single **variable** or multiple variables. A variable is a varying
    quantity of an entity, usually represented by concise symbols
    ![x](https://latex.codecogs.com/svg.latex?x "x"),
    ![y](https://latex.codecogs.com/svg.latex?y "y") or
    ![x_i](https://latex.codecogs.com/svg.latex?x_i "x_i") where
    ![i=1, \cdots, n](https://latex.codecogs.com/svg.latex?i%3D1%2C%20%5Ccdots%2C%20n "i=1, \cdots, n").
-   The relative **quantity** of each variable. *For example, let
    ![x](https://latex.codecogs.com/svg.latex?x "x") represent the
    number of eggs and ![y](https://latex.codecogs.com/svg.latex?y "y")
    represent the number of cups of sugar required to make a dessert.*
    The term
    ![x + y](https://latex.codecogs.com/svg.latex?x%20%2B%20y "x + y")
    describes a 1:1 ratio of eggs to sugar whereas the term
    ![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y")
    describes a 2:1 ratio of eggs to sugar and will result in a very
    different taste.
-   The arithmetic **operator(s)** applied between variables. *For
    example, in additive models, the relationship between parameters
    ![y = b_o+b_1x_1 + \cdots + b_nx_n](https://latex.codecogs.com/svg.latex?y%20%3D%20b_o%2Bb_1x_1%20%2B%20%5Ccdots%20%2B%20b_nx_n "y = b_o+b_1x_1 + \cdots + b_nx_n")
    is additive and the dependent variable
    ![y](https://latex.codecogs.com/svg.latex?y "y") therefore increases
    by ![b_1](https://latex.codecogs.com/svg.latex?b_1 "b_1") amount for
    one unit increase in
    ![x_1](https://latex.codecogs.com/svg.latex?x_1 "x_1").*

# Manipulating inequalities

Algebraic terms using inequalities are common when we want to prove the
existence of an upper or lower bound. *For example, if A is an event in
the probability space, we know that the probability of event A occurring
is between 0 and 1 inclusive i.e.*
![0 \leq P(A) \leq 1](https://latex.codecogs.com/svg.latex?0%20%5Cleq%20P%28A%29%20%5Cleq%201 "0 \leq P(A) \leq 1").

There are three rules for manipulating inequalities:

-   Adding or subtracting the same quantity from both sides of an
    inequality leaves the inequality symbol unchanged.
-   Multiplying or dividing both sides of an inequality by a positive
    number leaves the inequality symbol unchanged.
-   Multiplying or dividing both sides of an inequality by a negative
    number reverses the inequality symbol.

![](../figures/algebra-inequality_rules.svg)

<div class="panel-tabset">

## R

In R, inequality statements are outputted as Boolean values i.e. `TRUE`
or `FALSE`.

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

# Simplifying fractions

# Factorisation

# Resources

-   [Entry](https://plato.stanford.edu/entries/algebra/) on algebra from
    the Stanford Encyclopedia of Philosophy.  
-   Khan academy [YouTube
    series](https://www.khanacademy.org/math/algebra-basics/alg-basics-algebraic-expressions#alg-basics-intro-to-variables)
    on algebra basics.  
-   A
    [factsheet](https://www.mathcentre.ac.uk/resources/uploaded/mc-bus-manipinequ-2009-1.pdf)
    on manipulating inequalities from the Uk Maths Centre.
