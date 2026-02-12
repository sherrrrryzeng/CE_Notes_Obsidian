## $f(x)=0,x=?$
- Bisection Method
- Fixed-point Method
- Newton-Raphson Method
- `scipy.optimize.fsolve()`
- `scipy.optimize.root()`

## $\mathbf{A}\cdot\mathbf{x}=\mathbf{b}$
- Direct Method - Gaussian Elimination
- Jacobi Method
- Gauss-Seidel Method
- `scipy.linalg.solve(A,b)` (direct)
- Newton-Raphson Method for Non-linear

## $\int f(x)dx=?$
- Rectangle Method
- Midpoint Method
- Trapezoid Method
- Simpson's Method
- `numpy.trapz(A)`
- `scipy.integrate.qual(Func,a,b)`
- `scipy.integrate.simpson(A)`

## $\frac{df(x)}{dx}=?$
- Finite Difference Method
	-Forward
	-Backward
	-Central
- `np.diff(a,n=1,axis=-1,prepend/append=<no value>)`

## ODE & IVPs
- Analytical solution
- Explicit/Forward Euler Method
- Implicit/Backward Euler Method
- Heun's Method (Modified/Improved Euler)
- Runge-Kutta Method
- `scipy.solve_ivp(func,t_span,y0,method,t_eval)` 

## ODEs & BVPs
- Finite Difference Method + Matrix Form
- Shooting Method
- `scipy.solve_bvp(func,bc,x,y_guess)` 