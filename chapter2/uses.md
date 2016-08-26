# Uses of $$\Sigma$$ and $$\Pi$$ Notation

Here we focus on common uses of $$\Sigma$$ and $$\Pi$$ Notation within the GISciences.

## General descriptive statistics

* Mean: take the sum of a set of elements, $$x$$ and multiply by the reciprocal of the length of the set. 

$$\displaystyle\overline{m} = \frac{1}{n}\sum_{i=1}^{n}x_{i}$$

* Variance (of a discrete random variable), describing how far the observed values are from the expected mean or what is the sum of the squared deviations of all observations from the mean.  

$$\displaystyle \mu = \sum_{i=1}^{n}p_{i}\cdot (x_{i} - \sigma)^{2}$$

You will also see $$Var(x)$$ in place of $$\mu$$.  The meaning is the same.  For the above $$\sigma$$ is expected to be

$$\displaystyle \sigma = \sum_{i=1}^{n} p_{i} \cdot x_{i}$$

and $$p$$ is a probability density functions (that we will talk about in coming weeks), e.g. a normal distribution.

$$\displaystyle f(x) = \frac{1}{\sqrt{2\pi \sigma^{2}}}e^{-\frac{(x-\mu)^{2}}{2\sigma^{2}}}$$

Here the goal is to just see the summation notation in action and have a general idea of what the variance equation is doing.  $$\sigma$$ and $$\mu$$ can be viewed as 'black box' variables where something else is going on.


* Standard Deviation

$$\displaystyle\sqrt\frac{\sum_{i=1}^{n}(x_{i} - \overline{x})^{2}}{(n - 1)}$$

Here $$x$$ is the value of some observation, $$\overline{x}$$ is the mean of the set of all $$x$$ and $$n$$ is the number of elements in $$x$$ (or more formally, the population size).  In a spatial analysis context, you will sometimes see the denominator of a statistics as $$n$$ instead of $$n-1$$ in instances where the population size is known.

## Linear Regression
Linear regresssion is one way to model a linear relationship between a dependent variable and some number of independent variables.  For example, the number of snowy days (dependent) might have a linear relationship with elevation (independent).  We could try to model that relationship with linear regression.

If you have never taken a statistics class, no need to worry.  The goal here is simply to demonstrate how summation notation is used in the context of linear regression.


![](images/ols.png)Here we see a population (black dots) and a best fit line.

The relationship between these variables is modeled as $$ y = \approx \beta_{0} + \beta_{1} \cdot X$$ or the dependent variable is approximately equal to the intercept plus the slope of the line times $$X$$.  This is a linear function.

How then do we estimate $$\hat{\beta}_{0} $$and $$\hat{\beta}_{1}$$?  We can do this using summation!

As a quick aside, compare $$\beta_{0}$$ and $$\hat{\beta}_{0}$$.  The hat here means predicted value.  Looking at the image above, we can clearly see that the function describing the blue line ($$y = mx + b$$) will sometimes be close to the correct estimate and other times be quite divergent.

Back to estimation.  We can find the best fit coefficients using the following formula (derived using calculus that we are not worried about here).

$$\displaystyle\hat{\beta}_{1} = \frac{\sum_{i=1}^{n}(x_{i} - \overline{x})(y_{i} - \overline{y})}{\sum_{i=1}^{n}(x_{i} - \overline{x})^{2}}$$

and

$$\displaystyle\hat{\beta}_{0} = \overline{y} - \hat{\beta}_{1}\overline{x}$$.

$$\overline{x}$$ and $$\overline{y}$$ are the sample means.

The formula for estimating $$\hat{\beta}_{1}$$ moves the start and stop notation from the top and bottom, respictively to the right hand side.  This is just another way that you might encounter a forumla notated.  The meaning is exactly the same.

## Computational Geometry

Here the topics get a bit closer to what is occuring under the hood of a Geographic Information System.  Much of the foundational GIS work come from geometry and more recently [computational geometry](https://en.wikipedia.org/wiki/Computational_geometry).

* Length of a line

First, let's start with the length of a line segment composed of two points.  We know that in [Euclidean space](https://en.wikipedia.org/wiki/Euclidean_space) the distance between any two points is defined by the [Pythagorean theorem](https://en.wikipedia.org/wiki/Pythagorean_theorem):

$$d = \sqrt{(x_{2} - x_{1})^{2} + (y_{2} - y_{1})^{2}}$$

Therefore, it is possible to utilize Sigma notation to formulate the computation of the total line length as the sum of the lengths of the segments:

$$\displaystyle\sum_{i=1}^{n - 1}d(x_{i}, x_{i+1})$$,

where $$d()$$ is a function that computes the Euclidean distance between $$x_{i}$$ and the next point in the set $$x_{i+1}$$, and $$n$$ is the total number of vertices in the line. 

* Area of a [simple polygon](https://en.wikipedia.org/wiki/Simple_polygon)

Frequently, we utilize a GIS to compute the area of 2-dimensional vector features.  For example, if we want to know the area of all the residential lots in Tempe, we would need to first be able to compute the area of each individual lot.  Then it is possible to use the same strategy as above - define the single entity function and then nest said function inside Sigma notation.  Assuming every residential lot in Tempe is a simple polygon, we could forumulate the area function as:

$$\displaystyle A = \sum_{k=1}^{n}\frac{(x_{k+1} + x_{k})(y_{k+1} - y_{k})}{2}$$, 

where $$A$$ is the area, $$k$$ is the k-th point in the set of counter-clockwise sorted points, and (x,y) are the vertex (point) coordinates.

For those of you that are interested - this is a derivation of [Green's Theorm](https://en.wikipedia.org/wiki/Green%27s_theorem)

* Average nearest neighbor distance

As a final example, in spatial point pattern analysis, it is frequently desirable to know the distance between a given point and the nearest neighbor, for example to compute a G-function ($$\hat{G}(d)$$).

Average nearest neighbor distance can be formulated by first computing the distance between a point and all other points or $$minimum(d(i,j)) \forall i \neq j$$.  Textually, compute the minimum distance ($$minimum(d(i,j))$$ between a point $$i$$ and all of the other points $$j$$ in a set.  This notation assumes that the sets of points $$\{i\}$$ and $$\{j\}$$ are the refering to the same point set ($$points = i = j$$).

The mean nearest neighbor distance is then:

$$\displaystyle\sum_{i=1}^{n}\frac{d_{i}}{n}$$, 

where $$d_{i}$$ is the distance between observation $$i$$ and its nearest neighbor.



