---
date: 2025-10-15
Prof: Zoë J.G. Gromotka
aliases:
  - Shooting method
---
# Boundary Value Problem(BVP)
## Shooting method
Guess an initial value $\gamma_0$
Adjust the guess $\gamma_1$
......
Get the right answer


How to make clever guesse
\<Example>
ODE:$$\frac{d^2y}{dx^2}=4(y-x)$$
Domain $x\in[0,1]$
Boundary conditions $y(0)=0,\,\,y(1)=2$
Variable substitution:$$y_1=y,\,\,y_2=\frac{dy_1}{dx}$$
1st order ODE system:$$\frac{dy_1}{dx}=y_2,\,\,\frac{dy_2}{dx}=4(y_1-x)$$
Initial conditions:$$y_1(0)=0,\,\,y_2(0)=?$$
1. Make a random guess for the initial condition of $y_2$: $$y_2(0)=\gamma_0$$
2. Solve the ODE system with the IVP methods (e.g. Forward Euler method)
3. Evaluate the solution and update the guess $\gamma$ for $y_2(0)$ until $y_1(1;\gamma)=2$


How to update guess?
### Linear interpolation
- Take two random guesses $\gamma_0, \gamma_1$ 
- Compute next guess using linear interpolation between the previous two results:$$\frac{\triangle y_{1,0\to 1}}{\triangle \gamma_{0\to 1}}=\frac{\triangle y_{1,1\to 2}}{\triangle \gamma_{1\to 2}}$$$$\frac{y_1(x_{N-1};\gamma_1)-y_1(x_{N-1};\gamma_0)}{\gamma_1-\gamma_0}=\frac{y_1(x_{N-1})-y_1(x_{N-1};\gamma_1)}{\gamma_2-\gamma_1}$$
Guess$$\gamma_2=\gamma_1+(\gamma_1-\gamma_0)\frac{y_1(x_{N-1})-y_1(x_{N-1};\gamma_1)}{y_1(x_{N-1};\gamma_1)-y_1(x_{N-1};\gamma_0)}$$
Advantage:
- **Linear interpolation directly yields correct guess** for linear ODEs
Disadvantage:
- In practice, the solution from the IVP solver 𝑦(1; 𝛾𝑖) is not exact
	-For bad guesses 𝛾0, 𝛾1, the next guess 𝛾2 might be off

Therefore, ideally always use the root-finding using secant method.


### Secant method
Define a **residual function** measuring how far the boundary condition is from being satisfied: $$\phi(\gamma)=y_1(x_{N-1};\gamma)-y_1(x_{N-1})$$
for $\gamma_{i+1}$: $$\phi(\gamma_{i+1})=y_1(x_{N-1};\gamma_{i+1})-y_1(x_{N-1})$$
Taylor expansion:$$\phi(\gamma_{i+1})=\phi(\gamma_{i}+\triangle\gamma)+\frac{d\phi}{d\gamma}|_{\gamma_i}\triangle\gamma+o(\triangle\gamma^2)$$
The optimal value for $\gamma$ satisfies $\phi(\gamma_i)=0$: $$0=\phi(\gamma_{i})+\frac{d\phi}{d\gamma}|_{\gamma_i}\triangle\gamma+o(\triangle\gamma^2)$$
neglect $o(\triangle\gamma^2)$: $$\triangle\gamma=-\frac{\phi(\gamma_i)}{\frac{d\phi}{d\gamma}|_{\gamma_i}}=-\frac{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1})}{\frac{dy_1(x_{N-1};\gamma_i)}{d\gamma}}$$
Approximate the derivative numerically (backward difference): $$\frac{dy_1(x_{N-1};\gamma_i)}{d\gamma}=\frac{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}{\gamma_i-\gamma_{i-1}}$$$$\triangle\gamma=-(y_1(x_{N-1};\gamma_i)-y_1(x_{N-1}))\frac{\gamma_i-\gamma_{i-1}}{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}$$
$$\gamma_{i+1}=\gamma_i+(\gamma_i-\gamma_{i-1})\cdot\frac{(y_1(x_{N-1})-y_1(x_{N-1};\gamma_i))}{y_1(x_{N-1};\gamma_i)-y_1(x_{N-1};\gamma_{i-1})}$$

*\*The shooting method solves IVPs. Hence, it inherits the stability (or instability) of the associated IVP solver*

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

### Advanced shooting methods
Breaks domain into sub-domains and solves IVP in each sub-domain.
Add continuity and boundary conditions for each sub-domain.

Advantages:
-  Improved stability
-  Parallelization
+ More flexibility for initial guesses
![[795ae9534db3465dbd7431e642234528722ee6d0e788561ca72c48d7d04a9376.png]]

Finite difference method:
- ODE is solved only once
- Nonlinear ODEs require to solve a system of nonlinear equations

Shooting method:
- Solution of nonlinear equations is fairly straightforward
- ODE needs to be solved several times.


## Solve_bvp method
Uses the collocation method:
- modification of the Multiple Shooting Method and the Finite Difference Method.

Function arguments:
- _fun_: Function containing the ODE system.
- _bc_: Boundary conditions defined as a function.
- _x:_ Domain, must include domain boundaries.
- _y_: Initial guess for function values.

Return (_solve_bvp_ returns a tuple including, besides others):
- _sol_: Polynomial approximation of the solution. This is a function that takes **grid points as input**.
- _x_: Nodes of the final mesh (grid points inside solver).
- _y_: Solution values at the mesh nodes.
Note the difference between _sol_ and _y_ !
