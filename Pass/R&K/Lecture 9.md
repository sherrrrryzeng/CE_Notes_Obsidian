---
date: 2025-12-12
Prof: Atsushi Urakawa
aliases:
  - Chemical Kinetics
---
# Surface sorption (adsorption/desorption)

## Langmuir Adsorption
Reaction takes place typically at solid(catalyst) surfaces
First step in reaction -> adsorption

Physisorption vs. Chemisorption
![[5409ea73357afae9c2aa3c0f88623e93d5d63f1973040ede69e8a1eef1412ba7.png]]
*Nickel is a perfect kind of catalyst for dissociating hydrogen*


**Langmuir adsorption assumptions**: 
- Gaseous molecules behave ideally
- Only one monolayer forms
- All sites on the surface are equivalent
- Non adsorbate-adsorbate interactions
- Adsorbed species (atoms/molecules) are immobile

Langmuir adsorption model: 
![[27a4737393635fb32574fd9f2624a844edfaace8bc9fa0eaa86119e20dad3506.png]]

$$A+S\Leftrightarrow^{k_a}_{k_d}\Leftrightarrow A-S$$ A: atom/molecule;  S: vacant site
 $k_a$: adsorption rate constant;  $k_d$: desorption rate constant
 $p_A$: (Partial) pressure of A
 $N$: total number of surface sites
 $\theta$: **fraction of occupied surface sites** $$\theta=\frac{\text{number of adsorption sites occupied}}{\text{number of adsorption sites available }(=N)}$$
 \* pressure instead of concentration $c=\frac{n}{V}=\frac{P}{RT}$ 
 
 Adsorption rate: $$r_a=k_ap_AN(1-\theta)$$Desorption rate: $$r_d=k_dN\theta$$At equilibrium (REA): $r_a=r_d$ $$k_ap_AN(1-\theta)=k_dN\theta$$Adsorption constant: $K=\frac{k_a}{k_d}$ 
 Rearrange $$\theta=\frac{Kp_A}{1+Kp_A}$$
 - Low pressure ($Kp_A<<1$) : $\theta\approx Kp_A$ 
 - High pressure ($Kp_A>>1$) : $\theta\approx 1$ 
 
 First order sorption![[78470dd05748ea1ce8f46c9f4da1571f257b5128cefc5c872223c4746d4ccb36.png]]


In case of the volume of adsorbed molecules is measured: $$\theta=\frac{V_{ads}}{V_m}=\frac{Kp_A}{1+Kp_A}$$
In case of the concentration is measured: $$\bar{c}_A=N\theta=\frac{NKp_A}{1+Kp_A}=\frac{\bar{c}_mKp_A}{1+Kp_A}=\frac{\bar{c}_mK_1c_A}{1+K_1c_A}$$
$$\frac{1}{\bar{c}_A}=\frac{1+K_1c_A}{\bar{c}_mK_1c_A}=\frac{1}{\bar{c}_mK_1c_A}+\frac{1}{\bar{c}_m}=(\frac{1}{\bar{c}_mK_1})(\frac{1}{c_A})+(\frac{1}{\bar{c}_m})$$
$$\frac{c_A}{\bar{c}_A}=(\frac{1}{\bar{c}_m})c_A+(\frac{1}{\bar{c}_mK_1})$$


## Dissociative adsorption
![[20b55be99ee38dc5495914864ce31938e05ff208b02f50993fe1bbbf712ad1fd.png]]
$$H_2+2S\Leftrightarrow^{k_a}_{k_d}\Leftrightarrow 2H-S$$
Adsorption rate $$r_a=k_ap_{H_2}N(1-\theta_H)^2$$Desorption rate $$r_d=k_dN\theta_H^2$$ *$\theta_H$ is for atom H*
At Equilibrium (REA) : $r_a=r_d$ 
$$Kp_{H_2}(1-\theta_H)^2=\theta_H^2$$$$\theta_H=\frac{\sqrt{Kp_{H_2}}}{1+\sqrt{Kp_{H_2}}}$$
Molecular vs. Dissociative adsorption: ![[e953292e8d3b5035410d5cf730ab8a3823424db6d22bbb5942111cdbcdc2e6d2.png]]


## Multicomponent adsorption
A binary case: ![[477a4f759b15316f6e121e51d6e4922c571597384c4a95d61897d616748cf190.png]]
 $$\theta_S=1-\theta_A-\theta_B$$
A:
adsorption: $$r_{a,A}=k_{a,A}p_AN\theta_S$$desorption: $$r_{d,A}=k_{d,A}N\theta_A$$ At eq. :$$\theta_A=K_Ap_A\theta_S$$
B:$$\theta_B=K_Bp_B\theta_S$$Rearrange $$\theta_S=\frac{1}{1+K_Ap_A+K_Bp_B}$$ $$\theta_A=\frac{K_Ap_A}{1+K_Ap_A+K_Bp_B}$$ $$\theta_B=\frac{K_Bp_B}{1+K_Ap_A+K_Bp_B}$$

# Surface reaction (heterogeneous catalysis)

## Unimolecular reaction
$$A_{gas}\leftrightarrow A_{ads}\to P$$
- Transformation occurs uniformly across the surface
- Products are weakly bound and rapidly desorbed
- The rate determining step (**RDS**) is the surface transformation step
![[1990a004965ee21c3a64f6417e3dbb5b6577c2089f385eb536de0aff72dd0f05.png]]

For reaction: $$r=kN\theta_A$$ *N is often not shown (or integrated)*
$$R_P=r=\frac{kNKp_A}{1+Kp_A}=\frac{k'Kp_A}{1+Kp_A}$$


### Approximation details
![[a432ac8704db1c6a8989722b00dea1eadd52de833daa56955f53588ec228dc2c.png]]
Assume $P_{ads}$ as QSSA

$$r_1=k_1p_AN\theta_S-k_{-1}N\theta_A$$$$r_2=k_2N\theta_A$$$$r_3=k_3N\theta_P$$QSSA: $$R_{P_{ads}}=r_2-r_3=k_2N\theta_A-k_3N\theta_P=0$$$$\theta_P=\frac{k_2}{k_3}\theta_A$$

reaction order: ![[d90cc6e0f0d0e02aed2f1c3c13efa6fac35f1bed984a863ae1a83f8f28a00193.png]]


### When P adsorbs strongly
$$r=kN\theta_A=\frac{kNK_Ap_A}{1+K_Ap_A+K_Pp_P}$$
When $K_Pp_P>>1+K_Ap_A$ $$r\approx\frac{kNK_Ap_A}{K_Pp_P}$$ Now r is first order in A but has an order of -1 in P
-> **Product Poisoning**


## Bimolecular reaction
**Langmuir-Hinshelwood kinetics**
![[5fc1aedaa2462f67e944d62de8e36ef8742e786d5d75907d7ea41fe50977f97d.png]]
![[c581c69ab61a26017079ec1a96b5d73f7fcb59461ff3a4d04b3bb6f1f88acd36.png]]


Kinetic expression: ![[927fc0082b165dc5557a61b47201186ab5cb96de8c4fb719431d056933109bd2.png]]
$$r=\frac{k\cdot K_ip_i}{(1+\sum K_ip_i)^N}$$





