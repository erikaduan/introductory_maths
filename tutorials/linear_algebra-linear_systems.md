Introduction to linear systems
================
Erika Duan
2022-08-28

-   [A single linear equation](#a-single-linear-equation)
-   [A system of linear equations](#a-system-of-linear-equations)
-   [Equivalent linear systems](#equivalent-linear-systems)
-   [Equivalence relations](#equivalence-relations)
-   [Augmented matrices and matrix echelon
    forms](#augmented-matrices-and-matrix-echelon-forms)
-   [Row reduction algorithmn](#row-reduction-algorithmn)
-   [Homogenous linear systems and infinite
    solutions](#homogenous-linear-systems-and-infinite-solutions)
-   [Homogenous linear systems and linear
    independence](#homogenous-linear-systems-and-linear-independence)
-   [Resources](#resources)

# A single linear equation

There is a fundamental relationship between the linear equation
![ax + by = c](https://latex.codecogs.com/svg.format?ax%20%2B%20by%20%3D%20c "ax + by = c"),
which contains two unknown variables, and lines. A line represents the
space occupied by all possible solutions to the linear equation
![ax + by = c](https://latex.codecogs.com/svg.format?ax%20%2B%20by%20%3D%20c "ax + by = c").

This means that linear equations can be described using geometric as
well as mathematical intuition, for equations with
![\\leq](https://latex.codecogs.com/svg.format?%5Cleq "\leq") 3 unknown
variables i.e. for scenarios in 1D to 3D space. For example, the
solution for
![3x - 2y = 2](https://latex.codecogs.com/svg.format?3x%20-%202y%20%3D%202 "3x - 2y = 2")
can be rearranged into the form
![y = \\tfrac{3}{2}x - 1](https://latex.codecogs.com/svg.format?y%20%3D%20%5Ctfrac%7B3%7D%7B2%7Dx%20-%201 "y = \tfrac{3}{2}x - 1"),
which is a line with slope
![\\tfrac{3}{2}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B3%7D%7B2%7D "\tfrac{3}{2}")
and y-intercept ![-1](https://latex.codecogs.com/svg.format?-1 "-1").

A single linear equation can be inconsistent (where no solution exists)
or consistent (where a single solution or infinite solutions exist). For
any consistent linear equation, the solution set also has a geometric
form. For example, the solutions to
![3x-2y=2](https://latex.codecogs.com/svg.format?3x-2y%3D2 "3x-2y=2")
map to a single line within a 2D plane. Any point on this line is an
individual solution and the line of infinite solutions is a copy of
![\\mathbb{R}^1](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E1 "\mathbb{R}^1")
inside
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2").

The geometric intuition that solutions exist as a copy of
![\\mathbb{R}^{n-1}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E%7Bn-1%7D "\mathbb{R}^{n-1}")
inside
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
is true for all linear equations. For example, the solution to the
linear system
![3x=2](https://latex.codecogs.com/svg.format?3x%3D2 "3x=2") is a copy
of
![\\mathbb{R}^0](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E0 "\mathbb{R}^0")
inside
![\\mathbb{R}^1](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E1 "\mathbb{R}^1")
and maps to a single point along a 1D line.

<img src="../figures/linear_systems-consistent_solutions.svg" width="80%" style="display: block; margin: auto;" />

**Note:** In linear algebra, it is preferable to write linear equations
in the form
![ax_1 + bx_2 = c](https://latex.codecogs.com/svg.format?ax_1%20%2B%20bx_2%20%3D%20c "ax_1 + bx_2 = c")
instead of
![ax + by = c](https://latex.codecogs.com/svg.format?ax%20%2B%20by%20%3D%20c "ax + by = c"),
as we often deal with dimensions greater than 3 (commonly represented by
the x, y, z coordinates).

**Note:** Linear equations with the form
![c_1x_1 + c_2x_2 = 0](https://latex.codecogs.com/svg.format?c_1x_1%20%2B%20c_2x_2%20%3D%200 "c_1x_1 + c_2x_2 = 0")
rather than
![c_1x_1 + c_2x_2 = k](https://latex.codecogs.com/svg.format?c_1x_1%20%2B%20c_2x_2%20%3D%20k "c_1x_1 + c_2x_2 = k")
have the distinct property that they also pass the point of origin
i.e. they also contain a trivial solution
![c_1 = c_2 = 0](https://latex.codecogs.com/svg.format?c_1%20%3D%20c_2%20%3D%200 "c_1 = c_2 = 0").

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot 3x - 2y = 2 -----------------------------------------------------------
x <- seq(-4, 4, by = 1)
y <- 3/2*x - 1

p1 <- ggplot(data.frame(x, y), aes(x, y)) +
  geom_hline(yintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_line() + 
  coord_cartesian(xlim = c(-4, 4), 
                  ylim = c(-4, 4)) +
  labs(title = "3x - 2y = 2") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot 3x - 2y = 0 -----------------------------------------------------------
x <- seq(-4, 4, by = 1)
y <- 3/2*x

p2 <- ggplot(data.frame(x, y), aes(x, y)) +
  geom_hline(yintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_line() + 
  coord_cartesian(xlim = c(-4, 4), 
                  ylim = c(-4, 4)) +
  labs(title = "3x - 2y = 0") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot ggplot figures side by side --------------------------------------------- 
p1 + p2
```

<img src="linear_algebra-linear_systems_files/figure-gfm/unnamed-chunk-3-1.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

# A system of linear equations

In linear algebra, we solve for a solution set
![S = \\{s_1, s_2, \\cdots\\, s_n\\}](https://latex.codecogs.com/svg.format?S%20%3D%20%5C%7Bs_1%2C%20s_2%2C%20%5Ccdots%5C%2C%20s_n%5C%7D "S = \{s_1, s_2, \cdots\, s_n\}")
to unknown variables
![\\{x_1, x_2, \\cdots\\, x_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bx_1%2C%20x_2%2C%20%5Ccdots%5C%2C%20x_n%5C%7D "\{x_1, x_2, \cdots\, x_n\}")
given that multiple observations or constraints are described. Each
observation or constraint is incorporated as an additional linear
equation containing different scalars of the same unknown variables. A
set of linear equations that must be simultaneously solved is called a
**linear system**.

In statistics, a linear system is used to describe multiple observations
of a phenomenon and ![X](https://latex.codecogs.com/svg.format?X "X")
and
![\\vec y](https://latex.codecogs.com/svg.format?%5Cvec%20y "\vec y")
are treated as random variables. Within this linear system, given
observed values of ![X](https://latex.codecogs.com/svg.format?X "X") and
![\\vec y](https://latex.codecogs.com/svg.format?%5Cvec%20y "\vec y"),
we solve for
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b")
where
![X \\vec b + \\vec \\epsilon = \\vec y](https://latex.codecogs.com/svg.format?X%20%5Cvec%20b%20%2B%20%5Cvec%20%5Cepsilon%20%3D%20%5Cvec%20y "X \vec b + \vec \epsilon = \vec y").
![X](https://latex.codecogs.com/svg.format?X "X") and
![\\vec y](https://latex.codecogs.com/svg.format?%5Cvec%20y "\vec y")
are random variables because we attribute a component of randomness to
observed ![X](https://latex.codecogs.com/svg.format?X "X") and
![\\vec y](https://latex.codecogs.com/svg.format?%5Cvec%20y "\vec y")
values. We are therefore never interested in modelling a single solution
to our linear system i.e. to generate a perfect curve which fits through
all points of ![X](https://latex.codecogs.com/svg.format?X "X") and
![\\vec y](https://latex.codecogs.com/svg.format?%5Cvec%20y "\vec y").
In statistics, the latter task is known as model overfitting.

In contrast, in mathematical modelling, a linear system contains
multiple fixed observations and we solve for
![(x_1, x_2, ..., x_n)](https://latex.codecogs.com/svg.format?%28x_1%2C%20x_2%2C%20...%2C%20x_n%29 "(x_1, x_2, ..., x_n)")
or ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
where
![\\vec a_1x_1 + \\vec a_2x_2 + \\cdots + \\vec a_nx_n = \\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20a_1x_1%20%2B%20%5Cvec%20a_2x_2%20%2B%20%5Ccdots%20%2B%20%5Cvec%20a_nx_n%20%3D%20%5Cvec%20b "\vec a_1x_1 + \vec a_2x_2 + \cdots + \vec a_nx_n = \vec b")
or
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
and
![a\_{i,j}, b \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?a_%7Bi%2Cj%7D%2C%20b%20%5Cin%20%5Cmathbb%7BR%7D "a_{i,j}, b \in \mathbb{R}").
The linear system is true when a set of values
![(c_1, c_2, ..., c_n)](https://latex.codecogs.com/svg.format?%28c_1%2C%20c_2%2C%20...%2C%20c_n%29 "(c_1, c_2, ..., c_n)")
substitutes for
![(x_1, x_2, ..., x_n)](https://latex.codecogs.com/svg.format?%28x_1%2C%20x_2%2C%20...%2C%20x_n%29 "(x_1, x_2, ..., x_n)").

<img src="../figures/linear_systems-linear_forms.svg" width="80%" style="display: block; margin: auto;" />

For any linear system, we have three possible scenarios:

-   The linear system is inconsistent (at least one equation is
    inconsistent with respect to other equations) and we have an
    **empty** set of solutions
    i.e. ![S = \\{\\}](https://latex.codecogs.com/svg.format?S%20%3D%20%5C%7B%5C%7D "S = \{\}").  
-   The linear system is consistent and has only one solution set
    i.e. ![S = \\{(c_1, c_2, \\cdots, c_n)\\}](https://latex.codecogs.com/svg.format?S%20%3D%20%5C%7B%28c_1%2C%20c_2%2C%20%5Ccdots%2C%20c_n%29%5C%7D "S = \{(c_1, c_2, \cdots, c_n)\}")
    where
    ![c_1, c_2, \\cdots, c_n](https://latex.codecogs.com/svg.format?c_1%2C%20c_2%2C%20%5Ccdots%2C%20c_n "c_1, c_2, \cdots, c_n")
    are fixed scalars.  
-   The linear system is consistent and has infinite solutions (or the
    solution set has infinitely many elements)
    i.e. ![S = \\{(c_1, c_2, x_3 - 2) \| x_3 \\in \\mathbb{R}\\}](https://latex.codecogs.com/svg.format?S%20%3D%20%5C%7B%28c_1%2C%20c_2%2C%20x_3%20-%202%29%20%7C%20x_3%20%5Cin%20%5Cmathbb%7BR%7D%5C%7D "S = \{(c_1, c_2, x_3 - 2) | x_3 \in \mathbb{R}\}")
    where
    ![c_1, c_2](https://latex.codecogs.com/svg.format?c_1%2C%20c_2 "c_1, c_2")
    are fixed scalars and
    ![x_3](https://latex.codecogs.com/svg.format?x_3 "x_3") represents
    any real number.

**Note:** Infinite solutions always occur when you have less
observations than variables i.e. the
![n\<p](https://latex.codecogs.com/svg.format?n%3Cp "n<p")
[problem](https://stats.stackexchange.com/questions/385711/what-is-the-problem-with-p-n).
In a linear system, ![p](https://latex.codecogs.com/svg.format?p "p")
represents the number of observations and
![n](https://latex.codecogs.com/svg.format?n "n") represents the number
of unknown variables present.

Using linear systems with two unknown variables as an example, we can
see that solutions to linear systems have two properties:  
+ Solutions can be solved through mathematical simplification.  
+ Solutions have a geometric intuition. In 2D, solutions can be
represented as two lines which never intersect (no solution), two lines
which only intersect once (single solution), or two lines superimposed
on each other (infinite solutions).

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot inconsistent linear system in R -----------------------------------------
p1 <- data.frame(x <- seq(-10, 10, by = 1), 
                 y1 <- (-2*x - 5) / 3,
                 y2 <- (-4*x - 2) / 6) %>% 
  ggplot(aes(x)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(y = y1)) + 
  geom_line(aes(y = y2)) + 
  coord_cartesian(xlim = c(-4, 4), 
                  ylim = c(-4, 4)) +
  labs(title = "No solution") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot consistent linear system with single solution in R ----------------------
p2 <- data.frame(x1 <- 8/4,
                 y1 <- seq(-10, 10, by = 1),
                 x2 <- seq(-10, 10, by = 1), 
                 y2 <- 2/3) %>% 
  ggplot(aes(x2, y1)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(x = x1)) + 
  geom_line(aes(y = y2)) + 
  coord_cartesian(xlim = c(-4, 4), 
                  ylim = c(-4, 4)) +
  labs(title = "Single solution") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))  

# Plot consistent linear system with infinite solutions in R -------------------
p3 <- data.frame(x <- seq(-10, 10, by = 1),
                 y1 <- (-2*x + 5) / 3,
                 y2 <- (-4*x + 10) / 6) %>% 
  ggplot(aes(x)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(y = y1), colour = "steelblue", lwd=2) + 
  geom_line(aes(y = y2)) + 
  labs(title = "Infinite solutions") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))   

# Plot ggplot figures side by side --------------------------------------------- 
p1 + p2 + p3
```

<img src="linear_algebra-linear_systems_files/figure-gfm/unnamed-chunk-5-1.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

# Equivalent linear systems

Two linear systems are row equivalent if they have the same n-tuple
solution set i.e. if
![\\{s_1, \\cdots, s_n\\} = \\{t_1, \\cdots, t_n \\}](https://latex.codecogs.com/svg.format?%5C%7Bs_1%2C%20%5Ccdots%2C%20s_n%5C%7D%20%3D%20%5C%7Bt_1%2C%20%5Ccdots%2C%20t_n%20%5C%7D "\{s_1, \cdots, s_n\} = \{t_1, \cdots, t_n \}").
Row equivalence implies that we can convert one linear system into an
equivalent linear system to find the simplest linear system to solve
for.

The process of converting a linear system into an equivalent simpler
linear system can be considered as an algorithm. To construct this
algorithm, we need to identify the operations which maintain equivalency
between two linear systems i.e. prove that all elementary equation
operations (EEOs) maintain equivalency between linear systems A and B.

<img src="../figures/linear_systems-equivalence.svg" width="80%" style="display: block; margin: auto;" />

The three elementary equation operations (EEOs) are:  
+ **Replacement** - replace an equation by the sum of itself and the
multiple of another equation.  
+ **Interchange** - interchange the listed order of two equations.  
+ **Scaling** - replace an equation with a multiple of itself.

If we know that there is a finite and reversible sequence of elementary
equation operations to transform A into B, then the best algorithm will
select the minimal sequence of EEOs to reach B, where B is the simplest
equivalent linear system to solve. This is how the row reduction (or
Gauss Jordan elimination) algorithm works.

# Equivalence relations

Let A be a set. A relation on A is any subset of
![A \\times A](https://latex.codecogs.com/svg.format?A%20%5Ctimes%20A "A \times A"),
or any set of ordered pairs
![(a,b)](https://latex.codecogs.com/svg.format?%28a%2Cb%29 "(a,b)")
where
![a,b \\in A](https://latex.codecogs.com/svg.format?a%2Cb%20%5Cin%20A "a,b \in A"),
which satisfies the conditions of a statement or function being applied
on ![a](https://latex.codecogs.com/svg.format?a "a") to
![b](https://latex.codecogs.com/svg.format?b "b").

<img src="../figures/linear_systems-relations.svg" width="80%" style="display: block; margin: auto;" />

**Equivalence relations** refers to relations that are:

-   Reflexive - for any
    ![a \\in A](https://latex.codecogs.com/svg.format?a%20%5Cin%20A "a \in A"),
    ![a](https://latex.codecogs.com/svg.format?a "a") applies to
    ![a](https://latex.codecogs.com/svg.format?a "a").  
-   Symmetric - for any
    ![a, b \\in A](https://latex.codecogs.com/svg.format?a%2C%20b%20%5Cin%20A "a, b \in A"),
    if ![a](https://latex.codecogs.com/svg.format?a "a") applies to
    ![b](https://latex.codecogs.com/svg.format?b "b"), then
    ![b](https://latex.codecogs.com/svg.format?b "b") applies to
    ![a](https://latex.codecogs.com/svg.format?a "a").  
-   Transitive - for any
    ![a, b, c \\in A](https://latex.codecogs.com/svg.format?a%2C%20b%2C%20c%20%5Cin%20A "a, b, c \in A"),
    if ![a](https://latex.codecogs.com/svg.format?a "a") applies to
    ![b](https://latex.codecogs.com/svg.format?b "b") and
    ![b](https://latex.codecogs.com/svg.format?b "b") applies to
    ![c](https://latex.codecogs.com/svg.format?c "c"), then
    ![a](https://latex.codecogs.com/svg.format?a "a") applies to
    ![c](https://latex.codecogs.com/svg.format?c "c").

For example, suppose that matrix A is equivalent to matrix B and C.
There exists a finite sequence of EROs which transforms A into B and A
into C. Because EROs are reversible, the finite sequence of EROs which
transforms B into A and then A into C yields a finite sequence of EROs
which transforms B into C. Therefore row equivalence is also transitive.

Row equivalence is therefore an equivalence relation on the set of all
linear systems in the same set of variables
i.e. ![\\{x_1, x_2, \\cdots, x_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bx_1%2C%20x_2%2C%20%5Ccdots%2C%20x_n%5C%7D "\{x_1, x_2, \cdots, x_n\}").
This also means that row equivalence is also an equivalence relation on
the set of all
![m \\times n](https://latex.codecogs.com/svg.format?m%20%5Ctimes%20n "m \times n")
matrices.

# Augmented matrices and matrix echelon forms

A linear system can be represented in matrix form, through an augmented
matrix for linear systems with form
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
and through a coefficient matrix for linear systems with form
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0").

Each matrix can exist in multiple echelon forms and in one unique
reduced echelon form.

The matrix equivalent of elementary equation operations (EEOs) are
elementary row operations (EROs).

<img src="../figures/linear_systems-echelon_forms.svg" width="80%" style="display: block; margin: auto;" />

A matrix is in an **echelon form** if:  
+ All non-zero rows are above rows of all zeros.  
+ Each leading entry (or pivot column of a row) is located to the left
of the leading entry of the row below it. Each leading entry in the
echelon form represents a fixed or **basic variable** in the linear
system.  
+ All entries in a column below a leading entry are zeros.

A matrix is in its **reduced echelon form** if additionally:  
+ All leading entries are 1.  
+ Each leading 1 is the only non-zero entry in its column.

When a matrix is in an echelon form, we can solve the linear system by
either:  
1. Directly using back substitution to simplify the list of equations
and then solve for each variable. Solutions should be presented in the
form of constants and free variables only.  
2. Further reducing the matrix to its reduced echelon form, where the
solution for each variable is obvious
i.e. ![x_1 = c_1, x_2 = c_2, \\cdots, x_n = c_n](https://latex.codecogs.com/svg.format?x_1%20%3D%20c_1%2C%20x_2%20%3D%20c_2%2C%20%5Ccdots%2C%20x_n%20%3D%20c_n "x_1 = c_1, x_2 = c_2, \cdots, x_n = c_n").

<img src="../figures/linear_systems-echelon_solutions.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Linear systems with infinite solutions are easily identified
in matrix echelon form by the presence of at least one row lacking a
pivot column. Free variables correspond to variables lacking a
corresponding pivot column in the matrix echelon form.

# Row reduction algorithmn

In the row reduction algorithm (also know as the Gauss Jordan
Elimination algorithm), we aim to:

1.  Find the matrix **echelon form** by applying replacement elementary
    row operations
    i.e. ![R_j = R_i](https://latex.codecogs.com/svg.format?R_j%20%3D%20R_i "R_j = R_i")
    or
    ![R_j = kR_j](https://latex.codecogs.com/svg.format?R_j%20%3D%20kR_j "R_j = kR_j")
    or
    ![R_j = R_j + kR_i](https://latex.codecogs.com/svg.format?R_j%20%3D%20R_j%20%2B%20kR_i "R_j = R_j + kR_i")
    on all columns below the leading edge in a row. Repeat this step for
    each leading edge of each row.  
2.  Find the matrix **reduced echelon form** by identifying the right
    most leading edge and using a scaling elementary row operation to
    convert it into 1. Apply replacement elementary row operations
    i.e. ![R_i = R_i + kR_j](https://latex.codecogs.com/svg.format?R_i%20%3D%20R_i%20%2B%20kR_j "R_i = R_i + kR_j")
    on all columns above the leading 1. Repeat this step for each
    leading edge of each row.

<details>
<summary>
Python code
</summary>
<p>

``` python
# To be completed --------------------------------------------------------------
import numpy as np
A=np.array([[1,-1,1,3],[2,1,8,18],[4,2,-3,-2]])

def RowSwap(A,k,l):
# =============================================================================
#     A is a NumPy array.  RowSwap will return duplicate array with rows
#     k and l swapped.
# =============================================================================
    m = A.shape[0]  # m is number of rows in A
    n = A.shape[1]  # n is number of columns in A
    
    B = np.copy(A).astype('float64')
        
    for j in range(n):
        temp = B[k][j]
        B[k][j] = B[l][j]
        B[l][j] = temp
        
    return B

def RowScale(A,k,scale):
# =============================================================================
#     A is a NumPy array.  RowScale will return duplicate array with the
#     entries of row k multiplied by scale.
# =============================================================================
    m = A.shape[0]  # m is number of rows in A
    n = A.shape[1]  # n is number of columns in A
    
    B = np.copy(A).astype('float64')

    for j in range(n):
        B[k][j] *= scale
        
    return B

def RowAdd(A,k,l,scale):
# =============================================================================
#     A is a numpy array.  RowAdd will return duplicate array with row
#     l modifed.  The new values will be the old values of row l added to 
#     the values of row k, multiplied by scale.
# =============================================================================
    m = A.shape[0]  # m is number of rows in A
    n = A.shape[1]  # n is number of columns in A
    
    B = np.copy(A).astype('float64')
        
    for j in range(n):
        B[l][j] += B[k][j]*scale
        
    return B
    
    
B1 = RowSwap(A,0,2)
B2 = RowScale(A,2,0.5)
B3 = RowAdd(A,0,1,2)

## Add -2 times row 0 to row 1
A1 = RowAdd(A,0,1,-2)
print(A1,'\n')

## Add -4 times row 0 to row 2
A2 = RowAdd(A1,0,2,-4)
print(A2,'\n')

## Add -2 times row 1 to row 2
A3 = RowAdd(A2,1,2,-2)
print(A3,'\n')

## Multiply row 1 by 1/3
A4 = RowScale(A3,1,1.0/3)
print(A4,'\n')

## Multiply row 2 by 1/19
A5 = RowScale(A4,2,1.0/-19.)
print(A5)
```

``` python
# To be completed --------------------------------------------------------------
n = int(input('Enter number of unknowns: '))
a = np.zeros((n,n+1))
x = np.zeros(n)
print('Enter Augmented Matrix Coefficients:')
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input( 'a['+str(i)+']['+ str(j)+']='))
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
         
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
         
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
 
x[n-1] = a[n-1][n]/a[n-1][n-1]
 
for i in range(n-2,-1,-1):
    x[i] = a[i][n]
     
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
     
    x[i] = x[i]/a[i][i]
 
print('\nThe solution is: ')
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = '\t')
```

</p>
</details>
<p>

**Note:** Each matrix is row equivalent to exactly one matrix in reduced
echelon form. This will be proved in the [next
lecture](https://github.com/erikaduan/introductory_maths/blob/master/tutorials/linear_algebra-vectors.md)
on vectors, where matrix representation of linearly independent versus
dependent vectors is discussed.

# Homogenous linear systems and infinite solutions

It is easier to work with homogeneous linear systems, with the form
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0"),
as these systems can only have either a single trivial solution
![\\{x_1, x_2 \\cdots, x_n\\} = \\{0, 0, \\cdots, 0\\}](https://latex.codecogs.com/svg.format?%5C%7Bx_1%2C%20x_2%20%5Ccdots%2C%20x_n%5C%7D%20%3D%20%5C%7B0%2C%200%2C%20%5Ccdots%2C%200%5C%7D "\{x_1, x_2 \cdots, x_n\} = \{0, 0, \cdots, 0\}")
or infinite solutions
i.e. ![\\{x_1, x_2 \\cdots, x_n\\} = \\{2x_2, x_2, \\cdots, -x_2\\}](https://latex.codecogs.com/svg.format?%5C%7Bx_1%2C%20x_2%20%5Ccdots%2C%20x_n%5C%7D%20%3D%20%5C%7B2x_2%2C%20x_2%2C%20%5Ccdots%2C%20-x_2%5C%7D "\{x_1, x_2 \cdots, x_n\} = \{2x_2, x_2, \cdots, -x_2\}").
This observation is obvious when you consider that the reduced echelon
form of A can only equate to
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0") or
a vector containing free variables (as infinite solutions are defined
with respect to all free variables only).

We can therefore re-write infinite solutions to any linear system
![A\\vec x=\\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%20b "A\vec x=\vec b")
as the addition of a positional vector
![\\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20p "\vec p") to
the infinite solution set of a homogeneous linear system
![A\\vec x=\\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%200 "A\vec x=\vec 0").

If
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
has infinite solutions:  
+ One solution is
![\\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20p "\vec p")
i.e. a single vector of real numbers or a point in
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m").  
+ The remaining solutions exist in the vector span of
![\\{\\vec v_1, ... , \\vec v_h\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20...%20%2C%20%5Cvec%20v_h%5C%7D "\{\vec v_1, ... , \vec v_h\}")
where
![A\\vec v_h = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20v_h%20%3D%20%5Cvec%200 "A\vec v_h = \vec 0")
and
![\\vec x = \\vec p + \\vec v_h](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%3D%20%5Cvec%20p%20%2B%20%5Cvec%20v_h "\vec x = \vec p + \vec v_h").  
+ The solution set of
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
can therefore also be presented in the parametric vector form
![\\{\\vec p + c_1\\vec v_1 + ... + c_h\\vec v\_{h}\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20p%20%2B%20c_1%5Cvec%20v_1%20%2B%20...%20%2B%20c_h%5Cvec%20v_%7Bh%7D%5C%7D "\{\vec p + c_1\vec v_1 + ... + c_h\vec v_{h}\}")
where
![c_1, \\cdots, c_h](https://latex.codecogs.com/svg.format?c_1%2C%20%5Ccdots%2C%20c_h "c_1, \cdots, c_h")
represents free variables in
![\\mathbb{R}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D "\mathbb{R}").

<img src="../figures/linear_systems-infinite_solutions.svg" width="80%" style="display: block; margin: auto;" />

Solving a linear system can therefore also be viewed as either finding a
parametric description of the solution set or determining that the
system is inconsistent.

<img src="../figures/linear_systems-parametric_solutions.svg" width="80%" style="display: block; margin: auto;" />

When an infinite solution is expressed as a parametric vector form, we
can form some geometric intuition about the space that it occupies. For
an infinite solution, the solution is a copy of
![\\mathbb{R}^h](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Eh "\mathbb{R}^h")
in
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
that intersects with the point represented by
![\\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20p "\vec p").

<img src="../figures/linear_systems-parametric_solution_example.svg" width="80%" style="display: block; margin: auto;" />

**Note:** All solutions to a homogeneous linear system will contain the
origin point. This is true for homogeneous linear systems with a single
trivial solution or infinite solutions.

# Homogenous linear systems and linear independence

A homogeneous linear system
![A\\vec x=\\vec0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec0 "A\vec x=\vec0")
is linearly independent if it only has one trivial solution i.e. only
the solution
![x_1 = x_2 = \\cdots = x_n = 0](https://latex.codecogs.com/svg.format?x_1%20%3D%20x_2%20%3D%20%5Ccdots%20%3D%20x_n%20%3D%200 "x_1 = x_2 = \cdots = x_n = 0")
exists. The reduced echelon form of matrix
![A](https://latex.codecogs.com/svg.format?A "A") posits that a
homogeneous linear system with a single trivial solution does not
contain any free variables. Homogeneous linear systems containing free
variables are therefore not linearly independent.

If a homogeneous linear system has infinite solutions, its augmented
matrix form contains at least one free variable and the system is
linearly dependent.

<img src="../figures/linear_systems-linear_dependence_a.svg" width="80%" style="display: block; margin: auto;" />

Linear independence and linear dependence are easier to conceptualise
when we view the coefficient matrix A as a collection of
![n](https://latex.codecogs.com/svg.format?n "n") column vectors
i.e. ![A = \\begin{bmatrix} \\vec a_1 & \\vec a_2 & \\cdots & \\vec a_n \\end{bmatrix}](https://latex.codecogs.com/svg.format?A%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cvec%20a_1%20%26%20%5Cvec%20a_2%20%26%20%5Ccdots%20%26%20%5Cvec%20a_n%20%5Cend%7Bbmatrix%7D "A = \begin{bmatrix} \vec a_1 & \vec a_2 & \cdots & \vec a_n \end{bmatrix}").

The concept of representing linear systems using vectors is covered in
the [next
tutorial](https://github.com/erikaduan/introductory_maths/blob/master/tutorials/linear_algebra-vectors.md)
on vectors.

# Resources

-   [YouTube video
    series](https://www.youtube.com/watch?v=ZKUqtErZCiU&list=PLHXZ9OQGMqxfUl0tcqPNTJsb7R6BqSLo6)
    by Dr Trefor Bazett on linear systems.  
-   [Blog
    post](https://bvanderlei.github.io/jupyter-guide-to-linear-algebra/Gaussian_Elimination.html)
    containing Python code to perform elementary row operations.  
-   [Solution](https://levelup.gitconnected.com/gaussian-elimination-algorithm-in-python-4e90cb3a0fd9)
    for the row reduction algorithm in Python.  
-   [YouTube video](https://www.youtube.com/watch?v=4P1YUKPIc4w) on the
    properties of homogeneous linear systems.  
-   YouTube videos introducing
    [relations](https://www.youtube.com/watch?v=dbihQ6tiRJ0) and
    [equivalence
    relations](https://www.youtube.com/watch?v=ZgcTX16borA).
