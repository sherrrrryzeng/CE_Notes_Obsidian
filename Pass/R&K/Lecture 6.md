---
date: 2025-11-28
Prof: Jose Palomo Jimenez
aliases:
  - Parameters estimation
  - Non-ideal Reactors
---
# Parameters estimation

Deal with the provided experimental datas

What can we measure:
- Concentration $= f(x,t)$
- Temperature
- Intermediate species
- Residence time distribution
- ......


## Linear models - **Least-squares estimation**
We want to describe y as a function of x, using a linear relationship: $$y_{i,model}=mx_{i,exp}+b$$
Definition of **least squared error** (cost function): $$\phi(\theta)=\sum_{i=1}^{n}(y_{i,exp}-y{i,model}(\theta))^2\,\,\to\,\text{minimum}$$
Least-square solution:![[Pasted image 20251204110935.png]]$$\phi(\theta)=|Y-X\theta|^2=(Y-X\theta)^T(Y-X\theta)$$ $$\frac{d\phi(\theta)}{d\theta_T}|_{\theta_{opt}}=0,\,\,\nabla^2\phi(\theta)|_{\theta_{opt}}>0$$
$$\theta_{opt}=[(X^TX)^{-1}X^T]Y$$

> [!Example] 
> $$r=kC_A^nC_B^m$$
> Linearization: $$\to\,\log_{10}(r)=\log_{10}(k)+n\log_{10}(C_{A})+m\log_{10}(C_{B})$$
> From experiment, $$\log_{10}(r)=y,\,\,log_{10}(C_A)=x_1,\,\,\log_{10}(C_{B})=x_2$$
> Matrices X and Y : ![[0768276e0b71cce3fabbf388c25f3d17df5fe9507984ece80b16664fe5c3afbb.png]]
$$\theta=[m\,\,\,n\,\,\,\log_{10}(k)]^T$$
$$\theta_{opt}=[(X^TX)^{-1}X^T]Y$$



## Non-linear systems - Optimization
We want to describe y as a function of x, using a model: $$y_{i,model}=h(x_i,\theta)$$
This function can have any shape, it can even be a differential equation. $$\phi(\theta)=\sum_{i=1}^n(y_{i,exp}-h(x_i,\theta))^2\,\,\,\to\,\text{minimum}$$

### Python for parameters estimation
`scipy.optimize.fmin(func,x0,args=(),xtol=...)`
This function looks for the minimum of the function using a gradient approach. It requires an initial guess. 

Procedure:
- Read/load/write the experimental data
- Define the **error function**
	Error function receives $k= [k_1,k_2]$ as independent variable and the rest of parameters as extra arguments (exp concentrations, time,…). 
	This function must:
	1. Solve the reactor mass balance for A, B and C *(you have to define the reactor mass balance before invoking the integrator!).*
	2. Compute the differences between the experimental and calculated concentrations:$$\phi(\theta)=\sum[(C_{A,exp}-C_{A,calc})^2+(C_{B,exp}-C_{B,calc})^2+(C_{C,exp}-C_{C,calc})^2]$$
	3. Return the error value.
- Finally, we invoke `fmin` for optimization


# Non-ideal Reactors
![[2437899bfb7c0ffdfc6352eeb111b503bac343b7cf7c2d6426e8cb1ae1e9ce30.png]]

- Macromixing -> **Residence time distribution (RTD)**
	 Information about the time spent by the different molecules inside the reactor
- Micromixing -> **The quality of mixing (Reactor Model)**
	 Describes how molecules of different ages encounter one another in the reactor


## RTD - Residence time distribution

Characterisation of tracers:
- Dyes
- Fluorescent
- Radioactive
- NMR

Injection: pulse / step


### C(t), E(t), F(t)
-> C(t) experimental determination
![[e8c9629bc523a770d11f3186d2aa89f2b34e2661f646f71ceced66a16e5ec982.png]]

-> E(t) **residence time distribution function - ==RTD==**: $$E(t)=\frac{C_A(t)}{\int_0^\infty C_Adt}$$ $E(t)dt$ is the fraction of fluid that have left the reactor and have spent at time inside between t and dt. $$\int_0^\infty E\,dt=1$$
-> F(t) **cumulative distribution function**: $$F=\int_0^t Edt,\,\,E=\frac{dF}{dt}$$ F(t) is the fraction of effluent that has been in reactor for less than time t.


### RTD - E(t)
**MRT - Mean Residence Time**: $$t_m=\frac{\int_0^\infty tE(t)dt}{\int_0^\infty E(t)dt}=\int_0^\infty tE(t)dt$$
**Variance of the residence time**: $$\sigma^2=\int_0^\infty(t-t_m)^2E(t)dt$$

> [!Ideal CSTR]
> (Constant density/volume)
Mole balance: $$V\frac{dC_A}{dt}=-C_Av,\,\,\to\,\,C_A=C_{A0}e^{-\frac{t}{\tau}}$$
C-curve to E-curve: $$E(t)=\frac{C_A}{\int_0^\infty C_Adt}=\frac{e^{-\frac{t}{\tau}}}{\tau}$$
(Dimensional)
First moment (mean): $$t_m=\tau$$
Second moment (variance): $$\sigma^2=\tau^2$$

## Dimensionless RTD
$$E(\theta)=\tau E(t),\,\,\theta=\frac{t}{\tau}$$
$$E(\theta)=exp(-\theta)$$

### Ideal CSTR
From Example:
First moment: $\theta_m=1$ 
Second moment: $\sigma_{\theta}^2=1$
\* For CSTR it's special --- both moments are 1!

So CSTR in series: $$N=\frac{t_m^2}{\sigma^2}=\frac{\theta_m^2}{\sigma_\theta^2}$$

### Ideal PFR
![[b9a2ad68febc5294da654bc1501ce23ad2c07de8b7fdb5930482b9ae3cf9ae56.png]]
$$\delta(x)=0\,(x\neq 0),\,\,\,\infty(x=0)$$
$$E(t)=\delta(t-\tau)$$
First moment: $t_m=\tau$
Second moment: $\sigma^2=0$

### Any reaction system
![[2c67d2c2c282f3437148384e69cb463ff68991c0a99de1655fcd26dd09efb52e.png]]


# RTD as a tool for reactor diagnostics and troubleshooting

![[d1c82d1ccb82a9d6554cae784c81be97e770c35c42cc98ddbae026892b98c32b.png]]
![[ff42d0f66055eaa736180454c81bd895f71689176def8314c4aca317c97b6b20.png]]
![[a4e6050ea27033ad5bc9229f41359dddfddff240aa900e5c3b4f1ce3dee33df8.png]]

