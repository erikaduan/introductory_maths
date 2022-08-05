Introduction to vectors
================
Erika Duan
2022-08-05

-   [Vectors](#vectors)
-   [Vector scalar multiplication](#vector-scalar-multiplication)
-   [Vector addition](#vector-addition)
-   [Vector span](#vector-span)
-   [Resources](#resources)

# Vectors

Vectors are an important form used to convey object position in
dimensional space and vector operations enable us to transform vectors
in useful ways.

A column vector
![\\vec u](https://latex.codecogs.com/svg.format?%5Cvec%20u "\vec u") is
an
![m\\times1](https://latex.codecogs.com/svg.format?m%5Ctimes1 "m\times1")
matrix where
![\\vec u\\in \\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cvec%20u%5Cin%20%5Cmathbb%7BR%7D%5Em "\vec u\in \mathbb{R}^m").
Two vectors are equal if they have the same number of rows and their
corresponding entries are equal.

**Note:** Do not confuse the zero vector
![\\vec 0](https://latex.codecogs.com/svg.format?%5Cvec%200 "\vec 0") as
a scalar 0 during vector operations.

<img src="../figures/linear_systems-vectors.svg" width="80%" style="display: block; margin: auto;" />

Key vector operations are:

-   Scalar multiplication - when a vector is scaled by a constant.  
-   Vector addition - when two vectors of the same dimensions are added
    to form a new vector (with a new length and direction).  
-   Vector multiplication - used to calculate how far apart two vectors
    are, with respect to the origin, by superimposing one along the axis
    of the other.

# Vector scalar multiplication

Vector scalar multiplication is used to scale the length of the vector
and/or to change its direction (i.e. vector direction can also be
reversed by multiplication of a negative constant).

Vector scalar multiplication is denoted as
![c\\vec u](https://latex.codecogs.com/svg.format?c%5Cvec%20u "c\vec u")
where
![c\\in\\mathbb{R}](https://latex.codecogs.com/svg.format?c%5Cin%5Cmathbb%7BR%7D "c\in\mathbb{R}").

<img src="../figures/linear_systems-vector_scalar_multiplication.svg" width="80%" style="display: block; margin: auto;" />

**Note:** The reverse of
![\\vec u](https://latex.codecogs.com/svg.format?%5Cvec%20u "\vec u") is
denoted as
![-\\vec {u}](https://latex.codecogs.com/svg.format?-%5Cvec%20%7Bu%7D "-\vec {u}").

# Vector addition

Two vectors of the same dimension can be added entry-wise. This produces
a new vector with a new length and direction in dimensional space.

Vector addition is denoted as
![\\vec u + \\vec v = \\vec{(u+v)}](https://latex.codecogs.com/svg.format?%5Cvec%20u%20%2B%20%5Cvec%20v%20%3D%20%5Cvec%7B%28u%2Bv%29%7D "\vec u + \vec v = \vec{(u+v)}").
Geometrically, in 2D space, vector addition corresponds to the 4th
vertex of the parallelogram whose other vertices are
![\\vec 0, \\vec u,](https://latex.codecogs.com/svg.format?%5Cvec%200%2C%20%5Cvec%20u%2C "\vec 0, \vec u,")
and
![\\vec v](https://latex.codecogs.com/svg.format?%5Cvec%20v "\vec v").

<img src="../figures/linear_systems-vector_addition.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Vector subtraction is equivalent to the addition of a vector
scaled by -1
i.e. ![\\vec u - \\vec v = \\vec u + (-1)(\\vec v)](https://latex.codecogs.com/svg.format?%5Cvec%20u%20-%20%5Cvec%20v%20%3D%20%5Cvec%20u%20%2B%20%28-1%29%28%5Cvec%20v%29 "\vec u - \vec v = \vec u + (-1)(\vec v)").

# Vector span

# Resources

-   A great [YouTube
    series](https://www.youtube.com/watch?v=fNk_zzaMoSs) on vectors by
    3Blue1Brown.
