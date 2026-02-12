---
date: 2025-09-24
Prof: Ferdinand Grozema
aliases:
  - Numerical integration and differentiation
---
# Numerical Integration - Quadrature rules
Analytical solution can become inconvenient/unfeasible

Riemann sum:$$S=\sum^{N-1}_{i=0}{f(x_i^*)(\triangle x)_i}$$
Grid and indexing:
![[dbff0d9f89c02843e378705b6052550728b3aec81a8ba2d8e6fb1e072ab703bb.png]]


## Rectangle method
$$I=h\sum_{i=0}^{N-2}{f(x_i)}$$

The error of the rectangle method:
- The results from numerical solution and analytical solution depend on **the shape of the function**. 

### Error Analysis
- Mean value theorem / Lagrange theorem:
	-firstly estimate the integral error (Ei) for one discretization step.  
	-In the rectangle method you consider the function as constant through the interval.  
	-Thus, the method does not consider the variation of the function along the interval  
	-We measure such deviation 𝜖(𝑥) using the mean value theorem:$$f'(\epsilon)=\frac{f(x)-f(x_i)}{x-x_i}$$
	![[52fc727bc06663c35478dbc8019867e5282c54e0e25cccbd1ca8a4bb5a93ea82.png]]	
	The integral error on a single rectangle is bounded by a term proportional to the square of the interval: $$E\leq max|f'(\epsilon)|(b-a)\frac{h}{2}$$
\*Hardly used -> lack of accuracy


## Newton-Cotes rules
### Midpoint method
$$I=h\sum_{i=0}^{N-2}{\frac{f(x_i+x_{i+1})}{2}}$$
Error analysis:
$$E\leq max|f'(\epsilon)|(b-a)\frac{h^2}{24}$$

### Trapezoid Rule
On a small interval, a function can be approximated by linear interpolant.
$$I=\frac{h}{2}(f(a)+f(b))$$
Both corners of the intervals(close method):
$$I=\sum_{j=0}^{N-2}{\frac{h}{2}(f(x_j)+f(x_{j+1}))}=\frac{h}{2}\left(f(x_0)+\sum_{j=1}^{N-2}{(2f(x_j))+f(x_{N-1}))}\right)$$
Error analysis:
$$E\leq max|f^"(\epsilon)|(b-a)\frac{h^2}{12}$$

### Simpson's 1/3 Rule
  The integral of the function can be approximated by the integral of the **interpolant**: $$I=\frac{h}{6}\left(f(a)+4f(\frac{a+b}{2})+f(b)\right) $$
Here we consider 2 intervals and 3 discretization points for each sub-integration. After some computation you can achieve the final formula (closed method): $$I=\frac{h}{3}\left(\sum_{j=0}^{\frac{N-3}{2}}{f(x_{2·j})+4f(x_{2·j+1})+f(x_{2·j+2})}\right)= \sum_{j=0}^{\frac{N-3}{2}}Simpson_{1/3}([x_{2·j},x_{2·j+2}])$$
Error analysis:
$$E\leq max|f^{(4)}(\epsilon)|(b-a)\frac{h^4}{180}$$
**\*Most accurate method**
Consider the amount of calculation


## Built-in Python Functions
Numpy:
- `numpy.trapz` → Performs numerical integration using the **trapezoidal rule**

SciPy:
- `scipy.integrate.quad` → Computes the definite integral of a function using adaptive quadrature.  
	*The methods used for quad vary according to the slope
- `scipy.integrate.simpson` → Performs numerical integration using **Simpson's rule**.  


# Numerical Differentiation
## Taylor Polynomial
$$f(x)=f(x_i)+\frac{df}{dx}|_{x_i}(x-x_i)+...+\frac{d^Nf}{dx^N}(x-x_i)^N+o(\triangle x^N)$$
The approximation error: $o(\triangle x^N)$


### Finite Difference Method (FDM)
First-order differentiation schemes:
- Forward difference$$\frac{df}{dx}|_{x_i}=\frac{f(x_{i+1})-f(x_i)}{x_{i+1}-x_i}$$
$$E=\frac{1}{x_{i+1}-x_{i}}\frac{d^2f}{dx^2}|_{x_i}\frac{h^2}{2}\sim ah$$

- Backward difference$$\frac{df}{dx}|_{x_i}=\frac{f(x_{i})-f(x_{i-1})}{x_{i}-x_{i-1}}$$
$$E=\frac{1}{x_{i}-x_{i-1}}\frac{d^2f}{dx^2}|_{x_i}\frac{h^2}{2}\sim ah$$

- Central difference$$\frac{df}{dx}|_{x_i}=\frac{f(x_{i+1})-f(x_{i-1})}{x_{i+1}-x_{i-1}}$$
$$E=\frac{1}{x_{i+1}-x_{i-1}}\frac{d^3f}{dx^3}|_{x_i}\frac{h^3}{3}\sim ah^2$$


Second-order differentiation schemes:
$$f(x_{i+1})+f(x_{i-1})=f(x_i)+\frac{df}{dx}|_{x_i}(x_{i+1}-x_i)+\frac{df}{dx}|_{x_i}(x_{i-1}-x_i)$$
$$+\frac{d^2f}{dx^2}|_{x_i}\frac{(x_{i+1}-x_i)^2}{2}+\frac{d^2f}{dx^2}|_{x_i}\frac{(x_{i-1}-x_i)^2}{2}$$
$$=2f(x_i)+2\frac{d^2f}{dx^2}|_{x_i}\frac{h^2}{2}$$
Rearranging: 
$$\frac{d^2f}{dx^2}|_{x_i}=\frac{f(x_{i+1})-2f(x_i)+f(x_{i-1})}{h^2}$$


## Built-in Python functions
`np.diff`
- Computes the difference between consecutive elements of an array  
- Given two array: f (dependent variable) and x (independent variable) you can, for instance, obtain the first order forward difference scheme as:  *df_dt = np.diff(f) / np.diff(x)*  