---
date: 2026-02-09
Prof: Ruud van Ommen
aliases:
  - Intro to Fixed Bed Reactors
---
# Fixed Bed Reactors
(Single phase)

**Bed porosity** (void fraction): $$\epsilon_{bed}=\frac{V_{fluid}}{V_{solid}+V_{fluid}}$$
Pros:
- simple, cheap, well-known
- robust, easy scale-up
- ~ Plug Flow
Cons:
- moderate mass/heat transfer
- high pressure drop
- diffusion limitation
- shut-down for catalyst replacement

## Multiphase phenomena
### Mole balance 
![[6e2944a423bc53407fa7a40c849ec387bccc29858aedbe3597aba9679e00d59c.png]]

-> General mole balance heterogeneous model:
- 1 D: $$\epsilon_{bed}\frac{\partial C_A}{\partial t}=-\frac{\partial(C_Au)}{\partial z}+\frac{\partial}{\partial z}(D_{ax}\frac{\partial C_A}{\partial z})+(1-\epsilon_{bed})\rho_{cat}R_{A,obs}$$
- Steady state: $$\frac{d(C_Au)}{dz}=\frac{d}{dz}(D_{ax}\frac{dC_A}{dz})+(1-\epsilon_{bed})\rho_{cat}R_{A,obs}$$

### Obvious reaction rate
-Film diffusion + Pore diffusion ( $\eta_i \,\&\, \eta_o$ )
- No intraparticle diffusion:![[d71bf4c900b79b056cd2f038d38bf22e59a85981eb3c82e8ac1eeae154d9b53d.png]]
	- Steady state: ![[09fb25cabd7a8dd49cc9c8e10302d77a398121eb4d2eaf4831258f7312b61532.png]]
- Intra pellet:![[8adca542b0c1f2e936b1b46817ccb528e1d8441c47df0e20db2b91e1bd17bf58.png]]
	- Steady state:![[fdbe662cea759d979a02ee3b6c6b1f8a2d95327e386a3be58e8068e750d02fb2.png]]


#### Catalyst effectiveness
![[3b558db23e1d70d11c150dc1302d3f8302b71a111370932a881889474896b0cc.png]]


-> With effectiveness: ![[dd6a9ec5f84417bafff04be96ea041bdd69b539435db0881f5acb678ced1c08b.png]]


## Energy Balance
![[32df52f3d06544e2ab64a1f0df39717b8884b46e963d18af841d929f9cde3d85.png]]

- Steady state: ![[a53c3a04cdb61bddce9319e89a06de0e583f530ea7cdfe00cbc706fbb8c7348d.png]]


### Heat Transfer
- Thin film - no intraparticle diffusion: ![[d2785fbf46c6d54c608e6eb9c540ef6feafa53d7f7b90b389b223445dceee7c6.png]]
- Intra pellet:![[d484d04a6a6ec8a2d45537c2217410e2a5b8021e6af9a9aacce726e913590405.png]]


## Momentum balance / Pressure drop
Friction between fluid and solid, and friction in fluid internally, causes “energy dissipation”
- Mechanical energy → Thermal energy
- Pressure → Heat
$$Pa=\frac{N}{m^2}=\frac{J}{m^3}$$

![[8032ff2f81ec367eedcfd384b077c4d407a1afc72ed1cf787b1efc74d8d85f06.png]]

![[dc1617851b8dcc39fecf3b3dc24d47aff89ac64a4cd6df91fc4a6f822c4dfa91.png]]

How to estimate pressure drop:
- Experimentally (measurements)
- Numerically (computational fluid dynamics(CFD) simulations)

### Axial dispersion
![[cc3f50757a0586eeec9421f6b2af57eae331632e2d1209c3cde3bfff5c94b9c9.png]]

![[4835acbbe0a38649509238caa6adc92edf74e8b9b097cab2f4161ea0eae0fc9c.png]]

Use tanks-in-series model can get similar curves:
![[0ce586e764dd0858fbb9d45d24d8b3f24c0e805fcc58e7fedf9c91cbdfbace88.png]]
for multiple N -> choose Axial dispersion to reduce calculation
for avoiding differential equation -> choose tanks-in-series

Correlations: 
![[770dfe4d54d6819f6a40ec4a24e0ef3f0d35bc84482b97b287d8ddeac0cbb9a5.png]]

Dimensionless numbers:![[b21a4cc4a1f45a3ed2d7d0ae4ace74a529624df67c8d5ff47f283ba735b6c9bc.png]]
