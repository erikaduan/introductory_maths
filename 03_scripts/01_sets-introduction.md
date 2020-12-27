Introduction to sets
================
Erika Duan
2020-12-27

  - [Resources](#resources)
  - [What is a mathematical set?](#what-is-a-mathematical-set)
      - [Set notation](#set-notation)
      - [Relations](#relations)
      - [Functions](#functions)

# Resources

This section on mathematical sets is taken from [Introduction to Linear
Algebra for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#sets) by
Pablo Caceres. All credit should be attributed to Pablo Caceres.

# What is a mathematical set?

A [set](https://en.wikipedia.org/wiki/Set_\(mathematics\)) is a
collection of **distinct** mathematical objects.  
It is helpful for denoting:

  - Belonging i.e. ![a \\in
    A](https://latex.codecogs.com/png.latex?a%20%5Cin%20A "a \\in A") or
    element a is an object within set A.  
  - Inclusion i.e. ![A \\subset
    B](https://latex.codecogs.com/png.latex?A%20%5Csubset%20B
    "A \\subset B") or set A is a smaller subset within set B.

Sets do not need to be ordered and are contained within `{}`. This
nonemclature is preserved in Python.  
Two sets are equal if and only if they contain the same elements.

``` python
#-----create a set in Python-----   
set_1 = {1, 3, 4, 3, 5, 8, 8}
set_1
#> {1, 3, 4, 5, 8}  
```

## Set notation

Set notation is used to describe object belonging.  
We can also use set notation to create subsets by asserting new subset
properties i.e. by specifying a condition which only holds true for a
subset of elements within a larger set.

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/02_figures/01_sets-notation.jpg)

## Relations

Pairs of sets can be unordered or ordered:

  - For an unordered set pair, ![x, y = y,
    x](https://latex.codecogs.com/png.latex?x%2C%20y%20%3D%20y%2C%20x
    "x, y = y, x").  
  - For an ordered set pair with binary relationships, ![(x, y) \\neq
    (y,x)](https://latex.codecogs.com/png.latex?%28x%2C%20y%29%20%5Cneq%20%28y%2Cx%29
    "(x, y) \\neq (y,x)").

Sets of ordered pairs can be denoted using the concept of relations.
Relations have a domain and range.

**Domain:** the values of x such that at least one element of y has an
(x, y) ordered relationship.  
![domain\\;R = \\{x:
for\\;some\\;y(x\\:R\\:y)\\}](https://latex.codecogs.com/png.latex?domain%5C%3BR%20%3D%20%5C%7Bx%3A%20for%5C%3Bsome%5C%3By%28x%5C%3AR%5C%3Ay%29%5C%7D
"domain\\;R = \\{x: for\\;some\\;y(x\\:R\\:y)\\}")

**Range:** the values of y such that at least one element of x has an
(x, y) ordered relationship.  
![range\\;R = \\{y:
for\\;some\\;x(x\\:R\\:y)\\}](https://latex.codecogs.com/png.latex?range%5C%3BR%20%3D%20%5C%7By%3A%20for%5C%3Bsome%5C%3Bx%28x%5C%3AR%5C%3Ay%29%5C%7D
"range\\;R = \\{y: for\\;some\\;x(x\\:R\\:y)\\}")

## Functions

We can also consider functions as a relationship between ordered set
pairs.  
A function transforms an element x to a corresponding value of y,
i.e. for each ![x\\in
X](https://latex.codecogs.com/png.latex?x%5Cin%20X "x\\in X"), ![y\\in
Y](https://latex.codecogs.com/png.latex?y%5Cin%20Y "y\\in Y") exists
such that ![(x,y)\\in
f](https://latex.codecogs.com/png.latex?%28x%2Cy%29%5Cin%20f
"(x,y)\\in f").

This can also be denoted as a relation between ordered set pairs such
that:

  - ![f:X\\to Y](https://latex.codecogs.com/png.latex?f%3AX%5Cto%20Y
    "f:X\\to Y") or
  - ![f(x) = y](https://latex.codecogs.com/png.latex?f%28x%29%20%3D%20y
    "f(x) = y")

In machine learning, we are interested in learning functional
relationships from data, where the domain is a vector of variables that
is transformed onto a vector of target values.

``` r
#-----create a simple function in R-----  
f1 <- tibble(x = c(seq(1, 20)),
             fx = x^2)  

#-----plot function-----
f1 %>%
  ggplot(aes(x, fx)) +
  geom_point() +
  geom_smooth(formula = y ~ x^2, color = "salmon") + # plot a line of best fit according to a formula  
  scale_x_continuous(breaks = seq(min(f1$x), max(f1$x))) +
  labs(y = "f(x)") + 
  theme_minimal() +
  theme(panel.border = element_rect(fill = NA, color = "black"),
        panel.grid = element_blank())
```

<img src="01_sets-introduction_files/figure-gfm/unnamed-chunk-3-1.png" width="75%" style="display: block; margin: auto;" />

``` python
#-----create a simple function in Python-----  
import numpy as np  
import pandas as pd  
import matplotlib.pyplot as plt  
import seaborn as sns  

x = pd.Series(np.arange(1, 20+1, 1))  
fx = x.apply(lambda x: x ** 2)

f2 = pd.DataFrame({'x_values' : x, 'fx_values' : fx})

#-----plot function-----
sns.set_style("white") 

sns.scatterplot(data = f2, x = 'x_values', y = 'fx_values')
sns.lineplot(data = f2, x = 'x_values', y = 'fx_values', color = 'salmon')
```

``` python
plt.xlabel('x')
plt.ylabel('f(x)')
plt.show()  
```

<img src="01_sets-introduction_files/figure-gfm/unnamed-chunk-4-1.png" style="display: block; margin: auto;" />
