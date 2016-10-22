# Eigen Values and Eigen Vectors

Definition: A nonzero vector $$x$$ is an *eigenvector* or characteristic vector of a square matrix **A** if there exists a scalar $$\lambda$$ such that $$Ax = \lambda x$$.  Then $$\lambda$$ is the *eigenvalue* characteristic value of **A**.

What exactly does the above mean?  If a square matrix is multiplied by a vector, the result is a vector or $$Ax = y$$, where A is a square matrix, and x and y are vectors.  Sometimes, it is possible to find a vector and scalar so that the following equality is true: $$Ax = \lambda x$$.  The scalar $$\lambda$$ is the eigenvalue and the vector $$x$$ is the eigen vector (which is never a zero vector).

Why would we want to do this?  In spatial analysis, we might be interested in assessing the strength of spatial autocorrelation](https://en.wikipedia.org/wiki/Spatial_analysis#Spatial_autocorrelation) and it has been shown that a relationship exists between measures for spatial autocorrelation (for example, Moran's I) and the eigenvalue computabled from a spatial weights object.  The rest of this chapter explores both of those ideas and the take away here is simply that eigen values and vectors can be viewed as summarizations of more complex matrix representations.

## Computing Eigen Values and Eigen Vectors
The computation of eigen values and vectors will utilize many of the linear algebra skills practiced in the previous two chapters including use of an [identity matrix](https://en.wikipedia.org/wiki/Identity_matrix), matrix multiplication, and the use of elementary row operations.

I like to look at computing eigen values using an example:

$$A = \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix}$$

and we want to compute the eigen values first:

$$|A - \lambda \cdot I| = \left| \begin{bmatrix}
0 & 1 \\
-2 & -3
\end{bmatrix} - \begin{bmatrix} 
\lambda & 0 \\
0 & \lambda
\end{bmatrix} \right| = 0$$

$$= \left| \begin{bmatrix}
-\lambda & 1  \\
-2 & -3-\lambda
\end{bmatrix} \right|$$

then the determinant,

$$= \lambda^{2} + 3\lambda + 2$$

so, 

$$\lambda_{1} = -1$$ and $$\lambda_{2} = -2$$

Reminder: These were computed using the quadratic formula!

Once we have computed the eigen values, it is time to compute the eigen vectors.  From above, we know that the following equality must hold:

$$Ax = \lambda_{1}x$$ or $$A\cdot v_{1} = \lambda_{1} \cdot v_{1}$$

So this is now a 'plug and chug' operations for a system of equations.  Even though we officially look at systems of linear equations next week, you have already been solving them using elementary row operations!  To keep rolling with the example, a little algebraic manipulation and:

$$(A - \lambda_{1}) \cdot v_{1} = 0$$

$$ = \begin{bmatrix}
-\lambda_{1} & 1 \\
-2 & -3 - \lambda_{1} 
\end{bmatrix} \cdot v_{1} = 0$$

$$ = \begin{bmatrix}
1 & 1 \\
-2 & -2
\end{bmatrix} \cdot \begin{bmatrix} v_{1,1} \\ v_{1,2} \end{bmatrix} = 0$$

From the top row, we see:

$$(1)v_{1,1} + (1)v_{1,2} = 0$$, so

$$v_{1,1} = -v_{1,2}$$

and from the second row we see that:

$$(-2)v_{1,1} + (-2)v_{1,2} = 0$$

$$ v_{1,1} = -v_{1,2}$$

So the values in the eigen vector must have equal and opposite signs.  Notice that the actual scalar values in the vector do not matter.  In other words, the magnitude.  What does matter is the direction.

The process described above is then repeated for each of the other eigen values; plug the eigen value into 
$$(A - \lambda_{1}) \cdot v = 0$$ and solve.

### Additional Examples
Once again, [Paul's Online math notes](http://tutorial.math.lamar.edu/Classes/DE/LA_Eigen.aspx) has a number of wonderful examples that step through computing the eigen values and then solving the system of linear equations.

#### Supplemental Video

[![Eigen Values](http://img.youtube.com/vi/PhfbEr2btGQ/0.jpg)](https://www.khanacademy.org/math/linear-algebra/alternate-bases/eigen-everything/v/linear-algebra-introduction-to-eigenvalues-and-eigenvectors)

[![Eigen Values](http://img.youtube.com/vi/pZ6mMVEE89g/0.jpg)](https://www.khanacademy.org/math/linear-algebra/alternate-bases/eigen-everything/v/linear-algebra-example-solving-for-the-eigenvalues-of-a-2x2-matrix)

[![Eigen Values](http://img.youtube.com/vi/3-xfmbdzkqc/0.jpg)](https://www.khanacademy.org/math/linear-algebra/alternate-bases/eigen-everything/v/linear-algebra-finding-eigenvectors-and-eigenspaces-example)

### Properties
Here are a few interesting properties of eigenvalues and vectors:

* the sum of eigen values is equal to the trace of the matrix
* a matrix is singular, if and only if is has a zero eigenvalue
* if $$\lambda$$ is an eigen value of **A** and **A** is invertable, then $$1/\lambda$$ is an eigen value of $$A^{-1}$$.
* If $$\lambda$$ is an eigenvalue of A then it is also an eigenvalue of $$A^{T}$$.

## Who cares?
I like the following two webpages:

* [this math.stackexchange post](http://math.stackexchange.com/questions/23312/what-is-the-importance-of-eigenvalues-eigenvectors) where the top answer is quite good
* [this blog style post](http://setosa.io/ev/eigenvectors-and-eigenvalues/) looking at what eigen vectors are visually

