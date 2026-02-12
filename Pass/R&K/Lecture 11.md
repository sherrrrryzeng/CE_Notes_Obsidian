---
date: 2025-12-19
Prof: Atsushi Urakawa
aliases:
  - Catalytic Reactions
---
# Internal Mass Transfer
## Diffusion & Reaction through slab
A first-order irreversible reaction (rate constant _k_) is taking place in a slab. External mass transfer can be neglected.![[494853988cb87412588f3da9a9c63b204081c7fe52c4706f2bf7b63fdce79338.png]]

Write a mass balance and derive the differential equation describing the concentration profile along the thickness axis (x):
$$\frac{dN}{dt}=\frac{d(CA\triangle x)}{dt}=0$$$$=-AD\frac{dC}{dx}|_x-(-AD\frac{dC}{dx}|_{x+\triangle x})+r\triangle V=0$$ Reaction rate: $r=-kC$ $$\frac{AD(\frac{dC}{dx}|_{x+\triangle x}-\frac{dC}{dx}|_{x}))}{A\triangle x}-kC=0$$$x\to 0$:  $$D\frac{d^2C}{dx^2}-kC=0$$**Boundary conditions** (steady state): 
1. Symmetry: $x=0,\,\,\frac{dC}{dx}=0$ 
2. Surface: $x=L,\,\,C=C_s$

**Normalise** the concentration by the surface concentration $C_s$: $$C^*=\frac{C}{C_s}$$Normalise the length x by $L$: $$x^*=\frac{x}{L}$$
Replace: $$\frac{DC_s}{L^2}\frac{d^2C^*}{dx^{*2}}-kC_sC^*=0$$
**Thiele modulus** is defined by *(for first-order irreversible reactions)* $$\phi=L\sqrt{\frac{k}{D}}$$Final Equation:$$\frac{d^2C^*}{dx^{*2}}-\phi^2C^*=0$$
\* For second order differential equation, you can describe the solution by means of hyperbolic functions: $$\sinh{(x)}=\frac{e^x-e^{-x}}{2}$$$$\cosh{(x)}=\frac{e^x+e^{-x}}{2}$$$$\tanh{(x)}=\frac{e^x-e^{-x}}{e^x+e^{-x}}$$
Solving the final equation (neglecting  \*): $$C=C_1e^{r_1x}+C_2e^{r_2x}$$ $r=+-\phi$ $$C=C_1e^{\phi x}+C_2e^{-\phi x}$$ $$\frac{dC}{dx}=C_1\phi e^{\phi x}-C_2\phi e^{-\phi x}$$ $x=0:\,\,\frac{dC}{dx}=0$ -> $$C_1=C_2$$ $x=1:C_1e^\phi+C_1e^{-\phi}=1$ -> $$C_1=\frac{1}{e^\phi+e^{-\phi}}$$ FINAL: $$C=\frac{e^{\phi x}+e^{-\phi x}}{e^\phi+e^{-\phi}}$$ $$C^*\left(=\frac{C}{C_s}\right)=\frac{\cosh(\phi x^*)}{\cosh{(\phi)}}$$ ![[5ee9564b3e8f77c6364be23bfae725e31ef2daeee626810ff70a738d072ed031.png]]

In principle:
- **blue line** -> use all the catalyst efficiently *(what we want)*
	 CAN normalise with surface concentration $C_s$ 
- purple line -> only use the outside part of catalyst


## Effectiveness factor for internal mass transfer
$$\eta_i=\frac{\text{observed rate}}{\text{rate at external surface condition}}=\frac{\int_0^{Vp}r_V(C,T)dV}{r_V(C_s,T_s)V_p}$$ $$=\frac{\text{Diffusion rate at x=L}}{r_V(C_s,T_s)V_p}=\frac{A(-(-D\frac{dC}{dx}|_{x=L}))}{kC_sLA}$$ $$=\frac{ADC_s\frac{dC^*}{dx^*}|_{x^*=1}}{kC_sL^2A}=\frac{1}{\phi^2}\frac{dC^*}{dx^*}|_{x^*=1}$$ $$=\frac{1}{\phi^2}\frac{\phi \sinh(\phi)}{\cosh(\phi)}=\frac{\tanh(\phi)}{\phi}$$ FINAL: $$\eta_i=\frac{\tanh(\phi)}{\phi}$$
![[c27184d7149b70ddc4bc7f492718efe5068dbc65c4e9741bc13c50784ddcd54b.png]]


### Thiele modulus for other catalyst shapes
![[384b97792e8b06db7c5ddf1eae94a64e1785ce9be5503dcd485811e0b17a13e7.png]]
- Slab *(in practice most used)*$$\eta_i=\frac{\tanh(\phi)}{\phi}$$
- Sphere $$\eta_i=\frac{1}{\phi}\left(\frac{1}{\tanh(3\phi)}-\frac{1}{3\phi}\right)$$
- Cylinder - *$I$ means Bessel function* $$\eta_i=\frac{1}{\phi}\frac{I_1(2\phi)}{I_0(2\phi)}$$
- Others ![[54787279dcf5d5549a943306b6084fdc4aee6e5ad64598750a5d71c8175fa610.png]]