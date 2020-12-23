Introduction to sets
================
Erika Duan
2020-12-23

  - [What is a mathematical set?](#what-is-a-mathematical-set)
      - [Set notation](#set-notation)

# What is a mathematical set?

A [set](https://en.wikipedia.org/wiki/Set_\(mathematics\)) is a
collection of **distinct** mathematical objects.  
It is helpful for denoting:

  - Belonging i.e. ![a \\in
    A](https://latex.codecogs.com/png.latex?a%20%5Cin%20A "a \\in A") or
    element a is an object within set A.  
  - Inclusion i.e. ![A \\subset
    B](https://latex.codecogs.com/png.latex?A%20%5Csubset%20B
    "A \\subset B") or set A is a smaller subset within set B.

Sets do not need to be ordered and are contained within `{}`. This
nonemclature is preserved in Python.  
Two sets are equal if and only if they contain the same elements.

``` python
#-----create a set in Python-----   
set_1 = {1, 3, 4, 3, 5, 8, 8}
set_1
#> {1, 3, 4, 5, 8}  
```

## Set notation

We create subsets by asserting new subset properties i.e. a condition
![S(x)](https://latex.codecogs.com/png.latex?S%28x%29 "S(x)") only holds
true for a subset of elements within a set.
