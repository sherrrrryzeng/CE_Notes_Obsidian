---
date: 2025-11-24
Prof: Valeria Garbin
aliases:
  - Surface tension and wetting
---
# Surface tension

## Definition and molecular origin
### Definition
From textbook:
	For a liquid exposed to a gas the attractive van der Waals forces between molecules are felt equally by all molecules except those in the interfacial region. This **imbalance** pulls the latter molecules towards the interior of the liquid. The contracting force at the surface is known as the **surface tension**. 
	Since the surface has a tendency to contract spontaneously in order to **minimise** the surface area, droplets of liquid and bubbles of gas tend to adopt a spherical shape: this reduces the total **surface free energy**. 


- Interface between two fluids costs energy. 
- The attractive van der Waals forces between molecules are felt equally by all molecules except those in the interfacial region. 
	*(The energy cost arises from the **imbalance** of molecular forces at the boundary compared to the bulk of the fluids.)*
- The surface tends to contract spontaneously in order to minimize its interfacial area.

### Molecular origin of surface tension
In Liquid/Vapour Interface:
- **Cohesive** forces towards the liquid bulk are not balanced. 
- The molecules are attracted inwards.
- The molecules have **higher free energy**. 

In Bulk liquid:
- **Cohesive** forces are balanced in all directions. (equilibrium)
- The molecules do not experience any net force.
- The molecules have **lower free energy**


## Surface tension as a force, energy, or pressure
### Energy
![[ea48d4c49f4ec0a735a5a2216666c06b816ff40a950a363669af5149cc543312.png]]
-> Surface tension as change in free **energy** (per unit area): $$dW=dE=\gamma dA$$ $\gamma$ : surface tension $[J/m^2]$


### Force
Pull the rod to the right by a distance dx: $$dW=2F_\gamma dx$$Why times 2: **2 interfaces** (air-liquid-air)
$$dE=\gamma dA=2\gamma Ldx$$ -> Surface tension as a **force** (per unit length): $$F_\gamma=\gamma L$$
### Pressure
From Laplace pressure, the pressure across a curved interface can be described as: $$\triangle p=\gamma\left(\frac{1}{R}+\frac{1}{R'}\right)$$*R': in curves the radius could be different in different directions* 
For a sphere $R=R'$ -> Surface tension as a **pressure**: $$\triangle p=\frac{2\gamma}{R}$$
## Measurement methods
Surface tension of common liquids![[21318e620ffb93721f4d4a26d0a6ea368598c97a7a5da5bcf7d08330ffccc5a3.png]]
- The **unit** for surface tension is usually: mN/m
- **Solvents** tend to exhibit polar interactions and higher surface tension


### Wilhelmy plate method
![[a125080959d36931814902a290a4c2bc2a6b0e607b61025a065b0473352125a9.png]]
$$\gamma=\frac{F}{L\cos\theta}$$

### Pendant drop method
![[b4a24cff46f6520de82316a1a6bffd81d00149267dcc48553f7c93ab3561426c.png]]
Bond number describe the shape: $$Bo=\frac{\text{gravity}}{\text{force dut to }\gamma}=\frac{\triangle\rho gR^3}{\gamma R}=\frac{\triangle\rho gR^2}{\gamma}$$

# Wetting phenomena

![[59e182498a75cf7192284b2f3cff9e96d8080ffa3f37d29cd872baffd0dec894.png]]

In mechanical equilibrium through energy minimization: $$dE=0$$ *<- solve numerically*
 If other energies (e.g. gravitational) play a role, they can be added to the expression for the free energy. 


## Contact angle (equilibrium, advancing, receding)
![[c753e5cb7062360e953f15686529801b1ddb5ed09f16e51ca58c56f22be4e515.png]]
Mechanical equilibrium: $$\gamma_{al}\cos\theta=\gamma_{sa}-\gamma_{sl}$$
**Young's equation** (thermal dynamic property): $$\cos\theta=\frac{\gamma_{sa}-\gamma_{sl}}{\gamma_{al}}$$
Typically: large air-liquid surface tension -> large $\theta$

More specifically:
   **Wetting of a solid by a liquid**
![[c5bd42877bc87dbea6bfa9c16a2a0b64b88bb22d5d5de1f719a4d710c8fd20d8.png]]

Capillary bridge:![[1247426b90d690b43279f7375d697fe80a885c6b8b3615bdd270883c5fb5b199.png]]


### Advancing and receding contact angle
Rain drops can stick to windows
-> Equilibrium contact angle (thermodynamic property) is not the full story
![[353118ca694767d9f0d3a268763b8739ab22f459ff2e8f44b3892ff2a0c66afb.png]]

**Pinning of the contact line**: 
	the drop tends to change the contact angle first before changing the contact line. (Contact line gets stuck)

**Contact angle hysteresis**:$$\triangle\theta=\theta_A-\theta_R\sim15-20°$$
Force (per unit length) needed to make a drop slide over a solid surface: $$f=\frac{\gamma_{al}(\cos\theta_R-\cos\theta_A)}{2}$$
### Effect of surface roughness
![[737ac63f65f9a73bfbad6244828f77053ba6fef25f7ac7584b2dc8ef890c727a.png]]
Not Young's contact angle
Drop in Wenzel state:
![[95757fb33695610716935fd4997fc543a5633de8c1c3b0837e6b7b2822890653.png]]
-> **Apparent contact angle $\theta_W^*$ - Wenzel Equation**:$$\cos\theta_W^*=R_W\cos\theta$$ $R_W$: roughness factor $$R_W=\frac{A_{true}}{A_{apparent}}$$
### Effect of chemical heterogeneity
The structure of leaves
![[ea755ccffd038dd55a23539df136c764bbdf62a04e2abba08553cf0c00f3e270.png]]
Drop in Cassie-Baxter state:
![[78229b416689c03ab7ab24ec3a2628855a06ec93e919fa162e5f35b9c477072b.png]]
**Different Young's contact angles -> Cassie-Baxter Equation**: $$\cos\theta^*_{CB}=f_1\cos\theta_1+f_2\cos\theta_2$$ $f_i$: surface fractions $$f_1=1-f_2$$
