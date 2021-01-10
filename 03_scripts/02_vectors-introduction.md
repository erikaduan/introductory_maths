Introduction to vectors
================
Erika Duan
2021-01-10

  - [Resources](#resources)
  - [What is a vector?](#what-is-a-vector)
  - [Special vectors](#special-vectors)
  - [Vector dimensions and the coordinate
    system](#vector-dimensions-and-the-coordinate-system)
  - [Basic vector operations](#basic-vector-operations)
      - [Vector-vector addition](#vector-vector-addition)
      - [Vector-scalar multiplication](#vector-scalar-multiplication)
      - [Vector linear combination](#vector-linear-combination)
      - [Vector-vector multiplication (the
        dot-product)](#vector-vector-multiplication-the-dot-product)
  - [Vector space, span and subspace](#vector-space-span-and-subspace)
      - [Vector span](#vector-span)
      - [Vector subspace](#vector-subspace)
  - [Linear dependence and linear
    independence](#linear-dependence-and-linear-independence)
  - [Vector null space](#vector-null-space)

# Resources

This section on vectors is taken from [Introduction to Linear Algebra
for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#vectors) by
Pablo Caceres, [Linear combinations and
span](https://www.youtube.com/watch?v=Qm_OS-8COwU) by Khan Academy and
[Essence of linear
algebra](https://www.3blue1brown.com/essence-of-linear-algebra-page) by
3Blue1Brown. All credit should be attributed to these sources.

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

<img src="../02_figures/02_vectors-types.jpg" width="100%" style="display: block; margin: auto;" />

``` python
#-----create 1 dimensional vector in Python via Numpy-----
import numpy as np 

x = np.array([np.arange(1, 10+1)])
x.shape
#> (1, 10) 
```

``` python
#-----create 3-dimensional vector in Python via Numpy-----
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
  - It is associative. ![(x + y) + z = x + (y +
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
#-----create and add two vectors in Python via Numpy----  
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
# arrays are not typically used for analysis in R i.e. its 2D array matrix form is used instead       

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
    \\times (\\beta \\times
    x)](https://latex.codecogs.com/png.latex?%28%5Calpha%20%5Ctimes%20%5Cbeta%20%29%5Ctimes%20x%20%3D%20%5Calpha%20%5Ctimes%20%28%5Cbeta%20%5Ctimes%20x%29
    "(\\alpha \\times \\beta )\\times x = \\alpha \\times (\\beta \\times x)")  
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
#-----vector-scalar multiplication in Python via Numpy-----
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
#-----vector-scalar multiplication in R-----  
alpha <- 4
x <- array(c(1, 1,
             2, 2,
             3, 3), 
           dim = c(1, 2, 3))

str(alpha * x)  
#>  num [1, 1:2, 1:3] 4 4 8 8 12 12    
```

## Vector linear combination

A linear combination utilises the both rules of vector-vector addition
and vector-scalar multiplication.

There are a few different ways of thinking about linear combinations:

  - Graphically as the addition of two vectors to form a new vector
    (which can also be visualised as a point in space) in the Cartesian
    plane.  
  - Mathmatically as the proof that any new vector can be created by a
    scalar combination of two existing basis vectors.

<img src="../02_figures/02_vectors-linear-combination.jpg" width="100%" style="display: block; margin: auto;" />

Another way to express linear combinations is with summation notation as
![\\displaystyle\\sum\_{i=1}^{k}\\beta\_{i}x\_{i}](https://latex.codecogs.com/png.latex?%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bk%7D%5Cbeta_%7Bi%7Dx_%7Bi%7D
"\\displaystyle\\sum_{i=1}^{k}\\beta_{i}x_{i}"). Note that two linearly
independent vectors do not need to be orthogonal to each other for the
span of their linear combinations to be ![{\\rm
I\\\!R}^3](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E3
"{\\rm I\\!R}^3").

``` python
#-----linear combination in Python via Numpy-----  
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

``` r
#-----linear combinations in R----- 
a <- -2
b <- 3

x <- array(c(2, 3), 
           dim = c(1, 2, 1))

y <- array(c(4, 5), 
           dim = c(1, 2, 1))

str(a*x + b*y)
#>  num [1, 1:2, 1] 8 9   
```

## Vector-vector multiplication (the dot-product)

Vector-vector multiplication involves taking the transpose of the first
vector and then calculating the sum of the product of each vector
dimension.  
  
![x\\cdot y = \\begin{bmatrix}
x\_1\\\\
x\_2\\\\
\\end{bmatrix}^T \\cdot
\\begin{bmatrix}
y\_1\\\\
y\_2\\\\
\\end{bmatrix} = 
\\begin{bmatrix}
x\_1, x\_2\\\\
\\end{bmatrix} \\cdot 
\\begin{bmatrix}
y\_1\\\\
y\_2\\\\
\\end{bmatrix} = 
\\begin{bmatrix}
(x\_1\\times y\_1) + (x\_2\\times y\_2)
\\end{bmatrix}](https://latex.codecogs.com/png.latex?x%5Ccdot%20y%20%3D%20%5Cbegin%7Bbmatrix%7D%0A%20x_1%5C%5C%0A%20x_2%5C%5C%0A%5Cend%7Bbmatrix%7D%5ET%20%5Ccdot%0A%5Cbegin%7Bbmatrix%7D%0A%20y_1%5C%5C%0A%20y_2%5C%5C%0A%5Cend%7Bbmatrix%7D%20%3D%20%0A%5Cbegin%7Bbmatrix%7D%0A%20x_1%2C%20x_2%5C%5C%0A%5Cend%7Bbmatrix%7D%20%5Ccdot%20%20%0A%5Cbegin%7Bbmatrix%7D%0A%20y_1%5C%5C%0A%20y_2%5C%5C%0A%5Cend%7Bbmatrix%7D%20%3D%20%0A%5Cbegin%7Bbmatrix%7D%0A%28x_1%5Ctimes%20y_1%29%20%2B%20%28x_2%5Ctimes%20y_2%29%0A%5Cend%7Bbmatrix%7D
"x\\cdot y = \\begin{bmatrix}
 x_1\\\\
 x_2\\\\
\\end{bmatrix}^T \\cdot
\\begin{bmatrix}
 y_1\\\\
 y_2\\\\
\\end{bmatrix} = 
\\begin{bmatrix}
 x_1, x_2\\\\
\\end{bmatrix} \\cdot  
\\begin{bmatrix}
 y_1\\\\
 y_2\\\\
\\end{bmatrix} = 
\\begin{bmatrix}
(x_1\\times y_1) + (x_2\\times y_2)
\\end{bmatrix}")  

**Note:** Vector-vector multiplication will always return a single
value.

``` python
#-----vector-vector multiplication in Python via Numpy-----  
x = np.array([[-2],
              [2]])  

y = np.array([[4],
              [-3]])  

np.transpose(x) # can also be written as x.T
#> array([[-2,  2]])    
```

``` python
np.transpose(x) @ y
#> array([[-14]])   
```

``` r
#-----vector-vector multiplication in R-----  
# t() only works on matrices so we need to create x and y as matrices rather than arrays    

x <- matrix(c(-2, 2), nrow = 2)

y <- matrix(c(4, -3), nrow = 2)

t(x) 
#>      [,1] [,2]
#> [1,]   -2    2  

t(x) %*% y
#>      [,1]
#> [1,]  -14
```

# Vector space, span and subspace

A vector space is the set of proper vectors (objects which follow the
rules defined for vector behaviour) and all possible linear combinations
of the vector set.

## Vector span

If we take the vectors x and y and the scalars
![\\alpha](https://latex.codecogs.com/png.latex?%5Calpha "\\alpha") and
![\\beta](https://latex.codecogs.com/png.latex?%5Cbeta "\\beta"), the
vector span is defined as the set of all possible linear combinations of
![\\alpha x + \\beta
y](https://latex.codecogs.com/png.latex?%5Calpha%20x%20%2B%20%5Cbeta%20y
"\\alpha x + \\beta y").

<img src="../02_figures/02_vectors-span.jpg" width="100%" style="display: block; margin: auto;" />

## Vector subspace

A vector subspace is a vector space that lies within a larger vector
space.

For a vector subspace S to be valid, it has to meet three conditions:

  - Contains the zero vector. ![0\\in
    S](https://latex.codecogs.com/png.latex?0%5Cin%20S "0\\in S")  
  - Exhibits closure under multiplication i.e. ![for\\; all\\; \\alpha
    \\in {\\rm I\\\!R} \\to \\alpha \\times s\_i \\in
    S](https://latex.codecogs.com/png.latex?for%5C%3B%20all%5C%3B%20%5Calpha%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%20%5Cto%20%5Calpha%20%5Ctimes%20s_i%20%5Cin%20S
    "for\\; all\\; \\alpha \\in {\\rm I\\!R} \\to \\alpha \\times s_i \\in S")  
  - Exhibits closure under addition i.e. ![for\\; all\\; s\_i \\in S
    \\to s\_1 + s\_2 \\in
    S](https://latex.codecogs.com/png.latex?for%5C%3B%20all%5C%3B%20s_i%20%5Cin%20S%20%5Cto%20s_1%20%2B%20s_2%20%5Cin%20S
    "for\\; all\\; s_i \\in S \\to s_1 + s_2 \\in S")

[Closure](https://www.mathsisfun.com/sets/closure.html) can be thought
of as the inability to jump out from one space into another. For
example, in the set of odd numbers, odd numbers exhibit closure under
multiplication.

<img src="../02_figures/02_vectors-subspace.jpg" width="100%" style="display: block; margin: auto;" />

There are two ways to think about vector subspaces:

**Geometrically for 2D or 3D vectors**

You can think about closure under multiplication or addition as the
addition of two vectors in the Cartesian plane. This is slightly harder
to visualise in 3D and impossible for vectors of higher dimensions.

**Mathematically evaluating individual vectors**

You can ask whether the vector ![x= \\begin{bmatrix} 1\\\\ 2\\\\
\\end{bmatrix}](https://latex.codecogs.com/png.latex?x%3D%20%5Cbegin%7Bbmatrix%7D%20%201%5C%5C%20%202%5C%5C%20%5Cend%7Bbmatrix%7D
"x= \\begin{bmatrix}  1\\\\  2\\\\ \\end{bmatrix}") is a valid subpace
of ![{\\rm
I\\\!R}^2](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E2
"{\\rm I\\!R}^2").

  - Because the span of a vector is the set of all its linear
    combinations, the span of ![x= \\begin{bmatrix} 1\\\\ 1\\\\
    \\end{bmatrix}](https://latex.codecogs.com/png.latex?x%3D%20%5Cbegin%7Bbmatrix%7D%20%201%5C%5C%20%201%5C%5C%20%5Cend%7Bbmatrix%7D
    "x= \\begin{bmatrix}  1\\\\  1\\\\ \\end{bmatrix}") does contain
    zero i.e. ![0\\times x= 0 \\times \\begin{bmatrix} 1\\\\ 1\\\\
    \\end{bmatrix} = \\begin{bmatrix} 0\\\\ 0\\\\
    \\end{bmatrix}](https://latex.codecogs.com/png.latex?0%5Ctimes%20x%3D%200%20%5Ctimes%20%5Cbegin%7Bbmatrix%7D%20%201%5C%5C%20%201%5C%5C%20%5Cend%7Bbmatrix%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%20%200%5C%5C%20%200%5C%5C%20%5Cend%7Bbmatrix%7D
    "0\\times x= 0 \\times \\begin{bmatrix}  1\\\\  1\\\\ \\end{bmatrix} = \\begin{bmatrix}  0\\\\  0\\\\ \\end{bmatrix}")  
  - Closure by multiplication implies that if we take the vector x and
    multiply it by any real scalar, the resulting vector will stay in
    the span of x. This is also true as ![\\alpha \\times
    x](https://latex.codecogs.com/png.latex?%5Calpha%20%5Ctimes%20x
    "\\alpha \\times x") will only stretch the length and or change the
    direction of x, so the resulting vector remains in the span of
    ![{\\rm
    I\\\!R}^2](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E2
    "{\\rm I\\!R}^2").  
  - Closure by addition implies that if we add together any vectors
    beloning to x, the resulting vector remains in the span of ![{\\rm
    I\\\!R}^2](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E2
    "{\\rm I\\!R}^2"). If we add ![x +
    x](https://latex.codecogs.com/png.latex?x%20%2B%20x "x + x"), the
    vector does not gain any new dimensions and remains in the span of
    ![{\\rm
    I\\\!R}^2](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5E2
    "{\\rm I\\!R}^2").

# Linear dependence and linear independence

A set of vectors is linearly dependent if at least one vector can be
obtained as a linear combination of other vectors in the set. Another
way to define linear dependence is to consider a set of vectors ![x\_1,
..., x\_k](https://latex.codecogs.com/png.latex?x_1%2C%20...%2C%20x_k
"x_1, ..., x_k") and scalars ![\\beta \\in {\\rm
I\\\!R}](https://latex.codecogs.com/png.latex?%5Cbeta%20%5Cin%20%7B%5Crm%20I%5C%21R%7D
"\\beta \\in {\\rm I\\!R}"). Linearly dependent vectors exist if we can
obtain ![0 = \\displaystyle\\sum\_{i=1}^{k}
\\beta\_{i}x\_{i}](https://latex.codecogs.com/png.latex?0%20%3D%20%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bk%7D%20%5Cbeta_%7Bi%7Dx_%7Bi%7D
"0 = \\displaystyle\\sum_{i=1}^{k} \\beta_{i}x_{i}") using at least one
vector where ![\\beta
\\neq 0](https://latex.codecogs.com/png.latex?%5Cbeta%20%5Cneq%200
"\\beta \\neq 0"). (This implies that there is a vector in the same
direction as a linear combination of other vectors, and we can therefore
choose a scalar value that is equal in length but in the opposite
direction to the linear combination of those other vectors to obtain ![0
= \\displaystyle\\sum\_{i=1}^{k}
\\beta\_{i}x\_{i}](https://latex.codecogs.com/png.latex?0%20%3D%20%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bk%7D%20%5Cbeta_%7Bi%7Dx_%7Bi%7D
"0 = \\displaystyle\\sum_{i=1}^{k} \\beta_{i}x_{i}") ).

A set of vectors is linearly independent if no vector can be obtained as
a linear combination of other vectors in the set.

<img src="../02_figures/02_vectors-independence.jpg" width="100%" style="display: block; margin: auto;" />

To summarise, linearly dependent vectors contain redundant information
and the span of linearly dependent vectors cannot cover the whole set of
values in ![{\\rm
I\\\!R}^n](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5En
"{\\rm I\\!R}^n"). In contrast, linearly independent vectors do not
contain redundant information.

# Vector null space

The null space of a set of vectors are all the linear combinations that
map back into the zero vector.

<img src="../02_figures/02_vectors-null-space.jpg" width="100%" style="display: block; margin: auto;" />

In the example above, we can form the following two combinations of
vectors that will map into the zero vector (0,0).
