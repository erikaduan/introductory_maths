Introduction to combinatorial analysis
================
Erika Duan
3/10/23

-   <a href="#the-mn-rule" id="toc-the-mn-rule">The mn rule</a>
-   <a href="#factorials" id="toc-factorials">Factorials</a>
-   <a href="#permutations" id="toc-permutations">Permutations</a>
-   <a href="#combinations" id="toc-combinations">Combinations</a>
    -   <a href="#combinations-and-the-bijection-principle"
        id="toc-combinations-and-the-bijection-principle">Combinations and the
        bijection principle</a>
    -   <a href="#combinations-and-lattice-paths"
        id="toc-combinations-and-lattice-paths">Combinations and lattice
        paths</a>
-   <a href="#distinct-object-partions"
    id="toc-distinct-object-partions">Distinct object partions</a>
-   <a href="#pascals-identity" id="toc-pascals-identity">Pascal’s
    identity</a>
-   <a href="#vandermondes-identity"
    id="toc-vandermondes-identity">Vandermonde’s identity</a>
-   <a href="#resources" id="toc-resources">Resources</a>

<div>

> **Summary**
>
> This tutorial explains how to use factorials, permutations and
> combinations to count object combination possibilities. It also covers
> more advanced combinatorial analysis methods involving distinct object
> partitions, non-distinct object combinations and the Pascal and
> Vandermonde identities. Combinatorial analysis is a prerequisite for
> calculating event probabilities and the total possible sample space
> using the sample-point method.

</div>

# The mn rule

The
![m\times n](https://latex.codecogs.com/svg.latex?m%5Ctimes%20n "m\times n")
rule is a simple rule for finding the total number of all possible
ordered pairs
![(a_i, b_j)](https://latex.codecogs.com/svg.latex?%28a_i%2C%20b_j%29 "(a_i, b_j)")
from two different sets ![A](https://latex.codecogs.com/svg.latex?A "A")
and ![B](https://latex.codecogs.com/svg.latex?B "B").

When you have one scenario containing
![m](https://latex.codecogs.com/svg.latex?m "m") possible elements
i.e. ![A = \\{a_1, a_2, \cdots, a_m\\}](https://latex.codecogs.com/svg.latex?A%20%3D%20%5C%7Ba_1%2C%20a_2%2C%20%5Ccdots%2C%20a_m%5C%7D "A = \{a_1, a_2, \cdots, a_m\}")
and one scenario containing with
![n](https://latex.codecogs.com/svg.latex?n "n") possible elements
i.e. ![B = {b_1, b_2, \cdots, b_n}](https://latex.codecogs.com/svg.latex?B%20%3D%20%7Bb_1%2C%20b_2%2C%20%5Ccdots%2C%20b_n%7D "B = {b_1, b_2, \cdots, b_n}"),
the total number of possible joint scenarios is the total number of
ordered pairs
![(a_i, b_j)](https://latex.codecogs.com/svg.latex?%28a_i%2C%20b_j%29 "(a_i, b_j)")
where
![1 \leq i \leq m](https://latex.codecogs.com/svg.latex?1%20%5Cleq%20i%20%5Cleq%20m "1 \leq i \leq m")
and
![1 \leq j \leq n](https://latex.codecogs.com/svg.latex?1%20%5Cleq%20j%20%5Cleq%20n "1 \leq j \leq n").

This is equal to
![m\times n = mn](https://latex.codecogs.com/svg.latex?m%5Ctimes%20n%20%3D%20mn "m\times n = mn").

![](../figures/combinatorics-mn_rule.svg)

This rule is best illustrated by the scenario of rolling two dice. The
total number of possible ordered pairs of two dice rolls is
![6 \times 6 = 36](https://latex.codecogs.com/svg.latex?6%20%5Ctimes%206%20%3D%2036 "6 \times 6 = 36"),
as each dice roll generates 6 possible simple events
i.e. ![A = \\{1, 2, 3, 4, 5, 6\\}](https://latex.codecogs.com/svg.latex?A%20%3D%20%5C%7B1%2C%202%2C%203%2C%204%2C%205%2C%206%5C%7D "A = \{1, 2, 3, 4, 5, 6\}")
and
![B = \\{1, 2, 3, 4, 5, 6\\}](https://latex.codecogs.com/svg.latex?B%20%3D%20%5C%7B1%2C%202%2C%203%2C%204%2C%205%2C%206%5C%7D "B = \{1, 2, 3, 4, 5, 6\}").

This can also be denoted by
![S = \\{(a, b) : a \in \\{1, \cdots, 6\\}, b \in \\{1, \cdots, 6\\}\\}](https://latex.codecogs.com/svg.latex?S%20%3D%20%5C%7B%28a%2C%20b%29%20%3A%20a%20%5Cin%20%5C%7B1%2C%20%5Ccdots%2C%206%5C%7D%2C%20b%20%5Cin%20%5C%7B1%2C%20%5Ccdots%2C%206%5C%7D%5C%7D "S = \{(a, b) : a \in \{1, \cdots, 6\}, b \in \{1, \cdots, 6\}\}")
where
![n_S = 6\times6 = 36](https://latex.codecogs.com/svg.latex?n_S%20%3D%206%5Ctimes6%20%3D%2036 "n_S = 6\times6 = 36").

# Factorials

The definition of an n-factorial is
![n! = n! \times (n-1)! \times (n-2)! \times \cdots \times 1](https://latex.codecogs.com/svg.latex?n%21%20%3D%20n%21%20%5Ctimes%20%28n-1%29%21%20%5Ctimes%20%28n-2%29%21%20%5Ctimes%20%5Ccdots%20%5Ctimes%201 "n! = n! \times (n-1)! \times (n-2)! \times \cdots \times 1").
The total number of all possible arrangements of
**![n](https://latex.codecogs.com/svg.latex?n "n") distinct objects** in
a row is equal to ![n!](https://latex.codecogs.com/svg.latex?n%21 "n!").

![](../figures/combinatorics-factorial.svg)

For example, take a scenario where we have four different cats. The
total number of possible ways that these 4 cats can sit in a row is
equal to
![4 \times 3\times 2\times 1 = 4!](https://latex.codecogs.com/svg.latex?4%20%5Ctimes%203%5Ctimes%202%5Ctimes%201%20%3D%204%21 "4 \times 3\times 2\times 1 = 4!").
This is intuitively explained by the fact that once a cat has occupied
the first position, there are only 3 remaining cats who can occupy the
second position, and only 2 remaining cats who occupy the third
position.

<div class="panel-tabset">

## R

In R, the function `factorial()` accepts a numerical vector as its
argument.

``` r
# Calculate factorials in R ----------------------------------------------------
factorial(4)
#> [1] 24

factorial(4) == 4 * 3 * 2 * 1
#> [1] TRUE
```

## Python

In Python, the function `factional()` exists in the math module and has
a fast C type internal implementation.

``` python
# Calculate factorials in Python -----------------------------------------------
import math 
math.factorial(4)
#> 24

# Factorials can also be calculated using a for loop ---------------------------
# Method is slower than math.factorial()  

n = 4 # State n-th factorial
fact = 1
 
for i in range(1, n + 1): # To output n, Python slices to n + 1
    fact = fact * i
 
f"The factorial of {n} is {fact}"  

# The code above is equivalent to the following operations  
# fact = 1 * 1
# fact = 1 * 2
# fact = 2 * 3
# fact = 6 * 4
```

## Julia

In Julia, the function `factorial()` is in-built and accepts an integer
as its argument.

``` julia
# Calculate factorials in Julia ------------------------------------------------
factorial(4)  
#> 24

factorial(4) == 4 * 3 * 2 * 1
#> true
```

</div>

# Permutations

A permutation of objects occurs when you have
![n](https://latex.codecogs.com/svg.latex?n "n") distinct objects and
must find the total number of **ordered** object arrangements occupying
![r](https://latex.codecogs.com/svg.latex?r "r") positions, where
![r \< n](https://latex.codecogs.com/svg.latex?r%20%3C%20n "r < n").

![P^n_r = \frac{n!}{n-r!} = n \times (n-1) \times \cdots \times (n - r + 1)](https://latex.codecogs.com/svg.latex?P%5En_r%20%3D%20%5Cfrac%7Bn%21%7D%7Bn-r%21%7D%20%3D%20n%20%5Ctimes%20%28n-1%29%20%5Ctimes%20%5Ccdots%20%5Ctimes%20%28n%20-%20r%20%2B%201%29 "P^n_r = \frac{n!}{n-r!} = n \times (n-1) \times \cdots \times (n - r + 1)")

![](../figures/combinatorics-permutation.svg)

Intuitively, this makes sense as you only have
![r positions](https://latex.codecogs.com/svg.latex?r%20positions "r positions")
available for ![n](https://latex.codecogs.com/svg.latex?n "n") distinct
objects to occupy, so there are
![n](https://latex.codecogs.com/svg.latex?n "n") objects occupying the
first position,
![n - 1](https://latex.codecogs.com/svg.latex?n%20-%201 "n - 1") objects
occupying the second position and
![n - r + 1](https://latex.codecogs.com/svg.latex?n%20-%20r%20%2B%201 "n - r + 1")
objects occupying the
![r^{th}](https://latex.codecogs.com/svg.latex?r%5E%7Bth%7D "r^{th}")
position.

For example, when
![n = 4](https://latex.codecogs.com/svg.latex?n%20%3D%204 "n = 4") and
![r = 2](https://latex.codecogs.com/svg.latex?r%20%3D%202 "r = 2"), we
have 4 distinct objects occupying the first position and 3 distinct
objects occupying the second (and final) position. Therefore
![P^4_2 = 4 \times 3 = 12](https://latex.codecogs.com/svg.latex?P%5E4_2%20%3D%204%20%5Ctimes%203%20%3D%2012 "P^4_2 = 4 \times 3 = 12").

Finding the product of different permutations is useful when counting
the number of times that one of two top candidates appear in a selection
panel of two candidates from a total of five candidates. This can be
framed as finding the total different arrangements of 1) selecting 1 top
candidate from 2 top candidates and 2) selecting 1 mediocre candidate
from 3 mediocre candidates.

![P^2_1 \times P^3_1 = \frac{2!}{(2-1)!} \times \frac{3!}{(3-1)!} = 2 \times 3 = 6](https://latex.codecogs.com/svg.latex?P%5E2_1%20%5Ctimes%20P%5E3_1%20%3D%20%5Cfrac%7B2%21%7D%7B%282-1%29%21%7D%20%5Ctimes%20%5Cfrac%7B3%21%7D%7B%283-1%29%21%7D%20%3D%202%20%5Ctimes%203%20%3D%206 "P^2_1 \times P^3_1 = \frac{2!}{(2-1)!} \times \frac{3!}{(3-1)!} = 2 \times 3 = 6")

# Combinations

A combination of objects occurs when you have
![n](https://latex.codecogs.com/svg.latex?n "n") distinct objects and
must find the total number of **unordered** object arrangements
occupying ![r](https://latex.codecogs.com/svg.latex?r "r") positions,
where
![r \< n](https://latex.codecogs.com/svg.latex?r%20%3C%20n "r < n").
*For example, we consider “ACT” and “CAT” to be different ordered word
arrangements (two permutations). When order does not matter, “ACT” and
“CAT” contain the same distinct letters and are counted as the same
combination.*

![C^n_r = {n\choose r} = \frac{P^n_r}{r!} = \frac{n!}{(n-r)!r!}](https://latex.codecogs.com/svg.latex?C%5En_r%20%3D%20%7Bn%5Cchoose%20r%7D%20%3D%20%5Cfrac%7BP%5En_r%7D%7Br%21%7D%20%3D%20%5Cfrac%7Bn%21%7D%7B%28n-r%29%21r%21%7D "C^n_r = {n\choose r} = \frac{P^n_r}{r!} = \frac{n!}{(n-r)!r!}")

Intuitively, this is because the total possible arrangement of
![r](https://latex.codecogs.com/svg.latex?r "r") distinct objects is
![r!](https://latex.codecogs.com/svg.latex?r%21 "r!"). Therefore,
![C^n_r = \frac{P^n_r}{r!}](https://latex.codecogs.com/svg.latex?C%5En_r%20%3D%20%5Cfrac%7BP%5En_r%7D%7Br%21%7D "C^n_r = \frac{P^n_r}{r!}").

![](../figures/combinatorics-combination.svg)

## Combinations and the bijection principle

What happens when we are interested in the number of ways that
**identical objects** can be distributed to different locations? We can
adapt this question as a combination calculation even though it involves
positioning identical rather than distinct objects.

Consider the different ways that 2 identical hoops can be placed on two
posts:

-   We represent the scenario where both are placed on the first post as
    “oo+”.  
-   We represent the scenario where one hoop is placed on the first hoop
    and one ring is placed on the second hoop as “o+o”.  
-   We represent the scenario where two hoops are placed on the second
    hoop as “+oo”.  
-   The boundary between the two posts is therefore represented as the
    third distinct object “+”.

![](../figures/combinatorics-bijection_principle.svg)

Because the hoops are identical, the order of individual hoop placements
on the same post does not matter (as they correspond to the same
combination). Therefore, the total possible ways that two identical
hoops can be placed through two posts is equal to
![C^3_2 = \frac{3!}{(3-2)!\times2!} = \frac{3\times2\times1}{1\times2\times1} = 3](https://latex.codecogs.com/svg.latex?C%5E3_2%20%3D%20%5Cfrac%7B3%21%7D%7B%283-2%29%21%5Ctimes2%21%7D%20%3D%20%5Cfrac%7B3%5Ctimes2%5Ctimes1%7D%7B1%5Ctimes2%5Ctimes1%7D%20%3D%203 "C^3_2 = \frac{3!}{(3-2)!\times2!} = \frac{3\times2\times1}{1\times2\times1} = 3").

## Combinations and lattice paths

The **bijection principle** can also be applied to the identification of
lattice pathway solutions.

![](../figures/combinatorics-lattice_path.svg) The properties of
combination addition can also be derived from the study of lattice
paths. Consider the lattice graph above, which has end coordinates of
![(4, 3)](https://latex.codecogs.com/svg.latex?%284%2C%203%29 "(4, 3)")
along the Cartesian plane. The sum of all solutions leading to
coordinates
![(3, 3)](https://latex.codecogs.com/svg.latex?%283%2C%203%29 "(3, 3)")
and
![(4, 2)](https://latex.codecogs.com/svg.latex?%284%2C%202%29 "(4, 2)")
is equal to all the solutions leading to coordinates
![(4, 3)](https://latex.codecogs.com/svg.latex?%284%2C%203%29 "(4, 3)").

![](../figures/combinatorics-lattice_path_2.svg)

Therefore,
![C^7_3 = C^6_3 + C^6_2](https://latex.codecogs.com/svg.latex?C%5E7_3%20%3D%20C%5E6_3%20%2B%20C%5E6_2 "C^7_3 = C^6_3 + C^6_2")
where
![C^7_3 = 35](https://latex.codecogs.com/svg.latex?C%5E7_3%20%3D%2035 "C^7_3 = 35"),
![C^6_3 = 20](https://latex.codecogs.com/svg.latex?C%5E6_3%20%3D%2020 "C^6_3 = 20")
and
![C^6_2 = 15](https://latex.codecogs.com/svg.latex?C%5E6_2%20%3D%2015 "C^6_2 = 15").

# Distinct object partions

The conditions for calculating the total number of ways of partitioning
![n](https://latex.codecogs.com/svg.latex?n "n") distinct objects into
![k](https://latex.codecogs.com/svg.latex?k "k") distinct groups are:

-   A total of ![n](https://latex.codecogs.com/svg.latex?n "n") distinct
    objects are partitioned into
    ![k](https://latex.codecogs.com/svg.latex?k "k") distinct groups.  
-   Each object only appears in exactly one group.  
-   This implies that the sum of objects in all groups is equal to
    ![n](https://latex.codecogs.com/svg.latex?n "n").  
-   The groups are denoted by
    ![r_1, r_2, \cdots, r_k](https://latex.codecogs.com/svg.latex?r_1%2C%20r_2%2C%20%5Ccdots%2C%20r_k "r_1, r_2, \cdots, r_k")
    where
    ![\displaystyle\sum\_{i=1}^{k} r_i = n](https://latex.codecogs.com/svg.latex?%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bk%7D%20r_i%20%3D%20n "\displaystyle\sum_{i=1}^{k} r_i = n").

![](../figures/combinatorics-distinct_partitions.svg)

# Pascal’s identity

Pascal’s identity can be derived from an extension of the lattice path
analogy, where the sum of all solutions leading to coordinates
![(a+b-1, b)](https://latex.codecogs.com/svg.latex?%28a%2Bb-1%2C%20b%29 "(a+b-1, b)")
and
![(a+b-1, b-1)](https://latex.codecogs.com/svg.latex?%28a%2Bb-1%2C%20b-1%29 "(a+b-1, b-1)")
is equal to all the solutions leading to coordinates
![(a+b, b)](https://latex.codecogs.com/svg.latex?%28a%2Bb%2C%20b%29 "(a+b, b)").

If we substitute
![a + b - 1 = m](https://latex.codecogs.com/svg.latex?a%20%2B%20b%20-%201%20%3D%20m "a + b - 1 = m")
and ![b = k](https://latex.codecogs.com/svg.latex?b%20%3D%20k "b = k"),
we obtain the formula for Pascal’s identity.

![{m+1\choose k} = {m\choose k} + {m\choose k-1}](https://latex.codecogs.com/svg.latex?%7Bm%2B1%5Cchoose%20k%7D%20%3D%20%7Bm%5Cchoose%20k%7D%20%2B%20%7Bm%5Cchoose%20k-1%7D "{m+1\choose k} = {m\choose k} + {m\choose k-1}")
where
![m \in \\{0, 1, 2, \cdots\\}](https://latex.codecogs.com/svg.latex?m%20%5Cin%20%5C%7B0%2C%201%2C%202%2C%20%5Ccdots%5C%7D "m \in \{0, 1, 2, \cdots\}")
and
![k \in \\{1, 2, 3, \cdots\\}](https://latex.codecogs.com/svg.latex?k%20%5Cin%20%5C%7B1%2C%202%2C%203%2C%20%5Ccdots%5C%7D "k \in \{1, 2, 3, \cdots\}")

Pascal’s identity can also be derived by considering the following
scenario. Suppose we need to count the total possible unordered
arrangements of a committee, when selecting
![k](https://latex.codecogs.com/svg.latex?k "k") persons from
![m](https://latex.codecogs.com/svg.latex?m "m") men and 1 woman.

![](../figures/combinatorics-pascal_identity.svg)

# Vandermonde’s identity

The formula for Vandermonde’s identity can be derived by considering an
extension of the previous scenario. Suppose we need to count the total
possible unordered arrangements of a committee, when selecting
![k](https://latex.codecogs.com/svg.latex?k "k") persons from
![m](https://latex.codecogs.com/svg.latex?m "m") men and
![w](https://latex.codecogs.com/svg.latex?w "w") woman.

![{m+w\choose k} = {m\choose 0}{w\choose k} + {m\choose 1}{w\choose k-1} + \cdots + {m\choose k-1}{w\choose 1} + {m\choose k}{w\choose 0}](https://latex.codecogs.com/svg.latex?%7Bm%2Bw%5Cchoose%20k%7D%20%3D%20%7Bm%5Cchoose%200%7D%7Bw%5Cchoose%20k%7D%20%2B%20%7Bm%5Cchoose%201%7D%7Bw%5Cchoose%20k-1%7D%20%2B%20%5Ccdots%20%2B%20%7Bm%5Cchoose%20k-1%7D%7Bw%5Cchoose%201%7D%20%2B%20%7Bm%5Cchoose%20k%7D%7Bw%5Cchoose%200%7D "{m+w\choose k} = {m\choose 0}{w\choose k} + {m\choose 1}{w\choose k-1} + \cdots + {m\choose k-1}{w\choose 1} + {m\choose k}{w\choose 0}")

# Resources

-   A
    [tutorial](https://www.mathsisfun.com/combinatorics/combinations-permutations.html)
    comparing permutations and combinations from
    [Mathsisfun.com](https://www.mathsisfun.com/).
