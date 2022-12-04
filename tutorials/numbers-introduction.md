Introduction to numbers
================
Erika Duan
12/4/22

-   <a href="#numbers" id="toc-numbers">Numbers</a>
-   <a href="#natural-numbers" id="toc-natural-numbers">Natural numbers</a>
-   <a href="#integers" id="toc-integers">Integers</a>
-   <a href="#real-numbers" id="toc-real-numbers">Real numbers</a>
-   <a href="#complex-numbers" id="toc-complex-numbers">Complex numbers</a>
-   <a href="#resources" id="toc-resources">Resources</a>

# Numbers

Numbers are used to:

-   Count objects. *For example, I have 10 tutorials to read.*  
-   Describe object behaviour. *For example, the area of a unit circle
    is*
    ![\pi r^2](https://latex.codecogs.com/svg.latex?%5Cpi%20r%5E2 "\pi r^2")
    where
    ![r = 1](https://latex.codecogs.com/svg.latex?r%20%3D%201 "r = 1").  
-   Solve problems, often by introducing simple assumptions. *For
    example, if 5 bees can pollinate a*
    ![100 m^2](https://latex.codecogs.com/svg.latex?100%20m%5E2 "100 m^2")
    field in 10 minutes, how many bees are required to pollinate a 350
    ![m^2](https://latex.codecogs.com/svg.latex?m%5E2 "m^2") field?
    Assume that pollination efficiency scales perfectly and is not
    impacted by land shape.  
-   Represent complex abstractions. *For example, how can individual
    words be represented in an n-dimensional feature space?*

Numbers can be classified into different categories according to their
properties. A number can belong to multiple categories. For example, the
number 2 is a **count** (a natural number) and a **whole number** (an
integer), and can be represented as a **fraction**
i.e. ![\tfrac{2}{1}](https://latex.codecogs.com/svg.latex?%5Ctfrac%7B2%7D%7B1%7D "\tfrac{2}{1}")
(a rational number) and a **complex number**
i.e. ![3+i^2](https://latex.codecogs.com/svg.latex?3%2Bi%5E2 "3+i^2").

Number classifications have an elegant hierarchical property:

-   All natural numbers are integers.  
-   All integers are rational numbers
    i.e. ![n = \tfrac{n}{1}](https://latex.codecogs.com/svg.latex?n%20%3D%20%5Ctfrac%7Bn%7D%7B1%7D "n = \tfrac{n}{1}").  
-   All rational numbers are complex numbers
    i.e. ![\tfrac{n}{1} = \tfrac{n}{1}+0i](https://latex.codecogs.com/svg.latex?%5Ctfrac%7Bn%7D%7B1%7D%20%3D%20%5Ctfrac%7Bn%7D%7B1%7D%2B0i "\tfrac{n}{1} = \tfrac{n}{1}+0i").

![](../figures/numbers-categories.svg)

# Natural numbers

Natural numbers
(![\mathbb{N}](https://latex.codecogs.com/svg.latex?%5Cmathbb%7BN%7D "\mathbb{N}"))
are useful for describing the dimensions of mathematical space (also
known as a [feature
space](https://stats.stackexchange.com/questions/46425/what-is-feature-space)).
For example, the Cartesian plane is an example of an
![\mathbb{R}^2](https://latex.codecogs.com/svg.latex?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2")
feature space.

An extension of natural numbers is the need to partition them into
consistent bundles, to represent very large natural numbers. For
example, the **base 10** or **decimal** system represents 136 as
![(1\times10^2) + (3\times 10^1) + (6\times 10^0)](https://latex.codecogs.com/svg.latex?%281%5Ctimes10%5E2%29%20%2B%20%283%5Ctimes%2010%5E1%29%20%2B%20%286%5Ctimes%2010%5E0%29 "(1\times10^2) + (3\times 10^1) + (6\times 10^0)")
whereas the **base 2** or **binary** system represents 136 as
![(1\times2^7) + (0\times 2^6) + (0\times 2^5) + (0\times 2^4) + (1\times 2^3) + (0\times 2^2) + (0\times 2^1) + (0\times 2^0)](https://latex.codecogs.com/svg.latex?%281%5Ctimes2%5E7%29%20%2B%20%280%5Ctimes%202%5E6%29%20%2B%20%280%5Ctimes%202%5E5%29%20%2B%20%280%5Ctimes%202%5E4%29%20%2B%20%281%5Ctimes%202%5E3%29%20%2B%20%280%5Ctimes%202%5E2%29%20%2B%20%280%5Ctimes%202%5E1%29%20%2B%20%280%5Ctimes%202%5E0%29 "(1\times2^7) + (0\times 2^6) + (0\times 2^5) + (0\times 2^4) + (1\times 2^3) + (0\times 2^2) + (0\times 2^1) + (0\times 2^0)").

![](../figures/numbers-number_system.svg)

The binary number system is a more cumbersome representation, but its
binary expression range (as a series of logic gates outputting 0s or 1s)
underlies its adoption by computer-based systems.

# Integers

Integers are whole numbers that can be either positive or negative.

<div class="panel-tabset">

## R

In R, we assign a whole number as an integer type by either denoting an
`L` after the number or using `as.integer()`. If we assign a whole
number without `L`, R assigns the number as a `double` type. Both
`integer` and `double` data types belong to the `numeric` class.

``` r
# Check whole number type in R -------------------------------------------------
# Be careful of the difference between class() and typeof()
# https://adv-r.hadley.nz/base-types.html 

typeof(3L)
#> [1] "integer"

typeof(3)
#> [1] "double" 

class(3L)
#> [1] "integer" 

class(3)
#> [1] "numeric"   
```

## Python

In Python, we assign a whole number as an integer type by default. There
is no limit on how long an integer can be in Python.

``` python
# Check whole number type in Python --------------------------------------------
type(3)
#> <class 'int'>  
```

## Julia

In Julia, [multiple integer types
exist](https://docs.julialang.org/en/v1/manual/integers-and-floating-point-numbers/)
and the default type is `Int64` or `Int32` depending on whether your
computer system has a 64-bit or 32-bit architecture.

``` julia
# Check whole number type in Julia ---------------------------------------------
typeof(3)
#> Int64  

# Check minimum and maximum possible integers
(typemin(Int8), typemax(Int8))
#> (-128, 127)  

(typemin(Int64), typemax(Int64))
#> (-9223372036854775808, 9223372036854775807)  
```

</div>

# Real numbers

# Complex numbers

# Resources

-   The [Wikipedia
    article](https://en.wikipedia.org/wiki/Number#Main_classification)
    on the number system.  
-   The [Numberphile YouTube
    video](https://www.youtube.com/watch?v=NHZt8eBKcRA) on numbers.  
-   Introduction to number systems and binary numbers from [Khan
    Academy](https://www.youtube.com/watch?v=ku4KOFQ-bB4).  
-   Introduction to rational and irrational numbers from [Khan
    Academy](https://www.youtube.com/watch?v=cLP7INqs3JM).
