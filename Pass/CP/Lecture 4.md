---
date: 2025-12-03
Prof: Tanuj Karia
aliases:
  - Numerical Optimization
---
# Basics of mathematical optimization
“Mathematical optimization or mathematical programming is the selection of a best element, with regard to some criteria, from some set of available alternatives.”

## Objective function
Objective function quantifies the performance of different decisions (→ Criteria for judging what is best)
*e.g.,Maximize profit + Minimize CO2 emissions*

It is possible to specify multiple objective functions 
→ “Multi-objective optimization”

Equivalence of formulations: $$\min_x({f(x)})=\max_x(-f(x))$$**Convention**: We formulate everything as minimization problems


## Variables & DoF
**Variables** 𝒙 can be varied and acts as arguments to the objective function 𝑓(𝒙)

If no constraints exist, the number of variables corresponds to the **degree of freedom** (DoF)

𝒙 is usually a set of 𝑁 continuous variables that can have any value within a given compact domain \[𝒙𝐿, 𝒙𝑈] (bounds) , over a subset of ℝ𝑁

Variables can also be a set of discrete choices



# Conditions for optimality
## Necessary condition for optimality
### Definitions
- **Local / Global minimum**
![[6d447cb357a520e818dc96ee1b537d38664330e4606421c99b9aabd559b81537.png]]
![[44be5bbb362e861019ba9561611b1e2f1a6bdbaa879474c6fe6343d2dfdb85cb.png]]

- **Weak / strict minima**
![[044ffb12323502b71228ddf22eb58312a79dddf6fbbc0dd545579f1b6df608f3.png]]
![[377855e035026e99c4e2d95ea7ad4b064b450983e5d0ceeb797d2b3de0d32336.png]]

- **Critical point (stationary point)**
![[233c4ca1cc2668cd8001b4f8180458469881f84b573e787f329249f28a2336d4.png]]

- **Lipschitz continuous**
![[00e16f73a67d8fe5acfa0e76f569547c3e01956bedc113c4a610c31d1fc20230.png]]


## Convexity of a function
![[75542c197a145b1feee6854e9aef7dc2ee1fa1d5f852efe5eff4c94bdf9c4132.png]]

### Importance of convexity for optimization
   Convexity helps us to determine whether a function will have a local minima or not (or determine global minimum):
-  If a function is convex → the critical points are weak global minimum
- If a function is **strictly** convex → the critical point is a unique, **strong** global minimum
- If a function is non-convex → it may have critical points some of which are not global minimum
![[f9a94c23f86bb0c95a67d0772934c76db8a50b0a84c305c321c4d5ab866adc66.png]]


### Testing for convexity
Convexity depends on the curvature of the function 
→ **==second-order derivative==** information required

Conditions for convexity - univariate function:
- 𝑓(𝑥) is convex if 𝑓′′ 𝑥 ≥ 0 ∀ 𝑥 ∈ \[𝑥𝐿, 𝑥𝑈]
- 𝑓(𝑥) is **strictly** convex if 𝑓′′ 𝑥 > 0 ∀ 𝑥 ∈ \[𝑥𝐿, 𝑥𝑈]

For multivariate functions:
- 𝑓(𝒙) is convex if its Hessian matrix 𝑯(𝒙) is positive semi-definite ∀ 𝒙 ∈ \[𝒙𝐿, 𝒙𝑈]
- 𝑓(𝒙) is **strictly** convex if its Hessian matrix 𝑯(𝒙) is **positive definite** ∀ 𝒙 ∈ \[𝒙𝐿, 𝒙𝑈]

**Definition**: A matrix is…
- positive semi-definite if and only all of its eigenvalues are non-negative
- positive definite if and only **all of its ==eigenvalues== are positive**
`eigenvalue,eigenvector = scipy.linalg.eig(A)`


## Sufficient condition for optimality
![[362f2df0652fdbfde847996167fd8c0ac41271428cd3316247b86cc44cfb129f.png]]

Condition for local optimality for **multivariate** function:![[a53e3330f63c06e0182fadc3968dd5e661553dd21600a34ff1fcfc7dd49277c0.png]]
Positive definite Hessian matrix -> SOSC 
+FONC -> Strong local minimum


# Unconstrained optimization
## Gradient descent algorithm pseudo-code
Descent direction algorithms
- Start at an initial point
- Determine a descent direction based on some local information
- Make a step in this direction
- Repeat this procedure to converge to a local minimum


### Descent direction algorithm: pseudo-code
Algorithm:
1. Initialize $𝒙^{(1)}$ and 𝑘 = 1
2. Determine the descent direction 𝒅(𝑘) using information such as the gradient or hessian.
3. Determine the step size 𝛼(𝑘) (called _learning rate_ in machine learning)
4. Set 𝒙(𝑘+1) ← 𝒙(𝑘) + 𝛼(𝑘)𝒅(𝑘) and 𝑘 ← 𝑘 + 1
5. Terminate if 𝑓(𝒙(𝑘+1)) − 𝑓 𝒙 𝑘 < 𝜖 or if 𝑘 > 𝑘𝑚𝑎𝑥

Vector 𝒅(𝑘) is a **descent direction** at 𝒙(𝑘) if $∇(𝑓(𝒙^{(𝑘)})^𝑇𝒅 < 0$

![[f55094ab7ac9f0f28773ceac964b635bb0002da8885fe7353afdacebaf3e485d.png]]


### Determining the descent direction and step-size
**Open questions:**
- Determining _descent_ direction 𝒅(𝑘)
- Determining step size 𝛼(𝑘)


![[a9439eafe3dfa21fefda9187aceee708721c5682f9e1f40572eeab107ff019b4.png]]
![[8957cf469b1157f35a1a40e18b66f81f23b8f066eb68d10cb0a0686f29a9a577.png]]


## First-order search methods
Use first derivative information to update the descent direction to determine the local minimum
- Defining  $$\textbf{g}^{(k)}=\nabla f(\mathbf{x}^{(k)})$$
- For **steepest descent method**: $$\textbf{d}^{(k)}=-\frac{\mathbf{g}^{(k)}}{||\mathbf{g}^{(k)}||}$$*(normalize the direction of steepest descent)*


If the functional behavior exhibits **narrow valleys**, gradient descent performs **poorly**.

*Example*: Slow convergence of steepest descent method for Rosenbrock function

More advanced methods incorporate faster gradient calculations such as Momentum, Nesterov, Adam, etc. and are also used to train deep neural networks



## Second-order search methods
- First-order methods lack information about the **curvature** of the function → cannot determine how far a step to take.
	If the functional behaviour exhibits **narrow valleys**, gradient descent performs **poorly**.

- Second-order information can help address this issue and accordingly determine the descent direction

Notion of step size can be eliminated using second-order information: 𝒙(𝑘+1) ← 𝒙(𝑘) + 𝒅(𝑘)


### Univariate case
Consider second-order Taylor series approximation of univariate function 𝑓(𝑥) at point 𝑥(𝑘) $$f(x)\approx f(x^{(k)})+(x-x^{(k)})f'(x^{(k)})+\frac{1}{2}(x-x^{(k)})^2f''(x^{(k)})$$
We wish to minimize f(x), on applying First-order necessary condition(FONC): $$f'(x)=0\,\to\,f'(x^{(k)})+(x-x^{(k)})f''(x^{(k)})=0$$ $$x^{(k+1)}=x^{(k)}-\frac{f'(x^{(k)})}{f''(x^{(k)})}$$

### Multivariate case
Consider second-order Taylor series approximation of multivariate function 𝑓(𝒙) at point 𝒙(𝑘) $$f(\mathbf{x})\approx f(\mathbf{x}^{(k)})+(\mathbf{g}^{(k)})^T(\mathbf{x}-\mathbf{x}^{(k)})+\frac{1}{2}(\mathbf{x}-\mathbf{x}^{(k)})^T\mathbf{H}^{(k)}(\mathbf{x}-\mathbf{x}^{(k)})$$
We wish to minimize 𝑓(𝑥), on applying First-order necessary condition (FONC): $$\nabla f(x)=0\,\to\,\mathbf{g}^{(k)}+\mathbf{H}^{(k)}(\mathbf{x}-\mathbf{x}^{(k)})=0$$$$\mathbf{x}^{(k+1)}=\mathbf{x}^{(k)}-\mathbf{H}^{(k)^{-1}}\mathbf{g}^{(k)}$$
 If the function is quadratic and its Hessian is positive definite, the update step in Newton method converges to global minimum in one step
Newton methods exhibit _quadratic_ convergence behavior. 


### Limitations of Newton’s method
- Determining the Hessian matrix is computationally expensive
- Inverting matrices further adds to the computational burden 
- Newton method **does not** work well when:
	- Second derivative is zero → first derivative is a linear hyperplane
	- Second derivative is very close to zero → next iterate will lie very far from the current point
	- The descent direction is reliable when the difference between the true function and the quadratic approximation is not too large
	- When 𝑯(𝑘) is not positive definite, the descent direction may be ill-defined or may not satisfy the condition for descent
- Quasi-Newton methods aim to address some of these limitations (implementations available in popular packages)


## Unconstrained optimization using Scipy
`scipy.optimize.minimize(objective,x0)`
Ideal for solving linear, nonlinear, and constrained optimization problems. Easy-to-use interface for various optimization tasks.
```
# objective is a defined function
def objective(x):
	return (x-3)**2
result = scipy.optimize.minimize(objective,x0=0)
print(result.x)
```