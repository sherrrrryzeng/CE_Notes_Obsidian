# Lecture 1

- Dictionary
	- {}
	- key:value
	`a={"name":"Alice","age":25}`
	- `a["city"]="Delft"`    ==\*\[ ]==
	  
- for
	`for element in range(5):`
	- start from 0 up until 5-1=4
	`for element in range(2,8,2)`
	`# 2,4,6`
	- range(start, stop, step)


## Matplotlib
`import matplotlib as plt`

### Basic
- `plt.plot(x, y, label="y=x", color="blue")`
- `plt.xlabel("x")`
- `plt.ylabel("y")`
- `plt.title("Title")`
- `plt.legend()`
- `plt.show()`

### Others
- `fig, ax = plt.subplots()`   handle the figure as objects
	`ax.plot(x,y1,label="y1=x")`
	`ax.plot(x, y1, label="y2=2x")`    multiple lines in one plot
	`ax.set_xlabel("x")
	`ax.set_ylabel("y")
	`ax.set_title("Title")
	`ax.legend()
	`plt.show()

- `fig, ax = plt.subplots(2, 2)`     create multiple plots
	`ax[0, 0].plot(x, y)`    plot in the first subplot

- `plt.figure(figsize=(10, 5))`    change plot size
- `fig, ax = plt.subplots(figsize=(8, 4))` 

## Reminder
- `a=5`   \# default 5 -> int(5)
	`a=str(5)`
	
- string.lower()
	`lower_joined_string=joined_string.lower()`
	- string.upper()
	- string.replace("o", "p")
	
- list.append()
	
- str.find(substring, start, (end))
	*find nothing -> return* -1
```
mole_dict={'C':12.01,'H':1.00,'O':16.00,'N':14.01}
def calculate_molecular_weight(molecule:str)->float|None:
	Weight=0
	i=0
	while i<len(molecule):
		character=molecule[i]
		if character=='[':
			j=molecule.find(']',i)
			if j==-1:
				return None
			number=molecule[i+1:j]
			try:
				value=float(number)
				if value<0:
					return None
			except ValueError:
				return None
			Weight+=value
			i=j+1
			continue
		elif character in mole_dict:
			Weight+=mole_dict[character]
			i+=1
			continue
		else:
			return None
	return Weight
```


# Lecture 2

## Calculus
- Taylor approximation $$P_k(x)=lim\sum_{n=0}^{k}\frac{f^{(n)}(a)}{n!}(x-a)^n$$$$=f(a)+f'(a)(x-a)+\frac{f''(a)}{2!}(x-a)^2+...+\frac{f^k(a)}{k!}(x-a)^k$$
- Gradient of $f$ at point $x_\alpha$ $$
\nabla f(\mathbf{x}_a) =
\begin{bmatrix}
\frac{\partial f}{\partial x_1}(\mathbf{x}_a) \\
\frac{\partial f}{\partial x_2}(\mathbf{x}_a) \\
\vdots \\
\frac{\partial f}{\partial x_n}(\mathbf{x}_a)
\end{bmatrix} \in \mathbb{R}^n
$$
- Hessian matrix $$
H(f) =
\begin{bmatrix}
\frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\
\frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \cdots & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2 f}{\partial x_n \partial x_1} & \frac{\partial^2 f}{\partial x_n \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_n^2}
\end{bmatrix}$$
- Jacobian matrix $$J_{\mathbf{f}}(x) =
\begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n}
\end{bmatrix}$$

## Approximation Methods for Nonlinear Equation
- **Bisection method**
	**Limitation**: edge cases - multiple roots or no root between \[a,b]
	Solution: plot first
	
- **Fixed-point equation**
	*rewrite $g(x)$ into $h(x)=x$, iterate $x_1=g(x_0)$ -> $x_2=g(x_1)$ -> ...*
	Limitation: convergence
	Solution: convergence proof $|g'(x)|<1$
	
- **Newton-Raphson method**
	$y_1=f(x_0)+f'(x_0)(x-x_0)$
	Update rule: $x_{n+1}=x_n-\frac{1}{f'(x_n)}f(x_n)$
	
- **Error formulations**
![[d6c9406dbf6ab61dcf27e0c964ff2d7723b415b7ae42c0340c277162abbb63b7.png]]

## Built-in Functions for Nonlinear Equation
- **scipy.optimize.fsolve()**
	solve f(x)=0, return root
	```
	def f(x):
		return x**3-2*x-5
	root=scipy.optimize.fsolve(f,x0=2)
	```
- **scipy.optimize.root()**
	more flexible, return root, convergence and iterance
	```
	def F(X):
		x,y=X
		return [x+y-3, x**2+y**2-9]
	sol=scipy.optimize.root(F,[1,1],method='hybr')
	print(sol.x) #root
	print(sol.success) #converge or not
	print(sol.message)
	```

## Reminder
- np.zeros_like(x,dtype=float)
- math.factorial() - n!
```
def taylor_sin(x: npt.NDArray, degree: int) -> npt.NDArray:
	i=0
	approximation=np.zeros_like(x,dtype=float)
	while i<=degree:
		if (i+1)%4==2:k=1
		elif (i+1)%4==0:k=-1
		else: k=0
		approximation+=k*x**(i)/math.factorial(i)
		i+=1
return approximation
```

# Lecture 3

## Vector
- Vector: `numpy.array([x1,x2,...,xn])`
- Dot product: `numpy.dot(u,v)` or `numpy.vdot(u,v)` $$\mathbf{a} \cdot \mathbf{b} =
\begin{bmatrix} a_1 & a_2 & a_3 \end{bmatrix}
\begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
= a_1 b_1 + a_2 b_2 + a_3 b_3
$$$$\mathbf{u}\cdot\mathbf{v}=||\mathbf{u}||\,||\mathbf{v}||cos\theta$$
Example: 
```
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.dot(a, b))
# [[19 22]
#  [43 50]]
print(np.vdot(a, b))
# 1*5 + 2*6 + 3*7 + 4*8 = 70
```

- Cross product: `np.cross(u,v)` $$
\mathbf{a} \times \mathbf{b} =
\begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} \times
\begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
=\begin{bmatrix}
a_2 b_3 - a_3 b_2 \\
a_3 b_1 - a_1 b_3 \\
a_1 b_2 - a_2 b_1
\end{bmatrix}
$$
$$\mathbf{u}\times \mathbf{v}=||\mathbf{u}||\,||\mathbf{v}||\,sin\theta \,\mathbf{n}$$

- **Linear dependency**
$$\sum_{i=1}^{n} \alpha_i \mathbf{v}_i=0\implies \alpha_1 = \dots = \alpha_n = 0$$

- **Vector norms**: A scalar value that measures the "length" or "size" of a vector.
	For a vector $\mathbf{v} = [v_1, v_2, \dots, v_n]$:  $$
	  \|\mathbf{v}\|_p = \left( \sum_{i=1}^{n} |v_i|^p \right)^{1/p}, \quad p \ge 1$$
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
- Matrix: `A=numpy.array([[a11,a12],[a21,a22]])`
- Identity matrix: `I=numpy.eye(n)`   $$I_n = 
\begin{bmatrix}
1 & 0 & \dots & 0 \\
0 & 1 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1
\end{bmatrix}_{n \times n}$$
- Addition: `np.add(x1,x2)` or `+`
- Scalar multiplication: `numpy.multiply(a,A)` or `*`
- Transposition: `numpy.transpose(A)` or `A.T`
- Matrix(vector) multiplication: `numpy.matmul(A,B)` or `A@B`

\*Important properties:
- Non-commutativity: $AB\neq BA$
- Distributivity: $A(B+C)=AB+AC$ and $(B+C)A=BA+CA$


- **Determinant**: `numpy.linalg.det(A)` $$\det (A) = \sum_{j=1}^{n} a_{ij} C_{ij}, \quad \text{for any } i = 1,2,\dots,n$$**Cofactor expansion rule:**  checkerboard pattern of signs
$$C_{ij} =
\begin{bmatrix}
+ & - & + & - & \dots \\
- & + & - & + & \dots \\
+ & - & + & - & \dots \\
- & + & - & + & \dots \\
\vdots & \vdots & \vdots & \vdots & \ddots \end{bmatrix}= (-1)^{i+j} \det(\mathbf{A}_{ij})$$
  $\mathbf{A}_{ij}$ obtained from deleting i-th row and j-th column of $\mathbf{A}$

- **Eigenvalue & Eigenvector**: `a,v=np.linalg.eig(A)`
  $$  A \cdot v = \lambda v  $$
  $\lambda$ is the eigenvalue, $v$ is the eigenvector. Rearrange:
$$  (A - \lambda_i \mathbf{I_n}) \cdot\mathbf{v_i} = 0$$
  How to solve - characteristic polynomial:
$$  \det(A - \lambda I_n) = 0$$

| Type                   | Definition (for all nonzero $x \neq 0$) | Eigenvalue condition                       | Notation      |
| ---------------------- | --------------------------------------- | ------------------------------------------ | ------------- |
| Positive definite      | $x^T A x > 0$                           | all $\lambda_i > 0$                        | $A \succ 0$   |
| Positive semi-definite | $x^T A x \ge 0$                         | all $\lambda_i \ge 0$                      | $A \succeq 0$ |
| Negative definite      | $x^T A x < 0$                           | all $\lambda_i < 0$                        | $A \prec 0$   |
| Negative semi-definite | $x^T A x \le 0$                         | all $\lambda_i \le 0$                      | $A \preceq 0$ |
| Indefinite             | $x^T A x$ can be positive or negative   | some $\lambda_i > 0$, some $\lambda_i < 0$ | —             |

- **Matrix rank:** `np.linalg.matrix_rank(matrix_A)`
  The rank of a matrix is equal to the minimum number of linearly ==independent== rows or columns.

  **full rank**:  $\text{rank } A = \min(m, n)$
  **rank deficient**: $\text{rank } A < \min(m, n)$

- Matrix norms: 
  for $1 \le p \le \infty$, the matrix **p-norm** is defined as:  $$\|A\|_p = \max_{v \ne 0} \frac{\|A v\|_p}{\|v\|_p}$$
1. **L1-norm (maximum absolute column sum)**   `scipy.linalg.norm(A, 1)` $$\|A\|_1 = \max_j \sum_{i=1}^n |a_{ij}|$$
2. **L∞-norm (maximum absolute row sum)**  `scipy.linalg.norm(A, np.inf)` $$
   \|A\|_\infty = \max_i \sum_{j=1}^n |a_{ij}| $$
3. **Spectral norm (2-norm)**     `scipy.linalg.norm(A, 2)` $$\|A\|_2 = \sigma_{\max}(A)$$  - $\sigma_{\max}$ is the largest singular value of $A$  

4. **Frobenius norm**    `scipy.linalg.norm(A, 'fro')`  default$$\|A\|_F = \sqrt{\sum_{i=1}^n \sum_{j=1}^n |a_{ij}|^2}$$

- **Matrix exponential**: `scipy.linalg.expm(A)` 

  A **diagonal matrix** is a matrix where all nonzero entries lie on the diagonal.

  A matrix $A \in \mathbb{R}^{n \times n}$ is **diagonalizable** if there exists an invertible matrix $P$ and a diagonal matrix $D$ such that:  $$A = P D P^{-1} \quad \Rightarrow \quad P^{-1} A P = D$$
  If $P$ is invertible, then:  $e^{PDP^{-1}} = P e^D P^{-1}$ holds.

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

## Approximating solutions of linear systems of equation
$$
\begin{cases}
a_{11} m_1 + a_{12} m_2 + a_{13} m_3 = b_1 \\
a_{21} m_1 + a_{22} m_2 + a_{23} m_3 = b_2 \\
a_{31} m_1 + a_{32} m_2 + a_{33} m_3 = b_3
\end{cases}
$$
Matrix-vector equation:$$
\mathbf{A}
\mathbf{x}
=\mathbf{b}$$Matrix inversion: $$\mathbf{x}=\mathbf{A^{-1}b}$$
- The inversion of a matrix: `numpy.linalg.inv(A)`

The inversion of a matrix 𝑨 ∈ $𝐾^{𝑛×𝑛}$ is possible if 𝑨 is **non-singular**. 

A non-singular matrix 𝑨 has the following properties:
- The determinant of 𝑨 is nonzero: $det(𝑨) \neq 0$
- Matrix 𝑨 has full rank: $rank(𝑨) = 𝑛$
- The system 𝑨𝒙 = 𝒃 has a unique solution $𝒙 ∈ ℝ^𝑛$ for every $𝒃 ∈ ℝ^𝑛$
- The homogeneous system 𝑨𝒙 = 𝟎 only evaluates to the trivial solution 𝒙 = 𝟎

The inversion of a matrix is **computationally challenging** if the matrix is sparse and large, i.e., most elements are zero.


### Direct Method: 
- Gaussian Elimination![[060bcfab3693a3611407663ac8dbe51d14bc3ebd392214475c20ecf4a9c2eae9.png]]

### Indirect Approximation Methods
- Condition for convergence of iterative methods:
	Let $A=M+N$ be nonsingular. If M is non-singular and the ==spectral radius== of $M^{-1}N$ is **less than 1**, then the iterates $$Mx^{k+1}=b-Nx^{k}$$ converge to $x=A^{-1}b$ for any starting vector $x^0$.
	
	The **spectral radius** of a matrix K is defined as the maximum of the absolute values of its eigenvalues: $$\rho(K)=max{\{|\lambda_1|,...,|\lambda_n|}\}$$

- **Jacobi Method**: `sp.linalg.solve(a,b)` 
![[365952fc49d4696aec2fb0b2cf09771d07735d81c48d01580953a304903ed910.png]]
![[5f0ac4ae896ac4dda9c051f5d0df4ddac8730f1e656f65867d4a42a7cc570031.png]]
- The Jacobi method is especially suitable for **strictly row diagonal-dominant** matrices, i.e., the values on the diagonal are larger than the sum of the other row entries. 
  -> $\rho(D^{-1}(L+U))<1$ can be met more easily
  -> converge
- If **both A and 2D-A** are symmetric and **positive definite**(SPD), then the Jacobi method converges

- Gauss-Seidel Method
![[b604907e84e02fe72319a6f6e2033730de789c5c9d990d80f05c8a365dacc4a4.png]]
- The Gauss-Seidel method is basically the same as Jacobi method, except that we use the x values in the **new iteration** in the same iteration. 
- Equations for $x_i$ cannot be solved **in parallel**, because we need to know $x_1^{(k+1)}$ before we calculate $x_2^{(k+1)}$
- If the matrix is **strictly row-diagonally dominant**, the Gauss-Seidel method converge.
- If the matrix is symmetric and **positive definite**(for all nonzero $x \neq 0$, $x^T A x > 0$), then the Gauss-Seidel method converges


## Approximating solutions of Nonlinear systems of equation
- Newton-Raphson Method
  Use Taylor expansion to linearize the equations, and apply Netwon-Raphson method:$$\mathbf{F}(\mathbf{x}^{(k+1)})=\mathbf{F}(\mathbf{x}^{(k)})+\mathbf{J}(\mathbf{x}^{(k)})(\mathbf{x}^{k+1}-\mathbf{x}^{k})=0$$
$$\mathbf{x}^{(k+1)} = \mathbf{x}^{(k)} - \mathbf{J}^{-1}(\mathbf{x}^{(k)}) \mathbf{F}(\mathbf{x}^{(k)})
$$
- Note that the matrix **inversion computation**($\mathbf{J}^{-1}$) is very expensive, especially for large systems. Solve the linear system instead:$\mathbf{F}(\mathbf{x}^{(k)})+\mathbf{J}(\mathbf{x}^{(k)})(\mathbf{x}^{k+1}-\mathbf{x}^{k})=0$
  To solve it, use iterative method for linear systems (e.g., Gauss-Seidel).
- Newton-Raphson method for systems of nonlinear equations results in a **nested iterative method** (double-layer interation)
