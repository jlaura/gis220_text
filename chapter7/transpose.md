# Matrix Transposition

Transposition of a matrix means to pivot the matrix.  If an $$m x n$$ matrix is given, the transposed matrix has the order $$n x m$$.  For example:

$$\mathbf{A} = \begin{bmatrix}
10 & 2 \\
4 & 6 \\
1 & 9
\end{bmatrix} \rightarrow \mathbf{A}^{T} = \begin{bmatrix}
10 & 4 & 1 \\
2 & 6 & 9
\end{bmatrix}$$

The transposition of a matrix is notated using the $$T$$ superscript:

$$\mathbf{A} \rightarrow \mathbf{A}^{T}$$

Positional notation for a transpose is:

$$a_{ij}^{T} = a_{ji}$$

## Properties of the transpose

* $$(\mathbf{A}^{T})^{T} = \mathbf{A}$$
* $$(\lambda\mathbf{A})^{T} = \lambda\mathbf{A}^{T}$$, where $$\lambda$$ is a scalar
* $$(\mathbf{A} + \mathbf{B})^{T} = \mathbf{A}^{T} + \mathbf{B}^{T}$$
* $$(\mathbf{A} + \mathbf{B} + \mathbf{C})^{T} = \mathbf{A}^{T} + \mathbf{B}^{T} + \mathbf{C}^{T}$$
* $$(\mathbf{AB})^{T} = \mathbf{B}^{T}\mathbf{A}^{T}$$
* $$(\mathbf{ABC})^{T} = \mathbf{C}^{T}\mathbf{B}^{T}\mathbf{A}^{T}$$