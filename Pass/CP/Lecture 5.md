---
date: 2025-12-10
Prof: Tanuj Karia
aliases:
  - Numerical Optimization
---
# Optimization Problem

Typically, mathematical optimization problem consists of:
- Objective function
- Equality constraints
- Inequality constraints
- Variable bounds

## Equality constraints $h(x,y)=0$
A set or a vector of $n_h$ equality constraints 
-> typically defines the mathematical model

Determines the degrees of freedom (DOF) of a mathematical optimization model$$DOF = n+k-n_h$$
For all optimization models, degrees of freedom must always be greater than zero.


## Inequality constraints $g(x,y)\leq 0$
Inequality constraints constraint the values that variables can possibly take. Generally, it is a vector of $n_g$ equations. 

**Feasible region** defines the region where all constraints to the optimization problem are satisfied.![[d91d3c00c0ced9b45f194e23ae380ead6a0ff6bc89adc1b2bfc4fbed3fab46e1.png]]


**==Convexity==** of a set: 
	*the set is convex if all points on the line between two points inside the set is inside the set.*
	**Sufficient condition** for convexity: If 
	- equality constraints $h(x)$ are linear
	- inequality constraints $g(x)$ are convex functions 
	-> then the set is convex *(-> a limited case)*

- Strictly convex - all in the set
- Convex - can be on the **border** 
![[0058f2f4b929363ba3b003c13411ef58b50e5e2b461eae382fa6848084266431.png]]


# Linear Programming (LP)

All inequalities reformulated to equalities by introducing **slack variables**: $$g(x)+s=0,\,\,s>=0$$
![[982310d8c2cf48789452a13d39cb5b58969f76d5dc2d711c1d33ca59c3a0f08f.png]]

Example:![[e7b41f12aed0aa31d45821c3d7b9acc34fd24f558149be5a7b82a988e6e126c7.png]]
For LP problems, the feasible region is always a polyhedron.


Fundamental properties of LPs:
	all linear functions are convex
	-> **all LPs are convex optimization problems**

Since LPs are convex:
- Every local optimum for an LP is a **global** optimum.
- If an LP has a non-constant objective function, then an optimal solution of an LP **cannot lie in the interior of the feasible region**. 
- If an LP has a unique optimal solution, then the optimal **must** lie at **an extreme point** of the feasible region. 
- If an LP has multiple optimal solutions, then one of them **must** occur at an extreme point of the feasible region. 


## Solving IPs
--- Conceptual overview of simplex and interior point algorithms

Typically, the procedure to obtain the optimal solution of a linear programming problem involves:
- Determining a feasible points in an iterative fashion such that the objective improves at every iteration
- Terminating the search if no further improvement is possible
This is popularly referred to as the **improving search principle**.

![[44ba8f4606147a681bda664611230000cc0306413f2a114bb320f1b856acfc80.png]]


### Simplex algorithm
Only consider **adjacent extreme points** for improving direction.  Move along the edge that yield largest rate of improvement. Move until another extreme point has been reached. Check if further improvement is possible: if ‘yes’ _continue_; else _terminate_.

Can potentially struggle if there are a high number of extreme points. **High number of extreme points** occur when there are many variables and constraints but few degrees of freedom. 


### Interior point algorithm
Determine an **improving direction**. Move along that direction, but the feasible point in should **strictly remain in the interior of the feasible region**. Check of significant change has been made: if ‘yes’ _continue_; else _terminate_. 

Works well when **DOF is large**. 
For smaller problems simplex algorithm may be more efficient.


### LP in Scipy
`scipy.optimize.linprog(c,A_ub,b_ub,A_eq,b_eq,bounds,method)`

**Objective**: minimize $\mathbf{c}^T\mathbf{x}$ by passing the coefficient vector $\mathbf{c}$. 
**Constraints**: $\mathbf{A}_{ub}$ and $\mathbf{b}_{ub}$ represent coefficients of constraints
- Inequalities $\mathbf{A}_{ub}\,\mathbf{x}\leq \mathbf{b}_{ub}$ 
- Equalities $\mathbf{A}_{eq}\,\mathbf{x}=\mathbf{b}_{eq}$ 
**Bounds**: Define variable ranges with bounds using. 
	Defaults to **non-negative** variables.
	 Use list / list of tuples `bounds=[(0,None),(0,None)]`
**Solvers**: Default is '**highs**', with alternatives for specific needs.
**Result**: Check `result.success`, and retrieve `result.x` (solution) and `result.fun` (optimal value). 

Example:![[9a5b4c34608388f8de3e9ad44dac7d6bc306613bba040b6462c71991060c47e1.png]]


## Formulating LP models
**Objective function**: *maximize the profit by selling the products P1 and P2* -> minimize the negative profit

Mathematically, $$\text{Profit} = C_{P1}P_1+C_{P2}P_2-C_FF$$$P_1,\,P_2,\,F$ represent the amounts of the products and the feed respectively in kg.
We know the _yield_ of products of each feed. 
We know _unit costs_ of the product and the feed: $$C_{P1}=0.6,\,\,C_{P2}=0.3,\,\,F=0.4$$
**Capacity limitations**: 
- Maximum feed of the plant is $10000\,\text{kg/day}$
	-> $F=F_A+F_B+F_C\leq10000\,\text{kg/day}$
- Each unit cannot handle more than $5000\,\text{kg/day}$ 
	-> $F_A,F_B,F_C\leq5000\,\text{kg/day}$
- Maximum demand of $P_1$ and $P_2$ are $4000\,\text{kg/day}$ and $5000\,\text{kg/day}$ 
	-> $P_1\leq 4000\,\text{kg/day},\,\,\,P_2\leq 5000\,\text{kg/day}$ 
- All material flow are non-negative
	-> $F,F_A,F_B,F_C,P_1,P_2\geq 0$ 

**LP Formulation**: ![[07d8bdb108abe3e10562fb5569dccd316ceafc7eb10f040fe114b3d6ff2fd353.png]]


## Analyzing solutions
![[f29ddce582c1ef0b6d923c30982b4c21efe7a4f57148397ac9d6ed618aceb686.png]]
1. First part of the log shows whether the solver terminated successfully or not. **Always** check first if the solver terminated successfully or not before analyzing the solution reported. `success: True`
2. `fun` report the value of the objective function of your problem. 
3. `x` is a vector of the decision variables in your problem and SciPy reports their values in the order you defined. 
4. `nit` represents the **number of iterations** the solver required to optimize the problem. 
5. `residual` refers to the difference between the value at the optimal solution and the value of the respective **bound/constraints**.
6. `marginals` refers to the **dual cost or shadow price** and is only non-zero if the value is at the bound/constraint is active -> residual = 0 

- **Equality** constraints always have a zero residual
- **Inequality** constraint only have a zero residual if the constraint is **active**
- Marginal is ==only non-zero if the residual is zero== -> constraint is active

Example:›![[a8803affeb6cdd7d9dc4897f7d4d0c7ab486f1ab1ebe57cbae2d575e3a1032b8.png]]


# Mixed-integer Linear Programming (MILP)
Building on from linear programming, a mixed-integer linear program also comprises a set of integer (or discrete) variables
![[22ba10a36d8a43bc384c323bd67c9fe3e4816d5174e42950001d32c025157c98.png]]
The feasible region is **discontinuous** -> ==**non-convex==**

Discrete variables:
- **Binary variables**
	 0 or 1 (what we focus here)
	 = True or False
- Integer variables
	 0,1,2,3,4,5,...
	 How many...?


## Modelling the logical proposition
### OR
We can model common logical propositions using binary variables. Assuming $J$ is a set representing multiple options, generally. 
- Selecting at least one component (logically equivalent to **inclusive OR** -> $\sum y_j\geq1$)
- Selecting exactly one component (logically equivalent to **exclusive OR** -> $\sum y_j=1$)
- Selecting at most one component ($\sum y_j\leq1$)

*Example: Choose A or B -> $y_A+y_B \leq 1$ (linear)*

**Truth table**: ![[a2d930e49f148ff4cf4e1040214e0bce8fdc099ee7e61bf0fc77c4fcfd850ac2.png]]

### AND & NOT
*Example: Choose A and B -> $y_A\geq1,\,\,y_B \geq 1$ 

*Example: If $y_A$ represents that A is selected, $1-y_A$ represents B is not selected.* 


## Activating specific constraints only if needed
This is particularly useful when values of continuous variables are linked to discrete variables. 

**Big-M formulation**: ![[d12b5d54d3c3a9ccbbbe17477c085c05df56060908d750c275fb878a8e60f661.png]]

Choosing appropriate big-M values: 
Big-M values should be **==sufficiently high==**
- If big-M value is too low, feasible solution becomes **infeasible**
- If big-M value is too large, solve times become **slower**
![[af17511ecdfb94d418fbcb55f0d9450ae23832be0b8dfc58665cd2622f069955.png]]


## Formulating MILP
Feed flowrate should be 0 if a reactor is not chosen. 
Over all three reactors this is expressed as $$x_1+x_2+x_3\leq15$$All material flows are non-negative $$x_1,x_2,x_3\geq0$$
We use the Big-M approach to model this: $$x_i-15y_i\leq0$$
Here M is 15 -> maximum feed availability is 15. 
- When $y_i=0$ we get $x_i\leq0$. Recall constraint we have $x_i=0$. 
- When $y_i=1$ we get $x_i\leq15$. 

Solving the MILP in SciPy:![[0a5a709a3378e2c9d284c1126093c9d4d20b7118e54b326e1c5c6135d4d344f5.png]]

MILP in SciPy:
```
result = scipy.optimize.milp(c,constraints,bounds,integrality)
constraints=scipy.optimize.LinearConstraint(A,lb,ub)
bounds=scipy.optimize.Bounds(bounds)
```
**constraints**:Define all the inequalities into matrix A and upper bound vector
	Example: `A=np.array([1,1,-5]),b=np.array([0])` ->`x+y-5z<=0`
**bounds**: Define the lower and upper bounds into two lists
	Example: `UB=[0,0,0], LB=[1,1,np.inf]` -> `(0,1)(0,1)(0,inf)`
**integrality**: 0-continuous, 1-integer, 2-Semi-continuous, 3-Semi-integer