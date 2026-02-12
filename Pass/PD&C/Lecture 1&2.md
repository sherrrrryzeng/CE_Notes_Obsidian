---
date: 2025-09-02
Prof: Dr.ir. Farzad Mousazadeh & Dr.ir Marta Zagorowska
Email: " CH3044A-PDC-TNW@tudelft.nl"
aliases:
  - "Chapter 1: Introduction of Process"
---
# Module 1: Not important
### Batch mode
- never be in steady state
- control includes automation of a recipe
- flexible & low capital cost
- lower safety & lower efficient

### Continuous mode
- can be in steady state(s)
- control includes maintaining operating points
- high efficiency & high safety
- not flexible & high capital cost

**Choosing:** raw materials - base chemicals - intermediates - final products

### Why control?: 
- ensure **quality & quantity** of conversion
- ensure to operate within **operational (limits)**  \*important
- **constraints** ensure economical operation

A hard operational constraint: ==SAFETY==
1. inherent safety measures
2. safety relief valves (SRVs)
3. instrument protective functions (IPFs)
BUT: safety system is completely different from control system
---


# Module 2: Modelling 
--- Procedure of Dynamic Modelling
## Modelling Flow Chart
1 Define objectives
- purpose of the model
- required accuracy
2 Prepare information
- sketch process
- determine system boundary
- identify variables of interest
- state assumptions   **(be careful)**
3 Formulate model
- conservation laws
- constitutive equations
- DOF's (degree of freedom)
4 Determine solution
- analytical
- numerical
5 Analyse results
- results correct?
- interpret the results
6 Validate model
- Select key variables
- compare with experiment
---

### Balance as
Rate of Change =  In - Out + Source - Sink = In - Out + Net Production
in Mass / Energy(Heat) / ~~Momentum~~ (not considered in ChemE)
Flow assumption: Ideal mixing, Plug flow, etc. 

Important terms: Rate of Change / Accumulation terms
$$\frac{d(\rho V)}{dt} , \frac{d(VC_A)}{dt} , \frac{d(V\rho\int c_pdT)}{dt}$$
**Mind the units**:
$V$: $m^3$
$\rho$: $kg/m^3$
$C_A$: $mol/m^3$
$C_p$: $J/kg \cdot °C$

---
Constitutive Equations:
- not universally applicable
- sufficiently accurate

A few examples:
- Reaction rate: $$-r_A=k_0e^{(-E/RT)}C_A$$
- Heat transfer rate: $$Q=hA\triangle T$$
- Equation of State: $$PV=nRT$$
- Fick's First Law of Diffusion: $$J_A = -D_{AB} \, \frac{\partial C_A}{\partial x}$$
- Fick's Second Law of Diffusion: $$\frac{\partial C_A}{\partial t} = D_{AB} \, \frac{\partial^2 C_A}{\partial x^2}$$
- Fourier's Law of Heat Conduction:$$q = -k \, \frac{\partial T}{\partial x}$$
--- 

## Step123: Formulate model
### Example1: Constant Stirred Tank Reactor(CSTR)
#Background_Knowledge
For a general chemical reaction:
$$aA+bB -> cC+dD$$
reaction rate:$$-r_A=kC^m_AC^n_B$$where:
- k: rate constant
- m: reaction order with respect to A
- n: reaction order with respect to B

Arrhenius Equation:$$K=k_0e^{(\frac{-E_A}{RT})}$$

Balance equations:
$$Accumulation=In-Out+Net production$$
- **Mass Balance:$$\frac{d(\rho V)}{dt}=\rho\phi_{in}-\rho\phi_{out}$$Component Mass Balance(A):**$$\frac{d(VC_A)}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A,out}+rate*V, rate=(\alpha C_A)$$
- **Energy:**$$\frac{d(\rho VC_pT)}{dt}=\phi_{in}\rho C_pT-\phi_{out}\rho C_pT_{out}+Q_{q,loss}$$
---
#CSTR Case 1
Step1: Model purpose
Step2: Sketch Process & Assumptions
- ideally mixed
- density is constant
- first order reaction
- reaction heat is negligible
Step3: Formulate model
**Mass balance:**$$\frac{d(\rho V)}{dt}=\rho\phi_{in}-\rho\phi_{out}=\rho(\phi_{in}-\phi_{out})=0$$
$$\phi_{in}=\phi_{out}=\phi$$
**Component mass balance:**$$\frac{d(VC_A)}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A,out}-VkC_A$$$$C_A\frac{dV}{dt}+V\frac{dC_A}{dt}=0+V\frac{dC_A}{dt}$$$$\frac{dC_A}{dt}=\frac{\phi_{in}}{V}C_{A,in}-\frac{\phi_{out}}{V}C_{A}-kC_A$$

---


#CSTR: Case 2 - Volume of liquid in the tank is not constant

density is still a constant --**Mass balance:**$$\frac{d(\rho V)}{dt}=\rho\frac{dV}{dt}=\rho(\phi_{in}-\phi_{out})$$$$\frac{dV}{dt}=\phi_{in}-\phi_{out}$$
**Component mass balance:**$$\frac{d(VC_A)}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A}-VkC_A$$$$C_A\frac{dV}{dt}+V\frac{dC_A}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A}-VkC_A$$$$C_A(\phi_{in}-\phi_{out})+V\frac{dC_A}{dt}=\phi_{in}C_{A,in}-\phi_{out}C_{A}-VkC_A$$
$$V\frac{dC_A}{dt}=\phi_{in}(C_{A,in}-C_A)-VkC_A$$

### Example2: Distillation Column
#Background_Knowledge 
Vapor-Liquid Equilibrium (Antonie Equation):$$lnP_L^0=\frac{b}{c+T}+a$$
x: mol fraction in liquid phase
y: mol fraction in gas phase
![[e7885d02b331013a9c564ae7cb43cda3995bc53d5bb2eec31ea7a90facfec774.png]]
![[55058775d6ecedc451c0fa5c1eb7a2e290157892a8dfbeeb88b7cc36b0250827.png]]

Raoult's Law (Liquid):
$$P_l=x_lP^0_l$$
$$P_m+P_e=P=x_mP^0_m+(1-x_m)P^0_e$$
$$x_m=\frac{P-P^0_e}{P^0_m-P^0_e}$$
- P: total pressure
- $P_l$: partial pressure of component $l$ in gas mixture above the solution
- $P^0_l$: equilibrium vapor pressure of the pure component $l$


Dalton's Law (Gas):
$$P_l=y_lP$$
->$$y_mP=x_mP^0_m$$
Relative Volatility: (usually T up, $\alpha$ down)
$$\alpha=\frac{\frac{vapor mole fraction of lighter component}{liquid mole fraction of lighter component}}{\frac{vapor mole fraction of heavier component}{liquid mole fraction of heavier component}}=\frac{\frac{y_m}{x_m}}{\frac{y_e}{x_e}}=\frac{\frac{\frac{x_mP^0_m}{P}}{x_m}}{\frac{\frac{x_eP^0_e}{P}}{x_e}}=\frac{P^0_m}{P^0_e}$$
$$P^0_m=\alpha P^0_e$$
![[bc3ec515e8334b23372130a39934f7c5d93fd8c24ce43da13f4c9d7ac5e966a7.png]]

---

#DC Case 1
60°C & 1 bar --- 0.50 mol MeOH + 0.50 mol EtOH
**61°C** & 1 bar --- 0,424 mol MeOH + 0,376 mol EtOH + 0,076 mol MeOH +0,124 EtOH

Step1: Model purpose
Step2: Sketch Process & Assumptions
- vapor phase can be neglected ($\rho_{liq}>>\rho_{gas}$)
- trays are well-mixed
- outgoing flows are in Thermodynamic equilibrium ($\alpha$ is constant)
- liquid molar hold-up is constant
- liquid and vapor molar flows are constant
Step3: Formulate the Model
- only write the mol fractions for Methanol
- x in liquid phase & y in vapor phase

Step4: Sketch
![[580543eca582b13b1c25e44d4ab9be1a6d74dd246b02f71cff4e6896e65063a5.png]]

Step5: Balance
- **Mass balance:** (M is molar holdup)
$VE_{10}$: $0=\frac{d(M_{10})}{dt}=V_9-L_{10}-D$         (IN)
$VE_{n}$: $0=V_{n-1}+L_{n+1}-V_{n}-L_{n}$
$VE_{5}$: $0=V_4-L_6-V_5-L_5+F$         (FEED)
$VE_{m}$: $0=V_{m-1}+L_{m+1}-V_{m}-L_{m}$
$VE_{1}$: $0=V_2-V_{1}-B$                            (OUT)

- **Component mass balance**: 
$VE_{10}$: $\frac{d(M_{10}x_{10})}{dt}=M_{10}\frac{dx_{10}}{dt}=V_9y_9-L_{10}x_{10}-Dx_{D}$
$VE_{n}$: $\frac{d(M_{n}x_{n})}{dt}=V_{n-1}y_{n-1}+L_{n+1}x_{n+1}-V_{n}y_{n}-L_{n}x_{n}$
$VE_{5}$: $\frac{d(M_{5}x_{5})}{dt}=V_{4}y_{4}+L_{6}x_{6}-V_{5}y_{5}-L_{5}x_5+FZ_F$
$VE_{m}$: $\frac{d(M_{m}x_{m})}{dt}=V_{m-1}y_{m-1}+L_{m+1}x_{m+1}-V_{m}y_{m}-L_{m}x_{m}$
$VE_{1}$: $\frac{d(M_{5}x_{5})}{dt}=L_{2}x_{2}-V_{1}y_{1}-Bx_B$
