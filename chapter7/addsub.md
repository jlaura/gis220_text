# Matrix Addition and Subtraction

First, two matrices are identical if they have the same order (dimensions) and $$b_{ij} = a_{ij}$$.  Intuitively, if the matrices have the same shape, and all of the elements in $$\mathbf{A}$$ are the same as all of the elemtns in $$\mathbf{B}$$ the matrices are equal.

If two matrices have the same order, it is possible to apply element-wise additional and subtraction operations.  For example:

$$\mathbf{A} = \begin{bmatrix}
10 & 2\\ 
4 & 6 \\ 
 1 & 9 
\end{bmatrix}$$

and

$$\mathbf{B} = \begin{bmatrix}
5 & 4\\ 
2 & 1 \\ 
 8 & 3 
\end{bmatrix}$$

then

* $$\mathbf{A} + \mathbf{B} = \begin{bmatrix}
10 + 5 & 2 + 4\\ 
4 + 2 & 6 + 1 \\ 
1 + 8 & 9 + 3 
\end{bmatrix} = \begin{bmatrix}
15 & 6\\ 
6 & 7 \\ 
9 & 12\end{bmatrix} $$

* $$\mathbf{A} - \mathbf{B} = \begin{bmatrix}
10 - 5 & 2 - 4\\ 
4 - 2 & 6 - 1 \\ 
1 - 8 & 9 - 3 
\end{bmatrix} = \begin{bmatrix}
5 & -2\\ 
2 & 5 \\ 
-7 & 6\end{bmatrix} $$

Also implicit in the above: $$\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}$$.

We can also identify a special matrix - the zero matrix.  

$$\mathbf{C} = 
\begin{bmatrix}
0 & 0\\
0 & 0\\
0 & 0
\end{bmatrix}$$

Using the zero matrix, it is also possible to define:

$$\mathbf{A} + \mathbf{C} = \mathbf{A}$$, assuming that \textbf{A} and textbf{C} are the same order.

#### Supplemental Video

[![Linear Substitution](http://img.youtube.com/vi/WR9qCSXJlyY/0.jpg)](https://www.khanacademy.org/math/algebra-home/alg-matrices/alg-adding-and-subtracting-matrices/v/matrix-addition-and-subtraction-1)

---------

### Multiplication by a scalar
It is possible to multiple a scalar with a matrix.  For any scalar $$\lambda_{1}$$,

$$\lambda_{1}\mathbf{A}\begin{bmatrix}
\lambda_{1}a_{11} & \lambda_{1}a_{21}\\ 
\lambda_{1}a_{12} & \lambda_{1}a_{22} \\ 
 \lambda_{1}a_{13} & \lambda_{1}a_{23} 
\end{bmatrix}$$

and 

$$ \lambda_{1}\mathbf{A} = \mathbf{A}\lambda_{1}$$

For example:

$$3\mathbf{A} = \begin{bmatrix}
3(10) & 3(2)\\ 
3(4) & 3(6) \\ 
3(1) & 3(9)\end{bmatrix} = \begin{bmatrix}
30 & 6\\ 
12 & 18 \\ 
 3 & 27 
\end{bmatrix}$$

The final example illustrates the element-wise multiplication of a matrix with a scalar.  This is *not* matrix multiplication.
