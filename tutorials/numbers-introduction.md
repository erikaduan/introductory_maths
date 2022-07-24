Introduction to numbers
================
Erika Duan
2022-07-24

-   [Numbers](#numbers)
-   [Natural numbers](#natural-numbers)
-   [Real numbers](#real-numbers)
-   [Complex numbers](#complex-numbers)
-   [Resources](#resources)

# Numbers

Numbers are used to:  
+ Count objects. For example, I have 1 :apple:.  
+ Describe object behaviour. For example, the area of a :white_circle:
is
![\\pi r^2](https://latex.codecogs.com/svg.format?%5Cpi%20r%5E2 "\pi r^2").  
+ Solve problems, often by introducing simple assumptions. For example,
if 5 :bee: can pollinate a 100
![m^2](https://latex.codecogs.com/svg.format?m%5E2 "m^2") field in 10
minutes, how many :bee: are required to pollinate a 350
![m^2](https://latex.codecogs.com/svg.format?m%5E2 "m^2") field? Assume
that pollination efficiency scales perfectly and is not impacted by land
shape.  
+ Represent complex abstractions. For example, how can individual words
be represented in an n-dimensional feature space?

Numbers can be classified into different categories according to their
properties. A number can belong to multiple categories. For example, the
number 2 is a count (a natural number) and a whole number (an integer),
and can also be represented as a fraction
i.e. ![\\tfrac{2}{1}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B2%7D%7B1%7D "\tfrac{2}{1}")
(a rational number) and a complex number
i.e. ![3+i^2](https://latex.codecogs.com/svg.format?3%2Bi%5E2 "3+i^2").

Number classifications have an elegant hierarchical property. All
natural numbers are integers. All integers are rational numbers
i.e. ![n = \\tfrac{n}{1}](https://latex.codecogs.com/svg.format?n%20%3D%20%5Ctfrac%7Bn%7D%7B1%7D "n = \tfrac{n}{1}").
All rational numbers are complex numbers
i.e. ![\\tfrac{n}{1} = \\tfrac{n+1}{1}+i^2](https://latex.codecogs.com/svg.format?%5Ctfrac%7Bn%7D%7B1%7D%20%3D%20%5Ctfrac%7Bn%2B1%7D%7B1%7D%2Bi%5E2 "\tfrac{n}{1} = \tfrac{n+1}{1}+i^2").

<img src="../figures/numbers-categories.svg" width="90%" style="display: block; margin: auto;" />

> **Note**  
> Can you think of different ways to classify the number 2 compared to
> the number
> ![\\tfrac{5}{2}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B5%7D%7B2%7D "\tfrac{5}{2}")?

# Natural numbers

Natural numbers
(![\\mathbb{N}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BN%7D "\mathbb{N}"))
are useful for describing the dimensions of a [feature
space](https://stats.stackexchange.com/questions/46425/what-is-feature-space).
For example, the Cartesian plane is an example of an
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2")
feature space where
![\\mathbb{N} = 2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BN%7D%20%3D%202 "\mathbb{N} = 2").

# Real numbers

Real numbers are useful for describing the domain of a function, which
comprises all possible values of
![x](https://latex.codecogs.com/svg.format?x "x") from
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)"). For
example, when
![f(x) = \\sqrt{3-x}](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%20%5Csqrt%7B3-x%7D "f(x) = \sqrt{3-x}"),
the domain of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
![D: \\; (-\\infty, 3\]](https://latex.codecogs.com/svg.format?D%3A%20%5C%3B%20%28-%5Cinfty%2C%203%5D "D: \; (-\infty, 3]")
or
![D: \\; \\{x\| \\; x\\leq 3\\}](https://latex.codecogs.com/svg.format?D%3A%20%5C%3B%20%5C%7Bx%7C%20%5C%3B%20x%5Cleq%203%5C%7D "D: \; \{x| \; x\leq 3\}").

``` r
# Plot the domain of f(x) = sqrt(3-x) ------------------------------------------
set.seed(111)

ggplot(data.frame(x = runif(1000, -3, 3)), aes(x)) +
  geom_function(fun = ~ sqrt(3-(.x))) +
  geom_vline(xintercept = 3, colour = "firebrick", linetype = "dotted") + 
  xlim(-4, 4) + 
  ylim(-2, 4) + 
  labs(title = "f(x) = sqrt(3-x)") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 2.2, y = 3.6, label = "D: (-infinity, 3]")
```

<img src="numbers-introduction_files/figure-gfm/unnamed-chunk-3-1.png" width="70%" style="display: block; margin: auto;" />

# Complex numbers

Complex numbers
(![a+bi](https://latex.codecogs.com/svg.format?a%2Bbi "a+bi")) are
represented by two components which cannot be further simplified:  
+ The term ![a](https://latex.codecogs.com/svg.format?a "a") represents
a real number.  
+ The term ![bi](https://latex.codecogs.com/svg.format?bi "bi")
represents the product of a real number and an imaginary number, where
![i^2=-1](https://latex.codecogs.com/svg.format?i%5E2%3D-1 "i^2=-1").

Because the terms ![a](https://latex.codecogs.com/svg.format?a "a") and
![bi](https://latex.codecogs.com/svg.format?bi "bi") occupy completely
different number plans (a real plane versus an imaginary plane), we can
think of the combination of
![a+bi](https://latex.codecogs.com/svg.format?a%2Bbi "a+bi") as the sum
of two vectors in 2D space.

Our 2D space is different to the Cartesian plane as the basis for a
complex number
![\\mathbb{C}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BC%7D "\mathbb{C}")
is
![\\{(1, 0), (0, i)\\}](https://latex.codecogs.com/svg.format?%5C%7B%281%2C%200%29%2C%20%280%2C%20i%29%5C%7D "\{(1, 0), (0, i)\}").
However, the same principles of vector addition apply.

Complex numbers therefore allow us to think about the additive and
multiplicative properties of vectors in
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2").

<img src="../figures/numbers-complex.svg" width="90%" style="display: block; margin: auto;" />

# Resources

-   A great
    [Wikipedia](https://en.wikipedia.org/wiki/Number#Main_classification)
    explanation of the number system.  
-   Introduction to number systems and binary numbers from [Khan
    Academy](https://www.youtube.com/watch?v=ku4KOFQ-bB4).  
-   Introduction to rational and irrational numbers from [Khan
    Academy](https://www.youtube.com/watch?v=cLP7INqs3JM).  
-   Numbers classification from
    [Nerdstudy](https://www.youtube.com/watch?v=vbPUS-0Wbv4).
