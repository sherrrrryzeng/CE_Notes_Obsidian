---
date: 2025-12-15
Prof: Emma Hinderink
aliases:
  - Introduction of Emulsions
---
\* All **surfactant**s are capable of reducing interfacial tension, only those that can form a stable and robust interfacial film are classified as **emulsifier**s.*(not all surfactants are emulsifiers, but all emulsifiers are surfactants)*

# How are emulsions formed?

**Emulsions**: Two **==immiscible liquids==** in which one is dispersed in the other as droplets. -> Interface-dominated system

## Classification
- O/W (oil in water) Emulsion
- W/O (water in oil) Emulsion

*Example: in O/W emulsion*
*Oil - dispersed/inner phase*
*Water - continuous/outer phase*


Whether emulsion is oil-in-water or water-in-oil:
- **volume ratio** of inner/outer phases
- **viscosity ratio** of the two phases 
  (phase of higher viscosity is typically continuous phase)
- type and concentration of **emulsifier**


## Mayonnaise
Mayonnaise contains up to 80% oil - BUT **O/W**
Egg yolks contain water and proteins
**Proteins** act as surfactants to stabilize the emulsion
![[c2b33751e715414fa6e72710cf214d84e0a8ffbcb662b2b40062b0203967cead.png]]


## Emulsification
**Energy**:
	Emulsification Increases a lot of interfaces 
	-> high energy cost

**Transparency**: 
	Droplets smaller than wavelength of the light -> transparent

**Emulsification process**:
- **Dynamic** process
	 droplets are formed and de-formed, collide, break-up, coalesce(merge into larger droplets)
	 In most cases emulsification is not spontaneous.
	
- Thermodynamics
	 Change in **Gibbs free energy**$$\triangle G_d\sim \gamma\triangle A$$ ($dE=dW=\gamma dA$)
	 $\gamma$ is interfacial tension;
	 $A$ is increase in the interfacial area.

The smaller the droplets, the larger the surface:volume ratio, the larger energy cost.
In most cases energy input is required for emulsification


### Fluid flow/mixing
 Reynolds number $$Re=\frac{\rho vL}{\eta_0}$$
  - Laminar regime: Re<2500 -> **even droplets**
  - Turbulent regime: Re>2500 -> **uneven droplets** ![[e47b0bb85fb961523152207ad2c37cd7f4638b7e98124931c8eda478649caa63.png]]


**In Laminar Flow** (Shear flow) - **==Weber Number==**
$$We=\frac{\eta_0\varepsilon R_d}{2\gamma}=\frac{\text{External forces}}{\text{Interfacial forces}}$$
$\varepsilon$ is shear rate \[/s]
![[99622518b334a693289648dc9c9233e31669db8d9bd313e0b8c266e5348d1584.png]]
Droplets deform due to the flow field and eventually break-up. 
*\* Note: deformation increases the surface area, so a sufficient amount of energy is needed for this.* 

**For droplet break-up to occur**: $$We>We_{cr}$$ 
Effect of viscosity ratio: $\frac{\eta_i}{\eta_0}$ 
![[7a37325a55c55104afd2e24e6a9d847eda551f9b193f63674ea597d4b9918505.png]]

In **extensional flow** droplets keep rotating and have lower $We_{cr}$ 
-> easier to break up
-> more effective at disrupting droplets

The effect of **surfactant**:
- reduce interface tension
- provide physical stabilisation

The effect of the amount of surfactant: 
![[844fc8c927c374f69ae19c248a1ddff4973d5765ae1b06d4a8e1e94bb915e111.png]]

If we want smaller droplets with the same amount of surfactant:
==**Increase pressure**==
-> More energy in the system


# What determines their macroscopic properties?

## Rheology
![[94d49d4eee38a21f3da73a1494aa46e605771f3fe9e3bb6522c839707cc980e6.png]]

**Volume fraction $\phi$** :$$\phi=\frac{\text{volume of the inner phase}}{\text{volume of the outer phase}}$$
**For dilute emulsions** ($\phi<5\%$):
   droplets are spheres. Assuming rigid spheres, **==Einstein law==**: $$\eta=\eta_0(1+\frac{5}{2}\phi)>\eta_0$$ where $\eta_0$ is viscosity of the pure outer phase material.

**For non-dilute emulsions: ==Krieger Dougherty==**
$$\eta=\eta_0(1-\frac{\phi}{\phi_m})^{-[\eta]\phi_m}$$  where $\phi_m$ is the **maximum volume fraction** *(experimenal data)*
 dependent on droplet-interactions, deformability, polydispersity
 ![[a4a11a319ae9c811b8900416128d0a8c3775b4f5273be6c7240a54639b71ac6f.png]]

If **Polydispersity** increases, $\phi_m$ increases. 
*(More space contained)*
![[8e8a6c96097d059e8c893d736772efec999a39cdcd1b50ab86626101147fd450.png]]

**Concentrated emulsions exhibit non-Newtonian rheological behaviours**  *e.g., yield stress and shear thinning.*

Viscosity depends on:
- volume fraction $\phi$
- viscosities of inner/outer phase
- droplet size
- droplet deformability
- nature of droplet-droplet interactions


*At certain volume fraction the **phase inversion** happens -
the inner and outer phase exchange
viscosity drops immediately, and then increase*


# How are they stabilized?
## Effect of surfactant type
Type of emulsion (O/W or W/O) is also determined by type of surfactant used

**Bancroft rule** (a rule of thumb): 
    phase in which the emulsifier is more soluble becomes a continuous phase. 

**Hydrophilic-lipophilic balance (HLB)**:
- HLB<5: no dispersibility in water
- low HLB: W/O emulsion
- high HLB: O/W emulsion
- HLB>15: clear solution

![[ae01e278a310f9603e07733a01864545916d0024972ecb3a6bb475e8ec0d658c.png]]
*The hydrophilic part of Tween is relatively larger than the tail part. So it prefers to go to the water phase, which makes the water phase the continuous(outer) phase -> O/W*

![[5478607d256e4cb5c735b9335b2db7c262a3a37903cf633336bf456342f7f22f.png]]


## Interface stabilization
![[3e2d43c7cd218b899a2b0c39ec5e23eca09a16336c85353e7bce783f28955972.png]]

1. **Low molecular weight(LMW) surfactant**
	<- Adding surfactant lower **surface tension** of liquid
	*Gibbs adsorption equation: $$\Gamma=-\frac{1}{RT}\frac{d\gamma}{d\ln c}$$* After CMC surface tension doesn't decrease much anymore
	
2. **Charged LMW surfactants** 
	Reduce interfacial tension
	Provide electrostatic repulsion
	
3. **Flexible polymers**
	Reduce interfacial tension
	Provide steric repulsion
	
4. **Pickering particle**
	Macroscopic physical barrier
	high adsorption energy
	insoluble - mechanical stiffness


## Long term stability
Emulsions are generally unstable:
- due to flocculation of droplets
- due to creaming / sedimentation
- followed by coalescence → detrimental
![[a27825fcf179178a086fa71c325055c84b8a5c08123bbbb10a7cddf71cd2380a.png]]

![[4476434f90ac5a7804fa5472447c5adb39419d4d02707d14bee8fc4c74569cdb.png]]

First decreases (0 → Optimum):
1. **Surface Tension:** adding surfactants lower the surface tension, making it mechanically easier to break large droplets into smaller ones during shearing.
2. **Surface Coverage:** More surfactant molecules are available to quickly coat newly formed interfaces, providing a protective barrier (electrostatic or steric) that prevents immediate coalescence (re-merging).    

Then Increases (Past the Optimum):
1. **Flocculation:** Excess surfactant forms **==micelles==** in the continuous phase. Micelles act like non-adsorbing polymers and causes **==depletion==** flocculation *(create osmotic pressure imbalance that forces droplets to clump together)*.
2. **Increased Viscosity:** Very high surfactant levels thicken the continuous phase. 
   - This reduces the efficiency of the mixing energy (shear stress) reaching the droplets, making them harder to break. 
   - Viscosity also affects sedimentation velocity ($v_s$), which might lead to **==creaming==**.  


### Pickering emulsions
![[02ae6b591290a9454749f627ac801b0f608bc15c1eca8a6d20a2f5ccd9913543.png]]

![[233153ae463cc0cf25586d4d42e12da04bc6f43b6371c3eab4d58fd67cfd02b5.png]]

because of the mechanical stiffness of the interface
The particles are in 8-shape and are **stable**


**Helmoltz free energy**: $$\triangle E=\pi a^2\gamma(1-|\cos\theta|)^2$$
Stable mechanisms:
- **large desorption energy** $\sim 10^2-10^6 k_BT$     
   *much larger than thermal energy of solvent particles*
- **Interfacial microstructure**    *e.g., jamming*
   *- local deformation of the interface induces **capillary interactions** -> rigidity, mechanical strength* 
   *- **particle network** in the continuous phase*


