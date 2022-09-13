Introduction to matrices
================
Erika Duan
2022-09-10

-   [Matrices](#matrices)
-   [Types of matrices](#types-of-matrices)
-   [Matrix column space](#matrix-column-space)
-   [Matrix null space](#matrix-null-space)
-   [Matrix scalar multiplication](#matrix-scalar-multiplication)
-   [Matrix addition](#matrix-addition)
-   [Matrix multiplication](#matrix-multiplication)
-   [The inverse matrix](#the-inverse-matrix)
-   [Matrix determinant](#matrix-determinant)
-   [TODO](#todo)
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

The matrix inverse can be thought of as a matrix form of the
multiplication inverse
![\\tfrac{1}{k}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B1%7D%7Bk%7D "\tfrac{1}{k}")
where
![k \\times \\tfrac{1}{k} = 1](https://latex.codecogs.com/svg.format?k%20%5Ctimes%20%5Ctfrac%7B1%7D%7Bk%7D%20%3D%201 "k \times \tfrac{1}{k} = 1").
When finding inverse matrices, we only consider matrices with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n").

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

# TODO

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
