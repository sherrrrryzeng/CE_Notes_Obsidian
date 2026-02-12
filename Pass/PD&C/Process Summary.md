# Module 2 : Modelling

- **Mass Balance:$$\frac{d(\rho V)}{dt}=\rho\phi_{in}-\rho\phi_{out}$$Component Mass Balance(A):**$$\frac{d(VC_A)}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A,out}+rate*V$$
- **Energy:**$$\frac{d(\rho VC_pT)}{dt}=\phi_{in}\rho C_pT-\phi_{out}\rho C_pT_{out}+Q_{q,loss}$$
### Example of Modelling 1 CSTR
1. **Define Objectives**

2. **Prepare Information**
Assumptions:
- ideally mixed
- constant density
- first order reaction
- negligible reaction heat
- constant temperature

For **constant liquid level**:
3. **Formulate Model**
Balance Equations:
- Total Mass Balance: $$\frac{d(\rho V)}{dt}=\rho(\phi_{in}-\phi_{out})=0$$ $$\phi_{in}=\phi_{out}=\phi$$
- Component Mass Balance: $$\frac{d(VC_A)}{dt}=V\frac{dC_A}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_A-VkC_A$$ $$\frac{dC_A}{dt}=\frac{\phi}{V}C_{A,in}-\frac{\phi}{V}C_{A}-kC_A$$
For **not constant liquid level**:
Balance Equations:
- Total Mass Balance: $$\frac{dV}{dt}=\phi_{in}-\phi_{out}$$
- Component mass balance: $$C_A\frac{dV}{dt}+V\frac{dC_A}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A}-VkC_A$$ $$C_A(\phi_{in}-\phi_{out})+V\frac{dC_A}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A}-VkC_A$$ $$V\frac{dC_A}{dt}=\phi_{in}(C_{A,in}-C_A)-VkC_A$$
### Example of Modelling 2 Distillation Column
1. Model Purpose
2. Prepare Information (System, variables)
Assumptions:
- vapor phase can be neglected
- trays are very well mixed
- outgoing flows are in Thermodynamic equilibrium ($\alpha$ is constant)
- liquid molar hold-up is constant
- liquid and vapor molar flows are constant

## Degree of Freedom
- Mathematical Degree of Freedom:
	$N_V$: number of Variables
	$N_E$: number of Equations
	$DOF=N_V-N_E$
	
	$DOF=0$ --- exactly specified
	$DOF<0$ --- over specified, no solution(something is wrong)
	$DOF >0$ --- under specified, control

## Different types of Variables
- **State variables**: changes with time
- **Input variables**: control points
- **Disturbances**: determined by upstream
- **Parameters**: constant for specific cases


4. **Determine Solution**
- Analytical, very complicated for very large systems
- Numerical, possible to solve for complicated systems


5. **Analyze Results**
Result correct?
Interpret the results


6. **Validate Model**
Validation is the step where experiments can be carried out to check if your model is (to an acceptable degree) accurate.


# Module 3 : Analysis
\[ Step 5 ]

Type of analysis:
- Steady-state non-linear
- Dynamic linear

Process Properties:
- Non-linear
- Large variables (e.g. $10^3-10^4$ variables in DC with 100 stages)
- Stiff(differential equations), large time variability
- Poor scaling, variables have wide range of values
- Uncertainty
- Sparse, high number of equations & low number of variables in equation

Goal of analysis:
- **==Operating window==** : the **range of process conditions** (such as temperature, pressure, flow rate, composition, etc.) within which the process can **operate safely, stably, and efficiently** — while meeting product quality and safety constraints.

## Steady-state Analysis
- **Find Steady-States & Allow the process Handle Disturbance**![[830c6893d2f5e62a4cceda91b4935a26b1bb9a3ee4e4bac2130092e018de4b6d.png]]
STABLE steady-state points: the first and third point. 
	Reason: *We want stable steady-states where if you perturb/disturb a process slightly, then the process comes back to its state before the perturbation.*
ONLY the higher (third steady state) is the operating point <- the first one is **below ignition**.


## Linearization
Sources of **non-linearity** in a process:
- Cross-terms: $\phi_{in}(t)\cdot C_{A,in}(t)$
- Saturation: $k_0e^{-E_a/RT}$
- Thermodynamic property: $lnP_L^0=\frac{b}{c+T}+a$
- Reaction kinetics: $r=k\,C_A^m\,C_B^n$

Linearization steps:
1. Find steady-state operating points
2. Deviation variable: $\tilde{x}=x-x_0$
3. Linearize - Laplace Transform (Easier way to solve) (Keep all the properties of original set of equations) (Linear)$$F(s) = \mathcal{L}\{f(t)\}= \int_{0}^{\infty} f(t)\, e^{-st}\, dt$$ **==First-order differential==**: $$\mathcal{L}[f'(t)]=sF(s)-f(0)$$\*For steady state $f(0)=0$.
   
   **==Delay / dead time==** $\theta$: $$\mathcal{L}[f(t-\theta)]=e^{-\theta s}F(s)$$ \*from Taylor approximation $$e^{-Ls}\approx 1-Ls$$ \*from Padé approximation$$e_{-Ls}\approx\frac{1-\frac{L}{2}s}{1+\frac{L}{2}s}$$ **==Final Value Theorem==**: $$\lim\limits_{t\to\infty}f(t)=\lim\limits_{s\to 0}[sF(s)]$$ Initial Value Theorem:$$\lim\limits_{t\to 0}f(t)=\lim\limits_{s\to\infty}[sF(s)]$$
 
## Transfer Function
$$P(s)=\frac{Y(s)}{U(s)}=\frac{\mathcal{L}(Output)}{\mathcal{L}(Input)}=\frac{\text{numerator}}{\text{denominator}}$$
Properties:
- **Order**:
	Degree of "s" in the denominator
	= the highest order of the original differential equation
	
- **==Poles==**:
	Roots of the denominator (polynomial)
	= solve for s by putting denominator=0
	
- ==**Zeros==**:
	Roots of the numerator (polynomial)
	= solve for s by putting numerator=0
	
- **Gain**:
	How much the output changes by change of input = $\frac{\triangle Y}{\triangle U}$
	- ==Steady-state Gain==:
		Gain after the system reaches steady-state
> [!Example]
> $$P(s)=\frac{Y(s)}{U(s)}=\frac{K_p}{\tau s+1}$$
> Steady-state : $t\to\infty,\,\,s\to 0$ $$K_p=K_s=\text{steady state gain}$$
	
- **==Stability==**: If all the (real parts of the) POLES are negative. 
	
- **Speed**:  determined by the POLE ==Closest== to Origin = Rate Determining Step = the Slowest Process


**==Proper==** Transfer Function: 
degree of numerator polynomial =< degree of denominator polynomial
E.g. $$\frac{s+7}{s^2+23s+2}\to proper$$ $$\frac{s^3+2s+7}{s+3}\to improper$$
**==Characteristic time==** $\tau$:
![[2e0b05a58bb36270b82765a16a22e3432365acfd1fa976f8cf99123492ebacba.png]]
$t=3\tau:\text{reaches 95\% of final steady-state value}$
$t=5\tau:\text{reaches 99\% of final steady-state value}$

> [!CASE1]
> 
> CSTR Example rearrange:$$\frac{1}{(\frac{\phi}{V}+k)}\frac{dC_A}{dt}+C_A=\frac{\phi C_{A,in}}{\phi+kV}$$**What we want**: $$\tau\frac{dy}{dt}+y=k_pu(t)$$Laplace Transform: $$\tau sY(s)+Y(s)=K_pU(s)$$

> [!CASE3]
> Second-order systems:
> $$\tau^2\frac{d^2y}{dt^2}+2\zeta\tau\frac{dy}{dt}+y=K_pu(t)$$ $$\tau^2s^2Y(s)+2\zeta\tau sY(s)+Y(s)=K_pu(s)$$ $$P(s)=\frac{Y(s)}{U(s)}=\frac{K_p}{\tau^2s^2+2\zeta\tau s+1}$$
> $\zeta$: **damping parameter**. A dimensionless quantity that describes how oscillations in a system decay over time.


> [!Case4] 
> Dead Time
> $y(t)=u(t-\theta)$
> $$P(s)=\frac{Y(s)}{U(s)}=e^{-\theta s}$$


> [!Case7] 
> Processes in Parallel
> $$P(s)=P_1(s)+P_2(s)=\frac{2}{10s+1}+\frac{-1}{s+1}=\frac{-8s+1}{(10s+1)(s+1)}$$
> Inverse Response ![[1bc6930b08d30f15e3edda8e499e2f1a727c5e2015ed0b7a12294841e88058de.png]]
> R.H.P. (right half plain (s>0)) zero -> inverse response
> here zero:$(-8s+1)=0,\,\,s=\frac{1}{8}>0$


> [!Case8] 
> Recycle ![[301bdf39c37fa29ec645afc7da725fa2a2ef7573088c40e7b98bc96fe389c2b6.png]]
$$Y(s)=[U(s)+P_2(s)Y(s)]\,P_1(s)$$
Negative sign in the denominator -> negative feedback$$P(s)=\frac{Y(s)}{U(s)}=\frac{P_1(s)}{1-P_1(s)P_2(s)}$$
> $$\tau\approx\frac{-1}{\text{the slowest pole}}$$
> Recycle **slows down** the process shockingly. 
> Poles shifting to the left, faster response, more damping. 


## Transfer Function Matrix
Transfer function Matrix - G(s):
$$
\begin{cases}
\frac{d\tilde{\mathbf{x}(t)}}{dt} = A \tilde{\mathbf{x}(t)} + B \tilde{\mathbf{u}(t)} + E \tilde{\mathbf{d}(t)} \\[1mm]
\tilde{\mathbf{y}(t)} = C \tilde{\mathbf{x}(t)}
\end{cases}
$$
ignore $B_d$, then
$$
\frac{d\tilde{\mathbf{x}}}{dt} =
\begin{bmatrix}
\frac{\partial x_1}{\partial t} \\[2mm]
\frac{\partial x_2}{\partial t} \\[1mm]
\vdots \\[1mm]
\frac{\partial x_n}{\partial t}
\end{bmatrix}
=
A
\begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix}
+
B
\begin{bmatrix}
u_1 \\ u_2 \\ \vdots \\ u_m
\end{bmatrix}
$$
$$
s \begin{bmatrix} X_1(s) \\ X_2(s) \\ \vdots \\ X_n(s) \end{bmatrix} = A \begin{bmatrix} X_1(s) \\ X_2(s) \\ \vdots \\ X_n(s) \end{bmatrix} + B \begin{bmatrix} U_1(s) \\ U_2(s) \\ \vdots \\ U_m(s) \end{bmatrix}
$$
$$
\begin{bmatrix} X_1(s) \\ X_2(s) \\ \vdots \\ X_n(s) \end{bmatrix} = (sI - A)^{-1} B \begin{bmatrix} U_1(s) \\ U_2(s) \\ \vdots \\ U_m(s) \end{bmatrix}
$$
$$\begin{bmatrix} Y_1(s) \\ Y_2(s) \\ \vdots \\ Y_n(s) \end{bmatrix} = C\begin{bmatrix} X_1(s) \\ X_2(s) \\ \vdots \\ X_n(s) \end{bmatrix}= C[sI-A]^{-1}B\begin{bmatrix} U_1(s) \\ U_2(s) \\ \vdots \\ U_m(s) \end{bmatrix}$$
$$G(s)=\frac{Y(s)}{U(s)}$$
$$G(s) = C [sI - A]^{-1} B + D$$
Poles: determinant=$[sI-A]^{-1}$ $\to det|sI-A|=0$