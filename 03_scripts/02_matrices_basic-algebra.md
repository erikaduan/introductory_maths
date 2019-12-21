Basic matrix algebra in R and Python
================

  - [Matrix algebra](#matrix-algebra)
      - [Equality of 2 matrices](#equality-of-2-matrices)
      - [Scalar multiplication](#scalar-multiplication)
      - [Addition of 2 matrices](#addition-of-2-matrices)
      - [Multiplication of two
        matrices](#multiplication-of-two-matrices)
      - [Integral power of matrices](#integral-power-of-matrices)

# Matrix algebra

## Equality of 2 matrices

Two matrices are equal if they have the same dimensions and their
corresponding elements are equal.

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
```

In Python, this can be checked using logical comparison (i.e. using
`==`) or the \``compare` package`np.array_equal` or `np.array_equiv`
functions.

``` python
#-----matrix equality test-----
import numpy as np  
import pandas as pd

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

## Scalar multiplication

The scalar product of a matrix is given below (and the same rule holds
for division).

<img src="../02_figures/02_matrices-scalar-product.jpg" width="70%" style="display: block; margin: auto;" />

``` r
#-----scalar multiplication-----
a <- matrix(data = c(3, 4, 5, -2,
                     1, 0, -3, 2),
            nrow = 2,
            byrow = T)

(a)
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    3    4    5   -2
    ## [2,]    1    0   -3    2

``` r
(-2 * a)
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]   -6   -8  -10    4
    ## [2,]   -2    0    6   -4

``` r
(a / 2) # holds as it is the same as the scalar multiple (1/2) * a 
```

    ##      [,1] [,2] [,3] [,4]
    ## [1,]  1.5    2  2.5   -1
    ## [2,]  0.5    0 -1.5    1

## Addition of 2 matrices

The rules of addition apply if two matrices have the same order (m and n
are the same).

<img src="../02_figures/02_matrices-addition.jpg" width="70%" style="display: block; margin: auto;" />

``` r
#-----addition or subtraction of 2 matrices-----  
a <- matrix(data = c(0, 2, 4,
                     -1, -3 , -5),
            nrow = 2,
            byrow = T)

(3 * a) - (2 * a)
```

    ##      [,1] [,2] [,3]
    ## [1,]    0    2    4
    ## [2,]   -1   -3   -5

``` r
#----when two matrices do not have the same order-----  
a <- matrix(data = c(0, 2, 4,
                     -1, -3 , -5),
            nrow = 2,
            byrow = T)

b <- matrix(data = c(0, 2, 4, 3, 
                     -1, -3 , -5, 2),
            nrow = 2,
            byrow = T)

# a + b produces an error message   
```

## Multiplication of two matrices

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
