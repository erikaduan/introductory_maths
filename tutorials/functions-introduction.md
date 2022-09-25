Introduction to functions
================
Erika Duan
2022-09-25

-   [Properties of functions](#properties-of-functions)
-   [Finding the function limit](#finding-the-function-limit)
-   [The Squeeze theorem](#the-squeeze-theorem)
-   [Continuity](#continuity)
-   [Intermediate value theorem](#intermediate-value-theorem)
-   [Resources](#resources)

# Properties of functions

A **function** can be thought of as a rule that maps each element
![x](https://latex.codecogs.com/svg.format?x "x") in set A to exactly
one element
![y=f(x)](https://latex.codecogs.com/svg.format?y%3Df%28x%29 "y=f(x)")
in set B.

-   The domain of
    ![f: A \\to B](https://latex.codecogs.com/svg.format?f%3A%20A%20%5Cto%20B "f: A \to B")
    is the set A, which is usually
    ![\\mathbb{R}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D "\mathbb{R}")
    or
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   The domain can be restricted by the function form. For
    ![f(x) = \\sqrt{x_2-4}](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%20%5Csqrt%7Bx_2-4%7D "f(x) = \sqrt{x_2-4}"),
    the domain is
    ![\\{x \\in \\mathbb{R} \| x \\geq 2](https://latex.codecogs.com/svg.format?%5C%7Bx%20%5Cin%20%5Cmathbb%7BR%7D%20%7C%20x%20%5Cgeq%202 "\{x \in \mathbb{R} | x \geq 2")
    or
    ![x \\leq -2 \\}](https://latex.codecogs.com/svg.format?x%20%5Cleq%20-2%20%5C%7D "x \leq -2 \}")
    or
    ![(- \\infty, -2\] \\cup \[2, \\infty )](https://latex.codecogs.com/svg.format?%28-%20%5Cinfty%2C%20-2%5D%20%5Ccup%20%5B2%2C%20%5Cinfty%20%29 "(- \infty, -2] \cup [2, \infty )").  
-   The co-domain of
    ![f: A \\to B](https://latex.codecogs.com/svg.format?f%3A%20A%20%5Cto%20B "f: A \to B")
    is the set B, which is usually
    ![\\mathbb{R}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D "\mathbb{R}")
    or
    ![\\mathbb{R}^n](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D%5En "\mathbb{R}^n").  
-   The range of
    ![f: A \\to B](https://latex.codecogs.com/svg.format?f%3A%20A%20%5Cto%20B "f: A \to B")
    is
    ![R(f) = \\{y \| y = f(x)](https://latex.codecogs.com/svg.format?R%28f%29%20%3D%20%5C%7By%20%7C%20y%20%3D%20f%28x%29 "R(f) = \{y | y = f(x)")
    for some
    ![x \\in A\\}](https://latex.codecogs.com/svg.format?x%20%5Cin%20A%5C%7D "x \in A\}").
-   The range is more restricted than the co-domain. For
    ![f(x) = sin(x)](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%20sin%28x%29 "f(x) = sin(x)"),
    the co-domain is
    ![\\mathbb{R}](https://latex.codecogs.com/svg.format?%5Cmathbb%7BR%7D "\mathbb{R}")
    and the range is
    ![\[-1, 1\]](https://latex.codecogs.com/svg.format?%5B-1%2C%201%5D "[-1, 1]").

<img src="../figures/functions-simple_function_example.svg" width="80%" style="display: block; margin: auto;" />

For ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") and
![g(x)](https://latex.codecogs.com/svg.format?g%28x%29 "g(x)"), if the
range of ![g(x)](https://latex.codecogs.com/svg.format?g%28x%29 "g(x)")
is in the domain of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)"), the
**function composite**
![(f\\circ g)(x) = f(g(x))](https://latex.codecogs.com/svg.format?%28f%5Ccirc%20g%29%28x%29%20%3D%20f%28g%28x%29%29 "(f\circ g)(x) = f(g(x))")
exists. For example, if
![f(x) = log(x)](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%20log%28x%29 "f(x) = log(x)")
and
![g(x) = \\sqrt{x+1}](https://latex.codecogs.com/svg.format?g%28x%29%20%3D%20%5Csqrt%7Bx%2B1%7D "g(x) = \sqrt{x+1}"),
then
![(f\\circ g)(x)=log(\\sqrt{x+1})](https://latex.codecogs.com/svg.format?%28f%5Ccirc%20g%29%28x%29%3Dlog%28%5Csqrt%7Bx%2B1%7D%29 "(f\circ g)(x)=log(\sqrt{x+1})")
and
![(g\\circ f)(x) = \\sqrt{log(x)+1}](https://latex.codecogs.com/svg.format?%28g%5Ccirc%20f%29%28x%29%20%3D%20%5Csqrt%7Blog%28x%29%2B1%7D "(g\circ f)(x) = \sqrt{log(x)+1}").

# Finding the function limit

The limit of a function
![lim\_{x \\to a} f(x) = L](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28x%29%20%3D%20L "lim_{x \to a} f(x) = L")
comprises values of
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") for
values of ![x](https://latex.codecogs.com/svg.format?x "x") close to but
not equal to ![a](https://latex.codecogs.com/svg.format?a "a"). This is
equivalent to saying that
![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)")
approaches the limit ![L](https://latex.codecogs.com/svg.format?L "L")
as ![x](https://latex.codecogs.com/svg.format?x "x") approaches
![a](https://latex.codecogs.com/svg.format?a "a").

The **formal definition** of a function limit involves:

-   Choose
    ![\\epsilon](https://latex.codecogs.com/svg.format?%5Cepsilon "\epsilon")
    and
    ![\\delta](https://latex.codecogs.com/svg.format?%5Cdelta "\delta")
    such that
    ![\\epsilon \> 0](https://latex.codecogs.com/svg.format?%5Cepsilon%20%3E%200 "\epsilon > 0")
    and
    ![\\delta \> 0](https://latex.codecogs.com/svg.format?%5Cdelta%20%3E%200 "\delta > 0").  
-   Solve
    ![0 \< \|x-a\| \< \\delta](https://latex.codecogs.com/svg.format?0%20%3C%20%7Cx-a%7C%20%3C%20%5Cdelta "0 < |x-a| < \delta").  
-   Confirm that when
    ![x \\neq a](https://latex.codecogs.com/svg.format?x%20%5Cneq%20a "x \neq a"),
    ![\|f(x) - L\| \< \\epsilon](https://latex.codecogs.com/svg.format?%7Cf%28x%29%20-%20L%7C%20%3C%20%5Cepsilon "|f(x) - L| < \epsilon").

This method is not used in practice as it is very laborious to find
![\\delta](https://latex.codecogs.com/svg.format?%5Cdelta "\delta"). For
example, in order to verify that
![lim\_{x \\to a} x^2 = 4](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20x%5E2%20%3D%204 "lim_{x \to a} x^2 = 4"),
we need to:

-   Factorise
    ![\|x^2 - 4\| \< \\epsilon](https://latex.codecogs.com/svg.format?%7Cx%5E2%20-%204%7C%20%3C%20%5Cepsilon "|x^2 - 4| < \epsilon")
    into
    ![\|x - 2\|\|x + 2\| \< \\epsilon](https://latex.codecogs.com/svg.format?%7Cx%20-%202%7C%7Cx%20%2B%202%7C%20%3C%20%5Cepsilon "|x - 2||x + 2| < \epsilon").  
-   Manually calculate what happens to the
    ![\|x + 2\|](https://latex.codecogs.com/svg.format?%7Cx%20%2B%202%7C "|x + 2|")
    when
    ![\|x - 2\| \< 1](https://latex.codecogs.com/svg.format?%7Cx%20-%202%7C%20%3C%201 "|x - 2| < 1").
    When
    ![\|x - 2\| \< 1](https://latex.codecogs.com/svg.format?%7Cx%20-%202%7C%20%3C%201 "|x - 2| < 1"),
    ![1 \< x \< 3](https://latex.codecogs.com/svg.format?1%20%3C%20x%20%3C%203 "1 < x < 3")
    and therefore
    ![3 \< x + 2 \< 5](https://latex.codecogs.com/svg.format?3%20%3C%20x%20%2B%202%20%3C%205 "3 < x + 2 < 5").  
-   Substitute
    ![3 \< x + 2 \< 5](https://latex.codecogs.com/svg.format?3%20%3C%20x%20%2B%202%20%3C%205 "3 < x + 2 < 5")
    into
    ![\|x - 2\|\|x + 2\| \< \\epsilon](https://latex.codecogs.com/svg.format?%7Cx%20-%202%7C%7Cx%20%2B%202%7C%20%3C%20%5Cepsilon "|x - 2||x + 2| < \epsilon").
    Therefore
    ![\|x - 2\|\|x + 2\| \< 5\|x - 2\| \< \\epsilon](https://latex.codecogs.com/svg.format?%7Cx%20-%202%7C%7Cx%20%2B%202%7C%20%3C%205%7Cx%20-%202%7C%20%3C%20%5Cepsilon "|x - 2||x + 2| < 5|x - 2| < \epsilon").  
-   Therefore, when
    ![5\|x - 2\| \< \\epsilon](https://latex.codecogs.com/svg.format?5%7Cx%20-%202%7C%20%3C%20%5Cepsilon "5|x - 2| < \epsilon"),
    ![\|x + 2\| \< 1](https://latex.codecogs.com/svg.format?%7Cx%20%2B%202%7C%20%3C%201 "|x + 2| < 1")
    and
    ![\|x + 2\| \< \\tfrac{\\epsilon}{5}](https://latex.codecogs.com/svg.format?%7Cx%20%2B%202%7C%20%3C%20%5Ctfrac%7B%5Cepsilon%7D%7B5%7D "|x + 2| < \tfrac{\epsilon}{5}").  
-   Therefore
    ![\\delta = min(1, \\tfrac{\\epsilon}{5})](https://latex.codecogs.com/svg.format?%5Cdelta%20%3D%20min%281%2C%20%5Ctfrac%7B%5Cepsilon%7D%7B5%7D%29 "\delta = min(1, \tfrac{\epsilon}{5})").

As a matter of pragmatism, to find the function limit, we simplify the
function or composite function using the limit laws.

<img src="../figures/functions-limit_laws.svg" width="80%" style="display: block; margin: auto;" />

**Note:** For non-arbitrary or non-split functions, a consequence of the
limit laws is that
![lim\_{x \\to a} f(x) = f(a)](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28x%29%20%3D%20f%28a%29 "lim_{x \to a} f(x) = f(a)")
when ![a](https://latex.codecogs.com/svg.format?a "a") is in the domain
of ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)").

Types of limits:

-   Left limit: if
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    defined for all
    ![x \< a](https://latex.codecogs.com/svg.format?x%20%3C%20a "x < a")
    where ![x](https://latex.codecogs.com/svg.format?x "x") is near
    ![a](https://latex.codecogs.com/svg.format?a "a").  
-   Right limit: if
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    defined for all
    ![x \> a](https://latex.codecogs.com/svg.format?x%20%3E%20a "x > a")
    where ![x](https://latex.codecogs.com/svg.format?x "x") is near
    ![a](https://latex.codecogs.com/svg.format?a "a").  
-   Limit at infinity: if
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    defined for all sufficiently large positive values of
    ![x](https://latex.codecogs.com/svg.format?x "x") and
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    close enough to L.  
-   Limit at negative infinity: if
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    defined for all sufficiently small positive values of
    ![x](https://latex.codecogs.com/svg.format?x "x") and
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    close enough to L.

<img src="../figures/functions-limit_types.svg" width="80%" style="display: block; margin: auto;" />

**Note:** Not all functions have limits. For
![lim\_{x \\to \\infty} (x+1)](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20%5Cinfty%7D%20%28x%2B1%29 "lim_{x \to \infty} (x+1)"),
the limit is
![\\infty](https://latex.codecogs.com/svg.format?%5Cinfty "\infty") and
is therefore undefined. A function only has a limit if the left limit
and right limit are defined and equal to each other.

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot f(x) = x^2 --------------------------------------------------------------
set.seed(111)

p1 <- ggplot(data.frame(x = runif(1000, -20, 20)), aes(x)) +
  geom_function(fun = ~ (.x)^2) +
  xlim(-4, 4) + 
  ylim(-1, 4) + 
  labs(title = "f(x) = x^2") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 1.4, y = -0.2, label = "D: (-infinity, infinity)") +
  annotate("text", x = 1.4, y = -0.5, label = "R: [0, infinity)") +
  annotate("text", x = 1.4, y = -0.8, label = "Undefined limit at infinity")  

# Plot f(x) = abs(x)/x ---------------------------------------------------------
set.seed(111)

p2 <- ggplot(data.frame(x = runif(1000, -20, 20)), aes(x)) +
  geom_function(fun = ~ abs(.x)/.x) +
  geom_vline(xintercept = 0, linetype = "dotted") + 
  xlim(-4, 4) + 
  ylim(-1, 4) + 
  labs(title = "f(x) = abs(x)/x") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 1.8, y = -0.2, label = "D: (-infinity, infinity)") +
  annotate("text", x = 1.8, y = -0.5, label = "R: -1 or 1") +
  annotate("text", x = 1.8, y = -0.8, label = "Undefined limit at infinity")

# Plot ggplot figures side by side --------------------------------------------- 
p1 + p2
```

<img src="functions-introduction_files/figure-gfm/unnamed-chunk-5-1.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

# The Squeeze theorem

The **Squeeze theorem** allows us to define the limit of a function
based on an understanding of the lower and upper boundaries of a related
function.

Let ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)"),
![g(x)](https://latex.codecogs.com/svg.format?g%28x%29 "g(x)") and
![h(x)](https://latex.codecogs.com/svg.format?h%28x%29 "h(x)") exist
where
![f(x) \\leq g(x) \\leq h(x)](https://latex.codecogs.com/svg.format?f%28x%29%20%5Cleq%20g%28x%29%20%5Cleq%20h%28x%29 "f(x) \leq g(x) \leq h(x)").
For all values of ![x](https://latex.codecogs.com/svg.format?x "x")
sufficiently close to ![a](https://latex.codecogs.com/svg.format?a "a"),
suppose that
![lim\_{x \\to a} f(x) = lim\_{x \\to a} h(x) = L](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28x%29%20%3D%20lim_%7Bx%20%5Cto%20a%7D%20h%28x%29%20%3D%20L "lim_{x \to a} f(x) = lim_{x \to a} h(x) = L"),
then
![lim\_{x \\to a} g(x) = L](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20g%28x%29%20%3D%20L "lim_{x \to a} g(x) = L").

For example, to find
![lim\_{x \\to a} x sin(\\tfrac{1}{x})](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20x%20sin%28%5Ctfrac%7B1%7D%7Bx%7D%29 "lim_{x \to a} x sin(\tfrac{1}{x})"),
we start by knowing that
![-1\\leq sin(x) \\leq1](https://latex.codecogs.com/svg.format?-1%5Cleq%20sin%28x%29%20%5Cleq1 "-1\leq sin(x) \leq1")
and therefore that
![-x\\leq xsin(x) \\leq x](https://latex.codecogs.com/svg.format?-x%5Cleq%20xsin%28x%29%20%5Cleq%20x "-x\leq xsin(x) \leq x")
for all
![x \\neq 0, x \>0](https://latex.codecogs.com/svg.format?x%20%5Cneq%200%2C%20x%20%3E0 "x \neq 0, x >0").
The right limit of ![-x](https://latex.codecogs.com/svg.format?-x "-x")
as it approaches 0 is 0 and the right limit of
![x](https://latex.codecogs.com/svg.format?x "x") as it approaches 0 is
also 0. Therefore
![lim\_{x \\to a} x sin(\\tfrac{1}{x}) = 0](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20x%20sin%28%5Ctfrac%7B1%7D%7Bx%7D%29%20%3D%200 "lim_{x \to a} x sin(\tfrac{1}{x}) = 0")
by the Squeeze theorem.

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot f(x) = x * sin(x) -------------------------------------------------------
set.seed(111)

p1 <- ggplot(data.frame(x = runif(1000, -20, 20)), aes(x)) +
  geom_function(fun = ~ (.x) * sin(.x)) +
  labs(title = "f(x) = x sin(x)") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 1.4, y = -18, label = "Limit as x approaches 0: 0")  

# Plot f(x) = sin(x)/x ---------------------------------------------------------
set.seed(111)

p2 <- ggplot(data.frame(x = runif(1000, -20, 20)), aes(x)) +
  geom_function(fun = ~ sin(.x)/.x) +
  labs(title = "f(x) = sin(x)/x") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 1.8, y = -0.8, label = "Limit as x approaches 0: 1")

# Plot ggplot figures side by side --------------------------------------------- 
p1 + p2
```

<img src="functions-introduction_files/figure-gfm/unnamed-chunk-6-1.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

# Continuity

A function is **continuous** at point
![a](https://latex.codecogs.com/svg.format?a "a") if:

-   ![f(a)](https://latex.codecogs.com/svg.format?f%28a%29 "f(a)") is
    defined
    i.e. ![a \\in](https://latex.codecogs.com/svg.format?a%20%5Cin "a \in")
    domain of
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") and
    ![lim\_{x \\to a} f(x) = f(a)](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28x%29%20%3D%20f%28a%29 "lim_{x \to a} f(x) = f(a)").  
-   ![lim\_{x \\to a} f(x)](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28x%29 "lim_{x \to a} f(x)")
    exists i.e. the right limit and left limit both exist and are equal
    to each other as ![x](https://latex.codecogs.com/svg.format?x "x")
    approaches ![a](https://latex.codecogs.com/svg.format?a "a") for
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)").  
-   By geometric intuition, if
    ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") is
    continuous as point
    ![x = a](https://latex.codecogs.com/svg.format?x%20%3D%20a "x = a"),
    the points
    ![(x, f(x))](https://latex.codecogs.com/svg.format?%28x%2C%20f%28x%29%29 "(x, f(x))")
    continue to approach the point
    ![(a, f(a))](https://latex.codecogs.com/svg.format?%28a%2C%20f%28a%29%29 "(a, f(a))")
    and there is no gap in the graph.

If
![f(x), g(x)](https://latex.codecogs.com/svg.format?f%28x%29%2C%20g%28x%29 "f(x), g(x)")
are continuous on some domain and
![c](https://latex.codecogs.com/svg.format?c "c") is a constant, then
the functions formed from
![f(x) \\pm g(x)](https://latex.codecogs.com/svg.format?f%28x%29%20%5Cpm%20g%28x%29 "f(x) \pm g(x)"),
![cf(x)](https://latex.codecogs.com/svg.format?cf%28x%29 "cf(x)"),
![(f\\circ g)(x)](https://latex.codecogs.com/svg.format?%28f%5Ccirc%20g%29%28x%29 "(f\circ g)(x)"),
and
![\\tfrac{f(x)}{g(x)}](https://latex.codecogs.com/svg.format?%5Ctfrac%7Bf%28x%29%7D%7Bg%28x%29%7D "\tfrac{f(x)}{g(x)}")
are all continuous.

If
![lim\_{x \\to a} g(x) = b](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20g%28x%29%20%3D%20b "lim_{x \to a} g(x) = b"),
then
![lim\_{x \\to a} f(g(x)) = f(lim\_{x \\to a}g(x)) = f(b)](https://latex.codecogs.com/svg.format?lim_%7Bx%20%5Cto%20a%7D%20f%28g%28x%29%29%20%3D%20f%28lim_%7Bx%20%5Cto%20a%7Dg%28x%29%29%20%3D%20f%28b%29 "lim_{x \to a} f(g(x)) = f(lim_{x \to a}g(x)) = f(b)").

<details>
<summary>
R code
</summary>
<p>

``` r
# Plot f(x) = 1/x --------------------------------------------------------------
set.seed(111)

p1 <- ggplot(data.frame(x = runif(1000, -20, 20)), aes(x)) +
  geom_function(fun = ~ 1/(.x)) +
  xlim(-6, 6) + 
  ylim(-6, 6) + 
  labs(title = "f(x) = 1/x") +  
  theme_minimal() + 
  theme(panel.border = element_rect(fill = NA),
        panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 0, y = -5, label = "f(x) is continuous but undefined at x = 0")  

p1
```

<img src="functions-introduction_files/figure-gfm/unnamed-chunk-7-1.png" width="80%" style="display: block; margin: auto;" />

</p>
</details>
<p>

**Note:** Rather than saying that
![f(x) = 1/x](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%201%2Fx "f(x) = 1/x")
is discontinuous because f(0) is undefined, we can say that
![f(x) = 1/x](https://latex.codecogs.com/svg.format?f%28x%29%20%3D%201%2Fx "f(x) = 1/x")
is continuous for
![x \\neq 0](https://latex.codecogs.com/svg.format?x%20%5Cneq%200 "x \neq 0").

# Intermediate value theorem

The intermediate value theorem extends ideas from the Squeeze theorem.
It is mainly used to judge whether a solution will exist between a
specific interval of values in the domain.

Let ![f(x)](https://latex.codecogs.com/svg.format?f%28x%29 "f(x)") be
continuous along the closed interval
![\[a, b\]](https://latex.codecogs.com/svg.format?%5Ba%2C%20b%5D "[a, b]")
where ![v](https://latex.codecogs.com/svg.format?v "v") is a number
between ![f(a)](https://latex.codecogs.com/svg.format?f%28a%29 "f(a)")
and ![f(b)](https://latex.codecogs.com/svg.format?f%28b%29 "f(b)").
There exists a number
![c \\in \[a,b\]](https://latex.codecogs.com/svg.format?c%20%5Cin%20%5Ba%2Cb%5D "c \in [a,b]")
such that
![f(c) = v](https://latex.codecogs.com/svg.format?f%28c%29%20%3D%20v "f(c) = v").

<img src="../figures/functions-intermediate_value_theorem.svg" width="80%" style="display: block; margin: auto;" />

# Resources

-   Lectures and exercises from the Khan academy [functions
    unit](https://www.khanacademy.org/math/algebra/x2f8bb11595b61c86:functions).
