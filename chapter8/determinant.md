# Determinant & Trace

## Determinant

Determinant is a scalar that reflects characteristics of a given *square* matrix. It is important for many aspects of a matrix.
A determinant can be defined (or calculated) only for a square matrix, including Determinant of a matrix **A** is denoted by det(**A**).

For example, if **A** is the matrix,

$$A = \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}$$

the determinant is notated simply as:

$$det(A) = \begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}$$

You will also see the determinant notated using parallel lines (as opposed to the square brackets).  For example, 

$$\begin{vmatrix}A\end{vmatrix} = \begin{vmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{vmatrix}$$

### 1 x 1 Matrices
In the most simplistic case, a $$1 x 1$$ matrix, the determinant is the scalar value.  For example, if $$A = \begin{bmatrix}
a
\end{bmatrix}$$, then $$det(A) = a$$.

### 2 x 2 Matrices
The determinant of a $$2 x 2$$ matrix, $$A = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}$$, is the scalar $$ad - bc$$.  

For example,

$$A = \begin{bmatrix}
3 & 5 \\
9 & 1
\end{bmatrix}$$ 

and 

$$det(A) = (3)(1) - (5)(9) = -42$$.

#### Supplemental Video

[![Combinations](http://img.youtube.com/vi/OU9sWHk_dlw/0.jpg)](https://www.khanacademy.org/math/precalculus/precalc-matrices/determinant-of-2x2-matrix/v/finding-the-determinant-of-a-2x2-matrix)

### Larger Matrices
For square matrices larger than $$2 x 2$$ it is necessary to utilize [Laplace expansion](https://en.wikipedia.org/wiki/Laplace_expansion) or cofactor expansion.  The final determinant, $$\begin{vmatrix}B\end{vmatrix}$$, is the weighted sum of the subdivided $$2 x 2$$ determinants that make **B**.

To do this, it is necessary to identify the cofactor for each $$2 x 2$$ sub-matrix.  I think an example is easiest to visualize how this process works.


Assume that matrix **B** is given as:

$$\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}$$

and the goal is to compute: 

$$\begin{vmatrix}B\end{vmatrix} = \begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix}$$

The cofactors are any row of the matrix **B**.  The sub-matrices are the other $n$ rows.  In the example below, I have selected the first row to contain the cofactors but **any** row will work.

First, select element $$a$$ and cross out the remaining elements in row a (b, c) and remaining elements in column a (d, g).  The resultant $$2 x 2$$ submatrix (and determinant) is:

$$\begin{vmatrix}
e & f \\
h & k
\end{vmatrix}$$

and 

$$\begin{vmatrix}B\end{vmatrix} = \begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix} = a\begin{vmatrix}
e & f \\
h & k
\end{vmatrix}$$

Next, select element b and cross off the other elements in row b (a, c) and other elements in column b (e, h).  The resultant $$2 x 2$$ submatrix is:

$$\begin{vmatrix}
d & f \\
g & k
\end{vmatrix}$$

and 

$$\begin{vmatrix}B\end{vmatrix} = \begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix} = a\begin{vmatrix}
e & f \\
h & k
\end{vmatrix} - b\begin{vmatrix}
d & f \\
g & k
\end{vmatrix}$$

Finally, select element c and cross of the row and column containing element c.  This results in:

$$\begin{vmatrix}
d & e \\
g & h
\end{vmatrix}$$

and 

$$\begin{vmatrix}B\end{vmatrix} = \begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix} = a\begin{vmatrix}
e & f \\
h & k
\end{vmatrix} - b\begin{vmatrix}
d & f \\
g & k
\end{vmatrix} + c\begin{vmatrix}
d & e \\
g & h
\end{vmatrix}$$

The sign between the sub-matrices alternatives, +, -, +.

#### Supplemental Video

[![Combinations](http://img.youtube.com/vi/0c7dt2SQfLw/0.jpg)](https://www.khanacademy.org/math/linear-algebra/matrix-transformations/inverse-of-matrices/v/linear-algebra-3x3-determinant)

What about a $$4 x 4$$  or an $$n x n$$?

As above, select any row as the cofactors.  Doing this leaves an $$n-1 x n$$ matrix.  For each element in the selected from, identify the $$n-1 x n-1$$ submatrix associated with a given cofactor, alternating the sign between elements (+, -, +, -).  Repeat this process until the matrix has been decomposed in a (large) number of $$2x2$$ determinant problems.

#### Supplemental Video

[![Combinations](http://img.youtube.com/vi/H9BWRYJNIv4/0.jpg)](https://www.khanacademy.org/math/linear-algebra/matrix-transformations/inverse-of-matrices/v/linear-algebra-nxn-determinant)

## Properties of determinants

* If one row of a matrix consists entirely of zeros, then the determinant is zero.
* If two rows of a matrix are interchanged, the determinant changes sign
* If two rows of a matrix are identical, the determinant is zero
* If the matrix **B** is obtained from the matrix A by multiplying every element in one row of A by the scalar $$\lambda$$, then $$det(B) = \lambda det(A)$$.
* For an n x n matrix and any scalar $$\lambda$$, $$det(\lambda A) = \lambda^{n}det(A)$$
* A square matrix has an inverse if and only if its determinant is non-zero.

## Trace

In comparison to the determinant, the trace of a matrix is trivial to compute.  It is simply the sum of the diagonal of a square matrix.  For example:

$$A = \begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}$$

and the trace of A (tr(A):

$$tr(A) = a + e + i$$


## Applications to Geography
Frequently, the natural log of the determinant of a semi-definite matrix ($$ln(det(A))$$) needs to be computed in the context of spatial regression (multivariate maximum liklihood estimation problems for non-independent data).  If you would like more information about this, check out [this blog post](http://jseabold.net/blog/2013/08/06/sparse-log-determinants/) about estimating the log determinant.  An estimate is necessary becase the calculation is quite expensive for a computer as the total number of observations increases; this is a problem that should sounds familiar having just finished the sections on computational geometry and the goal of maximizing efficiency.