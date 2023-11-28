# Introduction to algebra
Erika Duan
2023-07-22

- [Elementary algebra](#elementary-algebra)
- [Simplifying algebraic terms](#simplifying-algebraic-terms)
- [Factorisation](#factorisation)
- [Manipulating inequalities](#manipulating-inequalities)
- [Resources](#resources)

<div>

> **Summary**
>
> This tutorial introduces basic algebra concepts and illustrates some
> algebraic tricks, such as factorisation and working with inequalities,
> that are useful for solving mathematical problems related to calculus
> and statistical mathematics in later tutorials.

</div>

# Elementary algebra

Elementary algebra, also referred to as just algebra, is commonly
associated with tasks like *Find x if
![2x = 6](https://latex.codecogs.com/svg.latex?2x%20%3D%206 "2x = 6").*
However, it is more useful to think of algebra as a form of expression
that allows us to represent infinitely possible terms using a finite
one.

For example, the terms
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y"),
![4x + 2y](https://latex.codecogs.com/svg.latex?4x%20%2B%202y "4x + 2y")
and
![6x + 3y](https://latex.codecogs.com/svg.latex?6x%20%2B%203y "6x + 3y")
are equivalent and infinite variations of this expression exist, with
the simplest being
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y").
When we read the term
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y"),
we can intuit that 2 parts of
![x](https://latex.codecogs.com/svg.latex?x "x") and 1 part of
![y](https://latex.codecogs.com/svg.latex?y "y") are always required
(usually to make up another quantity).

Mathematics involves being precise with descriptions, and it is much
easier to write
![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y")
than to write ‘*all possible values where we have 2 parts of one
component and one part of a different component*’.

![](../figures/algebra-representation.gif)

An algebraic term can therefore be decomposed into three components:

- Variable(s): a variable is a varying quantity of an entity, usually
  represented by concise symbols such as
  ![x](https://latex.codecogs.com/svg.latex?x "x"),
  ![y](https://latex.codecogs.com/svg.latex?y "y"),
  ![z](https://latex.codecogs.com/svg.latex?z "z") or
  ![x_i](https://latex.codecogs.com/svg.latex?x_i "x_i") where
  ![i=1, \cdots, n](https://latex.codecogs.com/svg.latex?i%3D1%2C%20%5Ccdots%2C%20n "i=1, \cdots, n").  
- Operator(s): the arithmetic operation applied to variables. *For
  example, in additive models, the relationship between parameters
  ![y = b_o+b_1x_1 + \cdots + b_nx_n](https://latex.codecogs.com/svg.latex?y%20%3D%20b_o%2Bb_1x_1%20%2B%20%5Ccdots%20%2B%20b_nx_n "y = b_o+b_1x_1 + \cdots + b_nx_n")
  is additive and the dependent variable
  ![y](https://latex.codecogs.com/svg.latex?y "y") therefore increases
  by ![+b_1](https://latex.codecogs.com/svg.latex?%2Bb_1 "+b_1") for per
  unit increase in
  ![x_1](https://latex.codecogs.com/svg.latex?x_1 "x_1").*  
- Relative quantity of variable(s): *For example, let
  ![x](https://latex.codecogs.com/svg.latex?x "x") represent the number
  of eggs and ![y](https://latex.codecogs.com/svg.latex?y "y") represent
  the number of cups of sugar required to make a dessert. The term
  ![x + y](https://latex.codecogs.com/svg.latex?x%20%2B%20y "x + y")
  describes a 1:1 ratio of eggs to sugar whereas the term
  ![2x + y](https://latex.codecogs.com/svg.latex?2x%20%2B%20y "2x + y")
  describes a 2:1 ratio of eggs to sugar and will result in a very
  different taste.*

# Simplifying algebraic terms

A few rules of algebraic manipulation are:

- We can simplify product terms using product expansion. *For example,
  ![4(x + 2.5y) = 4x + 10y](https://latex.codecogs.com/svg.latex?4%28x%20%2B%202.5y%29%20%3D%204x%20%2B%2010y "4(x + 2.5y) = 4x + 10y").*  
- We cannot further simplify a term if it is the input of another
  mathematical operator. *For example,
  ![(4x + 10y)^2 = 6z \not\equiv](https://latex.codecogs.com/svg.latex?%284x%20%2B%2010y%29%5E2%20%3D%206z%20%5Cnot%5Cequiv "(4x + 10y)^2 = 6z \not\equiv")
  (2x + 5y)^2 = 3z\$.*  
- We can add or subtract fractions by multiplying the fractions to form
  a common denominator. For example,
  ![\tfrac{3y}{x} + \tfrac{4x}{y} = \tfrac{3y^2 + 4x^2}{xy}](https://latex.codecogs.com/svg.latex?%5Ctfrac%7B3y%7D%7Bx%7D%20%2B%20%5Ctfrac%7B4x%7D%7By%7D%20%3D%20%5Ctfrac%7B3y%5E2%20%2B%204x%5E2%7D%7Bxy%7D "\tfrac{3y}{x} + \tfrac{4x}{y} = \tfrac{3y^2 + 4x^2}{xy}").

::: panel-tabset \## R

``` r
# Solve algebraic term in R ----------------------------------------------------
4 <= 4
#> [1] TRUE

4 < 4
#> [1] FALSE

class(4 < 4)
#> [1] "logical"
```

# Factorisation

Factorisation is the reverse process to product expansion and can be
thought of as breaking down a fully expanded algebraic term into the
product of its factors. *For example, the factors of
![10x + 2y](https://latex.codecogs.com/svg.latex?10x%20%2B%202y "10x + 2y")
are ![2](https://latex.codecogs.com/svg.latex?2 "2") and
![5x + y](https://latex.codecogs.com/svg.latex?5x%20%2B%20y "5x + y") as
![10x + 2y = 2(5x + y)](https://latex.codecogs.com/svg.latex?10x%20%2B%202y%20%3D%202%285x%20%2B%20y%29 "10x + 2y = 2(5x + y)").*

The reason why factorisation is useful is that it allows us to solve for
special function properties, for example to identify whether a quadratic
function intersects the x-axis.

Quadratic equations with the form
![ax^2 + bx + c](https://latex.codecogs.com/svg.latex?ax%5E2%20%2B%20bx%20%2B%20c "ax^2 + bx + c")
can be simplified through factorisation using:

- 
- 

# Manipulating inequalities

Algebraic terms using inequalities are common when we want to prove the
existence of an upper or lower bound. *For example, if A is an event in
the probability space, we know that the probability of event A occurring
is between 0 and 1 inclusive i.e.*
![0 \leq P(A) \leq 1](https://latex.codecogs.com/svg.latex?0%20%5Cleq%20P%28A%29%20%5Cleq%201 "0 \leq P(A) \leq 1").

There are three rules for manipulating inequalities:

- Adding or subtracting the same quantity from both sides of an
  inequality leaves the inequality symbol unchanged.
- Multiplying or dividing both sides of an inequality by a positive
  number leaves the inequality symbol unchanged.
- Multiplying or dividing both sides of an inequality by a negative
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

- [Entry](https://plato.stanford.edu/entries/algebra/) on algebra from
  the Stanford Encyclopedia of Philosophy.  
- Khan academy [YouTube
  series](https://www.khanacademy.org/math/algebra-basics/alg-basics-algebraic-expressions#alg-basics-intro-to-variables)
  on algebra basics.  
- A
  [factsheet](https://www.mathcentre.ac.uk/resources/uploaded/mc-bus-manipinequ-2009-1.pdf)
  on manipulating inequalities from the Uk Maths Centre.
