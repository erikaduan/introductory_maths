Introduction to vectors
================
Erika Duan
2021-01-06

  - [Resources](#resources)
  - [What is a vector?](#what-is-a-vector)
  - [Special vectors](#special-vectors)
  - [Vector dimensions and the coordinate
    system](#vector-dimensions-and-the-coordinate-system)
  - [Basic vector operations](#basic-vector-operations)
      - [Vector-vector addition](#vector-vector-addition)
      - [Vector-scalar multiplication](#vector-scalar-multiplication)
  - [Linear combinations of vectors](#linear-combinations-of-vectors)

# Resources

This section on vectors is taken from [Introduction to Linear Algebra
for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#vectors) by
Pablo Caceres, [Linear combinations and
span](https://www.youtube.com/watch?v=Qm_OS-8COwU) by Khan Academy and
[Linear combinations, span and basis
vectors](https://www.youtube.com/watch?v=k7RM-ot2NWY) by 3Blue1Brown.
All credit should be attributed to these sources.

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
    variables and exponents) like
    ![f(x)=x^{2}+y+1](https://latex.codecogs.com/png.latex?f%28x%29%3Dx%5E%7B2%7D%2By%2B1
    "f(x)=x^{2}+y+1").  
  - Elements of ![{\\rm
    I\\\!R}^n](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5En
    "{\\rm I\\!R}^n") - sets of real numbers. A vector in ![{\\rm
    I\\\!R}^3](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E3
    "{\\rm I\\!R}^3") has the shape below.  
    ![x = \\begin{bmatrix} x\_1 \\\\ x\_2 \\\\ x\_3 \\end{bmatrix} \\in
    {\\rm
    I\\\!R}^{3}](https://latex.codecogs.com/png.latex?x%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20x_1%20%5C%5C%20x_2%20%5C%5C%20x_3%20%20%5Cend%7Bbmatrix%7D%20%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5E%7B3%7D
    "x =  \\begin{bmatrix} x_1 \\\\ x_2 \\\\ x_3  \\end{bmatrix}  \\in {\\rm I\\!R}^{3}")

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/02_figures/02_vectors-types.jpg)

``` python
#-----create 1 dimensional vector in Python-----
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

## Vector-vector addition

Vector-vector addition is performed element-wise and it only applies for
vectors of the same size.

![x + y = \\begin{bmatrix} x\_1 \\\\ x\_2 \\\\ \\vdots \\\\ x\_n
\\end{bmatrix} + \\begin{bmatrix} y\_1 \\\\ y\_2 \\\\ \\vdots \\\\ y\_n
\\end{bmatrix} = \\begin{bmatrix} x\_1 + y\_1 \\\\ x\_2 + y\_2 \\\\
\\vdots \\\\ x\_n + y\_n
\\end{bmatrix}](https://latex.codecogs.com/png.latex?x%20%2B%20y%20%3D%20%5Cbegin%7Bbmatrix%7D%20%20x_1%20%5C%5C%20%20x_2%20%5C%5C%20%20%5Cvdots%20%5C%5C%20%20x_n%20%20%5Cend%7Bbmatrix%7D%20%20%2B%20%20%5Cbegin%7Bbmatrix%7D%20%20y_1%20%5C%5C%20%20y_2%20%5C%5C%20%20%5Cvdots%20%5C%5C%20%20y_n%20%20%5Cend%7Bbmatrix%7D%20%3D%20%20%5Cbegin%7Bbmatrix%7D%20%20x_1%20%2B%20y_1%20%5C%5C%20%20x_2%20%2B%20y_2%20%5C%5C%20%20%5Cvdots%20%5C%5C%20%20x_n%20%2B%20y_n%20%20%5Cend%7Bbmatrix%7D
"x + y = \\begin{bmatrix}  x_1 \\\\  x_2 \\\\  \\vdots \\\\  x_n  \\end{bmatrix}  +  \\begin{bmatrix}  y_1 \\\\  y_2 \\\\  \\vdots \\\\  y_n  \\end{bmatrix} =  \\begin{bmatrix}  x_1 + y_1 \\\\  x_2 + y_2 \\\\  \\vdots \\\\  x_n + y_n  \\end{bmatrix}")

Vector-vector addition has the following properties:

  - It is commutative. ![x + y = y +
    x](https://latex.codecogs.com/png.latex?x%20%2B%20y%20%3D%20y%20%2B%20x
    "x + y = y + x")  
  - It is associative ![(x + y) + z = x + (y +
    z)](https://latex.codecogs.com/png.latex?%28x%20%2B%20y%29%20%2B%20z%20%3D%20x%20%2B%20%28y%20%2B%20z%29
    "(x + y) + z = x + (y + z)")  
  - Addition of the zero vector has no effect. ![x + 0 =
    x](https://latex.codecogs.com/png.latex?x%20%2B%200%20%3D%20x
    "x + 0 = x")  
  - Subtracting the vector from itself returns the zero vector. ![x - x
    = 0](https://latex.codecogs.com/png.latex?x%20-%20x%20%3D%200
    "x - x = 0")

<!-- end list -->

``` python
#-----create and add two vectors via NumPy arrays----  
x = np.array([[1, 1],
              [2, 2],
              [3, 3]])  

x.shape # 3-dimensional NumPy array  
#> (3, 2)
```

``` python
y = np.array([[1, 0],
              [0, 1],
              [1, 1]])

x + y
#> array([[2, 1],
#>        [2, 3],
#>        [4, 4]])
```

``` python
np.add(x, y)
#> array([[2, 1],
#>        [2, 3],
#>        [4, 4]])
```

``` r
#-----create and add two vectors in R-----  
# vectors of n dimensions can be stored inside arrays   

x <- array(c(1, 1,
             2, 2,
             3, 3), 
           dim = c(1, 2, 3))

str(x)  
#>  num [1, 1:2, 1:3] 1 1 2 2 3 3  

y <- array(c(1, 0,
             0, 1,
             1, 1), 
           dim = c(1, 2, 3))  

str(x + y) 
#>  num [1, 1:2, 1:3] 2 1 2 3 4 4 
```

## Vector-scalar multiplication

Vector-scalar multiplication is also an element-wise operation.

![\\alpha x = \\begin{bmatrix} \\alpha x\_1\\\\ \\alpha x\_2\\\\ \\vdots
\\\\ \\alpha x\_n
\\end{bmatrix}](https://latex.codecogs.com/png.latex?%5Calpha%20x%20%3D%20%5Cbegin%7Bbmatrix%7D%20%20%5Calpha%20x_1%5C%5C%20%20%5Calpha%20x_2%5C%5C%20%20%5Cvdots%20%5C%5C%20%20%5Calpha%20x_n%20%5Cend%7Bbmatrix%7D
"\\alpha x = \\begin{bmatrix}  \\alpha x_1\\\\  \\alpha x_2\\\\  \\vdots \\\\  \\alpha x_n \\end{bmatrix}")

Vector-scalar multiplication has the following properties:

  - It is associative. ![(\\alpha \\times \\beta )\\times x = \\alpha
    \\times ( \\beta \\times
    x)](https://latex.codecogs.com/png.latex?%28%5Calpha%20%5Ctimes%20%5Cbeta%20%29%5Ctimes%20x%20%3D%20%5Calpha%20%5Ctimes%20%28%20%5Cbeta%20%5Ctimes%20x%29
    "(\\alpha \\times \\beta )\\times x = \\alpha \\times ( \\beta \\times x)")  
  - It is left-distributive. ![(\\alpha + \\beta )x = \\alpha x + \\beta
    x](https://latex.codecogs.com/png.latex?%28%5Calpha%20%2B%20%5Cbeta%20%29x%20%3D%20%5Calpha%20x%20%2B%20%5Cbeta%20x
    "(\\alpha + \\beta )x = \\alpha x + \\beta x")  
  - It is right-distributive. ![x(\\alpha + \\beta ) = x\\alpha +
    x\\beta](https://latex.codecogs.com/png.latex?x%28%5Calpha%20%2B%20%5Cbeta%20%29%20%3D%20x%5Calpha%20%2B%20x%5Cbeta
    "x(\\alpha + \\beta ) = x\\alpha + x\\beta")  
  - It is right-distributive for vector addition. ![\\alpha
    (x+y)=\\alpha x+ \\alpha
    y](https://latex.codecogs.com/png.latex?%5Calpha%20%28x%2By%29%3D%5Calpha%20x%2B%20%5Calpha%20y
    "\\alpha (x+y)=\\alpha x+ \\alpha y")

<!-- end list -->

``` python
#-----vector scalar multiplication via NumPy arrays-----
alpha = 4 

x = np.array([[1, 1],
              [2, 2],
              [3, 3]])  
             
alpha * x    
#> array([[ 4,  4],
#>        [ 8,  8],
#>        [12, 12]])
```

``` r
#-----vector scalar multiplication in R-----  
alpha <- 4
x <- array(c(1, 1,
             2, 2,
             3, 3), 
           dim = c(1, 2, 3))

str(alpha * x)  
#>  num [1, 1:2, 1:3] 4 4 8 8 12 12    
```

# Linear combinations of vectors

A linear combination utilises the both rules of vector-vector addition
and vector-scalar multiplication.

There are a few different ways of thinking about linear combinations:

  - Graphically as the addition of two vectors to form a new vector
    (which can also be visualised as a point in space) in the Cartesian
    plane.  
  - Mathmatically as the proof that any new vector can be created by a
    scalar combination of two existing basis vectors.

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/02_figures/02_vectors-linear-combination.jpg)

Another way to express linear combinations is with summation notation as
![\\displaystyle\\sum\_{i=1}^{k}\\beta\_{i}x\_{i}](https://latex.codecogs.com/png.latex?%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bk%7D%5Cbeta_%7Bi%7Dx_%7Bi%7D
"\\displaystyle\\sum_{i=1}^{k}\\beta_{i}x_{i}").

``` python
#-----linear combination via NumPy arrays-----  
a, b = -2, 3 # input scalar values  

x = np.array([[2],
              [3]])

y = np.array([[4],
              [5]])  

a*x + b*y
#> array([[8],
#>        [9]]) 

#> [[-4 + 12],
#>  [-6 + 15]]  
```
