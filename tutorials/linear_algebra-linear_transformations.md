Linear transformations
================
Erika Duan
2022-09-16

-   [Vector transformation notation](#vector-transformation-notation)
-   [Linear transformation
    compositions](#linear-transformation-compositions)
-   [Injective linear
    transformations](#injective-linear-transformations)
-   [Surjective linear
    transformations](#surjective-linear-transformations)
-   [Bijective linear
    transformations](#bijective-linear-transformations)
-   [Resources](#resources)

# Vector transformation notation

A key focus of linear algebra is the linear transformations of vector
spaces.

A linear transformation can be described as:

-   A function that maps a vector
    ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
    in
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
    to a vector
    ![\\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20w "\vec w")
    in
    ![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m"),
    where
    ![T(\\vec x) = \\vec w](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20%5Cvec%20w "T(\vec x) = \vec w").  
-   This is denoted by
    ![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
    respectively.  
-   The domain of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    is
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   The co-domain of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    can be
    ![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
    respectively.  
-   The image of
    ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x")
    under T is the set
    ![\\{\\vec w \\in \\mathbb{R}^m \| \\vec w = T(\\vec x)\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20w%20%5Cin%20%5Cmathbb%7BR%7D%5Em%20%7C%20%5Cvec%20w%20%3D%20T%28%5Cvec%20x%29%5C%7D "\{\vec w \in \mathbb{R}^m | \vec w = T(\vec x)\}")
    where
    ![\\vec x \\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En "\vec x \in \mathbb{R}^n").  
-   The range of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    also describes the set
    ![\\{\\vec w \\in \\mathbb{R}^m \| \\vec w = T(\\vec x)\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20w%20%5Cin%20%5Cmathbb%7BR%7D%5Em%20%7C%20%5Cvec%20w%20%3D%20T%28%5Cvec%20x%29%5C%7D "\{\vec w \in \mathbb{R}^m | \vec w = T(\vec x)\}")
    where
    ![\\vec x \\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%5Cin%20%5Cmathbb%7BR%7D%5En "\vec x \in \mathbb{R}^n").

<img src="../figures/linear_systems-linear_transformation_notation.svg" width="80%" style="display: block; margin: auto;" />

A linear transformation can also be described as a matrix
transformation, where
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") is the standard
matrix for the linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
and
![T(\\vec x) = A\\vec x](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20A%5Cvec%20x "T(\vec x) = A\vec x")
where
![A_T = \\begin{bmatrix}T(\\vec e_1) & T(\\vec e_2) & \\cdots & T(\\vec e_n) \\end{bmatrix}](https://latex.codecogs.com/svg.format?A_T%20%3D%20%5Cbegin%7Bbmatrix%7DT%28%5Cvec%20e_1%29%20%26%20T%28%5Cvec%20e_2%29%20%26%20%5Ccdots%20%26%20T%28%5Cvec%20e_n%29%20%5Cend%7Bbmatrix%7D "A_T = \begin{bmatrix}T(\vec e_1) & T(\vec e_2) & \cdots & T(\vec e_n) \end{bmatrix}").

<img src="../figures/linear_systems-standard_matrix.svg" width="80%" style="display: block; margin: auto;" />

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
must satisfy the following two properties:

-   For vectors
    ![\\vec u, \\vec v \\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cvec%20u%2C%20%5Cvec%20v%20%5Cin%20%5Cmathbb%7BR%7D%5En "\vec u, \vec v \in \mathbb{R}^n"),
    ![T(\\vec u + \\vec v) = T(\\vec u) + T(\\vec v)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20u%20%2B%20%5Cvec%20v%29%20%3D%20T%28%5Cvec%20u%29%20%2B%20T%28%5Cvec%20v%29 "T(\vec u + \vec v) = T(\vec u) + T(\vec v)").  
-   Let ![c](https://latex.codecogs.com/svg.format?c "c") be a scalar,
    ![T(c \\vec u) = cT(\\vec u)](https://latex.codecogs.com/svg.format?T%28c%20%5Cvec%20u%29%20%3D%20cT%28%5Cvec%20u%29 "T(c \vec u) = cT(\vec u)").

Examples of linear transformations include projections onto lower
dimensions, sheering transformations, scaling transformations and
rotations around the point of origin.

<img src="../figures/linear_systems-linear_transformation_examples.svg" width="80%" style="display: block; margin: auto;" />

# Linear transformation compositions

If function
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") maps
element A to B and function
![g(x)](https://latex.codecogs.com/svg.format?g%28x%29 "g(x)") maps
element B to C, then the composition of f then g, denoted as
![g \\circ f](https://latex.codecogs.com/svg.format?g%20%5Ccirc%20f "g \circ f"),
is the function which maps element A to C and
![(g \\circ f)(a) = g(f(a))](https://latex.codecogs.com/svg.format?%28g%20%5Ccirc%20f%29%28a%29%20%3D%20g%28f%28a%29%29 "(g \circ f)(a) = g(f(a))").

Similarly, if
![T_1: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T_1%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T_1: \mathbb{R}^n \to \mathbb{R}^m")
and
![T_2: \\mathbb{R}^m \\to \\mathbb{R}^p](https://latex.codecogs.com/svg.format?T_2%3A%20%5Cmathbb%7BR%7D%5Em%20%5Cto%20%5Cmathbb%7BR%7D%5Ep "T_2: \mathbb{R}^m \to \mathbb{R}^p"),
the co-domain of ![T_1](https://latex.codecogs.com/svg.format?T_1 "T_1")
equals the domain of
![T_2](https://latex.codecogs.com/svg.format?T_2 "T_2") and the
composition
![T_2 \\circ T_1](https://latex.codecogs.com/svg.format?T_2%20%5Ccirc%20T_1 "T_2 \circ T_1")
maps
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
to
![\\mathbb{R}^p](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Ep "\mathbb{R}^p").

The linear transformation composition
![T_2 \\circ T_1](https://latex.codecogs.com/svg.format?T_2%20%5Ccirc%20T_1 "T_2 \circ T_1")
also satisfies the following two properties:

-   ![(T_2 \\circ T_1)(\\vec u + \\vec v) = T_2(T_1(\\vec u + \\vec v)) = \\cdots = (T_2 \\circ T_1)(\\vec u) + (T_2 \\circ T_1)(\\vec v)](https://latex.codecogs.com/svg.format?%28T_2%20%5Ccirc%20T_1%29%28%5Cvec%20u%20%2B%20%5Cvec%20v%29%20%3D%20T_2%28T_1%28%5Cvec%20u%20%2B%20%5Cvec%20v%29%29%20%3D%20%5Ccdots%20%3D%20%28T_2%20%5Ccirc%20T_1%29%28%5Cvec%20u%29%20%2B%20%28T_2%20%5Ccirc%20T_1%29%28%5Cvec%20v%29 "(T_2 \circ T_1)(\vec u + \vec v) = T_2(T_1(\vec u + \vec v)) = \cdots = (T_2 \circ T_1)(\vec u) + (T_2 \circ T_1)(\vec v)").  
-   ![(T_2 \\circ T_1)(c\\vec u) = T_2(T_1(c\\vec u) = T_2(cT_1(\\vec u) = cT_2(T_1(\\vec u) = c(T_2 \\circ T_1)(\\vec u)](https://latex.codecogs.com/svg.format?%28T_2%20%5Ccirc%20T_1%29%28c%5Cvec%20u%29%20%3D%20T_2%28T_1%28c%5Cvec%20u%29%20%3D%20T_2%28cT_1%28%5Cvec%20u%29%20%3D%20cT_2%28T_1%28%5Cvec%20u%29%20%3D%20c%28T_2%20%5Ccirc%20T_1%29%28%5Cvec%20u%29 "(T_2 \circ T_1)(c\vec u) = T_2(T_1(c\vec u) = T_2(cT_1(\vec u) = cT_2(T_1(\vec u) = c(T_2 \circ T_1)(\vec u)").

<img src="../figures/linear_systems-matrix_composition.svg" width="80%" style="display: block; margin: auto;" />

**Note:** In the example above, even though the sequence of
transformations
![(T_2 \\circ T_1)(\\vec x)](https://latex.codecogs.com/svg.format?%28T_2%20%5Ccirc%20T_1%29%28%5Cvec%20x%29 "(T_2 \circ T_1)(\vec x)")
and
![(T_1 \\circ T_2)(\\vec x)](https://latex.codecogs.com/svg.format?%28T_1%20%5Ccirc%20T_2%29%28%5Cvec%20x%29 "(T_1 \circ T_2)(\vec x)")
produce the same grid lines in the 2D plane, the position of the basis
vectors
![\\hat i](https://latex.codecogs.com/svg.format?%5Chat%20i "\hat i")
and
![\\hat j](https://latex.codecogs.com/svg.format?%5Chat%20j "\hat j")
are different.

# Injective linear transformations

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
is injective (or one-to-one) if:

-   Every vector
    ![\\vec b \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cvec%20b%20%5Cin%20%5Cmathbb%7BR%7D%5Em "\vec b \in \mathbb{R}^m")
    is the image of at most one vector
    ![\\vec x in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cvec%20x%20in%20%5Cmathbb%7BR%7D%5En "\vec x in \mathbb{R}^n").  
-   Different vectors
    ![\\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5En "\in \mathbb{R}^n")
    have different images in
    ![\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5Em "\in \mathbb{R}^m").  
-   If
    ![T(\\vec u) = T(\\vec v)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20u%29%20%3D%20T%28%5Cvec%20v%29 "T(\vec u) = T(\vec v)"),
    then
    ![\\vec u = \\vec v](https://latex.codecogs.com/svg.format?%5Cvec%20u%20%3D%20%5Cvec%20v "\vec u = \vec v").

Another way of thinking about this is that
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") must contain a
set of independent vectors
![\\{\\vec v_1, \\cdots, \\vec v_p\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%5C%7D "\{\vec v_1, \cdots, \vec v_p\}")
which spans a p-dimensional space in
![\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5Em "\in \mathbb{R}^m").
Therefore a unique set of coordinates
![\\{c_1, \\cdots, c_p \\}](https://latex.codecogs.com/svg.format?%5C%7Bc_1%2C%20%5Ccdots%2C%20c_p%20%5C%7D "\{c_1, \cdots, c_p \}")
must exist which scales
![\\{\\vec v_1, \\cdots, \\vec v_p\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_p%5C%7D "\{\vec v_1, \cdots, \vec v_p\}")
to form
![T(\\vec x) = \\vec b](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20%5Cvec%20b "T(\vec x) = \vec b")
and
![T(\\vec x) = \\vec 0](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20%5Cvec%200 "T(\vec x) = \vec 0")
only contains the trivial solution.

<img src="../figures/linear_systems-injective_transformations.svg" width="80%" style="display: block; margin: auto;" />

By extension, a linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n")
is only injective if
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") contains a basis
for
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
i.e. a set of independent vectors
![\\{\\vec v_1, \\cdots, \\vec v_n\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%5C%7D "\{\vec v_1, \cdots, \vec v_n\}")
which span
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").
The matrix rank, or dimensions of
![ColA](https://latex.codecogs.com/svg.format?ColA "ColA"), must be
![n](https://latex.codecogs.com/svg.format?n "n") for
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") to be injective
when
![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n").

# Surjective linear transformations

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
is surjective (or onto) if:

-   The range of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)"),
    ![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b"),
    spans
    ![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
    for
    ![T(\\vec x) = \\vec b](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20%5Cvec%20b "T(\vec x) = \vec b").  
-   The equation
    ![A(\\vec x) = \\vec b](https://latex.codecogs.com/svg.format?A%28%5Cvec%20x%29%20%3D%20%5Cvec%20b "A(\vec x) = \vec b")
    has a solution for all
    ![\\vec b \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cvec%20b%20%5Cin%20%5Cmathbb%7BR%7D%5Em "\vec b \in \mathbb{R}^m").  
-   The column space of A must span the co-domain
    ![\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5Em "\in \mathbb{R}^m")
    i.e. the dimensions of the basis for
    ![ColA](https://latex.codecogs.com/svg.format?ColA "ColA") must be
    ![m](https://latex.codecogs.com/svg.format?m "m").

Another way of thinking about this is that
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") must span
![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
i.e. the range and co-domain of
![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
must both be
![\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cin%20%5Cmathbb%7BR%7D%5Em "\in \mathbb{R}^m").
By definition,
![A_T \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?A_T%20%5Cin%20%5Cmathbb%7BR%7D%5Em "A_T \in \mathbb{R}^m")
if it contains a set of linearly independent vectors
![\\{\\vec v_1, \\cdots, \\vec v_m\\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_m%5C%7D "\{\vec v_1, \cdots, \vec v_m\}").
Therefore,
![ColA \\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?ColA%20%5Cin%20%5Cmathbb%7BR%7D%5Em "ColA \in \mathbb{R}^m")
for a surjective linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m").

**Note:** The set of vectors
![\\{\\vec v_1, \\cdots, \\vec v_m, \\cdots, \\vec v_p \\}](https://latex.codecogs.com/svg.format?%5C%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_m%2C%20%5Ccdots%2C%20%5Cvec%20v_p%20%5C%7D "\{\vec v_1, \cdots, \vec v_m, \cdots, \vec v_p \}")
in ![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") does not need
to be linearly independent for surjective linear transformations where
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m").

<img src="../figures/linear_systems-surjective_transformations.svg" width="80%" style="display: block; margin: auto;" />

By extension, a linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n")
is only surjective if
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") contains a basis
for
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
i.e. the image of
![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
is also in
![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").

# Bijective linear transformations

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n")
is therefore bijective (one-to-one and unto) if:

-   ![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") contains a
    linearly independent set of vectors
    ![{\\vec v_1, \\cdots, \\vec v_n}](https://latex.codecogs.com/svg.format?%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%7D "{\vec v_1, \cdots, \vec v_n}")
    and a unique set of coordinates scales
    ![{\\vec v_1, \\cdots, \\vec v_n}](https://latex.codecogs.com/svg.format?%7B%5Cvec%20v_1%2C%20%5Ccdots%2C%20%5Cvec%20v_n%7D "{\vec v_1, \cdots, \vec v_n}")
    to form a different
    ![\\vec b](https://latex.codecogs.com/svg.format?%5Cvec%20b "\vec b")
    for each unique
    ![\\vec x](https://latex.codecogs.com/svg.format?%5Cvec%20x "\vec x"),
    where
    ![T(\\vec x) = \\vec b](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29%20%3D%20%5Cvec%20b "T(\vec x) = \vec b").  
-   As ![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") contains
    a basis with n dimensions, the range of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    is therefore equal to the co-domain
    i.e. ![A_T \\in \\mathbb{R}^n](https://latex.codecogs.com/svg.format?A_T%20%5Cin%20%5Cmathbb%7BR%7D%5En "A_T \in \mathbb{R}^n").

Bijective linear transformations are an example of the rank and nullity
theorem.

Given a bijective linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n")
where ![A_T](https://latex.codecogs.com/svg.format?A_T "A_T") has
dimensions
![n \\times n](https://latex.codecogs.com/svg.format?n%20%5Ctimes%20n "n \times n"),
the rank of ![T](https://latex.codecogs.com/svg.format?T "T") is the
column space of ![A_T](https://latex.codecogs.com/svg.format?A_T "A_T"),
which is n. The nullity of
![T](https://latex.codecogs.com/svg.format?T "T") is the null space of
![A_T](https://latex.codecogs.com/svg.format?A_T "A_T"), which is 0.
![Rank\\,T + Nullity\\,T = n + 0 = n](https://latex.codecogs.com/svg.format?Rank%5C%2CT%20%2B%20Nullity%5C%2CT%20%3D%20n%20%2B%200%20%3D%20n "Rank\,T + Nullity\,T = n + 0 = n").

<img src="../figures/linear_systems-bijective_transformations.svg" width="80%" style="display: block; margin: auto;" />

# Resources

-   Great YouTube videos on
    [2D](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3)
    and
    [3D](https://www.youtube.com/watch?v=rHLEWRxRGiM&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=5)
    linear transformations by 3Blue1Brown.
