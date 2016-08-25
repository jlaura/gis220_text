# Sigma Notation

The Greek capital letter $$\Sigma$$ (Sigma) is used to represent summation.  The most general $$\Sigma$$ notation describes the sum of some unknown number of elements.

$$\displaystyle\sum\limits x_{i} = x_{1} + x_{2} + x_{3} + \ldots + x_{i}$$

To the right of the $$\sigma$$ is the *term* that is being summed.  In this case, the term is simply $$x$$.  We can not evaluate the above.  Where do we start?  Where do we stop?  These conditions are defined by two additional elements.  

$$\displaystyle\sum\limits_{1}^{4} 5 = 5+5+5+5$$

The bottom element tells us inclusively where to start and the top element is the termination condition.  In the above example we start counting at 1 and stop counting at 4.  The term is a constant, so we add 5 together 4 times.  Now we can evaluate the summation:

$$\displaystyle\sum\limits_{1}^{4} 5 = 20$$

The notation above is not too flexible because the start, stop, and term are all hard coded.  If we wanted to sum the number of neighbors to each county in Arizona, we would need to write 15 different summations (assuming all 15 counties have a different number of neighbors) with the start and stop parameters defined by the number of neighbors.  Something along the lines of:

|**County**|**Notation**|
|----------|------------|
|Apache| $$\displaystyle\sum\limits_{1}^{2} 1 = 1 + 1$$|
|Cochise| $$\displaystyle\sum\limits_{1}^{3} 1 = 1 + 1 + 1$$|
|Coconino| $$\displaystyle\sum\limits_{1}^{4} 1 = 1 + 1 + 1 + 1$$|
| ... | ...|
|Yuma | $$\displaystyle\sum\limits_{1}^{3} 1 = 1 + 1 + 1$$|


Clearly, this style of notation is not really very portable (or useful - we have to compute the answer to define the upper bound).  

## Variables in the term

To solve the above problem, we need to generalize the summation.  The first (but not final) step in doing this is to introduce a variable into the bottom start location and the term.

$$\displaystyle\sum\limits_{i=1}^{4} i = 1 + 2 + 3 + 4 = 10$$

Using either the fixed or variable start notation, we can have an arbitrary starting point.

$$\displaystyle\sum\limits_{i=-1}^{4} i = -1 + 0 + 1 + 2 + 3 + 4$$

or

$$\displaystyle\sum\limits_{i=-5}^{5} i = -5 + -4 + -3 + -2 + -1 + 0 + 1 + 2 + 3 + 4 + 5$$

or

$$\displaystyle\sum\limits_{i=2}^{5} i = 2 + 3 + 4 + 5$$

Using a variable does not preclude the multiplication we achieved above ($$\displaystyle\sum\limits_{1}^{4} 5$$) can be rewritten such that the variable is defined in the start but never used:

$$\displaystyle\sum\limits_{i=1}^{4} 5 = 20$$

Using a variable, we can also write more complex logic into the start.  For example, it is possible to use a subset of numbers.  Imagine that we define a set of even integers in the interval [0,4]: $$j = {0,2,4}$$.  We can then use this variable in a summation:

$$\displaystyle\sum\limits_{i | i \in j} i = 0 + 2 + 4$$

## More complex terms

The addition of a variable in the term adds flexability, but not enough to be really useful.  What is required is to have, potentially, more complex terms.  For example, the sum of the squared terms could be written as:

$$\displaystyle\sum\limits_{i=1}^{4} x^{2} = 1^{2} + 2^{2} + 3^{2} + 4^{2}$$

## Nesting and inclusion with other notation
It is possible to include sigma notation within other formula, functions, or equations.  For example:

$$\overline{m} = \frac{1}{n}\displaystyle\sum\limits_{i=1}^{n}a_{i}$$

The variable $$m$$ equal to the sum of the terms from 1 to $$n$$ times $$\frac{1}{n}$$, or the mean.

We can also nest sigmas  

$$\displaystyle\sum\limits_{i=1}^{2}\displaystyle\sum\limits_{j=2}^{4}ij = (i_{1}*2 + i_{2}*3 + i_{3}*4) + (i_{2} * 2 + i_{2} * 3 + i_{2} * 4)$$

$$ = 1*2 + 1*3 + 1*4 + 2*2 + 2*3 + 2*4$$

## Summation Rules
A number of well known summation properties (or rules) exist.  Before we dive into them, also note how it is possible to include a variable in the stop:

$$n = 4$$

$$\displaystyle\sum\limits_{i=1}^{n} i^{2} = 1^{2} + 2^{2} + 3^{2} + 4^{2}$$

The $$n$$ variable is assigned to some number and then utilized as the stop.  Now that we have generic methods to notate the start and stop, as well as the ability to write complex terms, here are few common summation rules:

* $$\displaystyle\sum\limits_{i=1}^{n} c = c_{1} + c_{2} + c_{3} + \ldots + c_{n} = constant * n$$, where $$c$$ is a constant

* $$\displaystyle\sum\limits_{i=1}^{n} i = 1 + 2 + 3 + \ldots + n = \frac{n(n+1)}{2}$$

* $$\displaystyle\sum\limits_{i=1}^{n} i^{2} = 1^{2} + 2^{2} + 3^{3} + \ldots + n^{2} = \frac{n(n+1)(2n + 1)}{6}$$

We will see more notation like this in the usage section.

#### Supplemental Video
[![Sigma Notation](http://img.youtube.com/vi/5jwXThH6fg4/0.jpg)](https://youtu.be/5jwXThH6fg4)



