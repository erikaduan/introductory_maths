Probability theory - introduction
================
Erika Duan
2022-03-19

-   [Introduction to probability](#introduction-to-probability)
    -   [Set operations](#set-operations)
-   [Resources](#resources)

# Introduction to probability

Probability is an abstract concept. The frequentist approach considers
probability as the relative frequency of a specific outcome, observed
for a sample of the true population. The Bayesian approach considers
probability as a subjective possibility space dependent on the prior
hypothesis and the observed evidence.

Probability can be best thought of as the size of a mathematical set
(which can be represented in 2D as a proportion of total space).

### Scenario 1

Imagine that we simultaneously roll two fair dice. What is the
probability that the sum of two dice equals 5?

-   We would first need to calculate all possible combinations of the
    dice rolls. The total number of possible combinations is the
    **sample space** i.e. the set of all possible outcomes. As there are
    6 faces on one dice and we are rolling two dice, the sample space is
    ![6\\times6](https://latex.codecogs.com/svg.format?6%5Ctimes6 "6\times6")
    or ![6^2](https://latex.codecogs.com/svg.format?6%5E2 "6^2")
    possible outcomes.  
-   We would then calculate all possible combinations of dice rolls
    which sum to 5. This is the **event**, which is a smaller subset of
    the sample space.  
-   The **probability** of the event occurring is therefore the ratio of
    the event relative to the sample space.  
-   In this scenario, the probability that the sum of two dice equals 5
    is
    ![\\frac{4}{36}](https://latex.codecogs.com/svg.format?%5Cfrac%7B4%7D%7B36%7D "\frac{4}{36}")
    or approximately 0.11.

<img src="../figures/probability-introduction_to_probability-scenario_1.svg" width="60%" style="display: block; margin: auto;" />

### Scenario 2

Imagine that we simultaneously roll two fair dice. What is the
probability that the sum of two dice is less than 5 and an odd number?

-   The sample space is still the same, as the total number of possible
    dice roll combinations is fixed.  
-   The event subset has changed as we are interested in the
    intersection of
    ![E_1 \\subset \\{2, 3, 4\\}](https://latex.codecogs.com/svg.format?E_1%20%5Csubset%20%5C%7B2%2C%203%2C%204%5C%7D "E_1 \subset \{2, 3, 4\}")
    and
    ![E_2 \\subset \\{2, 4\\}](https://latex.codecogs.com/svg.format?E_2%20%5Csubset%20%5C%7B2%2C%204%5C%7D "E_2 \subset \{2, 4\}")
    or
    ![E= E_1 \\cap E_2 = \\{2, 4\\}](https://latex.codecogs.com/svg.format?E%3D%20E_1%20%5Ccap%20E_2%20%3D%20%5C%7B2%2C%204%5C%7D "E= E_1 \cap E_2 = \{2, 4\}").  
-   In this scenario, the probability that the sum of two dice is less
    than 5 and an odd number is
    ![\\frac{4}{36}](https://latex.codecogs.com/svg.format?%5Cfrac%7B4%7D%7B36%7D "\frac{4}{36}")
    or approximately 0.11.

<img src="../figures/probability-introduction_to_probability-scenario_2.svg" width="70%" style="display: block; margin: auto;" />

## Set operations

# Resources

-   The [Probability for Data Science
    textbook](https://probability4datascience.com/) by Stanley H Chan,
    specifically [Chapter
    2](https://drive.google.com/file/d/1v9jLsbwG5Tl5d7XfLCfmhHuOkZZUOVNa/view)
    on probability  
-   Introduction to probability theory [GitHub
    resource](https://betanalpha.github.io/assets/case_studies/probability_theory.html)
    by Michael Betancourt  
-   Introduction to probability theory [Youtube
    series](https://www.youtube.com/playlist?list=PLUl4u3cNGP60hI9ATjSFgLZpbNJ7myAg6)
    from MIT
