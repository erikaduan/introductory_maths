Introduction to matrices
================
Erika Duan
2022-08-20

-   [Matrices](#matrices)
-   [Types of matrices](#types-of-matrices)
-   [Matrix column space](#matrix-column-space)
-   [Matrix null space](#matrix-null-space)
-   [Matrix addition](#matrix-addition)
-   [Matrix scalar multiplication](#matrix-scalar-multiplication)
-   [Matrix multiplication](#matrix-multiplication)
-   [Finding the inverse matrix](#finding-the-inverse-matrix)
-   [Resources](#resources)

# Matrices

A matrix with ![m](https://latex.codecogs.com/svg.format?m "m") rows and
![n](https://latex.codecogs.com/svg.format?n "n") columns can be used to
hold the coefficients from any linear system
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b").

For any homogeneous linear system with linearly independent vectors
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_p](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_p "\vec a_1, \vec a_2, \cdots, \vec a_p"),
each vector represents a scalable basis vector and
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_p\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_p%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_p\}")
spans subspace H, where subspace H has
![p](https://latex.codecogs.com/svg.format?p "p") dimensions.

<img src="../figures/linear_systems-matrix_transformations.svg" width="80%" style="display: block; margin: auto;" />

# Types of matrices

Types of matrices include:

-   Transpose matrix: If matrix A has dimensions
    ![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n"),
    then its transpose matrix
    ![A^T](https://latex.codecogs.com/svg.format?A%5ET "A^T") has
    dimensions
    ![n \\times m](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20m "n \times m")
    and every row of A is a column in
    ![A^T](https://latex.codecogs.com/svg.format?A%5ET "A^T").  
-   Zero matrix: a matrix in which every entry is 0.  
-   Symmetrical matrix: a matrix where values on either side of the
    diagonal are equal to each other. Symmetrical matrices therefore
    have the property
    ![A^T = A](https://latex.codecogs.com/svg.format?A%5ET%20%3D%20A "A^T = A").  
-   Identity matrix: a matrix with dimensions
    ![m \\times m](https://latex.codecogs.com/svg.format?m%20%5Ctimes%20m "m \times m")
    where each diagonal entry is 1 and all other entries are 0.

<img src="../figures/linear_systems-matrix_types.svg" width="80%" style="display: block; margin: auto;" />

# Matrix column space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A,
![A = \\begin{bmatrix} \\vec a_1 & \\vec a_2 & \\cdots & \\vec a_n \\end{bmatrix}](https://latex.codecogs.com/svg.format?A%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cvec%20a_1%20%26%20%5Cvec%20a_2%20%26%20%5Ccdots%20%26%20%5Cvec%20a_n%20%5Cend%7Bbmatrix%7D "A = \begin{bmatrix} \vec a_1 & \vec a_2 & \cdots & \vec a_n \end{bmatrix}").
The column space of A, denoted as
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA"), is therefore
the span of
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_n\}").

Therefore
![ColA = \\{\\vec b \\in \\mathbb{R}^m \| A\\vec x = \\vec b \\,for \\,some \\, \\vec x \\in \\mathbb{R}^n\\}](https://latex.codecogs.com/svg.format?ColA%20%3D%20%5C%7B%5Cvec%20b%20%5Cin%20%5Cmathbb%7BR%7D%5Em%20%7C%20A%5Cvec%20x%20%3D%20%5Cvec%20b%20%5C%2Cfor%20%5C%2Csome%20%5C%2C%20%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En%5C%7D "ColA = \{\vec b \in \mathbb{R}^m | A\vec x = \vec b \,for \,some \, \vec x \in \mathbb{R}^n\}").

![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") is also the
subspace of
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
which is spanned by the basis vectors
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_p\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_p%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_p\}")
or pivot columns of matrix A.

<img src="../figures/linear_systems-matrix_column_space.svg" width="80%" style="display: block; margin: auto;" />

# Matrix null space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A, the null space of A, denoted as
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA"), is the set
of all solutions to the homogeneous linear system
![A\\vec x=\\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%200 "A\vec x=\vec 0").

Therefore
![NulA = \\{\\vec x \\in \\mathbb{R}^n \| A\\vec x = \\vec 0\\}](https://latex.codecogs.com/svg.format?NulA%20%3D%20%5C%7B%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En%20%7C%20A%5Cvec%20x%20%3D%20%5Cvec%200%5C%7D "NulA = \{\vec x \in \mathbb{R}^n | A\vec x = \vec 0\}").

As homogeneous linear systems have either a single trivial solution or
infinite solutions,
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") is either
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0") or
a subspace of
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").

When
![A\\vec x=\\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%200 "A\vec x=\vec 0")
has infinite solutions,
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") can also be
expressed in the parametric form
![c_1\\vec v_1 + c_2\\vec v_2 + \\cdots + c_n\\vec v_h](https://latex.codecogs.com/svg.format?c_1%5Cvec%20v_1%20%2B%20c_2%5Cvec%20v_2%20%2B%20%5Ccdots%20%2B%20c_n%5Cvec%20v_h "c_1\vec v_1 + c_2\vec v_2 + \cdots + c_n\vec v_h")
as
![Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_h\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_h%5C%7D "Span\{\vec v_1, \vec v_2, \cdots, \vec v_h\}").

<img src="../figures/linear_systems-matrix_null_space.svg" width="80%" style="display: block; margin: auto;" />

**Note:** ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA")
represents the span of the basis vectors of matrix A whereas
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") represents
the set of all possible solutions to
![A \\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%20%5Cvec%20x%20%3D%20%5Cvec%200 "A \vec x = \vec 0")
and also has a span when homogeneous linear systems have infinite
solutions.

# Matrix addition

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Matrix scalar multiplication

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Matrix multiplication

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Finding the inverse matrix

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Resources

-   A great [YouTube
    video](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3)
    introducing matrices by 3Blue1Brown.  
-   A great [YouTube
    video](https://www.youtube.com/watch?v=XkY2DOUCWMU&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=4)
    explaining the purpose of matrix multiplication by 3Blue1Brown.
