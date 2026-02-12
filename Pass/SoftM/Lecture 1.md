---
date: 2025-11-10
Prof: Eduardo Mendes
aliases:
  - Intro to Soft Matter
---
# Soft Matter Definition
- A subfield of condensed matter comprising a variety of physical states that are easily deformed by thermal stresses or thermal fluctuations. 
- They include **liquids, colloids, polymers, foams, gels, granular materials, and a number of biological materials**. 
- These materials share an important common feature: predominant physical behaviours occur at an energy scale comparable with ==**room temperature thermal energy**==. ( $E_k=k_BT$ )


# Forces, Energies and Timescales
## Intermolecular forces
- Van der Waals forces: The derivative of **van der Waals Potential** (Intermolecular potential) $$F=-\frac{dU}{dt}$$$F$ : The force between two molecules, or colloid particles mediated by the solvent.  ![[56be8b142872e756e197818a73654beb9b5cf4a038d714e06c1276016d0ddc5c.png]]
- *Short range repulsion:* 
	*quantum mechanical origin (Pauli's exclusion principle)*
	*usually idealized with hard sphere potential ( $\approx\infty$ )*
- *Long range attraction:*
	*origin on fluctuating dipole-dipole interactions*


- **van der Waals attraction part** *(uncharged particles)*: $$U_{dis}\sim\frac{\alpha^2}{r^6}$$ where $\alpha$ is **polarizability**, 
  $r$ is distances between molecules
  
  \* The order of magnitude of the strength of the interaction between two molecules in contact is around $10^{-20}J$, which is the same order of magnitude as thermal energy $k_BT$ at room temperature. 


- **Ionic forces** (Coulomb): $$U_C=\frac{q_1q_2}{4\pi\epsilon_0r}$$ where $U_C$ is Coulomb potential. Ions carry charges $q_1$ and $q_2$ at separation $r$.  ~ $100\times10^{-20}J$. BUT can be **screened** in solution and take a window of values. 


- **Covalent bonds**: Electron shared between 2 atomic nuclei. $30-100\times10^{-20}J$. Covalent bonding is short-ranged and highly directional. 


- **Hydrogen bonds**: $2-6\times10^{-20}J>k_BT$ 


- **Hydrophobic interaction**: Each individual solute molecule is surrounded by a solvent cage as solvent re-arrange around the solute. Organization of solvent molecules around the solute decreases entropy, favouring aggregation. This decrease in entropy leads to attraction forces of $\sim 10^{-20}J \sim k_BT$. 


## Viscous, elastic, and viscoelastic behaviour
### Hookean Solid & Newtonian Liquid
The response of matter to a shear stress:![[fdc6a770e748a7f9079f3ae9380c181180fa799a0d698eeb2c0545ab79505dac.png]]

- For a **Hookean** solid
	Ideally **elastic** - an applied shear stress produces a shear strain in response, which is proportional to shear stress, and the constant of proportionality is the **shear modulus** $G$: $$G=\frac{\sigma}{e}$$ where $\sigma$ is shear stress$$\sigma=\frac{F}{A}$$ $e$ is shear strain$$e=\frac{\triangle x}{y}$$
- For a **Newtonian** liquid
	Ideal liquid - an applied shear stress produces a flow with a **constant** shear strain rate in response, which is proportional to the shear stress, and the constant of proportionality is the **viscosity**. 
	Shear strain $$e=\frac{v}{y}$$ where $v$ is the relative velocity, $y$ is the distance in between. The velocity gradient $v/y$ is in fact identical to the time derivative of the shear strain.
	
	The Newtonian viscosity $$\eta=\frac{\sigma}{\dot{e}}$$ $$\eta=\frac{\sigma}{\dot{e}}=\frac{F/A}{v/y}$$So the resisting force due to viscosity is: $$F=A\,\eta\,\frac{v}{y}$$
	Shear modulus$$G=\frac{\eta}{\tau}$$ where $\tau$ is the relaxation time. 


### Timescales of matter response
Soft matters often behave in a way that combines viscous and elastic response, with an additional dependence on timescale. 

**Viscoelasticity**:
- If shear is applied fast rate - responds like a solid; 
- If shear is applied in slow rate - flows like a liquid. 

**Relaxation time** $\tau$:
- A characteristic time that separates two behaviour. 
- Depends on the system. 

![[abd7a7288113d4355ea1a7fd6c885d5747f41ff81f261a0d5faf63ba1ece1851.png]]

Soft matter exhibits viscoelastic behaviour, but get often more complex with ==non-linear== behaviour. $$\sigma=\eta(\dot{e})\,\dot{e}$$
- (a) Newtonian
- (b) **Shear-thinning** 
  *(paint: easy to brush, uneasy to sag under its own weight)*
- (c) **Shear-thickening** 
  *(pastes with rather a high volume fraction of particles)*
![[ab0f9b72e1d80419df797515c823d7b07ccddc03ced046166a5f187e4d35ac5c.png]]

For a steady flow, we can generalise and get: $$\sigma=\eta(\dot{e})\,\dot{e}$$ where $\eta(\dot{e})$ is a shear-rate dependent viscosity. 


### Mechanical response of matter at a Molecular Level
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
- $\epsilon$ is the **energy barrier**
	usually $\epsilon\sim 0.4\epsilon'$ (the **latent heat of vaporisation**)
	unit $[J/mol]$ !
	leading to $\tau\sim 10^{-12\sim -10}s$
- Boltzmann factor $exp(-\frac{\epsilon}{kT})$
	 = probability of scape. 


Using $\eta\sim G_0\tau$:
$$\eta=\frac{G_0}{v}exp(\frac{\epsilon}{kT})$$
It is related to the ability of vibrations to overcome the caging effect. 

\*BUT this behaviour breaks down **at lower temperatures**, where the system exhibits a much stronger dependence...and the liquid approaches the **glass transition temperature**. 


## Liquids and Glasses
Glass is an amorphous solid. Liquids can become amorphous solids as the temperature is lowered, provides it does not crystallize (density difference between glass and liquid is very small).

Close to glass transition temperature, viscosity is better described by the phenomenological(/experimental) **==Vogel-Fulcher Law==**: $$\eta=\eta_0\,exp(\frac{B}{T-T_0})$$ where $T_0$ is the Vogel-Fulcher temperature. 

**==Cooperativity==**
	at these lower temperatures, viscosity is governed by rearrangements of neighbouring molecules that provide "space" for movement. 


If viscosity goes to infinite for a glass, it should take a long time to measure it (way longer than **experimental time** $\tau_{exp}$) . 
So we measure **DENSITY** instead of shear modulus appearance. 

![[a418fda1c71c8e7d189ef823b0b24c4b14d46229ff1d9df4920ad5400f8353ae.png]]
![[450d0c36d4aee10dcfe1fe3703b8b3af9c6fe640f7dda148bece36f2f2920f5d.png]]
![[f5a041ede69cb20427f0ee00b87082635f97d00df8ade1ec614d8c181e872060.png]]
-> Density of Glass slightly lower than crystal 
-> Extra "space" between atoms

### Explanation
- **Glass state:**
	As a material cools, molecules attempt to rearrange into a highly organised **crystalline solid state**. However, typical cooling speeds are too fast to allow for this perfect alignment.Due to rapid cooling, the material enters a **glass state** instead. In this state, the structure is less organized (amorphous) and contains "extra space" between atoms.
  
- **Density Differences:** 
	Because of the extra internal space, the density of glass is lower than its crystalline counterpart. The faster the cooling process, the less time molecules have to pack together, resulting in an even lower density in the final glass.

- **Structural Degradation:**
	Since the crystalline state represents the **lowest free energy** (most stable) state, the molecules naturally try to move toward it over time to eliminate that extra space. This slow, ongoing movement of molecules toward a more stable state is what we observe macroscopically as **degradation** or structural aging.


Assume **free volume** between atoms is $v_f$ , and microscopically thermal expansion mimics macroscopic world, the fraction of free volume in sample of total volume is: $$\frac{v_f}{v}=f_g+\alpha_f(T-T_g)$$ where:
	$v$ : total volume
	$f_g$ : fraction of free volume at $T_g$ 
	$\alpha_f$ : thermal expansion coefficient


Assume that the viscosity close to $T_g$ still has the Arrhenius form, but
instead of relating probability of molecular movement to Temperature, assume that movement comes from **excess of free volume** that promotes molecular re-arrangements: $$\eta=a\,exp(\frac{bv}{v_f})$$ Here we can recover the Vogel-Fulcher law. 



# Conceptual questions

1. **What is Soft Condensed Matter?**
	Soft matter systems (colloids, emulsions, biological tissue, glasses, etc.) represent a class of materials in which material structure is dictated by their environment(solvent) and mediated by thermal motion(kT). The properties of these materials is closely related to their structure and often distributed with a probability which is linked to the thermal energy(exp(-E/kT)). 

2. **What is relaxation time in Soft Matter Systems?**
	The time taken by a soft material to adjust/respond to an applied stress (physical or thermal) through molecular or atomic rearrangement. 

3. **Explain ‘Experimental Time’ in relation to ‘Relaxation time’ in soft matter systems.**
	The experimental time is the amount of time needed to observe a response or change in configuration in soft matter systems. 
	Depending on the time of observation different properties from the same material maybe obtained. For example, cornstarch slurry in water behaves like a solid at low experimental time scales as opposed to being a liquid material at longer time intervals. 

4. **Why does Arrhenius viscosity break down at lower temperatures?**
	The Arrhenius viscosity breaks down at lower temperatures due to the formation of a glassy state which is a solid of infinite apparent viscosity but in reality the timescale of the observation is not long enough to observe the flow of such a material. 

5. **What is glassy state?**
	The glassy state is a state of matter in which a liquid is cooled fast enough that it forms an amorphous state of lower density as compared to that of a crystal. 

6. The Lennard-Jones potential is a pair-wise potential. Explain why it still gives a good description of Young’s modulus for a solid even when, in a solid, there are many neighbours around a given atom, all interacting at the same time. 
	   **Lennard-Jones Potential**: $$U(r) = 4\epsilon \left[ \left( \frac{\sigma}{r} \right)^{12} - \left( \frac{\sigma}{r} \right)^6 \right]$$
	![[2347af2bd45c4860ce077283311e30f5c3bc2d4b71c1542f744b43d8d3b12faf.png]]
	
	Answer: ![[e312c8bca1e61c40bf30a06289cd153e4ceea66159a7e366c0551bdb8b674d3d.png]]
	The above is a schematic of the periodic potential of a lattice of a metallic solid. As observed the atoms (marked by black dots) rest on the deep well in the potential that is at the equilibrium distance of atoms. The Lennard-Jones potential is a pair-wise potential that approximates the potential of the entire solid by including only the interactions of the nearest neighbours while neglecting others. By neglecting the higher order terms in the representation of the potential, we only shift the depth of the well by a scaling factor and not change the behaviour of the material. Hence it is sufficient to explain the youngs modulus of the material. 