---
date: 2025-09-11
Prof: Dr.ir. Farzad Mousazadeh
aliases:
  - "Chapter 3: Analysis"
---
≈Ω<Elaboration on step 5>
## Background of Analysis
Why carry out Analysis --- To understand the process better and carry over to control

Types of Analysis:
- Steady-state non-linear
- Dynamic linear

Process Properties:
- Non-linear
- Large variables (e.g. $10^3-10^4$ variables in DC with 100 stages)
- Stiff(differential equations), large time variability
- Poor scaling, variables have wide range of values
- Uncertainty
- Sparse, high number of equations & low number of variables in equation

## Steady-state Analysis
Mass Balance:$$0=\frac{\phi}{V}C_{A,in}-\frac{\phi}{V}C_{A}-k_0e^{-E_A/RT}C_A$$
Energy Balance:$$0=\frac{\phi}{V}T_{in}-\frac{\phi}{V}T-\frac{\triangle H_r}{\rho c_P}k_0e^{-E_A/RT}C_A-\frac{h_A}{V\rho c_P}(T-T_c)$$
### Number of Steady-states
Steady-State Points: 2
![[f3b46bce928af4a8610c5b045d3582521db2f83f80e8ad9a8d369e15ce2bc13e.png]]
\*The second point in the middle is not a stable steady-state point

**Engineering understanding of Stability**: if you perturb a process slightly, then the process comes back to its state before the perturbation.

\*Only the third steady-state point is the operating point, because the first one is below ignition.


> [!Example] Real industry challenge: Heat Exchange Rupture
> Solution: simulate in tanks
> - Put liquid and gas in separate tanks(close systems), also simulate the heat exchange. 
> - Use a value to connect two close systems. Open it for 1mm to simulate the leaking hole.
> - The result shows that it only takes 3-4 seconds to reach 8 bar, while the PSV valve needs 20 seconds to close.
>
>Discovery: Not Safe

## Linearization

Sources of **non-linearity** in a process:
- cross-terms$$\phi_{in},\phi_{out},\phi_{in}(t),\phi_{out}(t)$$
- saturation$$k_0e^{-E_a/RT}$$
- thermodynamic property$$lnP_L^0=\frac{b}{c+T}+a$$
- reaction kinetics$$r=k\,C_A^m\,C_B^n$$

For$\frac{dx}{dt}=f(x,u,d)$, where x: state variable; u: input; d: disturbance

1. find steady-state operating points
2. define deviation variable $\tilde{x}=x-x_0$
3. linearize


From Taylor expansion, the equation of Linearization: 
$$\frac{d\tilde{x}}{dt}=(\frac{\partial f}{\partial x})\tilde{x}+(\frac{\partial f}{\partial u})\tilde{u}+(\frac{\partial f}{\partial d})\tilde{d}$$
@$x=x_0, u=u_0, d=d_0$


> [!Example] CSTR
> A->B with a first order reaction
> $$\frac{dC_A}{dt}=\frac{\phi_v C_{A,in}}{V}-\frac{\phi_v C_{A}}{V}-kC_A$$
> Linearize:$$\frac{dC_A}{dt}=(\frac{\partial f}{\partial C_A})\tilde{C_A}+(\frac{\partial f}{\partial \phi})\tilde{\phi}+(\frac{\partial f}{\partial C_{A,in}})\tilde{C_{A,in}}$$
> $$\frac{dC_A}{dt}=[-\frac{\phi}{V}]\tilde{C_A}+[\frac{C_{A,in}}{V}-\frac{C_{A}}{V}]\tilde{\phi}+[\frac{\phi}{V}]\tilde{C_{A,in}}$$


> [!Example] State-Space
> Non-isothermal CSTR with an exothermic reaction
> $$\frac{dx_1}{dt}=f_1(x_1,x_2,u_1,u_2,d)$$
> $$\frac{dx_2}{dt}=f_2(x_1,x_2,u_1,u_2,d)$$
> $$\frac{d}{dt} \begin{bmatrix}\tilde{x}_1 \\[6pt] \tilde{x}_2 \end{bmatrix}=A \begin{bmatrix}\tilde{x}_1 \\[6pt] \tilde{x}_2 \end{bmatrix}+B \begin{bmatrix} \tilde{u}_1 \\[6pt] \tilde{u}_2\end{bmatrix}+E \,\tilde{d}$$
> $$A =
\begin{bmatrix}
\left.\dfrac{\partial f_1}{\partial x_1}\right|_* & \left.\dfrac{\partial f_1}{\partial x_2}\right|_* \\[10pt]
\left.\dfrac{\partial f_2}{\partial x_1}\right|_* & \left.\dfrac{\partial f_2}{\partial x_2}\right|_*
\end{bmatrix},
\quad
B =
\begin{bmatrix}
\left.\dfrac{\partial f_1}{\partial u_1}\right|_* & \left.\dfrac{\partial f_1}{\partial u_2}\right|_* \\[10pt]
\left.\dfrac{\partial f_2}{\partial u_1}\right|_* & \left.\dfrac{\partial f_2}{\partial u_2}\right|_*
\end{bmatrix},
\quad
E =
\begin{bmatrix}
\left.\dfrac{\partial f_1}{\partial d}\right|_* \\[10pt]
\left.\dfrac{\partial f_2}{\partial d}\right|_*
\end{bmatrix}.$$


## Laplace Transform

Why Laplace:
- To convert a function of real variable (normally time, t) to a function of complex variable “s”.
- Converting differentiation and integration in the time domain to easier form in Laplace domain.
- Tool for solving linear differential equations and dynamic systems by simplifying ordinary differential equation to algebraic equation.


Laplace transform equation:
$$F(s) = \mathcal{L}\{f(t)\}= \int_{0}^{\infty} f(t)\, e^{-st}\, dt$$
**s: Laplace domain**
- an easier way to solve
- linear
- keeps all the properties from the original equation


### Analysis in Laplace Domain
1. $f(t)=Constant$:
$$F(S)=\int_{0}^{\infty} Ce^{-st}dt=\frac{C}{s}$$

 2. input functions, (unit) step function: $$u(t)=0@t=0, u(t)=c@t>0$$unit step input: $u(t)=1@t>0$
 
3. $f(t)=e^{at}$:
$$F(s)=\mathcal{L}\{f(t)\}=\frac{1}{s-a}$$
4. $f(t)=e^{-at}$:
$$F(s)=\mathcal{L}\{f(t)\}=\frac{1}{s+a}$$
5. $f(t)=sin(\omega t)$:
$$F(s)=\mathcal{L}\{f(t)\}=\frac{\omega}{s^2+\omega^2}$$
6. $f(t)=cos(\omega t)$:
$$F(s)=\mathcal{L}\{f(t)\}=\frac{s}{s^2+\omega^2}$$
7. $f(t)=\frac{t^k}{k}$:
$$F(s)=\mathcal{L}\{f(t)\}=\frac{1}{s^{k+1}}$$
8. $\mathcal{L}\{f(t)\}= \int_{0}^{\infty} f'(t)\, e^{-st}\, dt$:$$\mathcal{L}[f'(t)]=sF(s)-f(0)$$
### Delay/dead time $\theta$
$$\mathcal{L}[f(t-\theta)]=\int_{0}^{\infty} f(t-\theta)\, e^{-st}\, dt=\int_{0}^{\infty} f(t_0)\, e^{-s(t_0+\theta)}\, dt_0$$
$$=e^{-s\theta}\int_{0}^{\infty} f(t_0)\, e^{-st_0}\, dt_0=e^{-s\theta}F(s)$$
($t=t_0+\theta, dt=dt_0$)


### Final Value $f(t \to \infty)$
$$\mathcal{L}[f'(t)]= \int_{0}^{\infty} f'(t)\, e^{-st}\, dt=sF(s)-f(0)$$
Take limit on both sides:
$$lim_{s\to 0}\int_{0}^{\infty} f'(t)\, e^{-st}\, dt=lim_{s\to 0}(sF(s)-f(0))$$
$$lim\int_{0}^{\infty} f'(t)dt=f(\infty)-f(0)=lim(sF(s))-f(0)$$
$$f(t\to\infty,s\to 0)=lim(sF(s))$$

> [!Example] Laplace Transform
>Time response of a system: $10\frac{dx}{dt}+x=2u(t)$
>unit step input e.g. $10m^3/min,11m^3/min$ 
>Laplace transform:$$10 \mathcal{L}\left\{\frac{dx}{dt}\right\} + \mathcal{L}\{x\} = 2 \mathcal{L}\{u(t)\}$$$$10 \big(s X(s) - x(0)\big) + X(s) = 2 \cdot \frac{1}{s}$$$$10s\,X(s)+X(s)=\frac{2}{s}$$
>$$X(s)=\frac{2}{s(10s+1)}=\frac{0.2}{s(s+0.1)}=\frac{2}{s}-\frac{2}{s+0.1}$$
>Inverse Laplace Transformation: $$x(t)=2-2e^{-0.1t}$$



## Transfer Function
$$P(s)=\frac{Y(s)}{U(s)}=\frac{\mathcal{L}(Output)}{\mathcal{L}(Input)}=\frac{\text{numerator}}{\text{denominator}}$$
where:
P(s): Process Transfer Function
Y(s): Transfer Function of output
U(s): Transfer Function of input


Example:$\quad 10 \frac{dy}{dt} + y(t) = 2 u(t)$
Laplace transformation:$\quad 10 s Y(s) + Y(s) = 2\, U(s)$
$$Y(s) (10 s + 1) = 2\, U(s)$$
$$\frac{Y(s)}{U(s)} = \frac{2}{10 s + 1} = P(s)$$


### Properties of Transfer Function
- **Order**: Degree of "s" in the denominator of Transfer Function
**Degree** is highest power = order of the original differential equation

- **Poles**: Roots of the denominator(polynomial)
**Roots** solve for "s" by putting denominator equal to 0

- **Zeroes**: Roots of the numerator(polynomial)
**Roots** solve for "s" by putting numerator equal to 0

- **Gain**: $\triangle Y/\triangle U(s\to 0)$  How much the output changes by change of input
**Steady-state gain** is the gain after the system reaches steady-state

- **Stability**: If all the (real parts of the) poles are negative. 
It ensures that the system’s free response decays over time, and the system eventually settles at a steady state.

- **Speed**: 
a) The more negative the real part of a pole, the faster the system response; 
b)Strong negative feedback(higher gain) also increases the speed.


For $\frac{Y(s)}{U(s)} = \frac{2}{10 s + 1} = P(s)$:
$$
\begin{array}{|c|c|c|}
\hline
\text{Property} & \text{Value} & \text{Explanation} \\
\hline
\text{Order} & 1 & \text{Highest power of } s \text{ in the denominator (first-order system)} \\
\hline
\text{Poles} & s = -0.1 & \text{Roots of the denominator (solve } 10s+1=0\text{)} \\
\hline
\text{Zeros} & \text{None} & \text{Roots of the numerator (constant, no root)} \\
\hline
\text{Gain} & K = 2 & \Delta Y / \Delta U, \text{steady-state gain} \\
\hline
\end{array}
$$


### Proper & Improper Transfer Functions
Proper: degree of numerator polynomial =< degree of denominator polynomial
E.g. $$\frac{s+7}{s^2+23s+2}\to proper$$
$$\frac{s^3+2s+7}{s+3}\to improper$$


### Case 1: First Order System
Diff Eq.: $$\tau \frac{dy}{dt}+y(t)=K_pu(t)$$Laplace Transform: $$\tau s Y(s)+Y(s)=K_pU(s)$$
$$P(s)=\frac{Y(s)}{U(s)}=\frac{K_p}{\tau s+1}$$
Pole: roots for denominator $\tau s+1$
$$s=\frac{-1}{\tau}$$
> [!Example] Example 1
> $$P(s)=\frac{1}{5s+1}$$
For a unit step input, $\mathcal{L}(u(t))=\frac{1}{s}$
$$Y(s)=P(s)U(s)=\frac{1}{5s+1}\,\frac{1}{s}=\frac{1}{s}+\frac{-5}{5s+1}$$
Inverse Laplace: $$y(t)=1-e^{-0.2t}$$
![[d29d3ec0a7272043b00ae8aa85347ad50136484c960156cddcff953e3b804a7f.png]]


![[5b6921c1b42a80c51c98c07243c310b084b9f4001aee780a8bb87c70a7752d9c.png]]


### Case 2: Integrators
Diff Eq.: $$\frac{dy}{dt}=K_pu(t)$$Laplace Transform: $$s Y(s)=K_pU(s)$$$$P(s)=\frac{Y(s)}{U(s)}=\frac{K_p}{s}$$Pole: roots for denominator $s=0$ , unstable
Time response for unit step input: 
$$Y(s)=\frac{K_p}{s}\,\frac{1}{s}=\frac{K_p}{s^2}$$
Inverse Laplace $$y(t)=K_pt$$
![[c95513b6a8980e36054953265fe8bb54862c9e5d64db7780740c60ffa9590f4c.png]]


### Case 3: Second order systems
$$\tau^2\frac{d^2y}{dt^2}+2\zeta\tau\frac{dy}{dt}+y=K_pu(t)$$
$\zeta$: damping parameter. A dimensionless quantity that describes how oscillations in a system decay over time.

Laplace Transform: $$\tau^2s^2Y(s)+2\zeta\tau sY(s)+Y(s)=K_pu(s)$$$$P(s)=\frac{Y(s)}{U(s)}=\frac{K_p}{\tau^2s^2+2\zeta\tau s+1}$$
![[7e99986543e7870f84c5cd91de8400a629ea8e13dedfac627aeda643b99fc52c.png]]


### Case 4: Dead time
E.g. plug flow reactor, material transport conveyor

Time domain: $y(t)=u(t-\theta)$, which $\theta$ is dead time
$$P(s)=\frac{Y(s)}{U(s)}=e^{-\theta s}$$
![[f42d5807bfe4482c988a4f69934ae6f0e0d25c6bd5306857c1fd57353761602a.png]]


### Case 5: Processes in Series
![[4d476409efb1ae465141490f265888a0fcbb0bca134d32da145a1073d9a94792.png]]
Combined transfer function:$$Y(s)=P_3(s)Y_2(s)=P_3(s)P_2(s)Y_1(s)=P_3(s)P_2(s)P_1(s)U(s)$$$$P(s)=\frac{Y(s)}{U(s)}=P_3(s)P_2(s)P_1(s)$$

### Case 6: Processes in Parallel
![[ea57003fa805eb512e867e081a1f707a659ca9f45e10e0ed5c6edbc89e6b37c3.png]]
$$Y(s)=U(s)P_1(s)+U(s)P_2(s)$$
$$P(s)=\frac{Y(s)}{U(s)}=P_1(s)+P_2(s)$$

### Case 7: Inverse Response
Two stable processes are in parallel: $$P_1(s)=\frac{2}{10s+1};\ P_2(s)=\frac{-1}{s+1}$$
Combined transfer function: $$P(s)=P_1(s)+P_2(s)=\frac{-8s+1}{(10s+1)(s+1)}$$
Calculate time response of this system:![[22ef25dc9bcd51a7e50c2a09746ae1f1425dd4c9c3117854b0cb99a3011c7d92.png]]

Final steady-state gain: $P_1=2, P_2=-1\to P(s)\approx1$

Example: thermometer / reboiler


### Case 8: Recycle
![[301bdf39c37fa29ec645afc7da725fa2a2ef7573088c40e7b98bc96fe389c2b6.png]]
$$Y(s)=[U(s)+P_2(s)Y(s)]\,P_1(s)$$
$$P(s)=\frac{Y(s)}{U(s)}=\frac{P_1(s)}{1-P_1(s)P_2(s)}$$
> [!Example] Recycle system
> $P_1(s)=\frac{1}{5s+1},\,P_2(s)=\frac{0.8}{10s+1},\,3\tau=30min$ to reach 95% of steady state
> Time constants are 5 & 10; Poles are -0.20 & -0.1
> $$P(s)=\frac{P_1(s)}{1-P_1(s)P_2(s)}=\frac{10s+1}{50s^2+15s+0.2}$$
> $$s_1=-0.0140,\,s_2=-0.2860$$
> $$\tau\approx\frac{-1}{\text{the slowest pole}}=\frac{-1}{0.014}$$
> Poles shifting to the left, faster response, more damping


## Connection to Control
- **Open-loop**: Feed-forward (measure disturbance, adjust input)
![[f29dadba78072237f7017b07c46c6e3f3e0253086625b90ce22436e823bc6a18.png]]

- ==**Closed-loop**==: Feedback (measure output, adjust input, e.g. Electric oven)
![[b1718de1f1a2b1fdbb43ca2bb0781b7fd2586e7cd05d1c016dfbf833fc658361.png]]


## Model Approximation
![[3530a31b2f2d5a06aea4235920fc6cab6965814ee2dc998862ab966886bcef29.png]]


## Interaction
One input influences many outputs
![[b4d742dc261eeebc6100145769007c48738ef303669d935a4bd5b5e5f8b400ad.png]]

Transfer function Matrix G(s):
$$
\begin{cases}
\frac{d\tilde{\mathbf{x}}}{dt} = A \tilde{\mathbf{x}} + B \tilde{\mathbf{u}} + B_d \tilde{\mathbf{d}} \\[1mm]
\tilde{\mathbf{y}} = C \tilde{\mathbf{x}} + D \tilde{\mathbf{u}}
\end{cases}
$$
ignore $B_d$, then
$$
\frac{d\mathbf{x}}{dt} =
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
$$Y(s)=CX(s)+DU(s)=C[sI-A]^{-1}BU(s)+DU(s)$$
$$Y(s)=G(s)U(s)$$
$$G(s) = C [sI - A]^{-1} B + D$$
Poles: determinant=$[sI-A]^{-1}$ $\to det|sI-A|=0$