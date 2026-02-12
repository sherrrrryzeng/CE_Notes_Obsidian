---
date: 2025-11-18
Prof: Jose Palomo Jimenez
aliases:
  - Material Balance
---
 # Mass (mole) Balances for Chemical Reactors
Assumptions:
- Isothermal operation
- Ideal reactor behaviour & no pressure drops

## Mass & mole balances
Common form of mass balance or continuity equation:$$\frac{dm}{dt}=\varphi_{m,in}-\varphi_{m,out}+generation$$$$\frac{\partial\rho}{\partial t}+\nabla(\rho\mathbf{u})=0$$ where $\rho$ is mass density; $\mathbf{u}$ is velocity. 

For component i: $$\frac{\partial\rho Y_i}{\partial t}+\nabla(\rho\mathbf{u}_iY_i)=\omega_i$$
![[9e8da9868ce2274e16579f4c7895e964e517af6dfc6da210c3bc8639e983ce4a.png]]

Mole balance: $$\frac{\partial N_i}{\partial t}=F_{i,in}-F_{i,out}+\int_Vv_ir\,dV$$

## Ideal Reactors (isothermal)
### Batch Reactor
![[02a17c0b43f004bf81050331754cf884c443e5cbcb0d512f38d9f54f001ef1b7.png]]
*\* $v_i$ is the reaction coefficient*
$$\frac{dN_A}{dt}=0-0+\int_0^VR_AdV=R_AV$$$$\frac{dC_A}{dt}=R_A$$
Expressed with $X_A$: $$X_A=\frac{N_{A0}-N_A}{N_{A0}}=\frac{C_{A0}-C_A}{C_{A0}}$$ $$R_AV=\frac{dN_A}{dt},\,\,R_AV=-\frac{N_{A0}dX_A}{dt}$$ $$R_A=\frac{dC_A}{dt},\,\,R_A=-\frac{C_{A0}dX_A}{dt}$$
### CSTR
![[640518018746e6ea62cbcee48b37728190fbc4ac5dccb20c0df30bb996efe2e4.png]]

Steady state conditions:$$F_{A,0}-F_A=F_{A,0}X_A=-R_AV$$ $F_A=v_0C_A$, $v_0$ is the volumetric flow rate: $$C_{A,0}-C_A=C_{A,0}X_A=-R_A\frac{V}{v_0}$$
**Space time**: time required to process one reactor volume of feed $$\tau=\frac{1}s{}=\frac{V}{v_0}$$**Space velocity**: $$s=\frac{1}{\tau}$$
### PFR
![[e6d757f2a53e5ec0ab0f6e038d4a8656f5071ebf1f4872e67eb28dd8b2802869.png]]
$$\frac{dN_A}{dt}=F_{A|l}-F_{A|l+\triangle l}+R_AA\triangle l$$
Steady state condition: $$\frac{F_{A|l+\triangle l}-F_{A|l}}{A\triangle l}=R_A$$$\triangle l\to 0$:![[5ae44a3a87334d58b1bf758bcf268245ada07e3af6a311b07c56b9bc28c6403b.png]]



