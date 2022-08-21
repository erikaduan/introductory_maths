Introduction to matrices
================
Erika Duan
2022-08-21

-   [Matrices](#matrices)
-   [Types of matrices](#types-of-matrices)
-   [Matrix column space](#matrix-column-space)
-   [Matrix null space](#matrix-null-space)
-   [Matrix scalar multiplication](#matrix-scalar-multiplication)
-   [Matrix addition](#matrix-addition)
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

In summary:

-   ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA")
    represents the span of the basis vectors of matrix A.  
-   ![NulA](https://latex.codecogs.com/svg.format?NulA "NulA")
    represents the set of all possible solutions to
    ![A \\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%20%5Cvec%20x%20%3D%20%5Cvec%200 "A \vec x = \vec 0").
    When the solution is presented in parametric form (when there are
    infinite solutions to
    ![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")),
    ![NulA](https://latex.codecogs.com/svg.format?NulA "NulA") also has
    a vector span in relation to its free variables.

<img src="../figures/linear_systems-matrix_rank_and_nullity.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Using examples of homogeneous linear systems, we can see that
the number of column vectors in matrix A, represented as
![n](https://latex.codecogs.com/svg.format?n "n"), is equal to the sum
of the dimensions of
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") and the
dimensions of
![NulA](https://latex.codecogs.com/svg.format?NulA "NulA").

# Matrix scalar multiplication

This property is useful for further defining the properties of linear
transformations, which is covered in the next tutorial on linear
transformations.

<img src="../figures/linear_systems-matrix_scalar_multiplication.svg" width="80%" style="display: block; margin: auto;" />

# Matrix addition

Some of the most useful properties of matrix addition include:

-   That
    ![A + B = B + A](https://latex.codecogs.com/svg.format?A%20%2B%20B%20%3D%20B%20%2B%20A "A + B = B + A").
    This shows that the order of matrix addition does not matter.  
-   That
    ![k(A + B) = kA + kB](https://latex.codecogs.com/svg.format?k%28A%20%2B%20B%29%20%3D%20kA%20%2B%20kB "k(A + B) = kA + kB").
    This shows that the scalar transformation of the sum of matrices A
    and B is identical to the sum of the scalar transformation of A and
    the scalar transformation of B. This is also crucial for defining
    the properties of linear transformations.

<img src="../figures/linear_systems-matrix_addition.svg" width="80%" style="display: block; margin: auto;" />

# Matrix multiplication

Unlike matrix addition, the order of matrix multiplication impacts the
matrix multiplication product and
![A \\times B \\neq B \\times A](https://latex.codecogs.com/svg.format?A%20%5Ctimes%20B%20%5Cneq%20B%20%5Ctimes%20A "A \times B \neq B \times A").

Matrix multiplication has extra special meaning in linear algebra as it
represents the sequence of linear transformations applied to any vector
![\\vec v](https://latex.codecogs.com/svg.format?%5Cvec%20v "\vec v"),
where
![\\vec v \\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cvec%20v%20%5Cin%20%5Cmathbb%7BR%7D%5En "\vec v \in \mathbb{R}^n").

<img src="../figures/linear_systems-matrix_multiplication.svg" width="80%" style="display: block; margin: auto;" />

# Finding the inverse matrix

A matrix with dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n")
is invertible if it has an inverse form such that
![A\\times A^{-1} = I](https://latex.codecogs.com/svg.format?A%5Ctimes%20A%5E%7B-1%7D%20%3D%20I "A\times A^{-1} = I")
and
![(A^{-1})^{-1} = A](https://latex.codecogs.com/svg.format?%28A%5E%7B-1%7D%29%5E%7B-1%7D%20%3D%20A "(A^{-1})^{-1} = A"),
where ![I](https://latex.codecogs.com/svg.format?I "I") is the identity
matrix. Therefore a matrix is invertible if matrix
![A](https://latex.codecogs.com/svg.format?A "A") is row equivalent to
its identify matrix ![I](https://latex.codecogs.com/svg.format?I "I")
and any finite sequence of elementary row operations that transforms
![A](https://latex.codecogs.com/svg.format?A "A") to
![I](https://latex.codecogs.com/svg.format?I "I") also transforms
![I](https://latex.codecogs.com/svg.format?I "I") to
![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}").

The matrix inverse can be thought of as a matrix form of the
multiplication inverse
![\\tfrac{1}{k}](https://latex.codecogs.com/svg.format?%5Ctfrac%7B1%7D%7Bk%7D "\tfrac{1}{k}")
where
![k \\times \\tfrac{1}{k} = 1](https://latex.codecogs.com/svg.format?k%20%5Ctimes%20%5Ctfrac%7B1%7D%7Bk%7D%20%3D%201 "k \times \tfrac{1}{k} = 1").

The connection between linear systems and invertible matrices is that
the linear system
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
has a unique solution if matrix A is invertible. This occurs as
![A^{-1}A \\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5E%7B-1%7DA%20%5Cvec%20x%20%3D%20%5Cvec%20b "A^{-1}A \vec x = \vec b")
can be simplified to
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
    ![A^{-1}](https://latex.codecogs.com/svg.format?A%5E%7B-1%7D "A^{-1}")
    i.e. ![C=A^{-1}](https://latex.codecogs.com/svg.format?C%3DA%5E%7B-1%7D "C=A^{-1}").
    If the left-hand side cannot be simplified to a reduced echelon
    form, then matrix A is not invertible.

<img src="../figures/linear_systems-inverse_matrix.svg" width="80%" style="display: block; margin: auto;" />

**Note:** If matrix A is row equivalent to the identity matrix
![I_n](https://latex.codecogs.com/svg.format?I_n "I_n"), then A must
have ![n](https://latex.codecogs.com/svg.format?n "n") pivot columns and
the equation
![A\\vec x = \\vec 0](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%200 "A\vec x = \vec 0")
must only contain the trivial solution
![x_1 = x_2 = \\cdots = x_n = 0](https://latex.codecogs.com/svg.format?x_1%20%3D%20x_2%20%3D%20%5Ccdots%20%3D%20x_n%20%3D%200 "x_1 = x_2 = \cdots = x_n = 0").

**Note:** A matrix that is not invertible is also called a singular
matrix. An invertible matrix is also called a non-singular matrix.

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
