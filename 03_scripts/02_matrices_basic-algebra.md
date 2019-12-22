Basic matrix algebra in R and Python
================

  - [Equality of 2 matrices](#equality-of-2-matrices)
      - [Checking matrices equality in
        R](#checking-matrices-equality-in-r)
      - [Checking matrices equality in
        Python](#checking-matrices-equality-in-python)
  - [Scalar multiplication](#scalar-multiplication)
      - [Scalar multiplication in R](#scalar-multiplication-in-r)
      - [Scalar multiplication in
        Python](#scalar-multiplication-in-python)
  - [Addition of 2 matrices](#addition-of-2-matrices)
      - [Adding matrices in R](#adding-matrices-in-r)
      - [Adding matrices in Python](#adding-matrices-in-python)
  - [Multiplication of two matrices](#multiplication-of-two-matrices)
      - [Integral power of matrices](#integral-power-of-matrices)
  - [Coding resources](#coding-resources)

# Equality of 2 matrices

Two matrices are equal if they have the same dimensions and their
corresponding elements are equal.

## Checking matrices equality in R

In R, this can be checked using logical comparison (i.e. using `==`) or
the `compare` package.

``` r
#-----matrix equality test-----
a <- matrix(data = c(4, -2, 7,
                    -2, -1, -2),
            nrow = 2,
            ncol = 3,
            byrow = T)

b <- a   

a == b # prints a logical matrix

#>      [,1] [,2] [,3]
#> [1,] TRUE TRUE TRUE
#> [2,] TRUE TRUE TRUE

summary(a == b) # logical results summed by matrix column  

#>     V1             V2             V3         
#>  Mode:logical   Mode:logical   Mode:logical  
#>  TRUE:2         TRUE:2         TRUE:2   
 
colSums(a == b) # column sums of all TRUEs (i.e. TRUE == 1)  

#> [1] 2 2 2

compare(a, b, equal = T) # from the compare package

#> TRUE

#-----unequal matrices-----  
c <- matrix(data = c(4, -2, 8,
                    -2, -1, -2),
            nrow = 2,
            ncol = 3,
            byrow = T)

summary(a == c) # logical results summed by matrix column 

#>     V1             V2              V3         
#>  Mode:logical   Mode:logical   Mode :logical  
#>  TRUE:2         TRUE:2         FALSE:1        
#>                                TRUE :1  

colSums(a == c)  

#> [1] 2 2 1
```

## Checking matrices equality in Python

In Python, this can be checked using logical comparison (i.e. using
`==`) or the R `compare` package equivalent `np.array_equal` or
`np.array_equiv`.

``` python
#-----matrix equality test-----
import numpy as np  

matrix_1 = np.array([[1, 2, 3],
                    [4, -5, 6]]) 
                    
matrix_2 = np.copy(matrix_1)  

matrix_1 == matrix_2

#> array([[ True,  True,  True],
#>        [ True,  True,  True]])

np.array_equal(matrix_1, matrix_2) # test if same shape, same elements values
np.array_equiv(matrix_1, matrix_2)  # test if broadcastable shape, same elements values

#> True  
#> True

#-----unequal matrices-----  
matrix_3 = np.array([[1, 2, 3],
                     [4, -5, 9]])  
                    
np.array_equal(matrix_1, matrix_3) 
```

# Scalar multiplication

The scalar product of a matrix is given below.

<img src="../02_figures/02_matrices-scalar-product.jpg" width="70%" style="display: block; margin: auto;" />

**Note:** The same principle holds for division, as it is an inverse
multiplication operation i.e: ![M\\times \\frac{1}{n} =
\\frac{M}{n}](https://latex.codecogs.com/png.latex?M%5Ctimes%20%5Cfrac%7B1%7D%7Bn%7D%20%3D%20%5Cfrac%7BM%7D%7Bn%7D
"M\\times \\frac{1}{n} = \\frac{M}{n}").

## Scalar multiplication in R

``` r
#-----scalar multiplication-----
a <- matrix(data = c(3, 4, 5, -2,
                     1, 0, -3, 2),
            nrow = 2,
            byrow = T)

(a)

#>      [,1] [,2] [,3] [,4]
#> [1,]    3    4    5   -2
#> [2,]    1    0   -3    2

((1/2) * a)  

#>      [,1] [,2] [,3] [,4]
#> [1,]  1.5    2  2.5   -1
#> [2,]  0.5    0 -1.5    1

(a / 2) # same as the scalar multiple (1/2) * a  

#>      [,1] [,2] [,3] [,4]
#> [1,]  1.5    2  2.5   -1
#> [2,]  0.5    0 -1.5    1
```

## Scalar multiplication in Python

``` python
#-----scalar multiplication-----  
import numpy as np  

matrix_1 = np.array([[1, 2, 3],
                    [4, -5, 6]])
                    
print(matrix_1) 

#> [[ 1  2  3]
#>  [ 4 -5  6]]

matrix_2 = matrix_1 * 3

print(matrix_2)

#> [[  3   6   9]
#>  [ 12 -15  18]]  

matrix_3 = matrix_1 / (1/3)
print(matrix_3)

#> [[  3.   6.   9.]
#>  [ 12. -15.  18.]] 

np.array_equal(matrix_2, matrix_3) 

#> True
```

# Addition of 2 matrices

The rules of addition apply if two matrices have the same order (m and n
are the same).

<img src="../02_figures/02_matrices-addition.jpg" width="70%" style="display: block; margin: auto;" />

## Adding matrices in R

``` r
#-----addition or subtraction of 2 matrices-----  
a <- matrix(data = c(0, 2, 4,
                     -1, -3 , -5),
            nrow = 2,
            byrow = T)

((3 * a) - (2 * a))

#>      [,1] [,2] [,3]
#> [1,]    0    2    4
#> [2,]   -1   -3   -5

#----when two matrices do not have the same order-----  
a <- matrix(data = c(0, 2, 4,
                     -1, -3 , -5),
            nrow = 2,
            byrow = T)

b <- matrix(data = c(0, 2, 4, 3, 
                     -1, -3 , -5, 2),
            nrow = 2,
            byrow = T)

(a + b)

#> Error in a + b : non-conformable arrays  
```

## Adding matrices in Python

# Multiplication of two matrices

Multiplication is only possible if the number of the number of columns
of matrix A is equivalent to the number of columns of matrix B.

<img src="../02_figures/02_matrices-multiplication.jpg" width="70%" style="display: block; margin: auto;" />

``` r
#-----when matrices can be multiplied-----
a <- matrix(data = c(0, 2, 4, 5
                     -1, -3 , -5, -4),
            nrow = 2,
            ncol = 4,
            byrow = T)
```

    ## Warning in matrix(data = c(0, 2, 4, 5 - 1, -3, -5, -4), nrow = 2, ncol =
    ## 4, : data length [7] is not a sub-multiple or multiple of the number of
    ## rows [2]

``` r
b <- matrix(data = c(0, 2,
                     4, 3, 
                     -1, -3,
                     2, 1),
            nrow = 4,
            ncol = 2, 
            byrow = T) 

a %*% b # matrix multiplication symbol  
```

    ##      [,1] [,2]
    ## [1,]   12   -2
    ## [2,]  -16   -9

<img src="../02_figures/02_matrices-multiplication-reverse-order.jpg" width="70%" style="display: block; margin: auto;" />

``` r
b %*% a # different matrix product 
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]   -6  -10   -8    0
    ## [2,]   -9   -7    4   16
    ## [3,]    9   13    8   -4
    ## [4,]   -3   -1    4    8

## Integral power of matrices

# Coding resources

**Online articles:**

\+[Broadcasting in
Python](https://www.geeksforgeeks.org/python-broadcasting-with-numpy-arrays/)
