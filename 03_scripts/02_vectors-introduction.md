Introduction to vectors
================
Erika Duan
2020-12-27

  - [Resources](#resources)
  - [What is a vector?](#what-is-a-vector)
  - [Special vectors](#special-vectors)
  - [Vector dimensions and the coordinate
    system](#vector-dimensions-and-the-coordinate-system)
  - [Basic vector operations](#basic-vector-operations)

# Resources

This section on mathematical sets is taken from [Introduction to Linear
Algebra for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#vectors) by
Pablo Caceres. All credit should be attributed to Pablo Caceres.

# What is a vector?

A vector is a ordered and finite list of numbers (i.e. not character
elements) and can be viewed as the most basic object in machine
learning.  
Vectors can have any number of dimensions and are mathematical objects
that can be added or multipled i.e. transformed into another vector.

Different types of vectors exist:

  - Geometrical vectors - lines with directions.  
  - [Polynomials](https://www.mathsisfun.com/algebra/polynomials.html) -
    an algebraic expression that has multiple terms (constants,
    variables and exponents) like ![f(x) =
    x^{2}+y+1](https://latex.codecogs.com/png.latex?f%28x%29%20%3D%20x%5E%7B2%7D%2By%2B1
    "f(x) = x^{2}+y+1").  
  - Elements of space ![{\\rm
    I\\\!R}^{n}](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E%7Bn%7D
    "{\\rm I\\!R}^{n}") - sets of real numbers. A vector in ![{\\rm
    I\\\!R}^{3}](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E%7B3%7D
    "{\\rm I\\!R}^{3}") has the shape below.  
    ![x = \\begin{bmatrix} x\_1 \\\\ x\_2 \\\\ x\_3 \\end{bmatrix} \\in
    {\\rm
    I\\\!R}^{3}](https://latex.codecogs.com/png.latex?x%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20x_1%20%5C%5C%20x_2%20%5C%5C%20x_3%20%20%5Cend%7Bbmatrix%7D%20%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5E%7B3%7D
    "x =  \\begin{bmatrix} x_1 \\\\ x_2 \\\\ x_3  \\end{bmatrix}  \\in {\\rm I\\!R}^{3}")

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/02_figures/02_vector-types.jpg)

``` python
#-----create 1 dimensional vector via Numpy array-----
import numpy as np 

x = np.array([np.arange(1, 10+1)])
x.shape
#> (1, 10) 
```

``` python
#-----create 3-dimensional vector via Numpy array-----
# note the placement of double square brackets [[y1],[y2],[y3]]

y = np.array([[1, 2, 3],
              [4, 5, 6],
              [7, 8, 9]])  
y.shape   
#> (3, 3)  
```

# Special vectors

Special vectors include:

  - Zero vectors - a vector which is only composed of zeros.  
    ![x = \\begin{bmatrix} 0 \\\\ 0 \\\\ 0
    \\end{bmatrix}](https://latex.codecogs.com/png.latex?x%20%3D%20%20%5Cbegin%7Bbmatrix%7D%200%20%5C%5C%200%20%5C%5C%200%20%20%5Cend%7Bbmatrix%7D
    "x =  \\begin{bmatrix} 0 \\\\ 0 \\\\ 0  \\end{bmatrix}")  
  - Unit vectors - a vector containing a single element of 1 with
    remaining elements of zero. Useful for reducing the dimensions of a
    vector.  
    ![y = \\begin{bmatrix} 1 \\\\ 0 \\\\ 0
    \\end{bmatrix}](https://latex.codecogs.com/png.latex?y%20%3D%20%20%5Cbegin%7Bbmatrix%7D%201%20%5C%5C%200%20%5C%5C%200%20%20%5Cend%7Bbmatrix%7D
    "y =  \\begin{bmatrix} 1 \\\\ 0 \\\\ 0  \\end{bmatrix}")  
  - Sparse vectors - sparse vectors predominantly contain elements of
    zero. To maximise computational efficiency, we can represent sparse
    matrices by storing only its non-zero elements in a `[[row],
    [column], [value]]` triplet array.  
    ![y = \\begin{bmatrix} 0, 0, 3, 0, 0, 0 \\\\ 0, 0, 0, 0, 0, 0
    \\\\ 0, 0, 0, 0, 1, 0 \\end{bmatrix} y\_{sparse} =
    \\begin{bmatrix} 0, 2, 3 \\\\ 2, 4, 1
    \\end{bmatrix}](https://latex.codecogs.com/png.latex?y%20%3D%20%20%5Cbegin%7Bbmatrix%7D%200%2C%200%2C%203%2C%200%2C%200%2C%200%20%5C%5C%200%2C%200%2C%200%2C%200%2C%200%2C%200%20%5C%5C%200%2C%200%2C%200%2C%200%2C%201%2C%200%20%20%5Cend%7Bbmatrix%7D%20%20y_%7Bsparse%7D%20%3D%20%20%5Cbegin%7Bbmatrix%7D%200%2C%202%2C%203%20%5C%5C%202%2C%204%2C%201%20%20%5Cend%7Bbmatrix%7D
    "y =  \\begin{bmatrix} 0, 0, 3, 0, 0, 0 \\\\ 0, 0, 0, 0, 0, 0 \\\\ 0, 0, 0, 0, 1, 0  \\end{bmatrix}  y_{sparse} =  \\begin{bmatrix} 0, 2, 3 \\\\ 2, 4, 1  \\end{bmatrix}")

# Vector dimensions and the coordinate system

Vectors can have any number of dimensions. During our studies, we tend
to encounter the 2-dimensional cartesian plane and 3-dimensional space,
as these can be visualised as geometric vectors. In machine learning,
however, we encounter problems involving tens, hundreds or even
thousands of dimensions.

The notation of a vector `x` of `n` dimensions is written below.  
![x = \\begin{bmatrix} x\_1 \\\\ x\_2 \\\\ \\vdots \\\\ x\_n
\\end{bmatrix} \\in {\\rm
I\\\!R}^{n}](https://latex.codecogs.com/png.latex?x%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20%20x_1%20%5C%5C%20%20x_2%20%5C%5C%20%20%5Cvdots%20%5C%5C%20%20x_n%20%20%5Cend%7Bbmatrix%7D%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5E%7Bn%7D
"x =  \\begin{bmatrix}  x_1 \\\\  x_2 \\\\  \\vdots \\\\  x_n  \\end{bmatrix} \\in {\\rm I\\!R}^{n}")

Vector dimensions map into coordinate systems, which have an origin at
(0, 0, …, 0).  
![x = \\begin{bmatrix} 1 \\\\ 2 \\\\ 3 \\end{bmatrix} \\in {\\rm
I\\\!R}^{3}](https://latex.codecogs.com/png.latex?x%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20%201%20%5C%5C%20%202%20%5C%5C%20%203%20%20%5Cend%7Bbmatrix%7D%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5E%7B3%7D
"x =  \\begin{bmatrix}  1 \\\\  2 \\\\  3  \\end{bmatrix} \\in {\\rm I\\!R}^{3}")
can therefore also be described as a position within a 3-dimensional
coordinate system i.e. starting at (0, 0, 0), move 1 unit in the 1st
perpendicular axis `x`, move 2 units in the 2nd perpendicular axis `y`
and then move 3 units in the 3rd perpendicular axis `z`.

# Basic vector operations
