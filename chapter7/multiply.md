# Matrix Multiplication

Matrix multiplication is different from scalar multiplication.  First, the product of two matrices \textbf{AB} is defined if the number of columns of \textbf{A} is equal to the number of rows of \textbf{B}.  The equivilency that defines the shape of two matrices that are multiplied is:

$$(k x n)(n x p) = (k x p)$$

If matrix **A** is of order $$(k x n)$$ and matrix **B** is of order $$(n x p)$$, then the product **AB** is defined.  For example, if **A** is of order (2 x 3) and **B** is of order (3 x 5), then the product is defined (and the above is equivilency is true).  The resultant matrix is of order (2 x 5).  If **A** is of order (2 x 3) and **B** is of order (2 x 3) the product is undefined.

#### Notation

Before, looking at the mechanics of matrix multiplication, a quick note on more generalized matrix notation.  When notating a matrix of arbitrary size, it is common to use $n$ as a column counter and $k$ as a row counter.  For example, if one would like to notate an arbitrarily sized matrix *A* it is possible to write:

$$\begin{bmatrix}
a_{11} & \ldots & a_{1n} \\ 
a_{21} & \ldots & a_{2n} \\ 
\vdots & \ddots & \vdots \\
a_{k1} & \ldots & a_{kn}
\end{bmatrix}$$

What is going on with all of the dots?  They are the 'filler' that is used to notate that the matrix is of arbitrary size.

### Mechanics of Matrix Multiplication

Elements of the product of two matrices are calculated as:

$$\begin{bmatrix}
a_{11} & \ldots & a_{1n} \\ 
a_{21} & \ldots & a_{2n} \\ 
\vdots & \ddots & \vdots \\
a_{k1} & \ldots & a_{kn}
\end{bmatrix}\begin{bmatrix}
b_{11} & \ldots & b_{1p} \\ 
b_{21} & \ldots & b_{2p} \\ 
\vdots & \ddots & \vdots \\
b_{n1} & \ldots & b_{np}
\end{bmatrix} = \begin{bmatrix}
c_{11} & \ldots & c_{1p} \\ 
c_{21} & \ldots & c_{2p} \\ 
\vdots & \ddots & \vdots \\
c_{k1} & \ldots & c_{kp}
\end{bmatrix}$$

How though is each element calculated?  By computing the *dot product* of each row in matrix **A** with each column in matrix **B**.

Let's assume that two matrices are given:

$$\mathbf{A} = \begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23}
\end{bmatrix} $$

and 

$$\mathbf{B} = \begin{bmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22} \\
b_{31} & b_{32}
\end{bmatrix}$$

We already know that:

$$\mathbf{A}\mathbf{B} = \mathbf{C} = \begin{bmatrix}
c_{11} & c_{12} \\
c_{21} & c_{22}
\end{bmatrix}$$

To compute **C**, we need to compute each element: 

* First, multiple the first row of **A** with the first column of **B**:

$$c_{11} = (a_{11})(b_{11}) + (a_{12})(b_{21}) + (a_{13})(b_{31})$$

* Next, multiple the first row of **A** by the second column of **B**:

$$c_{12} = (a_{11})(b_{12}) + (a_{12})(b_{22}) + (a_{13})(b_{32})$$

* Third, multiple the second row of **A** by the first column of **B**.

$$c_{21} = (a_{21})(b_{11}) + (a_{22})(b_{21}) + (a_{23})(b_{31})$$

* Finally, multiple the second row of **A** by the second column of **B**.

$$c_{22} = (a_{21})(b_{12}) + (a_{22})(b_{22}) + (a_{23})(b_{32})$$

#### Example

$$\mathbf{A} = \begin{bmatrix}
4 & 1 & 2 \\
9 & 6 & 5
\end{bmatrix} $$

$$\mathbf{B} = \begin{bmatrix}
-5 & 0\\
3 & 9\\
-1 & 3
\end{bmatrix}$$

##### Product: AB

$$\mathbf{AB} = \begin{bmatrix}
4(-5) + 1(3) + 2(-1) & 4(0) + 1(9) + 2(3) \\
9(-5) + 6(3) + 5(-1) & 9(0) + 6(9) + 5(3)
\end{bmatrix}$$

$$= \begin{bmatrix}
-20 + 3 - 2 & 0 + 9 + 6 \\
-45 + 18 - 5 & 0 + 54 + 15
\end{bmatrix}$$

$$ = \begin{bmatrix}
-19 & 15 \\
-32 & 69
\end{bmatrix}$$

##### Product: BA

$$\mathbf{BA} = \begin{bmatrix}
-4(4) + 0(9) & (-5)(1) + 0(6) & (-5)2 + 0(2)\\
3(4) + 9(9) & 3(1) + 9(6) & 3(2) + 9(5) \\
-1(4) + 3(9) & (-1)1 + 3(6) & (-1)2 _ 3(5)
\end{bmatrix}$$

$$= \begin{bmatrix}
-20 & -5 & -10 \\
93 & 57 & 51 \\
33 & 17 & 13
\end{bmatrix}$$

#### Multiplication Communicative
In general: 

* **AB** $$\neq$$ **BA**
* **A**(**BC**) = (**AB**)C
* **A**(**B** + **C**) = **AB** + **AC**
* (**B** + **C**)**A** = **BA** + **CA**


#### Supplemental Video

[![Linear Substitution](http://img.youtube.com/vi/kT4Mp9EdVqs/0.jpg)](https://www.khanacademy.org/math/precalculus/precalc-matrices/multiplying-matrices-by-matrices/v/matrix-multiplication-intro)

[![Linear Substitution](http://img.youtube.com/vi/OMA2Mwo0aZg/0.jpg)](https://www.khanacademy.org/math/precalculus/precalc-matrices/multiplying-matrices-by-matrices/v/multiplying-a-matrix-by-a-matrix)


