---
date: 2025-12-08
Prof: Eduardo Mendes
aliases:
  - Self Assembly
---
# Self-Assembly

Block copolymers (in bulk) could be observed in different shapes
![[77138c704f52008d60d27c966336a993b2554e303d8f21f65331016727540097.png]]

Self-assembling also happens in selective solvent solution:
![[92a80cd7a572b1ac774c00264311a9bc590687dc6592897f10aeb4e7569bb5bf.png]]


**Critical Packing Parameter**:$$\frac{V}{a_0l_C}$$![[9d03dc8d42947b4c5285acad3c2a593492039a14a34f5aadd0ebb6c09138bea6.png]]
- <1/3 - Cone - spherical micelles
- 1/3-1/2 - Truncated cone - cylindrical micelles
- ~1 - Cylinder - Planar bilayers

*But aggregates are dynamic, labile* 
*-not real spheres but fluctuating*


## Chemical potential Theory
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
That is the reason why such kind of molecules tend to form vesicles, to get rid of the rim. 

![[122473060292c39dcf4ed5c763f57464ac27a81117184456b3a576df0105d4ee.png]]
Disc-like micelles of finite radius are **not stable**
For 2D-self-assembly only **infinite aggregates** are stable.


#  Membranes
2D-aggregation -> infinite bilayer

Persistence Length - for distances on the membrane $<\xi_k$ the membrane looks flat:
$$\xi_k = a \exp \left( \frac{4\pi \kappa}{\alpha k_B T} \right)$$
- $\kappa$: Bending rigidity

Helfrich effective potential - close to a surface, the membrane cannot take all conformations and entropy decreases, creating a repulsive force described by: $$\triangle F_{Helfrich}\sim\frac{(k_BT)^2}{kd^2}$$

# Interface

Surface tension: 
$$\gamma\sim\frac{k_BT}{a^2}\sqrt{\mathcal{X}}$$
- $a$: Kuhn length
- $\mathcal{X}$: Interaction parameter


In case of lamella, the stretching of chains has to match the interfacial energy. The free energy change per chain due to **stretching** can be described as: $$F_{el}\sim k_BT\frac{d^2}{Na^2}$$
**The interfacial free energy** per chain: $$F_{int}=\frac{\gamma Na^3}{d}$$
Adding both terms and minimizing in respect to d $$d\sim(\frac{\gamma a^5}{k_BT})^{1/3}N^{2/3}$$