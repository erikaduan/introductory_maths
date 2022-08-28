# Introductory mathematics in R and Python    
This repository contains tutorials on the introductory mathematical concepts required for studying statistics and machine learning.   
Extra visualisations are created in `R` and code to solve linear systems are written in both `R` and `Python`.    

![](https://github.com/erikaduan/Introductory-maths-in-R-and-Python/blob/master/figures/repo_logo.jpg)

## Tutorials    
|Topics|Tutorials|
|:-----|:--------|
|:1234:|[Introduction to numbers](./tutorials/numbers-introduction.md)|  
|:1234:|Introduction to functions|
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
|:chopsticks:|[Linear transformations](./tutorials/linear_algebra-linear_transformations.md)|  
|:chopsticks:|Vector embeddings|
|:department_store:|[Introduction to matrices](./tutorials/linear_algebra-matrices.md)|    
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
+ Construct a definition statement for A (use a fixed but arbitary example of A).   
+ Extend and simplify mathematical definitions derived from A to reach B.   
+ When you are asked if A and **only** A is true, then B is true, first suppose A to reach B. Then suppose B to reach A.   

**Induction proof**  
+ Occurs when you need to prove that something is true for all cases.  
+ Start by proving the base case when $n = 1$.  
+ Assume that the case is also true for some integer $k$.  
+ Prove that the case for $k + 1$ also holds i.e. prove the next incremental step up a ladder stretching to infinity.  

**Uniqueness proof**  
+ Occurs when you need to prove that a solution is unique.  
+ Show that there is one solution first.   
+ Show that there is a second solution and that the first and second solutions must be equal.   

## References  
+ A guide to [linear algebra](https://pabloinsente.github.io/intro-linear-algebra) for applied machine learning by Pablo Caceres
+ The [Mathematics for Machine Learning textbook](https://mml-book.github.io/book/mml-book.pdf) by Marc Peter Deisenroth, A Aldo Faisal and Cheng Soon Ong - Cambridge University Press
+ The [Probability for Data Science textbook](https://probability4datascience.com/) by Stanley H Chan - Michigan Publishing
+ The [Probabilistic modelling tutorials](https://betanalpha.github.io/writing/) by Michael Betancourt - GitHub
+ Writing [mathematical operations in LaTex/R](https://en.wikibooks.org/wiki/LaTeX/Mathematics#Fractions_and_Binomials) - Wikibooks
