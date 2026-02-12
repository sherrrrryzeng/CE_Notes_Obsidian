# Lecture 6

## BVPs
The number of sufficient conditions for integration = order

**Homogeneous**: 
- A linear ODE : ==y=0== 
- A boundary condition : ==y=0== 

Assume $\frac{d^2y}{dx^2}=f(x)$
- **Dirichlet** boundary condition: $y=g$
- **Neumann** boundary condition: $\frac{dy}{dx}=g$
- **Robin** boundary condition: $ay+b\frac{dy}{dx}=g$
- **Cauchy** boundary condition: $y=g\,\,\,\,\&\,\,\, \frac{dy}{dx}=p$
- **Periodic** boundary condition: $y(x_0)=y(x_1)\,\,or\,\,\frac{dy}{dx}|_{x_0}=\frac{dy}{dx}|_{x_1}$

Differentiation: the Finite Difference Approach (Central)
$$\frac{dy}{dx}|_{x_i}=\frac{y_{i+1}-y_{i-1}}{2h}$$ $$\frac{d^2y}{dx^2}|_{x_i}=\frac{y_{i+1}-2y_i+y_{i-1}}{h^2}$$ The equation becomes: $$\frac{y_{i+1}-2y_i+y_{i-1}}{h^2}+\alpha\frac{y_{i+1}-y_{i-1}}{2h}+\beta y_i=f(x_i)$$ Rearrange: $$y_{i-1}\left(1-\frac{h}{2}\alpha\right)+y_i(h^2\beta-2)+y_{i+1}\left(1+\frac{h}{2}\alpha\right)=h^2f(x_i)$$ 
 - **Option 1**: 
	 Assemble and solve the full system, including the known boundary nodes. Final matrix form ($\mathbf{A}y=\mathbf{b}$): $$
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
\right)$$
	Then **solve** this linear system of equations using Jacobi, Gauss-Seidel or `np.linalg.solve(a_matrix, b_vector)`
	
	
- **Option 2**: 
	Remove the known boundary nodes and solve a reduced system for only the interior nodes. Start with the finite (central) difference equation at a generic interior node i.
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

Discretization with Neumann boundary condition
Equation:$$-k\frac{d^2T}{dx^2}=Q$$Finite Difference approach: 
$$T_{i-1}-2T_i+T_{i+1}=-Sh^2$$ Boundary condition: $\frac{dT}{dx}|_{x=L}=0$. use **backward difference scheme**: $$T_{N-1}=T_{N-2}$$ Case **==i=N-2==**: $$1T_{N-3}-1T_{N-2}=-Sh^2$$ 
Accuracy of backward difference discretization: 
	- Backward-difference is only **first order accurate**. Central-difference is **second order accurate**. Thus, extend the grid by adding ==a ghost point== $x_N$: $$\frac{dT}{dx}|_{x=L}\approx\frac{T_N-T_{N-2}}{2h}$$ Case **==i=N-1==**: $T_N=T_{N-2}$ $$1T_{N-2}-2T_{N-1}+1T_N=-Sh^2 \to 2T_{N-2}-2T_{N-1}=-Sh^2$$ $$\begin{pmatrix}
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
Upwind and Downwind schemes: 
 *The more accurate discretization schemes(e.g., central) are not always a good idea. (could be unstable and inaccurate)*
- The upwind/downwind difference scheme takes into account the flow direction
- **Upwind** scheme uses points upstream - ==stable==


Finite Volume:
- divides the computational domain into control volumes (cells) and place nodes in the centre of volumes. 
- calculates the numerical integral over each face of the volume. 
- has good conservation properties.
- Applications: CFD(computational fluid dynamics), Heat and mass transfer modelling. 

Finite Elements Method (FEM):
- can automatically generate irregular grid.
- ==Most common method== for simulations of heat and mass transfer, fluids and mechanics. (in commercial simulation software e.g., Ansys, COMSOL).


# Lecture 7

## Shooting Method
- **Basic Core**
Updating guess: $$\frac{y_1(x_{N-1};\gamma_1)-y_1(x_{N-1};\gamma_0)}{\gamma_1-\gamma_0}=\frac{y_1(x_{N-1})-y_1(x_{N-1};\gamma_1)}{\gamma_2-\gamma_1}=$$ Next guess: $$\gamma_2=\gamma_1+(\gamma_1-\gamma_0)\frac{y_1(x_{N-1})-y_1(x_{N-1};\gamma_1)}{y_1(x_{N-1};\gamma_1)-y_1(x_{N-1};\gamma_0)}$$ 
- Linear interpolation directly yields correct guess for linear ODEs. 
- But for bad guesses, the next guess might be off
- Ideally, always use the root-finding using secant method. 


- **Root-finding with Secant Method**
Define a residual function measuring how far the boundary condition is from being satisfied: $$\phi(\gamma)=y_1(x_{N-1};\gamma)-y_1(x_{N-1})$$for $\gamma_{i+1}$: $$\phi(\gamma_{i+1})=y_1(x_{N-1};\gamma_{i+1})-y_1(x_{N-1})$$Taylor expansion:$$\phi(\gamma_{i+1})=\phi(\gamma_{i}+\triangle\gamma)+\frac{d\phi}{d\gamma}|_{\gamma_i}\triangle\gamma+o(\triangle\gamma^2)$$The optimal value for $\gamma$ satisfies $\phi(\gamma_i)=0$: $$0=\phi(\gamma_{i})+\frac{d\phi}{d\gamma}|_{\gamma_i}\triangle\gamma+o(\triangle\gamma^2)$$neglect $o(\triangle\gamma^2)$: $$\triangle\gamma=-\frac{\phi(\gamma_i)}{\frac{d\phi}{d\gamma}|_{\gamma_i}}=-\frac{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1})}{\frac{dy_1(x_{N-1};\gamma_i)}{d\gamma}}$$Approximate the derivative numerically (backward difference): $$\frac{dy_1(x_{N-1};\gamma_i)}{d\gamma}=\frac{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}{\gamma_i-\gamma_{i-1}}$$$$\triangle\gamma=-(y_1(x_{N-1};\gamma_i)-y_1(x_{N-1}))\frac{\gamma_i-\gamma_{i-1}}{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}$$
$$\gamma_{i+1}=\gamma_i-(y_1(x_{N-1};\gamma_i)-y_1(x_{N-1}))\cdot\frac{\gamma_i-\gamma_{i-1}}{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}$$
The equation is the same.

\*The shooting method solves IVPs. Hence, it inherits the **stability (or instability) of the associated IVP solver**

==Loop intuition:==
- Start
	-system of 1st order ODEs
	-initial guesses $\gamma_0,\,\,\gamma_1$
	-solve IVP with $\gamma_0,\,\,\gamma_1 \to y_1(x_{N-1};\gamma_0),\,\,y_1(x_{N-1};\gamma_1)$
- Check
	-$|\phi|=|y_1(x_{N-1};\gamma_i)-y_1(x_{N-1})|\leq\epsilon$
- Then
	-compute $\gamma_{i+1}=\gamma_i-(y_1(x_{N-1};\gamma_i)-y_1(x_{N-1}))\cdot\frac{\gamma_i-\gamma_{i-1}}{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}$
	-solve IVP with $\gamma_{i+1} \to y_1(x_{N-1};\gamma_{i+1})$
	-set $\gamma_i=\gamma_{i+1},\,\,\gamma_{i-1}=\gamma_i$


- **Shooting Method for M equations(Matrix)**
For M equations:
$$
\Delta \boldsymbol{\gamma} = 
\mathbf{J}(x_{N-1}; \boldsymbol{\gamma})^{-1}
\begin{pmatrix}
y_{j[0]}(x_{N-1}; \boldsymbol{\gamma}_{j[0]}) \\
\vdots \\
y_{j[-1]}(x_{N-1}; \boldsymbol{\gamma}_{j[-1]})
\end{pmatrix}
$$
With $J(x_{N-1};\gamma)$ being the Jacobian: $$
\mathbf{J}(x_{N-1}; \boldsymbol{\gamma}) =
\begin{pmatrix}
\frac{\partial y_{j[0]}}{\partial \gamma_{j[0]}} & \cdots & \frac{\partial y_{j[0]}}{\partial \gamma_{j[-1]}} \\
\vdots & \ddots & \vdots \\
\frac{\partial y_{j[-1]}}{\partial \gamma_{j[0]}} & \cdots & \frac{\partial y_{j[-1]}}{\partial \gamma_{j[-1]}}
\end{pmatrix}
$$
The differentiations are approximated with previous guess, only exact for linear ODEs


- **The Multiple Shooting Method (Advanced shooting method)**
  -Break domain into sub-domains and solve IVP in each sub-domain. 
  -Add continuity and boundary conditions for each sub-domain. 
  -Pros: Improved stability. Parallelization. More flexibility for initial guesses. 


## Built-in for BVPs
- `scipy.solve_bvp(func,bc,x,y_guess)`
	-bc: Boundary conditions defined as a function.![[327d30dcd19ba4ec7600134258b79599d3f7d8aa3a4c246ba328cdc8820f238c.png]]
	-x: Domain, must include domain boundaries. 
	-y_guess: Initial guess for function values.(usually zeros)
- Return: a tuple - (sol,x,y)
	-sol: Polynomial approximation of the solution. It's a function that takes grid points as input.
	-x: Nodes of the final mesh(grid points inside solver)
	-y: Solution values at the mesh nodes.