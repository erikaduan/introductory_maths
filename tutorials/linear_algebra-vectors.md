Introduction to vectors
================
Erika Duan
2022-08-28

-   [Vectors](#vectors)
-   [Vector scalar multiplication](#vector-scalar-multiplication)
-   [Vector addition](#vector-addition)
-   [Vector span](#vector-span)
-   [Linear independence versus linear
    dependence](#linear-independence-versus-linear-dependence)
-   [Vector subspaces](#vector-subspaces)
-   [Basis vectors](#basis-vectors)
-   [Coordinate systems](#coordinate-systems)
-   [Resources](#resources)

# Vectors

Vectors are an important way to represent values as positions in
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").
Vector operations and matrix-vector operations enable us to transform
values in useful ways.

A column vector
![\\vec u](https://latex.codecogs.com/svg.format?%5Cvec%20u "\vec u") is
an
![m \\times 1](https://latex.codecogs.com/svg.format?m%20%5Ctimes%201 "m \times 1")
matrix where
![\\vec u \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cvec%20u%20%5Cin%20%5Cmathbb%7BR%7D%5Em "\vec u \in \mathbb{R}^m").
Two vectors are equal if they have the same number of rows and their
corresponding entries are equal.

**Note:** Do not confuse the zero vector
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0")
with the scalar value of 0 when writing vector operations.

<img src="../figures/linear_systems-vectors.svg" width="80%" style="display: block; margin: auto;" />

Key vector operations are:

-   Scalar multiplication - when a vector is scaled by a constant
    ![c](https://latex.codecogs.com/svg.format?c "c") where
    ![c \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?c%20%5Cin%20%5Cmathbb%7BR%7D "c \in \mathbb{R}").  
-   Vector addition - when two vectors with the same dimensions are
    added to form a new vector
    i.e. ![\\vec u + \\vec v = \\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20u%20%2B%20%5Cvec%20v%20%3D%20%5Cvec%20w "\vec u + \vec v = \vec w").
    This is equivalent to creating a new position in
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   Vector multiplication - used to calculate how far apart two vectors
    are with respect to each other, by superimposing the position and
    length of one vector along the axis of the other.

# Vector scalar multiplication

Vector scalar multiplication is used to scale the length of a vector and
can change its direction (i.e. vector direction can be reversed by
multiplication with a negative constant).

Vector scalar multiplication is denoted as
![c\\vec u](https://latex.codecogs.com/svg.format?c%5Cvec%20u "c\vec u")
where
![c \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?c%20%5Cin%20%5Cmathbb%7BR%7D "c \in \mathbb{R}").

<img src="../figures/linear_systems-vector_scalar_multiplication.svg" width="80%" style="display: block; margin: auto;" />

**Note:** The reverse of
![\\vec u](https://latex.codecogs.com/svg.format?%5Cvec%20u "\vec u") is
represented as
![-\\vec u](https://latex.codecogs.com/svg.format?-%5Cvec%20u "-\vec u").

# Vector addition

Two vectors with the same dimensions can be added entry-wise. This
produces a new vector with a new length and direction in
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m").

Vector addition is denoted as
![\\vec u + \\vec v = \\vec{(u+v)}](https://latex.codecogs.com/svg.format?%5Cvec%20u%20%2B%20%5Cvec%20v%20%3D%20%5Cvec%7B%28u%2Bv%29%7D "\vec u + \vec v = \vec{(u+v)}").
Geometrically, in a 2D plane, vector addition corresponds to the 4th
vertex of the parallelogram whose other vertices are
![\\vec 0, \\vec u,](https://latex.codecogs.com/svg.format?%5Cvec%200%2C%20%5Cvec%20u%2C "\vec 0, \vec u,")
and
![\\vec v](https://latex.codecogs.com/svg.format?%5Cvec%20v "\vec v").

<img src="../figures/linear_systems-vector_addition.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Vector subtraction is equivalent to the addition of a vector
scaled by -1
i.e. ![\\vec u - \\vec v = \\vec u + (-1)(\\vec v)](https://latex.codecogs.com/svg.format?%5Cvec%20u%20-%20%5Cvec%20v%20%3D%20%5Cvec%20u%20%2B%20%28-1%29%28%5Cvec%20v%29 "\vec u - \vec v = \vec u + (-1)(\vec v)").

# Vector span

Let vector
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b") be
the linear combination of
![c_1\\vec v_1 + c_2\\vec v_2 + \\cdots + c_p\\vec v_p](https://latex.codecogs.com/svg.format?c_1%5Cvec%20v_1%20%2B%20c_2%5Cvec%20v_2%20%2B%20%5Ccdots%20%2B%20c_p%5Cvec%20v_p "c_1\vec v_1 + c_2\vec v_2 + \cdots + c_p\vec v_p"),
where
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b")
has the dimensions
![m \\times 1](https://latex.codecogs.com/svg.format?m%20%5Ctimes%201 "m \times 1").
In other words, the constants
![c_1, c_2, \\cdots, c_p](https://latex.codecogs.com/svg.format?c_1%2C%20c_2%2C%20%5Ccdots%2C%20c_p "c_1, c_2, \cdots, c_p")
act as scalars of the base vectors
![\\vec v_1, \\vec v_2, \\cdots, \\vec v_p](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_p "\vec v_1, \vec v_2, \cdots, \vec v_p")
to form
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b").

We can also describe this by stating that
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b") is
in
![Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_p\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_p%5C%7D "Span\{\vec v_1, \vec v_2, \cdots, \vec v_p\}")
or in the subspace of
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
generated by
![\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_p\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_p%5C%7D "\{\vec v_1, \vec v_2, \cdots, \vec v_p\}").

<img src="../figures/linear_systems-vector_span.svg" width="80%" style="display: block; margin: auto;" />

We can therefore rewrite our linear system of equations
![A\\vec x = \\vec b](https://latex.codecogs.com/svg.format?A%5Cvec%20x%20%3D%20%5Cvec%20b "A\vec x = \vec b")
in the vector form
![x_1\\vec a_1 + x_2\\vec a_2 + \\cdots + x_n\\vec a_n = \\vec b](https://latex.codecogs.com/svg.format?x_1%5Cvec%20a_1%20%2B%20x_2%5Cvec%20a_2%20%2B%20%5Ccdots%20%2B%20x_n%5Cvec%20a_n%20%3D%20%5Cvec%20b "x_1\vec a_1 + x_2\vec a_2 + \cdots + x_n\vec a_n = \vec b").
This highlights that
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b")
can be generated by a linear combination of
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_n](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n "\vec a_1, \vec a_2, \cdots, \vec a_n")
as long as a solution to the linear system exists.

The set of linear combinations of
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_n](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n "\vec a_1, \vec a_2, \cdots, \vec a_n")
is called the subset of
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
generated or spanned by
![\\vec a_1, \\vec a_2, \\cdots, \\vec a_n](https://latex.codecogs.com/svg.format?%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n "\vec a_1, \vec a_2, \cdots, \vec a_n").
This is also written as
![Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}").

Asking whether
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b") is
in
![Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
is therefore equivalent to asking whether there is a consistent solution
to the linear system
![x_1\\vec a_1 + x_2\\vec a_2 + \\cdots + x_n\\vec a_n = \\vec b](https://latex.codecogs.com/svg.format?x_1%5Cvec%20a_1%20%2B%20x_2%5Cvec%20a_2%20%2B%20%5Ccdots%20%2B%20x_n%5Cvec%20a_n%20%3D%20%5Cvec%20b "x_1\vec a_1 + x_2\vec a_2 + \cdots + x_n\vec a_n = \vec b")
and then solving for the coefficients vector
![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
which scales
![Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
to form
![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b").

<img src="../figures/linear_systems-vector_span_examples.svg" width="80%" style="display: block; margin: auto;" />

**Note:** For homogeneous linear systems,
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0") is
always in
![Span\\{\\vec a_1, \\vec a_2, \\cdots, \\vec a_n\\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20a_1%2C%20%5Cvec%20a_2%2C%20%5Ccdots%2C%20%5Cvec%20a_n%5C%7D "Span\{\vec a_1, \vec a_2, \cdots, \vec a_n\}")
as
![x_1\\vec a_1 + x_2\\vec a_2 + \\cdots + x_n\\vec a_n = \\vec 0](https://latex.codecogs.com/svg.format?x_1%5Cvec%20a_1%20%2B%20x_2%5Cvec%20a_2%20%2B%20%5Ccdots%20%2B%20x_n%5Cvec%20a_n%20%3D%20%5Cvec%200 "x_1\vec a_1 + x_2\vec a_2 + \cdots + x_n\vec a_n = \vec 0")
for both the single trivial solution and for infinite solutions.

# Linear independence versus linear dependence

When a homogeneous linear system
![x_1\\vec a_1 + x_2\\vec a_2 + \\cdots + x_n\\vec a_n = \\vec 0](https://latex.codecogs.com/svg.format?x_1%5Cvec%20a_1%20%2B%20x_2%5Cvec%20a_2%20%2B%20%5Ccdots%20%2B%20x_n%5Cvec%20a_n%20%3D%20%5Cvec%200 "x_1\vec a_1 + x_2\vec a_2 + \cdots + x_n\vec a_n = \vec 0")
only has a single trivial solution
![x_1 = x_2 = \\cdots = x_n = 0](https://latex.codecogs.com/svg.format?x_1%20%3D%20x_2%20%3D%20%5Ccdots%20%3D%20x_n%20%3D%200 "x_1 = x_2 = \cdots = x_n = 0"),
we conclude that the vectors
![\\vec v_1, \\vec v_2, \\cdots, \\vec v_n](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n "\vec v_1, \vec v_2, \cdots, \vec v_n")
are linearly independent. The geometric intuition for this is that
![\\vec v_1, \\vec v_2, \\cdots, \\vec v_n](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n "\vec v_1, \vec v_2, \cdots, \vec v_n")
are not in the span of each other
i.e. ![\\vec v_i](https://latex.codecogs.com/svg.format?%5Cvec%20v_i "\vec v_i")
is not formed from a linear combination of the other vectors. As a
result, there is no scalar combination of one or more vectors which can
sum back to
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0").

When a homogeneous linear system has infinite solutions, we conclude
that the vectors
![\\vec v_1, \\vec v_2, \\cdots, \\vec v_n](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n "\vec v_1, \vec v_2, \cdots, \vec v_n")
are linearly dependent. The geometric intuition for this is that a
non-trivial linear combination of
![x_1\\vec v_1 + x_2\\vec v_2 + \\cdots + x_n\\vec v_n](https://latex.codecogs.com/svg.format?x_1%5Cvec%20v_1%20%2B%20x_2%5Cvec%20v_2%20%2B%20%5Ccdots%20%2B%20x_n%5Cvec%20v_n "x_1\vec v_1 + x_2\vec v_2 + \cdots + x_n\vec v_n")
exists which sums back to
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0").

Another way to describe linear dependence is to consider any set of
linearly independent vectors
![\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_n \| \\vec v \\in \\mathbb{R}^m\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n%20%7C%20%5Cvec%20v%20%5Cin%20%5Cmathbb%7BR%7D%5Em%5C%7D "\{\vec v_1, \vec v_2, \cdots, \vec v_n | \vec v \in \mathbb{R}^m\}").
Let a new vector
![\\vec w \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cvec%20w%20%5Cin%20%5Cmathbb%7BR%7D%5Em "\vec w \in \mathbb{R}^m")
be any vector that is not in the set of the linearly independent
vectors. The set
![\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_n, \\vec w\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n%2C%20%5Cvec%20w%5C%7D "\{\vec v_1, \vec v_2, \cdots, \vec v_n, \vec w\}")
is only linearly dependent if
![\\vec w \\in Span\\{\\vec v_1, \\vec v_2, \\cdots, \\vec v_n\\}](https://latex.codecogs.com/svg.format?%5Cvec%20w%20%5Cin%20Span%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Ccdots%2C%20%5Cvec%20v_n%5C%7D "\vec w \in Span\{\vec v_1, \vec v_2, \cdots, \vec v_n\}").

<img src="../figures/linear_systems-linear_dependence_b.svg" width="80%" style="display: block; margin: auto;" />

We can also use the properties of linear independence to prove that
every matrix A only has one reduced echelon form. Matrix A, B and C are
equivalent if a finite sequence of elementary row operations (EROs)
exists which transforms A to B and A to C. Therefore, we can prove that
a finite sequence of EROs also exist which transforms B to C and that B
and C are row equivalent.

If matrix B and C are row equivalent, their columns must be in the same
span and satisfy the same linear dependence equations. Therefore B and C
must contain the same number of pivot columns.

<img src="../figures/linear_systems-reduced_echelon_form_proof.svg" width="80%" style="display: block; margin: auto;" />

-   Any pivot columns in a reduced echelon form matrix cannot be written
    as a linear combination of all pivot columns to its left.  
-   Any non-pivot columns in a reduced echelon form matrix can be
    written using a unique linear combination of all pivot columns to
    its left.

As the columns of B and C must satisfy the same linear dependence
equations, the pivot columns of the reduced echelon form of B and C must
be identical and the non-pivot columns of the reduced echelon form of B
and C must also be identical. Therefore B and C have the same reduced
echelon form.

**Note:** A set of three linearly independent vectors with dimensions
![3 \\times 1](https://latex.codecogs.com/svg.format?3%20%5Ctimes%201 "3 \times 1")
will span 3D space. A set of two linearly independent vectors with
dimensions
![3 \\times 1](https://latex.codecogs.com/svg.format?3%20%5Ctimes%201 "3 \times 1")
will span a 2D plane in 3D. A single vector with dimensions
![3 \\times 1](https://latex.codecogs.com/svg.format?3%20%5Ctimes%201 "3 \times 1")
will span a 1D line in 3D.

**Note:** Therefore, a set of two or more vectors
![\\{\\vec v_1, \\cdots, \\vec v_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%5C%7D "\{\vec v_1, \cdots, \vec v_n\}")
is linearly independent if removing a vector decreases the span of the
vector set. A set of linearly independent vectors can also be extended
to form a larger set of linearly independent vectors if the new vector
is not in the span of the original set.

# Vector subspaces

A vector subspace is simply a closed vector space that exists inside a
larger closed vector space. For example, the span of vectors
![\\{\\vec v_1, \\vec v_2, \\vec v_3\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Cvec%20v_3%5C%7D "\{\vec v_1, \vec v_2, \vec v_3\}"),
represented as subset ![H](https://latex.codecogs.com/svg.format?H "H"),
is only a vector subspace inside
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
if the following properties are true:

-   The vectors
    ![\\vec v_1, \\vec v_2, \\vec v_3](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Cvec%20v_3 "\vec v_1, \vec v_2, \vec v_3")
    each have dimensions
    ![n \\times 1](https://latex.codecogs.com/svg.format?n%20%5Ctimes%201 "n \times 1").  
-   ![Span(\\vec v_1, \\vec v_2, \\vec v_3)](https://latex.codecogs.com/svg.format?Span%28%5Cvec%20v_1%2C%20%5Cvec%20v_2%2C%20%5Cvec%20v_3%29 "Span(\vec v_1, \vec v_2, \vec v_3)")
    contains the zero vector
    ![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0").  
-   If vectors
    ![\\vec v_1, \\vec v_2](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%2C%20%5Cvec%20v_2 "\vec v_1, \vec v_2")
    are in the subspace, so is
    ![\\vec v_1 + \\vec v_2](https://latex.codecogs.com/svg.format?%5Cvec%20v_1%20%2B%20%5Cvec%20v_2 "\vec v_1 + \vec v_2").
    This is also known as being closed under vector addition.  
-   If vector
    ![\\vec v_1](https://latex.codecogs.com/svg.format?%5Cvec%20v_1 "\vec v_1")
    is in the subspace, so is
    ![c \\vec v_1](https://latex.codecogs.com/svg.format?c%20%5Cvec%20v_1 "c \vec v_1")
    where
    ![c \\in \\mathbb{R}](https://latex.codecogs.com/svg.format?c%20%5Cin%20%5Cmathbb%7BR%7D "c \in \mathbb{R}").
    This is also known as being closed under scalar multiplication.

As a result, any subspace of
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
is also the span of a finite set of vectors
![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}").

<img src="../figures/linear_systems-vector_subspaces.svg" width="80%" style="display: block; margin: auto;" />

# Basis vectors

We can describe a subspace of
![\\mathbb{R}^{n}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E%7Bn%7D "\mathbb{R}^{n}")
as the span of a set of vectors
![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}").
Defining a vector subspace allows us to define the search space for an
optimal solution to a linear system.

For any vector
![\\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20w "\vec w") in
![Span\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?Span%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "Span\{\vec v_1, \cdots, \vec v_p \}"),
a unique list of scalars
![c_1, \\cdots, c_p](https://latex.codecogs.com/svg.format?c_1%2C%20%5Ccdots%2C%20c_p "c_1, \cdots, c_p")
exists such that
![c_1 \\vec v_1 + \\cdots + c_p \\vec v_p = \\vec w](https://latex.codecogs.com/svg.format?c_1%20%5Cvec%20v_1%20%2B%20%5Ccdots%20%2B%20c_p%20%5Cvec%20v_p%20%3D%20%5Cvec%20w "c_1 \vec v_1 + \cdots + c_p \vec v_p = \vec w").

A set of vectors are the **basis vectors** or **a basis** for subspace H
if:

-   The set of vectors
    ![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}")
    are linearly independent.  
-   The set of vectors
    ![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}")
    span subspace H.  
-   This means that the number of basis vectors for subspace H
    determines the dimensions of subspace H itself.

<img src="../figures/linear_systems-basis_vectors.svg" width="80%" style="display: block; margin: auto;" />

Geometrically, we can think of basis vectors as the unit vectors of the
coordinate grid of subspace H.

<img src="../figures/linear_systems-basis_vector_examples.svg" width="80%" style="display: block; margin: auto;" />

The set
![\\epsilon_n = \\{\\vec e_1, \\vec e_2, \\cdots, \\vec e_n\\}](https://latex.codecogs.com/svg.format?%5Cepsilon_n%20%3D%20%5C%7B%5Cvec%20e_1%2C%20%5Cvec%20e_2%2C%20%5Ccdots%2C%20%5Cvec%20e_n%5C%7D "\epsilon_n = \{\vec e_1, \vec e_2, \cdots, \vec e_n\}")
is called the standard basis for
![\\mathbb{R}^{n}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5E%7Bn%7D "\mathbb{R}^{n}")
where
![\\vec e_1 = \\begin{bmatrix}1\\\\0\\\\\\vdots\\\\0\\end{bmatrix}](https://latex.codecogs.com/svg.format?%5Cvec%20e_1%20%3D%20%5Cbegin%7Bbmatrix%7D1%5C%5C0%5C%5C%5Cvdots%5C%5C0%5Cend%7Bbmatrix%7D "\vec e_1 = \begin{bmatrix}1\\0\\\vdots\\0\end{bmatrix}").

As basis vectors are a set of linearly independent vectors, they are
equivalent to the pivot columns of a coefficient matrix
![A = \\begin{bmatrix} \\vec a_1 & \\vec a_2 & \\cdots & \\vec a_n \\end{bmatrix}](https://latex.codecogs.com/svg.format?A%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cvec%20a_1%20%26%20%5Cvec%20a_2%20%26%20%5Ccdots%20%26%20%5Cvec%20a_n%20%5Cend%7Bbmatrix%7D "A = \begin{bmatrix} \vec a_1 & \vec a_2 & \cdots & \vec a_n \end{bmatrix}").

If we reduce matrix A into its echelon form i.e. to matrix B, the
position of the pivot columns in matrix B are equivalent to the position
of pivot columns in matrix A and can be used to locate the basis vectors
in matrix A.

<img src="../figures/linear_systems-locating_basis_vectors.svg" width="80%" style="display: block; margin: auto;" />

**Note:** If
![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}")
span subspace H,
![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}")
can be either linearly independent or linearly dependent. However, if
![{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "{\vec v_1, \cdots, \vec v_p \}")
are basis vectors (or are a basis) for subspace H, then
![{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "{\vec v_1, \cdots, \vec v_p \}")
must be linearly independent.

**Note:** For a linearly dependent set of vectors, the number of basis
vectors corresponds to the number of columns in the coefficient matrix A
that contain a pivot column. Therefore for a linearly dependent set of
vectors, the number of basis vectors is always less than the number of
column vectors in A.

# Coordinate systems

Let
![\\mathcal{B} = \\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5Cmathcal%7BB%7D%20%3D%20%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\mathcal{B} = \{\vec v_1, \cdots, \vec v_p \}")
be a basis for subspace H. This means that every vector
![\\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20w "\vec w") in
subspace H can be formed from one unique linear combination of
![\\{\\vec v_1, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_p \}")
i.e. ![\\vec w = c_1\\vec v_1 + \\cdots + c_p \\vec v_p](https://latex.codecogs.com/svg.format?%5Cvec%20w%20%3D%20c_1%5Cvec%20v_1%20%2B%20%5Ccdots%20%2B%20c_p%20%5Cvec%20v_p "\vec w = c_1\vec v_1 + \cdots + c_p \vec v_p").

The unique list of scalars
![\\{c_1, \\cdots, c_p\\}](https://latex.codecogs.com/svg.format?%5C%7Bc_1%2C%20%5Ccdots%2C%20c_p%5C%7D "\{c_1, \cdots, c_p\}")
therefore acts as the list of coordinates of
![\\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20w "\vec w")
with respect to the basis vectors
![\\mathcal{B}](https://latex.codecogs.com/svg.format?%5Cmathcal%7BB%7D "\mathcal{B}").

<img src="../figures/linear_systems-coordinates.svg" width="80%" style="display: block; margin: auto;" />

**Note:** The unique list of coordinates used to generate
![\\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20w "\vec w")
with respect to
![\\mathcal{B}](https://latex.codecogs.com/svg.format?%5Cmathcal%7BB%7D "\mathcal{B}")
can be written as the coordinate vector
![\\begin{bmatrix}c_1\\\\\\vdots\\\\c_p\\end{bmatrix}\_\\mathcal{B}](https://latex.codecogs.com/svg.format?%5Cbegin%7Bbmatrix%7Dc_1%5C%5C%5Cvdots%5C%5Cc_p%5Cend%7Bbmatrix%7D_%5Cmathcal%7BB%7D "\begin{bmatrix}c_1\\\vdots\\c_p\end{bmatrix}_\mathcal{B}").

# Resources

-   A great [YouTube
    series](https://www.youtube.com/watch?v=fNk_zzaMoSs) on vectors by
    3Blue1Brown.  
-   A [YouTube series](https://www.youtube.com/watch?v=tM4TDL9Hj8U) on
    vectors by Professor Dave Explains.
