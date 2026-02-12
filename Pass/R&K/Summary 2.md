# Chemical Kinetics
## Elementary reaction
**Transition State Theory**:
- Elementary reaction = Direct use of stoichiometry coefficient
- Reaction rate constant - Arrhenius rate expression $$k=A\exp{(-\frac{Ea}{RT})}$$
	- $A$: Frequency factor or pre-exponential factor
	- $E_a$: Activation energy
		*-for a reaction to occur, reactant molecules must collide with **sufficient kinetic energy** to break existing chemical bonds and form new ones.* 


![[a026449618eb8c73e46e23f43f0f4123ea0b621427dfc9b166f45b90b8883d81.png]]

**Rate-determining(limiting) step**
	*slow step determines the total duration*$$k_2,k_{-2}>>k_1,k_{-1}$$-> **==Reaction equilibrium assumption (REA)==**
$$\text{fast step }\,\,\,\to\,\,\, r_2=0$$

**For short-lived intermediate(s)** 
	(typically small amounts)$$k_2>>k_1$$-> ==**Quasi-steady-state assumption (QSSA)**== $$R_B=\frac{dC_B}{dt}=0$$


## Surface Reactions
### Adsorption & Desorption

**Langmuir adsorption model**![[27a4737393635fb32574fd9f2624a844edfaace8bc9fa0eaa86119e20dad3506.png]]
Assumptions:
- Gaseous molecules behave ideally
- Only one monolayer forms
- All sites on the surface are equivalent
- Non adsorbate-adsorbate interactions
- Adsorbed species (atoms/molecules) are immobile

---
#### (1) Molecular adsorption
![[db5da77a8eb75af982a0e87a0e3fadc26ece4675efc4fec9b4c2736371aa4af0.png]]
 $k_a$: adsorption rate constant;  
 $k_d$: desorption rate constant
 $p_A$: (Partial) pressure of A
	  *\*use pressure instead of concentration $c=\frac{n}{V}=\frac{P}{RT}$* 

 $N$: total number of surface sites
 ==**Fraction of occupied surface sites :**== $$\theta=\frac{\text{number of adsorption sites occupied}}{\text{number of adsorption sites available }(=N)}$$
- **Adsorption rate**: $$r_a=k_ap_AN(1-\theta)$$
- **Desorption rate**: $$r_d=k_dN\theta$$
**At equilibrium (REA)**, $r_a=r_d$ $$k_ap_AN(1-\theta)=k_dN\theta$$
- **Adsorption constant** $$K=\frac{k_a}{k_d}$$
 Rearrange $$\theta=\frac{Kp_A}{1+Kp_A}$$
 Pressure Analysis:
 - Low pressure ($Kp_A<<1$) : $\theta\approx Kp_A$ 
	 -> First order sorption - linearly dependent on $p_A$
 - High pressure ($Kp_A>>1$) : $\theta\approx 1$ 
	 -> Zero order sorption - no $p_A$ dependency

Convert back to concentration: $$N\theta=\frac{NKp_A}{1+Kp_A}\,\,\,\to\,\,\,\bar{c}_A=\frac{\bar{c}_mKp_A}{1+Kp_A}$$$$\frac{1}{\bar{c}_A}=\frac{1+K_1c_A}{\bar{c}_mK_1c_A}=\frac{1}{\bar{c}_mK_1c_A}+\frac{1}{\bar{c}_m}=(\frac{1}{\bar{c}_mK_1})(\frac{1}{c_A})+(\frac{1}{\bar{c}_m})$$
$$\frac{c_A}{\bar{c}_A}=(\frac{1}{\bar{c}_m})c_A+(\frac{1}{\bar{c}_mK_1})$$
-> $y=ax+b$ 

---
#### (2) Dissociative adsorption
![[15af45b4c3afab4c9158b2fa092cff958d650e3c51462b84b21a3b1602abcdd6.png]]

- **Adsorption rate** $$r_a=k_ap_{H_2}N(1-\theta_H)^2$$
- **Desorption rate** $$r_d=k_dN\theta_H^2$$
**At Equilibrium (REA)**  $r_a=r_d$ 
$$Kp_{H_2}(1-\theta_H)^2=\theta_H^2$$$$\theta_H=\frac{\sqrt{Kp_{H_2}}}{1+\sqrt{Kp_{H_2}}}$$
Molecular vs. Dissociative adsorption: ![[8bbc3979d22bc2a252036a192a571a512e5ec06a2ec4f18c9f1b400d371d6df5.png]]


---
#### (3) Multicomponent adsorption
![[7bb4f8fdfda30b366f0c5d74d243abac6fe6ffbc4ace1c4f4738f970a3e1f5e4.png]]

- **Adsorption rate** $$r_{a,A}=k_{a,A}p_{A}N\theta_s$$$$r_{a,B}=k_{a,B}p_{B}N\theta_s$$
- **Desorption rate** $$r_{d,A}=k_{d,A}N\theta_A$$$$r_{d,B}=k_{d,B}N\theta_B$$
**At Equilibrium (REA)**  $r_a=r_d$ 
$$\theta_A=K_Ap_A\theta_s$$$$\theta_B=K_Bp_B\theta_s$$Relationship between A,B,S is $$\theta_A+\theta_B+\theta_s=1$$Final equation: $$\theta_s=\frac{1}{1+K_Ap_A+K_Bp_B}$$$$\theta_A=\frac{K_Ap_A}{1+K_Ap_A+K_Bp_B}$$$$\theta_B=\frac{K_Bp_B}{1+K_Ap_A+K_Bp_B}$$


### Surface reaction
#### (1) Unimolecular reaction
![[25e8027ac49d4daa72d5c15208454b6d612b07f7f7d35101ea52f297ce8dd6c4.png]]
$$r=kN\theta_A=\frac{kNKp_A}{1+Kp_A}=\frac{k'Kp_A}{1+Kp_A}$$

#### (2) Unimolecular reaction - when P adsorbs strongly
![[ee7e38b6f3a52d16171e60527fd058817a736850ce6cc4277d92e64ebc82b7ec.png]]
*Consider adsorption of both A and P* $$\theta_A=\frac{K_Ap_A}{1+K_Ap_A+K_Pp_P}$$$$r=kN\theta_A=\frac{kNK_Ap_A}{1+K_Ap_A+K_Pp_P}$$
When $K_Pp_P>>1+K_Ap_A$: $$r\approx\frac{kNK_Ap_A}{K_Pp_P}$$-> **==Product Poisoning==**: 
	reaction is first order in A 
	but has an order of -1 in P


#### (3) Bimolecular reaction - Langmuir-Hinshelwood kinetics
![[5a0b297784b6cacab17cae7878f338a6fc73785363dfb399392b791471fd12b6.png]]
$$r=kN(^2)\theta_A\theta_B=\frac{kN(^2)K_Ap_AK_Bp_B}{(1+K_Ap_A+K_Bp_B)^2}$$$$r=\frac{k'K_Ap_AK_Bp_B}{(1+K_Ap_A+K_Bp_B)^2}$$
General expression:![[1f801c8a3d172e7a228042a3cb98368e54921a0c302c2b9a4c95f05910ee96f6.png]]



# Catalytic Reactions
## Mass transport (Diffusion)
Hougen-Watson kinetics(LHHW kinetics): $$r_{intrinsic}=\frac{k\cdot K_ip_i}{(1+\sum K_ip_i)^N}$$
The observed reaction rate is not the same:$$r^{obs}=\eta \,r^{intrinsic}=\eta_i \eta_e \,r^{intrinsic}$$ 
- $\eta$ : **effectiveness factor**. 
- Physicochemical events inside and outside of catalyst:
	- film diffusion (external)
	- pore diffusion (internal)


 $r_V$ : reaction rate per unit particle volume
- **External Effectiveness Factor** $$\eta_e=\frac{\text{rate at external surface condition}}{\text{rate at bulk fluid condition}}=\frac{r_V(C_s,T_s)V_p}{r_V(C_b,T_b)V_p}$$
- **Internal Effectiveness Factor** $$\eta_i=\frac{\text{observed rate}}{\text{rate at external surface condition}}=\frac{\int_0^{C_p}r_V(C,T)dV}{r_V(C_s,T_s)V_p}$$ 


### Types of diffusion

**Mean free path** (gas phase): $$\lambda=\frac{k_BT}{\sqrt{2}\pi\sigma^2P}$$
-  $\sigma$ is the kinetic diameter (molecular diameter).


**Average pore radius**: $$r_a=\frac{2V_{pore}}{S_g}$$
- $V_{pore}$ is pore volume; 
- $S_g$ is surface area.

Compare mean free path and pore radius:![[167ada45d8baeb0137bb3c2f46863815ed3d80ef4a3ea88127e287f671b1155d.png]]

*For gas, 1 atm, room temperature, $\lambda$ is in the order of $10^{-5}$ cm (order of 100 nm = $10^{-7}$ m)*
$$\lambda<<r_a\,\,\,\,\to\,\,\,\,\text{Molecular diffusion -> intermolecular collisions}$$$$\lambda>>r_a\,\,\,\,\to\,\,\,\,\text{Knudsen diffusion} -> \text{collisions with pore walls}$$$$\lambda\approx r_a\,\,\,\,\to\,\,\,\,\text{Molecular and Knudsen diffusion}$$$$\frac{1}{\bar{D}}=\frac{1}{D_{AB}}+\frac{1}{D_{K,i}}$$
- $r_a\approx \sigma_p(\text{radius of particle})\,\,\,\,\to\,\,\,\,\text{Single file diffusion}$
- $r_a<\sigma_p\,\,\,\,\to\,\,\,\,\text{No diffusion}$



### Effective Diffusivity
-  $\epsilon$ : **==Porosity==** $[m^3_{void}\,m^{-3}_{total}]$
- $\tau$ : **==Tortuosity==** $[-]$

Effective diffusivity $$D_{eff,i}=\frac{\epsilon}{\tau}D_i$$
*With porosity and tortuosity the diffusivity is significantly lower*



![[f251f738b97b8e700639a6a21cf85643946f32d085a86fd760754da8d4747f98.png]]
## External Mass Transfer
*white part -> grey part*
Fick's first law $$J_i=-D_i\frac{dC_i}{dz}\,\,[mol\cdot cm^{-2}s^{-1}]$$*Fick's law says the concentration profile is **linear***


External mass transfer flux: $$r_V(C_s,T_s)V_p=A_pk_m(C_b-C_s)$$
- $A_p$ : External catalyst surface area
- $k_m$ : mass transfer coefficient $[m/s]$ $$k_m=\frac{D}{\delta}$$
	- $\delta$: effective film thickness
Rearrange with specific surface area $$a_s=\frac{A_p}{V_p}\,\,[m^{-1}]$$$$r_V(C_s,T_s)=a_sk_m(C_b-C_s)$$For 1st order, irreversible reaction, from reaction kinetics $$r_V(C_s,T_s)=k_VC_s$$$$k_VC_s=a_sk_m(C_b-C_s)\,\,\,\,\to\,\,\,\,C_s=\frac{a_sk_m}{k_V+a_sk_m}C_b$$$$r_V(C_s,T_s)=k_V\frac{a_sk_m}{k_V+a_sk_m}C_b=\frac{1}{1+\frac{k_V}{a_sk_m}}k_VC_b$$
**==External effectiveness factor==**: $$\eta_e=\frac{1}{1+\frac{k_V}{a_sk_m}}$$
Analyse the resistances:
$$r_V(C_s,T_s)=\frac{1}{\frac{1}{k_V}+\frac{1}{a_sk_m}}C_b=\frac{1}{\tau_R+\tau_T}C_b$$
- $\tau_R$: Chemical resistance from reaction
- $\tau_T$: Physical resistance from mass transfer


### Dimensionless numbers
- **Second Damkohler number** $Da_{II}$ (non observable)$$Da_{II}=\frac{\text{rate at bulk concentration}}{\text{maximum mass transfer rate}}=\frac{r_V(C_b,T_b)}{a_sk_mC_b}$$
  *For 1st order irreversible reaction:* $$\eta_e=\frac{1}{1+\frac{k_V}{a_sk_m}}=\frac{1}{1+Da_{II}}$$$$Da_{II}=\frac{k_V}{a_sk_m}=\frac{\tau_T}{\tau_R}$$

- **Carberry number** $Ca$ (observable)$$Ca=\frac{\text{Observed reaction rate}}{\text{maximum mass transfer rate}}=\frac{r_{V,obs}}{a_sk_mC_b}$$
  *For 1st order irreversible reaction:* $$Ca=\frac{a_sk_m(C_b-C_s)}{a_sk_mC_b}=\frac{C_b-C_s}{C_b}=1-\eta_e$$$$Ca=\eta_eDa_{II}=\frac{Da_{II}}{1+Da_{II}}$$

To get mass transfer coefficient $k_m$:
![[1cb4881553003fc2735be8b9df24e90e3e3edfc7b994435cc8012fc717ead223.png]]
$$k_m\sim \frac{u^{0.64}}{d_p^{0.36}}$$
- $u$ : velocity of the fluid
- $d_p$ : diameter of the particle


### Stable reaction
![[0295cea1e12857a216169bb71b9c0bc09aebda011d20ef90c067891d742a598e.png]]
*Reaction happens on the surface*

Analysis: 
- green curve - Hougen-Watson kinetics (reaction)$$r=\frac{k'C_s}{(1+KC_s)^2}$$
- red curve - supply rate slope (mass transport)$$r=a'k_f(C_b-C_s)$$
Cross-points : possible solutions for equilibrium
 - **Stable** - the first and third one
 - **Desired** - **==the first one==**
	- low $c_s$ (surface concentration)
	- high $r$ (reaction rate)


## Internal Mass Transfer
### Diffusion Through Slab
![[494853988cb87412588f3da9a9c63b204081c7fe52c4706f2bf7b63fdce79338.png]]
*Write a mass balance and derive the differential equation describing the concentration profile along the thickness axis (x).* 
*Here neglect external mass transfer ($D_{eff}=D$).* 

The mass transfer under steady state is 0:
$$\frac{dN}{dt}=\frac{d(CA\triangle x)}{dt}=-AD\frac{dC}{dx}|_x-(-AD\frac{dC}{dx}|_{x+\triangle x})+r\triangle V=0$$ 
Reaction rate: $r=-kC$ $$\frac{AD(\frac{dC}{dx}|_{x+\triangle x}-\frac{dC}{dx}|_{x}))}{A\triangle x}-kC=0$$$x\to 0$:  $$D\frac{d^2C}{dx^2}-kC=0$$**Boundary conditions**: 
1. Symmetry: $x=0,\,\,\frac{dC}{dx}=0$ 
2. Surface: $x=L,\,\,C=C_s$

**Normalise** the concentration by the surface concentration $C_s$: $$C^*=\frac{C}{C_s}$$Normalise the length x by $L$: $$x^*=\frac{x}{L}$$Normalised Equation:$$\frac{d^2C^*}{dx^{*2}}-\phi^2C^*=0$$
*\*For second order differential equation, you can describe the solution by means of hyperbolic functions:* $$\sinh{(x)}=\frac{e^x-e^{-x}}{2}\,\,\,\,\,\,\cosh{(x)}=\frac{e^x+e^{-x}}{2}\,\,\,\,\,\,\tanh{(x)}=\frac{e^x-e^{-x}}{e^x+e^{-x}}$$
Solving the final equation (neglecting \* ): $$C=\frac{e^{\phi x}+e^{-\phi x}}{e^\phi+e^{-\phi}}$$$$C^*\left(=\frac{C}{C_s}\right)=\frac{\cosh(\phi x^*)}{\cosh{(\phi)}}$$ ![[5ee9564b3e8f77c6364be23bfae725e31ef2daeee626810ff70a738d072ed031.png]]

In principle:
- **blue line** -> use all the catalyst efficiently *(what we want)*
	 CAN normalise with surface concentration $C_s$ 
- purple line -> only use the outside part of catalyst


### Thiele modulus
Internal effectiveness factor:$$\eta_i=\frac{\tanh(\phi)}{\phi}$$*(for slab and most used in practice)*
![[c27184d7149b70ddc4bc7f492718efe5068dbc65c4e9741bc13c50784ddcd54b.png]]


Characteristic length $L$:
![[384b97792e8b06db7c5ddf1eae94a64e1785ce9be5503dcd485811e0b17a13e7.png]]


From generalised form of Thiele modulus and reaction rate,
- **The apparent reaction order changes**
	->Order of Knudsen diffusion $$\frac{n+1}{2}$$
	->Order of Molecular diffusion $$\frac{n}{2}$$
- **Internal mass transfer (pore diffusion) limits reaction strongly** -> **==Falsified kinetics==** $$E_{obs}=\frac{1}{2}(E_a+E_{diff})\approx\frac{1}{2}E_a$$($E_{diff}<<E_a$)



## Mass transfer Limitations
1. **Wheeler-Weisz modulus** - internal diffusion
	*(need to know intrinsic kinetics)* $$\Phi=\frac{\text{observed reaction rate}}{\text{diffusion rate}}=\eta_i\phi^2=\frac{r_{V,obs}}{a_sD_{eff}C_s}(\frac{n+1}{2})$$
	- $\Phi<0.15$ : no limitation
	- $\Phi>>1$ : strong limitation
	
2. **Carberry number** - external mass transfer
	No limitation if  $$Ca=\frac{r_{V,obs}}{a_sk_mC_b}<\frac{0.05}{|n|}$$

Flowrate: 
![[5f292b7f93fff9c37613eb6e7937e2cdc4cd1e5d54852f55dbc96381100e0820.png]]
	Flow rate increases
	-> film thickness decreases
	-> conversion increases


Temperature:![[491021370bfea125653c8cdd81d60a43c7ebc3f2242f558231e2789f1d88c7a1.png]]


## Combined Mass Transfer
*Internal and external in slab case*

Introducing **==Biot number==**: $$Bi_m=\frac{\text{rate of external mass transfer}}{\text{rate of internal diffusion}}=\frac{k_mL}{D_{eff}}$$$$Da_{II}=\frac{\phi^2}{Bi_m}$$
**Overall effectiveness factor**: $$\eta=\eta_i\eta_e=\frac{\eta_i}{1+\eta_iDa_{II}}=\frac{\tanh\phi}{\phi(1+\frac{\phi\tanh\phi}{Bi_m})}$$
- if $Bi_m$ is large(>10) -> internal control -> $\eta=\frac{\tanh(\phi)}{\phi}$ 
- if $Bi_m$ is small -> external control -> $$\eta=\frac{Bi_m}{\phi^2}=\frac{1}{Da_{II}}$$


### Effect of reaction heat
![[cd89ee8028441777528d9823a936c18a2d1cf93095870be4b824bba5f9396a49.png]]

**==Prater number==**$$\beta_i=\frac{D_{eff}(-\triangle H)C_s}{\lambda_eT_s}$$
- $\lambda_e$: effective thermal conductivity of porous materials

Typically,
- Exothermal -> $\beta_i=0\to0.3$ 
- Endothermal -> $\beta_i=-0.1\to0$
![[314a83381ec1b322d47f8d4547045954bb804d45b7138a3ee29ec9805cdd1085.png]]

Key Observations:
- **Negative βᵢ** (blue curve): 
    - ηᵢ remains **below unity(1)**. No enhancement region is observed
    - Indicates inhibitory coupling between temperature (or concentration) and reaction rate.
- **Positive βᵢ** (other curve): 
	1. **Low φᵢ (kinetic control):**
	    - ηᵢ ≈ 1 for all βᵢ
	    - Internal mass transfer limitations are **negligible**
	    - Reaction rate is controlled by intrinsic kinetics
	2. **Intermediate φᵢ:**
	    -  ηᵢ exhibits a maximum and may exceed unity(1). This is caused by **internal temperature rise** in exothermic reactions.
	    - Arrhenius dependence amplifies the reaction rate
	    - Larger βᵢ leads to higher and sharper peaks
	3. **High φᵢ (diffusion control):**
		- ηᵢ decreases with increasing φᵢ
		- **Strong** internal diffusion resistance dominates
		- Thermal enhancement becomes insufficient to compensate for diffusion limitations. 
