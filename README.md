# Introductory mathematics in R and Python  

This repository contains tutorials on the introductory mathematical concepts required for studying statistics and machine learning. Mathematical calculations are executed in both `R` and `Python`.    

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/figures/repo_logo.jpg)

## Tutorials

|Topics|Tutorials|
|:-----|:--------|
|:1234:|[Introduction to numbers](./tutorials/numbers-introduction.md)|
|:1234:|Introduction to algebra|
|:1234:|Exponents and logarithms|
|:1234:|Logarithms and information theory|
|:black_joker:|[Introduction to probability theory](./tutorials/probability-introduction.md)|
|:black_joker:|[Conditional probability](./tutorials/probability-conditional_probability.md)|
|:black_joker:|Bayes theorem|
|:cookie:|Introduction to summations|
|:compass:|Introduction to trigonometry|
|:compass:|Distance metrics|
|:compass:|Cosine similarity|
|:chopsticks:|[Introduction to linear systems](./tutorials/linear_algebra-linear_systems.md)|  
|:chopsticks:|[Introduction to vectors](./tutorials/linear_algebra-vectors.md)|
|:chopsticks:|Vector transformations|
|:chopsticks:|Vector embeddings|
|:department_store:|Introduction to matrices|  
|:roller_coaster:|Introduction to derivatives|  

## Contributors

+ [Erika Duan](https://github.com/erikaduan/)
+ [Chuanxin Liu](https://github.com/codetrainee)

## Project setup   
This project was created using the following setup:    
+ R package dependencies are managed using `renv` for `R version 4.1.2 (2021-11-01)`.    
+ Python virtual environment and package dependencies are managed using `poetry` for `Python 3.9.6`.     

## Guide to writing mathematical proofs   
**Direct proof**   
+ Occurs when you need to prove that A and B are equivalent.   
+ Start by assuming A is true.   
+ Construction definition statement for A.   
+ Extend and simplify mathematical definitions derived from A to reach B.   

**Induction proof**  
+ Occurs when you need to provde that something is true for all cases.  
+ Start by proving the base case when $n = 1$.  
+ Assume that the case is also true for some integer $k$.  
+ Prove that the case for $k + 1$ also holds i.e. proving the next incremental step up a ladder stretching to infinity.  

## References

+ A guide to [linear algebra](https://pabloinsente.github.io/intro-linear-algebra) for applied machine learning by Pablo Caceres
+ The [Mathematics for Machine Learning textbook](https://mml-book.github.io/book/mml-book.pdf) by Marc Peter Deisenroth, A Aldo Faisal and Cheng Soon Ong - Cambridge University Press
+ The [Probability for Data Science textbook](https://probability4datascience.com/) by Stanley H Chan - Michigan Publishing
+ The [Probabilistic modelling tutorials](https://betanalpha.github.io/writing/) by Michael Betancourt - GitHub
+ Writing [mathematical operations in LaTex/R](https://en.wikibooks.org/wiki/LaTeX/Mathematics#Fractions_and_Binomials) - Wikibooks
