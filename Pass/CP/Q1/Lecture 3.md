---
date: 2025-09-17
Prof: Ferdinand Grozema
aliases:
  - Solving systems of equations in R^n
---
# Algebra Refresher
## Vectors
### Vectors in $R^n$
example n=3
`numpy.array([x1,x2,x3])`

### Vector operations
- Dot product: `dot_product = np.dot(a, b)`
$$\mathbf{a} \cdot \mathbf{b} =
\begin{bmatrix} a_1 & a_2 & a_3 \end{bmatrix}
\begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
= a_1 b_1 + a_2 b_2 + a_3 b_3
$$
Or: `dot_product = np.vdot(a, b)`
\*Compute only the vector inner product, with automatic conjugation for complex vectors.
![[aca912cb4dcd979e56898b8eda32d76d3ffbd38028c0ea487b97b79befef1907.png]]

- Cross product: `cross_product = np.cross(a, b)`
$$
\mathbf{a} \times \mathbf{b} =
\begin{bmatrix}
a_2 b_3 - a_3 b_2 \\
a_3 b_1 - a_1 b_3 \\
a_1 b_2 - a_2 b_1
\end{bmatrix}
$$
$$u\times v=||u||||v||sin\theta n$$
![[c79fb21129318d101dc1adc23ac97a0ee7cb8a5954927c27c15b55e5ef191e85.png]]

### Linear dependency
Vector space: $V$ over $\mathbb{R}$, vectors $\mathbf{v}_1, \dots, \mathbf{v}_n \in V$, scalars $\alpha_1, \dots, \alpha_n \in \mathbb{R}$
- Linear combination (superposition): $$\sum_{i=1}^{n} \alpha_i \mathbf{v}_i$$Linear dependence: exists if a non-trivial combination equals zero.
- Linear independence if $\sum_{i=1}^{n} \alpha_i \mathbf{v}_i = 0 \implies \alpha_1 = \dots = \alpha_n = 0$ holds.

### Vector norms
A scalar value that measures the "length" or "size" of a vector.
For a vector $\mathbf{v} = [v_1, v_2, \dots, v_n]$:  
  $$
  \|\mathbf{v}\|_p = \left( \sum_{i=1}^{n} |v_i|^p \right)^{1/p}, \quad p \ge 1
  $$

Common norms:  
  1. **1-norm (Manhattan norm):**  
     $\|\mathbf{v}\|_1 = |v_1| + |v_2| + \dots + |v_n|$  
	  `np.linalg.norm(a,ord=1)`
  2. **2-norm (Euclidean norm):**  
     $\|\mathbf{v}\|_2 = \sqrt{v_1^2 + v_2^2 + \dots + v_n^2}$  
	  `np.linalg.norm(a,ord=2)`
  3. **∞-norm (Max norm):**  
     $\|\mathbf{v}\|_\infty = \max(|v_1|, |v_2|, \dots, |v_n|)$
	  `np.linalg.norm(a,np.inf)`

Properties:  
  - Non-negative: $\|\mathbf{v}\| \ge 0$, and $\|\mathbf{v}\| = 0 \iff \mathbf{v} = 0$  
  - Homogeneity: $\|\alpha \mathbf{v}\| = |\alpha| \, \|\mathbf{v}\|$  
  - Triangle inequality: $\|\mathbf{v} + \mathbf{w}\| \le \|\mathbf{v}\| + \|\mathbf{w}\|$


## Matrices
Let $A$ be a matrix with $m$ rows and $n$ columns.
- Row index: $i$, $1 \le i \le m$
- Column index: $j$, $1 \le j \le n$
- Element at row $i$ and column $j$: $a_{ij}$

$$
A = 
\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \dots & a_{mn}
\end{bmatrix}
$$
`A=numpy.array([a11,a12],[a21,a22])`

### Special Matrices
**Square Matrix**: $m=n$

**Identity Matrix**: `I=numpy.identity(n)`

$$
I_n = 
\begin{bmatrix}
1 & 0 & \dots & 0 \\
0 & 1 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1
\end{bmatrix}_{n \times n}
$$

**Row vector**(m=1): `v=numpy.array([v1,v2,...])`
**Column vector**(n=1): `u=numpy.array([u1],[u2],...)`


### Matrix operations:
- Addition: `np.add(x1,x2)` / ==+== *(for np.ndarray objects)*
	$C = A + B \implies c_{ij} = a_{ij} + b_{ij}, \forall i,j$
- Scalar multiplication: `numpy.multiply(a,A)`/ ==\*== *(for np.ndarray objects)*
	$\alpha \cdot A \equiv (\alpha \cdot a_{ij})$
- Transposition: `numpy.transpose(A)`/ ==A.T== *(for np.ndarray objects)*
	$A^T, \quad (A^T)_{ij} = A_{ji}$
		- $\alpha \cdot A^T = (\alpha \cdot A)^T$  
		- $A + B^T = A^T + B^T$  
		- $(A^T)^T = A$
- Matrix vector multiplication: `numpy.matmul(A,v)`

- **Matrix multiplication**:
	$$c_{ij} = \sum_{k=1}^{n} a_{ik} \, b_{kj}, \quad 1 \le i \le m, \; 1 \le j \le p$$
	- Non-commutativity: AB!=BA
	- Distributivity: $A(B+C)=AB+AC$ and $(B+C)A=BA+CA$


## Determinant
`numpy.linalg.det(A)`

Let $A$ be a square $n \times n$ matrix, use the **Cofactor expansion rule:**  
$$\det (A) = \sum_{j=1}^{n} a_{ij} C_{ij}, \quad \text{for any } i = 1,2,\dots,n$$
Checkerboard pattern of signs:  
$$
\begin{bmatrix}
+ & - & + & - & \dots \\
- & + & - & + & \dots \\
+ & - & + & - & \dots \\
- & + & - & + & \dots \\
\vdots & \vdots & \vdots & \vdots & \ddots
\end{bmatrix}
$$
**Cofactor formula:**  
$$
C_{ij} = (-1)^{i+j} \det(A_{ij})
$$


## Eigenvalues and eigenvectors
`a,v=np.linalg.eig(A)`

- **Eigenvector:**  
	An eigenvector $v$ of a matrix $A \in K^{n \times n}$ is the solution to the equation:    $$  A \cdot v = \lambda v  $$Graphically, this implies that the transformation performed by multiplying $A$ and $v$ is equal to stretching $v$ by a constant factor, i.e., resulting in a multiple of $v$ itself.
	
	The eigenvectors $v_1, \dots, v_n$ of matrix $A \in K^{n \times n}$ are computed by solving:$$  (A - \lambda_i I_n) \cdot v_i = 0, \quad i = 1, \dots, n$$The above equation has solutions $v_i$ different from the null vector if (and only if) the factor $A - \lambda_i I_n$ is zero.

- **Eigenvalue**:
	The roots $\lambda_1, \lambda_2, \dots, \lambda_n \in \mathbb{C}$ of the resulting characteristic polynomial  
$$  \det(A - \lambda I_n) = 0$$
	  are referred to as the eigenvalues of matrix $A$.


- **Definite Matrices**:
	Let $M \in \mathbb{R}^{n \times n}$ be a real, square, and symmetric matrix ($M^T = M$).
	- **Positive-definite (PD):**   $x^T M x > 0$ for all $x \in \mathbb{R}^n \setminus \{0\}$  
	  -All eigenvalues of $M$ are $> 0$
	- **Positive-semidefinite (PSD):**  $x^T M x \ge 0$ for all $x \in \mathbb{R}^n$  
	  -All eigenvalues of $M$ are $\ge 0$
	- **Negative-definite (ND):**  $x^T M x < 0$ for all $x \in \mathbb{R}^n \setminus \{0\}$  
	  -All eigenvalues of $M$ are $< 0$
	- **Negative-semidefinite (NSD):**   $x^T M x \le 0$ for all $x \in \mathbb{R}^n$  
	  -All eigenvalues of $M$ are $\le 0$


## Matrix rank
`np.linalg.matrix_rank(matrix_A)`
The rank of a matrix is equal to the minimum number of linearly independent rows or columns.

In general, a matrix $A \in K^{m \times n}$ is of **full rank** if:  $\text{rank } A = \min(m, n)$
Otherwise, $A$ is **rank deficient**, $\text{rank } A < \min(m, n)$


## Matrix norms
Let $A \in K^{n \times n}$ be a matrix:  $$A =
\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \dots & a_{nn}
\end{bmatrix}$$
- A matrix norm is a function $\|\cdot\|: \mathbb{R}^{n \times n} \to \mathbb{R}^+,A\to||A||$ 
	that satisfies the standard conditions (positivity, homogeneity, triangle inequality).

- Recalling vector norms, for $1 \le p \le \infty$, the **matrix p-norm** is defined as:  $$\|A\|_p = \max_{v \ne 0} \frac{\|A v\|_p}{\|v\|_p}$$
1. **L1-norm (maximum absolute column sum)**  $$\|A\|_1 = \max_j \sum_{i=1}^n |a_{ij}|$$
   `scipy.linalg.norm(A, 1)`

2. **L∞-norm (maximum absolute row sum)**  $$
   \|A\|_\infty = \max_i \sum_{j=1}^n |a_{ij}| $$`scipy.linalg.norm(A, np.inf)`

3. **Spectral norm (2-norm)**  $$\|A\|_2 = \sigma_{\max}(A)$$  - $\sigma_{\max}$ is the largest singular value of $A$  
   `scipy.linalg.norm(A, 2)`

4. **Frobenius norm**  $$\|A\|_F = \sqrt{\sum_{i=1}^n \sum_{j=1}^n |a_{ij}|^2}$$   `scipy.linalg.norm(A, 'fro')`


## Matrix exponential
**Important properties**: 
- A diagonal matrix is a matrix where all nonzero entries lie on the diagonal.

- A matrix $A \in \mathbb{R}^{n \times n}$ is diagonalizable if there exists an **invertible** matrix $P$ and a diagonal matrix $D$ such that:  $$A = P D P^{-1} \quad \Rightarrow \quad P^{-1} A P = D$$
- If $P$ is invertible, then:  $e^{PDP^{-1}} = P e^D P^{-1}$ holds.

Exponential of a diagonal matrix $D \in \mathbb{R}^{n \times n}$ is equal to applying the exponential function to all entries on the diagonal:  $$
  D = 
  \begin{bmatrix}
  d_{11} & 0 & \dots & 0 \\
  0 & d_{22} & \dots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \dots & d_{nn}
  \end{bmatrix}
  \quad \Rightarrow \quad
  e^D = 
  \begin{bmatrix}
  e^{d_{11}} & 0 & \dots & 0 \\
  0 & e^{d_{22}} & \dots & 0 \\
  \vdots & \vdots & \ddots & \vdots \\
  0 & 0 & \dots & e^{d_{nn}}
  \end{bmatrix}
  $$
---

# Approximating Solutions
## Linear system of equation
### Definition of a linear system

> [!Exercise] 
> Distillation Column
> Equations:
> 0.9 𝑚1 + 0.3 𝑚2 + 0.1 𝑚3 = 30
> 0.1 𝑚1 + 0.5 𝑚2 + 0.2 𝑚3 = 25
> 0.0 𝑚1 + 0.2 𝑚2 + 0.7 𝑚3 = 10

Matrix-vector equation:$$
\begin{bmatrix}
0.9 & 0.3 & 0.1 \\0.1 & 0.5 & 0.2 \\0.0 & 0.2 & 0.7\end{bmatrix}
\begin{bmatrix}\dot{m}_1 \\\dot{m}_2 \\\dot{m}_3\end{bmatrix}
=\begin{bmatrix}30 \\25 \\10\end{bmatrix}$$
Solution: Invert the matrix --- $x=A^{-1}b$
The inversion of a matrix is: `numpy.linalg.inv(A)`

The inversion of a matrix 𝑨 ∈ $𝐾^{𝑛×𝑛}$ is possible if 𝑨 is non-singular. 
A non-singular matrix 𝑨 has the following properties:
- The determinant of 𝑨 is nonzero: det 𝑨 ≠ 0
- Matrix 𝑨 has full rank: rank 𝑨 = 𝑛
- The system 𝑨𝒙 = 𝒃 has a unique solution 𝒙 ∈ ℝ𝑛 for every 𝒃 ∈ ℝ𝑛
- The homogeneous system 𝑨𝒙 = 𝟎 only evaluates to the trivial solution 𝒙 = 𝟎.

The inversion of a matrix 𝑨 ∈ $𝐾^{𝑛×𝑛}$ is **computationally challenging** if the matrix is sparse and large, i.e., most elements are zero.


### Methods for solving Ax=b:
**Direct methods**
- Solve the system of linear equations by performing a finite number of operations to find an exact solution
- Common algorithms: Gaussian Elimination, LU Decomposition, Cholesky Decomposition
- Yields an exact solution
- Suitable for small to medium-sized systems or dense matrices.
- Computationally expensive for large systems.

**Indirect methods**
- approximate the solution gradually by iterating
- Common algorithms: Jacobi, Gauss-Seidel, Conjugate Gradient
- Can handle very large systems, especially when the matrix is sparse
- Often uses much less memory than direct methods
- May converge slowly or not at all if the system is ill-conditioned.

#### Gaussian Elimination
$$
\begin{cases}
a_{11} m_1 + a_{12} m_2 + a_{13} m_3 = b_1 \\
a_{21} m_1 + a_{22} m_2 + a_{23} m_3 = b_2 \\
a_{31} m_1 + a_{32} m_2 + a_{33} m_3 = b_3
\end{cases}
$$
$$
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} & | & b_1 \\
a_{21} & a_{22} & \cdots & a_{2n} & | & b_2 \\
\vdots & \vdots & \ddots & \vdots & | & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn} & | & b_n
\end{bmatrix}
\;\xrightarrow{\text{row operations}}\;
\begin{bmatrix}
u_{11} & u_{12} & \cdots & u_{1n} & | & y_1 \\
0      & u_{22} & \cdots & u_{2n} & | & y_2 \\
\vdots & \vdots & \ddots & \vdots & | & \vdots \\
0      & 0      & \cdots & u_{nn} & | & y_n
\end{bmatrix}
$$


### Approximation method 1: Jacobi method
$$
m_i^{(k+1)} = \frac{1}{a_{ii}} \Big( b_i - \sum_{j \neq i} a_{ij} \, m_j^{(k)} \Big), \quad i = 1, 2, \dots, n
$$
$$
\begin{bmatrix}
m_1^{(k+1)} \\ m_2^{(k+1)} \\ m_3^{(k+1)}
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{a_{11}} & 0 & 0 \\
0 & \frac{1}{a_{22}} & 0 \\
0 & 0 & \frac{1}{a_{33}}
\end{bmatrix}
\left(
\begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
-
\begin{bmatrix}
0 & a_{12} & a_{13} \\
a_{21} & 0 & a_{23} \\
a_{31} & a_{32} & 0
\end{bmatrix}
\begin{bmatrix} m_1^{(k)} \\ m_2^{(k)} \\ m_3^{(k)} \end{bmatrix}
\right)
$$

Initial guess: $m_1^{(0)}=10, m_2^{(0)}=8, m_3^{(0)}=24$
Iteration: $$
\begin{aligned}
m_1^{(k+1)} &= \frac{1}{a_{11}} \left( b_1 - a_{12} m_2^{(k)} - a_{13} m_3^{(k)} \right) \\
m_2^{(k+1)} &= \frac{1}{a_{22}} \left( b_2 - a_{21} m_1^{(k)} - a_{23} m_3^{(k)} \right) \\
m_3^{(k+1)} &= \frac{1}{a_{33}} \left( b_3 - a_{31} m_1^{(k)} - a_{32} m_2^{(k)} \right)
\end{aligned}
$$
Stopping condition: `np.linalg.norm(f-np.dot(A,m))`


`numpy.linalg.solve`

### Approximation method 2: Gauss-Seidel method
$$
m_i^{(k+1)} = \frac{1}{a_{ii}} \Bigg( b_i 
- \sum_{j=1}^{i-1} a_{ij} m_j^{(k+1)} 
- \sum_{j=i+1}^{n} a_{ij} m_j^{(k)} \Bigg), \quad i = 1,2,\dots,n
$$
$$
\begin{bmatrix} m_1^{(k+1)} \\ m_2^{(k+1)} \\ m_3^{(k+1)} \end{bmatrix}
=
\begin{bmatrix} \frac{1}{a_{11}} & 0 & 0 \\ 0 & \frac{1}{a_{22}} & 0 \\ 0 & 0 & \frac{1}{a_{33}} \end{bmatrix}
\left(
\begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
-
\begin{bmatrix} 0 & a_{12} & a_{13} \\ a_{21} & 0 & a_{23} \\ a_{31} & a_{32} & 0 \end{bmatrix}
\begin{bmatrix} m_1^{(k)} \\ m_2^{(k)} \\ m_3^{(k)} \end{bmatrix}
\right)
$$

$$
\begin{aligned}
m_1^{(k+1)} &= \frac{1}{a_{11}} \left( b_1 - a_{12} m_2^{(k)} - a_{13} m_3^{(k)} \right) \\
m_2^{(k+1)} &= \frac{1}{a_{22}} \left( b_2 - a_{21} m_1^{(k+1)} - a_{23} m_3^{(k)} \right) \\
m_3^{(k+1)} &= \frac{1}{a_{33}} \left( b_3 - a_{31} m_1^{(k+1)} - a_{32} m_2^{(k+1)} \right)
\end{aligned}
$$

Compare two methods:
- Equations for $𝑥_𝑖$ cannot be solved in parallel for Gauss-Seidel method.
- If the matrix 𝑨 ∈ $ℝ^𝑛×𝑛$ is **strictly row-diagonally dominant**, both the Jacobi and the Gauss-Seidel method converge.
- If 𝑨 is symmetric and **positive definite**, then the **Gauss-Seidel method converges**.
BUT
- If **both** 𝑨 and 2𝑫 − 𝑨 are symmetric and **positive definite, then the Jacobi method converges**.


## Nonlinear systems of equation

### Newton-Raphson method
Coupled nonlinear equations:
$$f_1(x_1,x_2)=0, f_2(x_1,x_2)=0$$
Taylor expansion:$$f_1(x_1^{(k+1)}, x_2^{(k+1)}) \approx f_1(x_1^{(k)}, x_2^{(k)}) + \frac{\partial f_1}{\partial x_1} (x_1^{(k+1)} - x_1^{(k)}) + \frac{\partial f_1}{\partial x_2} (x_2^{(k+1)} - x_2^{(k)})$$$$\begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2}
\end{bmatrix}_{(x_1^{(k)}, x_2^{(k)})}
\begin{bmatrix}
\delta x_1 \\ \delta x_2
\end{bmatrix}= - \begin{bmatrix}
f_1(x_1^{(k)}, x_2^{(k)}) \\
f_2(x_1^{(k)}, x_2^{(k)})
\end{bmatrix}$$
$$
\mathbf{F}(\mathbf{x}^{(k+1)}) \approx \mathbf{F}(\mathbf{x}^{(k)}) + J(\mathbf{x}^{(k)}) (\mathbf{x}^{(k+1)} - \mathbf{x}^{(k)})
$$

$$
\text{Set } \mathbf{F}(\mathbf{x}^{(k+1)}) = 0 \text{ to get } 
\mathbf{x}^{(k+1)} - \mathbf{x}^{(k)} = - J^{-1}(\mathbf{x}^{(k)}) \mathbf{F}(\mathbf{x}^{(k)})
$$

$$
\text{Update rule: } \mathbf{x}^{(k+1)} = \mathbf{x}^{(k)} - J^{-1}(\mathbf{x}^{(k)}) \mathbf{F}(\mathbf{x}^{(k)})
$$


