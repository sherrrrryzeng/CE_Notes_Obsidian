---
date: 2025-11-17
Prof: Pouyan Boukany
aliases:
  - Polymers
---
# Polymer Introduction
Definition: A giant molecule made up of many repeat units covalently joined together in the form of a long chain. 

State: liquid, glass, crystal, liquid crystal
*not gas/vapor (Decompose before the evaporation temperature)*

## Stereochemistry
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


### Structure Differences
- **Main molecule**: 
   Giant molecules usually with **==carbons==** building the backbone
   exceptions exist (e.g., Si, N)
- **Molecule structures**: **==Isomers==** of polymers - tacticity
- **Chain structures**: *Linear chains, branched chains, ladders, networks, dendrimers* ![[4240569c109721c8983ecd3d1b0c8d1992557f866d87075b31f9a8c7bffae9ee.png]]
- **Chain sequence**: Homopolymers, copolymers, random copolymers, microphase-separated polymers (like amphiphilic polymers)

-> Polymers are very heterogeneous class of materials


## Molecular Weight and Distribution
Synthetic polymers are made by processes that yield not a single degree of polymerisation, but a distribution:

- Number-average molecular weight: $$M_n=\frac{\sum n_iM_i}{\sum n_i}$$
- Weight-average molecular weight:$$M_w=\frac{\sum w_iM_i}{\sum w_i}=\frac{\sum n_iM_i^2}{\sum n_iM_i}$$
- **Poly-dispersity Index(PDI):** $$\frac{M_w}{M_n}$$

# Random Walks
## Ideal Chain Model
Under equilibrium polymers are in **coil** shape
![[8993fbe6a505c8c290e5e00beec278c39098cc79b3a50966f995a19e45f6e7a5.png]]
- $N$: degree of polymerization
- $a$: length defined by chemical bonds
- $R$: end-to-end vector that describes a coil made up of N jump vectors $a_i$ 


Ideal polymer chain model **assumptions**:
1. Consider random steps of equal length $a$ defined by chemical bonds.
2. The segments can rotate freely around the bond.


### End-to-End Distance
$$R=a_1+a_2+...+a_N=\sum^N_{i=1}a_i$$ The average over the polymer chain is: $$<R>=0$$
The mean square displacement (MSD) is: $$<R^2>=<\sum_{i=1}^N a_i\cdot\sum^N_{j=1} a_j>=<\sum_{i=1}^N\sum^N_{j=1} a_ia_j>$$ $$=Na^2+2a^2\sum_{i=1}^{N-1}\sum^N_{j=i+1}\cos\theta_{ij}$$
For a freely jointed chain the average of the cross term $$<\sum_{i\neq j}^N a_ia_j>=0$$ then $$<R^2>=Na^2$$

From Brownian motion we have: $<R^2>=6Dt$ 

**The radius of gyration**: the RMS distance of the collection of atoms from their common center of gravity$$R_g=\sqrt{\frac{<R^2>}{6}}=a\sqrt{\frac{N}{6}}$$

## Real Chains
In real chains there are 
- **Excluded volume effects** *($\cos\theta$ not random but a finite value)*
- **Steric limitations** *(side groups, interactions, etc.)*


Recall that $$<R^2>=Na^2+2a^2\sum_{i=1}^{N-1}\sum^N_{j=i+1}\cos\theta_{ij}$$ Correlation between bond vectors: $$<a_i\cdot a_{i-m}>=a^2cos^m\theta$$ $$lim_{|i-j|\to\infty}<\cos\theta_{ij}>=0$$-> The correlation between bond vectors "dies" with increasing separation. 


Replace the **monomer size** $a$ with an effective monomer size
$b$ : ==**Statistical step length== or ==Kuhn segment**== $$<R^2>=C_{\infty}Na^2=Nb^2$$
==**Flory Characteristic Ratio==**: $$C_{\infty}=\frac{b^2}{a^2}$$
-> After renormalization, this relation holds for all flexible linear polymers.


### End-to-end Distribution Function
The Gaussian distribution of R: $$P(R)=(\frac{2\pi Na^2}{3})^{-2/3}exp(-\frac{3R^2}{2Na^2})$$
3D distribution: $$P(R,N)=(\frac{2\pi<R^2>}{3})^{-2/3}exp(-\frac{3R^2}{2<R^2>})$$

### Entropic effects in a Gaussian Coil
Boltzmann equation: $$S=k_bln\Omega$$  $\Omega$ : statistical weight

The **entropy** of a Gaussian coil: $$ln(P(R))=ln\Omega$$ $$S(R)=\frac{3k_bR^2}{2Na^2}+\text{constant}$$
\* Entropy decreases with the stretching (increasing order), like springs 


When the entropy is known as a function of chain elongation, we can get the **free energy** from a random walk model: $$G(R)=U-TS=-\frac{3k_bTR^2}{2Na^2}+\text{constant}$$ *(not only Gibbs but also other type of free energy)*


The **force** required to stretch or compress the chain is: $$F(R)=\frac{\partial G}{\partial R}=\frac{3k_bTR}{Na^2}$$
The **"spring constant"** is: $$\frac{\partial^2G}{\partial R^2}=\frac{\partial F}{\partial R}=\frac{3k_bT}{Na^2}$$
The spring constant increase with T(easier to pull with low temperature), decrease with N(easier to pull long polymers).
*Unlike a traditional energetic spring where stiffness comes from internal energy U.*

Now all is based on conformational entropy, no interaction energies are accounted for yet.


### The Excluded Volume Effect
Steric hindrance on short distances limits the number of conformations.
At longer distances, we have a topological constraint: **the self-avoiding walk or the excluded volume effect**. 

Instead of $<R>=aN^{0.5}$, we will have $$<R>=aN^v$$ where $v>0.5$. Experimental data discovered that $v\approx 0.6$ 

Derivation:
![[a3aa4693a510d5e7df5ba0bd416124a61f4d7b6d41ef1d5cac238d6ad2fc6135.png]]

Flory's result for the Swollen Coil:
$$G_{tot}(R)=G_{rep}+G_{el}+\text{constant}$$ $$=\frac{k_bvTN^2}{R^3}+\frac{3k_bTR^2}{2Na^2}+\text{constant}$$ 
where $G_{rep}$ is from **excluded volume**, $G_{el}$ from **elastic entropy**. 

The sum of repulsive and elastic free energy goes to minimum: $$\frac{dG_{tot}}{dR}=-\frac{3k_bvTN^2}{R^4}+\frac{3k_bTR}{Na^2}=0$$ $$R^5=a^2vN^3$$ $v\approx a^3$, then$$R\approx aN^{3/5}=aN^{0.6}$$

# Dynamic Properties
To get the viscosity, diffusion, and a quantitative microscopic description for observed macroscopic properties. 

## Rouse Model: Bead-Spring Concepts
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

The effect on Viscosity:![[a40f2296283992e62cbcfe398e1c44870515379b041cba22b5bbd5b73b22d267.png]]


# Tutorial Conceptual questions

1. What is the tacticity of a polymer? What are the different types? Which tacticity do you think a highly crystalline polymer could have?
	Tacticity describes how the side groups on the polymer backbone are arranged in space. It's a stereochemical property. 
	The different types are:
	- Isotactic
	- Syndiotactic
	- Atactic
	A highly crystalline polymer could have either isotactic or syndiotactic arrangement. 
	
2. Explain in your own words what is Kuhn length and contour length. What relation does it have with the end-to-end distance of a polymer?
	For the correlations of real chains, we replace monomer length with an effective segment length, which is the Kuhn length $b$ . It means the length of an equivalent freely jointed segment that reproduced the real chain's statistic. 
	The contour length $L$ is the fully stretched length of the polymer. 
	The relation with the end-to-end distance of a polymer is $$<R^2>=C_\infty Na^2=Nb^2$$
	where $C_\infty$ is Flory's characteristic ratio.
	
3. What is the radius of gyration of a polymer? How does it relate to the polymer end-to- end distance (R)?
	The radius of gyration of a polymer is defined as the root-mean-square-distance of all monomers from the chain's center of mass. For a Gaussian coil:$$R_g=\sqrt{\frac{<R^2>}{6}}$$
	
4. Explain the difference between good, theta and poor solvents. How does the end-to-end distance (R) correlate with the number of monomers (N) in these systems?
	Polymer segments prefer the good solvents, in which polymer chains swells by the excluded-volume exponent $v\approx 0.6$. The correlation equation is$$R\sim N^{0.6}$$
	In theta solvent polymer-solvent interactions cancel excluded volume effects. So the system is similar to ideal chain model, where $$R\sim N^{0.5}$$
	In poor solvent monomer-monomer attraction dominates and chain collapses into a globule. Scaling: $$R\sim N^{1/3}$$
	
5. What are the Rouse and reptation models? Under which circumstances would you invoke them?
	The Rouse model treats polymer as beads connected by springs, which is applicable to short chains in melt. It predicts diffusion and relaxation scaling like $$\tau_R\sim N^2$$
	The reptation model considers chains as being constrained to move inside a "tube" formed by surrounding chains, which applied to long, entangled polymer melts. It predicts relaxation time scales like $$\tau_d \sim N^{3\sim 3.4}$$


