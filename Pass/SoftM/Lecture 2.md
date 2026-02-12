---
date: 2025-11-12
Prof: Pouyan Boukany
aliases:
  - Colloidal Dispersions
---
# Colloids Systems Introduction

**Colloids**: 
	A colloidal dispersion is a heterogeneous system in which particles of solid or droplets of liquid with dimensions of order 10 µm or less are dispersed in a liquid medium.
	
- Size: 
	Small enough to be influenced by thermal fluctuations and not dominated by gravity. 
	Big enough to be treated as one body with average density, surface charge, etc.
	
- High area of interface:
	Properties and behaviour controlled by surfaces. 
	*For example, in a 10nm SiO2 particle, ~20% of the Si atoms are at the surface*

Control stability:
	Avoid aggregation
	Controlled aggregation

Control flow properties:
	Viscosity
	Shear rate dependence

![[415681b5594b73817be58415a15504f14be7a08cb906560251ec7fe341bcc33f.png]]


## Viscoelastic Systems
- Shear stress(Pa): $$\sigma=\frac{F}{A}$$
- Shear Strain: $$e=\frac{\triangle x}{H}$$
- **Shear rate** ($s^{-1}$): $$\frac{\triangle e}{\triangle t}=\frac{\triangle x}{H\cdot\triangle t}\,\,\to\,\,\dot{e}=\frac{v}{H}$$ where $\dot{e}=\triangle e/\triangle t$, $v=\triangle x/\triangle t$ 


- ==**Deborah Number**==
	The response of soft matter (e.g. colloids, polymers) to an imposed stress may resemble the behaviour of a solid or a liquid, depending on the situation.
	Liquid is favoured by longer time scales and higher temperatures.
	Solid is favoured by short time and lower temperature.
	$$De=\frac{\text{characteristic relaxation time}}{\text{time scale of the deformation (observation)}}=\frac{\lambda_C}{t_S}$$
	If De is large -> solid behaviour;
	If De is small -> liquid behaviour.


## Diffusion in Colloidal Systems
*Same as MTP*
- Random Walk
	- The average of the molecules: $$<x(n)>\,\,=\,\,<x(n-1)>\,\,=\,\,...\,\,=\,\,<x(0)>\,\,=0$$
	- The spread of the molecules: (MSD-1D) $$<x^2(n)>\,\,=n\delta^2=2Dt$$
- Langevin: 
	- MSD Formula: $$<x^2>=\frac{k_BT}{3\pi\eta\alpha}t+C$$
	- Stokes-Einstein's Formula: $$D=\frac{k_BT}{6\pi\eta\alpha}$$
![[cc5c547e59351be40b850497df5dffe3f068b5f709df1eab42d5b02906773200.png]]


# Stability of Colloidal Systems
## Force on an individual particles:
1. **Gravity**: (Consider the effective mass due to buoyancy) $$F_g=\frac{4}{3}\pi\alpha^3\triangle\rho g$$
	where $\triangle\rho=\rho_2-\rho_1$ 
	$\triangle\rho>0$ - sedimentation
	$\triangle\rho<0$ - creaming

2. **Drag Force**: (Stokes law)$$F_D=-6\pi\eta\alpha v$$
Particle in steady motion -> $F_g=F_D$ $$\frac{4}{3}\pi\alpha^3\triangle\rho g=-6\pi\eta\alpha v$$ Terminal Velocity: $$v=\frac{2\alpha^2\triangle\rho g}{9\eta}$$ -> The sedimentation rate increases with $\alpha^2$, so larger particles/aggregates settle faster. 

3. **Brownian Motion** - Diffusion


## The Interactions between many particles:
### 1. Attractive - **van der Waal Interaction

- Origin: 
	quantum mechanical 
	-arising from the interaction between fluctuating dipoles in each of the atoms. 

- Between **two atoms/molecules**: $$U(r)\sim-\frac{1}{r^6}$$ -> Attractive and short ranged, but weak ($\approx k_BT$)

- Between **two particles** - additive individual contributions $$U(h)=-\frac{AR}{12h}$$ Strong attractive force 
  *h is the distance between two surfaces* ![[aeab5fbf80de5546ccbb1aa747b419b05d21106f8b83fe9970c3458b1e78291c.png]]

- Example: 
	Soft plastics like **cling film** adhere to wide variety of other solids
	-> ==Close contact== can be achieved for soft, deformable solids. 


### 2. Repulsive - **Electrostatic**

- Surfaces often charged because of:
	1. **Structural Origin**
		*The structure of materials itself may naturally have an imbalance of charges.* 
		*e.g., Al2O3, SiO2*
	2. **Surface Groups**
		*Chemical groups on the surface can gain or lose protons in solution, leaving the surface charged.*
		*e.g., -COOH, -OH*
	3. **Selective Adsorption**
		*The surface can adsorb specific ions from the surrounding medium.*
		*e.g., Ag adsorbs Cl-*

We can manipulate and control interaction through surface chemistry
-changing the dielectric properties of the solvent. 


- **Reduction of repulsive force - Screening effects**
  <- due to presence of ions in the medium
  *From MTP*![[5b3373da7bcf5ba4ea3bfc4020046cfcfdac2b57f2f14d19425c921f7c893bf4.png]]

  **Debye Screening length**: $$\kappa^{-1}=\left(\frac{\varepsilon\varepsilon_0k_BT}{2z^2e^2n_0}\right)^{1/2}$$ where $\varepsilon$ is relative dielectric constant (介电常数)
  $n_0$ is ionic concentration in medium 
    **! affected by ==salt concentration== (sometimes use I - ionic strength)**
  $ze$ is ionic charge
  At $h>>\kappa^{-1}$ electrostatic interaction $\to 0$ 


### DLVO Theory
- **DLVO Theory** (Derjaguin Landau Verwey Overbeek): 
	Attractive + Repulsive $$V=V_R+V_A$$
	-Large separation - no aggregation  -> meta-stable
	-Small separation - particles aggregates are very stable
![[6fea51f43ff33d3632cec0635e13bfcbd6802053cd539f4b2c4efa48424dc322.png]]


## Stabilisation Methods
Stabilise polymers by coating the particle with a polymer layer

### Repulsive Forces
- **Steric effect**
	If the polymer chains start to overlap (if no attractive interaction between polymer chains), there will be repulsive force. 
	Depends on the size and density of polymers. 
	
- **Osmotic effect**
	The concentration of polymer solution inside the gap increases.
	Depends on the solvent. 
	(==**Good solvent**==: the polymer can be effective at stabilising the colloid)
	
- **Entropic effect**
	Reduction in degrees of freedom
	

### Attractive Forces
- **Bridging**
	![[Pasted image 20251126171046.png]]
	- Low concentration of polymers causes the formation of **bridges**. 
		These bridges pull particles together, causing *local aggregation*.
		Even a few bridges can reduce stability, leading to small clusters or flocs.
		
	- High concentration of polymers causes many aggregations at the same time, polymer **bridging flocculation**. 
		The system may become structurally **==stable==**, because the network prevents further settling or dispersion. 
		*(used in purifying water, clearing wine)*
	
- **Depletion**
	Add non-adsorbing polymer -> Non-adsorbing polymers will become polymer **coils**
	-> In the suspension add second particle, $r_2<r_C$
	-> Osmotic pressure effect due to excluded volume 
	*(polymers can not stick to particle surfaces. In a solution they cannot enter the narrow gap between two nearby particles because of size exclusion)*
	-> Concentration gradient near the surface.
	-> Push the particles together. 
	
	The outcome: an effective **attractive** force
	\* So the polymer concentration can be used to tune the interaction
	
	**Depletion flocculation**: decreased effective concentration by aggregation![[b2dfb56187bc09d5dc82938afdf290a3c9c5009b2b4480b5e46e6068df415026.png]]

### Tuning the Interaction
1. **Add salt** -> reduce ==screening length==, decrease the magnitude of the ==electrostatic== repulsion relative to the van der Waals attraction;
2. **Add poor solvent** -> increase ==polymer/polymer attractive== interaction, lead to a net attraction between the colloid particles;
3. **Add non-adsorbing polymer** -> increase the size of the ==depletion== interaction;
4. **Remove grafted polymers** (chemically) from the surface of the colloidal particles. 


# Flow Properties
![[b6a9ba0af73c2f022b229f6ef07335de7d4508fa7fd4ca25d0918a51bfe09ad9.png]]
- **Low concentrations** (Hard Sphere) $$\eta=\eta_0(1+2.5\phi)$$ where $\phi$ is the volume fraction. 
- **High concentrations**: 
	rapid increase in viscosity  -> non-newtonian behaviour

## Flow Behaviour / Rheology
Flow behaviour depends on particle size, medium, ...
When the system is subjected to flow, its internal structure becomes disturbed -> Non-equilibrium
-> Rearrange to reach a new configuration that minimizes the energy

With shear rate $\gamma$ , the characteristic time is $$\tau_{shear}=\dot{\gamma}^{-1}$$ The restored equilibrium is decided by Brownian motion: $$\tau_B=\frac{\alpha^2}{D_{SE}}=\frac{6\pi\eta_0\alpha^3}{k_BT}$$ **Peclet number**: 
	A dimensionless number.  $$Pe=\frac{\tau_B}{\tau_{shear}}=\frac{6\pi\eta_0\alpha^3\cdot\dot{\gamma}^{-1}}{k_BT}$$
$Pe<<1$: Brownian motion dominates
$Pe>1$: Shear restructures the fluid
$$Pe=\frac{UL}{D}$$ where: D is diffusion coefficient, U is velocity, L is the characteristic length. ![[37c6914248020a84d97910f978360f82dd89ee6b0712f58997895384dd71248a.png]]


**Laminar & Turbulent Flow**: $$Re=\frac{\rho vL}{\eta}$$ ![[b574a442cb25a25f803777b5cf94a4c166fb251f2eedfa1cd1b103aeb937e12d.png]]
*In this course: Re low, L low, no inertial, no turbulence*


# Colloidal Aggregation
![[be57157d181b0438a122fc093c2d811a9b8ee28dc3f1c12bbab7b55cd0e60d57.png]]
b) is stronger, therefore the structure is stiffer, while a) is more flexible. 
![[cb918f8ef34360da811a010597bcff4a2860f4ccb84cf883803214576317fb11.png]]


# Conceptual Questions
1. What is a colloid? Why are they considered soft matter? Give some real life examples of colloid systems.
	A colloidal dispersion is a heterogeneous system in which particles of solid or droplets of liquid with dimensions of order 10 µm or less are dispersed in a liquid medium.
	Colloids are dominated by thermal fluctuations, Brownian motion, surface forces, and week interparticle interactions. Their structure and properties change easily under small stresses, which is characteristic of soft matter. 
	Examples: milk, fog, paints and inks, mayonnaise, cream, lotions. 

2. What is Brownian motion? How will you approach modelling it?
	Brownian motion is the random, jittery motion of small particles resulting from constant collisions with solvent molecules. 
	We can use Random Walk model to approach modelling it, using Langevin equation or diffusion equation (Stokes-Einstein relation). 

3. Why do macroscopic surfaces fail to adhere through molecular interactions? Which one is better cling film or metallic solid and why?
	Macroscopic surfaces are rough at micro- and nano-scales, so only a tiny fraction of atoms get close enough for molecular attraction. 
	Cling film adheres better because soft polymers can deform and conform to surface irregularities, increasing real contact area; metallic solid is stiff and cannot conform, so molecular attraction is negligible. 

4. Explain sedimentation in colloidal systems. Name an application that uses this property. How will you prevent sedimentation in Brownian systems?
	When gravity dominates over Brownian motion, particles move downward and accumulate at the bottom. 
	Application: Centrifugation
	How to prevent sedimentation: 
	- Reduce particle density difference
	- Reduce particle size
	- Increase viscosity of the medium
	- Add electrostatic or steric stabilizer to prevent aggregation. 

5. What is screening of charges in colloidal systems? How does it affect the columbic interaction? Explain with a schematic. 
	Charged colloids in a liquid with ions attract counterions around them. These counterions create an ionic "cloud" around that partially neutralized the colloid's surface charge. 
	The Coulomb interaction no longer decays as 1/r but becomes short-ranged. The potential is exponentially screened; at high salt concentration, the interaction becomes very short-ranged.

6. Sterically-stabilized silica spheres in cyclohexane are considered as a good model for the so called hard-sphere (HS) model. In this model, spherical particles feel an infinity force whenever their surfaces contact, see sketch below. This model holds when the steric stabilization arises due to the presence of very small alkanes on the silica surface.![[bcffd6023102d48e82a34d262ec234381a2544d47e3af4f8100481b6aa4bed17.png]]
   (a) How is the sphere-sphere interaction modified if the silica spheres are grafted with long polymer chains instead of very small alkanes?
	Long polymer chains create a thick **steric brush**, causing an additional soft, repulsive, entropic force when polymer layers overlap. The interaction becomes soft-repulsive instead of hard-sphere-like. 

   (b) On the original silica particles in cyclohexane, one adds polydimethylsiloxane (PDMS) polymers. PDMS is soluble in cyclohexene, and does not adhere to the surface of the silica spheres. How the polymer-mediated sphere-sphere interaction depends on the molar mass of the added PDMS?
	Because PDMS stays in solution, the interaction becomes polymer-induced **depletion attraction**:
	Higher molar mass → larger polymer coils → larger excluded volume → stronger and longer-ranged attractive depletion force.

   (c) Why this HS model is a good approximation for these colloidal particles in cyclohexane but not in water?
	In cyclohexane: silica surfaces with short alkanes have almost no charge; solvent has no strong **ionic screening**. Interactions are short-ranged and mostly steric → closely resembles hard-sphere physics.
    In water: silica surfaces ionize and become charged; **electrostatic double layers create long-ranged repulsion** → strong deviation from HS behavior.

   (d) The resulting sphere-sphere interaction in water depends on the background salt concentration of the water used. Is this interaction more long-ranged at low or high salt concentration?
	Low salt: longer Debye length → long-ranged electrostatic repulsion.
	High salt: screening is strong → short-ranged interaction.
    Therefore, interaction is more long-ranged at low salt concentration. 

