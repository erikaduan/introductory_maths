Probability theory - introduction
================
Erika Duan
2022-04-18

-   [Introduction to probability](#introduction-to-probability)
    -   [Scenario 1](#scenario-1)
    -   [Scenario 2](#scenario-2)
-   [Set notations](#set-notations)
    -   [The power set](#the-power-set)
-   [Set operations](#set-operations)
-   [General rules of probability](#general-rules-of-probability)
-   [Acknowledgements](#acknowledgements)

# Introduction to probability

Probability is an abstract concept. The frequentist approach considers
probability as the relative frequency of a specific outcome, observed
from a sample of the true population. The Bayesian approach considers
probability as a subjective possibility space dependent on the prior
hypothesis and the observed evidence.

Probability can be best thought of as the size of a mathematical set
(which can be represented in 2D as a proportion of the total area).

## Scenario 1

Imagine that we simultaneously rolled two fair dice. What is the
probability that the sum of two dice equals 5?

-   From our understanding of the properties of fair dice, we know that
    the outcome of one dice throw is independent of another.  
-   We need to calculate all possible combinations of two independent
    dice rolls. The total number of possible combinations is the
    **sample space** i.e. the set of all possible outcomes. As there are
    6 faces on one dice and we are rolling two dice, the sample space is
    ![6\\times6](https://latex.codecogs.com/svg.format?6%5Ctimes6 "6\times6")
    or ![6^2](https://latex.codecogs.com/svg.format?6%5E2 "6^2")
    possible outcomes.  
-   We would then calculate all possible combinations of dice rolls
    which sum to 5. This is the **event**
    (![E](https://latex.codecogs.com/svg.format?E "E")), which is a
    smaller subset of the sample space.  
-   The **probability** of the event occurring is therefore the ratio of
    the event relative to the sample space.  
-   In this scenario, the probability that the sum of two dice equals 5
    is
    ![\\frac{4}{36}](https://latex.codecogs.com/svg.format?%5Cfrac%7B4%7D%7B36%7D "\frac{4}{36}")
    or approximately 0.11.

<img src="../figures/probability-introduction_to_probability-scenario_1.svg" width="70%" style="display: block; margin: auto;" />

## Scenario 2

Imagine that we simultaneously rolled two fair dice. What is the
probability that the sum of two dice is less than 5 **and** an odd
number?

-   The sample space is still the same, as the total number of possible
    dice roll combinations is fixed.  
-   The event subset has changed as we are interested in the
    intersection of
    ![E_1\\subset\\{2, 3, 4\\}](https://latex.codecogs.com/svg.format?E_1%5Csubset%5C%7B2%2C%203%2C%204%5C%7D "E_1\subset\{2, 3, 4\}")
    and
    ![E_2\\subset\\{2, 4, 6\\}](https://latex.codecogs.com/svg.format?E_2%5Csubset%5C%7B2%2C%204%2C%206%5C%7D "E_2\subset\{2, 4, 6\}")
    i.e. ![E=E_1\\cap E_2=\\{2, 4\\}](https://latex.codecogs.com/svg.format?E%3DE_1%5Ccap%20E_2%3D%5C%7B2%2C%204%5C%7D "E=E_1\cap E_2=\{2, 4\}").  
-   In this scenario, the probability that the sum of two dice is
    ![\\{2,4\\}](https://latex.codecogs.com/svg.format?%5C%7B2%2C4%5C%7D "\{2,4\}")
    is
    ![\\frac{4}{36}](https://latex.codecogs.com/svg.format?%5Cfrac%7B4%7D%7B36%7D "\frac{4}{36}")
    or approximately 0.11.

<img src="../figures/probability-introduction_to_probability-scenario_2.svg" width="70%" style="display: block; margin: auto;" />

# Set notations

Sets are used to denote object belonging under a specific condition. The
statement “the set of elements
![x](https://latex.codecogs.com/svg.format?x "x") in the space
![X](https://latex.codecogs.com/svg.format?X "X") such that condition
![f(x)\>0](https://latex.codecogs.com/svg.format?f%28x%29%3E0 "f(x)>0")
holds” is represented by the notation
![S = \\{x\\in X\\vert f(x)\>0\\}](https://latex.codecogs.com/svg.format?S%20%3D%20%5C%7Bx%5Cin%20X%5Cvert%20f%28x%29%3E0%5C%7D "S = \{x\in X\vert f(x)>0\}").

<img src="../figures/probability-introduction_to_probability-set_notations.svg" width="70%" style="display: block; margin: auto;" />

Examples of sets include:

-   The set
    ![A_1 = \\{x\\in\\mathbb{N}\\vert 1\\leq x\\leq 5\\}](https://latex.codecogs.com/svg.format?A_1%20%3D%20%5C%7Bx%5Cin%5Cmathbb%7BN%7D%5Cvert%201%5Cleq%20x%5Cleq%205%5C%7D "A_1 = \{x\in\mathbb{N}\vert 1\leq x\leq 5\}")
    is a finite set with a finite closed interval on the set of all
    natural numbers.  
-   The set
    ![A_2 = \\{x\\in\\mathbb{R}\\vert -5\\leq x\\leq 1\\}](https://latex.codecogs.com/svg.format?A_2%20%3D%20%5C%7Bx%5Cin%5Cmathbb%7BR%7D%5Cvert%20-5%5Cleq%20x%5Cleq%201%5C%7D "A_2 = \{x\in\mathbb{R}\vert -5\leq x\leq 1\}")
    is an infinite set with a finite closed interval on the set of all
    real numbers.  
-   The set
    ![F = \\{f:\\mathbb{R}\\to\\mathbb{R}\\vert f(x)=ax+b,\\;a,b\\in\\mathbb{R}\\}](https://latex.codecogs.com/svg.format?F%20%3D%20%5C%7Bf%3A%5Cmathbb%7BR%7D%5Cto%5Cmathbb%7BR%7D%5Cvert%20f%28x%29%3Dax%2Bb%2C%5C%3Ba%2Cb%5Cin%5Cmathbb%7BR%7D%5C%7D "F = \{f:\mathbb{R}\to\mathbb{R}\vert f(x)=ax+b,\;a,b\in\mathbb{R}\}")
    is an infinite set of all straight lines in 2D as
    ![f](https://latex.codecogs.com/svg.format?f "f") takes the specific
    form
    ![f(x)=ax+b](https://latex.codecogs.com/svg.format?f%28x%29%3Dax%2Bb "f(x)=ax+b").

In probability theory, the event can be viewed as a subset within the
set of the sample space, where the total number of possible event types
(or total possible event combinations) is represented by the power set
of the sample space.

## The power set

When the elements inside a set are finite and countable, we can
calculate the total number of possible event types in two elegant ways.

Consider the graphical approach drawn below. We can map all possible
element combinations for every possible subset size. Doing so highlights
the existence of graph symmetry where, for example, the smallest and
largest subsets contain the same number of element combinations i.e. 1.
The graphical approach, however, is cumbersome for large sets.

<img src="../figures/probability-introduction_to_probability-power_set_graphs.svg" width="80%" style="display: block; margin: auto;" />

We can then consider the numerical approach. For each subset size, we
must calculate how many unique element combinations exist. We do not
care about element order and element repetition also cannot occur.

When a set has 3 elements, the combinations of a subset containing 2
elements is
![\\frac{3!}{(3-2)!\\times 2!}](https://latex.codecogs.com/svg.format?%5Cfrac%7B3%21%7D%7B%283-2%29%21%5Ctimes%202%21%7D "\frac{3!}{(3-2)!\times 2!}")
or
![{3\\choose2}](https://latex.codecogs.com/svg.format?%7B3%5Cchoose2%7D "{3\choose2}").  
For the same set of 3 elements, the combinations of a subset containing
1 element is
![\\frac{3!}{(3-1)!\\times 1!}](https://latex.codecogs.com/svg.format?%5Cfrac%7B3%21%7D%7B%283-1%29%21%5Ctimes%201%21%7D "\frac{3!}{(3-1)!\times 1!}")
or
![{3\\choose1}](https://latex.codecogs.com/svg.format?%7B3%5Cchoose1%7D "{3\choose1}").

**Note:** The graph symmetry of a power set can be explained by the
observation that
![\\frac{3!}{(3-2)!\\times 2!}= \\frac{3!}{(3-1)!\\times 1!} = \\frac{3!}{2!}](https://latex.codecogs.com/svg.format?%5Cfrac%7B3%21%7D%7B%283-2%29%21%5Ctimes%202%21%7D%3D%20%5Cfrac%7B3%21%7D%7B%283-1%29%21%5Ctimes%201%21%7D%20%3D%20%5Cfrac%7B3%21%7D%7B2%21%7D "\frac{3!}{(3-2)!\times 2!}= \frac{3!}{(3-1)!\times 1!} = \frac{3!}{2!}").

<img src="../figures/probability-introduction_to_probability-power_set_combinations.svg" width="80%" style="display: block; margin: auto;" />

The power set, or total number of possible event types, is therefore the
sum of all possible subset combinations. A quick [mathematical
proof](https://www.youtube.com/watch?v=wM9T--A1gQA) using the binomial
theorem shows how the power set can be calculated as
![2^n](https://latex.codecogs.com/svg.format?2%5En "2^n"), where n is
the size of the set.

# Set operations

Set operations are methods for manipulating sets and are useful tools
for describing the properties of the probability space.

-   The set **complement** is defined as all the elements that do not
    belong in the specified set. The set complement can be used to
    describe the probability that an event does not occur.  
-   The **union** of two sets is defined as the set of elements that are
    included in either set. The union of two sets can be used to
    describe the probability of either event A or event B occurring.  
-   The **intersection** of two sets is defined as the set of elements
    that are included in both sets. The intersection of two sets can be
    used to describe the probability that event A and event B both
    occurs.

<img src="../figures/probability-introduction_to_probability-set_operations.svg" width="80%" style="display: block; margin: auto;" />

``` r
# Perform set operations in R --------------------------------------------------
a <- c(1, 2, 3)
b <- c(2, 4) 

union(a, b)
#> [1] 1 2 3 4

intersect(a, b)  
#> [1] 2 

setdiff(a, b)
#> [1] 1 3 

setequal(a, b) 
#> [1] FALSE
```

``` python
# Perform set operations in Python ---------------------------------------------
# Variables in the R environment can be accessed in Python via R.variable
# Atomic vectors in R are automatically converted into Python lists

a = set(r.a)
b = set(r.b)

a.union(b) # Can also be evaluated as a | b
#> {1.0, 2.0, 3.0, 4.0} 
```

``` python
a.intersection(b) # Can also be evaluated as a & b
#> {2.0} 
```

``` python
a.difference(b)
#> {1.0, 3.0}
```

``` python
a.symmetric_difference(b) # Can also be evaluated as a ^ b
#> {1.0, 3.0, 4.0}
```

Revisiting [scenario 2](#Scenario%202), the probability that the sum of
two dice is less than 5 **and** an odd number is the intersection of
![E_1\\subset\\{2,3,4\\}](https://latex.codecogs.com/svg.format?E_1%5Csubset%5C%7B2%2C3%2C4%5C%7D "E_1\subset\{2,3,4\}")
and
![E_2\\subset\\{2,4,6\\}](https://latex.codecogs.com/svg.format?E_2%5Csubset%5C%7B2%2C4%2C6%5C%7D "E_2\subset\{2,4,6\}")
or
![E=E_1\\cap E_2=\\{2,4\\}](https://latex.codecogs.com/svg.format?E%3DE_1%5Ccap%20E_2%3D%5C%7B2%2C4%5C%7D "E=E_1\cap E_2=\{2,4\}").

If we were asked to find the probability that the sum of two dice is
less than 5 **or** an odd number, this would be
![E=E_1\\cup E_2=\\{2,3,4,6\\}](https://latex.codecogs.com/svg.format?E%3DE_1%5Ccup%20E_2%3D%5C%7B2%2C3%2C4%2C6%5C%7D "E=E_1\cup E_2=\{2,3,4,6\}"),
which is a very different subset of the sample space.

# General rules of probability

We can think of a function as a relation that associates a set of
elements in the input space (subset A in X) to a set of elements in the
output space (subset B in Y). A function induces this mapping of
![A\\to B](https://latex.codecogs.com/svg.format?A%5Cto%20B "A\to B") by
applying itself to each individual element in the input space. The act
of being a relation implies that an inverse function also exists, which
maps the set of elements in the output space back to the set of elements
in the input space
i.e. ![A = f^{-1}(B)](https://latex.codecogs.com/svg.format?A%20%3D%20f%5E%7B-1%7D%28B%29 "A = f^{-1}(B)").

A probability distribution can be thought of as the function which maps
a set of events to their set of probabilities.

<img src="../figures/probability-introduction_to_probability-set_mappings.svg" width="80%" style="display: block; margin: auto;" />

Consider the set ![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1")
as a subset of the sample space X, where
![P\_\\pi(A_1)](https://latex.codecogs.com/svg.format?P_%5Cpi%28A_1%29 "P_\pi(A_1)")
is the probability assigned to
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") by the
probability distribution
![\\pi](https://latex.codecogs.com/svg.format?%5Cpi "\pi"):  
+ The probability of X is the probability of all events (or all possible
subsets) occurring
i.e. ![P\_{\\pi}(X)=1](https://latex.codecogs.com/svg.format?P_%7B%5Cpi%7D%28X%29%3D1 "P_{\pi}(X)=1").
Since probability is the ratio of the event to the sample space, we can
define
![P\_{\\pi}(X)=1](https://latex.codecogs.com/svg.format?P_%7B%5Cpi%7D%28X%29%3D1 "P_{\pi}(X)=1")
for simplicity.  
+ The complement of
![P\_{\\pi}(X)=1](https://latex.codecogs.com/svg.format?P_%7B%5Cpi%7D%28X%29%3D1 "P_{\pi}(X)=1")
is the probability of an impossible event
i.e. ![P\_{\\pi}(X^C)=0](https://latex.codecogs.com/svg.format?P_%7B%5Cpi%7D%28X%5EC%29%3D0 "P_{\pi}(X^C)=0").  
+ The range of possible probabilities for
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") is therefore
![0\\leq P\_{\\pi}(A_1)\\leq1](https://latex.codecogs.com/svg.format?0%5Cleq%20P_%7B%5Cpi%7D%28A_1%29%5Cleq1 "0\leq P_{\pi}(A_1)\leq1")
and
![P\_{\\pi}(A_1)=1-P\_{\\pi}(A_1^C)](https://latex.codecogs.com/svg.format?P_%7B%5Cpi%7D%28A_1%29%3D1-P_%7B%5Cpi%7D%28A_1%5EC%29 "P_{\pi}(A_1)=1-P_{\pi}(A_1^C)").

<img src="../figures/probability-introduction_to_probability-set_mutually_exclusive.svg" width="70%" style="display: block; margin: auto;" />

Consider the set ![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2")
as a different subset of the sample space X:  
+ If ![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") and
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") are mutually
exclusive (elements in
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") and
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") do not overlap),
the intersection of
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") and
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") is 0
i.e. ![P\_\\pi(A_1\\cap A_2) = 0](https://latex.codecogs.com/svg.format?P_%5Cpi%28A_1%5Ccap%20A_2%29%20%3D%200 "P_\pi(A_1\cap A_2) = 0")
and the probability of
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") or
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") occurring is
![P\_\\pi(A_1\\cup A_2) = P\_\\pi(A_1) + P\_\\pi(A_2)](https://latex.codecogs.com/svg.format?P_%5Cpi%28A_1%5Ccup%20A_2%29%20%3D%20P_%5Cpi%28A_1%29%20%2B%20P_%5Cpi%28A_2%29 "P_\pi(A_1\cup A_2) = P_\pi(A_1) + P_\pi(A_2)").  
+ If ![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") and
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") are not mutually
exclusive (elements in
![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1") and
![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") overlap), the
probability of ![A_1](https://latex.codecogs.com/svg.format?A_1 "A_1")
or ![A_2](https://latex.codecogs.com/svg.format?A_2 "A_2") occurring is
![P\_\\pi(A_1\\cup A_2) = P\_\\pi(A_1) + P\_\\pi(A_2) - P\_\\pi(A_1\\cap A_2)](https://latex.codecogs.com/svg.format?P_%5Cpi%28A_1%5Ccup%20A_2%29%20%3D%20P_%5Cpi%28A_1%29%20%2B%20P_%5Cpi%28A_2%29%20-%20P_%5Cpi%28A_1%5Ccap%20A_2%29 "P_\pi(A_1\cup A_2) = P_\pi(A_1) + P_\pi(A_2) - P_\pi(A_1\cap A_2)").

**Note**: The term mutually exclusive refers to the property of whether
elements in two or more subsets overlap with each other.

# Acknowledgements

The source materials for this tutorial are:

-   The [Probability for Data Science
    textbook](https://probability4datascience.com/) by Stanley H Chan,
    specifically [Chapter
    2](https://drive.google.com/file/d/1v9jLsbwG5Tl5d7XfLCfmhHuOkZZUOVNa/view)
    on probability  
-   Introduction to probability theory [GitHub
    resource](https://betanalpha.github.io/assets/case_studies/probability_theory.html)
    by Michael Betancourt  
-   Introduction to probability theory [Youtube
    series](https://www.youtube.com/playlist?list=PLUl4u3cNGP60hI9ATjSFgLZpbNJ7myAg6)
    from MIT  
-   [General probability rules from
    STAT800](https://online.stat.psu.edu/stat800/lesson/general-probability-rules)
    from Penn State Eberly College of Science
