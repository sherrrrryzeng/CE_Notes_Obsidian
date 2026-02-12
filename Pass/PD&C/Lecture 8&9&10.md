---
date: 2025-09-25
Prof: Dr.ir Marta Zagorowska
aliases:
  - "Chapter 5: Control for SISO system"
---
## Basic Intro

**Process control objectives**:
- safety
- quantity (production rates)
- quality (specifications)

## Process description
**Process variables**:
- temperatures
- flowrates in&out
- pressures
- composition

**Input variables** - ==u==: 
- Variables that can influence the system independently and make changes
- Input variables can be **manipulated variables** if we can modify them as we want, or **disturbance variables** (- ==d==,) if we cannot decide the value. 

**Output variables** - ==y==: 
- Variables that provide information about the process internals

**State Variables** - ==x==:
- describe the internal condition of the process

\*Difference: 
	- Outputs are measurements of the state variables, or their combination. Output variables can be **measured variables**, if measurements are available, or unmeasured variables. 
	- Typically, by measured variables we mean **online measurements**.


## Process control
The tasks of process control:
1. Monitoring output variables by measurements
2. Making decisions for the manipulated variables considering the current and the desired state of the process
3. Implementing the decisions on the process

### Manual control systems
---when the tasks are done by humans

### Automatic control systems
---when the tasks are done by machine(computer mostly) *what we focus on*

- Sensors
	Thermocouples, differential pressure cells, chromatographs,...
- Controllers
	Pneumatic controllers, electronic controllers
- Final control elements(actuators)\
	Valves, pumps, compressors, relay switches,...

Choosing the hardware elements --- Process Design
Designing how the process is operated --- Process Control


## Control System Configurations

**Open loop control:**
- The controller takes decisions without considering the outputs or disturbances --- no loop
- *Example: traffic lights*


**Feedforward control:**
- The decision is taken before the disturbance affects the controller --- fed forward
- Used typically to compensate for **known disturbances**


**Feedback control:**    *what we focus on*
- Decisions are based on information(output) "fed back" to the controller - **closed loop**
- The **most common** control framework

- are independent of the type of system
- For linear systems, feedback control systems can be represented and analysed in a block diagram with transfer functions
- Dynamics of the sensors and actuators are often neglected, with $K_a=K_S=1$
![[6b42a383306e6567597b6a8e788605ded2f05b22f143084ec1106240a74ab692.png]]


#### Case: Tank level control
1. **Manual control**
	
2. **On-off control**
	regardless of the size of the error, the controller goes full on or full off.
	*Examples: Non-critical systems(home cooling/heating)*
	
3. **Proportional control**
	Steady state:$$F_{i_{steady}}=F_{o_{steady}} \text{ , tank level is }h_s$$
	Use proportional control valve to change the level = 
	Control inputs are proportional to the error.   *K: Proportional gain*
	
	The input applied to the system: $$F_{i_{applied}}=F_{i_{steady}} + K(h_{s}-h_{})$$
	$\bar{h}=h-h_s$, $\bar{u}=F_{i_{applied}}-F_{i_{steady}}$, $F_{o}=c*h$
	Derivation: $$A\frac{d\bar{h}}{dt}=F_{i_{applied}}-F_o=\bar{u}-(F_o-F_{o_{steady}})=\bar{u}-c(h-h_s)$$
	Tank dynamics with deviation variables: $$\frac{d\bar{h}}{dt}=-\frac{c}{A_c}\bar{h}-\frac{1}{A_c}\bar{u}$$
	Tank dynamics with the proportional controller:$$\frac{d\bar{h}}{dt}=-\frac{c}{A_c}\bar{h}-\frac{K}{A_c}\bar{h}$$
	
	Another derivation:$$A\frac{dh}{dt}=F_i(t)-F_o(t)=F_i(t)-c*h$$
	$\tau$: proportional time; $K_t$: proportional gain $$\tau\frac{dh}{dt}+h=K_tF_i(t)$$$$\tau sH(s)+H(s)=K_tF_i(s)$$$$G(s)=\frac{H(s)}{F_i(s)}=\frac{K_t}{\tau s+1}$$

	An easier derivation:$$K(h_{sz}-h)=c*h$$	$$h=\frac{K}{c+K}h_{sz}<h_{sz}$$


## Proportional Control
Close-loop transfer function:
$$Y(s)=\frac{C(s)G(s)}{1+C(s)G(s)}R(s)+\frac{1}{1+C(s)G(s)}D(s)$$
![[e6b611480230b1e1e95c7c0a31a3263c40148577714b75c38e8d5abdcf056691.png]]

- Proportional controller in time domain:$$u(t)=Ke(t)$$
- Proportional controller transfer function:$$U(s)=KE(s)$$
- From the block diagram:$U(s)=C(s)E(s)$, therefore ==proportional controller==:$$C(s)=K$$

- Ignore disturbance $D(s)$, consider step change in R:$$\frac{Y(s)}{R(s)}=\frac{KG(s)}{1+KG(s)}$$
	Unit step transfer function: $R(S)=\frac{1}{s}$
	Tank transfer function:$$G(s)=\frac{K_t}{\tau s+1}$$
	Closed-loop transfer function:$$G_{CL}(s)=\frac{KG(s)}{1+KG(s)}=\frac{KK_t}{\tau s+1+KK_t}=\frac{K^*}{\tau^*s+1}$$
	where $K^*=\frac{KK_t}{1+KK_t}$, $\tau^*=\frac{\tau}{1+KK_t}$
	
	Closed-loop response: $$Y(s)=G_{CL}(s)R(s)=\frac{KK_t}{\tau s+1+KK_t}\cdot \frac{1}{s}=\frac{K^*}{\tau^*s+1}\cdot \frac{1}{s}$$
	![[e46bc07e909ca505565b4b5f2c827110c2b2900245bc546a8d1d005af6677b09.png]]
	- under proportional control is a response of a first-order system as well


In time domain:$$y(t)=K^*\left(1-exp(-\frac{t}{\tau^*}) \right)\to K^*<1\,\, (t\to \infty)$$
from Final Value Theorem:$$lim_{s\to 0}Y(s)=s\cdot G_{CL}(s)R(s)=K^*$$
- The larger the proportional gain K, the closer $K^*$ will be to unity. There is an offset:$$\delta_{final}=1-K^*$$
- More generally, for a step change of magnitude M:$$\delta_{final}=M-y(\infty)$$
- Adjusting K allow speeding up the response of the system:$$\tau^*=\frac{\tau}{1+KK_t}<\tau$$
Usage: Systems where **offset is unimportant**. (e.g., a tank used for storage)


### A three-tank system
$$\frac{Y_3(s)}{U(s)}=\frac{K}{(\tau_1s+1)(\tau_2s+1)(\tau_3s+1)}$$
$$G_{CL}(s)=\frac{KK_p}{(\tau_1s+1)(\tau_2s+1)(\tau_3s+1)+KK_p}$$

for s:
- non-zero imaginary part == oscillations in system
	but does not affect the stability of system
- the real part affect the stability --- negative real part == stable
- only negative imaginary part == only sustained oscillations == stable


# Stability

We consider only linear systems described by transfer function with m zeros and n poles:$$G(s)=K\frac{(s-z_1)\cdot ...\cdot(s-z_m)}{(s-p_1)\cdot...\cdot(s-p_n)}$$
A linear system is stable if the output is bounded for all bounded inputs. 
*Assuming distinct poles, the response of the system G(s) to a step input 1/s is:*$$Y(s)=G(s)\cdot \frac{1}{s}=\frac{A_0}{s}+\frac{A_1}{s-p_1}+...+\frac{A_n}{s-p_n}$$
*In time domain:*$$y(t)=A_p+A_1exp(p_1t)+...+A_nexp(p_nt)$$
If:
- $p_i$ is real and positive: $exp(p_it)\to\infty$
- $p_i$ is real and negative: $exp(p_it)\to 0$
- $p_i$ is imaginary $p_i=\alpha_i+j\beta_i$:
	- $\alpha_1$ is positive: $exp(\alpha_it)\to\infty$
	- $\alpha_1$ is negative: $exp(\alpha_it)\to 0$

Therefore:
- **A linear system is stable if all the poles have negative real parts**
- NB: Distinct poles with **zero real parts** also give stability. 
- Repeated poles with zero real parts need more attention, but are rare in process control
- Non zero imaginary part == oscillation

![[e2bdaf462c8d35190c1643e12f42f0109cdb36f698e8669e3831687061c5a95c.png]]

### Feedback control - stability
Close-loop transfer function:
$$Y(s)=\frac{C(s)G(s)}{1+C(s)G(s)}R(s)+\frac{1}{1+C(s)G(s)}D(s)$$
- Poles of closed-loop transfer function:$$1+C(s)G(s)=0$$


For a three-tank system:$$G_{CL}(s)=\frac{KK_p}{(\tau_1s+1)(\tau_2s+1)(\tau_3s+1)+KK_p}$$
with $K=\frac{1}{c_3},\,\tau_i=\frac{A_i}{c_i}$.

- The characteristic polynomial is:$$48s^3+44s^2+12s+(1+6K_p)=0$$
- Depending on different $K_p$ we choose, the stability of the system is different:
![[ff2292f5301df32a6f6ed6975dff19b03a5e495aa0d1b37c5213f5e06340e178.png]]
( $j^2=-1$ )


**The meaning of the ==Root Locus==:**
  indicates how the poles of the closed loop system change with a parameter
  
- For $K_p = 0$ : three real poles –-- no oscillations

- For $K_p < 0.004$ : three real poles

-  For $0.004<K_p<1.67$ : one real pole “moving” along the horizontal axis to the left, and two poles with non-zero imaginary part –--  oscillatory behaviour

- For $K_p> 1.67$ : two poles on the right-hand side of the imaginary axis –-- unstable behaviour

- For $K_p = 1.67$ : two poles on the imaginary axis –-- boundary of stability



How to find the maximal $K_p$ : 
  ---Direct substitution method
- We will be on the boundary of stability if $s=j\omega$ solves the characteristic equation. Plugging it in and solving for $\omega$ and $K_p$ :$$\omega=0, K_p=-\frac{1}{6}\,\,or\,\,\omega=+-\frac{1}{2}, K_p=\frac{5}{3}$$

# Controllers

## Integral control
![[59cc63dbf1e4b10705ccbf040ec2871009a7822271421e723248b3441a5d05a7.png]]

Integral Control action depends on the integral of the error:$$u(t)=\frac{1}{T_i}\int_0^te(\tau)d\tau$$
where: $T_i$ is the integral time *(scale of the integral - can be changed depending on how much impact we want from the integral controller)* and can be adjusted.

In Laplace domain:$$C(s)=\frac{1}{T_is}$$
Why this works:
$$G(s)\,\,@\,\,(s=0)\to g$$
$$R(s)=\frac{M}{s}\,\,\text{(step input to M)}$$
$$(R(s)-Y(s))C(s)=U(s)=Y(s)G(s)^{-1}$$
$$sY(s)=s\frac{R(s)C(s)G(s)}{1+C(s)G(s)}=\frac{s\frac{M}{s}\frac{1}{T_is}G(s)}{1+\frac{1}{T_is}G(s)}=\frac{MG(s)}{T_is+G(s)}$$
$$s\to0: sY(s)\to \frac{Mg}{0+g}=M$$
-> Integral controller reacts immediately

![[17a09f2c1f1b5f9ff9e444dd96d6dbf523d2b32cb2002ae832718abdcd2d8f96.png]]
Properties:
- has no offset
- for fast response ==can introduce oscillations==
- can be sluggish, if no oscillations allowed


### Integrator Windup
When the error is too big for controller, it opens completely *(reach physical boundaries)* and can not react. -> can not reach the set point
![[bdf8234347e2cc866df532e61c21aac4331b152f1174dd7d0fcb6ff4c2ad3c6d.png]]
![[97469e8ffa901f634e9a39ed0ad573136f2fb6d55f4c09c0980418ecb4d9aa70.png]]

How to counteract: A possible anti-windup scheme
![[493ed0976c5edde85dd7261111971face81a998d35142c81fb0813d2f58334c5.png]]
![[638bc16c99094a7fee34d2166898f037fed0ef6b41215b847cbc68d8fcea7070.png]]



## Proportional-Integral control 
Proportional control: $C(s)=K$
Integral control: $C(s)=\frac{1}{T_is}$
Combine two:$$C(s)=K\left(1+\frac{1}{T_is}\right)$$An equivalent: $$C(s)=K_p+\frac{1}{K_is}$$
*If there is an integral controller in the system, a proportional controller is enough to have 0 offset.* 

## Proportional-Derivative control
Derivative control anticipates the change in the error:$$u(s)=K_d\frac{de(t)}{dt}$$
In Laplace domain:$$C(s)=K_ds$$
Ideal derivative: $$u_D(t)=K_d\delta(t)$$
-> Impossible to do physically![[6bce5a5cc28544cee0fe172984106cc14191661a67d6d9dfae98d5c6b61ec5e7.png]]

Use **filtered derivative**:$$C_D(s)=\frac{K_ds}{K_fs+1}$$
Here $K_f=0.1K_d$
![[c2584ea4657b1234a025572a91ce477e86c316da0cb695ffa7d4cf5acc5680d8.png]]
-> Filtering reduces noise sensitivity *(prevent big spike / kick)*.


Derivative controllers are never used solely - lead to infinite oscillation. 
Typically combined with a proportional controller:$$C(s)=K(1+K_ds)$$
![[e3c053c4f44c722da7502e31eaaec963dad3defd7f17cfef0522c0d5b83c0b50.png]]

 Properties:
 - Fewer oscillations
 - Offset remained
 


## Proportional-Integral-Derivative control
In Laplace domain:$$C(s)=K(1+K_ds+\frac{1}{T_is})$$
![[8a4106a912e7a741e4dc22b32255662b996b4b83253484c49e142211fab55d39.png]]

Step response of the controller:
- $E(s)=\frac{1}{s}$
- $U(s)=(U_P(s)+U_D(s)+U_I(s))\cdot\frac{1}{s}$

In time domain:
- Proportional action: $u_P(t)=K$
- Integral action: $u_I(t)=\frac{K}{T_i}\cdot t$
- Derivative action: $u_D(t)=KK_d\delta(t)$
-where $\delta$ is dirac function


Most common controllers in industry:
- Simple to design and implement
- With few parameters to tune – the parameters are directly related to the response
- Often “sufficiently good” and more complex approaches would not be better
- Easily extendable