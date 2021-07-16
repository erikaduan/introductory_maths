Introduction to sets
================
Erika Duan
2021-07-14

-   [Resources](#resources)
-   [What is a mathematical set?](#what-is-a-mathematical-set)
    -   [Set notation](#set-notation)
    -   [Relations](#relations)
    -   [Functions](#functions)
-   [Further reading](#further-reading)

# Resources

This section on mathematical sets is taken from [Introduction to Linear
Algebra for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#vectors) by
Pablo Caceres. All credit should be attributed to Pablo Caceres.

# What is a mathematical set?

A [set](https://en.wikipedia.org/wiki/Set_(mathematics)) is a collection
of **distinct** mathematical objects.  
It is helpful for denoting:

-   Belonging
    i.e. ![a \\in A](https://latex.codecogs.com/png.latex?a%20%5Cin%20A "a \in A")
    or element a is an object within set A.  
-   Inclusion
    i.e. ![A \\subset B](https://latex.codecogs.com/png.latex?A%20%5Csubset%20B "A \subset B")
    or set A is a smaller subset within set B.

Sets do not need to be ordered and are contained within `{}`. This
nomenclature is preserved in Python.  
Two sets are equal if and only if they contain the same elements.

``` python
# Create a set in Python -------------------------------------------------------   
set_1 = {1, 3, 4, 3, 5, 8, 8}
set_1
#> {1, 3, 4, 5, 8}  
```

## Set notation

Set notation is used to describe object belonging within a group.

We also use set notation to create subsets (or subgroups) by specifying
conditions which only hold true for a subset of elements within a larger
group. For example,
![S = \\{ d \\in D \\; \| \\; d \\; is \\; pupper \\}](https://latex.codecogs.com/png.latex?S%20%3D%20%5C%7B%20d%20%5Cin%20D%20%5C%3B%20%7C%20%5C%3B%20d%20%5C%3B%20is%20%5C%3B%20pupper%20%5C%7D "S = \{ d \in D \; | \; d \; is \; pupper \}")
generates a new subset S from the set of all dogs D, where all dogs in S
are puppers.

<img src="../02_figures/02_sets-notation.jpg" width="100%" style="display: block; margin: auto;" />

## Relations

Pairs of sets can be unordered or ordered:

-   For an unordered set pair,
    ![x, y = y, x](https://latex.codecogs.com/png.latex?x%2C%20y%20%3D%20y%2C%20x "x, y = y, x").  
-   For an ordered set pair,
    ![(x, y) \\neq (y, x)](https://latex.codecogs.com/png.latex?%28x%2C%20y%29%20%5Cneq%20%28y%2C%20x%29 "(x, y) \neq (y, x)").

Relations are defined as sets of ordered pairs and denoted using
![R](https://latex.codecogs.com/png.latex?R "R"). Relations have a
domain and range.

**Domain:** the **values of x** such that at least one element of
![y](https://latex.codecogs.com/png.latex?y "y") has an
![(x, y)](https://latex.codecogs.com/png.latex?%28x%2C%20y%29 "(x, y)")
ordered relationship.  
![domain\\;R = \\{x: for\\;some\\;y(x\\:R\\:y)\\}](https://latex.codecogs.com/png.latex?domain%5C%3BR%20%3D%20%5C%7Bx%3A%20for%5C%3Bsome%5C%3By%28x%5C%3AR%5C%3Ay%29%5C%7D "domain\;R = \{x: for\;some\;y(x\:R\:y)\}")

**Range:** the **values of y** such that at least one element of x has
an (x, y) ordered relationship.  
![range\\;R = \\{y: for\\;some\\;x(x\\:R\\:y)\\}](https://latex.codecogs.com/png.latex?range%5C%3BR%20%3D%20%5C%7By%3A%20for%5C%3Bsome%5C%3Bx%28x%5C%3AR%5C%3Ay%29%5C%7D "range\;R = \{y: for\;some\;x(x\:R\:y)\}")

## Functions

We can also consider functions as the relation between ordered set
pairs.  
A function transforms an element
![x](https://latex.codecogs.com/png.latex?x "x") to its corresponding
value of ![y](https://latex.codecogs.com/png.latex?y "y"), i.e. for each
![x\\in X](https://latex.codecogs.com/png.latex?x%5Cin%20X "x\in X"), a
unique element of
![y\\in Y](https://latex.codecogs.com/png.latex?y%5Cin%20Y "y\in Y")
exists such that
![(x,y)\\in f](https://latex.codecogs.com/png.latex?%28x%2Cy%29%5Cin%20f "(x,y)\in f").

This can also be formally denoted as:

-   ![f:X\\to Y](https://latex.codecogs.com/png.latex?f%3AX%5Cto%20Y "f:X\to Y")
    or
-   ![f(x) = y](https://latex.codecogs.com/png.latex?f%28x%29%20%3D%20y "f(x) = y")

In machine learning, we are interested in approximating or learning
functions. I.e. we are interesting in deriving the relation
![x \\: R \\: y](https://latex.codecogs.com/png.latex?x%20%5C%3A%20R%20%5C%3A%20y "x \: R \: y")
where the domain comprises a matrix of predictor variables that is
transformed by a relation into a vector of response variables.

``` r
# Simulate a simple functional relationship in R -------------------------------  
# The true functional relationship is y = x ^ 2   
x1 <- seq(1, 20, 1)
simulate_y <- function(x) (x ^ 2) + rnorm(1, 0, 4)

set.seed(111)
y1 <- simulate_y(x1)

df1 <- tibble(x = x1, 
              y = y1)

# Plot function using ggplot ---------------------------------------------------
df1 %>%
  ggplot(aes(x, y)) +
  geom_point() +
  # Plot a line of best fit according to a formula
  geom_smooth(formula = y ~ x^2, color = "salmon", lwd = 0.5) +   
  scale_x_continuous(breaks = seq(min(df1$x), max(df1$x))) +
  labs(y = "f(x)",
       title = "A function will never map x to more than one solution for y.") + 
  theme_minimal() +
  theme(plot.title = element_text(hjust = 0.5),
        panel.border = element_rect(fill = NA, color = "black"),
        panel.grid = element_blank())
```

<img src="02_sets-introduction_files/figure-gfm/unnamed-chunk-5-1.png" width="70%" style="display: block; margin: auto;" />

``` python
# Simulate a simple functional relationship in Python --------------------------  
# The true functional relationship is y = x ^ 2   
import numpy as np  
import pandas as pd  
import matplotlib.pyplot as plt  
import seaborn as sns  

x2 = pd.Series(np.arange(1, 20+1, 1))  
y2 = x2.apply(lambda x: x ** 2 + np.random.normal(0, 4)) 
func_relationship = x2.apply(lambda x: x ** 2) 

df2 = pd.DataFrame({'x' : x2,
                    'fx' : y2,
                    'funs' : func_relationship})

# Plot function using sns and plt ----------------------------------------------
sns.set_style("white") 

sns.scatterplot(data = df2, x = 'x', y = 'fx')
sns.lineplot(data = df2, x = 'x', y = 'funs', color = 'salmon', lw = 0.5)
plt.xticks(np.arange(1, 20 ,1))
plt.xlabel('x')
plt.ylabel('f(x)')
plt.title('Plotting in Python requires hardcoding of the true function.')
plt.show()  
```

<img src="02_sets-introduction_files/figure-gfm/unnamed-chunk-3-1.png" width="70%" style="display: block; margin: auto;" />

# Further reading

-   An introduction to
    [functions](https://courses.lumenlearning.com/boundless-algebra/chapter/introduction-to-functions/#:~:text=Functions%20are%20a%20relation%20between,is%20open%20on%20two%20ends)
    from Boundless Algebra.
