---
date: 2025-12-03
Prof: Eduardo Mendes
aliases:
  - "Kinetics of Phase Separation: Spinodal Decomposition"
---
# Fourier Transform
![[d78138196997bd1bfb45402f0c1202963ac804421bfca15682ef4ca4c97ea75a.png]]
*Solving differential equations in the frequency space is sometimes easier. Remind of the boundary conditions!*

- Fourier Transform: $$X(\omega)=\int_{-\infty}^\infty x(t)e^{-j\omega t}dt$$
- Inverse Fourier Transform:$$x(t)=\frac{1}{2\pi}\int_{-\infty}^\infty X(\omega)e^{j\omega t}d\omega$$

## How scattering relates to Fourier transform of scattering centres? 
-> **Scattering interference** is essentially the Fourier Transform of scattering positions in real space. 
Phase separation takes place via continuous change in composition called **spinodal decomposition**. ![[d9c84dd1b2229fc3ece82da24a59396fd178cb8fe625d5bd5185dd5e5033de93.png]]
The scattering pattern from detector shows the sum of interference by **pair of atoms**. $$I(q)=\sum_{i,j}b_ib_j\exp[-iq\cdot(R_i-R_j)]$$
In this way researchers can measure the growth of domains and phase separation kinetics non-destructively.
![[ad6c395c0670509b4ce4099c8441807fc0ecf87225630b52bf193e6ba94253e4.png]]![[8c8e8805b6a977bda25779daf2650bae5bd3e55692a1ae020036654eaa878f9c.png]]


# Phase separation
![[33a60e2cf54ff66fcf4ae5e48d375eed50cc064f09b38f18d488896470758883.png]]

## Nucleation
Definition: 
	Mixture compositions are **==metastable==**. 
	Separation will occur only if a drop of material will “somehow” occur in the **other coexisting concentration**.


2 types:
- **Homogeneous**
   if nucleation occurs via thermal fluctuations
- **Heterogeneous**
  if it happens via the presence surfaces (dust of impurities)


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
Definition:
	Mixture compositions are ==**unstable**==
	Phase separation takes place via continuous change in composition. 


**Small compositions fluctuations are strongly amplified**:
	Local fluctuations in concentration of A create high concentration regions. 
	Material flows from low concentration regions to high concentration regions governed by the ==**chemical potential**==. *(A prefer to be among A's as that costs less energy)*


The flux of species A due to chemical potential: $$J_A=-M\frac{d(\mu_A-\mu_B)}{dx}$$
- $\mu=\mu_A-\mu_B$: the energy cost of replacing one molecule A with per one molecule B $$\mu=(\frac{\partial F}{\partial N})_{T,S}$$
  $N$: number of particles at constant volume
- $M$: a positive constant

There are also gradient of concentration, so choose F that gives a nice functional form of the free energy: $$\mu=\frac{d}{d\phi}[f_0(\phi)+\kappa(\frac{d\phi}{dx})^2]$$
Then we have Cahn-Hilliard equation: $$\frac{\partial\phi}{\partial t}=Mf_0''\frac{\partial^2\phi}{\partial x^2}-2M\kappa\frac{\partial^4\phi}{\partial x^4}$$The equation looks like Fick's law with an extra term with an effective diffusion coefficient: $$D_{eff}=Mf_0''$$
- $f_0''$ can be either positive or negative. But inside the spinodal line it's **negative** since material diffuses from low to high concentrations.  

The solution for the Cahn-Hilliard equation reads in reciprocal space: $$\phi(x,t)=\phi_0+A\cos(qx)\exp[-D_{eff}q^2(1+\frac{2\kappa q^2}{f_0''})t]$$

In Fourier Transform $$q=2k_0\sin(\frac{\theta}{2})=\frac{4\pi}{\lambda}\sin(\frac{\theta}{2})$$
- $\lambda$: wavelength of input

when $\theta\to 0$, $\sin(\frac{\theta}{2})\to\frac{\theta}{2}$, $q\sim\frac{1}{\lambda}$

In small angle scattering experiment, the characteristic length of random concentration fluctuations in space $R^*$ is defined as:$$R^*=\frac{2\pi}{q_{max}}$$
- $q_{max}$: the wavevector where the amplification factor $-D_{eff}q^2(1+\frac{2\kappa q^2}{f_0''})$ has a maximum. 
  At $q_{max}$ the growing fluctuation in real space is the fastest. 


$R^*$ grows with time -> **==coarsening==** *(particle size increases)*
![[4cda02b32cd9a4938a6ae624936ab5bc6339b2027b123115f65e1cc78c75b1c7.png]]



![[d7cd60cd47d60a26f732f8c76cf44c17cd8c616c14a563ff7f1b0bcfb2b1c854.png]]



## Growth in the late stages
Once started, whether by spinodal decomposition or homogenous nucleation, the domains will grow.

![[55e61ccbfd7f091d918faa1690eb93fd05c86d72f1f50a22aa5a715cfecb72bd.png]]

During growth, observed patterns at time $t$ resembles the patterns at earlier times -> Domains grow **linearly** with time. 

And we can write for the correlation function.*(Although we cannot easily calculate a complex pattern, we can calculate how domain size R(t) grow.)*

Key point: **concentration close to small droplets is larger than that close to larger droplets.**
- molecules on the surface of a droplet are energetically less stable than the ones in the bulk
- larger particles have larger volume to surface molecule ratio
- and have less particles / volume that can leave the surface and diffuse into the solution
-> **==Ostwald ripening==**:
![[4145f946efaf9eee15fa5b750e5ebb5f884838515295f14109aa3363c3981501.png]]
$$\phi_{local}\sim\phi_{coex}\sim\frac{\gamma}{r}$$
- $r$: droplet curvature
- $\gamma$: surface tension

Calculation:![[782ac900707dd364005b467784f2a6cc1d13ae587ada8db97ac880f047530204.png]]
$$R(t)\sim(D\gamma t)^{1/3}$$
- $D$: diffusion coefficient

![[bad1fbcf1f35a261cd5d88d52feeaefadb3658c6d8d073ecf386596097799c0e.png]]
The relationship between peak wavevector $Q_m$ and reduced time $\tau$ *(dimensionless)* can be described as $$Q_m\sim R(t)^{-1}\sim\tau^{-1/3}$$


# Tutorial Conceptual Questions

1. **What is a phase diagram?**
	  A phase diagram for any given substance or molecular system is a graphic representation of the phases that **the substance/system can take as a function of "appropriate" variables**. Usually the phase relate to a molecular or supramolecular structure and the "appropriate" variables can be chosen according to the situation. 
	  For instance, in a binary system such as for a polymer solution (polymer + solvent) at constant volume and pressure, it is convenience to represent the phase diagram on the plane defined by temperature against polymer concentration. 
	
2. **Explain the origin of the interaction parameter $\mathcal{X}$ in the context of the phase diagram.**
	  The interaction parameter is defined as the ratio between the mutual pair interaction energies ($u_{AA},u_{AB},u_{BB}$) between two molecular species in the system and the absolute temperature. $\mathcal{X}$ is therefore $\sim\frac{1}{T}$. 
	  Assuming that those energies do not vary significantly with temperature, one can represent the phase diagram of binary mixtures by using T or $\mathcal{X}$ in one of the axis.
	
3. **What is spinodal decomposition? What does the lever rule say about phase separation?**
	  Spinodal decomposition is the spontaneous phase separation that occurs when a binary mixture is brought to the unstable region of the phase diagram. 
	  The lever rule: $$f_1 = \frac{\phi_{coex}^2 - C_0}{\phi_{coex}^2 - \phi_{coex}^1}\,\,\,\,\,\,\,\,\,\,f_2 = \frac{C_0 - \phi_{coex}^1}{\phi_{coex}^2 - \phi_{coex}^1}$$
4. **In terms of phase separation, what is nucleation? Explain the two ways a nucleus can form in this context. Which one**
