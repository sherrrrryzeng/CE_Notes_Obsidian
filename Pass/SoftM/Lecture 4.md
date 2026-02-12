---
date: 2025-11-19
Prof: Pouyan Boukany
aliases:
  - Entangled Polymers
---
# Polymers Examples

Alkane hydrocarbons -(CH2)-
![[417b1a1f3eb0f883858ea4422c1e87edccf79012e7c7f77c8eafadc44d0e1c57.png]]

Polymers in living nature
![[dbe49c894b3a878c851ff8e0da1a0d168622a3b3e48c911797d4a57fc560c8ac.png]]

Polymer properties depend on:
- Chemical composition of a monomer
- Degree of polymerization $N$
- **Flexibility**
	- Sufficiently long polymer is never straight
	- Different polymers bend differently
	
- **Architecture**
	![[0dacd4aa371329a646fc72f10d043474abc1e667d9d6dc3cb4d6ae2fb174bad2.png]]
	
- Homopolymer vs. Heteropolymer

Radius of gyration:
![[7bb8e70a728ea32555aab31d3481c404fce388dd5b1fe0ab412afecccaa961e4.png]]


# Viscoelasticity respond of Polymer Chains
![[ae21deff8947333e862d5367b7770e630fe5a81ff54451c7f6b096ca59dc8a93.png]]
**Chain Entanglement** is going to happen above $M_c$ (Critical Molecular Weight)

- before $M_c$: $$\frac{log(\eta_1/\eta_2)}{log(Me_1/Me_2)}=1$$
- after $M_c$: $$\frac{log(\eta_1/\eta_2)}{log(Me_1/Me_2)}=3.4$$

## Rubber Elasticity
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
Another way to express in terms of the average relative molecular mass **between cross links** $M_x$, and the density $\rho$: $$G=nk_BT=\frac{\rho N_{av}k_BT}{M_x}=\frac{\rho RT}{M_x}$$

## Time-Temperature Superposition(TTS)

![[2a112df097afa7d04aefff04c7af9c4aa596f09da1dbe9016721857334da4088.png]]
strain $e=\gamma$ (same quantity different symbols)

The relaxation reaction of entangled systems is different(see below)

![[17289838ffdd56c62b0e2abfd288470c639085f7d7ac4537374b13876be6d820.png]]

**Time-Temperature Superposition**:
![[b8eae4024a1958b588610a1340327829792e2eb60dd14f7af18c363b3c1574d4.png]]
![[5f10162e939a2a90c29a6c250cb96556cbe9f1d8f240a588882e13520cfb060a.png]]

![[10d3a14289911b5dcc72514c669248e0873a5a18fb3c7e4b887e66b7fa73a39d.png]]
![[02dadf204e1213f2497ae669afb9fe2f66bc1c4e2d836a24c6d5e940e94cdbd7.png]]


# Link Macroscopic Response of Entangled Network

## Reptation Model
The solution is **putting the chain in the tube** --- Rouse-like
![[274cc779002ee3effaa0d8e9e37cc268f7ac3e2dd6ef39106cf43bc26f8b3d04.png]]

![[c21c3aa051a58d820be7e428b553b041e5800bb141768cbc66dd4065d556c6b8.png]]
![[d36d482cfe0cc25ad28575e3b8c202fbf7ffaa70eda7040fe599ed5ee99c1260.png]]


## Oscillatory Deformation
![[ad0cb582a8b9c2575f003b9b24dcd265a9c66331b9722c6e7965ea4d4254aeef.png]]
Entangled wormlike micelles: 
![[6802aee7ae59a7997422221490e498d03867bf0050dc04e17997eb573bbdc6d3.png]]
![[83a44365ffdbb450a2a3fd2d7edcabd141a6413d671076d4f795d99b97fa6d56.png]]

Applies a sinusoidal strain $\gamma(t) = \gamma_0 \sin(\omega t)$ and measures the resulting stress $\sigma(t)$, especially the **time lag** between stress and strain.
- $\delta = 0^\circ$: Purely elastic (Solid).
- $0^\circ<\delta<90^\circ$: Viscous fluid (Polymers).
- $\delta = 90^\circ$: Purely viscous (Liquid).

- **Storage Modulus ($G'$)**: Represents **elasticity**; energy stored and recovered (Solid-like behavior).
- **Loss Modulus ($G''$)**: Represents **viscosity**; energy dissipated as heat (Liquid-like behavior).
- **Loss Tangent**: Quantifies the balance between viscous and elastic components$$\tan \delta = \frac{G''}{G'}$$- $>1$ is liquid-like, $<1$ is solid-like.
