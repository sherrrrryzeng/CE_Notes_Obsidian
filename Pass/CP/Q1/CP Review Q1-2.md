# Lecture 4
Analytical solution can become inconvenient/unfeasible

**Riemann sum**: the sum of the area under the curve. Considering the limit $\triangle x_i\to 0$, the Riemann sum is equal to the definite integral.  $$S=\sum^{N-1}_{i=0}{f(x_i^*)(\triangle x)_i}$$
## Quadrature rules
Grid and indexing:
![[dbff0d9f89c02843e378705b6052550728b3aec81a8ba2d8e6fb1e072ab703bb.png]]

- **Rectangle Method**: $$I=h\sum_{i=0}^{N-2}{f(x_i)}$$
	The results from numerical solution and analytical solution depend on **the shape of the function**. 
	
	- Error Analysis - Mean Value Theorem (or Lagrange theorem): $$\epsilon(x)=f(x)-f(x_i)=f'(\xi)(x-x_i)$$	![[8e43d2fe16264f037f1c147d609b114881a7def1c9bdd5a413437c81909508ac.png]]
	 The integral error on a single rectangle is bounded by a term proportional to the square of the interval. $$E_i\leq max|f'(\xi)|\frac{h^2}{2}$$
	 The total integral error is bounded by a term that is directly proportional to h: $$E\leq max|f'(\xi)|(b-a)\frac{h}{2}$$
	 Thus, when the interval step decreases, the error decreases proportionally. The error goes to 0 when the interval step h goes to 0 as well.
	 
	 \*Hardly used -> lack of accuracy
	 
- **Newton-Cotes Quadrature**:$$I=\int^b_af(x)dx\approx\sum^{N-1}_{i=0}w_if(x_i)$$
	 where $x_i$ are called **nodes** and $w_i$ **weights**. 
	 Two classes of Newton-Cotes rules:
	- **closed**: when they use the function values at the interval endpoints ($f(x_0=a)$)
	- **open**: when they don't use the function values at the endpoints
	 *The Rectangle methods are neither open nor closed (only use one boundary points and also do not belong to NC rules)*
	
	1. **Midpoint Method**: $$I=h\sum_{i=0}^{N-2}{f(\frac{x_i+x_{i+1}}{2})}$$$$E\leq max|f''(\xi)|(b-a)\frac{h^2}{24}$$	 
	2. **Trapezoid Method**: On a small interval, a function can be approximated by linear interpolant with 2 grid points. (closed method) *(sometimes more stable)* $$I=\sum_{j=0}^{N-2}{\frac{h}{2}(f(x_j)+f(x_{j+1}))}=\frac{h}{2}\left(f(x_0)+\sum_{j=1}^{N-2}{(2f(x_j))+f(x_{N-1}))}\right)$$ $$E\leq max|f^"(\xi)|(b-a)\frac{h^2}{12}$$
	3. **Simpson's 1/3 Method**: With 3 grid points(extremes and halfway point) and over 2 intervals. (closed method) $$I=\frac{h}{6}\left(f(a)+4f(\frac{a+b}{2})+f(b)\right) $$ $$I=\frac{h}{6}\left(\sum_{j=0}^{\frac{N-3}{2}}{f(x_{2·j})+4f(x_{2·j+1})+f(x_{2·j+2})}\right)= \sum_{j=0}^{\frac{N-3}{2}}Simpson_{1/3}([x_{2·j},x_{2·j+2}])$$
	 *If $h=\frac{b-a}{2}$ -> $\frac{h}{3}$* $$E\leq max|f^{(4)}(\xi)|(b-a)\frac{h^4}{180}$$

## Built-in Functions for numerical integration
- `numpy.trapz(A)`
- `scipy.integrate.quad(Func,a,b)` - adaptive quadrature
	return \[integral, error]
- `scipy.integrate.simpson(A)`


## Numerical differentiation
Sometimes numerical differentiation is required, since we only have discrete data points. Differentiation allows to measure the rate of variation of variables in space and time. 
In numerical derivative we take a discrete interval $\triangle x$ instead of the limit.

For Taylor polynomial the approximation error is of the order of the interval to the power of the order of the last expansion term. 

- **Finite Difference Method (FDM)**: Use the differences between function values on a grid to approximate the derivatives of a function. 
	
	First-order differentiation schemes: 
	1. **Forward difference**: $$\frac{df}{dx}|_{x_i}\approx\frac{f(x_{i+1})-f(x_i)}{x_{i+1}-x_i}$$ $$E=\frac{1}{x_{i+1}-x_{i}}\frac{d^2f}{dx^2}|_{x_i}\frac{h^2}{2}\sim ah$$
	2. **Backward difference**: $$\frac{df}{dx}|_{x_i}=\frac{f(x_{i})-f(x_{i-1})}{x_{i}-x_{i-1}}$$ $$E=\frac{1}{x_{i}-x_{i-1}}\frac{d^2f}{dx^2}|_{x_i}\frac{h^2}{2}\sim ah$$
	3. **Central difference**: $$\frac{df}{dx}|_{x_i}=\frac{f(x_{i+1})-f(x_{i-1})}{x_{i+1}-x_{i-1}}$$ $$E=\frac{1}{x_{i+1}-x_{i-1}}\frac{d^3f}{dx^3}|_{x_i}\frac{h^3}{3}\sim ah^2$$
	**Second-order differentiation schemes**: $$\frac{d^2f}{dx^2}|_{x_i}=\frac{f(x_{i+1})-2f(x_i)+f(x_{i-1})}{h^2}$$  $$E=\frac{1}{h^2}\frac{d^4f}{dx^4}|_{x_i}\frac{h^4}{12}\sim ah^2$$

## Built-in Functions for numerical differentiation
- `np.diff(a,n=1,axis=-1,prepend=<no value>,append=<no value>)`
	a: input array
	n: the order of differentiation (default=1)
	axis:The axis along which the difference is taken (default=the last axis)
	prepend/append: array *(可以在差分前后加额外元素，使输出数组长度与原数组相同（否则长度会少 n）*

## Reminder
- `np.linspace(a,b,n)` the n samples include a and b


# Lecture 5

## ODE (Ordinary Differential Equations)
Classification:
- **order**: $\frac{d^3y}{dt^3}=f(y)$ -> 3rd order
- **Non-autonomous**: $\frac{dy}{dt}=f(y,t)$ 
	*when there is t on the right side*
- **Non-linear**: $y\cdot\frac{dy}{dt}=t$

> [!Example] 
> $$\frac{d^2y}{dt^2}=(\frac{dy}{dt})^3-ty$$ is 2nd order, non-autonomous and non-linear. 


ODEs are easiest to solve if they are **linear, 1st order, autonomous**. New variables: $$y_1=\frac{dy}{dt},\,\,y_2=\frac{dy_1}{dt}$$
- **Analytically Solution**: $$\frac{d}{dt}\mathbf{c}=\mathbf{K}\cdot\mathbf{c}$$ $$\mathbf{c}=e^{\mathbf{K}t}\mathbf{c}_0$$ Solving a system of linear ODEs analytically, the BASE is: $$\mathbf{c}(t_{N-1})= e^{K\triangle t}·\mathbf{c}(t_{N-2})=e^{K(N-1)\triangle t}\mathbf{c}(0)=(e^{K\triangle t})^{(N-1)}\mathbf{c}(0)$$
- `eKdt=sp.linalg.expm(K*dt)` 
  Note:
	1. in scipy, **expm** - matrix exponentiation $$e^{K}=Ue^{\lambda}U^{-1}$$ exp: scalar value exponentiation
	2. This solution is only possible if we choose equidistant grid points. 


## Numerical Solution Methods for IVPs
Non-linear ODEs - Initial Value Problem

For every n-th order ODE, we need n initial conditions.


- **Forward/Explicit Euler Method**: Using Euler for ODEs:$$\frac{dy}{dt}=f(t,y)$$ $$y_{i+1}=y_i+\int^{t_{i+1}}_{t_i}f(t,y)dt$$ Rewriting the ODE: 
$$y_{i+1} = y_i+hf(t_i,y_i)$$
  
  \* step size h can be taken to be negative. *(so not always forward) 

- **Backward/Implicit Euler Method**: $$y_{i+1} = y_i+hf(t_{i+1},y_{i+1})$$We can exactly reformulate the problem to be explicit (*not possible for all equations*):$$y_{i+1}=f^*(t_i,y_i,h)$$ We can also formulate this as a root finding problem (Fixed-point iteration, Newton-Raphson method,...)

- **The Heun's Method (Modified/Improved Euler)**: = Trapezoid Method $$I=\frac{h}{2}(f(a)+f(b))$$
- **Runge-Kutta Method**: 
	-Most ==widely used== method in practice
	-==Explicit== method that uses multiple intermediate points to estimate the slope
	-==Greater accuracy== per step than forward/backward Euler
	![[325c594e427ec6b68217966b691e7629c93b4acbff46ce16601bba485302b59b.png]]


Errors in numerical solution of ODEs:
- A **trade-off** between accuracy and solution time
- **Rounding error**: due to finite precision of floating-point arithmetic
- **Truncation error**: due to the approximate nature of the method 
	**Global** truncation error: numerical solution - true solution$$e_i=y_i-y(t_i)$$ **Local** truncation error: numerical solution - true solution of ODE through previous point $(t_{i-1},y_{i-1})$ $$l_i=y_i-u_{i-1}(t_i)$$![[54fbb952610bf72a02ef0dee5299d5f2671e35a72c60024ec70aa8b4e738d5b2.png]]
	
- **Stability**
	Stable solution : errors may diminish
	Unstable solution : errors grow
	
	- Backward/Implicit Euler - **unconditionally stable**
	- Forward/explicit Euler & Runge-Kutta - conditionally stable (depending on step size h and stiffness of the problem)


## Built-in functions for solving IVPs
`scipy.solve_ivp(fun,t_span,y0,method,t_eval)`
- t_span: border of integration interval. 
- method: integration method. There are explicit (e.g., **RK45, RK23**, DOP853) and implicit (e.g., **Radau**, BDF) methods available.
- t_eval: Grid points for which solution is returned. 
- Result: y\[0]