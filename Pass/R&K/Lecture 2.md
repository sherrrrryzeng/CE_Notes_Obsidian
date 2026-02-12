---
date: 2025-11-14
Prof: Atsushi Urakawa
aliases:
  - Chemical Equilibrium
---
**Chemical equilibrium** is the state in which both the reactants and products are present in concentrations which have no further tendency to change with time, so that there is no observable change in the properties of the system.
-> The rate of the forward reaction equals the rate of the backward reaction.

Equilibrium conversion == practical max. conversion
How to improve the equilibrium conversion in general:

## Phase Equilibrium
CO2 phase diagram
![[e9e624654acc8d8dd9cb124af3e78ccdf26c6b80df7cde4a1b8013185142c3b5.png]]
- Normally in CO2 cylinder <-> Liquid + Gas
- Supercritical CO2: extract caffeine from coffee beans


Methanol Synthesis![[df4bb1d67bbdb38ba01db2b7d5cda496c99edf90fc710058bd48f840309fc3dd.png]]
- **Le Chatelier's Principle**: High pressure & Low temperature are favourable

- At $CO_2:H_2=1:3$
	![[0ec3368fbf735d906283b6b153287309abe94a59daa629950c9a44952d77929d.png]]
	Nearly full CO2 conversion and full MeOH selectivity possible


Ammonia Synthesis (Haber-Bosch Process)
$N_2+3H_3 \leftrightarrow 2NH_3$     $\triangle H=-92.4 kJ\cdot mol^{-1}$
- Le Chatelier's Principle: High pressure & Low temperature are favourable
- At $N_2:H_2=1:3$
	![[b6a556982a2c88057fa84dea5b5dd312285c751465a411c5748471f001772969.png]]


## Equation of State (EOS)
A thermodynamic expression that relates pressure(P), temperature(T), and volume(V) and used to describe the state of fluids at given conditions. 

- Ideal gas law: $PV=nRT$
	Assumptions: 
	- constant moving
	- negligible volume
	- negligible intermolecular forces
	- perfectly elastic collisions
	- average kinetic energy proportional to the ideal gas's absolute temperature ($\frac{1}{2}mv^2=\frac{1}{2}k_BT$)

- Virial EOS (general form): 
	$$\frac{PV}{nRT}=\frac{P\tilde{V}}{RT}=1+\frac{B}{\tilde{V}}+\frac{C}{\tilde{V}^2}+\frac{D}{\tilde{V}^3}+...$$         $\tilde{V}$ is molar volume

- Van der Waals EOS (cubic equation of state): 
	$$P=\frac{RT}{\tilde{V}-b}-\frac{a}{\tilde{V}^2}$$        $a=\frac{27R^2T_c^2}{64P_c}$ , accounting for attractive forces between molecules
	$b=\frac{RT_c}{8P_c}$ , correction for the volume occupied by the molecules

- Other EOS
	![[49d2231ba6eb334d0fc6b33c54672a37f0687fde97790134ed3919bcac7231c0.png]]


## Reaction Equilibrium
**Gibbs Energy Minimisation**: $$dG=-SdT+VdP+\sum_j𝜇_jdn_j$$ ![[202120ceba3cf076f7e6c4a95b4fea2ef777d14ddc945053404999bfaafc5f7f.png]]When T, P and initial $n_j$ are specified, we can determine the equilibrium state of the system.

![[715dad78d15a1fb4c7cbedeeddcb065398a4fb814a4f23ef6be0fded36eccfaa.png]]

Extend of reaction $\varepsilon$ $[mol]$ : the number of times a reaction event occurs
$$r=\frac{\triangle\varepsilon}{\triangle tV}\,\,[/(time\cdot volume)]$$

![[505d25a9b7ec5ada7c76692556e8698a6ce82365a29daf0d4c4f11265e74aa20.png]]

![[afc42dc3483af46ba29405ae7fbb9c8b8d3e52aedcdec4754ec0f2f4b7a44e89.png]]

![[713f70152866e19bfa5e3c3440604b995becb53d0f689cd6a8cd107e1496a742.png]]
K: Equilibrium Constant


> [!Example] Ideal-gas Reaction Equilibrium
> ![[324a16e0c9b7c9fb117540546516909a98ce71837b0267586113c1e7d97b385a.png]]
> ![[f9679bf8e1387d8a7546bc7417cccd9d27751dcf8e194e4bc4ef6fd7e3ece462.png]]
> ![[8a5444e629dd3e8c91632b84c2b59f1caaf2ec84b03b3d2d6e8b24c8479e1ef5.png]]
> ![[80d29e47d728f1134f12796b35857de2f89f73faf426d50df019215f654848de.png]]


### Temperature dependence of $\triangle G$ and $K$
Gibbs Energy: $$\triangle G_i^0=\sum_jv_{ij}G_{ij}^0$$
**Van't Hoff Equation**: $$\frac{\partial lnK}{\partial T}=\frac{\triangle H^0}{RT^2}$$ When the standard heat capacity change of reaction is negligible, $\triangle H^0$ is constant. Then, $$ln(\frac{K_2}{K_1})=-\frac{\triangle H^0}{R}(\frac{1}{T_2}-\frac{1}{T_1})$$
