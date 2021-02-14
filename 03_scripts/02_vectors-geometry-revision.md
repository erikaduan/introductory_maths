Geometry revision
================
Erika Duan
2021-02-07

-   [Resources](#resources)
-   [Introduction to triangles](#introduction-to-triangles)
-   [Triangle inequality theorem](#triangle-inequality-theorem)
-   [Sine, Cosine and Tangent](#sine-cosine-and-tangent)
-   [The Sine rule](#the-sine-rule)
-   [The Cosine rule](#the-cosine-rule)
-   [Cosine similarity](#cosine-similarity)
-   [Soft cosine similarity](#soft-cosine-similarity)
-   [Further reading](#further-reading)

# Resources

This geometry revision section is taken from the unit on
[triangles](https://www.khanacademy.org/math/geometry-home/triangle-properties)
from the Khan Academy and the unit on
[trigonometry](https://www.mathsisfun.com/algebra/trigonometry-index.html)
from MathsisFun.com. All credit should be attributed to these sources.

# Introduction to triangles

A brief revision of triangles is shown below.

<img src="../02_figures/02_vectors-angles-revision-1.jpg" width="80%" style="display: block; margin: auto;" />

Triangles and angles are an important mathematical concept to revise, as
vector similarity is calculated based on concepts from geometry and
trigonometry. The definition of vector norms
i.e. ![\|\|x\|\|](https://latex.codecogs.com/png.latex?%7C%7Cx%7C%7C "||x||")
and how they behave is also derived from insights from trigonometry.

# Triangle inequality theorem

Any side of a triangle must be shorter than the other two sides added
together. If the side is equal to the other two sides, the length of one
side is 0 and the object is a line.

<img src="../02_figures/02_vectors-angles-revision-2.jpg" width="80%" style="display: block; margin: auto;" />

# Sine, Cosine and Tangent

Sine, Cosine and Tangent are just a ratio of two specific sides of a
right angled triangle.

<img src="../02_figures/02_vectors-angles-revision-3.jpg" width="80%" style="display: block; margin: auto;" />

Let us examine the values
![0\\leq \\measuredangle \\leq 90](https://latex.codecogs.com/png.latex?0%5Cleq%20%5Cmeasuredangle%20%5Cleq%2090 "0\leq \measuredangle \leq 90").
The values for Sine and Cosine will always be between 0 and 1 (as the
hypotenus is always equal to or larger than the opposite and the
adjacent).

<img src="../02_figures/02_vectors-angles-revision-4.jpg" width="70%" style="display: block; margin: auto;" />

``` python
#-----draw sine and cosine function in Python-----   
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  

x = np.arange(-2*np.pi, 2*np.pi, 0.1) 
sine = np.sin(x)
cosine = np.cos(x)

# Python allows you to directly plot NumPy array values  

sns.set_style('whitegrid', {
              'grid.linestyle': '--'})

sns.lineplot(x = x, y = sine, label = "Sine wave", lw = 3)
sns.lineplot(x = x, y = cosine, label = "Cosine wave", lw = 3)
```

``` python
plt.xlabel("x")  
plt.ylabel("sin(x) and cos(x)")
plt.legend(loc = "upper right")
plt.show()
```

<img src="02_vectors-geometry-revision_files/figure-gfm/unnamed-chunk-7-1.png" width="672" style="display: block; margin: auto;" />

``` r
#-----draw sine and cosine function in R-----
x <- c(seq(-2*pi, 2*pi, length.out = 100))

sine <- sin(x) # calculate sine
cosine <- cos(x) # calculate cosine  

trig_plot <- tibble(x,
                    sine,
                    cosine)  

ggplot(trig_plot, aes(x, sine)) +
  geom_line(colour = "steelblue", size = 2) +
  geom_line(aes(x, cosine), colour = "firebrick", size = 2) +
  geom_hline(yintercept = 0) + 
  geom_vline(xintercept = 0) +  
  scale_x_continuous(breaks = seq(-2 * pi, 2 * pi , pi / 2),
                     labels = c("-2\u03c0", "-3/2\u03c0", "-1\u03c0", "-1/2\u03c0", "0", "1/2\u03c0", "1\u03c0", "3/2\u03c0", "2\u03c0")) + 
  labs(y = "sin(x) and cos(x)") +   
  theme_bw() + 
  theme(panel.grid.minor = element_blank(),
        panel.grid.major = element_line(linetype = "dotted")) +
  annotate("text", x = 4, y = 1, label = "Sine wave", colour = "steelblue") +
  annotate("text", x = 4, y = 0.9, label = "Cosine wave", colour = "firebrick")
```

<img src="02_vectors-geometry-revision_files/figure-gfm/unnamed-chunk-8-1.png" width="60%" style="display: block; margin: auto;" />

# The Sine rule

The [Sine rule](https://www.mathsisfun.com/algebra/trig-sine-law.html)
applies to all similar triangle types and is useful for solving triangle
angles and lengths. It does not have any direct application to machine
learning algorithms.

<img src="../02_figures/02_vectors-angles-revision-5.jpg" width="80%" style="display: block; margin: auto;" />

# The Cosine rule

In contrast, the [Cosine
rule](https://www.mathsisfun.com/algebra/trig-cosine-law.html) applies
to all triangle types (i.e. not just right-angled triangles) and is
useful for calculating object similarity in machine learning.

In trigonometry, the Cosine rule can be derived to find either an
unknown length given that two sides and the angle between them are
known, or an unknown angle given that all sides of the triangle are
known.

<img src="../02_figures/02_vectors-angles-revision-6.jpg" width="80%" style="display: block; margin: auto;" />

# Cosine similarity

In machine learning, [cosine
similarity](https://en.wikipedia.org/wiki/Cosine_similarity) is a
similarity measurement between two non-zero vectors that is equal to the
cosine of the angle between them. This is the same as calculating the
inner product of two vectors normalised to have norms of 1 (i.e. cosine
similarity only cares about vector direction and not magnitude).

![similarity = \\cos\\theta=\\frac{\\langle x, y\\rangle}{\\lVert x\\rVert \\lVert y \\rVert} = \\frac{\\displaystyle\\sum\_{i=1}^nA\_iB\_i}{\\sqrt{\\displaystyle\\sum\_{i=1}^nA^2\_i} \\times \\sqrt{\\displaystyle\\sum\_{i=1}^nB^2\_i}}](https://latex.codecogs.com/png.latex?similarity%20%3D%20%5Ccos%5Ctheta%3D%5Cfrac%7B%5Clangle%20x%2C%20y%5Crangle%7D%7B%5ClVert%20x%5CrVert%20%5ClVert%20y%20%5CrVert%7D%20%3D%20%5Cfrac%7B%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5EnA_iB_i%7D%7B%5Csqrt%7B%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5EnA%5E2_i%7D%20%5Ctimes%20%5Csqrt%7B%5Cdisplaystyle%5Csum_%7Bi%3D1%7D%5EnB%5E2_i%7D%7D "similarity = \cos\theta=\frac{\langle x, y\rangle}{\lVert x\rVert \lVert y \rVert} = \frac{\displaystyle\sum_{i=1}^nA_iB_i}{\sqrt{\displaystyle\sum_{i=1}^nA^2_i} \times \sqrt{\displaystyle\sum_{i=1}^nB^2_i}}")

In text mining, each unique term is assigned a different dimension, so
cosine similarity calculations tend to be applied to very high
dimensions. A document is then viewed as a vector whose direction is
determined by the proportion of unique terms that it contains.

<img src="../02_figures/02_vectors-angles-revision-7.jpg" width="90%" style="display: block; margin: auto;" />

``` python
#-----calculate cosine similarity in Python via sklearn----- 
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer 
from sklearn.metrics.pairwise import cosine_similarity

documents = ["learning Python and R are not so hard",
             "do I need to learn Python to be a data scientist",
             "R is my favourite data science language",
             "I use excel spreadsheets"]
             
tfidf_vectorizer = TfidfVectorizer()
tfidf_matrix = tfidf_vectorizer.fit_transform(documents) # TF-IDF sparse matrix

doc_term_matrix = tfidf_matrix.todense()
doc_term_df = pd.DataFrame(doc_term_matrix,
                           columns = tfidf_vectorizer.get_feature_names())

doc_term_df
#>         and       are        be  ...  spreadsheets        to      use
#> 0  0.388614  0.388614  0.000000  ...       0.00000  0.000000  0.00000
#> 1  0.000000  0.000000  0.312451  ...       0.00000  0.624903  0.00000
#> 2  0.000000  0.000000  0.000000  ...       0.00000  0.000000  0.00000
#> 3  0.000000  0.000000  0.000000  ...       0.57735  0.000000  0.57735
#> 
#> [4 rows x 22 columns]
```

``` python
cosine_similarity(tfidf_matrix, tfidf_matrix)
#> array([[1.       , 0.0754757, 0.       , 0.       ],
#>        [0.0754757, 1.       , 0.0819141, 0.       ],
#>        [0.       , 0.0819141, 1.       , 0.       ],
#>        [0.       , 0.       , 0.       , 1.       ]])
```

# Soft cosine similarity

An obvious weakness of the cosine similarity matrix is that
![n](https://latex.codecogs.com/png.latex?n "n") terms are arbitarily
assigned a dimension in
![{\\rm I\\!R}^n](https://latex.codecogs.com/png.latex?%7B%5Crm%20I%5C%21R%7D%5En "{\rm I\!R}^n"),
regardless of similarities or differences in their semantics. Soft
cosine similarity first implements word to vector embeddings, which
allows terms with similar meanings be more closely localised together
within the vector space.

According to
[Wikipedia](https://en.wikipedia.org/wiki/Cosine_similarity#Soft_cosine_measure),
to calculate the soft cosine, an additional matrix
![s](https://latex.codecogs.com/png.latex?s "s") is used to indicate
similarity between features, as calculated through the Levenshtein
distance, WordNet similarity or other measures. In practice, we use
pre-built word embedding models like `word2vec`, `fasttext` and others,
which have been built by training large corpuses of publicly available
text data.

<img src="../02_figures/02_vectors-angles-revision-8.png" width="80%" style="display: block; margin: auto;" />

# Further reading

-   A great
    [post](https://blog.christianperone.com/2013/09/machine-learning-cosine-similarity-for-vector-space-models-part-iii/)
    explaining the maths behind vector dot products and cosine
    similarity.

-   A [post](https://www.machinelearningplus.com/nlp/cosine-similarity/)
    explaining the different between cosine similarity and soft cosine
    similarity.

-   A [guide](https://www.machinelearningplus.com/nlp/gensim-tutorial/)
    to the Python Gensim package, which is useful for creating word to
    vector embeddings.
