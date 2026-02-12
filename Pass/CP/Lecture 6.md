---
date: 2025-12-17
Prof: Zoë J.G. Gromotka
aliases:
  - Interpolation and regression
---
# Data loading and saving

## open function
Read raw text data with the `open` function:
```
with open("file.txt","r") as file:
	data = file.read()
print(data)

# Or interatively get the lines of the file as string
	for line in file:
		print(line)
```
- `with...as` : **context manager**. 
	 Ensures that the file is closed properly if an error occurs. 
- `r` flag: means the file is opened in **read mode**. 
- `read` : get the entire content as **string**.
- `line` : iterate over the lines with a for-loop. 

Save raw text data similarly with the `open` function:
```
with open("output.txt","w") as file:
	file.write(data)
```
- `w` flag: open in **write mode**. 
- `write` : write the **string** data in the file. 
	This will ==overwrite== any existing content of the file, not add a new line. 
	If the file does not exist yet, a new file is created. 


## numpy arrays - Numpy
Saving and Loading numpy arrays:
```
# Save the array "data" to an .npy file
np.save("array.npy",data)
# Load the array back from the .npy file
loaded_data=np.load("array.npy")
```
- numpy has its own binary file format `.npy`. 
	This is not an open file format and can only be used by numpy.

## csv tabular data - Pandas
Use the `Pandas` library to load tabular data from csv to numpy:
```
df = pd.read_csv("data.csv")
data = df.to_numpy()
print(data)
```


## matplotlib visualizations
Use `savefig` function to save matplotlib figures:
```
fig.savefig("sine_wave_plot.png",
			format="png",
			dpi=300)
```



# Interpolation

![[18487c2d403b8423910d7036401b13fe9bdce6ca9d2e4765cdb03394381d413d.png]]

## Polynomial Interpolation
Challenge: $n+1$ discrete, precise data points
Task: find a polynomial $f(x)$ of degree $n$ $$f(x)=a_0+a_1x+a_2x^2+...+a_nx^n$$ that **passes through all points**. 

- *n=1: linea*
- *n=2: parabolic*
- *n=3: cubic*


![[4bb1d45af365105beb3221ecbfee0962276f5ee3874cf65d82ae3399fadf4e35.png]]
![[f8dc26ba8f3027294fa853c4060ace1d0176b91798152f4e45a026b16b5d19cd.png]]

### Lagrange interpolating polynomials
We do not want to solve/approximate the solution of a linear system of equations to compute the coefficients of our interpolating polynomial. 
Instead we use Lagrange interpolating polynomials: $$f_n(x)=\sum_{i-0}^n L_i(x)\hat{y}_i$$ with$$L_i(x) = \prod_{\substack{j=0 \\ j \ne i}}^{n} \frac{x - \hat{x}_j}{\hat{x}_i - \hat{x}_j}$$
The Lagrange interpolating polynomial $f_n(x)$ passes through all given data points by creating fractions $L_i(x)$ , which cancel out to 1 at the given datapoints ($\hat{x}_i,\hat{y}_i$) (i.e., at the knots). 
![[bc5bbb1652a1b5f8692a1b2e0e214e28e73f341468fa6c40a783ee5fe409515e.png]]
*Get 0 or 1*


Lagrange interpolation with SciPy: `scipy.interpolate.lagrange(x,y)`
- Purpose: Creates a polynomial that **passes through** a given set of points.
- Key Features: Simple to use for **small** data sets.
	 Large data sets lead to high order polynomials
	 -> Large calculation and large errors
- Returns: the interpolation polynomial as a **callable object**.
```
# Example
x_points = np.array([0,1,2,3])
y_points = np.array([1,2,0,2])
poly = scipy.interpolate.lagrange(x_points, y_points)

# Generate a smooth curve for visualization
x_fine = np.linspace(min(x_points),max(x_points),500)
y_fine = poly(x_fine)
plt.plot(x_fine,y_fine)
```

![[f17ca5745da72faa19ad7ff05bae93354f0bd86d53e15c2d8004ca64f901fde6.png]]

**Runge's phenomenon**: big spikes at the end points


## Piecewise/spline Interpolation
Break the data into smaller intervals and fit **lower-order** polynomials $s_i(x)$ **within each interval**. *(not smooth but continue)*
-> Ensures better control over oscillations compared to single high-degree polynomials.

Splines are piecewise polynomials going:
- through all given data points
- satisfying certain **continuity** conditions 

![[66da9b3c80822dbcfc3891d63851a51d4998a4ecc5529f5ff0093f9561fa727a.png]]
![[79a11c0beb5809ebd80a73b44563ad3c530141fc0d101f305854d0f78642adc4.png]]
Smoothness:
A function of class $C_k$ is a function of smoothness at least k (=has a kth derivative that is continuous in its domain). 
- $C_0$: continuous but not differentiable
- $C_1$: continuous and differentiable, but non-continuous second derivative
- $C_2$: continuous, differentiable, and continuous second derivative

Example:  $x\neq0,\,\,f(x)=x^2\sin(\frac{1}{x})\,\,\,\,\,\,\,\,x=0,\,\,f(x)=0$
	differentiable but has oscillation near $x=0$ -> not $C_1$ 


### Linear Spline
$$s_i(x)=a_ix+b_i$$
This can be explicitly calculated given the two neighbouring data points: $$s_i(x)=\frac{f(\hat{x}_i)-f(\hat{x}_{i-1})}{\hat{x}_{i}-\hat{x}_{i-1}}(x-\hat{x}_{i-1})+f(\hat{x}_{i-1})$$
`scipy.interpolate.interp1d` : 
Returns a callable function for evaluating intermediate values
*default:* kind="linear"
```
linear_interpolator = interp1d(x_points,y_points,kind="linear")
y_fine = linear_interpolator(x_fine)
```


Class `scipy.interpolate.interp1d` is considered **legacy** and will not receive updates
Alternatives:
- Piecewise linear interpolation using `numpy.interp`
- Cubic splines using the `CubicSpline` class of scipy.interp *(commonly used in practice)*
- `scipy.interpolate.make_interp_spline` using Bsplines


Pros:
- Simple and fast
	 easy to compute and implement, especially for real-time application
- Works well for datasets with low curvature
- Avoid Runge's phenomenon![[6b17797cf7a36ff4a585b0adb04e1043d349886d6ba281c1f653c0485a4542a4.png]]

Cons:
- Accuracy limitations
	 poor fit for highly curved data
- Continuous but not differentiable function ($C_0$)
- No physical model equations (->difficult to interpret)


### Quadratic Spline
$$s_i(x)=a_ix^2+b_ix+c_i$$
To construct 𝑛 linear splines for 𝑛 + 1 datapoints, we have 𝟑𝒏 **unknowns** (𝑎, 𝑏, 𝑐 for each spline).
-> We need to specify 3𝑛 conditions.

![[ab7a68a716dac3d77be2b53741bc7f42424f05defc5e54e5effdc398703190f5.png]]
![[934fa95c817538545876f957ed87e34b3c04fc04f541d6dc9eeb3f86fd996f5f.png]]

With SciPy: `quadratic_interpolator=interp1d(x_points,y_points,kind="quadratic")`
Returns a callable function for evaluating intermediate values.

Pros:
- Smoothness (Once continuously differentiable)
- Simplicity 
	 Simpler to construct compared to single higher-order polynomials

Cons:
- Continuous and differentiable but non- continuous second derivative ($C_1$)
- No physical model equations (->difficult to interpret)



### Cubic
$$f_i(x)=a_ix^3+b_ix^2+c_ix+d_i$$
![[12ad19fa3019f18f3f2f2d5d1b5e58c1ce06a6e31a73bc9bbdb1202a772b6d93.png]]
![[f7f8718d42a3cd0672a5ca5f823ab39be3aadc9be85389bd7fa0baee5c7c8184.png]]

With SciPy: `kind="cubic"`

Pros:
- Smooth transitions
	 Provides a continuous curve with smooth derivatives at interval boundaries ($C_2$)
- Accurate
	 Better fit for data with curvature
- Reduces oscillation
	 Handles larger datasets without the issues seen in higher-degree polynomial interpolation.

Cons:
- Requires solving a system of equations to compute coefficients. 
- No physical model equations (->difficult to interpret)


Class `scipy.interpolate.interp1d` is considered **legacy** and will not receive updates. Alternatives:
- Piecewise linear interpolation using `numpy.interp`
- Cubic splines using the `CubicSpline` class of scipy.interp *(commonly used in practice)*
- `scipy.interpolate.make_interp_spline` using Bsplines



### Wrapping up
Pros:
- **Reduces Oscillations**
	 Less prone to the oscillatory behavior seen in high-degree polynomial interpolation.
- **Flexibility**
	 Adapts somehow better to datasets with unevenly spaced data points (compared to simple interpolation).
- Maintains **smooth transitions** between intervals.

Cons:
- May require some **computational effort ***(particularly for cubic splines)*.
- Cannot reliably predict outside the dataset's **bounds**; results are undefined or nonsensical.
- Becomes computationally expensive and less stable as the dataset grows (**suits small datasets**)
- Typically focuses on **one independent variable** and doesn't handle multivariate relationships well.
- No **physical model** equations (→ difficult to interpret)

Applications:
- Frequently used in data tables for thermodynamic properties.
- Used in fluid dynamics for smooth curve generation.


# Regression
Data has noise ->
Regression allows finding a model that best fits the data without the constraint of passing though all datapoints necessarily. 
- Accounts for **data variability and noise** by finding a "best-fit" curve. 
- Interpretation: Can use **physical model equations** that are easier to interpret.


## Linear Regression
We want to find a straight line that best represents the observed data. $$\hat{y}=w_0+w_1x$$
The **residual** at point i: $$e_i=y_i-\hat{y}(x_i)$$
**Residual Sum of Squares (RSS)**: $$RSS=\sum_{i=1}^ne_i^2=\sum_{i=1}^n(y_i-w_0-w_1x_i)^2$$
Our task becomes: finding $(w_0,w_1)$ such that RSS is **minimal**. 


- Change one dimensional input to multi-dimensional input: 
	The input is $$\mathbf{X}_i=(x_{i1},x_{i2},...,x_{iD})$$D is the number of variables inside the equation. 
	For each input $\mathbf{X}_i$ we observe a scalar output $y_i$. 
	For $N$ observations the multi-dimensional output is $\mathbf{y}$. 
	
- We handle data pairs written as matrix $(\mathbf{X},\mathbf{y})$ *( $\mathbf{X}: N\times D$ )*.
	The data pairs are each denoted by $(\mathbf{X}_0,y_0)$, $(\mathbf{X}_1,y_1)$, ..., $(\mathbf{X}_N,y_N)$. 


Now we aim to approximate the output via the linear model $f(\mathbf{X}_i,\mathbf{w})$ such that $$\hat{y}_i=f(\mathbf{X}_i,\mathbf{w})=w_0+\sum_{j=1}^Dx_{ij}w_j$$where
- $\hat{y}_i$ : the prediction of the model
- $\mathbf{w}^T=(w_0,w_1,...,w_D)$ : model parameters (or coefficients)
- $w_0$ : the intercept (also known as bias)


Reformulate to matrix/vector form:
- We add a **constant value** in $\tilde{\mathbf{X}}=(1,x_{i1},x_{i2},...,x_{ij},...,x_{iD})$ such that $$\hat{y}_i=f(\tilde{\mathbf{X}}_i,\mathbf{w})=\sum_{j=0}^Dx_{ij}w_j$$
- Now we can write the linear model in matrix form: $$\hat{\mathbf{y}}=f(\tilde{\mathbf{X}},\mathbf{w})=\tilde{\mathbf{X}}\mathbf{w}$$

We aim to find the parameters $\hat{\mathbf{w}}$ that minimize the RSS: $$RSS(\mathbf{w})=\sum_{n=1}^N(y_i-\hat{y}_i)^2=\sum_{n=1}^N(y_i-\sum_{j=0}^Dx_{ij}w_j)^2$$ In matrix form: $$RSS(\mathbf{w})=(\mathbf{y}-\mathbf{X}\mathbf{w})^T(\mathbf{y}-\mathbf{X}\mathbf{w})$$
**Optimality conditions**:
- Necessary condition for optimality: The RSS’s derivative is zero at the stationary point.
- 𝑅𝑆𝑆(⋅) is a quadratic function w.r.t. the parameters 𝒘. 
	→ RSS is **convex**.
- The stationary point is a global minimum.


Minimizing the RRS:
- **Normal Equation**: ![[d311090e3bc3f4ba5afe809df03c731129b6909aefa6687996d2c3c0ea36b973.png]]

- Solutions:![[316ea0b5c221fbed6a116b1f015e10b5fdaf9e4e9b349c508c06b0b2ef76139a.png]]


- Option A example:![[514e693c39254d6aae6d4351edb6171f6fda007ae3555c088d403188f6c77a6e.png]]


```
# Datas
x_1_measurements = np.array([-1, -0.6, -1, -0.7, -1.3, -0.6])
x_2_measurements = np.array([-1, -1, -0.7, -0.6, -0.6, -1.3])
y_measurements = np.array([-4.6, -4.3, -4.3, -3.9, -4.6, -4.5])

# 1. Linear regression analytical solution (Direct method)
x_feature = np.vstack([x_1_measurements,x_2_measurements]).T
x_ones = np.ones((x_feature.shape[0],1))
X_b = np.column_stack((x_ones,x_feature))
theta = np.linalg.inv(X_b.T@X_b)@(X_b.T)@y_measurements
# or numpy.linalg.solve(X.T@X,X.T@y)

# 2. Indirect method using Jacobi or Gauss Seidel method

# 3. Solve an optimization problem with objective
def objective(w):
	return (y-X@w).T@(y-X@w)
result = scipy.optimize.minimize(objective,x0=np.zeros(len(y)))
```


## Polynomial Regression
Transformation of input variables (features) such that we use a polynomial to fit our data. We only consider one-dimensional inputs now. $$\hat{y}_i=w_0+w_1x_i+w_2x_i^2+...+w_Mx_i^M=\sum_{j=0}^Mw_jx_i^j$$ where
- $M$: the order of the polynomial
- $x_i^j$ : denotes $x_i$ raised to the power of $j$ 

Basic idea: precompute nonlinear "features" and then solve a linear regression problem. 
The model is nonlinear w.r.t the input $\mathbf{X}$ but still linear w.r.t. the parameters $\mathbf{w}$. 

- ![[a64a96520ea36a2996b96033e44c55588d182993750fd3e5ec925193f2b16aab.png]]

- ![[2f55fd767e7a9053fb2a974ec37d6ac90ad965655987a65092b1fd4669d958f5.png]]


The performance is measured by mean square error with true values $t_n$ and predictions $\hat{y}(x_n,\mathbf{w})$ : $$E(\mathbf{w})=\frac{1}{N}\sum_{n=1}^N{[\hat{y}(x_n,\mathbf{w})-t_n]}^2$$ Root mean square (RMS) error: $$E_{RMS}=\sqrt{\frac{1}{N}\sum_{n=1}^N{[\hat{y}(x_n,\mathbf{w})-t_n]}^2}$$
- ![[62317de53e3c6231df0e3f7ca381c5d9ef00bf6251017a4acd440c14b95e61e1.png]]

Properties of Polynomial regression:
- Small 𝑀 values lead to high test errors, indicating **underfitting**.
- 𝑀 = 5 results in the lowest test error, making it an optimal choice.
- Model **overfit**s for 𝑀 ≥ 6, as the test errors increase.

\* For a given model complexity, the over-fitting problem becomes less severe as the size of the data set increases. 

- ![[4e2c73c92614beadd554317cc2cf651554521b1682fc8e8b7ca47719d3068448.png]]

Example:![[bcc5606610b9592204cc06b756aee06dab22dfa90b16ac1146489f1bc9b10d99.png]]

```
# Create matrix X=[1,x,x^2,x^3,...]
X=np.zeros((len(x),degree+1))
for i in range(degree+1):
	X[:,i]=x**i
w=np.linalg.solve((X.T@X),(X.T@y))
y=X@w
```


## Nonlinear regression
Why we use non-linear regression:
- Real-world relationships can rarely accurately be expressed as polynomials.
- Nonlinear equations, in principle, allow to fit complex relationships with fewer parameters than polynomials.
	-> Increasing the degree of the fitting polynomial of a 𝐷-dimensional problem increases the number of parameters in the order of 𝒪(𝐷3). This increases computational complexity and the risk of overfitting.
- Extrapolation: Fitting parameters of known, universally valid physical relations often enables a more reasonable extrapolation outside the given data range than polynomial regression.

Consider a set of observations $(\mathbf{X}_i,y_i)$. We aim to find a nonlinear function $f(\mathbf{X},\mathbf{\beta})$ that is parametrized by a set of parameters $\beta$ : $$y_i=f(\mathbf{X}_i,\beta)+\epsilon =\hat{y}_i+\epsilon$$ $\epsilon$ is the error between the true value $y_i$ and the prediction $\hat{y}_i$. 


With SciPy: `scipy.optimize.curve_fit(func,xdata,ydata)`
Parameters:
- `func`: Callable model function. Takes **independent variable as first input argument** and parameters to fit as separate remaining arguments. 
- `xdata`: np.ndarray. Measured datapoints of independent variable.
- `ydata`: np.ndarray. Dependent data corresponding to measurements *xdata*. 

Returns: `popt,pcov = curve_fit(func,xdata,ydata)`
- `popt`: np.ndarray. Optimal values for parameters.
- `pcov`: 2-D array. Estimated approximate covariance of popt.

Plot: `plt.plot(xdata,func(xdata,*popt))`

Example:![[b097acc9b15212ff09b5c3ef4ac1d8f94ad1cedc54a2bea4f85cab35be8233a0.png]]


Summary:![[7dcfc06f54b8dbfa97c476c4f2383bf55dbe35883ffe8933f1919174c32b21da.png]]

