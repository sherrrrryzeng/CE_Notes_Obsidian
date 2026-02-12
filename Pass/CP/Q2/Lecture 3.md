---
date: 2025-11-26
Prof: Zoë J.G. Gromotka
aliases:
  - Numerical methods for PDEs
---
# Elliptic PDE
Elliptic PDEs describe systems that have already reached the steady state and thus are **time-independent**. 
- The two independent variables are 2 spatial coordinates
	Example - Laplace Equation$$\frac{\partial^2u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}=0,\,\,\,\,0\leq x\leq L_x,\,\,0\leq y\leq L_y$$
	The Laplace Equation describes the spatial evolution of a quantity _u_ in 2D through diffusion:
	- 𝑢 is the temperature (/concentration / velocity...)
	- $x$ and $y$ are two spatial coordinates
	

## Boundary Conditions at the Corners
For 2D elliptic PDEs $\frac{\partial^2u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}=0$ -> 4 BCs

Case study: Steady state heat transport in 2D (*e.g., plate heat exchanger*) ![[bdbf08fa23b8cca6e2786cfce1f1db0420d198f24bdbc403d67552ab5b1f470d.png]]

### Boundary Conditions in the Corners Continuity
- Ideal Case - BCs are continuous in the corners $$T^{(1)}(y=0)=T^{(3)}(x=0)$$
- Non-continuous BCs
	1. **Dominance of one BC**
		One BC is assigned to an open domain and the other on a closed domain. In the corner one condition holds.
	2. **Averaging**
		Corner value is set as the average of the two conflicting conditions
		\*Only applicable to Dirichlet BCs


## Finite Difference Method in 2D domain
![[900dcf4741cf5c199b85d20807758a131492d543ed44a8c4fca0f2d5f89efe81.png]]
Finite difference method can be applied to discretize the second order derivatives:$$\frac{T_{i-1,j}-2T_{i,j}+T_{i+1,j}}{\triangle x^2}+\frac{T_{i,j-1}-2T_{i,j}+T_{i,j+1}}{\triangle y^2}=0$$
Considering a homogeneous grid $\triangle x=\triangle y$ : $$T_{i-1,j}+T_{i+1,j}+T_{i,j-1}+T_{i,j+1}-4T_{i,j}=0$$
This equation is valid for every internal point: $$i=2,3,...,N_x-3;\,\,j=2,3,...,N_y-3$$

### Dirichlet BCs
![[3ac99be824b8034be8169a0174d524808b67881e1a44ca9749be48347dfb70e3.png]]
![[e630ecb08afc1e2a4d9e3a37072e60e5559157c100a39682174c279ae64988a0.png]]
![[d7fa7593e6fa958e5941f02611f2174dddedd74c352261166bd750a5e3054458.png]]
![[8484e88f20e8426c75df6f7f4425ee6446f3fa32951e424cca652f36095b1720.png]]

![[7c5e289412c5501487111390fd3f811a455dd2a3560cc9cd4b438917db03479c.png]]
![[f25100ff86e2cfafc35fe9047b6160ef236ccd462fff935e0c7a7b95863aea36.png]]
![[6e6f0d91f12274e779f894a212c38ae6a1a98a4e60a4a3bc667d62e84a1b1298.png]]
![[18a0ba945a3eba7dc6aaa5f0ac6aa5c9fcad7a9e5878710b563da032819d9724.png]]

### Neumann BCs
![[bcd21c1e3e0d32260dd3ef1f0f49ccb4e9e9137ad2bbf02e91b5f72d49da8f81.png]]


## Poisson Matrix
The equations defined in the nodes can in principle be arranged arbitrarily to compose a linear system of (𝑁𝑥− 2) × (𝑁𝑦− 2) equations.
However, meaningful arrangement can improve computation performance by exploiting sparsity patterns.

![[Pasted image 20260108172125.png]]

![[c83b5406a7f618890625deedd63b5ea20d9ee78ea28c74b352924034260d0444.png]]
![[9274d47bf35f6bb7d5d5a151f37eb3e963c75e814eb55f3db86b62bf8b9401ae.png]]


# Implementation of sparse matrices using Scipy
## Sparse Matrices
Poisson matrix is a large but sparse matrix (most coefficients are zero).
Scipy package implements efficient handlers and solvers for sparse systems.
If the matrix to be defined is structured with shared coefficient values (for instance, tridiagonal matrix with same values on the diagonals)
-> Use `scipy.sparse.spdiags` 

If the matrix definition is more complex, it might be necessary to define the coefficients with two nested loops, iterating through rows and columns
For instance, the Poisson matrix does not show same coefficients throughout entire diagonals
-> Use `scipy.sparse.lilmatrix` 


## lil_matrix
![[43a1a62e14055f2437b298ce8958b9f6ecec1e79aa7c0c4bc9db55366364a66b.png]]
![[c89c24e81b68fe74081069e3d570f1dc16ce23cf98c78ce6598b5292d70c381c.png]]

lil_matrix:
- "list of lists": a flexible builder before converting into a fast solver format.
- NOT ready for fast solving. Need to be converted to efficient format. 
- `scipy.sparse.spsolve(A,b)` can only solve sparse matrix
	 recommend `.tocsr()` or `.tocsc()`
```
A = lil_matrix((N,N))
A_csr = A.tocsr()
sol = scipy.sparse.spsolve(A_csr,b)
```
