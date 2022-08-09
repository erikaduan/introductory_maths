Introduction to linear systems
================
Erika Duan
2022-08-07

-   [A single linear equation](#a-single-linear-equation)
-   [A system of linear equations](#a-system-of-linear-equations)
-   [Equivalent systems](#equivalent-systems)
-   [Augmented matrices and matrix echelon
    forms](#augmented-matrices-and-matrix-echelon-forms)
-   [Row reduction algorithmn](#row-reduction-algorithmn)
-   [Homogenous linear systems](#homogenous-linear-systems)
-   [Linear independence and homogenous linear
    systems](#linear-independence-and-homogenous-linear-systems)
-   [Resources](#resources)

# A single linear equation

There is a fundamental relationship between the equation
![ax+by=c](https://latex.codecogs.com/svg.format?ax%2Bby%3Dc "ax+by=c")
and lines. Lines represent the vector subspace of all solutions found
for the linear equation
![ax+by=c](https://latex.codecogs.com/svg.format?ax%2Bby%3Dc "ax+by=c").

This means that we can describe linear equations with both mathematical
and geometric intuition (depending on the dimensions of the vector
space). For example, the solution for
![3x+\\tfrac{1}{2}y=2](https://latex.codecogs.com/svg.format?3x%2B%5Ctfrac%7B1%7D%7B2%7Dy%3D2 "3x+\tfrac{1}{2}y=2")
or
![3x_1+\\tfrac{1}{2}x_2=2](https://latex.codecogs.com/svg.format?3x_1%2B%5Ctfrac%7B1%7D%7B2%7Dx_2%3D2 "3x_1+\tfrac{1}{2}x_2=2")
is represented by every point in the line below.

Linear equations with the form
![c_1x_1+c_2x_2=0](https://latex.codecogs.com/svg.format?c_1x_1%2Bc_2x_2%3D0 "c_1x_1+c_2x_2=0")
rather than
![c_1x_1+c_2x_2=k](https://latex.codecogs.com/svg.format?c_1x_1%2Bc_2x_2%3Dk "c_1x_1+c_2x_2=k")
have an additional property that they also pass the point of origin.

For a single consistent and non-trivial linear equation, the set of
solutions also has a consistent vector span. For example,
![3x_1 - 2x_2 = 2](https://latex.codecogs.com/svg.format?3x_1%20-%202x_2%20%3D%202 "3x_1 - 2x_2 = 2")
describes a line. Any point on this line is a solution and is a copy of
![\\mathbb{R}^1](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E1 "\mathbb{R}^1")
inside
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2").
This illustrates that infinite solutions can exist for linear equations.
In scenarios with infinite solutions, we may want to provide additional
context to identify an optimal solution out of infinite possible
solutions. This is the utility of linear algebra.

<img src="../figures/linear_systems-consistent_solutions.svg" width="80%" style="display: block; margin: auto;" />

**Note:** In linear algebra, it is preferable to write
![ax_1+bx_2=c](https://latex.codecogs.com/svg.format?ax_1%2Bbx_2%3Dc "ax_1+bx_2=c")
instead of
![ax+by=c](https://latex.codecogs.com/svg.format?ax%2Bby%3Dc "ax+by=c")
as we usually deal with dimensions greater than 3 (alternatively
designated by the x, y, z coordinates).

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot 3x + 0.5y = 2 -----------------------------------------------------------
a <- 3
b <- 0.5
c <- 2

x <- seq(-4, 4, by = 1)
y <- (a*x + c) / b

p1 <- ggplot(data.frame(x, y), aes(x, y)) +
  geom_hline(yintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_line() + 
  labs(title = "3x + y/2 = 2") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot 3x + 0.5y = 0 -----------------------------------------------------------
a <- 3
b <- 0.5
c <- 0

x <- seq(-4, 4, by = 1)
y <- (a*x + c) / b

p2 <- ggplot(data.frame(x, y), aes(x, y)) +
  geom_hline(yintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "steelblue", linetype = "dashed") + 
  geom_line() + 
  labs(title = "3x + y/2 = 0") +  
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

What happens when we have a collection of linear equations, or a linear
system? In statistics, a linear system is used to contain multiple
observations of a phenomenon for modelling purposes and we solve for the
coefficient estimates
![\\hat{\\beta}](https://latex.codecogs.com/svg.format?%5Chat%7B%5Cbeta%7D "\hat{\beta}")
where
![Y = X\\beta + \\epsilon](https://latex.codecogs.com/svg.format?Y%20%3D%20X%5Cbeta%20%2B%20%5Cepsilon "Y = X\beta + \epsilon")
and ![X](https://latex.codecogs.com/svg.format?X "X") and
![Y](https://latex.codecogs.com/svg.format?Y "Y") are treated as random
variables.

In contrast, in mathematical modelling, a linear system is used to
contain multiple observations which are fixed and we solve for
![(x_1, x_2, ..., x_n)](https://latex.codecogs.com/svg.format?%28x_1%2C%20x_2%2C%20...%2C%20x_n%29 "(x_1, x_2, ..., x_n)")
where
![\\vec a_1x_1 + \\vec a_2x_2 + \\cdots+\\vec a_nx_n=\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20a_1x_1%20%2B%20%5Cvec%20a_2x_2%20%2B%20%5Ccdots%2B%5Cvec%20a_nx_n%3D%5Cvec%20b "\vec a_1x_1 + \vec a_2x_2 + \cdots+\vec a_nx_n=\vec b")
and
![a, b \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?a%2C%20b%20%5Cin%20%5Cmathbb%7BR%7D "a, b \in \mathbb{R}").
The linear system is true when the solution set
![(s_1, s_2, ..., s_n)](https://latex.codecogs.com/svg.format?%28s_1%2C%20s_2%2C%20...%2C%20s_n%29 "(s_1, s_2, ..., s_n)")
substitutes for
![(x_1, x_2, ..., x_n)](https://latex.codecogs.com/svg.format?%28x_1%2C%20x_2%2C%20...%2C%20x_n%29 "(x_1, x_2, ..., x_n)").

<img src="../figures/linear_systems-linear_forms.svg" width="80%" style="display: block; margin: auto;" />

For a system of linear equations, we have three possible scenarios:

-   The linear system is inconsistent (at least one equation is false
    with respect to other equations) and we have an **empty** set of
    solutions.  
-   The linear system is consistent and has one solution set
    i.e. ![\\{(a, b, c)\\}](https://latex.codecogs.com/svg.format?%5C%7B%28a%2C%20b%2C%20c%29%5C%7D "\{(a, b, c)\}")
    where a, b and c are constants.  
-   The linear system is consistent and has infinite solution (or the
    solution set has infinitely many elements)
    i.e. ![\\{(a, b, x_3 - 2) \| x_3 \\in \\mathbb{R}\\}](https://latex.codecogs.com/svg.format?%5C%7B%28a%2C%20b%2C%20x_3%20-%202%29%20%7C%20x_3%20%5Cin%20%5Cmathbb%7BR%7D%5C%7D "\{(a, b, x_3 - 2) | x_3 \in \mathbb{R}\}")
    where a and b are constants and
    ![x_3 \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?x_3%20%5Cin%20%5Cmathbb%7BR%7D "x_3 \in \mathbb{R}").
    Infinite solutions always occur when you have less observations than
    variables i.e. the
    ![n\<p](https://latex.codecogs.com/svg.format?n%3Cp "n<p")
    [problem](https://stats.stackexchange.com/questions/385711/what-is-the-problem-with-p-n)
    in statistics.

In 2D, we can see that solutions have two properties:  
+ Solutions can be solved (through simplification) using a consistent
mathematical approach.  
+ Solutions have a geometric intuition. For example in 2D, solutions can
be represented as two lines which never intersect, two lines which
intersect once, or two lines superimposed on each other i.e. infinite
intersection points.

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot inconsistent linear system in R -----------------------------------------
data.frame(x <- seq(-10, 10, by = 1), 
           y1 <- (-2*x - 5) / 3,
           y2 <- (-4*x + 2) / 6) %>% 
  ggplot(aes(x)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(y = y1)) + 
  geom_line(aes(y = y2)) + 
  labs(title = "Inconsistent") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot consistent linear system with single solution in R ----------------------
data.frame(x1 <- 8/4,
           y1 <- seq(-10, 10, by = 1),
           x2 <- seq(-10, 10, by = 1), 
           y2 <- 2/3) %>% 
  ggplot(aes(x2, y1)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(x = x1)) + 
  geom_line(aes(y = y2)) + 
  labs(title = "Consistent single solution") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted"))

# Plot consistent linear system with infinite solutions in R -------------------
data.frame(x <- seq(-10, 10, by = 1),
           y1 <- (-2*x + 5) / 3,
           y2 <- (-4*x + 10) / 6) %>% 
  ggplot(aes(x)) +
  geom_hline(yintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_vline(xintercept = 0, colour = "linen", linetype = "dashed") + 
  geom_line(aes(y = y1)) + 
  geom_line(aes(y = y2)) + 
  labs(title = "Consistent infinite solutions") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) 
```

<img src="linear_algebra-linear_systems_files/figure-gfm/unnamed-chunk-5-1.png" width="80%" style="display: block; margin: auto;" /><img src="linear_algebra-linear_systems_files/figure-gfm/unnamed-chunk-5-2.png" width="80%" style="display: block; margin: auto;" /><img src="linear_algebra-linear_systems_files/figure-gfm/unnamed-chunk-5-3.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

# Equivalent systems

Two linear systems are equivalent if they have the same n-tuple solution
set. That equivalence exists implies that we can convert one linear
system into an equivalent simpler linear system, to more easily find its
solution set.

The process of converting a linear system into an equivalent simpler
linear system can be considered as an algorithm. To construct this
algorithm, we would need to understand the operational constraints for
maintaining equivalency i.e. identify the set of possible elementary
equation operations.

<img src="../figures/linear_systems-equivalence.svg" width="80%" style="display: block; margin: auto;" />

The three elementary equation operations (EEOs) are:  
+ Replacement - replace an equation by the sum of itself and the
multiple of another equation.  
+ Interchange - interchange the listed order of two equations.  
+ Scaling - replace an equation with a multiple of itself.

If we know that there is a finite sequence of elementary equation
operations to transform A into B, then the best algorithm will select
the minimal sequence of elementary equation operations to transform A
into B, where B is the most easily solvable linear system. This is the
essence of the row reduction (or Gauss Jordan elimination) algorithm.

# Augmented matrices and matrix echelon forms

Linear systems can be represented by matrices (the coefficient matrix or
the augmented matrix). Matrices can exist in an echelon form and a
reduced echelon form.

The matrix equivalent of elementary equation operations are elementary
row operations (EROs).

<img src="../figures/linear_systems-echelon_forms.svg" width="80%" style="display: block; margin: auto;" />

A matrix is an echelon form if:  
+ All non-zero rows are above rows of all zeros. When rows of all zeros
exist, they represent the presence of **free variables** in a solution
i.e. when ![n\<p](https://latex.codecogs.com/svg.format?n%3Cp "n<p").  
+ Each leading entry (or pivot column of a row) is located to the right
of the leading entry of the row above it. Each leading entry in the
echelon form represents a fixed or **basic variable** in the linear
system.  
+ All entries in a column below a leading entry are zeros.

A matrix is in reduced echelon form if additionally:  
+ All leading entries are 1.  
+ Each leading 1 is the only non-zero entry in its column.

When a matrix is in the echelon form, we can solve the linear system by
either:  
1. Directly using back substitution to simply the list of equations and
solve for each variable. Solutions should be presented in the form of
constants or free variables only.  
2. Further reducing the matrix to its reduced echelon form (where the
solution for each variable is obvious).

<img src="../figures/linear_systems-echelon_solutions.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Linear systems with infinite solutions are easily identified
in matrix form, by the presence of at least one row which lacks a
leading edge. Free variables correspond to variables without a
positional leading edge or pivot column in the echelon form of the
augmented matrix.

# Row reduction algorithmn

In the row reduction algorithm (also know as the Gauss Jordan
Elimination algorithm), we aim to:

1.  Find the matrix **echelon form** by applying replacement elementary
    row operations
    i.e. ![R_j + kR_i](https://latex.codecogs.com/svg.format?R_j%20%2B%20kR_i "R_j + kR_i"))
    on all columns below the leading edge in a row. Repeat this step for
    each leading edge of each row.  
2.  Find the matrix **reduced echelon form** by identifying the right
    most leading edge and using a scaling elementary row operation to
    convert it into 1. Apply replacement elementary row operations
    i.e. ![R_i + kR_j](https://latex.codecogs.com/svg.format?R_i%20%2B%20kR_j "R_i + kR_j"))
    on all columns above the leading 1. Repeat this step for each
    leading 1 of each row.

**Note:** Each matrix is row equivalent to exactly one matrix in reduced
echelon form.

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

# Homogenous linear systems

How can we easily identify systems with infinite compared to single
solutions? By presenting the set of solutions
![(s_1, s_2, ..., s_n)](https://latex.codecogs.com/svg.format?%28s_1%2C%20s_2%2C%20...%2C%20s_n%29 "(s_1, s_2, ..., s_n)")
in a parametric vector form.

It is easy to identify the parametric vector form of homogeneous linear
systems, which have the form
![A\\vec x=\\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%200 "A\vec x=\vec 0").
These equations either have a single trivial solution (they only
intersect at the origin) or infinite solutions (defined in relation to
its free variables).

If
![A\\vec x=\\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%20b "A\vec x=\vec b")
has infinite solutions:  
+ At least one solution is
![\\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20p "\vec p")
i.e. a single vector of real numbers or a point in
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m").  
+ At least one other equation can be represented as a homogeneous linear
system with form
![A\\vec v_h=\\vec0](https://latex.codecogs.com/svg.format?A%5Cvec%20v_h%3D%5Cvec0 "A\vec v_h=\vec0"),
where the solution set is the vector span of
![\\{\\vec v_1, ... , \\vec v\_{h} \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20...%20%2C%20%5Cvec%20v_%7Bh%7D%20%5C%7D "\{\vec v_1, ... , \vec v_{h} \}")
where
![\\vec v_h = \\vec q - \\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20v_h%20%3D%20%5Cvec%20q%20-%20%5Cvec%20p "\vec v_h = \vec q - \vec p").  
+ The solution set of
![A\\vec x=\\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%20b "A\vec x=\vec b")
can therefore also be presented in the form
![\\{\\vec p+c_1\\vec v_1+ ... +c_h\\vec v\_{h}\|c_1, ... ,c_h\\in \\mathbb{R}\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20p%2Bc_1%5Cvec%20v_1%2B%20...%20%2Bc_h%5Cvec%20v_%7Bh%7D%7Cc_1%2C%20...%20%2Cc_h%5Cin%20%5Cmathbb%7BR%7D%5C%7D "\{\vec p+c_1\vec v_1+ ... +c_h\vec v_{h}|c_1, ... ,c_h\in \mathbb{R}\}").

<img src="../figures/linear_systems-infinite_solutions.svg" width="80%" style="display: block; margin: auto;" />

Solving a linear system can therefore also be viewed as either finding a
parametric description of the solution set or determining that the
system is inconsistent.

<img src="../figures/linear_systems-parametric_solutions.svg" width="80%" style="display: block; margin: auto;" />

When the solution is expressed as a parametric vector form, we can form
some geometric intuition about the vector span of
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b").
For an infinite solution, the solution is an
![\\mathbb{R}^{n-p}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E%7Bn-p%7D "\mathbb{R}^{n-p}")
object which intersects with the point represented by
![\\vec p](https://latex.codecogs.com/svg.format?%5Cvec%20p "\vec p").

<img src="../figures/linear_systems-parametric_solution_example.svg" width="80%" style="display: block; margin: auto;" />

**Note:** The solution to a linear system will only contain the origin
point if and only if the entire linear system is homogeneous i.e. the
entire linear system has form
![A\\vec x=\\vec0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec0 "A\vec x=\vec0").

# Linear independence and homogenous linear systems

A homogeneous linear system
![A\\vec v=\\vec0](https://latex.codecogs.com/svg.format?A%5Cvec%20v%3D%5Cvec0 "A\vec v=\vec0")
is linearly independent if it only has one trivial solution. The set of
solutions
![\\{s_1, s_2, \\cdots, s_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bs_1%2C%20s_2%2C%20%5Ccdots%2C%20s_n%5C%7D "\{s_1, s_2, \cdots, s_n\}")
therefore has linear independence.

If a homogeneous linear system has infinite solutions, at least one
linear equation is equivalent to another linear equation i.e. at least
one sub-matrix of form
![A\\vec v_h=\\vec0](https://latex.codecogs.com/svg.format?A%5Cvec%20v_h%3D%5Cvec0 "A\vec v_h=\vec0")
exists. The solution set of
![\\{s_1, s_2, \\cdots, s_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bs_1%2C%20s_2%2C%20%5Ccdots%2C%20s_n%5C%7D "\{s_1, s_2, \cdots, s_n\}")
therefore has linear dependence.

Linear dependence is therefore represented by the presence of one or
more free variables in a linear system and its equivalent augmented
matrix. When the parametric vector form of the solution set
![\\{s_1, s_2, \\cdots, s_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bs_1%2C%20s_2%2C%20%5Ccdots%2C%20s_n%5C%7D "\{s_1, s_2, \cdots, s_n\}")
is infinite, at least one
![x](https://latex.codecogs.com/svg.format?x "x") variable is non-zero
in the homogenous linear system
![x_1\\vec a_1+x_2\\vec a_2+\\cdots+x_n\\vec a_n=\\vec 0](https://latex.codecogs.com/svg.format?x_1%5Cvec%20a_1%2Bx_2%5Cvec%20a_2%2B%5Ccdots%2Bx_n%5Cvec%20a_n%3D%5Cvec%200 "x_1\vec a_1+x_2\vec a_2+\cdots+x_n\vec a_n=\vec 0").

<img src="../figures/linear_systems-linear_dependence_a.svg" width="80%" style="display: block; margin: auto;" />

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
