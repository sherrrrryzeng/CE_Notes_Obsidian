---
date: 2025-12-16
Prof: Atsushi Urakawa
aliases:
  - Catalytic Reactions
---
Mass transport (diffusion) using solid catalysts in reactor

# Catalyst
## Different catalyst shapes
Common Shaping Methods - Extrusion ![[e79f1a7151f7227f35dbf0e59227e7af13cb8e6229eb64a384f18a0d04c7a40f.png]]

Structured catalyst - monolith
- metal
- ceramic![[406e1463fc5558e0dc61fe78464f7a4cacd03e927370f34636bd08f978ea24e5.png]]
with coating part - **washcoat**


## Observed reaction rate
The observed reaction rate is not the intrinsic reaction rate calculated from Hougen-Watson kinetics(LHHW kinetics) $$r=\frac{k\cdot K_ip_i}{(1+\sum K_ip_i)^N}$$$$r^{obs}=\eta \,r^{intrinsic}$$ $\eta$ is the **effectiveness factor**. 
It should take into account every factor **(internal, external transfer limitations, porosity, pore structure, etc.)**


Physicochemical events inside and outside of catalyst:
- film diffusion
- pore diffusion
$$r^{obs}=\eta_i \eta_e \,r^{intrinsic}$$


# Internal and External Mass Transfer

- **Self diffusion**
	 No net transport (no concentration gradient)
- **Transport diffusion** 
	 Concentration-gradient driven diffusion with a net transport of mass in gas/liquid/solid
	 *\* What we need to discuss*

Mean free path (gas phase): $$\lambda=\frac{k_BT}{\sqrt{2}\pi\sigma^2P}$$ $\sigma$ is the kinetic diameter.


## Pore diffusion
Average pore radius: $$r_a=\frac{2V_{pore}}{S_g}$$$V_{pore}$ is pore volume; $S_g$ is surface area.
![[7e93cc3631c4fb0fcf2fab39dbcc0ef841adf84dfcd8fd78f8f3ae09947c40e1.png]]


### Molecular diffusion
When the mean free path is much smaller than pole radius
-> **Molecular diffusion** -> Diffusion coefficient is constant
- gas ![[09d37b7d5877861bd9cab6948f1c17eb6f5a6359716a7348b3c7500a19a0733d.png]]
- liquid ![[f87c5a2c48afb450268ef0c980c29d4de458ec59252b13c83a3f061b4bcced7f.png]]


### Knudsen diffusion
When the mean free path is smaller than pole radius *(not much)*
-> **Knudsen diffusion** -> D changes
- gas ![[3d1d3528980dbe2602418a3c754bd7e0d6ce364034323a6599900d1ebb5fb811.png]]

In between Molecular and Knudsen diffusion: ![[11a5df1414e9e7c1c24d9011cc9adf62c03e0bdc0501394edbb1ac4ac28b538c.png]]

### Single file diffusion
When the mean free path is around the same size
-> **Single file diffusion** 
-> pores are too small to allow molecules to pass

When the mean free path is larger than the pole radius
-> very small pore openings reject molecules


BUT:
The diffusivity calculated above is OK for the **microscopic** scale, but not for the macroscopic scale (e.g. whole catalyst sphere).


## Effective diffusivity
![[b590dbe5d8daae3be2b13c82580bd886a8ec640fc8a19e9ae51d31550eb88bbf.png]]
Effective diffusivity $$D_{eff,i}=\frac{\epsilon}{\tau}D_i$$ $\epsilon$ : Porosity $[m^3_{void}\,m^{-3}_{total}]$
$\tau$ : Tortuosity $[-]$

With porosity and tortuosity the diffusivity is significantly lower!


## External mass transfer
Fick's first law $$J_i=-D_i\frac{dC_i}{dz}\,\,[mol\cdot cm^{-2}s^{-1}]$$Fick's law says the concentration profile is linear
![[9069c8314ae3f0eb368798c92897422b8af38deff928f5bd3562e1718a9c0dcf.png]]


**External Effectiveness Factor** $$\eta_e=\frac{\text{rate at external surface condition}}{\text{rate at bulk fluid condition}}=\frac{r_V(C_s,T_s)V_p}{r_V(C_b,T_b)V_p}$$ $r_V$ : reaction rate per unit particle volume

**Internal Effectiveness Factor** $$\eta_i=\frac{\text{observed rate}}{\text{rate at external surface condition}}=\frac{\int_0^{C_p}r_V(C,T)dV}{r_V(C_s,T_s)V_p}$$ ![[77dd19eb2a20be6741011d6d73e19c27db99010488f6f122bf2f4feb56ce8325.png]]

Diffusion Effectiveness Factor $$\eta=\frac{\text{observed rate}}{\text{rate at bulk fluid condition}}=\eta_i\eta_e$$

External mass transfer flux: $$r_V(C_s,T_s)V_p=A_pk_m(C_b-C_s)$$ $k_m$ : mass transfer coefficient $[m/s]$ $$k_m=\frac{D}{\delta}$$ $A_p$ : External catalyst surface area

Rearrange, ![[b57bf0f7e1b42d024da25873358a197595733130b3128654369d029d5930b8a1.png]]

Dimensionless numbers![[6050b89a710b14a90808aa1b0959d9faa8114d2cf1b358e04ebb46cefeb4b0a9.png]]

Mass transfer coefficient $k_m$:
![[1cb4881553003fc2735be8b9df24e90e3e3edfc7b994435cc8012fc717ead223.png]]
$u$ : velocity of the fluid
$d_p$ : diameter of the particle


### Outer surface reaction
![[d0794eac311721f547bb5236dfcd7dd6806b8f4ed0e6607108600ca772777423.png]]
No pole inside Pt wire
Reaction happens on the surface

Analysis: 
- green curve - Hougen-Watson kinetics (reaction)
- red curve - supply rate slope (mass transport)
- cross-points : possible solutions for equilibrium
	 **Stable** - the first and third one
	 **Desired** - the first one
		- low $c_s$ (surface concentration)
		- high $r$ (reaction rate)
