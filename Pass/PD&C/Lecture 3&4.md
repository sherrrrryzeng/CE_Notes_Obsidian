---
date: 2025-09-09
Prof: Dr.ir. Farzad Mousazadeh
aliases:
  - "Chapter 2: Modelling"
---
## From Last Chapter
### Example2: Distillation Column
Step4: Sketch
![[580543eca582b13b1c25e44d4ab9be1a6d74dd246b02f71cff4e6896e65063a5.png]]

Step5: Balance
- **Mass balance:** (M is molar holdup)
$VE_{10}$: $0=\frac{d(M_{10})}{dt}=V_9-L_{10}-D$         (IN)
$VE_{n}$: $0=V_{n-1}+L_{n+1}-V_{n}-L_{n}$
$VE_{5}$: $0=V_4-L_6-V_5-L_5+F$         (FEED)
$VE_{m}$: $0=V_{m-1}+L_{m+1}-V_{m}-L_{m}$
$VE_{1}$: $0=V_2-V_{1}-B$                            (OUT)

- **Component mass balance**: (10DE)
$VE_{10}$: $\frac{d(M_{10}x_{10})}{dt}=M_{10}\frac{dx_{10}}{dt}=V_9y_9-L_{10}x_{10}-Dx_{D}$
$VE_{n}$: $\frac{d(M_{n}x_{n})}{dt}=V_{n-1}y_{n-1}+L_{n+1}x_{n+1}-V_{n}y_{n}-L_{n}x_{n}$
$VE_{5}$: $\frac{d(M_{5}x_{5})}{dt}=V_{4}y_{4}+L_{6}x_{6}-V_{5}y_{5}-L_{5}x_5+FZ_F$
$VE_{m}$: $\frac{d(M_{m}x_{m})}{dt}=V_{m-1}y_{m-1}+L_{m+1}x_{m+1}-V_{m}y_{m}-L_{m}x_{m}$
$VE_{1}$: $\frac{d(M_{5}x_{5})}{dt}=L_{2}x_{2}-V_{1}y_{1}-Bx_B$

- **Assumption: Molar flows are constant**
\*The assumption is valid when the number of distillation elements(DE) is relatively small (10 is okay)
$V=V_9=V_8=...=V_1$
$L=L_{10}=L_9=...=L_6$
$L+F=L_5=L_4=...=L_2$

- **Results**:
$D=V-L$
$B=L+F-V$

- **Constitutive equations**
9AE: $$y_m=\frac{x_m\alpha}{1+(\alpha -1)x_m}$$
Total No of Equations: $10AE+11DE=21Equations$


## Step3: Degree of Freedom
$N_V$: number of Variables
$N_E$: number of Equations
$DOF=N_V-N_E$

$DOF=0$ --- exactly specified
$DOF<0$ --- over specified, there is no solution(something is wrong)
$DOF >0$ --- under specified, control

### Example 2: DC DOF
$N_V=23$ : $x_1,...,x_{10}$   $y_1,...,y_9$    $L,V,B,D$
$N_E=21$ 
Therefore: $DOF=2$
Assume $F\& Z_f$ as disturbance, need 2 more equations to solve all equations

### Different types of variables
Assume:$$\frac{dx_1}{dt}=f_1(x_1,x_2,u_1,u_2,d_1)$$
$x_1,x_2$: state variables, changes over time
$u_1,u_2$: input variables, control points
$d_1$: disturbances, determines upstream

## Step 4: Determine solution
- Analytical, very complicated for very large systems
- Numerical, possible to solve for complicated systems
	Choice of solving method is extremely important while numerically solving an equation.
	(Explicit Euler / Implicit Euler / Modified Euler(Heun))


## Step 5: Analyse Results
### Analytical Solution
Derive $C_A(t)$:
$$\frac{dC_A}{dt}=\frac{\phi_v C_{A,in}}{V}-\frac{\phi_v C_{A}}{V}$$
$$\frac{dC_A}{dt}+\alpha C_A=\beta$$
which$$\alpha=\frac{\phi_v}{V},\beta=-\alpha dt$$
step 1:$$\frac{dC_A}{dt}+\alpha C_A=0$$
$C_A=k_1e^{-\alpha t}, k_1$ is integration constant

step 2: $k_1=function(t)$
$$\frac{dC_A}{dt}=\frac{dk_1}{dt}e^{-\alpha t}+k_1(-\alpha e^{-\alpha t})$$
And $\alpha C_A=\alpha k_1 e^{-\alpha t}$, therefore
$$\frac{dk_1}{dt}e^{-\alpha t}=\beta$$
Integrating:$$k_1=\frac{\beta}{\alpha}e^{\alpha t}+k_2$$
$$C_A=\frac{\beta}{\alpha}+k_2e^{-\alpha t}$$
IC: $C_A (t=0) = C_{A,0}$
**result**: $$C_A=C_{A0}e^{-\frac{\phi v}{V}t}+C_{A,in}(1-e^{-\frac{\phi v}{V}t})$$
### Numerical Solution
$$\frac{df(x)}{dx}=g(x)$$
==Explicit Euler:== $x_{i+1}=x_i+(t_{i+1}-t_i)f(x_i)$
\# the new value $x_{i+1}$ is computed directly from the old value $x_i$, but not stable

==Implicit Euler==: $x_{i+1}=x_i+(t_{i+1}-t_i)f(x_{i+1})$
\# the new value appears on both sides, unconditionally stable but more computationally expensive


## Step 6: Validate Model
- Select key variables
- Compare with experiments
- Modify the model after optimization through parameter estimation
![[4112c6113127e5c9d4e5c288763eac524ea9a16daf52a0cb064b78828d452102.png]]