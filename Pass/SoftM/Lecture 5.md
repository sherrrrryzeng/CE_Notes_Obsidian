---
date: 2025-11-24
Prof: Pouyan Boukany
aliases:
  - Gels
---
# Intro of Gels 
## Definition of Gels
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


### Example - Gelatine
Formed from **collagen**, a protein found in animals.
When collagen is heated, it breaks down into the protein **gelatin**.

- In water, gelatine swells, forming a polymer solution (*liquid*).
- At low temperature: gelatine + water forms a solid (*gel*) — the water is trapped in a loose polymer network structure.

- The system of gelatine+water is **thermo-reversible**
- Collagen molecules have cross-links from their **helix formation**. 

![[45ab78ee528806d5931d0b5d6225ab0d98507af5d8b15b36c06d6a73f10a75d8.png]]


## Transition from liquid-like to solid-like behaviour
- Development of a **shear modulus** at zero frequency $\omega=0$ 
- Development of **infinite viscosity** ($\dot{e}=\frac{v}{y}=0$)

Hookean solid -> Newtonian liquid:
Shear stress $$\sigma=\frac{F}{A}$$ Shear strain $$e=\frac{\triangle x}{y}$$ Hookean solid - Shear modulus $$G=\frac{\sigma}{e}$$ Newtonian liquid - Shear viscosity $$\eta=\frac{\sigma}{\dot{e}}$$

### Experiment methods
- **Rheology experiment** ($G\neq 0$)
	Measuring the Gel Point when the transition from liquid-like to solid-like behaviour happens
	-> development of a shear modulus ($\omega$=0)
	**Winter-Chambon method**: 
	 at the gel point  $$G(t)=St^{-n}$$![[3712abd9e5ba5d47fc5e0394d4ba4d275717f614a7812b2bcced88c12bb9739a.png]]
	 
- Falling ball
- TTT (tilt-test-tube)


## Flory-Stockmayer Model / Percolation Theory
The classical theory of Gelation - **Cayley tree**
![[dcd15e54a258af628049e510f91ee304dac4d7b11b2b6bf61310d3e558aea5ff.png]]
$$N\sim f(z-1)^n$$
Critical value - **percolation threshold** $f_c$ : $$f_c=\frac{1}{z-1}$$
As the number of generations n goes to infinity we n find two types of behaviour, depending on f: $$\text{if }\,\,f<f_c:N\to0\,\,\,\,\,as\,\,\,\,\,n\to \infty$$ -> below percolation threshold we have a solution of finite clusters - **a sol.** 
 $$\text{if }\,\,f>f_c:N\to\infty\,\,\,\,\,as\,\,\,\,\,n\to \infty$$
 -> above the percolation threshold we have an infinite cluster - **a gel**, which has a finite shear modulus. 


- At the gelation point an infinite cluster is created that spans the whole system. 
- The macroscopic properties changes abruptly from liquid-like to solid-like. 

**Connectivity transition**: 
Gelation can be described as a connectivity transition --- bond percolation problem
![[95886dc69fc766b2ba509004e60f263e21bbdc205110e42238630b2533092bee.png]]
- *We start with array of points, to which bonds are added at random.* 
- *As more bonds are added, clusters of points are formed.*
- *Ultimately the clusters joint to form a cluster which spans the entire system.* 


Define p: **probability of bond to neighbour**$$p<p_c \to sol\,\,\,\,\,\,\,\,\,\,p>p_c \to gel$$
In general the problem does not have an analytical solution, from experience:
- triangular lattice $p_c\approx 0.347$
- square lattice $p_c\approx 0.5$


**The gel-fraction**:![[7ea442cef24d9a2fb6e5328a8d169282843886cc68d75523254158430ac620fd.png]]
*The gel fraction abruptly rises from zero at the gel point;*
*close to the gel point the gel fraction can be expanded as a power law function of the distance away from the gel point.* 
\*Gelation is a continuous transition.


# Gel Family

## Types of Gels
- **Physical gels**
	 the bonds linking the subunits are physical interactions.
	 \*Usually the physical interactions are of the form that are disrupted by increasing the temperature, therefore physical gels are sometimes also known as ==**thermo-reversible==** gels. 
	
- **Chemical gels**
	 the bonds linking the subunits are covalent chemical bonds. 
	 \*To make a chemical gel, one needs **multi-functional** units that can be linked by chemical bonds to make a 3D network. *(Difunctional subunits cannot make a network but only a collection of linear polymers.)*
	
![[e405df474709c3deebb58ff41de5d21670878110aa168b2ce07d393a8f19f7aa.png]]

\*Chemically cross-linked gels have higher rheological properties as compared to physical gels.

### Chemical Gels
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


# 3D Bioprinter / Hydrogels
![[78484e4fa573fcd13d8ee65165253e74dd6b94413010fd64dbbf524c3e2740ee.png]]


# Tutorial Conceptual Questions

1. **What is reptation time? Does it exist only in melts? How does it vary with entanglements?**
	  In reptation model, reptation time $τ_d$​ is the time taken by a polymer chain to 'reptate' or navigate through an imaginary 'tube' formed by entanglements, which results in stress relaxation (also known as the terminal time $T_t$​).
     The phenomenon of reptation is primarily found in long-chain polymer melts , but it also occurs in concentrated polymer solutions. 
     The reptation time depends strongly on molecular weights (N). As the number of entanglements increases, the length of the imaginary tube increases, leading to an increase in the reptation time. According to the tube model $$\tau_d\sim N^3$$ which is close to the experimental results. 
     According to a power law $$T_t\sim N^{3.4}$$

2. **Explain in your own words what a gel is. What are two kinds of gels based on interactions? How can you experimentally study if gelation has occurred? Give some real life examples of food materials that form a gel. What is the method of gelation in these materials?**
	 A gel is a material composed of subunits that are able to bond with each other to form a network of macroscopic dimensions, in which all subunits are connected by bonds. A gel exhibits the mechanical properties characteristic of a solid, such as the ability to sustain shear stress with a spanning network , even though it may contain a high volume fraction of liquid solvent. 
	 *Solution: A gel is a soft material that has a network structure with viscoelastic behavior.*
	
	Based on interactions there are chemical gels and physical gels. 
	*Chemical gels consists of networks cross-linked by covalent bonds; physical gels are formed by non-covalent interactions such as hydrogen bonds, van der Waals forces, etc.*
	*Chemically cross-linked gels have higher rheological properties as compared to physical gels.*
	
	Example: Gelatin
	Gelatin is a common example for a food material that is used to make flavoured jellys (gels). The lowering of temperature aids in the formation of a gel. Gelatin gels are thermo-reversible and form a sol upon heating. 
	
	
3. **What is the process of gelation? Sketch the dependence of the shear modulus with time before the gel point, at the gel point, and after the gel point.**
	 The process of gelation:
	 - We start with individual subunits, to which bonds are added at random.
	 - As the bonds between subunits increase, clusters of points are formed.
	 - Ultimately the clusters joint to form a cluster which spans the entire system. The gel fraction abruptly rises from zero at the gel point. 
	
	log(G(t))~log(t):![[c96cf4eca0e5a343b07607c75b4bf5dcccb8f6d6095ffdf387b27e1b21d55645.png]]
	- *a: before the gel point*
	- *b: at the gel point*
	- *c: after the gel point*


