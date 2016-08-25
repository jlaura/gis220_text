# Pi ($$\Pi$$) Notation

The capital Greek letter Pi ($$\Pi$$) is utilized similarily to $$\Sigma$$ notation, but instead of summation, the product of the terms is computed.  For example, below the start, stop, and term are defined as three constants: 1, 4, and 5 respectively:

$$\displaystyle\prod\limits_{1}^{4} 5 = 5\cdot5\cdot5\cdot5$$

Likewise, we can define variables to the start, stop and term:

$$\displaystyle\prod\limits_{n=0}^{3}(n + x) = (0+x)(1+x)(2+x)(3+x)$$

Here we see a variable start and stop, as well as a term that contains a yet undefined variable $$x$$.  Since we do not know what value(s) $$x$$ should take, we evaluate the $$\prod$$ as far as possible.  That is, we apply algebraic simplification if possible.

Finally, $$\prod$$ notation is able to nest, just like $$\sum$$ notation.  For example:

$$\displaystyle\prod\limits_{i=1}^{2}\displaystyle\prod\limits_{j=2}^{4}2ij = (2i_{1}*2 * 2i_{2}*3 * 2i_{3}*4) * (2i_{2} * 2 * 2i_{2} * 3 * 2i_{2} * 4)$$

$$ = (2*2)(2*3)(2*4)(4*2)(4*3)(2*4)$$

## Factorials
While looking at $$\prod$$ notation, it is also timely to take a brief detour to look at factorials of non-negative integers:

$$5!$$

$$3!$$

$$20!$$

or more generally:

$$n!$$

This notation simply translates to: take the product of all positive integers less than or equal to $$n$$. For example:

$$5! = (1)(2)(3)(4)(5)$$

The aside is timely, because we can write the factorial using $$\prod$$ notation.  I am intentionally not going to demonstrate how to do this as it will be a question on the weekly assignment.  As a hint, remember that we can utilize a variable in the start and then reuse that variable in the term.
