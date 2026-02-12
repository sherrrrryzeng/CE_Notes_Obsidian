---
date: 2025-10-16
Prof: Dr.ir Marta Zagorowska
aliases:
  - Extensions to SISO
  - Controller implementation
  - MIMO
---
# Extensions to SISO
## Ratio control
Usually used in mixing

A special kind of ==feedforward== control with the objective of maintaining the **ratio between two variables** – manipulated 𝑢 and disturbance variable 𝑑, typically two flows $$R=\frac{u}{d}$$
![[e4a520c3780a0fa74157ebf7cede870b05006a778ebcf5182e50a67816a536bf.png]]

1. Measure the flow of water
2. The ratio station adjusts the salt concentration

- Advantage: Feedforward helps with speeding up the response.
- Limitation: Requires both disturbance and model information.


## Cascade control
Example: Heated stirred tank
-We control the level by adjusting the cold water flow through a valve
-If everything goes “as normal”, the controller works as expected
-What happens if there is pressure disturbance in the cold water flow?
![[abdef58f91771fdbfc020acc377d7b81dfe8eae4170e46c62ab40e13d185eca7.png]]

After the disturbance, the level controller might react too slow. 
-> Add an additional controller for the valve
![[b5cb29e5f3650d3aacc38372aec92f14080acdb19010b0727e9038cd515c4370.png]]

Cascade control – nested controllers 
- Primary controller – outer loop, responds to output disturbances
- ==Secondary controller== – inner loop, responds to input disturbances

Design and tuning:
- Inner loop is typically designed **around an actuator** – like a valve
- Inner loop should be faster than the outer loop – at least 5 times
- Inner loop controller should be **simple and stable**, typically P or PI *(usually the outer loop includes an integrator)*
- Inner loop should be tuned first


## Dead-time compensation
Systems with dead time are common due to:
- Transportation over a long distance
- Recycling loops
- Slow measuring devises
- Processing times (composition analysis)
- Multiple subsystems in series
- .......

Consequences of delays:
- Wasteful or sluggish controller
- Instability

![[dff825bf1306b2bec88492cc6b9cb554959efecffce147f8c3c9bdd91843a8c4.png]]

Dead-time compensation using a model in an additional feedback loop: $$G_m(s)exp(-\alpha_ms)$$
![[27013042c354d6ca3127ee28fcaa0bf1e8b5312446d2792b454817848a527e28.png]]

![[96641bd7ce72c70adf114b39945e34d69f48db0a6baad8e89b045711b13e8406.png]]

Limitation: We need to know the model of the system (G(s))

Mismatch:  $G_m(s)exp(-\alpha s)\neq G_p(s)exp(-\alpha s)$
![[5baf178e7ac75e7d73215619cbe5fd56820607fc0213ebeab668f7eb6d2586dd.png]]

To do:
- Design a PI controller using IMC tuning rules
- Compare the PI controller with the dead-time compensation scheme
- Analyse what happens if the model is different from the plant (mismatch)


## Other control
- **Mid- and split range control**
	*For cascade control, there are 2 measurements for 1 manipulated variable*
	So we want 1 measurement for 2 manipulated variables
	![[0d14f53fb90fe676c67051455e8fa5c01d91501fc68e774adb0327d74999d5a0.png]]
	- Valve 𝑣1 is small but has **high resolution** 
		-precise, but can handle small disturbances
	- Valve 𝑣2 is large, but has low resolution
		-can handle **large disturbances**
	-> Two or more actuators used to control the same manipulated variable at the same time
	![[e72423fe3929fd261ae638dcb9a3e3bbe64a626023ae0423a88cde563d48cd15.png]]


- **Selector control**
	*Mid and split-range – multiple actuators and controllers for 1 measured signal*
	Selector – multiple controllers for 1 actuator and 1 measured signal
	Typical applications:
	- Temperature in a reactor
	- Air-fuel control
	![[05207f4a70a22d0b3c8fc72ead27369b4b4b75fcfaf1e23a90e5ae399e342676.png]]
	
	High selector – use the largest value to compute the control action
	Other possibilities: Low selector / Median selector


- **Inferential control**
	When direct measurements are not available *(Y(s) is unknown)*
	Examples:
	- Distillation column – we cannot measure compositions, but we have tray temperatures
	- Dryer – we cannot measure moisture, but we can get temperatures at the inlet and outlet
	![[27824d559b4b0b97cddcd90c7d11aa826b6bef0d2f8ce46d6255312975818a47.png]]
	$Y_S(s)$: secondary measurements
	$Y_P(s)$: primary measurements


# Control implementation
## Deviation variables to actual system
When the set point changes into $y^{new}$, $$y^{new}=y^{ss}+r$$
now $r$ is a deviation from current steady state. 
Also the output is a deviation from steady state, becomes the true outcome:
$$y^{dev}+y^{ss}=y^{true}$$
We want $y^{true}=y^{new}$, but the outcome is $y^{true}$.
Thus $u^{true}$ is also a deviation, in real life we need to add the steady state value $u^{ss}$ for the system process $G(s)$
![[243fdc8c7b1b59e9a27ae225882d420a49ac8e9a85fe37841931564ca908b9db.png]]


## Time-domain control
![[Pasted image 20251016103500.png]]


## Model Predictive Control *(based in time domain)*



# MIMO Control

SISO Control: 
![[57a7e7951d35e7032666b08d9891e5e1b964045af52a8f1d25eb8ea1b6d823bc.png]]
- *Sometimes we can only measure tank3*

## MIMO Control:
![[96d1a7b6a55e8214c5aff8f68672e5ccc57a8e0faa622a3b4ff45ef387730b7b.png]]
- Stability is defined by the eigenvalues of *A* $$det(A-\lambda I)=0$$
	For all i $\lambda_i <0$ --- Stable

>[!Example]
> Let $$A = \begin{bmatrix}
2 & 1 \\
1 & 2
\end{bmatrix}$$
We find the eigenvalues $\lambda$ by solving the characteristic equation:
$$\det(A - \lambda I) = 0$$
$$A - \lambda I = \begin{bmatrix}2 - \lambda & 1 \\1 & 2 - \lambda \end{bmatrix}$$
Then:
$$\det(A - \lambda I) = (2 - \lambda)^2 - 1$$
Solve for $\lambda$:
$$\lambda_1 = 1, \quad \lambda_2 = 3$$
Therefore, the eigenvalues of $A$ are $1$ and $3$.


## MIMO interactions
![[0248ec59a62d3fecda1d71f07c80f5af19397b91d801a414c8acb0128e835418.png]]
- A change in one inflow affects both tanks
- The effects of the two inflows are not symmetric

![[31447d528dc4e7abe1caa7340285353f11a281c26286ed7e91b6222ff03e0423.png]]
- The control systems also interact with each other


## MIMO controller design

![[82afde62b4b9006429c8b1f8f6c0ba37d059131d0c703f0235b29f7ac21ac347.png]]
\*Mind the sequence when multiply!


### MIMO 2x2 system
![[95fd0f52ff997b22af998a1e46011f9b8a8b8f3681dbf20e19355846aaf258bf.png]]

![[e15cc841c4fbd19cb95c487f0ef198704cca0949a76c07a50fd2cb293537b0f4.png]]

![[c0dd5cbd12ee0dd082b6ca2cd373c72dd0d2bebbcf067be4468e17b1a180fbd1.png]]
- **Direct effect**:
	- Impact of $\triangle M_1$ on $Y_1^{ss}$: $$\left(\frac{\partial Y_1^{ss}}{\partial\triangle M_1}\right)_{\triangle M_2=0}=K_{11}$$
- **Indirect effect:**
	- Assuming perfect control $Y_2^{ss}=0$: $$0=K_{21}\triangle M_1+K_{22}\triangle M_2$$
	 and$$\triangle M_2=-\frac{K_{21}}{K_{22}}\triangle M_1$$
	- We get: $$Y_1{ss}=K_{11}\triangle{M_1}-K_{12}\cdot\frac{K_{21}}{K_{22}}\triangle M_1$$
	- Impact of $\triangle M_1$ on $Y_1^{ss}$: $$\left(\frac{\partial Y_1^{ss}}{\partial\triangle M_1}\right)_{\triangle M_2=0}=K_{11}\left(1-\frac{K_{12}K_{21}}{K_{11}K_{22}}\right)$$
- Relative gain between $Y_1^{ss}$ and $\triangle M_1$: $$\lambda_{11}=\frac{\text{open - loop gain}}{\text{closed - loop gain}}=\frac{K_{11}}{K_{11}\left(1-\frac{K_{12}K_{21}}{K_{11}K_{22}}\right)}=\frac{1}{1-\xi}$$
$$\xi=\frac{K_{12}K_{21}}{K_{11}K_{22}}$$
- Doing the same for others: $$\lambda_{12}=\lambda_{21}=-\frac{\xi}{1-\xi},\,\,\lambda_{22}=\lambda_{11}=\frac{1}{1-\xi}$$
![[bc52312ac84d5efb29466cdd775409c9453273cc7b70562f8b8ef91eaa4a4b3f.png]]



## Relative Gain Array (RGA)
---help with assessing the level of interactions
![[7faad04cd7bc984d392645c72e9913a2fc7f647ad2cdaee63cc53ab951fd3a23.png]]
![[4e47419a1a6bc1a6eeb94893cc0b82074ad9c4eb34c276ee01baf3ef6375fcdc.png]]
![[7943ebd4ea709cfe56c92ce7ec8b2c5faa571cb78aca329cba7e54ef79ec0e9d.png]]
![[0f87c225d18ac3c2b08359eb4602413a7cf8e0ae1745fadf07a4db883da081c9.png]]
- Recommendation:  $\lambda_{ij}$ should be **positive** and should close to **1**

- Drawbacks:
	- Developed for **steady state** analysis
	- Useful for **analysis** not design

- Controller design:
	- **Sequential tuning**
		-start with the fastest loop, then continue to the next one
	- **Detuning**
		-design controllers ignoring the interactions, make the controllers more conservative
		1. Tune the controllers individually, obtain controller gains $K_c^*$
		2. Adjust the implemented controller gains:
		![[e8ef0bd5e6ea25a97afed60ec47b49d3cb19d115e49c2a9eee74f9a3c738299e.png]]
	- **Decoupling**
		-treat interactions as disturbances and handle them by using "feedforward"
		-allows treating MIMO systems as multiple SISO systems
	- **Multivariable controllers by design**


## Model Predictive Control (MPC)
![[dc6ae34102171d8821302cc1bab63746e2e76655b2f89809f2dc7eaad1eae020.png]]

- Can handle MIMO systems by default
- Satisfies constraints
- Uses feedback to reach the set-point