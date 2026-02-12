---
date: 2026-01-05
Prof: Tom McCoy
aliases:
  - Surfactants
---
# Intro of Surfactants
## First Principles
*Example - sodium dodecyl sulfate (sodium lauryl sulfate)*
Surfactant - a surface active agent

Key effect:
	disruption of the attractions between water molecules at the interface, reducing surface tension.

Surface tension - Concentration:
	As more surfactant molecules partition to the interface, surface tension continues to drop… until CMC(critical micelle concentration)![[26e5e7c123d6469b05521967bd84520271eb3ac667b8cbe8657d60baf5c9ee0f.png]]

- Anionic surfactant (-): **SDS** (Sodium Dodecyl Sulfate)
	-**Detergents**
- Cationic surfactant (+): **CTAB** (Cetyltrimethylammonium Bromide)
	-**Hair conditioners / fabric softeners**
- Nonionic surfactant (0): **Triton X-100**
	-**Vaccines**


## Air/Water Adsorption
### The Gibbs dividing surface
Surfactant concentration - Distance to interface:![[7426c3798a6987da0e430f2140dea5850f9d18eae32ebeb2e9e638f4e383ef39.png]]

Derivation of the Gibbs eq *(beyond the scope of this course)*: ![[7f44a17d86791ac5276225f1bcb847b3c90f69eedd22a2e4e47eefa9b4ffc6f4.png]]
\* the Gibbs equation only applied BEFORE the CMC

- The Gibbs equation directly relates a measurable quantity (surface tension) to the number of molecules adsorbed at the interface.
- If you know the number of molecules at the interface, it’s only a quick step to calculate how much **space** each one takes up.
- Entity know as the **area per head group** (in Å$^2$)


At the CMC, where the air-water interface is as packed as it can possibly be, it’s like there is a ‘film’ of surfactant tail-groups.![[d9b879f809c6d8d21c1383669c6ab87baae7831476084fbbb31fcc9a77584d2e.png]]

### Surface excess
So, according to the Gibbs model, as bulk concentration increases, partitioning thermodynamics dictate that more surfactant is driven to the interface.

Until the interface is packed. And then micellisation happens. ![[7bae5405d43cf8bbda307b2e0b0f939557259323915af50ccfcad5d3d0b2a1d5.png]]



## Self-assembly
A spontaneous process, but 
	Entropy and the arrow of time resist the spontaneous formation of order. 
	And bringing all of those (charged) head-groups into close proximity is unfavourable

Answer:
	Spontaneous requires $ΔG = ΔH − TΔS < 0$ 
	- The **entropy of water increases** when micelles are formed. ($ΔS>0$)
	- The entropy of surfactant decreases due to ordering of surfactant molecules and the electrostatic repulsion between head groups. ($ΔS<0$)
	- Favorable enthalpic contributions($ΔH>0$, not always)
-> In total $ΔG<0$


- Various micelles![[303acecdce75bf1f059497e646ced256fee6f2a77582d3dadaf57d3f76dfb983.png]]


# Surfactants in Industry
In the real world, industrialists who use surfactants are less concerned with fundamental thermodynamics.

## Efficiency and effectiveness
- **Surfactant efficiency**: describes the concentration that is required to induce a specific drop in surface tension – usually 20 $mNm^{–1}$. 
- **Surfactant effectiveness**: the maximum decrease in surface tension that is possible for a surfactant, ==regardless of concentration==

- Efficiency is driven by raw **thermodynamics** (partitioning to the interface).
- Effectiveness is determined by **how dense a film** the surfactants can pack into at the interface.
![[b55925cb097ab405d40c1aa082a528d29b4a9c6b0bcb71f586442079ed4e927d.png]]


- Most surfactants with unbranched hydrocarbon tails have a limiting surface tension of ~35 +/– 5 $mNm^{–1}$. 
	With branched hydrocarbon tails the density of the film will be larger -> **increase effectiveness**
	*(could be inverse influenced if too branched -> decrease effectiveness)*
	With unbranched tails the straight chains pack into a **densely packed, saturated monolayer** at the interface, beyond which **further adsorption is impossible** and the interfacial free energy can no longer be reduced.
	
- Ionics tend to be slightly higher in surface tension than nonionics.
	Electrostatic repulsion between charged head groups limits how densely they can pack at the interface
	
- Surfactants with perfluorocarbon tail-groups tend to have lower CMC. 
	C-F keys are more hydrophobic. 
	


## Surfactant selection
The best surfactant for a given application will depend on many physical and chemical features:
- Efficiency and effectiveness,
- CMC
- Physical state (pour point, melting point),
- Chemical resistance (hydrolysis),
- Solubility in respective phases,
- _etc_.

### Some classic surfactants
![[8c33e94b2f435efc54e3d837abc0e9b8e758f8ab0677de5381e04f45826927d4.png]]
![[07f936267a3b629fd2443412a2b96027b40382eb1b9654753007f47396103999.png]]
![[c84b08a67d1a38a45d9420f323aa3d69639b048cac6b83894859ffac66ade91c.png]]
![[5db5651ff21bd850089137217ba83fe982588fa69116c19d21ec12c00ec0f105.png]]
*Most effective but banned(not environmental friendly):* ![[9849ecc8884b0fc6e2591236c366177b020c52b9d45082ceef8bc2d491ea59e4.png]]


## HLB (Hydrophilic-Lipophilic Balance)
essentially determines how much the surfactant likes water.
$$\text{HLB}=20\times \frac{M_{headgroup}}{M_{total}}$$
tends to work best for **nonionic** surfactants. 
![[6fc158414c4757d8b85aaaf617737abf1617c5602f3a968a4dd0ae79b5a6a0c5.png]]


## Kraffty Point
- Many surfactants experience a temperature at which their solubility in water suddenly increases.
- This results from a transition between hydrated crystals to a micellar solution, and has clear thermodynamic foundations.
- Below the Krafft point temperature, there is **no CMC** (micelles cannot form).
- Engineers might like to consider similarities with upper critical solution temperature (UCST)
 *-> To use a certain kind of surfactant, the expected temperature for use should be higher than Kraffty point.* 


## Cloud point
- a temperature above which solubility suddenly decreases. 
- Common for surfactants with **nonionic** poly(ethylene glycol) head-groups, as PEG tends to experience reverse solubility.
- Arises from **PEG shedding its hydrating water** (*hydrogen bonds break*), and becoming more ‘hydrophobic’ thus resulting in sudden attractions between micelles.


## Packing Parameter
Often use a temperature/concentration phase diagram to show which phases occur and when.![[8afdc8e43e229c693ea5c833a2959d9693f792c47151449147862eb28cdafc32.png]]

**Packing parameter**: $$N_S=\frac{V_C}{\alpha\cdot L_C}$$a simple way to predict the preferred curvature that a surfactant aggregate will take, and therefore the phase.
- $\alpha$: the area occupied by a head-group
- $V_C$: the volume of the tail-group chain(s)
- $L_C$: the length of the tail-group chain(s)

Clearly the relative size of the head and tail group will result in different geometries that can pack differently. ![[156467d1c7a94a480cb6ed604caab717d6f1f9d6de8b0eb6a650488fff49ba0d.png]]
\* For Ionic tail groups $\alpha$ might be larger (repel others)


## Interfacial tensions
Interfacial tention - salt concentration: 
![[f06ff6a999e0d9b445634550ed64b095e4e78d738c71d9c924b230a7ddab807c.png]]

- **Decreasing** <- The ==charged screening== of ionic surfactant molecules becomes less. The surfactant film becomes denser.
- **Increasing** <- After passing the ideal point the surfactant molecules get ==de-wetted== as water interacts more with salt. The surfactant concentration at the surface decreases. 