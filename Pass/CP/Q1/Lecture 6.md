---
date: 2025-10-08
Prof: Zoë J.G. Gromotka
aliases:
  - Boundary value problems(BVPs)
---
# Boundary value problems (BVPs)

- sufficient conditions for integration:
	-ODE 2nd order -> 2 conditions
	-ODE 4th order -> 4 conditions

- Definition of BVP:
	An ODE does not uniquely determine a solution. Additional side conditions must be imposed on the solution to make it unique. These side conditions prescribe values that the solution or its derivatives must have at some specified point or points.
	If all side conditions are specified at the **same point**, then we have an **initial value problem**(**IVP)**.
	If the side conditions are specified at **more than one point**, then we have a **boundary value** **problem** (**BVP)**.
	For an ODE in ℝ, the side conditions are typically specified at two points, namely the endpoints of some interval \[a, b], which is why the side conditions are called boundary conditions or boundary values.

## Boundary conditions

- Definition:
	A linear ODE is **homogeneous** if 𝑦 = 0 is a solution of the ODE. Otherwise, the ODE is **inhomogeneous.**
	*For example, $\frac{dy}{dx}+3y=2$ is inhomogeneous because 𝑦 = 0 is not a valid solution.*
	A boundary condition is **homogeneous** if 𝑦 = 0 satisfies it. Otherwise, the boundary condition is **inhomogeneous.**
	*For example,$y(x=0,a)=0$∀𝑎 is homogeneous, but $y(x=0,a)=5a$ ∀𝑎 is not homogeneous.*


Assume $\frac{d^2y}{dx^2}=f(x)$
- **Dirichlet** boundary condition:
	-Specifies the value of the function - $y=g$
- **Neumann** boundary condition:
	-Specifies the value of the derivative - $\frac{dy}{dx}=g$

Mixed boundary condition
- **Robin** boundary condition:
	-Specifies the combination of function and derivative value $$ay+b\frac{dy}{dx}=g$$
- **Cauchy** boundary condition: *(for 3rd or higher order BVPs)*
	-Specifies the value of the function and the derivative at different sections of the boundary$$y=g\,\,\,\,\text{and}\,\,\, \frac{dy}{dx}=p$$
- **Periodic** boundary condition:
	-Specifies the solution or its derivatives at two distinct points 𝑥 = 𝑥0 and 𝑥 = 𝑥1 are equal. $$y(x_0)=y(x_1)\,\,or\,\,\frac{dy}{dx}|_{x_0}=\frac{dy}{dx}|_{x_1}$$


## Differentiation

Equation:$$\frac{d^2y}{dx^2}+\alpha\frac{dy}{dx}+\beta y=f(x)$$
Domain: \[a,b]
Boundary conditions: $y(a)=y_a,\,\,y(b)=y_b$

Discretization:![[97e83cc883d1e1225123480612d2c30385f22440beb658ca8d47d70897e63d0a.png]]
Finite differences:$$\frac{dy}{dx}|_{x_i}=\frac{y_{i+1}-y_{i-1}}{2h}$$
$$\frac{d^2y}{dx^2}|_{x_i}=\frac{y_{i+1}-2y_i+y_{i-1}}{h^2}$$


## Finite difference method

- Equation:$$\frac{d^2y}{dx^2}+\alpha\frac{dy}{dx}+\beta y=f(x)$$
Finite (Central) Difference Equations:$$\frac{y_{i+1}-2y_i+y_{i-1}}{h^2}+\alpha\frac{y_{i+1}-y_{i-1}}{2h}+\beta y_i=f(x_i)$$
$i$ :\[1,N-2] -> would be out of range for $i=0$ or $i=N-1$

Rearrange: $$y_{i-1}\left(1-\frac{h}{2}\alpha\right)+y_i(h^2\beta-2)+y_{i+1}\left(1+\frac{h}{2}\alpha\right)=h^2f(x_i)$$

- **Option 1**: Assemble and solve the full system, including the known boundary nodes. 
	Final matrix form (Ay=b): $$
\left(
\begin{array}{cccccc}
1 & 0 & \cdots & \cdots & \cdots & 0 \\[4pt]
1 - \tfrac{h}{2}\alpha & h^2\beta - 2 & 1 + \tfrac{h}{2}\alpha & \cdots & \cdots & 0 \\[4pt]
0 & \ddots & \ddots & \ddots & & \vdots \\[4pt]
\vdots & \ddots & 1 - \tfrac{h}{2}\alpha & h^2\beta - 2 & 1 + \tfrac{h}{2}\alpha & \vdots \\[4pt]
\vdots & & \cdots & 1 - \tfrac{h}{2}\alpha & h^2\beta - 2 & 1 + \tfrac{h}{2}\alpha \\[4pt]
0 & \cdots & \cdots & 0 & 0 & 1
\end{array}
\right)
\left(
\begin{array}{c}
y_0 \\[4pt]
y_1 \\[4pt]
\vdots \\[4pt]
y_{N-2} \\[4pt]
y_{N-1}
\end{array}
\right)
=
\left(
\begin{array}{c}
y_a \\[4pt]
h^2 f(x_2) \\[4pt]
\vdots \\[4pt]
h^2 f(x_{N-2}) \\[4pt]
y_b
\end{array}
\right)
$$
	Then **solve** this linear system of equations using Jacobi, Gauss-Seidel or `np.linalg.solve(a_matrix, b_vector)`

- **Option 2**: Remove the known boundary nodes and solve a reduced system for only the interior nodes. 
	Start with the finite (central) difference equation at a generic interior node i.
	Continue constructing matrix form:
	1. $i=1$: here $y_{i-1}=y_0=y_a$. Move the known term to the RHS.$$y_1(h^2\beta-2)+y_2\left(1+\frac{h}{2}\alpha\right)=h^2f(x_1)-y_a\left(1-\frac{h}{2}\alpha\right)$$
	2. $1<i<N-2$: Neither neighbour is a boundary, so keep the standard form. $$y_{i-1}\left(1-\frac{h}{2}\alpha\right)+y_i(h^2\beta-2)+y_{i+1}\left(1+\frac{h}{2}\alpha\right)=h^2f(x_i)$$
	3. $i=N-2$: here $y_{i+1}=y_{N-1}=y_b$. Move the known term to the RHS.$$y_{N-3}\left(1-\frac{h}{2}\alpha\right)+y_{N-2}(h^2\beta-2)=h^2f(x_{N-2})-y_{b}\left(1+\frac{h}{2}\alpha\right)$$
	Final matrix form only contains interior points:$$
\begin{pmatrix}
h^2 \beta - 2 & 1 + \frac{h}{2} \alpha & & & \\
1 - \frac{h}{2} \alpha & h^2 \beta - 2 & 1 + \frac{h}{2} \alpha & & \\
& \ddots & \ddots & \ddots & \\
& & 1 - \frac{h}{2} \alpha & h^2 \beta - 2 & 1 + \frac{h}{2} \alpha \\
& & & 1 - \frac{h}{2} \alpha & h^2 \beta - 2
\end{pmatrix}
\begin{pmatrix}
y_1 \\
y_2 \\
\vdots \\
y_{N-3} \\
y_{N-2}
\end{pmatrix}
=
\begin{pmatrix}
h^2 f(x_1) - y_a \left( 1 - \frac{h}{2} \alpha \right) \\
h^2 f(x_2) \\
\vdots \\
h^2 f(x_{N-3}) \\
h^2 f(x_{N-2}) - y_b \left( 1 + \frac{h}{2} \alpha \right)
\end{pmatrix}
$$


### Discretization with Neumann boundary condition

Equation:$$-k\frac{d^2T}{dx^2}=Q$$
Boundary conditions:                     $T(x=0)=T_{start}$
$$\frac{dT}{dx}|_{x=L}=0$$

Discretization:$$T_{i-1}-2T_i+T_{i+1}=-Sh^2$$
$$T_{N-1}=T_{N-2}$$
- Matrix construction with Option 2:
	1. $-2T_1+T_2=-T_{start}-Sh^2$
	2. $1T_{i-1}-2T_i+1T_{i+1}=-Sh^2$
	3. $1T_{N-3}-1T_{N-2}=-Sh^2$
	$$\begin{pmatrix}
-2 & 1 & & & \\
1 & -2 & 1 & & \\
& \ddots & \ddots & \ddots & \\
& & 1 & -2 & 1 \\
& & & 1 & -2
\end{pmatrix}
\begin{pmatrix}
T_1 \\
T_2 \\
\vdots \\
T_{N-3} \\
T_{N-2}
\end{pmatrix}
=
\begin{pmatrix}
-T_{start} - Sh^2 \\
-Sh^2 \\
\vdots \\
-Sh^2 \\
-Sh^2
\end{pmatrix}$$



### Accuracy of backward difference discretization
Backward-difference is only **first order accurate**
Central-difference is **second order accurate**
	Second-order finite-difference stencil reproduces any quadratic exactly *(here the exact solution for 𝑇 is quadratic in 𝑥)*.
	The numerical and analytic solutions coincide, resulting in **zero error**, independent of the grid resolution.

**Solution**: introduce ==a ghost point==
- Extend the grid by adding $x_N$ ![[4b0b9435448edeb5e49917ec84e9adfced832598ac555adfbde2873bf08b6898.png]]
- Use the central difference scheme to achieve second order accuracy $$\frac{dT}{dx}|_{x=L}\approx\frac{T_N-T_{N-2}}{2h}$$
- Construct the matrix with Option 2:
	1. $-2T_1+T_2=-T_{start}-Sh^2$
	2. $1T_{i-1}-2T_i+1T_{i+1}=-Sh^2$
	3. $2T_{N-3}-2T_{N-2}=-Sh^2$
	$$\begin{pmatrix}
-2 & 1 & & & \\
1 & -2 & 1 & & \\
& 1 & -2 & 1 & \\
& & \ddots & \ddots & \ddots \\
& & & 2 & -2
\end{pmatrix}
\begin{pmatrix}
T_1 \\
T_2 \\
T_3 \\
\vdots \\
T_{N-1}
\end{pmatrix}
=
\begin{pmatrix}
-T_{start} - Sh^2 \\
-Sh^2 \\
-Sh^2 \\
\vdots \\
-Sh^2
\end{pmatrix}$$


## Discussion on upwind/downwind discretization schemes
![[e0e29504ebee6fdfe78b7177f8954956d4d6ec025267bd04c2dff25121529c6a.png]]
![[1641b807fbd0dffa97028a3d9f905821349d3c64c162aea4418ae23bf2d2dfa5.png]]


## Finite volumes and finite elements

- Finite Volumes:![[0d64d60c2db6a0be8dbd50dc8ed6ece5036ac27957a1fc8d0d4972059473ea8c.png]]
- Finite element method (FEM): ![[c43d74b675e7aeddf49101c7783914bebfb24af2c2eb34714c0dc7071b46f9ac.png]]
