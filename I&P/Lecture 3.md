---
date: 2025-11-17
Prof: Valeria Garbin
aliases:
  - Colloidal Interactions & Stability
---
(Particle-particle interactions)
# Definition of Colloids

Consider the Brownian motion of colloids
- **Brownian particles** (e.g.,colloids) ~ $10^{-7} - 10^{-4}\,\,m$ 
- Solvent molecules (e.g., water, oil) ~ $0.1 - 1\,\,nm=10^{-10}-10^{-9}\,\,m$ 

1. Solvent molecules undergo constant thermal motion: kinetic energy ~  $k_BT$ 
2. Collisions of solvent molecules with colloidal particles transfer kinetic energy
3. At given time, net force on Brownian particle is non-zero - **fluctuating force**; *the average of fluctuating force over time, or over all particles, is zero*. 

## Diffusion vs. Sedimentation
**Peclet number**: $$Pe=\frac{\text{sedimentation rate}}{\text{diffusion rate}}=\frac{v_s\alpha}{D}$$
- $\alpha$ : characteristic length (= the radius of the particle)
- $v_s$ : **sedimentation velocity** (terminal velocity)$$v_s=\frac{2\alpha^2(\rho_p-\rho_f)g}{9\eta}$$From Stokes-Einstein equation we have diffusion coefficient: $$D=\frac{k_BT}{6\pi\eta\alpha}$$Thus, $$Pe=\frac{4\pi\alpha^4(\rho_p-\rho_f)g}{3k_BT}$$
- $Pe>>1$: colloid will sediment
- $Pe<<1$: colloid remains suspended


# Particle-particle Interactions in colloids
![[fda4113c54072319a1495615cdff456f1180772116e64a3204adaf7e1f1bb712.png]]
**Dispersed state is UNSTABLE against aggregation.** 
*-Dispersed systems contains a lot of interfaces*
*-The interfaces cause the instability*
The Gibbs free energy: 
![[e6f2693d433d4999c00c6e90efac0b9c7fff7e93ef61b9cfd449a87bb318bfab.png]]
A kinetic barrier can prevent aggregation
![[fb5e0d4aed3e1c5da0a1ec09d425fb896968f6774f009a7bdc6df73bad4decc8.png]]
\* $x$ is the separation between interfaces

*No uniform definition*
**Stable** colloidal dispersion: 
	A colloidal dispersion is, by definition, thermodynamically unstable, because the configuration with the lowest free energy is reached when all the particles are aggregated. 
	When a colloidal dispersion is referred as stable, we refer to its **kinetic** stability, obtained by providing an ==energy barrier== sufficiently large with respect to the thermal energy of the solvent particles($k_BT$). 


## Attractive Interactions - van der Waals
![[845190147821e9c11b09e59bd473ddca08c99fce7ea90282b473a47280945baf.png]]
*will not be in exercises*

### Atomic/Molecular Origin of van der Waals
- Interactions between dipoles:
	1. Keesom (permanent-permanent dipoles)
	2. Debye (permanent-induced)
	3. London (fluctuating-induced)
-> Conclusion: **Every atom/molecule has vdW forces**


## Repulsive Interactions
### Electrostatic repulsion
Surfaces and interfaces in polar solvent acquire a surface charge
-> **Debye length** $$\lambda_D=\sqrt\frac{D\epsilon}{\sigma}$$
![[bd0899fadaa559a82cb363fdaddb3519a7b28d60dc0571c9d68f982ecd6c6556.png]]

**Double layer mediates inter-particle interaction**![[bf0210bab465c2127a1d9e9a3db865a6ccec188dc7dee8d5674d6c3d81c85e80.png]]
- In the overlap region of the two double layers, there is a locally higher concentration of ions.
- This results in an **osmotic pressure** (a concentration effect). 
- Electrical double-layer repulsion is NOT the same as the electrostatic repulsion. 


**DLVO Theory**: 
Combining vdW attraction and repulsion, we have 
![[11a8bb4ddee8e94ce10f7e8071935e8a42e661c0d19c7eec687f58cd0438bea8.png]]
*The equation is just a simple illustration, not very exact*

### Steric repulsion
**Brush configurations** create bumpy areas, making the distance between the particles larger. 
![[c4f231b19a203df6e7a9ad35c3902b99aaef36c5ace584b59c3b68caf046fa29.png]]
- It is a short-range repulsion that can be tuned by the thickness of the brush.
- It is too weak to give a kinetic barrier alone. 


Summary of particle interactions in colloids:

Attraction:
- **van der Waals** *(every atom/molecule)*
Repulsion:
- **Electrostatic**
- **Osmotic** *(salt)*
- **Steric** *(polymers)*

The effect of double layer (Stern layer & Debye layer):
- **screening** -> electrostatic (-)
- higher electrolyte concentration -> **osmotic** (+)

Summary:
The **Double Layer** originates from a particle's surface charge attracting a cloud of counter-ions. In DLVO theory, when these layers overlap, they provide colloidal stability through two coupled mechanisms: the **electrostatic** effect (Coulombic repulsion between surfaces) and the **osmotic** effect (pressure gradient from ion accumulation in the overlap zone). The double layer also creates a **screening** effect that causes the **electrostatic** potential to decay exponentially with distance. 



## Adding polymers in colloids
![[42cfb9562ca7d07dbc932f1524069e376ca8b018c27621e3ed236ccec4d741de.png]]
- Adsorbing polymers - **Bridging flocculation**
- Non-adsorbing polymers - **depletion**

### Depletion Interactions
The non-adsorbing polymers are called **Depletant**, with a radius of $R_g$. 
The **osmotic pressure** of a colloidal dispersion: $$Π=nk_BT$$When the surface distance is $h$, the depletion potential is: $$W_{dep}(h)=-Π\triangle V,\,\,0\leq h\leq R_g$$ The change in excluded volume is: $$\triangle V(h)=\frac{\pi}{6}(2R_g-h)^2(3R_c+2R_g+\frac{h}{2})$$ ![[f10ce3c7b92a9ad8ce830d8d13d982f3ab023111669c7da7a9556dde8322ea42.png]]


## Colloidal Stability
Double-layer repulsion: effect of electrolyte concentration
![[f9689a267d253f67ea6d97ef60ef836775c2937983a0ba915868edf83d0a6782.png]]

How to destabilize colloids: **add salt**
	Salt releases ions (e.g., Na⁺, Cl⁻) into the solution. These ions gather around the charged particle surfaces and neutralize or screen the charges. 
	-> Debye length decreases -> repulsion decreases -> aggregation

Add polymers:
- Adsorbing polymers - **Bridging flocculation**
- Non-adsorbing polymers - **depletion**
Add salt:
- Screening (+) -> electrostatic (-) -> repulsion (-)
- Osmotic effect (-) -> repulsion (-) 
  -> **Aggregation 

