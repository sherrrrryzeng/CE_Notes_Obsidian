---
date: 2025-10-01
Prof: Zoë J.G. Gromotka
aliases:
  - ODEs and IVPs
---
# ODE (Ordinary differential equations in reaction engineering)

$$\frac{dC_A}{dt}=-kC_A,\,\,C_B=1-C_A$$

## Classification of ODEs
Definition: 
- **orden** n: 
	Implicit form: $$g\left(t,y,\frac{dy}{dt},...,\frac{d^ny}{dt^n}\right)=0$$
	Explicit form: *(not always possible)* $$\frac{d^ny}{dt^n}=f\left(t,y,\frac{dy}{dt},...,\frac{d^{n-1}}{dt^{n-1}}\right)$$
	where
	- $t$: independent variable
	- $y(t)$: dependent variable
	
- When is an ODE **linear**?
	If it is linear in the dependent variable y(t) and its derivatives. 
	(Only to the first power and are never multiplied together)
	
- When is an ODE **autonomous**?
	If it does not include the independent variable t.

ODEs are easies to solve if they are **linear, 1st order, autonomous** ODEs.
Example: Original 3rd order ODE 
-> New variables: $$y_1=\frac{dy}{dt},\,\,y_2=\frac{dy_1}{dt}$$

## System of ODEs
Take the reaction: $$A<=>^{k_1}_{k_2}B<=>^{k_3}_{k_4}C$$
Corresponding ODEs giving the evolution of the concentrations of A, B, C:
$$\begin{align}
\frac{dc_A}{dt} &= -k_1 c_A + k_2 c_B, \\[6pt]
\frac{dc_B}{dt} &= k_1 c_A - (k_2 + k_3)c_B + k_4 c_C, \\[6pt]
\frac{dc_C}{dt} &= k_3 c_B - k_4 c_C.
\end{align}$$

Collect into matrix form: $$
\mathbf{c} =
\begin{pmatrix}
c_A \\[6pt]
c_B \\[6pt]
c_C
\end{pmatrix},
\qquad
\mathbf{K} =
\begin{pmatrix}
-\,k_1 & k_2 & 0 \\[6pt]
k_1 & -(k_2 + k_3) & k_4 \\[6pt]
0 & k_3 & -\,k_4
\end{pmatrix}
$$
$$\frac{d}{dt}\mathbf{c}=\mathbf{K}\cdot\mathbf{c}$$

$\mathbf{c}$ contains the exponential of a matrix: $\mathbf{c}=e^{\mathbf{K}t}\mathbf{c}_0$

How to solve $e^{\mathbf{K}t}\mathbf{c}_0$:
	If K is diagonalizable, it can be expressed as $$
K = U \, \Lambda \, U^{-1}, \quad 
\Lambda = \operatorname{diag}(\lambda_1, \ldots, \lambda_n)
$$
	So it can be written as $$
e^{K t} = U \, e^{\Lambda t} \, U^{-1}
$$
	Time discretization $$T = [\,0, \Delta t, 2\Delta t, \dots, (N-1)\Delta t\,]$$
	Solution $$\mathbf{c}_{t_{N-1}} = \mathbf{c}(t_{N-1}) = e^{K t_{N-1}} \, \mathbf{c}(0) = e^{K (N-1)\Delta t} \, \mathbf{c}(0)=(e^{{K \Delta t})^{(N-1)}} \, \mathbf{c}(0)$$

Solving a system of linear ODEs analytically:
BASE: $c(t_{N-1})= e^{K\triangle t}·c(t_{N-2})$
```
# Calculate exponential of matrix
eKdt = sp.linalg.expm(K * dt)
...
# use concentration from previous timestep to calculate new concentration
for i in range(1,len(t)):
c[:,i] = np.dot(eKdt,c[:,i-1])
```



# Numerical Solution Methods for Initial Value Problems(IVPs)

## Non-Linear ODEs
General form:$\frac{dy}{dt}=f(t,y)$
Initial condition: $y(t_0)=y_0$
\*For every n-th order ODE, we need n initial conditions. 

- Numerical solution through discretization:$$
t = [t_0, t_1, \dots, t_i, \dots, t_{N-1}] \;\; \Rightarrow \;\;
y = [\,y_0, y_1, \dots, y_i, \dots, y_{N-1}\,]$$
- Rewriting the ODE: $$\frac{dt}{dt}=f(t,y)$$
- Find the solution by integrating from an initial value $y_i$ to the subsequent value $y_{i+1}$ : $$\int_{t_i}^{t_{i+1}}\frac{dy}{dt}dt=\int_{t_i}^{t_{i+1}}f(t,y)dt$$


### Forward Euler / Explicit Euler
Rewriting the ODE: 
$$y_{i+1}\approx y_i+hf(t_i,y_i)$$

\* step size h can be taken to be negative. *(so not always forward)*

**Grid points vs. Evaluation points:**
![[8c9c121d4c05f6db2e487656d3549ef16f67f8cfaf36b633108f0f056e4e98f3.png]]


### Backward Euler / Implicit Euler
Only difference:
$$y_{i+1}\approx y_i+hf(t_{i+1},y_{i+1})$$

We can exactly reformulate the problem to be explicit *(not possible for all equations)* : $$y_{i+1}=f^*(t_i,y_i,h)$$
**Root-finding problem** for the backward Euler method: 
At every integration step, we need to solve the root finding problem - 
```
def backward_euler(func: Callable, c0: np.ndarray, t: np.ndarray) -> np.ndarray:
...
for i in range(len(t)-1):
	c_guess=c[:,i]
	euler = lambda c_next: c[:,i] +dt*func(t[i+1],c_next)-c_next
	  # lambda - define function euler with input c_next
	c[:i+1]=scipy.optimize.fsolve(euler,c_guess)
	  # Root-finding step (find the c_next that makes euler=0)
return c
```


### The Heun's Method / Modified/Improved Euler Method
=Trapezoid method
![[Pass/CP/Q1/Lecture 4#Trapezoid Rule]]

### Runge-Kutta Method (Most common)
-Greater accuracy per step than forward/backward Euler

$$k_1=f(t_n,y_n)$$
$$k_2=f(t_n+\frac{h}{2},y_n+\frac{h}{2}k_1)$$
$$k_3=f(t_n+\frac{h}{2},y_n+\frac{h}{2}k_2)$$
$$k_4=f(t_n+h,y_n+hk_3)$$
$$y_{n+1}=y_n+\frac{h}{6}(k_1+2k_2+2k_3+k_4)$$


## Errors in numerical solution of ODEs and stability

### Errors in numerical solution of ODEs
- Influence of the time step size
---A trade-off between accuracy and solution time


- Truncation Errors
	Global truncation error: $e_i=y_i-y(t_i)$
	Local truncation error: $l_i=y_i-u_{i-1}(t_i)$
	where:
	 $y_i$ is numerical solution y at point i
	 $y(t_i)$ is true solution at point i
	 $u_{i-1}(t_i)$ is true solution of ODE through previous point $(t_{i-1},y_{i-1})$

![[a94d12e8190c9fbe0d2c887e530608c8edaae7f993075868a83566fd24016b48.png]]


### Stability Analysis
- Backward Euler - unconditionally stable
- Forward Euler / Runge-Kutta - conditionally stable
	-depending on step size h and stiffness of the problem

Stiff ODEs:
	They often involve competing physical phenomena with widely varying time and/or spartial scales. 
	In general, an ODE is stiff if the eigenvalues of the Jacobian differ greatly in magnitude. 


## ODE solver in scipy
`results = scipy.integrate.solve_ivp(fun=dC, t_span=(t[0],t[-1]), y0=c0, t_eval=t, method="RK45")`
	a built-in IVP solver from scipy

- Methods: 
	explicit - 'RK45' ; implicit - 'Radau' *Choose wisely!*

- t_eval: 
	grid points for which solution is returned. Solver uses dynamic grid points to calculate solution. 
