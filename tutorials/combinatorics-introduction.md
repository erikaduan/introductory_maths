Introduction to combinatorial analysis
================
Erika Duan
3/10/23

-   <a href="#the-mn-rule" id="toc-the-mn-rule">The mn rule</a>
-   <a href="#factorials" id="toc-factorials">Factorials</a>
-   <a href="#resources" id="toc-resources">Resources</a>

<div>

> **Summary**
>
> This tutorial explains how to use factorials, permutations and
> combinations to count object combination possibilities. It also covers
> more advanced scenarios involving distinct object partitioning,
> non-distinct object combinations, lattice path applications and
> Pascal’s identity applications. Combinatorial analysis is a
> prerequisite for calculating event probabilities using the
> sample-point method.

</div>

# The mn rule

The
![m\times n](https://latex.codecogs.com/svg.latex?m%5Ctimes%20n "m\times n")
rule is a simple rule for finding the total number of possible ordered
pairs
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

# Resources

-   
