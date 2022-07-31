Introduction to numbers
================
Erika Duan
2022-07-31

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
i.e. ![n=\\tfrac{n}{1}](https://latex.codecogs.com/svg.format?n%3D%5Ctfrac%7Bn%7D%7B1%7D "n=\tfrac{n}{1}").
All rational numbers are complex numbers
i.e. ![\\tfrac{n}{1}=\\tfrac{n+1}{1}+i^2](https://latex.codecogs.com/svg.format?%5Ctfrac%7Bn%7D%7B1%7D%3D%5Ctfrac%7Bn%2B1%7D%7B1%7D%2Bi%5E2 "\tfrac{n}{1}=\tfrac{n+1}{1}+i^2").

<img src="../figures/numbers-categories.svg" width="90%" style="display: block; margin: auto;" />

**Question:** Can you think of different ways to classify the number 2
compared to the number
![\\tfrac{5}{2}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B5%7D%7B2%7D "\tfrac{5}{2}")?

# Natural numbers

Natural numbers
(![\\mathbb{N}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BN%7D "\mathbb{N}"))
are useful for describing the dimensions of a [feature
space](https://stats.stackexchange.com/questions/46425/what-is-feature-space).
For example, the Cartesian plane is an example of an
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2")
feature space where
![\\mathbb{N}=2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BN%7D%3D2 "\mathbb{N}=2").

# Real numbers

Real numbers are used to provide geometric intuition for how we envision
the vector space.

| Notation                                                                                                                                                                           | Dimension                               | Position in vector space         |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------|:---------------------------------|
| ![\\mathbb{R}^0](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E0 "\mathbb{R}^0") or 1                                                                                   | a single point                          | a fixed number                   |
| ![\\mathbb{R}^1](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E1 "\mathbb{R}^1") or ![\\mathbb{R}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D "\mathbb{R}") | number line                             | a single coordinate along a line |
| ![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2")                                                                                        | Euclidean 2D plane i.e. Cartesian plane | 2 coordinates                    |
| ![\\mathbb{R}^3](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E3 "\mathbb{R}^3")                                                                                        | Euclidean 3D space                      | 3 coordinates                    |

Real numbers can also be useful for describing the domain or range of a
function ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)").
The domain (D) represents all possible values that
![x](https://latex.codecogs.com/svg.format?x "x") can take and the range
(R) represents all possible values that
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") or
![y](https://latex.codecogs.com/svg.format?y "y") can take.

When
![f(x)=3x^2](https://latex.codecogs.com/svg.format?f%28x%29%3D3x%5E2 "f(x)=3x^2"):  
+ The domain of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
![D:\\,(-\\infty,\\infty)](https://latex.codecogs.com/svg.format?D%3A%5C%2C%28-%5Cinfty%2C%5Cinfty%29 "D:\,(-\infty,\infty)").  
+ This can also be represented as
![D:\\,\\{x\\in\\mathbb{R}\\}](https://latex.codecogs.com/svg.format?D%3A%5C%2C%5C%7Bx%5Cin%5Cmathbb%7BR%7D%5C%7D "D:\,\{x\in\mathbb{R}\}").  
+ The range of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
![R:\\,\[0,\\infty)](https://latex.codecogs.com/svg.format?R%3A%5C%2C%5B0%2C%5Cinfty%29 "R:\,[0,\infty)").  
+ This can also be represented as
![R:\\,\\{y\\in\\mathbb{R}\\,\|\\,y\\geq0\\}](https://latex.codecogs.com/svg.format?R%3A%5C%2C%5C%7By%5Cin%5Cmathbb%7BR%7D%5C%2C%7C%5C%2Cy%5Cgeq0%5C%7D "R:\,\{y\in\mathbb{R}\,|\,y\geq0\}").

``` r
# Plot the domain of f(x) = 3x^2 in R ------------------------------------------
set.seed(111)

ggplot(data.frame(x = runif(1000, -3, 3)), aes(x)) +
  geom_function(fun = ~ 3*(.x)^2) +
  xlim(-2, 2) + 
  ylim(-1, 8) + 
  labs(title = "f(x) = 3x^2") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) 
```

<img src="numbers-introduction_files/figure-gfm/unnamed-chunk-3-1.png" width="60%" style="display: block; margin: auto;" />

When
![f(x)=\\sqrt{3-x}](https://latex.codecogs.com/svg.format?f%28x%29%3D%5Csqrt%7B3-x%7D "f(x)=\sqrt{3-x}"):  
+ The domain of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
![D:\\;(-\\infty,3\]](https://latex.codecogs.com/svg.format?D%3A%5C%3B%28-%5Cinfty%2C3%5D "D:\;(-\infty,3]").  
+ This can also be represented as
![D:\\;\\{x\\in\\mathbb{R}\\,\|\\,x\\leq3\\}](https://latex.codecogs.com/svg.format?D%3A%5C%3B%5C%7Bx%5Cin%5Cmathbb%7BR%7D%5C%2C%7C%5C%2Cx%5Cleq3%5C%7D "D:\;\{x\in\mathbb{R}\,|\,x\leq3\}").  
+ The range of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
![R:\\; \[0,\\infty)](https://latex.codecogs.com/svg.format?R%3A%5C%3B%20%5B0%2C%5Cinfty%29 "R:\; [0,\infty)").  
+ This can also be represented as
![R:\\,\\{y\\in\\mathbb{R}\\,\|\\,y\\geq0\\}](https://latex.codecogs.com/svg.format?R%3A%5C%2C%5C%7By%5Cin%5Cmathbb%7BR%7D%5C%2C%7C%5C%2Cy%5Cgeq0%5C%7D "R:\,\{y\in\mathbb{R}\,|\,y\geq0\}").

``` r
# Plot the domain of f(x) = sqrt(3-x) in R -------------------------------------
set.seed(111)

ggplot(data.frame(x = runif(1000, -3, 3)), aes(x)) +
  geom_function(fun = ~ sqrt(3-(.x))) +
  geom_vline(xintercept = 3, colour = "firebrick", linetype = "dotted") + 
  xlim(-4, 4) + 
  ylim(-1, 3) + 
  labs(title = "f(x) = sqrt(3-x)") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 2.2, y = 3.6, label = "D: (-infinity, 3]")
```

<img src="numbers-introduction_files/figure-gfm/unnamed-chunk-4-1.png" width="60%" style="display: block; margin: auto;" />

# Complex numbers

Complex numbers
(![a+bi](https://latex.codecogs.com/svg.format?a%2Bbi "a+bi") or
![\\mathbb{C}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BC%7D "\mathbb{C}"))
are represented by two components which cannot be further simplified:  
+ The term ![a](https://latex.codecogs.com/svg.format?a "a") represents
a real number.  
+ The term ![bi](https://latex.codecogs.com/svg.format?bi "bi")
represents the product of a real number and an imaginary number, where
![i^2=-1](https://latex.codecogs.com/svg.format?i%5E2%3D-1 "i^2=-1").

Because the terms ![a](https://latex.codecogs.com/svg.format?a "a") and
![bi](https://latex.codecogs.com/svg.format?bi "bi") occupy completely
different number planes (a real plane versus an imaginary plane), we can
think of ![a+bi](https://latex.codecogs.com/svg.format?a%2Bbi "a+bi") as
the sum of two special vectors in a special 2D space.

The vector space for a complex number is different to the 2D Cartesian
plane as its basis is
![\\{(1, 0), (0, i)\\}](https://latex.codecogs.com/svg.format?%5C%7B%281%2C%200%29%2C%20%280%2C%20i%29%5C%7D "\{(1, 0), (0, i)\}").
However, the same principles of vector addition apply.

Complex numbers therefore allow us to think about the additive and
scalar multiplicative properties of vectors in
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2").
For example, the multiplication of a complex number by a scalar
![k](https://latex.codecogs.com/svg.format?k "k") also scales its
position in space by ![k](https://latex.codecogs.com/svg.format?k "k")
times.

<img src="../figures/numbers-complex.svg" width="90%" style="display: block; margin: auto;" />

Note that complex number multiplication does not behave like vector
multiplication as
![i^2 = -1](https://latex.codecogs.com/svg.format?i%5E2%20%3D%20-1 "i^2 = -1")
implies that the basis vectors
![\\{(1, 0), (0, i)\\}](https://latex.codecogs.com/svg.format?%5C%7B%281%2C%200%29%2C%20%280%2C%20i%29%5C%7D "\{(1, 0), (0, i)\}")
are not orthogonal with respect to each other.

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
