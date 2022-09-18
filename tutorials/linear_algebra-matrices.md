Introduction to matrices
================
Erika Duan
2022-09-18

-   [Matrices](#matrices)
-   [Types of matrices](#types-of-matrices)
-   [Matrix column space](#matrix-column-space)
-   [Matrix null space](#matrix-null-space)
-   [Matrix scalar multiplication](#matrix-scalar-multiplication)
-   [Matrix addition](#matrix-addition)
-   [Matrix multiplication](#matrix-multiplication)
-   [The inverse matrix](#the-inverse-matrix)
-   [Matrix determinant](#matrix-determinant)
-   [Eigenvalues and eigenvectors](#eigenvalues-and-eigenvectors)
-   [Complex eigenvalues and
    eigenvectors](#complex-eigenvalues-and-eigenvectors)
-   [Stochastic matrix](#stochastic-matrix)
-   [Resources](#resources)

# Matrices

A matrix with ![m](https://latex.codecogs.com/svg.format?m "m") rows and
![n](https://latex.codecogs.com/svg.format?n "n") columns can be used to
hold the coefficients from any linear system
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b").

If A is a matrix of linearly independent vectors
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_n](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n "\vec a_1, \vec a_2, \cdots, \vec a_n"),
each column vector represents a scalable basis vector with dimensions
![m \\times 1](https://latex.codecogs.com/svg.format?m%20%5Ctimes%201 "m \times 1").
![Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
generates subspace H, where subspace H has
![n](https://latex.codecogs.com/svg.format?n "n") dimensions and
![\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5Em "\in \mathbb{R}^m").

<img src="../figures/linear_systems-matrix_transformations.svg" width="80%" style="display: block; margin: auto;" />

**Note:** If matrix A is a square
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
matrix of linearly independent vectors, subspace H spanned by
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_n](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n "\vec a_1, \vec a_2, \cdots, \vec a_n")
has n dimensions and
![\\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5En "\in \mathbb{R}^n").

# Types of matrices

Types of matrices include:

-   Zero matrix: a matrix in which every entry is 0.  
-   Symmetrical matrix: a matrix where values on either side of the
    diagonal are equal to each other.
-   Transpose matrix: If matrix A has dimensions
    ![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n"),
    then its transpose matrix
    ![A^T](https://latex.codecogs.com/svg.format?A%5ET "A^T") has
    dimensions
    ![n \\times m](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20m "n \times m")
    and every row of A is a column in
    ![A^T](https://latex.codecogs.com/svg.format?A%5ET "A^T").
    Symmetrical matrices therefore have the property
    ![A^T = A](https://latex.codecogs.com/svg.format?A%5ET%20%3D%20A "A^T = A").  
-   Identity matrix: a matrix with dimensions
    ![m \\times m](https://latex.codecogs.com/svg.format?m%20%5Ctimes%20m "m \times m")
    where each diagonal entry is 1 and all other entries are 0. Identity
    matrices therefore have the property
    ![IA = AI = A](https://latex.codecogs.com/svg.format?IA%20%3D%20AI%20%3D%20A "IA = AI = A").

<img src="../figures/linear_systems-matrix_types.svg" width="80%" style="display: block; margin: auto;" />

# Matrix column space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A,
![A = \\begin{bmatrix} \\vec a_1 & \\vec a_2 & \\cdots & \\vec a_n \\end{bmatrix}](https://latex.codecogs.com/svg.format?A%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cvec%20a_1%20%26%20%5Cvec%20a_2%20%26%20%5Ccdots%20%26%20%5Cvec%20a_n%20%5Cend%7Bbmatrix%7D "A = \begin{bmatrix} \vec a_1 & \vec a_2 & \cdots & \vec a_n \end{bmatrix}").
The column space of A, denoted as
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA"), is the span
of
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_n\}").

Therefore
![ColA = \\{\\vec b \\in \\mathbb{R}^m \| A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?ColA%20%3D%20%5C%7B%5Cvec%20b%20%5Cin%20%5Cmathbb%7BR%7D%5Em%20%7C%20A%5Cvec%20x%20%3D%20%5Cvec%20b "ColA = \{\vec b \in \mathbb{R}^m | A\vec x = \vec b")
for some
![\\vec x \\in \\mathbb{R}^n\\}](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En%5C%7D "\vec x \in \mathbb{R}^n\}").

If
![\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
is linearly independent,
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") is also a
subspace of
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
with n-dimensions
i.e. ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") can be
represented in matrix form with n pivot columns. If the matrix form of
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") contains all
pivot columns and therefore no free variables,
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
must have a single solution and
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")
only has the trivial solution.

<img src="../figures/linear_systems-matrix_column_space.svg" width="80%" style="display: block; margin: auto;" />

# Matrix null space

For any
![m\\times n](https://latex.codecogs.com/svg.format?m%5Ctimes%20n "m\times n")
matrix A, the null space of A, denoted as
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA"), is
specifically defined as the set of all solutions to the homogeneous
linear system
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
expressed through its parametric form
![c_1\\vec v_1 + c_2\\vec v_2 + \\cdots + c_n\\vec v_h](https://latex.codecogs.com/svg.format?c_1%5Cvec%20v_1%20%2B%20c_2%5Cvec%20v_2%20%2B%20%5Ccdots%20%2B%20c_n%5Cvec%20v_h "c_1\vec v_1 + c_2\vec v_2 + \cdots + c_n\vec v_h")
as
![Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_h\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_h%5C%7D "Span\{\vec v_1, \vec v_2, \cdots, \vec v_h\}").

<img src="../figures/linear_systems-matrix_null_space.svg" width="80%" style="display: block; margin: auto;" />

In summary:

-   ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA")
    represents the span of the basis vectors of matrix A. This is also
    called matrix rank.  
-   ![NulA](https://latex.codecogs.com/svg.format?NulA "NulA")
    represents the set of all possible solutions to
    ![A \\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%20%5Cvec%20x%20%3D%20%5Cvec%200 "A \vec x = \vec 0").
    When the solution is presented in parametric form (when there are
    infinite solutions to
    ![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")),
    ![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") also has
    a vector span in relation to its free variables. This is also called
    matrix nullity.

<img src="../figures/linear_systems-matrix_rank_and_nullity.svg" width="80%" style="display: block; margin: auto;" />

**Note:** From examples of homogeneous linear systems, we can see that
the number of column vectors in matrix A, represented as
![n](https://latex.codecogs.com/svg.format?n "n"), is equal to the sum
of the dimensions of
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") and the
dimensions of
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA").

# Matrix scalar multiplication

Matrix scalar multiplication is useful for mapping linear
transformations, which is covered in the next tutorial on [linear
transformations](https://github.com/erikaduan/introductory_maths/blob/master/tutorials/linear_algebra-linear_transformations.md).

<img src="../figures/linear_systems-matrix_scalar_multiplication.svg" width="80%" style="display: block; margin: auto;" />

# Matrix addition

The most useful properties of matrix addition are:

-   That
    ![A + B = B + A](https://latex.codecogs.com/svg.format?A%20%2B%20B%20%3D%20B%20%2B%20A "A + B = B + A").
    This shows that the order of matrix addition does not matter.  
-   That
    ![k(A + B) = kA + kB](https://latex.codecogs.com/svg.format?k%28A%20%2B%20B%29%20%3D%20kA%20%2B%20kB "k(A + B) = kA + kB").
    This shows that the scalar transformation of the sum of A and B is
    identical to the sum of the scalar transformation of A and the
    scalar transformation of B. This is also crucial for understanding
    the form of a linear transformation.

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Matrix multiplication

Unlike matrix addition, the order of matrix multiplication impacts the
matrix multiplication product and
![A \\times B \\neq B \\times A](https://latex.codecogs.com/svg.format?A%20%5Ctimes%20B%20%5Cneq%20B%20%5Ctimes%20A "A \times B \neq B \times A").

When A and B have the same dimensions, matrix multiplication represents
the linear transformation of the original basis vectors (from A) onto
the position of new basis vectors (from B), to form a new linear
transformation (denoted by C) as interpreted using the standard
coordinate system.

<img src="../figures/linear_systems-matrix_multiplication.svg" width="80%" style="display: block; margin: auto;" />

# The inverse matrix

When finding inverse matrices, we only consider matrices with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").

The matrix inverse can be thought of as a matrix form of the
multiplication inverse
![\\tfrac{1}{k}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B1%7D%7Bk%7D "\tfrac{1}{k}")
where
![k \\times \\tfrac{1}{k} = 1](https://latex.codecogs.com/svg.format?k%20%5Ctimes%20%5Ctfrac%7B1%7D%7Bk%7D%20%3D%201 "k \times \tfrac{1}{k} = 1").
A matrix with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
is invertible if it has an inverse form such that
![A\\times A^{-1} = I](https://latex.codecogs.com/svg.format?A%5Ctimes%20A%5E%7B-1%7D%20%3D%20I "A\times A^{-1} = I"),
where ![I](https://latex.codecogs.com/svg.format?I "I") is the identity
matrix.

The existence of an inverse matrix
![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}")
implies the following other properties:

-   If
    ![A\\times A^{-1} = I](https://latex.codecogs.com/svg.format?A%5Ctimes%20A%5E%7B-1%7D%20%3D%20I "A\times A^{-1} = I"),
    ![A^{-1}\\times A = I](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D%5Ctimes%20A%20%3D%20I "A^{-1}\times A = I")
    is also true and therefor the inverse of
    ![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}")
    is A. Therefore
    ![(A^{-1})^{-1} = A](https://latex.codecogs.com/svg.format?%28A%5E%7B-1%7D%29%5E%7B-1%7D%20%3D%20A "(A^{-1})^{-1} = A").  
-   If matrices
    ![M_1, M_2, \\cdots, M_p](https://latex.codecogs.com/svg.format?M_1%2C%20M_2%2C%20%5Ccdots%2C%20M_p "M_1, M_2, \cdots, M_p")
    are invertible
    ![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
    matrices, then
    ![(M_1M_2\\cdots M_p)(M_p^{-1}\\cdots M_2^{-1}M_1^{-1}) = I](https://latex.codecogs.com/svg.format?%28M_1M_2%5Ccdots%20M_p%29%28M_p%5E%7B-1%7D%5Ccdots%20M_2%5E%7B-1%7DM_1%5E%7B-1%7D%29%20%3D%20I "(M_1M_2\cdots M_p)(M_p^{-1}\cdots M_2^{-1}M_1^{-1}) = I")
    and therefore the inverse of
    ![M_1, M_2, \\cdots, M_p](https://latex.codecogs.com/svg.format?M_1%2C%20M_2%2C%20%5Ccdots%2C%20M_p "M_1, M_2, \cdots, M_p")
    can be written as
    ![(M_1, M_2, \\cdots, M_p)^{-1} = (M_p^{-1}\\cdots M_2^{-1}M_1^{-1})](https://latex.codecogs.com/svg.format?%28M_1%2C%20M_2%2C%20%5Ccdots%2C%20M_p%29%5E%7B-1%7D%20%3D%20%28M_p%5E%7B-1%7D%5Ccdots%20M_2%5E%7B-1%7DM_1%5E%7B-1%7D%29 "(M_1, M_2, \cdots, M_p)^{-1} = (M_p^{-1}\cdots M_2^{-1}M_1^{-1})").  
-   If A is invertible,
    ![A^T(A^{-1}){^T}= (A^{-1}A)^{T} = I^T = I](https://latex.codecogs.com/svg.format?A%5ET%28A%5E%7B-1%7D%29%7B%5ET%7D%3D%20%28A%5E%7B-1%7DA%29%5E%7BT%7D%20%3D%20I%5ET%20%3D%20I "A^T(A^{-1}){^T}= (A^{-1}A)^{T} = I^T = I")
    and
    ![(A^{-1}){^T}A^T= (AA^{-1})^{T} = I^T = I](https://latex.codecogs.com/svg.format?%28A%5E%7B-1%7D%29%7B%5ET%7DA%5ET%3D%20%28AA%5E%7B-1%7D%29%5E%7BT%7D%20%3D%20I%5ET%20%3D%20I "(A^{-1}){^T}A^T= (AA^{-1})^{T} = I^T = I").
    Therefore ![A^T](https://latex.codecogs.com/svg.format?A%5ET "A^T")
    is also invertible and
    ![(A^T)^{-1} = (A^{-1})^{T}](https://latex.codecogs.com/svg.format?%28A%5ET%29%5E%7B-1%7D%20%3D%20%28A%5E%7B-1%7D%29%5E%7BT%7D "(A^T)^{-1} = (A^{-1})^{T}").

To develop an algorithm to find
![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}"),
we first consider the scenario where a single elementary row operation
(ERO) is performed on the identity matrix to convert it into another row
equivalent matrix.

The ERO can be represented as matrix multiplication by the elementary
matrix ![E_1](https://latex.codecogs.com/svg.format?E_1 "E_1") where
![E_1I = E_1](https://latex.codecogs.com/svg.format?E_1I%20%3D%20E_1 "E_1I = E_1").
Since EROs are reversible,
![E_1^{-1}](https://latex.codecogs.com/svg.format?E_1%5E%7B-1%7D "E_1^{-1}")
also exists and
![E_1E_1^{-1} = I](https://latex.codecogs.com/svg.format?E_1E_1%5E%7B-1%7D%20%3D%20I "E_1E_1^{-1} = I").
The same ERO that transforms
![I](https://latex.codecogs.com/svg.format?I "I") into
![E_1](https://latex.codecogs.com/svg.format?E_1 "E_1") can also be
applied to matrix A to transform it into matrix B
i.e. ![E_1A = B](https://latex.codecogs.com/svg.format?E_1A%20%3D%20B "E_1A = B").

If a single ERO transforms A into the identity matrix
i.e. ![E_1A=I](https://latex.codecogs.com/svg.format?E_1A%3DI "E_1A=I"),
then
![E_1 = A^{-1}](https://latex.codecogs.com/svg.format?E_1%20%3D%20A%5E%7B-1%7D "E_1 = A^{-1}").
If a finite sequence of EROs transforms A into the identity matrix
i.e. ![(E_p\\cdots E_2E_1)A=I](https://latex.codecogs.com/svg.format?%28E_p%5Ccdots%20E_2E_1%29A%3DI "(E_p\cdots E_2E_1)A=I"),
then
![(E_p\\cdots E_2E_1)I = A^{-1}](https://latex.codecogs.com/svg.format?%28E_p%5Ccdots%20E_2E_1%29I%20%3D%20A%5E%7B-1%7D "(E_p\cdots E_2E_1)I = A^{-1}").

<img src="../figures/linear_systems-elementary_matrix.svg" width="80%" style="display: block; margin: auto;" />

Therefore a matrix is invertible if matrix
![A](https://latex.codecogs.com/svg.format?A "A") is row equivalent to
its identify matrix ![I](https://latex.codecogs.com/svg.format?I "I")
and any finite sequence of elementary row operations that transforms
![A](https://latex.codecogs.com/svg.format?A "A") to
![I](https://latex.codecogs.com/svg.format?I "I") also transforms
![I](https://latex.codecogs.com/svg.format?I "I") to
![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}").

Thus, the connection between linear systems and invertible matrices is
that the linear system
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
only has a unique solution if matrix A is invertible, as the reduced
echelon form of A is the identity matrix. We can therefore also solve
for
![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
using
![\\vec x = A^{-1} \\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%3D%20A%5E%7B-1%7D%20%5Cvec%20b "\vec x = A^{-1} \vec b").

In the algorithm for finding the inverse matrix
![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}"),
we aim to:

1.  Write down the augmented matrix
    ![\\left\[\\begin{array}{c\|c}A&I_n\\end{array}\\right\]](https://latex.codecogs.com/svg.format?%5Cleft%5B%5Cbegin%7Barray%7D%7Bc%7Cc%7DA%26I_n%5Cend%7Barray%7D%5Cright%5D "\left[\begin{array}{c|c}A&I_n\end{array}\right]").  
2.  Row reduce the augmented matrix until its left-hand side is in
    reduced echelon form. Let this be the result
    ![\\left\[\\begin{array}{c\|c}B&C\\end{array}\\right\]](https://latex.codecogs.com/svg.format?%5Cleft%5B%5Cbegin%7Barray%7D%7Bc%7Cc%7DB%26C%5Cend%7Barray%7D%5Cright%5D "\left[\begin{array}{c|c}B&C\end{array}\right]").  
3.  If
    ![B = I_n](https://latex.codecogs.com/svg.format?B%20%3D%20I_n "B = I_n"),
    then the right-hand side of the augmented matrix is the inverse
    matrix
    i.e. ![C=A^{-1}](https://latex.codecogs.com/svg.format?C%3DA%5E%7B-1%7D "C=A^{-1}").
    If the left-hand side cannot be simplified to a reduced echelon
    form, then matrix A is not invertible.

<img src="../figures/linear_systems-inverse_matrix.svg" width="80%" style="display: block; margin: auto;" />

**Note:** If matrix A is row equivalent to the identity matrix
![I_n](https://latex.codecogs.com/svg.format?I_n "I_n"), then the
columns of A must all contain pivot columns i.e. no free variables exist
and the equation
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")
must only contain the trivial solution
![x_1 = x_2 = \\cdots = x_n = 0](https://latex.codecogs.com/svg.format?x_1%20%3D%20x_2%20%3D%20%5Ccdots%20%3D%20x_n%20%3D%200 "x_1 = x_2 = \cdots = x_n = 0").

**Note:** A matrix that is not invertible is also called a singular
matrix and an invertible matrix is therefore also called a non-singular
matrix.

# Matrix determinant

When finding inverse matrices, we only consider matrices with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").

The determinant of a matrix is a scalar value and is geometrically
equivalent to the area of the parallelogram formed by the basis vectors
in
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2")
or the volume of the parallelepiped formed by the basis vectors in
![\\mathbb{R}^3](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E3 "\mathbb{R}^3").
We can therefore use the determinant to describe how large or small the
basis of a subspace is relative to another basis for the same subspace.

This also implies that for a linear transformation
![T: \\mathbb{R}^2 \\to \\mathbb{R}^2](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5E2%20%5Cto%20%5Cmathbb%7BR%7D%5E2 "T: \mathbb{R}^2 \to \mathbb{R}^2"),
if S is a parallelogram in
![\\mathbb{R}^2](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E2 "\mathbb{R}^2"),
the area of
![T(S) = \|detA\|\\times S](https://latex.codecogs.com/svg.format?T%28S%29%20%3D%20%7CdetA%7C%5Ctimes%20S "T(S) = |detA|\times S").

<img src="../figures/linear_systems-determinant_geometric_representation.svg" width="80%" style="display: block; margin: auto;" />

The mathematical definition of the matrix determinant involves
identifying all relevant
![(i,j)](https://latex.codecogs.com/svg.format?%28i%2Cj%29 "(i,j)")-cofactor
submatrices of matrix A and finding the sum of the product of their
determinant and
![a\_{ij}](https://latex.codecogs.com/svg.format?a_%7Bij%7D "a_{ij}")
and
![(-1)^(i_j)](https://latex.codecogs.com/svg.format?%28-1%29%5E%28i_j%29 "(-1)^(i_j)").

<img src="../figures/linear_systems-determinant_definition.svg" width="80%" style="display: block; margin: auto;" />

Let A be an
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
matrix. We can use two approaches to calculate the determinant of an
matrix:

-   When
    ![n\\leq2](https://latex.codecogs.com/svg.format?n%5Cleq2 "n\leq2")
    or any row or column along matrix A contains predominantly zeros, we
    can use the
    ![(i,j)](https://latex.codecogs.com/svg.format?%28i%2Cj%29 "(i,j)")-cofactor
    expansion method to find
    ![detA](https://latex.codecogs.com/svg.format?detA "detA").  
-   When
    ![n\\geq3](https://latex.codecogs.com/svg.format?n%5Cgeq3 "n\geq3")
    and no rows or columns along matrix A contain predominantly zeros,
    we can use the row reduction method to find
    ![detA](https://latex.codecogs.com/svg.format?detA "detA").

**Deriving the row reduction method of finding detA:**  
If matrix A is in echelon form, detA is equal to the product of the
entries along the matrix diagonal. This is because when you select the
first column and calculate
![detA =\\displaystyle\\sum\_{i=1}^{n} (-1)^{i+1} \\times a\_{i1} \\times detA\_{i1}](https://latex.codecogs.com/svg.format?detA%20%3D%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20%28-1%29%5E%7Bi%2B1%7D%20%5Ctimes%20a_%7Bi1%7D%20%5Ctimes%20detA_%7Bi1%7D "detA =\displaystyle\sum_{i=1}^{n} (-1)^{i+1} \times a_{i1} \times detA_{i1}"),
only
![a\_{11}](https://latex.codecogs.com/svg.format?a_%7B11%7D "a_{11}")
produces a non-zero product and
![detA\_{11} = (-1)^2 \\times a\_{11}\\times detA\_{i1} = a\_{11} \\times (a\_{21} \\cdots \\times a\_{n1})](https://latex.codecogs.com/svg.format?detA_%7B11%7D%20%3D%20%28-1%29%5E2%20%5Ctimes%20a_%7B11%7D%5Ctimes%20detA_%7Bi1%7D%20%3D%20a_%7B11%7D%20%5Ctimes%20%28a_%7B21%7D%20%5Ccdots%20%5Ctimes%20a_%7Bn1%7D%29 "detA_{11} = (-1)^2 \times a_{11}\times detA_{i1} = a_{11} \times (a_{21} \cdots \times a_{n1})"),
which is the product of the entries along the matrix diagonal.

Let matrix E be an elementary matrix with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").
![det(EA) = detE \\times detA](https://latex.codecogs.com/svg.format?det%28EA%29%20%3D%20detE%20%5Ctimes%20detA "det(EA) = detE \times detA")
where
![detE = 1](https://latex.codecogs.com/svg.format?detE%20%3D%201 "detE = 1")
for a row replacement ERO,
![detE = -1](https://latex.codecogs.com/svg.format?detE%20%3D%20-1 "detE = -1")
for an interchange ERO and
![detE = k](https://latex.codecogs.com/svg.format?detE%20%3D%20k "detE = k")
for a scaling ERO than scales a row by
![k](https://latex.codecogs.com/svg.format?k "k").

<img src="../figures/linear_systems-determinant_elementary_matrices.svg" width="80%" style="display: block; margin: auto;" />

To calculate determinants for large matrices, we can therefore use the
row reduction algorithm to find an echelon form of matrix A **without
performing any scaling operations**, where
![E_p, \\cdots, E_1A = R](https://latex.codecogs.com/svg.format?E_p%2C%20%5Ccdots%2C%20E_1A%20%3D%20R "E_p, \cdots, E_1A = R")
and
![A = (E_p, \\cdots, E_1)^{-1}R](https://latex.codecogs.com/svg.format?A%20%3D%20%28E_p%2C%20%5Ccdots%2C%20E_1%29%5E%7B-1%7DR "A = (E_p, \cdots, E_1)^{-1}R").

Therefore,
![detA = (-1)^r \\times](https://latex.codecogs.com/svg.format?detA%20%3D%20%28-1%29%5Er%20%5Ctimes "detA = (-1)^r \times")
the product of the diagonal entries in R, where
![r](https://latex.codecogs.com/svg.format?r "r") is the number of row
interchange operations used.

<img src="../figures/linear_systems-determinant_row_reduction.svg" width="80%" style="display: block; margin: auto;" />

**Relationship between an invertible matrix and its determinant:**  
Matrix A is invertible if
![detA \\neq 0](https://latex.codecogs.com/svg.format?detA%20%5Cneq%200 "detA \neq 0")
has an invertible matrix has a row equivalent reduced echelon form where
all columns are pivot columns. The row equivalent reduced echelon form
of matrix A therefore does not have any zeros along its matrix diagonal
and
![detA \\neq 0](https://latex.codecogs.com/svg.format?detA%20%5Cneq%200 "detA \neq 0").

**Proving det(AB) = (detA)(detB):**  
When A is not an invertible matrix,
![detA=0](https://latex.codecogs.com/svg.format?detA%3D0 "detA=0") and
![0\\times detB = 0](https://latex.codecogs.com/svg.format?0%5Ctimes%20detB%20%3D%200 "0\times detB = 0").
Therefore
![det(AB) = detA \\times detB](https://latex.codecogs.com/svg.format?det%28AB%29%20%3D%20detA%20%5Ctimes%20detB "det(AB) = detA \times detB").  
When A and B are both invertible,
![detA= E_1^{-1}\\cdots E_p^{-1}I](https://latex.codecogs.com/svg.format?detA%3D%20E_1%5E%7B-1%7D%5Ccdots%20E_p%5E%7B-1%7DI "detA= E_1^{-1}\cdots E_p^{-1}I")
and
![detB= F_1^{-1}\\cdots F_p^{-1}I](https://latex.codecogs.com/svg.format?detB%3D%20F_1%5E%7B-1%7D%5Ccdots%20F_p%5E%7B-1%7DI "detB= F_1^{-1}\cdots F_p^{-1}I").  
![detA \\times detB = det(E_1^{-1}\\cdots E_p^{-1}I)det(F_1^{-1}\\cdots F_p^{-1}I)](https://latex.codecogs.com/svg.format?detA%20%5Ctimes%20detB%20%3D%20det%28E_1%5E%7B-1%7D%5Ccdots%20E_p%5E%7B-1%7DI%29det%28F_1%5E%7B-1%7D%5Ccdots%20F_p%5E%7B-1%7DI%29 "detA \times detB = det(E_1^{-1}\cdots E_p^{-1}I)det(F_1^{-1}\cdots F_p^{-1}I)")  
![detA \\times detB = det((E_1^{-1}\\cdots E_p^{-1})(F_1^{-1}\\cdots F_p^{-1})) = det(AB)](https://latex.codecogs.com/svg.format?detA%20%5Ctimes%20detB%20%3D%20det%28%28E_1%5E%7B-1%7D%5Ccdots%20E_p%5E%7B-1%7D%29%28F_1%5E%7B-1%7D%5Ccdots%20F_p%5E%7B-1%7D%29%29%20%3D%20det%28AB%29 "detA \times detB = det((E_1^{-1}\cdots E_p^{-1})(F_1^{-1}\cdots F_p^{-1})) = det(AB)")
as every elementary matrix is individually invertible.

**Relationship between a transpose matrix and its determinant:**  
![detA = detA^T](https://latex.codecogs.com/svg.format?detA%20%3D%20detA%5ET "detA = detA^T")
as reflected by the co-factor expansion method of finding a determinant
(where co-factor expansion can occur along either a column or a row).

**Using Cramer’s rule to find the determinant:**  
Cramer’s rule can be used to find the determinant when A is an
invertible matrix and
![detA \\neq 0](https://latex.codecogs.com/svg.format?detA%20%5Cneq%200 "detA \neq 0").

<img src="../figures/linear_systems-determinant_cramer.svg" width="80%" style="display: block; margin: auto;" />

The key to proving Cramer’s rule is to define
![detA_1(\\vec b) = AI_i(\\vec x)](https://latex.codecogs.com/svg.format?detA_1%28%5Cvec%20b%29%20%3D%20AI_i%28%5Cvec%20x%29 "detA_1(\vec b) = AI_i(\vec x)")
and then apply the determinant property that
![det(AI_i(\\vec x)) = detA \\times det(I_i(\\vec x))](https://latex.codecogs.com/svg.format?det%28AI_i%28%5Cvec%20x%29%29%20%3D%20detA%20%5Ctimes%20det%28I_i%28%5Cvec%20x%29%29 "det(AI_i(\vec x)) = detA \times det(I_i(\vec x))").

<img src="../figures/linear_systems-determinant_cramer_proof.svg" width="80%" style="display: block; margin: auto;" />

# Eigenvalues and eigenvectors

When finding eigenvalues and eigenvectors, we currently only consider
matrices with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").

Although matrices are used to represent the coordinate system of a
linear transformation, we can also categorise linear transformations by
type. One method is to categorise linear transformations by whether they
can be decomposed into a series of simpler transformations.

-   For scaling transformations, the basis vectors
    ![\\{\\vec v_1, \\cdots, \\vec v_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%5C%7D "\{\vec v_1, \cdots, \vec v_n\}")
    are each scaled by a constant
    ![\\{k_1, \\cdots, k_n\\}](https://latex.codecogs.com/svg.format?%5C%7Bk_1%2C%20%5Ccdots%2C%20k_n%5C%7D "\{k_1, \cdots, k_n\}").  
-   Other linear transformations may contain vector subspaces exists
    where the transformation of vector
    ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
    scales it by a constant
    i.e. ![A(\\vec x) = \\lambda \\vec x](https://latex.codecogs.com/svg.format?A%28%5Cvec%20x%29%20%3D%20%5Clambda%20%5Cvec%20x "A(\vec x) = \lambda \vec x").
    For example, for a sheer transformation, one basis vector is always
    scaled by a constant
    ![k](https://latex.codecogs.com/svg.format?k "k").  
-   A linear transformation is **diagonalisable** if it can be
    translated into a different basis
    ![\\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5En "\in \mathbb{R}^n"),
    where the basis vectors are then each scaled by a constant, and then
    translated back into the regular basis.

Properties of **eigenvalues**:  
+ Eigenvalues exist if a non-zero vector
![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
exists for
![A(\\vec x) = \\lambda \\vec x](https://latex.codecogs.com/svg.format?A%28%5Cvec%20x%29%20%3D%20%5Clambda%20%5Cvec%20x "A(\vec x) = \lambda \vec x"). +
Eigenvalues therefore exist if a non-trivial solution to
![(A-\\lambda I)\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?%28A-%5Clambda%20I%29%5Cvec%20x%20%3D%20%5Cvec%200 "(A-\lambda I)\vec x = \vec 0")
exists
i.e. ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
cannot be zero.  
+ Eigenvalues therefore exists if
![(A-\\lambda I)\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?%28A-%5Clambda%20I%29%5Cvec%20x%20%3D%20%5Cvec%200 "(A-\lambda I)\vec x = \vec 0")
has infinite solutions and if
![det(A-\\lambda I) = 0](https://latex.codecogs.com/svg.format?det%28A-%5Clambda%20I%29%20%3D%200 "det(A-\lambda I) = 0").  
+ ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
is therefore the eigenvector(s) corresponding to eigenvalue
![\\lambda](https://latex.codecogs.com/svg.format?%5Clambda "\lambda").  
+ If A is a triangular matrix (upper or lower triangular matrix or
diagonal matrix), the eigenvalues of A are the entries on its main
diagonal.

<img src="../figures/linear_systems-eigenvalues.svg" width="80%" style="display: block; margin: auto;" />

Properties of **eigenvectors**:  
+ The set of eigenvectors corresponding to an eigenvalue
![\\lambda](https://latex.codecogs.com/svg.format?%5Clambda "\lambda")
is equivalent to
![Nul(A-\\lambda I)](https://latex.codecogs.com/svg.format?Nul%28A-%5Clambda%20I%29 "Nul(A-\lambda I)")
and therefore is a subspace of
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
+ The set of eigenvectors corresponding to
![\\lambda](https://latex.codecogs.com/svg.format?%5Clambda "\lambda")
is linearly independent i.e. is a basis for the eigenspace of A
corresponding to
![\\lambda](https://latex.codecogs.com/svg.format?%5Clambda "\lambda").

**Matrix diagonalisation**:  
Let matrix A have dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").
Matrix A is diagonalisable if:

-   ![A = PDP^{-1}](https://latex.codecogs.com/svg.format?A%20%3D%20PDP%5E%7B-1%7D "A = PDP^{-1}")
    where ![P](https://latex.codecogs.com/svg.format?P "P") is an
    invertible
    ![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
    matrix and D is a diagonal
    ![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
    matrix.
-   The columns of P must form an eigenvector basis for
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
    is spanned by a linearly independent set of eigenvectors
    ![\\{\\vec v_1, \\cdots, \\vec v_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%5C%7D "\{\vec v_1, \cdots, \vec v_n\}")
    and each eigenvector is associated with a real eigenvalue.

When matrix A is diagonalisable, the sum of the dimensions of the
eigenspaces according to
![\\lambda](https://latex.codecogs.com/svg.format?%5Clambda "\lambda")
must therefore equal ![n](https://latex.codecogs.com/svg.format?n "n").

Conceptually, finding collections of linearly independent eigenvectors
allows us to find the bases for subspaces in
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
where the linear transformation is invariant (the domain and co-domain
of the linear transformation remains the same).

Pragmatically, finding a diagonalisable matrix is also useful for
quickly solving transformations involving
![A^k](https://latex.codecogs.com/svg.format?A%5Ek "A^k") calculations
i.e. ![A^k = PD^kP^{-1}](https://latex.codecogs.com/svg.format?A%5Ek%20%3D%20PD%5EkP%5E%7B-1%7D "A^k = PD^kP^{-1}").

<img src="../figures/linear_systems-matrix_diagonalisation.svg" width="80%" style="display: block; margin: auto;" />

# Complex eigenvalues and eigenvectors

Matrices with complex eigenvalues and eigenvectors cannot be
diagonalised. However, they can be rewritten in the form A = PCP-1,
where C represents the combination of a rotational and then scaling
transformation.

<img src="../figures/linear_systems-complex_eigenvalues.svg" width="80%" style="display: block; margin: auto;" />

# Stochastic matrix

A stochastic matrix ![T](https://latex.codecogs.com/svg.format?T "T") is
a square matrix with dimensions
![n\\times n](https://latex.codecogs.com/svg.format?n%5Ctimes%20n "n\times n")
probability vectors as columns. A probability vector
![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
contains non-negative entries which sum to 1. The probability of a state
occurring at
![t = k](https://latex.codecogs.com/svg.format?t%20%3D%20k "t = k") is
denoted as
![\\vec x_k](https://latex.codecogs.com/svg.format?%5Cvec%20x_k "\vec x_k").

A Markov Chain is therefore a sequence of probability vectors such that
![\\vec x\_{k+1} = T \\vec x_k](https://latex.codecogs.com/svg.format?%5Cvec%20x_%7Bk%2B1%7D%20%3D%20T%20%5Cvec%20x_k "\vec x_{k+1} = T \vec x_k").

<img src="../figures/linear_systems-stochastic_matrix.svg" width="80%" style="display: block; margin: auto;" />

In order for a system to be represented as a Markov Chain, the following
assumptions must hold:

-   At any moment, the system can only exist in one of
    ![n](https://latex.codecogs.com/svg.format?n "n") discreet states.  
-   We consider the probability that the system is in any state at
    evenly spaced i.e. discrete time steps.  
-   At any time step, the probability that the system will transition to
    another state or remain unchanged is fixed and can be represented by
    the stochastic matrix
    ![T](https://latex.codecogs.com/svg.format?T "T") i.e. a fixed
    matrix of transition probabilities.

If T is the stochastic matrix, a steady-state vector
![\\vec q](https://latex.codecogs.com/svg.format?%5Cvec%20q "\vec q")
exists if
![T(\\vec x) = 1\\vec x](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%201%5Cvec%20x "T(\vec x) = 1\vec x")
where
![\\lambda = 1](https://latex.codecogs.com/svg.format?%5Clambda%20%3D%201 "\lambda = 1")
i.e. ![\\vec q](https://latex.codecogs.com/svg.format?%5Cvec%20q "\vec q")
is an eigenvector for T when
![\\lambda = 1](https://latex.codecogs.com/svg.format?%5Clambda%20%3D%201 "\lambda = 1").

Note that the steady-state vector is represented as a probability
matrix, so all its entries must be non-negative and sum to 1.

**To find the steady-state vector for a stochastic matrix:**

-   Determine whether 1 is an eigenvalue of matrix T. If not, there are
    no steady-states.  
-   Find the set of eigenvectors corresponding to an eigenvalue of 1.  
-   Identify any eigenvectors with non-negative entries and scale the
    eigenvector so that its entries sum to 1. This is the steady-state
    vector for the stochastic matrix
    ![T](https://latex.codecogs.com/svg.format?T "T").

A stochastic matrix ![T](https://latex.codecogs.com/svg.format?T "T") is
regular if ![T_k](https://latex.codecogs.com/svg.format?T_k "T_k")
exists where it does not contain any zero entries. When
![T](https://latex.codecogs.com/svg.format?T "T") is regular, a unique
steady-state vector
![\\vec q](https://latex.codecogs.com/svg.format?%5Cvec%20q "\vec q")
exists and the Markov chain converges to
![\\vec q](https://latex.codecogs.com/svg.format?%5Cvec%20q "\vec q").

<img src="../figures/linear_systems-steady_state_vectors.svg" width="80%" style="display: block; margin: auto;" />

# Resources

-   A great [YouTube
    video](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3)
    introducing matrices by 3Blue1Brown.  
-   A great [YouTube
    video](https://www.youtube.com/watch?v=XkY2DOUCWMU&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=4)
    explaining the purpose of matrix multiplication by 3Blue1Brown.  
-   A [clear
    explanation](https://math.stackexchange.com/questions/664594/why-mathbf0-has-dimension-zero)
    of why the set containing only the zero vector has 0 dimensions.
