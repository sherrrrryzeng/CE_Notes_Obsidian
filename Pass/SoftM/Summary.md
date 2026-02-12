# Soft Matter
## Definition
- A subfield of condensed matter comprising a variety of physical states that are easily deformed by thermal stresses or thermal fluctuations. 
- They include **liquids, colloids, polymers, foams, gels, granular materials, and a number of biological materials**. 
- These materials share an important common feature: predominant physical behaviours occur at an energy scale comparable with ==**room temperature thermal energy**==. ( $E_k=k_BT$ )


## Van der Waals forces
![[56be8b142872e756e197818a73654beb9b5cf4a038d714e06c1276016d0ddc5c.png]]
	- *Short range repulsion:* 
		*quantum mechanical origin (Pauli's exclusion principle)*
		*usually idealized with hard sphere potential ( $\approx\infty$ )*
	- *Long range attraction:*
		*origin on fluctuating dipole-dipole interactions*


## Viscoelastic
- For a **Hookean** solid
	Ideally **elastic** - an applied shear stress produces a shear strain in response, which is proportional to shear stress, and the constant of proportionality is the **shear modulus** $G$: $$G=\frac{\sigma}{e}$$ where $\sigma$ is shear stress$$\sigma=\frac{F}{A}$$ $e$ is shear strain$$e=\frac{\triangle x}{y}$$
- For a **Newtonian** liquid
	Ideal liquid - an applied shear stress produces a flow with a **constant** shear strain rate in response, which is proportional to the shear stress, and the constant of proportionality is the **viscosity**. 
	Shear strain $$e=\frac{v}{y}$$ where $v$ is the relative velocity, $y$ is the distance in between. The velocity gradient $v/y$ is in fact identical to the time derivative of the shear strain.
	
	The Newtonian viscosity $$\eta=\frac{\sigma}{\dot{e}}$$ $$\eta=\frac{\sigma}{\dot{e}}=\frac{F/A}{v/y}$$So the resisting force due to viscosity is: $$F=A\,\eta\,\frac{v}{y}$$
	Shear modulus$$G=\frac{\eta}{\tau}$$ where $\tau$ is the relaxation time. 
	
- **Shear rate** ($s^{-1}$): 
	also $\dot{\gamma}$ $$\frac{\triangle e}{\triangle t}=\frac{\triangle x}{H\cdot\triangle t}\,\,\to\,\,\dot{e}=\frac{v}{H}$$
	where $\dot{e}=\triangle e/\triangle t$, $v=\triangle x/\triangle t$ 
	
- **Deborah Number**
	The response of soft matter (e.g. colloids, polymers) to an imposed stress may resemble the behaviour of a solid or a liquid, depending on the situation.
	Liquid is favoured by longer time scales and higher temperatures.
	Solid is favoured by short time and lower temperature.
	$$De=\frac{\text{characteristic relaxation time}}{\text{time scale of the deformation (observation)}}=\frac{\lambda_C}{t_S}$$
	If De is large -> solid behaviour;
	If De is small -> liquid behaviour.

## Relaxation time
![[abd7a7288113d4355ea1a7fd6c885d5747f41ff81f261a0d5faf63ba1ece1851.png]]

- (a) Newtonian
- (b) **Shear-thinning** 
  *(paint: easy to brush, uneasy to sag under its own weight)*
- (c) **Shear-thickening** 
  *(pastes with rather a high volume fraction of particles)*
![[ab0f9b72e1d80419df797515c823d7b07ccddc03ced046166a5f187e4d35ac5c.png]]


## Energy barrier
To **deform a solid**:
	We must counter internal forces of enthalpic origin between atoms that hold the solid together (basically the stored energy density). 
	The calculation of the Young Modulus: $$E=A\frac{\epsilon}{a^3}$$![[0e0878e5a7013a7fc7eaeb6d89efbcf606288ce63c78c877bc7def1e0d92d7b4.png]]
	where:
		$a$ is the interatomic separation in an ideal cubic lattice
		$\epsilon$ is the minimum energy of interatomic potential



To **deform a liquid**:
    Liquids respond **temporarily** the same way if deformation is applied fast enough. Thus the molecular origin for viscous liquids is $G_0$. 
	But liquid molecules can re-arrange locally, relaxing stress. 
	- The atom in a high energy configuration is locally **trapped by its neighbours**, which together confine it to a 'cage'. 
	- It is able to escape from its cage by a **thermally activated jump** into a new location of lower energy. 
	- The probability of the atom overcoming the energy barrier and escaping from its cage on any attempt is given by the **==Boltzmann distribution==**. $$\tau^{-1}\sim v\,exp(-\frac{\epsilon}{kT})$$
where:
- $\tau$ is the characteristic time to escape cage and relax stress;
- $v$ is the **characteristic frequency of molecular vibration** in cage (similar to those in solids);
$\epsilon$ is the **==energy barrier==**
	usually $\epsilon\sim 0.4\epsilon'$ (the **latent heat of vaporisation**)
	unit $[J/mol]$ !
	leading to $\tau\sim 10^{-12\sim -10}s$
- Boltzmann factor $exp(-\frac{\epsilon}{kT})$
	 = probability of scape. 


Using $\eta\sim G_0\tau$:
$$\eta=\frac{G_0}{v}exp(\frac{\epsilon}{kT})$$
It is related to the ability of vibrations to overcome the caging effect. 

\*BUT this behaviour breaks down **at lower temperatures**, where the system exhibits a much stronger dependence...and the liquid approaches the **glass transition temperature**. 


## Glass
- Definition:
	Glass is an amorphous solid. Liquids can become amorphous solids as the temperature is lowered, provides it does not crystallize (density difference between glass and liquid is very small).

- **Glass state:**
	As a material cools, molecules attempt to rearrange into a highly organised **crystalline solid state**. However, typical cooling speeds are too fast to allow for this perfect alignment. Due to rapid cooling, the material enters a **glass state** instead. In this state, the structure is less organized (amorphous) and contains "extra space" between atoms.
  
- **Density Differences:** 
	Because of the extra internal space, the density of glass is lower than its crystalline counterpart. The faster the cooling process, the less time molecules have to pack together, resulting in an even lower density in the final glass.

- **Structural Degradation:**
	Since the crystalline state represents the **lowest free energy** (most stable) state, the molecules naturally try to move toward it over time to eliminate that extra space. This slow, ongoing movement of molecules toward a more stable state is what we observe macroscopically as **degradation** or structural aging.


## Glass' viscosity
- Vogel-Fulcher Law: 
	Close to glass transition temperature, viscosity is better described by the phenomenological(/experimental) **==Vogel-Fulcher Law==**: $$\eta=\eta_0\,exp(\frac{B}{T-T_0})$$ where $T_0$ is the Vogel-Fulcher temperature. 

- **==Cooperativity==**
	at these lower temperatures, viscosity is governed by rearrangements of neighbouring molecules that provide "space" for movement. 

- Measure glass transition: 
	If viscosity goes to infinite for a glass, it should take a long time to measure it (way longer than **experimental time** $\tau_{exp}$) . 
	So we measure **==DENSITY==** instead of shear modulus appearance. 
	![[a418fda1c71c8e7d189ef823b0b24c4b14d46229ff1d9df4920ad5400f8353ae.png]]
	![[f5a041ede69cb20427f0ee00b87082635f97d00df8ade1ec614d8c181e872060.png]]
	-> Density of Glass slightly lower than crystal 
	-> Extra "space" between atoms

- Free volume: 
	Assume **free volume** between atoms is $v_f$ , and microscopically thermal expansion mimics macroscopic world, the fraction of free volume in sample of total volume is: $$\frac{v_f}{v}=f_g+\alpha_f(T-T_g)$$ where:
		$v$ : total volume
		$f_g$ : fraction of free volume at $T_g$ 
		$\alpha_f$ : thermal expansion coefficient
	
	Assume that the viscosity close to $T_g$ still has the Arrhenius form, but
	instead of relating probability of molecular movement to Temperature, assume that movement comes from **excess of free volume** that promotes molecular re-arrangements: $$\eta=a\,exp(\frac{bv}{v_f})$$ Here we can recover the Vogel-Fulcher law. 


# Colloids dispersion
## Definition
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


## Diffusion in Colloidal Systems
- Random Walk
	- The average of the molecules: $$<x(n)>\,\,=\,\,<x(n-1)>\,\,=\,\,...\,\,=\,\,<x(0)>\,\,=0$$
	- The spread of the molecules: (MSD-1D) $$<x^2(n)>\,\,=n\delta^2=2Dt$$
- Langevin: 
	- MSD Formula: $$<x^2>=\frac{k_BT}{3\pi\eta\alpha}t+C$$
	- Stokes-Einstein's Formula: $$D=\frac{k_BT}{6\pi\eta\alpha}$$
	![[cc5c547e59351be40b850497df5dffe3f068b5f709df1eab42d5b02906773200.png]]

## Force Balance of an individual particles
1. **Gravity**: (Consider the effective mass due to buoyancy) $$F_g=\frac{4}{3}\pi\alpha^3\triangle\rho g$$
	where $\triangle\rho=\rho_2-\rho_1$ 
	$\triangle\rho>0$ - sedimentation
	$\triangle\rho<0$ - creaming

2. **Drag Force**: (Stokes law)$$F_D=-6\pi\eta\alpha v$$
Particle in steady motion -> $F_g=F_D$ $$\frac{4}{3}\pi\alpha^3\triangle\rho g=-6\pi\eta\alpha v$$ Terminal Velocity: $$v=\frac{2\alpha^2\triangle\rho g}{9\eta}$$ -> The sedimentation rate increases with $\alpha^2$, so larger particles/aggregates settle faster. 

3. **Brownian Motion** - Diffusion


## The Interactions between many particles
### Attractive - **van der Waal Interaction
- Origin: 
	quantum mechanical 
	-arising from the interaction between fluctuating dipoles in each of the atoms. 

- Between **two atoms/molecules**: $$U(r)\sim-\frac{1}{r^6}$$ -> Attractive and short ranged, but weak ($\approx k_BT$)

- Between **two particles** - additive individual contributions $$U(h)=-\frac{AR}{12h}$$ Strong attractive force 
  *h is the distance between two surfaces* ![[aeab5fbf80de5546ccbb1aa747b419b05d21106f8b83fe9970c3458b1e78291c.png]]

- Example: 
	Soft plastics like **cling film** adhere to wide variety of other solids
	-> ==Close contact== can be achieved for soft, deformable solids. 


### Repulsive - **Electrostatic**

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


### Stabilisation Methods
Stabilise polymers by coating the particle with a polymer layer

Repulsive Forces:
- **Steric effect**
	If the polymer chains start to overlap (if no attractive interaction between polymer chains), there will be repulsive force. 
	Depends on the size and density of polymers. 
	
- **Osmotic effect**
	The concentration of polymer solution inside the gap increases.
	Depends on the solvent. 
	(==**Good solvent**==: the polymer can be effective at stabilising the colloid)
	
- **Entropic effect**
	Reduction in degrees of freedom
	

Attractive Forces:
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

- Tuning the Interaction:
	1. **Add salt** -> reduce ==screening length==, decrease the magnitude of the ==electrostatic== repulsion relative to the van der Waals attraction;
	2. **Add poor solvent** -> increase ==polymer/polymer attractive== interaction, lead to a net attraction between the colloid particles;
	3. **Add non-adsorbing polymer** -> increase the size of the ==depletion== interaction;
	4. **Remove grafted polymers** (chemically) from the surface of the colloidal particles. 


## Rheology 
- Concentration and viscosity:
	![[b6a9ba0af73c2f022b229f6ef07335de7d4508fa7fd4ca25d0918a51bfe09ad9.png]]
	- **Low concentrations** (for Hard Sphere) $$\eta=\eta_0(1+2.5\phi)$$ where $\phi$ is the volume fraction. 
	- **High concentrations**: 
		rapid increase in viscosity  -> non-newtonian behaviour

- Diffusion and Shear: 
	Flow behaviour depends on particle size, medium, ...
	When the system is subjected to flow, its internal structure becomes disturbed -> Non-equilibrium
	-> Rearrange to reach a new configuration that minimizes the energy
	
	With **shear rate** $\dot{\gamma}$ , the characteristic time is $$\tau_{shear}=\dot{\gamma}^{-1}$$ The restored equilibrium is decided by Brownian motion: $$\tau_B=\frac{\alpha^2}{D_{SE}}=\frac{6\pi\eta_0\alpha^3}{k_BT}$$ **Peclet number**: 
		A dimensionless number.  $$Pe=\frac{\tau_B}{\tau_{shear}}=\frac{6\pi\eta_0\alpha^3\cdot\dot{\gamma}^{-1}}{k_BT}$$
	$Pe<<1$: Brownian motion dominates
	$Pe>1$: Shear restructures the fluid
	
	Another form: $$Pe=\frac{UL}{D}$$ where: D is diffusion coefficient, U is velocity, L is the characteristic length. ![[37c6914248020a84d97910f978360f82dd89ee6b0712f58997895384dd71248a.png]]

- Flow regimes: 
	Reynold $$Re=\frac{\rho vL}{\eta}$$ ![[b574a442cb25a25f803777b5cf94a4c166fb251f2eedfa1cd1b103aeb937e12d.png]]
	*In this course: Re low, L low, no inertial, no turbulence*


## Colloidal Aggregation
Strong attraction: ![[be57157d181b0438a122fc093c2d811a9b8ee28dc3f1c12bbab7b55cd0e60d57.png]]
b) is stronger, therefore the structure is stiffer, while a) is more flexible. 
![[cb918f8ef34360da811a010597bcff4a2860f4ccb84cf883803214576317fb11.png]]


# Polymers
## Definition
A giant molecule made up of many repeat units covalently joined together in the form of a long chain. 

State: liquid, glass, crystal, liquid crystal
*not gas/vapor (Decompose before the evaporation temperature)*

Stereochemistry:
- **Isotactic**: side groups on the same side of the chain
- **Syndiotactic**: side groups on alternate sides
- **Atactic**: random arrangement of side groups![[9fcbf701b26d39f057af4cbcf6b2bdd2c3f79ba0008c0361b7259e54839ea7a9.png]]
-Tacticity determines ability to form ==**crystals**== 
   *(isotactic&syndiotactic can form crystals)*
-Disordered, atactic polymers form **==glasses**== 
   *(impossible to crystallise even at low temperatures)*


## Structure
![[5c450319b3ca526788ccdf79759ec1a1a46b5d0ae57c1f4885a842422d0e9478.png]]

- **==Homo-polymers**==: all repeat units are the same
- **==Co-polymers==**: 
   composed of more than one type of repeat unit
	- **Block** copolymer
	- **Random** copolymer
	- **Alternating** copolymer


Structure Differences:
- **Main molecule**: 
   Giant molecules usually with **==carbons==** building the backbone
   exceptions exist (e.g., Si, N)
- **Molecule structures**: **==Isomers==** of polymers - tacticity
- **Chain structures**: *Linear chains, branched chains, ladders, networks, dendrimers* ![[4240569c109721c8983ecd3d1b0c8d1992557f866d87075b31f9a8c7bffae9ee.png]]
- **Chain sequence**: Homopolymers, copolymers, random copolymers, microphase-separated polymers (like amphiphilic polymers)

-> Polymers are very heterogeneous class of materials


## Poly-dispersity
Synthetic polymers are made by processes that yield not a single degree of polymerisation, but a distribution:

- Number-average molecular weight: $$M_n=\frac{\sum n_iM_i}{\sum n_i}$$
- Weight-average molecular weight:$$M_w=\frac{\sum w_iM_i}{\sum w_i}=\frac{\sum n_iM_i^2}{\sum n_iM_i}$$
- **Poly-dispersity Index(PDI):** $$\frac{M_w}{M_n}$$


## Ideal Chain Model
Under equilibrium polymers are in **coil** shape
![[8993fbe6a505c8c290e5e00beec278c39098cc79b3a50966f995a19e45f6e7a5.png]]
- $N$: degree of polymerization
- $a$: length defined by chemical bonds
- $R$: end-to-end vector that describes a coil made up of N jump vectors $a_i$ 

Ideal polymer chain model **assumptions**:
1. Consider random steps of equal length $a$ defined by chemical bonds.
2. The segments can rotate freely around the bond.

End-to-End Distance:
$$R=a_1+a_2+...+a_N=\sum^N_{i=1}a_i$$ The average over the polymer chain is: $$<R>=0$$
The mean square displacement (MSD) is: $$<R^2>=<\sum_{i=1}^N a_i\cdot\sum^N_{j=1} a_j>=<\sum_{i=1}^N\sum^N_{j=1} a_ia_j>$$ $$=Na^2+2a^2\sum_{i=1}^{N-1}\sum^N_{j=i+1}\cos\theta_{ij}$$
For a freely jointed chain the average of the cross term $$<\sum_{i\neq j}^N a_ia_j>=0$$ then $$<R^2>=Na^2$$

From Brownian motion we have: $<R^2>=6Dt$ 

**The radius of gyration**: the RMS distance of the collection of atoms from their common center of gravity$$R_g=\sqrt{\frac{<R^2>}{6}}=a\sqrt{\frac{N}{6}}$$

## Real Chains
### Real Chain Calculations
In real chains there are 
- **Excluded volume effects** *($\cos\theta$ not random but a finite value)*
- **Steric limitations** *(side groups, interactions, etc.)*


Recall that $$<R^2>=Na^2+2a^2\sum_{i=1}^{N-1}\sum^N_{j=i+1}\cos\theta_{ij}$$ Correlation between bond vectors: $$<a_i\cdot a_{i-m}>=a^2cos^m\theta$$ $$lim_{|i-j|\to\infty}<\cos\theta_{ij}>=0$$-> The correlation between bond vectors "dies" with increasing separation. 


Replace the **monomer size** $a$ with an effective monomer size
$b$ : **Statistical step length or ==Kuhn segment**== $$<R^2>=C_{\infty}Na^2=Nb^2$$
**Flory Characteristic Ratio**: $$C_{\infty}=\frac{b^2}{a^2}$$
-> After renormalization, this relation holds for all flexible linear polymers.


End-to-end Distribution Function: 
The Gaussian distribution of R: $$P(R)=(\frac{2\pi Na^2}{3})^{-2/3}exp(-\frac{3R^2}{2Na^2})$$
3D distribution: $$P(R,N)=(\frac{2\pi<R^2>}{3})^{-2/3}exp(-\frac{3R^2}{2<R^2>})$$

Entropic effects in a Gaussian Coil:
Boltzmann equation: $$S=k_bln\Omega$$  $\Omega$ : statistical weight

The **entropy** of a Gaussian coil: $$ln(P(R))=ln\Omega$$ $$S(R)=\frac{3k_bR^2}{2Na^2}+\text{constant}$$
\* Entropy decreases with the stretching (increasing order), like springs 


When the entropy is known as a function of chain elongation, we can get the **free energy** from a random walk model: $$G(R)=U-TS=-\frac{3k_bTR^2}{2Na^2}+\text{constant}$$ *(not only Gibbs but also other type of free energy)*


The ==**force==** required to stretch or compress the chain is: $$F(R)=\frac{\partial G}{\partial R}=\frac{3k_bTR}{Na^2}$$
The **"==spring constant=="** is: $$\frac{\partial^2G}{\partial R^2}=\frac{\partial F}{\partial R}=\frac{3k_bT}{Na^2}$$
The spring constant increase with T(easier to pull with low temperature), decrease with N(easier to pull long polymers).
*Unlike a traditional energetic spring where stiffness comes from internal energy U.*

Now all is based on conformational entropy, no interaction energies are accounted for yet.


### The Excluded Volume Effect
Steric hindrance on short distances limits the number of conformations.
At longer distances, we have a topological constraint: **the self-avoiding walk or the excluded volume effect**. $$R\approx aN^{3/5}=aN^{0.6}$$

### Good solvent
Radius of gyration:
![[7bb8e70a728ea32555aab31d3481c404fce388dd5b1fe0ab412afecccaa961e4.png]]


## Rouse Model
![[abf0b3dcbd2e18ef0c6239de587394a31c9e41e10fbf7291d05d56c6575930d0.png]]
\* Applicable to **short chains in melt**.

Einstein Equation: $$D=\frac{k_BT}{\xi},\,\,<R^2>=6Dt$$ where $\xi$ : friction coefficient
For polymer with N beads, the chain fraction is $\xi N$

The diffusion coefficient is: $$D=\frac{k_BT}{\xi N}\sim\frac{1}{N}$$Since $$<R^2>=Na^2\sim N$$ The relaxation time is the time the chain takes to diffuse a distance equal to its size R: $$\tau_R=\frac{R^2}{D}\sim N^2$$

## Overlapping Concentration
When the system is in dilute regime, polymers do not interact with each other.
When the system reaches the **critical concentration** $C_{crit}$, the overlapping between polymers starts. 
Definition: $$C^*=\frac{M}{v^*N_{Av}}=\frac{M}{R_g^3N_{Av}}$$ The volume of the polymer is given above: $$R_g=\sqrt\frac{<R^2>}{6}=a\sqrt\frac{NC_{\infty}}{6}$$
A simpler case of polymer melts:
![[d9f845cd7dda0f308c2ef6b802eb3cf03cb6e1580d17a43ac99e2e675d8d0469.png]]

Polymer solutions (good solvents):
![[64e11931c786f21c8ea59ffb1365ecd71ac1b2aac9284141d848412e81468281.png]]

The effect on Viscosity:
![[a40f2296283992e62cbcfe398e1c44870515379b041cba22b5bbd5b73b22d267.png]]
After overlapping concentration polymers start to overlap, and the viscosity start to increase faster with increasing concentration. 



## Chain Entanglement
![[ae21deff8947333e862d5367b7770e630fe5a81ff54451c7f6b096ca59dc8a93.png]]
**Chain Entanglement** is going to happen above $M_c$ (Critical Molecular Weight)

- before $M_c$: $$\frac{log(\eta_1/\eta_2)}{log(Me_1/Me_2)}=1$$
- after $M_c$: $$\frac{log(\eta_1/\eta_2)}{log(Me_1/Me_2)}=3.4$$

## Rubber Elasticity (Affine deformation)
![[c3a7765c5d0c567d0c7ec4931c51b4acf095eff1ef359ca46264142ed11c3e55.png]]
![[b4cb2195bb25cfc944ac43671e00f1476496da06548b6154e0ee28e165d222ab.png]]
Rubber Elasticity: $(x,y,z)\to(\lambda_xx,\lambda_yy,\lambda_zz)$

Initial mean end-to-end distance:$$r_0^2=x^2+y^2+z^2$$
New mean end-to-end distance -**==Affine Deformation==** (when the rubber is deformed each individual cross-link point moves in proportion to the deformation of the whole sample):$$r_1^2=\lambda_x^2x^2+\lambda_y^2y^2+\lambda_z^2z^2$$
Assuming that rubber is **incompressible**: $$\lambda_x\lambda_y\lambda_z=1$$
A simple elongation in the x direction, **stretch ratio**($\lambda$) is: $$\lambda_x=\lambda,\,\,\lambda_y=\lambda_z=\frac{1}{\sqrt{\lambda}}$$
Change in entropy on deformation per strand: $$\triangle S_{strand}=\frac{-3k_B}{2Na^2}[(\lambda_x^2-1)x^2+(\lambda_y^2-1)y^2+(\lambda_z^2-1)z^2]$$where $$<x^2>=<y^2>=<z^2>=\frac{Na^2}{3}$$
Total entropy change per unit volume is: $$\triangle S_{volume}=\frac{-nk_B}{2}(\lambda_x^2+\lambda_y^2+\lambda_z^2-3)=\frac{-nk_B}{2}(\lambda^2+\frac{2}{\lambda}-3)$$
where n is strands per unit volume. 

Change in free energy: $$\triangle F_{volume}=-T\triangle S_{volume}=\frac{-nk_BT}{2}(\lambda^2+\frac{2}{\lambda}-3)$$
Elastic work done during the deformation, which means the tensile stress is: $$\sigma=\frac{\partial F}{\partial\lambda}=\frac{-nk_BT}{2}(2\lambda-\frac{2}{\lambda^2})$$
The relation between tensile stress $\sigma$ and strain $\gamma$ is:$$\lambda=1+\gamma$$ $$\sigma=nk_BT\left((1+\gamma)-\frac{1}{(1+\gamma)^2}\right)$$
For small strain($\gamma<<1$) we can simplify to: $$\sigma\approx\gamma nk_BT$$
**Shear modulus**: $$G=\frac{\sigma}{\gamma}=nk_BT$$
Another way to express in terms of the average relative molecular mass **between ==cross links**== $M_e$, and the density $\rho$: $$G=nk_BT=\frac{\rho N_{av}k_BT}{M_e}=\frac{\rho RT}{M_e}$$
Usually Critical Molecular weight for Chain entanglement: $M_{c}=2M_e$


## Time-Temperature Superposition
The relaxation reaction of entangled systems is different:![[17289838ffdd56c62b0e2abfd288470c639085f7d7ac4537374b13876be6d820.png]]

**Time-Temperature Superposition**:
$$a_T=\frac{\tau(T)}{\tau(T_0)}\approx\frac{\eta(T)}{\eta(T_0)}$$ $$\log{a_T}=\frac{-c_1(T-T_0)}{c_2+(T-T_0)}$$
![[10d3a14289911b5dcc72514c669248e0873a5a18fb3c7e4b887e66b7fa73a39d.png]]

The viscosity could be calculated by the slope (after $M_c$)
![[02dadf204e1213f2497ae669afb9fe2f66bc1c4e2d836a24c6d5e940e94cdbd7.png]]



## Reptation Model
Long-chain polymer melts contain entanglements between coils, which constrain their movement and therefore their response to mechanical deformation. 
-> The solution is **putting the chain in the tube  $$\eta\sim N^{3\sim3.4}$$
![[274cc779002ee3effaa0d8e9e37cc268f7ac3e2dd6ef39106cf43bc26f8b3d04.png]]


|**Feature**|**Rouse Model**|**Reptation Model**|
|---|---|---|
|**Constraint Environment**|Free environment (No entanglements)|Tube constraint (Entangled network)|
|**Molecular Weight Range**|$M < M_{cr}$ (Short chains)|$M > M_{cr}$ (Long chains)|
|**Viscosity Relation**|$\eta \propto M^1$|$\eta \propto M^{3 \sim 3.4}$|


## Oscillatory Deformation
![[83a44365ffdbb450a2a3fd2d7edcabd141a6413d671076d4f795d99b97fa6d56.png]]
Applies a sinusoidal strain $\gamma(t) = \gamma_0 \sin(\omega t)$ and measures the resulting stress $\sigma(t)$, especially the **time lag** between stress and strain.
- $\delta = 0^\circ$: Purely elastic (Solid).
- $0^\circ<\delta<90^\circ$: Viscous fluid (Polymers).
- $\delta = 90^\circ$: Purely viscous (Liquid).

Entangled wormlike micelles: red+blue = solid+liquid = viscoelastic
![[6802aee7ae59a7997422221490e498d03867bf0050dc04e17997eb573bbdc6d3.png]]

- **Storage Modulus ($G'$)**: Represents **elasticity**; energy stored and recovered (Solid-like behavior).
- **Loss Modulus ($G''$)**: Represents **viscosity**; energy dissipated as heat (Liquid-like behavior).
- **Loss Tangent**: Quantifies the balance between viscous and elastic components$$\tan \delta = \frac{G''}{G'}$$- $>1$ is liquid-like, $<1$ is solid-like.

聚合物并不是一直以单一的性质存在，而是会在不同的频率下呈现出不同的黏弹特征，这种特性反映了聚合物分子链的松弛行为和结构特征。


# Gels
## Definition
A gel is a material composed of subunits that are able to bond with each other in such a way that one obtains a **network** of macroscopic dimensions, in which all the subunits are connected by bonds.
- If one starts out with isolated subunits, and successively adds bonds, one goes from a liquid—a sol—to a material with a non-zero shear modulus—a gel.
- A gel has the **mechanical properties** characteristic of a solid, even though it is **structurally disordered** and indeed may contain a high volume fraction of liquid solvent. 

Useful definitions:
1. **Solid-like properties**
	 sustain shear stress with a network spanning the system.
2. Undergoes **liquid-solid transition** - ==**Gelation**==
3. **Heterogeneous**
	 multi-component systems dynamics on different time scales, multiple length scales.
	 immobile network + mobile solvent

## Gelatine
Formed from **collagen**, a protein found in animals.
When collagen is heated, it breaks down into the protein **gelatin**.

- In water, gelatine swells, forming a polymer solution (*liquid*).
- At low temperature: gelatine + water forms a solid (*gel*) — ==the water is trapped in a loose polymer network structure.==

- The system of gelatine+water is **thermo-reversible**
- Collagen molecules have cross-links from their **helix formation**. 

![[45ab78ee528806d5931d0b5d6225ab0d98507af5d8b15b36c06d6a73f10a75d8.png]]


## Rheology of Gels
- **Rheology experiment** ($G\neq 0$)
	Measuring the Gel Point when the transition from liquid-like to solid-like behaviour happens
	-> ==development of a shear modulus== ($\omega$=0)
	**Winter-Chambon method**: 
	 at the gel point  $$G(t)=St^{-n}$$![[3712abd9e5ba5d47fc5e0394d4ba4d275717f614a7812b2bcced88c12bb9739a.png]]
	 
- Falling ball
- TTT (tilt-test-tube)


## Flory-Stockmayer Model / Percolation Theory
The classical theory of Gelation - **Cayley tree**
![[dcd15e54a258af628049e510f91ee304dac4d7b11b2b6bf61310d3e558aea5ff.png]]
$$N\sim f(z-1)^n$$
Critical value - **percolation threshold** $f_c$ : $$f_c=\frac{1}{z-1}$$
当反应程度达到这个值时，体系会发生从“流体”到“弹性固体（凝胶）”的突变。
 
![[7ea442cef24d9a2fb6e5328a8d169282843886cc68d75523254158430ac620fd.png]]
- At the gelation point an infinite cluster is created that spans the whole system. 
- The macroscopic properties changes abruptly from liquid-like to solid-like. 
- *close to the gel point the gel fraction can be expanded as a power law function of the distance away from the gel point.* 
- \*Gelation is a continuous transition.

In general the problem does not have an analytical solution, from experience:
- triangular lattice $p_c\approx 0.347$
- square lattice $p_c\approx 0.5$


**Connectivity transition**: 
Gelation can be described as a connectivity transition --- bond percolation problem
![[95886dc69fc766b2ba509004e60f263e21bbdc205110e42238630b2533092bee.png]]
- *We start with array of points, to which bonds are added at random.* 
- *As more bonds are added, clusters of points are formed.*
- *Ultimately the clusters joint to form a cluster which spans the entire system.* 


## Types of Gels
- **Physical gels**
	 the bonds linking the subunits are **physical interactions**.
	 \*Usually the physical interactions are of the form that are disrupted by increasing the temperature, therefore physical gels are sometimes also known as ==**thermo-reversible==** gels. 
	
- **Chemical gels**
	 the bonds linking the subunits are **covalent chemical bonds**. 
	 \*To make a chemical gel, one needs **multi-functional** units that can be linked by chemical bonds to make a 3D network. *(Difunctional subunits cannot make a network but only a collection of linear polymers.)*
	![[e405df474709c3deebb58ff41de5d21670878110aa168b2ce07d393a8f19f7aa.png]]
	\*Chemically cross-linked gels have higher rheological properties as compared to physical gels.

## Rigidness of Gel
![[54838ead673491d4844bd62886b53bf7f4b62b91c29fad1c9e7f3d2f0a262556.png]]

- **Reacting monomers**
	 Materials such as epoxy resins are formed from a **resin**, which is a short polymer with reactive groups on both ends, and a **hardener**, which consists of a multi-functional molecule that can react with up to four resin end groups. 
	 When the resin and hardener are mixed the resin molecules are linked together to form a three-dimensional network. 
	 The increase in effective relative molecular mass of the growing clusters generally leads to a transition into the **glassy state**, so when cured epoxy resins are hard, stiff materials. 
	
- **Crosslinking polymers**
	 We can also begin with long, linear polymers which we subsequently cross-link instead of starting out with small units which polymerise. 
	 The basic idea is that one starts with an entangled melt of linear polymers; adjacent segments are randomly linked. As the density of cross-links increases we expect the modulus of the material to increase. At very high cross-link densities the material becomes glassy. 
	 *e.g. vulcanised rubber*

**Short stiff segments / High cross link density**: $$G=\frac{\rho RT}{M_x}$$ (rigid gel/glassy)
*(from polymer entanglement)*
![[3288117c699367a00e3eb20376b3b733be76a7517ed378ac475014ccc92004b5.png]]
- low M = before gel point = liquid
- high M = reptation model -> rubber plateau
- polymer cross-linked = after gel point = solid

| **特征** | **线性高分子 (Thermoplastic)**     | **交联高分子 (Thermoset/Rubber)** |
| ------ | ----------------------------- | ---------------------------- |
| 长时行为   | 会发生 Reptation，最终流动 (Terminal) | 永久保持橡胶平台 (Stable Plateau)    |
| 模量控制   | 受分子量 $M_w$ 和缠结 $M_e$ 控制       | 受交联点间分子量 $M_x$ 控制            |
| 动态特征   | 低频下 $G'' > G'$ (像液体)          | 即使极低频通常也保持 $G' > G''$        |


# Phase Transition
## Defintion
In soft matter molecular/aggregates interactions are of the order of $k_BT$. Therefore a qualitative system change obtained with a small quantitative variable change *(temperature, surfactant concentration, salt concentration, etc.)*. 
Some time is needed to achieve new morphology equilibrium. If not enough time is given to the system, the system is in **non-equilibrium state**. 

**==Phase transitions reflects the balance between internal energy and entropy.==** 

They can be of:
- **first order**
  discontinuous change of order parameter
  *ice -> water     change abruptly*
- **second order**
  continuous change of the order parameter
  *liquid-gas at critical point*

The phase separation takes some time to occur. Usually **==opalescence==** takes place first. ![[f33ace6cfa75e93f77e0415a1d70fcbef4f408c73133b86958eb17c3b1926842.png]]
*At critical point there are density/concentration fluctuations* 
*-> different refractive index*


## Lattice Theory
- To construct the phase diagram of a binary (polymer) mixture
	each monomer occupies a site in a lattice 
	every monomer (or site) has the same volume
	a polymer occupies many sites
	any site has many neighbour sites in 3D

### Entropy Change
$$A + B \leftrightarrow AB_{mixture}$$
![[73e4ba3762033beeca1de72b18f6fedbfe63f2d9f45bc46a3292ea59d228c755.png]]
Helmholtz free energy: $F=U-TS$
The free energy of mixing: $$F_{mix}=F_{AB}-(F_A+F_B)$$
Volume fraction: $$\phi_A=\frac{V_A}{V_A+V_B},\,\,\,\phi_B=\frac{V_B}{V_A+V_B}=1-\phi_A$$
Define: 
- **lattice site volume** $v_0$ 
- number of sites occupied by one molecule A  $N_A$
- number of sites occupied by one molecule B  $N_B$

Molecular volume: $$v_A=N_Av_0,\,\,\,v_B=N_Bv_0$$Total number of sites: $$n=\frac{v_A+v_B}{v_0}$$
Calculate entropy change using Boltzmann formula:$$S=k_B\ln\Omega$$*$\Omega$: number of microstates - number of all possible arrangements*

The centre of mass of a given molecule can occupy any site in the mixture: $$\Omega_{AB}=n$$Before mixing, molecules are restricted to a fraction of the mixture volume: $$\Omega_A=n\phi_A$$For a single molecule of species A, the entropy change on mixing is: $$\triangle S_A=k_B\ln\Omega_{AB}-k_B\ln\Omega_A=-k\ln\phi_A$$
For the total system (A+B): $$\triangle S_{mix}=n_A\triangle S_A+n_B\triangle S_B=-k_B(n_A\ln\phi_A+n_B\ln\phi_B)$$
The entropy of mixing per lattice site is an intrinsic thermodynamic quantity: $$\triangle \bar{S}_{mix}=\frac{\triangle S_{min}}{n}=-k_B[\frac{\phi_A}{N_A}\ln\phi_A+\frac{\phi_B}{N_B}\ln\phi_B]$$
$\phi=\phi_A=1-\phi_B$: $$\triangle\bar{S}_{mix}=k_B[\frac{\phi}{N_A}\ln\phi+\frac{1-\phi}{N_B}\ln(1-\phi)]$$
In a "**regular solution**" $N_A=N_B=1$, thus$$S_{mix}=-k_B(\phi_A\ln\phi_A+\phi_B\ln\phi_B)$$

### Energy Change
Interactions are considered **pair-wise** between neighbour molecules: $u_{AA},\,\,u_{AB},\,\,u_{BB}$

For one molecule A interacting with one neighbour, use volume fraction as the probability of neighbour: $$U_A=u_{AA}\phi_A+u_{AB}\phi_B$$Same for molecule B: $$U_B=u_{AB}\phi_A+u_{BB}\phi_B$$
In total, with $n$ sites and the **coordination number** $z$ depending on lattice geometry ($\phi=\phi_A=1-\phi_B)$: $$U=\frac{zn}{2}(U_A\phi_A+U_B\phi_B)=\frac{zn}{2}[u_{AA}\phi^2+2u_{AB}\phi(1-\phi)+u_{BB}(1-\phi)^2]$$Before mixing the total energy is: $$U_0=\frac{zn}{2}[u_{AA}\phi+u_{BB}(1-\phi)]$$The total energy change of mixing per site is:$$\triangle\bar{U}_{mix}=\frac{U-U_0}{n}=\frac{z}{2}\phi(1-\phi)(2u_{AB}-u_{AA}-u_{BB})$$
Define the **==Flory's interaction parameter $\mathcal{X}$==**$$\mathcal{X}=\frac{z}{2}\frac{(2u_{AB}-u_{AA}-u_{BB})}{k_BT}$$
Now we get the energy of mixing per lattice site $$\triangle\bar{U}_{mix}=\mathcal{X}\phi(1-\phi)k_BT$$
\*Note: this holds for polymer regular solutions, polymer solutions and blends


### Free Energy Change
$$\triangle\bar{F}_{mix}=\triangle\bar{U}_{mix}-T\triangle\bar{S}_{mix}$$$$=k_BT[\frac{\phi}{N_A}\ln\phi+\frac{1-\phi}{N_B}\ln(1-\phi)+\mathcal{X}\phi(1-\phi)]$$
In regular solution  $N_A=N_B=1$ $$\frac{F_{mix}}{k_BT}=\phi\ln\phi+(1-\phi)\ln(1-\phi)+\mathcal{X}\phi(1-\phi)$$or $$\frac{F_{mix}}{k_BT}=\phi_A\ln\phi_A+\phi_B\ln\phi_B+\mathcal{X}\phi_A\phi_B$$
The free energy of mixing divided by $k_BT$ - volume fraction $\phi$![[8767051bf1fdb0fb105affd990123f70174226be91bfe52577375bf7ae7b0c4d.png]]


## Phase Diagram
- Go from free energy to phase diagram:
	1. In practice $\mathcal{X}=A+\frac{B}{T}$, but $A$ can usually be forgotten;
	2. Find the **minima** of Free energy and plot these minima as a function of $1/\mathcal{X}$ (temperature) to obtain the **binodal** line;
	3. Same thing for the **inflection** points of the free energy to obtain the **spinodal** line. ![[5f9a70c65ae28c06608c8e48b74885e3ae41ea9581f10f4a96f2f34e473bd215.png]]

### Minima - Binodal curve
Since $$\triangle\bar{F}_{mix}=k_BT[\frac{\phi}{N_A}\ln\phi+\frac{1-\phi}{N_B}\ln(1-\phi)+\mathcal{X}\phi(1-\phi)]$$Take derivative to obtain minima of free energy: $$\left(\frac{\partial\triangle\bar{F}_{mix}}{\partial\phi}\right)_{\phi=\phi'}=\left(\frac{\partial\triangle\bar{F}_{mix}}{\partial\phi}\right)_{\phi=\phi''}=0$$$$k_BT[\frac{\ln\phi}{N}-\frac{\ln(1-\phi)}{N}+\mathcal{X}(1-2\phi)]=0$$
Use $N_A=N_B=N$ to simplify, $$\mathcal{X_b}=\frac{1}{2\phi-1}[\frac{\ln\phi}{N}-\frac{\ln(1-\phi)}{N}]=\frac{\ln(\frac{\phi}{1-\phi})}{(2\phi-1)N}$$
Simplify with $\mathcal{X}_b=A+\frac{B}{T_b}$, obtain for binodal $$T_b=\frac{B}{\frac{\ln[{\phi}/(1-\phi)]}{(2\phi-1)N}-A}$$
Outside of Binodal curve is homogeneous region. The system will be thermodynamically **stable**. 
A and B are completely miscible at molecular level, and form a uniform single phase. ![[24c0e72ff57b30bac4b2a4359fea9c66ca31bac872b826f9e857a7f292c4a19d.png]]

### Inflection points - Spinodal curve
Take second derivative to obtain inflection of free energy:$$\frac{\partial^2\triangle\bar{F}_{mix}}{\partial\phi^2}=0=k_BT[\frac{1}{N_A\phi}+\frac{1}{N_B(1-\phi)}-2\mathcal{X}]$$$$\mathcal{X_s}=\frac{1}{2}[\frac{1}{N_A\phi}+\frac{1}{N_B(1-\phi)}]$$Use $\mathcal{X_s}=A+\frac{B}{T_s}$$$T_s=\frac{B}{\frac{1}{2}[\frac{1}{N_A\phi}+\frac{1}{N_B(1-\phi)}]-A}$$
### Critical point
Critical point is at the lowest point in the spinodal curve:$$\frac{\partial\mathcal{X}_s}{\partial\phi}=0=\frac{1}{2}[-\frac{1}{N_A\phi^2}+\frac{1}{N_B(1-\phi)^2}]$$
Taking positive square root $$\phi_c=\frac{\sqrt{N_B}}{\sqrt{N_A}+\sqrt{N_B}}$$Taking the spinodal equation $$\mathcal{X_c}=\frac{1}{2}\frac{(\sqrt{N_A}+\sqrt{N_B})^2}{N_AN_B}=\frac{1}{2}(\frac{1}{\sqrt{N_A}}+\frac{1}{\sqrt{N_B}})^2$$Leading to the critical temperature$$T_c=\frac{B}{\mathcal{X}-A}=\frac{2B}{(\frac{1}{\sqrt{N_A}}+\frac{1}{\sqrt{N_B}})^2-A}$$When $N_A=N_B=N$ $$\phi_c=0.5,\,\,\,\,\,\mathcal{X}_c=\frac{2}{N}$$
For polymer blends (large N): 
-Critical interaction parameter $\mathcal{X}$ is very small for long chains
-> Most polymer blends are phase separated at some concentration range. 
-Only blends with 
- weak repulsion ($0<\mathcal{X}<\mathcal{X}_c$) *(similar chem structure)*
- or with net attraction ($\mathcal{X}<0$) *(hydrogen-bond etc.)*
are homogeneous for broad concentration range


### Information in phase diagram
Outside binodal curve is stable single-phase solution. 
   Thermal motion contributes to stability. 

Between binodal curve is the **Miscibility Gap**. 
- **Unstable region** - two phase
  between the inflection points $\phi_{sp1}$ and $\phi_{sp2}$ 
  Small fluctuations lead to phase separation
  -> **==Spinodal decomposition==**
- **Metastable region**
  between the inflection points and the equilibrium concentration (binodal)
  Large fluctuations are needed to induce phase separation (**==nucleation and growth==** in this case)

For any overall composition in the miscibility gap, the system can minimise the free energy by phase separating into fractions $\phi'$ and $\phi''$ (binodal)

![[281ac6366ef893f770326aa7e12303ecee6e4375a8baab713736d4afd8825f1c.png]]



# Phase Separation
## Scattering experiment
Phase separation takes place via continuous change in composition called **spinodal decomposition**. ![[d9c84dd1b2229fc3ece82da24a59396fd178cb8fe625d5bd5185dd5e5033de93.png]]

 **Scattering interference** is essentially the Fourier Transform of scattering positions in real space. 

The scattering pattern from detector shows the sum of interference by **pair of atoms**. $$I(q)=\sum_{i,j}b_ib_j\exp[-iq\cdot(R_i-R_j)]$$
- b: Scattering Length 原子的本征散射强度

In this way researchers can measure the growth of domains and phase separation kinetics non-destructively.
![[ad6c395c0670509b4ce4099c8441807fc0ecf87225630b52bf193e6ba94253e4.png]]![[8c8e8805b6a977bda25779daf2650bae5bd3e55692a1ae020036654eaa878f9c.png]]


## Nucleation
- Definition: 
	Mixture compositions are **==metastable==**. 
	Separation will occur only if a drop of material will “somehow” occur in the **other coexisting concentration**.

- Types:
	- **Homogeneous**
	   if nucleation occurs via thermal fluctuations
	- **Heterogeneous**
	  if it happens via the presence surfaces (dust of impurities)

- Free energy change:
	**The free energy cost** *to nucleate a particle of size r*:$$\triangle F(r)=\frac{4}{3}\pi r^3\triangle F_v+4\pi r^2\gamma$$
	- $\triangle F_v$: Free energy change per unit volume 
	  (**negative** because nucleation lowers free energy)
	- $\gamma$: Specific surface energy
	  (**positive** because nucleation increases free energy via formation of new surface)
	
	$\triangle F(r)$ has a **maximum** at $r^*$:
	- particles with $r>r^*$ : stable
	- particles with $r<r^*$ : unstable
	
	The probability of **homogeneous nucleation** $$\sim \exp(\frac{-\triangle F^*}{k_BT})$$
	With the energy needed to form nucleus $$\triangle F^*=\frac{16\pi\gamma^3}{3\triangle F_v^2}$$

## Spinodal Decomposition
- Definition:
	Mixture compositions are ==**unstable**==
	Phase separation takes place via continuous change in composition. 
	Local fluctuations in concentration of A create high concentration regions. 
	**Small compositions fluctuations are strongly amplified**:
		Material flows from low concentration regions to high concentration regions governed by the ==**chemical potential**==. *(A prefer to be among A's as that costs less energy)*

- Flux due to Chemical Potential $\mu$:
	The flux of species A due to chemical potential: $$J_A=-M\frac{d(\mu_A-\mu_B)}{dx}$$
	- $\mu=\mu_A-\mu_B$: the energy cost of replacing one molecule A with per one molecule B $$\mu=(\frac{\partial F}{\partial N})_{T,S}$$
	  $N$: number of particles at constant volume
	- $M$: a positive constant
	
	There are also gradient of concentration, so choose F that gives a nice functional form of the free energy: $$\mu=\frac{d}{d\phi}[f_0(\phi)+\kappa(\frac{d\phi}{dx})^2]$$
	Then we have Cahn-Hilliard equation: $$\frac{\partial\phi}{\partial t}=Mf_0''\frac{\partial^2\phi}{\partial x^2}-2M\kappa\frac{\partial^4\phi}{\partial x^4}$$The equation looks like Fick's law with an extra term with an effective diffusion coefficient: $$D_{eff}=Mf_0''$$
	- $f_0''$ can be either positive or negative. But inside the spinodal line it's **negative** since material diffuses from low to high concentrations.  
	
	The solution for the Cahn-Hilliard equation reads in reciprocal space: $$\phi(x,t)=\phi_0+A\cos(qx)\exp[-D_{eff}q^2(1+\frac{2\kappa q^2}{f_0''})t]$$

- Calculation from Scattering Angle:
	In Fourier Transform $q$ is the **Scattering Vector / Momentum Transfer**: $$q=2k_0\sin(\frac{\theta}{2})=\frac{4\pi}{\lambda}\sin(\frac{\theta}{2})$$
	- $\lambda$: wavelength of input
	
	when $\theta\to 0$, $$\sin(\frac{\theta}{2})\to\frac{\theta}{2}\,\,\,\,\,\,q\sim\frac{1}{\lambda}$$
	
	In small angle scattering experiment, the characteristic length of random concentration fluctuations in space $R^*$ is defined as:$$R^*=\frac{2\pi}{q_{max}}$$
	- $q_{max}$: the wavevector where the amplification factor $-D_{eff}q^2(1+\frac{2\kappa q^2}{f_0''})$ has a maximum. 
	  At $q_{max}$ the growing fluctuation in real space is the fastest. 

- Domain Size:
	The selection of the characteristic size ($R^*$) is a competition between **Thermodynamics** (energy penalty) and **Kinetics** (diffusion speed). ![[d7cd60cd47d60a26f732f8c76cf44c17cd8c616c14a563ff7f1b0bcfb2b1c854.png]]
	
	- **Scenario (b) - Wavelength is too long**: The distances for molecules to diffuse are too large, making the process ==kinetically== too slow; thus, growth is insignificant.
	    
	- **Scenario (c) - Wavelength is too short**: Too much ==interface== is created, causing a massive Free Energy Penalty; the system thermodynamically disallows this fluctuation to grow.
	    
	- **Scenario (a) - Golden Wavelength ($R^*$)**: This is the optimal trade-off between diffusion distance and interfacial energy; it grows the fastest and ultimately dominates the material's micro-morphology.

- Ostwald ripening:
	$R^*$ grows with time -> **coarsening** *(particle size increases)*![[4cda02b32cd9a4938a6ae624936ab5bc6339b2027b123115f65e1cc78c75b1c7.png]]
	
	Once started, whether by spinodal decomposition or homogenous nucleation, the domains will grow. ![[55e61ccbfd7f091d918faa1690eb93fd05c86d72f1f50a22aa5a715cfecb72bd.png]]
	- Early stage: difficult to model the aggregation rate
	- **Late stage**: Domain size is much larger than interface width $$R(t)\sim(D\gamma t)^{1/3}$$
		$D$: diffusion coefficient
	
	- How to derive this equation:
		
		Pattern: 
			During growth, observed patterns at time $t$ resembles the patterns at earlier times -> Domains grow **linearly** with time. 
			And we can write for the correlation function.*(Although we cannot easily calculate a complex pattern, we can calculate how domain size R(t) grow.)*
		
		Reason: 
			**concentration close to small droplets is larger than that close to larger droplets.**
			- molecules on the surface of a droplet are energetically less stable than the ones in the bulk
			- larger particles have larger volume to surface molecule ratio
			- and have less particles / volume that can leave the surface and diffuse into the solution
		
		-> Ostwald ripening: $$\phi_{local}\sim\phi_{coex}\sim\frac{\gamma}{r}$$
		- $r$: droplet curvature
		- $\gamma$: surface tension
		![[4145f946efaf9eee15fa5b750e5ebb5f884838515295f14109aa3363c3981501.png]]
		
		Calculation:![[782ac900707dd364005b467784f2a6cc1d13ae587ada8db97ac880f047530204.png]]
		
	- Peak scattering vector $Q_m$: 
		$Q_m=\max{q}$ : $$\frac{\partial[-D_{eff}q^2(1+\frac{2\kappa q^2}{f_0''})t]}{\partial{q}}=0$$$$Q_m=\sqrt\frac{-f_0''}{4\kappa}$$
		![[bad1fbcf1f35a261cd5d88d52feeaefadb3658c6d8d073ecf386596097799c0e.png]]
		The relationship between peak wavevector $Q_m$ and reduced time $\tau$ *(dimensionless)* can be described as $$Q_m\sim R(t)^{-1}\sim\tau^{-1/3}$$


# Self Assembly
## Shape of Micelles
Block copolymers (in bulk) could be observed in different shapes *(spheres, lamellae, cylinders, gyroid, disordered)* 

- **Critical Packing Parameter**
	Decide miclelles' shape $$\frac{V}{a_0l_C}$$![[9d03dc8d42947b4c5285acad3c2a593492039a14a34f5aadd0ebb6c09138bea6.png]]
	- <1/3 - Cone : **spherical** micelles
	- 1/3-1/2 - Truncated cone : **cylindrical** micelles
	- ~1 - Cylinder : **Planar bilayers**
	
	*But aggregates are dynamic, labile* 
	*-not real spheres but fluctuating*


## Chemical potential Theory
### General Equation
Chemical potential of N aggregate:$$\mu_N=\epsilon_N+\frac{k_BT}{N}\ln\frac{X_N}{N}$$
- $\epsilon_N$: the energy change when molecule from bulk solution joins the aggregate
- $X_N$: volume fraction of solute in aggregates containing N molecules (所有含有X个分子的聚集体的总体积分数)
- $\phi$: total volume fraction of solute (所有溶剂分子的体积分数) $$\sum_NX_N=\phi$$
Rearranging $$X_N=N\exp(\frac{N(\mu_N-\epsilon_N)}{k_BT})$$At equilibrium because of equality of chemical potential: $$\mu_1=\mu_N$$ $$\mu=\epsilon_1+\frac{k_BT}{1}\ln{\frac{X_1}{1}}=\epsilon_N+\frac{k_BT}{N}\ln{\frac{X_N}{N}}$$
$$X_N=N[X_1\exp(\frac{(\epsilon_1-\epsilon_N)}{k_BT})]^{N}$$

Now we need to calculate $\epsilon_N(N)$ for a given aggregate morphology: 

### Spherical aggregate
$$\epsilon_N=\epsilon_\infty+\frac{4\pi}{N}(\frac{3Nv}{4\pi})^{2/3}$$
- $\epsilon_\infty$: interactions in bulk of aggregate
- other part: interfacial tension
$$X_N\approx N[X_1\exp[\alpha(1-\frac{1}{N^{1/3}})]]^N$$$$\alpha k_BT=4\pi\gamma(\frac{3v}{4\pi})^{2/3}$$
For large N and also assume for a moment it's valid for N=1$$X_N\approx N[X_1\exp(\alpha)]^N$$
At low concentrations, most of surfactant molecules are isolated in solution and $X_1\sim \text{total surfactant concentration}$

Further increasing concentration of solution, define $$X_1\sim\exp(-\alpha)$$as the **==Critical Aggregation Concentration==** (CAC). After that a good fraction of surfactants are in large aggregates. 
![[5614f3b5a93fd3ce0790e48c68690d5d7a307309cc3823aa0e0bf41d276e93c7.png]]


### Cylindrical aggregates
A amphiphilic molecule that tends to form cylindrical micelles tend to **grow long** because the hydrophobic interactions at the open end cost too much energy:
-> surfactants are forced into round ends in place of “natural” cylinder they would like to form

Take into account the ends $$\epsilon_N=\epsilon_\infty+\frac{\alpha k_BT}{N}$$The equation contains bulk of aggregate and the end cap.
$$X_N=N[X_1\exp\alpha]^N\exp(-\alpha)$$
CAC:$$\phi_c\approx\exp(-\alpha)$$
For concentration far above CMC ($\phi\exp(\alpha)>>1$): $$X_1\approx(1-\frac{1}{\sqrt{\phi\exp(\alpha)}})\exp(-\alpha)$$
A broad distribution with maximum at $$N_{max}=\sqrt{\phi\exp(\alpha)}$$
![[147ccc34f68b3ebc0b37c6f0a101654363a5681842af3793f3f7bccc29663a14.png]]


### Discs aggregates
![[272072f8463ffcd462e9925e8cd5c0cd03e29311763c57b015a106cbd7906378.png]]

The equation contains bulk of aggregate and rim of aggregate: $$\epsilon_N=\epsilon_\infty+\frac{\alpha k_BT}{\sqrt{N}}$$$$X_N=N[X_1\exp(\alpha)]^N\exp(-\alpha N^{1/2})$$
if compared to cylinders : flat aggregates tend to grow **infinitely** *($X_N$ is dependent on N and tends to be infinite)*
That is the reason why such kind of molecules tend to form **vesicles**, to get rid of the rim. 

![[122473060292c39dcf4ed5c763f57464ac27a81117184456b3a576df0105d4ee.png]]
Disc-like micelles of finite radius are **not stable**
For 2D-self-assembly only **infinite aggregates** are stable.


##  Membranes
2D-aggregation -> infinite bilayer

**Persistence Length** - for distances on the membrane $<\xi_k$ the membrane **==looks flat==**:
$$\xi_k = a \exp \left( \frac{4\pi \kappa}{\alpha k_B T} \right)$$
- $\kappa$: Bending rigidity
- $<\xi_k$: large fluctuation, not flat


**Helfrich effective potential** - close to a surface, the membrane cannot take all conformations and entropy decreases, creating a repulsive force described by: $$\triangle F_{Helfrich}\sim\frac{(k_BT)^2}{kd^2}$$

## Interface
Surface tension: 
$$\gamma\sim\frac{k_BT}{a^2}\sqrt{\mathcal{X}}$$
- $a$: Kuhn length
- $\mathcal{X}$: Interaction parameter


In case of lamella, the stretching of chains has to match the interfacial energy. 
The free energy change per chain due to **stretching** can be described as: $$F_{el}\sim k_BT\frac{d^2}{Na^2}$$
**The interfacial free energy** per chain: $$F_{int}=\frac{\gamma Na^3}{d}$$
Adding both terms and minimizing in respect to d $$d\sim(\frac{\gamma a^5}{k_BT})^{1/3}N^{2/3}$$