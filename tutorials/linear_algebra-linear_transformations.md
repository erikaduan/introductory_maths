Linear transformations
================
Erika Duan
2022-08-22

-   [Vector transformation notation](#vector-transformation-notation)
-   [Dimensionality and linear
    transformations](#dimensionality-and-linear-transformations)
-   [Injective linear
    transformations](#injective-linear-transformations)
-   [Surjective linear
    transformations](#surjective-linear-transformations)
-   [Resources](#resources)

# Vector transformation notation

The essence of linear algebra involves the study of linear
transformations of vector spaces.

A linear transformation can be described as:

-   A function which maps a vector in
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
    to a vector in
    ![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
    or
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   This is denoted by
    ![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
    or
    ![T: \\mathbb{R}^n \\to \\mathbb{R}^n](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5En "T: \mathbb{R}^n \to \mathbb{R}^n")
    respectively.  
-   Alternatively, we can denote linear transformations with respect to
    its vector inputs and outputs
    i.e. ![\\vec x {\\; T \\;\\atop \\mapsto} \\vec w](https://latex.codecogs.com/svg.format?%5Cvec%20x%20%7B%5C%3B%20T%20%5C%3B%5Catop%20%5Cmapsto%7D%20%5Cvec%20w "\vec x {\; T \;\atop \mapsto} \vec w"),
    where
    ![\\vec w = T(\\vec x)](https://latex.codecogs.com/svg.format?%5Cvec%20w%20%3D%20T%28%5Cvec%20x%29 "\vec w = T(\vec x)").  
-   The domain of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    is
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   The co-domain of
    ![T(\\vec x)](https://latex.codecogs.com/svg.format?T%28%5Cvec%20x%29 "T(\vec x)")
    can be
    ![\\mathbb{R}^m](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5Em "\mathbb{R}^m")
    or
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n")
    respectively.  
-   The image of
    ![vec x](https://latex.codecogs.com/svg.format?vec%20x "vec x")
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
-   Linear transformations can also be regarded as a transformation by a
    standard matrix for T (draw this definition too)

<img src="../figures/linear_systems-linear_transformation_notation.svg" width="80%" style="display: block; margin: auto;" />

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
must satisfy the following two properties:

-   
-   

# Dimensionality and linear transformations

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
can be described in the following ways:

-   
-   

<img src="../figures/linear_systems-n_to_m_transformation.svg" width="80%" style="display: block; margin: auto;" />

A linear transformation
![T: \\mathbb{R}^n \\to \\mathbb{R}^m](https://latex.codecogs.com/svg.format?T%3A%20%5Cmathbb%7BR%7D%5En%20%5Cto%20%5Cmathbb%7BR%7D%5Em "T: \mathbb{R}^n \to \mathbb{R}^m")
can be described in the following ways:

-   
-   

# Injective linear transformations

# Surjective linear transformations

# Resources

-   Great YouTube videos on
    [2D](https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3)
    and
    [3D](https://www.youtube.com/watch?v=rHLEWRxRGiM&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=5)
    linear transformations by 3Blue1Brown.
