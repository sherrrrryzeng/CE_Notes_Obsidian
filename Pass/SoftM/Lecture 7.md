---
date: 2025-12-01
Prof: Eduardo Mendes
aliases:
  - Phase Diagram of Polymer Mixtures and 𝜒 parameter
---
# Phase Transitions in Soft Matter
In soft matter molecular/aggregates interactions are of the order of $k_BT$. Therefore a qualitative system change obtained with a small quantitative variable change *(temperature, surfactant concentration, salt concentration, etc.)*. 

Some time is needed to achieve new morphology equilibrium. If not enough time is given to the system, the system is in **non-equilibrium state**. 

Phase transitions reflects the balance between internal energy and entropy. They can be of:
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
To construct the phase diagram of a binary (polymer) mixture

**Lattice Theory**
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
Go from free energy to phase diagram:
1. In practice $\mathcal{X}=A+\frac{B}{T}$, but $A$ can usually be forgotten;
2. Find the **minima** of Free energy and plot these minima as a function of $1/\mathcal{X}$ (temperature) to obtain the **binodal** line;
3. Same thing for the **inflection** points of the free energy to obtain the **spinodal** line. 
![[5f9a70c65ae28c06608c8e48b74885e3ae41ea9581f10f4a96f2f34e473bd215.png]]


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
