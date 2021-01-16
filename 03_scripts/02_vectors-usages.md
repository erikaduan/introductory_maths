Working with vectors
================
Erika Duan
2021-01-16

  - [Resources](#resources)
  - [Vector norms](#vector-norms)
      - [Euclidean norm](#euclidean-norm)
      - [Manhattan norm](#manhattan-norm)
      - [Max norm](#max-norm)
  - [Vector inner product, length and
    distance](#vector-inner-product-length-and-distance)
  - [Vector angles and orthogonality](#vector-angles-and-orthogonality)
  - [Systems of linear equations](#systems-of-linear-equations)

# Resources

This section on vectors is taken from [Introduction to Linear Algebra
for Applied Machine Learning with
Python](https://pabloinsente.github.io/intro-linear-algebra#vector-norms)
by Pablo Caceres and [Lecture 8 - Norms of Vectors and
Matrices](https://www.youtube.com/watch?v=NcPUI7aPFhA) from Matrix
Methods in Data Analysis, Signal Processing, and Machine Learning, MIT
OpenCourseWare. All credit should be attributed to these sources.

# Vector norms

To measure vectors, you can think about the norm (i.e. length) of the
vector as the distance between its origin and end points.

![\\lVert x \\rVert = \\sqrt{x\_1^2 +
x\_2^2+...+x\_n^2}](https://latex.codecogs.com/png.latex?%5ClVert%20x%20%5CrVert%20%3D%20%5Csqrt%7Bx_1%5E2%20%2B%20x_2%5E2%2B...%2Bx_n%5E2%7D
"\\lVert x \\rVert = \\sqrt{x_1^2 + x_2^2+...+x_n^2}")

Norms are functions that map vectors to non-negative values. They are
used to assign ![length\\; \\lVert x\\rVert \\in {\\rm
I\\\!R}^n](https://latex.codecogs.com/png.latex?length%5C%3B%20%5ClVert%20x%5CrVert%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5En
"length\\; \\lVert x\\rVert \\in {\\rm I\\!R}^n") to a vector x.

A norm has to satisfy the following three properties:

  - It is absolutely homogenous. For all scalars that are real values,
    the length scales proportionally with the value of the scalar.
    ![\\forall \\alpha \\in {\\rm I\\\!R}, \\; \\lVert \\alpha x \\rVert
    = \\lVert \\alpha \\rVert \\cdot \\lVert x
    \\rVert](https://latex.codecogs.com/png.latex?%5Cforall%20%5Calpha%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%2C%20%5C%3B%20%5ClVert%20%5Calpha%20x%20%5CrVert%20%3D%20%5ClVert%20%5Calpha%20%5CrVert%20%5Ccdot%20%5ClVert%20x%20%5CrVert
    "\\forall \\alpha \\in {\\rm I\\!R}, \\; \\lVert \\alpha x \\rVert = \\lVert \\alpha \\rVert \\cdot \\lVert x \\rVert")  
  - It exhibits triangular inequality. In geometric terms, the sum of
    the lengths of any two sides must be greater or equal to the length
    of the third side. ![\\lVert x+y \\rVert \\leq \\lVert x \\rVert +
    \\lVert y
    \\rVert](https://latex.codecogs.com/png.latex?%5ClVert%20x%2By%20%5CrVert%20%5Cleq%20%5ClVert%20x%20%5CrVert%20%2B%20%5ClVert%20y%20%5CrVert
    "\\lVert x+y \\rVert \\leq \\lVert x \\rVert + \\lVert y \\rVert").  
  - It is positively defined. The length of x has to be a positive value
    and a length of zero only occurs if x = 0. ![\\lVert x \\rVert
    \\geq 0 \\; and \\; \\lVert x \\rVert = 0 \\iff x
    = 0](https://latex.codecogs.com/png.latex?%5ClVert%20x%20%5CrVert%20%5Cgeq%200%20%5C%3B%20and%20%5C%3B%20%5ClVert%20x%20%5CrVert%20%3D%200%20%5Ciff%20x%20%3D%200
    "\\lVert x \\rVert \\geq 0 \\; and \\; \\lVert x \\rVert = 0 \\iff x = 0").

The three main types of vector norms are illustrated below.

<img src="../02_figures/02_vectors-norm-types.jpg" width="80%" style="display: block; margin: auto;" />

## Euclidean norm

The Euclidean or ![L\_2](https://latex.codecogs.com/png.latex?L_2 "L_2")
norm is defined below.   
![\\lVert x\\rVert\_2 := \\sqrt{\\displaystyle\\sum\_{i=1}^{n} x\_i^2} =
\\sqrt{x^T\\times x}
](https://latex.codecogs.com/png.latex?%5ClVert%20x%5CrVert_2%20%3A%3D%20%5Csqrt%7B%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20x_i%5E2%7D%20%3D%20%5Csqrt%7Bx%5ET%5Ctimes%20x%7D%20
"\\lVert x\\rVert_2 := \\sqrt{\\displaystyle\\sum_{i=1}^{n} x_i^2} = \\sqrt{x^T\\times x} ")  

The euclidean norm can also be thought of as the square root of the dot
product of a vector by itself.

In 2D, the Eucliean norm is ![\\lVert x\\rVert\_2 \\in {\\rm I\\\!R}^2 =
\\sqrt{x\_1^2 +
x\_2^2}](https://latex.codecogs.com/png.latex?%5ClVert%20x%5CrVert_2%20%5Cin%20%7B%5Crm%20I%5C%21R%7D%5E2%20%3D%20%5Csqrt%7Bx_1%5E2%20%2B%20x_2%5E2%7D
"\\lVert x\\rVert_2 \\in {\\rm I\\!R}^2 = \\sqrt{x_1^2 + x_2^2}").  
This is equivalent to the Pythagoras theorem for calculating the
hypotenuse of a triangle with sides
![x\_1^2](https://latex.codecogs.com/png.latex?x_1%5E2 "x_1^2") and
![x\_2^2](https://latex.codecogs.com/png.latex?x_2%5E2 "x_2^2").

``` python
#-----calculate L2 norm in Python via NumPy-----  
import numpy as np  

x = np.array([[3],
              [-4]])  
              
np.linalg.norm(x, 2) 
#> 5.0  
```

``` r
#-----calculate L2 norm in R-----  
x <- matrix(c(3, -4), nrow = 2)

norm(x, type = "2")
#> [1] 5 
```

## Manhattan norm

The Manhattan or ![L\_1](https://latex.codecogs.com/png.latex?L_1 "L_1")
norm is analogous to measuring distances whilst moving in only vertical
and horizontal lines. It is defined below.  
  
![\\lVert x\\rVert\_1 :=
\\displaystyle\\sum\_{i=1}^{n}|x\_i|](https://latex.codecogs.com/png.latex?%5ClVert%20x%5CrVert_1%20%3A%3D%20%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%7Cx_i%7C
"\\lVert x\\rVert_1 := \\displaystyle\\sum_{i=1}^{n}|x_i|")  

The manhattan norm is preferred for discriminating between elements that
are exactly zero and elements that are small but not zero (or for
calculating a distance matrix between categorical data points).

``` python
#-----calculate L1 norm in Python via NumPy-----  
x = np.array([[3],
              [-4]])  
              
np.linalg.norm(x, 1) 
#> 7.0 

# |3| + |-4| = 7  
```

``` r
#-----calculate L1 norm in R-----  
x <- matrix(c(3, -4), nrow = 2)

norm(x, type = "O")
#> [1] 7   
```

## Max norm

The Max norm or infinity norm is the absolute value of the largest
element in the vector. It is defined below.  
  
![\\lVert x\\rVert\_\\infty :=
max\_i|x\_i|](https://latex.codecogs.com/png.latex?%5ClVert%20x%5CrVert_%5Cinfty%20%3A%3D%20max_i%7Cx_i%7C
"\\lVert x\\rVert_\\infty := max_i|x_i|")  

The max norm is a useful norm type as when the number of dimensions
increases, the vector length will be disproportionately influenced by
the largest vector shown from the equation below.  
  
![\\lVert x\\rVert\_p := \\sqrt{\\displaystyle\\sum\_{i=1}^{n}
x\_i^p}](https://latex.codecogs.com/png.latex?%5ClVert%20x%5CrVert_p%20%3A%3D%20%5Csqrt%7B%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20x_i%5Ep%7D
"\\lVert x\\rVert_p := \\sqrt{\\displaystyle\\sum_{i=1}^{n} x_i^p}")  

``` python
#-----calculate max norm in Python via NumPy-----  
x = np.array([[3],
              [-4]])  
              
np.linalg.norm(x, np.inf) 

#> 4.0 
```

``` r
#-----calculate max norm in R-----
x <- matrix(c(3, -4), nrow = 2)

norm(x, type = "O")
#> [1] 4  
```

# Vector inner product, length and distance

For practicality, you can conside the vector inner product and vector
length as equivalent to the vector dot product and vector norm.  
Every dot product is an inner product. The scalar inner product is
defined below.  
  
![\\langle x, y\\rangle := x \\cdot
y](https://latex.codecogs.com/png.latex?%5Clangle%20x%2C%20y%5Crangle%20%3A%3D%20x%20%5Ccdot%20y
"\\langle x, y\\rangle := x \\cdot y")  

In ![{\\rm
I\\\!R}^n](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5En
"{\\rm I\\!R}^n"), the inner product is a dot product defined below.  
  
![\\langle 
\\begin{bmatrix}
x\_1 \\\\
\\vdots \\\\
x\_n
\\end{bmatrix},
\\begin{bmatrix}
y\_1 \\\\
\\vdots \\\\
y\_n
\\end{bmatrix}
\\rangle := x \\cdot y = \\displaystyle\\sum\_{i=1}^{n} x\_i\\times
y\_i](https://latex.codecogs.com/png.latex?%5Clangle%20%0A%5Cbegin%7Bbmatrix%7D%0A%20%20x_1%20%5C%5C%0A%20%20%5Cvdots%20%5C%5C%0A%20%20x_n%0A%5Cend%7Bbmatrix%7D%2C%0A%5Cbegin%7Bbmatrix%7D%0A%20%20y_1%20%5C%5C%0A%20%20%5Cvdots%20%5C%5C%0A%20%20y_n%0A%5Cend%7Bbmatrix%7D%0A%5Crangle%20%3A%3D%20x%20%5Ccdot%20y%20%3D%20%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%20x_i%5Ctimes%20y_i
"\\langle 
\\begin{bmatrix}
  x_1 \\\\
  \\vdots \\\\
  x_n
\\end{bmatrix},
\\begin{bmatrix}
  y_1 \\\\
  \\vdots \\\\
  y_n
\\end{bmatrix}
\\rangle := x \\cdot y = \\displaystyle\\sum_{i=1}^{n} x_i\\times y_i")  

Because length is a concept from geometry, you can say that geometric
vectors have lengths and that vectors in ![{\\rm
I\\\!R}^n](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5En
"{\\rm I\\!R}^n") have norms.

Distance is therefore a relational concept, as it refers to the length
(or norm) of the difference between two vectors. For example, consider
the vectors x and y. We define the distance ![d(x,
y)](https://latex.codecogs.com/png.latex?d%28x%2C%20y%29 "d(x, y)") as
below.  
  
![d(x, y) := \\lVert x - y \\rVert = \\sqrt{\\langle x-y, x -y
\\rangle}](https://latex.codecogs.com/png.latex?d%28x%2C%20y%29%20%3A%3D%20%5ClVert%20x%20-%20y%20%5CrVert%20%3D%20%5Csqrt%7B%5Clangle%20x-y%2C%20x%20-y%20%5Crangle%7D
"d(x, y) := \\lVert x - y \\rVert = \\sqrt{\\langle x-y, x -y \\rangle}")  

This definition for distance is flexible. When the inner product is
specifically the dot product, the distance equals to the Euclidean
distance.  
<img src="../02_figures/02_vectors-distance.jpg" width="80%" style="display: block; margin: auto;" />

``` python
#-----calculate L2 distance between two vectors in Python via NumPy-----  
x = np.array([[3],
              [-4]])   

y = np.array([[-2],
              [2]])

x - y 
#> array([[ 5],
#>        [-6]])
```

``` python
distance = np.linalg.norm(x-y, 2)

print("L2 distance between x and y: {}".format(distance))
#> L2 distance between x and y: 7.810249675906654  
```

``` r
#-----calculate L2 distance between two vectors in R-----
x <- matrix(c(3, -4), nrow = 2)

y <- matrix(c(-2, 2), nrow = 2)   

x - y
#>      [,1]
#> [1,]    5
#> [2,]   -6  

norm(x - y, type = "2")
#> [1] 7.81025  
```

# Vector angles and orthogonality

# Systems of linear equations
