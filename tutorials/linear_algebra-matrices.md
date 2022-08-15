Introduction to matrices
================
Erika Duan
2022-08-15

-   [Matrices](#matrices)
-   [Matrix column space](#matrix-column-space)
-   [Matrix null space](#matrix-null-space)
-   [Resources](#resources)

# Matrices

A matrix with ![m](https://latex.codecogs.com/svg.format?m "m") rows and
![n](https://latex.codecogs.com/svg.format?n "n") columns can be used to
hold the coefficients from a linear system
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b").
In other words, each vector
![\\vec a_i](https://latex.codecogs.com/svg.format?%5Cvec%20a_i "\vec a_i")
inside matrix ![A](https://latex.codecogs.com/svg.format?A "A") stores
information about where the basis vector for the i-th dimension lands.

<img src="../figures/linear_systems-matrix_transformations.svg" width="80%" style="display: block; margin: auto;" />

# Matrix column space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A, the column space of A, denoted
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA"), is therefore
the subspace of
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
spanned by the columns i.e. basis vectors
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
of matrix A.

If we represent
![A = \\begin{bmatrix} \\vec a_1 & \\vec a_2 & \\cdots & \\vec a_n \\end{bmatrix}](https://latex.codecogs.com/svg.format?A%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cvec%20a_1%20%26%20%5Cvec%20a_2%20%26%20%5Ccdots%20%26%20%5Cvec%20a_n%20%5Cend%7Bbmatrix%7D "A = \begin{bmatrix} \vec a_1 & \vec a_2 & \cdots & \vec a_n \end{bmatrix}"),
then
![ColA=Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?ColA%3DSpan%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "ColA=Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}").

Therefore
![ColA = \\{\\vec b \\in \\mathbb{R}^m \| A\\vec x = \\vec b \\,for \\,some \\, \\vec x \\in \\mathbb{R}^n\\}](https://latex.codecogs.com/svg.format?ColA%20%3D%20%5C%7B%5Cvec%20b%20%5Cin%20%5Cmathbb%7BR%7D%5Em%20%7C%20A%5Cvec%20x%20%3D%20%5Cvec%20b%20%5C%2Cfor%20%5C%2Csome%20%5C%2C%20%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En%5C%7D "ColA = \{\vec b \in \mathbb{R}^m | A\vec x = \vec b \,for \,some \, \vec x \in \mathbb{R}^n\}").

<img src="../figures/linear_systems-matrix_column_space.svg" width="80%" style="display: block; margin: auto;" />

# Matrix null space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A, the null space of A is the set
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") of all
solutions to the homogeneous equation
![A\\vec x=\\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%3D%5Cvec%200 "A\vec x=\vec 0").

Therefore
![NulA = \\{\\vec x \\in \\mathbb{R}^n \| A\\vec x = \\vec 0\\}](https://latex.codecogs.com/svg.format?NulA%20%3D%20%5C%7B%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En%20%7C%20A%5Cvec%20x%20%3D%20%5Cvec%200%5C%7D "NulA = \{\vec x \in \mathbb{R}^n | A\vec x = \vec 0\}").

The null space of A is a subspace of
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
as the solution set of
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")
can also be expressed in the parametric form
![c_1\\vec v_1 + c_2\\vec v_2 + \\cdots + c_n\\vec v_h](https://latex.codecogs.com/svg.format?c_1%5Cvec%20v_1%20%2B%20c_2%5Cvec%20v_2%20%2B%20%5Ccdots%20%2B%20c_n%5Cvec%20v_h "c_1\vec v_1 + c_2\vec v_2 + \cdots + c_n\vec v_h")
i.e. as
![Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_h\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_h%5C%7D "Span\{\vec v_1, \vec v_2, \cdots, \vec v_h\}")
and
![Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_h\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_h%5C%7D "Span\{\vec v_1, \vec v_2, \cdots, \vec v_h\}")
is a subspace in
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").

<img src="../figures/linear_systems-matrix_null_space.svg" width="80%" style="display: block; margin: auto;" />

**Note:** ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA")
represents the span of all basis vectors of matrix A whereas
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") represents
the set of all possible solutions to form matrix A when
![A \\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%20%5Cvec%20x%20%3D%20%5Cvec%200 "A \vec x = \vec 0").

# Resources

-   A great [YouTube
    series](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3)
    on matrices by 3Blue1Brown.
