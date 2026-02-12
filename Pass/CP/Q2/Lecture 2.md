---
date: 2025-11-19
Prof: Zoë J.G. Gromotka
aliases:
  - Numerical methods for PDE
---
# Partial Differential Equation (PDE)
A partial differential equation is an equation involving partial derivatives of an unknown function with respect to more than one independent variable. $$\frac{\partial u}{\partial t}=\alpha\frac{\partial^2 u}{\partial x^2}+f(t,x,u)$$
In case of two independent variables, the solution is a bivariate function 𝑢 and can be visualized as a surface over the 2D domain (_x_, _t_) or (_x,_ _y_).

Alternative notations you may find in books and publications:$$u_x=\frac{\partial u}{\partial x},\,\,u_{xx}=\frac{\partial^2u}{\partial x^2},\,\,u_{xy}=u_{yx}=\frac{\partial^2u}{\partial x\partial y}$$$$u_t=\dot{u}=\frac{\partial u}{\partial t}$$
- **Order**: the highest-order partial derivative
- **Linear**: If the dependent variable($u$) and its partial derivatives appear only linearly (only degree one, no products/nonlinear functions), otherwise it is non-linear. $$\frac{\partial u}{\partial x}+\frac{\partial u}{\partial y}+f(x,y)\cdot u+g(x,y,u)=0$$ where:
     u: dependent variable
     x, y: independent variable
     $f(x, y)\cdot u$: a linear function of u
     $g(x,y,u)$: a nonlinear function. 
     \* If $g(x,y,u)=0$, then the PDE above is linear. 

> [!Example]
>    Linear: $$xy\cdot\frac{\partial u}{\partial x}+\left(\frac{1}{x}+y\right)\frac{\partial u}{\partial y}+(3x-y)\cdot u=f(x,y)$$
>    Non-linear: $$u\cdot\frac{\partial u}{\partial x} + \left(\frac{1}{x}\cdot u \right) \frac{\partial u}{\partial y} + (3x - y u^2) \cdot u = f(x,y,u)$$
> 


## Parabolic PDE
The general form of (bivariate) second-order linear PDEs is: $$a\frac{\partial^2u}{\partial x^2}+b\frac{\partial^2u}{\partial x\partial y}+c\frac{\partial^2u}{\partial y^2}+d\frac{\partial u}{\partial x}+e\frac{\partial u}{\partial y}+fu+g=0$$
- **Discriminant**: the quantity $D=b^2-4ac$ 
	- $D>0$: **Hyperbolic** PDE
	- $D=0$: **Parabolic** PDE
	- $D<0$: **Elliptic** PDE
	\* In this course, we cover solution methods for parabolic and elliptic PDEs. ($D<=0$)

Example: 
	The two independent variables are time and 1D space. Generally, we refer to as 1D parabolic PDE (referring only to spatial coordinates)
![[49c42d01c6147d058bb0ffeaa820518cbc5db9834727272e100331760584afce.png]]


## Initial & Boundary conditions
- **Initial conditions**: quantity specified for the solution of a PDE at the beginning of the time interval.
- **Boundary conditions**: quantity specified for the solution of a PDE (or its derivatives) along the boundaries of the spatial domain.

In general, you need **==a condition for each order==** of derivative appearing in the equation.
- Time derivative -> IC
- 1D spatial derivative -> BC

> [!Example]
> $\frac{\partial u}{\partial t}=\alpha\frac{\partial^2u}{\partial x^2}$ -> 1 IC, 2 BC
> $\frac{\partial^2u}{\partial t^2}=\beta\frac{\partial^2u}{\partial x^2}$ -> 2 IC, 2BC
> $$\frac{\partial^2u}{\partial x^2}+\alpha\frac{\partial^2u}{\partial y^2}=f(x,y)$$
> -> 2 BC(x direction) + 2 BC(y direction)


## Finite Difference Method for PDEs
![[7c4a1910927fd6419bb8da68a3a2f25c7a4b6e597908e9aa041c3a5fa8fcf056.png]]
Discretize multivariate domains
![[76fb7d75a80d2f97b7120f0afe3f7180671745db18a1d093aed5502be8f613ec.png]]
- Every variable will have its own (possibly different) discretization scheme
	 In general $h_x\neq h_y$. 
	 **Often** $h_x=h_y$.
- The choice of time step $\triangle t$ depends on the **stability** of the system. 

Ghost point -> Artificial points![[67c063a956d068e01786fdc4ef355c895863a1a9e8b3f620862b7aed2bf6089c.png]]


# Main techniques to solve PDE in Engineering
\<Case>  heat transport problem - unsteady heat transport in 1D *(e.g., tube wall - symmetric)* -> Parabolic PDE$$\frac{\partial T}{\partial t}=\alpha\frac{\partial^2T}{\partial x^2}$$Consider heat transfer across the wall of a tube in a shell-and-tube heat exchanger:
- **BC**: The temperatures of the process fluid (tube side) and coolant (shell side) are known. 
- **IC**: Initially, the tube wall is in thermal equilibrium with the coolant. 


## Semidiscrete Method: PDE to ODE
A way to approximate the solution of transient PDEs is 
- initially discretize in space 
- leave the time variable continuous
Introduce **spatial mesh points**: $x_i,\,i=0,1,...,N_x-1$, where $i$ is the discretization index and $\triangle x$ is the interval. 

At $x_i$, $T_i=T_i(t)$ is time dependent, then $$\frac{dT_i}{dt}=\alpha\frac{T_{i-1}-2{T_i}+T_{i+1}}{\triangle x^2}$$
With IC & BC: $$T_i(0)=T_{coolant}$$$$T_0(0)=T_{process},\,\,T_{N_x-1}(t)=T_{coolant}$$

In matrix form: $$\frac{d}{dt}\mathbf{T}=\frac{\alpha}{\triangle x^2}A\mathbf{T}_{complete}$$
which equals to$$\frac{d}{dt}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-2}
\end{pmatrix}=\frac{\alpha}{\triangle x^2}A\begin{pmatrix}
T_0\\[4pt]
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-2}\\[4pt]
T_{N_x-1}
\end{pmatrix}$$
- Left side: only internal points
- Right side: includes boundary points

Matrix A: $$A=
\begin{pmatrix}
-1 & 2 & -1 & 0 & \cdots & 0 & 0\\[6pt]
0 & -1 & 2 & -1 & \cdots & 0 & 0\\[6pt]
\vdots & & \ddots & \ddots & \ddots & & \vdots\\[6pt]
0 & 0 & \cdots & 0 & -1 & 2 & -1
\end{pmatrix}$$
A vector with the initial condition (IC): $$\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}(0)
=
\begin{pmatrix}
T_c\\[4pt]
T_c\\[4pt]
\vdots\\[4pt]
T_c\\[4pt]
T_c
\end{pmatrix}$$

### Dirichlet Boundary Conditions
Consider Dirichlet boundary conditions $T_0=T_p,\,T_{N_x-1}=T_c$ 
$i=1$: $$\frac{dT_1}{dt}=\frac{\alpha}{\triangle x^2}(T_p-2T_1+T_2)=\frac{\alpha}{\triangle x^2}(-2T_1+T_2)+\frac{\alpha}{\triangle x^2}T_p$$
$i=N_{x}-2$: $$\frac{dT_{N_x-2}}{dt}=\frac{\alpha}{\triangle x^2}(T_{N_x-3}-2T_{N_x-2}+T_c)=\frac{\alpha}{\triangle x^2}(T_{N_x-3}-2T_{N_x-2})+\frac{\alpha}{\triangle x^2}T_c$$
The final equation is: $$\frac{d}{dt}\mathbf{T}=\frac{\alpha}{\triangle x^2}(A\mathbf{T}+\mathbf{b}),\,\,\,\,\mathbf{T}(0)=\mathbf{T}_c$$ $$\frac{d}{dt}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}
=
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
-2 & 1  & 0  & \cdots & \cdots & 0\\[4pt]
1  & -2 & 1  & 0      & \cdots & 0\\[4pt]
\vdots & \ddots & \ddots & \ddots &        & \vdots\\[4pt]
0 & \cdots & 0 & 1 & -2 & 1\\[4pt]
0 & 0 & \cdots & 0 & 1 & -2
\end{pmatrix}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}
+
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
T_p\\[4pt]
0\\[4pt]
\vdots\\[4pt]
0\\[4pt]
T_c
\end{pmatrix}$$$\mathbf{b}$ represents boundary conditions (BCs). 


### Neumann Boundary Conditions
For completeness, consider now the case of Neumann boundary conditions: $$\frac{\partial T}{\partial x}|_{x=0}=\gamma_1$$ $$\frac{\partial T}{\partial x}|_{x=L}=\gamma_2$$
Discretization scheme 1:
- First order derivative in 𝑥 = 0 → **Forward** difference scheme
$i=1$: $$\frac{T_1-T_0}{\triangle x}=\gamma_1,\,\,T_0=T_1-\gamma_1\triangle x$$$$\frac{dT_1}{dt}=\frac{\alpha}{\triangle x^2}(T_0-2T_1+T_2)=\frac{\alpha}{\triangle x^2}(-T_1+T_2)-\frac{\alpha}{\triangle x}\gamma_1$$
- First order derivative in 𝑥 = L → **Backward** difference scheme
$i=N_{x}-2$: $$\frac{T_{N_x-1}-T_{N_x-2}}{\triangle t}=\gamma_2,\,\,T_{N_x-1}=T_{N_x-2}+\gamma_2\triangle x$$$$\frac{dT_{N_x-2}}{dt}=\frac{\alpha}{\triangle x^2}(T_{N_x-3}-2T_{N_x-2}+T_{N_x-1})=\frac{\alpha}{\triangle x^2}(T_{N_x-3}-T_{N_x-2})+\frac{\alpha}{\triangle x}\gamma_2$$
The final equation is: $$\frac{d}{dt}\mathbf{T}=\frac{\alpha}{\triangle x^2}(A\mathbf{T}+\mathbf{b}),\,\,\,\,\mathbf{T}(0)=\mathbf{T}_c$$ $$\frac{d}{dt}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}
=
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
-1 & 1  & 0  & \cdots & \cdots & 0\\[4pt]
1  & -2 & 1  & 0      & \cdots & 0\\[4pt]
\vdots & \ddots & \ddots & \ddots &        & \vdots\\[4pt]
0 & \cdots & 0 & 1 & -2 & 1\\[4pt]
0 & 0 & \cdots & 0 & 1 & -1
\end{pmatrix}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}
+
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
-\gamma_1\triangle x\\[4pt]
0\\[4pt]
\vdots\\[4pt]
0\\[4pt]
\gamma_2\triangle x
\end{pmatrix}$$ Initial condition: $$\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}(0)
=
\begin{pmatrix}
T_c\\[4pt]
T_c\\[4pt]
\vdots\\[4pt]
T_c\\[4pt]
T_c
\end{pmatrix}$$
### Neumann BC with Ghost points
Discretization scheme 2:
- Central difference scheme is possible with **==ghost points==**
$i=0$: $$\frac{T_1-T_{-1}}{2\triangle x}=\gamma_1,\,\,T_{-1}=T_1-2\gamma_1\triangle x$$$$\frac{dT_0}{dt}=\frac{\alpha}{\triangle x^2}(T_{-1}-2T_0+T_1)=\frac{\alpha}{\triangle x^2}(-2T_0+2T_1)-2\frac{\alpha}{\triangle x}\gamma_1$$
- First order derivative in 𝑥 = L → Backward difference scheme
$i=N_{x}-1$: $$\frac{T_{N_x}-T_{N_x-2}}{2\triangle t}=\gamma_2,\,\,T_{N_x}=T_{N_x-2}+2\gamma_2\triangle x$$$$\frac{dT_{N_x-1}}{dt}=\frac{\alpha}{\triangle x^2}(T_{N_x-2}-2T_{N_x-1}+T_{N_x})=\frac{\alpha}{\triangle x^2}(2T_{N_x-2}-2T_{N_x-1})+2\frac{\alpha}{\triangle x}\gamma_2$$
The final equation is: $$\frac{d}{dt}\mathbf{T}=\frac{\alpha}{\triangle x^2}(A\mathbf{T}+\mathbf{b}),\,\,\,\,\mathbf{T}(0)=\mathbf{T}_c$$ $$\frac{d}{dt}
\begin{pmatrix}
T_0\\[4pt]
T_1\\[4pt]
\vdots\\[4pt]
T_{N_x-2}\\[4pt]
T_{N_x-1}
\end{pmatrix}
=
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
-2 & 2  & 0  & \cdots & \cdots & 0\\[4pt]
1  & -2 & 1  & 0      & \cdots & 0\\[4pt]
\vdots & \ddots & \ddots & \ddots &        & \vdots\\[4pt]
0 & \cdots & 0 & 1 & -2 & 1\\[4pt]
0 & 0 & \cdots & 0 & 2 & -2
\end{pmatrix}
\begin{pmatrix}
T_0\\[4pt]
T_1\\[4pt]
\vdots\\[4pt]
T_{N_x-2}\\[4pt]
T_{N_x-1}
\end{pmatrix}
+
\frac{\alpha}{\Delta x^2}
\begin{pmatrix}
-2\gamma_1\triangle x\\[4pt]
0\\[4pt]
\vdots\\[4pt]
0\\[4pt]
2\gamma_2\triangle x
\end{pmatrix}$$

## Semidiscrete Method: Solution methods
PDEs -> ODEs -> IVPs![[30325e0d22bb1d861809e0f63101a6837f79505d1702f0d9a7adf3d3ac47bbeb.png]]
**Semidiscrete method** includes:
- Discretize in the spatial domain (FDM)
- Solver for IVP

### Forward(Explicit) Euler Method
The simplest choices for solving ODEs systems
$$t_k=k\cdot\triangle t$$
$$\frac{dT_i}{dt}=\frac{T_i^{k+1}-T_i^k}{\triangle t}=\alpha\frac{T_{i-1}^{k}-2T_{i}^{k}+T_{i+1}^{k}}{\triangle x^2}$$ The **updating closed form** for every ==internal== point: $$Fo=\frac{\alpha\triangle t}{\triangle x^2}$$$$T_i^{k+1}=T_i^k+Fo(T_{i-1}^{k}-2T_{i}^{k}+T_{i+1}^{k})$$

BC determine final form of the system equations:
- **Dirichlet** BC:![[2db0f7912e51929d3b8683d80b7b88e335da2157f27f55ab23fda2762bc976e7.png]]

- **Neumann** BC: ![[881d41b865b3320aa80d35c8df9243e0338c9ce3eaeebbfae7a3d3caa8ac167a.png]]

- **Add ghost points**:![[d422b62c4917ec68d78411db13c49e058b344971ec634d590dfbfed1893c404f.png]]


To avoid for-loops, work in matrix form: $$\mathbf{T}^{k+1}=\mathbf{T}^k+Fo(A\mathbf{T}^k+\mathbf{b})$$
Final matrix form for **Dirichlet** BCs: Forward Euler $$\mathbf{T}^{\,k+1}=Fo\;A_{DF}\,\mathbf{T}^{\,k}+Fo\;\mathbf{b}_{DF}$$
$$\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}^{k+1}
=
Fo\;
\begin{pmatrix}
\frac{1}{Fo}-2 & 1 & 0 & \cdots & \cdots & 0\\[6pt]
1 & \frac{1}{Fo}-2 & 1 & 0 & \cdots & 0\\[6pt]
\vdots & \ddots & \ddots & \ddots & & \vdots\\[6pt]
0 & \cdots & 0 & 1 & \frac{1}{Fo}-2 & 1\\[6pt]
0 & 0 & \cdots & 0 & 1 & \frac{1}{Fo}-2
\end{pmatrix}
\begin{pmatrix}
T_1\\[4pt]
T_2\\[4pt]
\vdots\\[4pt]
T_{N_x-3}\\[4pt]
T_{N_x-2}
\end{pmatrix}^{k}
\;+\;
Fo\;
\begin{pmatrix}
T_p\\[4pt]
0\\[4pt]
\vdots\\[4pt]
0\\[4pt]
T_c
\end{pmatrix}$$

Final matrix form for **Neumann** BCs: 
1. Forward Euler $$\mathbf{T}^{\,k+1}=Fo\;A_{NF}\,\mathbf{T}^{\,k}+Fo\;\mathbf{b}_{NF}$$ $$\begin{pmatrix}
T_1\\[2pt]
T_2\\[2pt]
\vdots\\[2pt]
T_{N_x-3}\\[2pt]
T_{N_x-2}
\end{pmatrix}^{k+1}
=
Fo\;
\begin{pmatrix}
\frac{1}{Fo}-1 & 1 & 0 & \cdots & 0 & 0\\[2pt]
1 & \frac{1}{Fo}-2 & 1 & 0 & \cdots & 0\\[2pt]
\vdots & \ddots & \ddots & \ddots & & \vdots\\[2pt]
0 & \cdots & 0 & 1 & \frac{1}{Fo}-2 & 1\\[2pt]
0 & \cdots & 0 & 0 & 2 & \frac{1}{Fo}-1
\end{pmatrix}
\begin{pmatrix}
T_1\\[2pt]
T_2\\[2pt]
\vdots\\[2pt]
T_{N_x-3}\\[2pt]
T_{N_x-2}
\end{pmatrix}^{k}
\;+\;
Fo\;
\begin{pmatrix}
-\gamma_1\triangle x\\[2pt]
0\\[2pt]
\vdots\\[2pt]
0\\[2pt]
\gamma_2\triangle x
\end{pmatrix}$$
2. Forward Euler with **==ghost points==** $$\mathbf{T}_G^{\,k+1}=Fo\;A_{NFG}\,\mathbf{T}_G^{\,k}+Fo\;\mathbf{b}_{NFG}$$ $$\begin{pmatrix}
T_0\\[2pt]
T_1\\[2pt]
T_2\\[2pt]
\vdots\\[2pt]
T_{N_x-3}\\[2pt]
T_{N_x-2}\\[2pt]
T_{N_x-1}
\end{pmatrix}^{k+1}
=
Fo\;
\begin{pmatrix}
\frac{1}{Fo}-2 & 2 & 0 & \cdots & 0 & 0\\[2pt]
1 & \frac{1}{Fo}-2 & 1 & 0 & \cdots & 0\\[2pt]
\vdots & \ddots & \ddots & \ddots & & \vdots\\[2pt]
0 & \cdots & 0 & 1 & \frac{1}{Fo}-2 & 1\\[2pt]
0 & \cdots & 0 & 0 & 2 & \frac{1}{Fo}-2
\end{pmatrix}
\begin{pmatrix}
T_0\\[2pt]
T_1\\[2pt]
T_2\\[2pt]
\vdots\\[2pt]
T_{N_x-3}\\[2pt]
T_{N_x-2}\\[2pt]
T_{N_x-1}
\end{pmatrix}^{k}
\;+\;
Fo\;
\begin{pmatrix}
-2\gamma_1\triangle x\\[2pt]
0\\[2pt]
\vdots\\[2pt]
0\\[2pt]
2\gamma_2\triangle x
\end{pmatrix}$$


## Stability of numerical solution approaches
Forward Euler: 
- **Pros**: simple implementation & explicit formula & efficient computation
- **Cons**: stability issues & potential memory issues *(required small time steps)*


**Stability criterion** for explicit methods 
   -> ==**Courant-Firedrichs-Lewy(CFL) condition**==:
A **necessary** condition for the convergence of parabolic PDEs. 
It states that, given an arbitrary space step, the time step must be necessarily small "enough" to converge. 
For 1D problems parabolic PDEs: $$Fo=\frac{\alpha\triangle t}{\triangle x^2}\leq\frac{1}{2}$$
   $Fo$: Fourier number (dimensionless)



An **==alternative==** to explicit methods to avoid instability issues -> **Backward Euler**
$$\frac{\partial\mathbf{T}}{\partial t}=\frac{\mathbf{T}^{k+1}-\mathbf{T}^k}{\triangle t}=\frac{\alpha}{\triangle x^2}(A\mathbf{T}^{k+1}+\mathbf{b})$$
\* A and b depend on the dv and BCs
Thus, giving the updating closed form: $$(I-FoA)\mathbf{T}^{k+1}=\mathbf{T}^{k}+Fo\mathbf{b}$$

# Built-in to support the solution of parabolic PDE
![[7ac78547056413a1d7aa76902932bb767f47c552e8670cee0c2d586dc977de70.png]]
Except for Forward/Backward Euler, we can use:
- `scipy.integrate.solve_ivp()` (Runge-Kutta)
To speed up computation 
  ->  exploit the **sparsity** of the discretization matrices.
- `scipy.sparse.spdiag(data,diags,m,n)`
	 Define a sparse diagonal matrix. (Not numpy.array)
	 `data`: 2D array. Every row is the data for one diagonal.  `data=[a,b,c]`
	 `diag`: k=0(diagonal), -1(lower diagonal), 1(upper diagonal),... `diag=[-1,0,1]`
	 `m,n`: the size of the matrix
	![[a174b38f599a8daad6ba2bca22a3cf979fb7c4ee987b69877da6f7ff16c8ef56.png]]
	 data=\[lower, main, upper]
	 diags=\[-1, 0, 1]

- `scipy.sparse.linalg.spsolve`
	 solve sparse linear systems efficiently
	 ![[81ce96a6fc1f609e65f01a3cdd0fadeb526e7d1dd204a53fe2c0e2598bcd8041.png]]
