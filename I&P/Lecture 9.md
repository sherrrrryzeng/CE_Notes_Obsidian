---
date: 2025-12-08
Prof: Ruud van Ommen
aliases:
  - Particle Technology (Granular matter)
---
# Intro of Particles

**Granular matter**:
	 a collection of **macroscopic** solid particles
	 - no Brownian motion
	 - dissipative particle-particle interactions 
	   *(kinetic energy -> heat)*
	 - can behave as a solid, liquid or gas depends on energy input and concentration. 


# How do particles pack
## 2D Particle Packing
- **Hexagonal Close Packing** ![[e46115966cb5cab339cfc8127a7c7f6b3a9a9994383ee05ebb04a2c836c0d915.png]]

- **Square Close Packing** ![[4322133cad643283e8e130c1437e116a7ca07f873899a0e4c830b39698ee1679.png]]

## 3D Particle Packing
![[885423442f31ff147123f645522e52318b702c07a40b347dbe96aed1d70c20cb.png]]
- **Simple cubic lattice**
- **Hexagonal closed packed lattice (HCP)**
- **Face-centered cubic lattice (FCC)**![[68823aefc539de21ed5ac91dcbfa7403638ebdb8e807fc5f177693b26d90ce6a.png]]

\* HCP vs FCC: 
- same packing fraction
- different stacking sequence 
![[8e5da61d313166782fe411bccc87ba9648621c3f77683f064885e82eb34aefcc.png]]

- **Random close packing**
	- Particles are packed as close as possible, but without order. No clear definition of the (dis-)order of the system. 
	- Usually defined statistically, and results are empirical. 
	  Packing fraction - 0.64 (2D - 0.84)


## The Effect of Agitation
![[6cf13fc90c1d89a73577d525804792a7862e96c391f62a99d32850aedafbbc3a.png]]

Agitation has a substantial impact on non-Brownian particles
- **Sonication**
- **Shaking**
- **Vibration**


## Particle packing Size Distribution
When adding a new particle into the system:
- Smaller particle - "a Rattler"
	 does not disturb packing if max 15% of original size
	 will fit in the hold of regular packing
- Larger particle
	 requires removal of original particle
	 leads to disorder in the system if size difference is larger than 25%

![[1c7c60dbea446045bfacb02f8200543b5126d04520417098f2870431677fe948.png]]


# External factors that affect the particle flow
## Stress
 leads to **==different packing / consolidation==**

*depends on:*
- Restrict particle flow
	**friction**
	**mechanical interlocking**
	**inter-particulate forces**
	**liquid bridging**
	**smaller particles**
- Enhance particle flow
	**aeration**

![[83f82dcb9019856dacbc6253818b674fec8c24e07172c718c777cd4108ad8def.png]]


### Angle of repose
 the ==steepest angle== of descent relative to the horizontal plane on which the material can be piled. ![[6b1eeac54ba38c1a038b0d568a7a15e5075a7f7e6707fffab510547d7ec4b2af.png]]
- **Material** dependent
- **Friction
	- **Roundness** -> mechanical interlocking
	- **Roughness**
- **Size**

![[7834fb0b1e0ef5ac4595074cc6a78d61bfd805c0018afb8ade9298ec2093df47.png]]
$$\theta=\arctan(\frac{h}{r})$$

Angle of repose reflects the flow property:
![[8fb80475cffa2c55b93e0a06e1dbc7723e3971f00c1ef13b9be2928000fcbec7.png]]


Nature example of angle of repose: antlion trap ![[be614d7ab8feaa00ce9e492ed0f7dac8a3b0af18493e6b91328484c2b845dab8.png]]


## Segregation
![[2bccb45e620ee30b06ac98a43d6cea9585b236711552505d021851f74c029603.png]]
$$\alpha=\frac{R_1}{R_2}$$
Definition: **in confined space**
- large particles accumulate on top
- small particles percolate due to gravity

\* The most important contributor is size. 
The **minimum pore size** for segregation for FCC: $$R_{2,minimum}<\frac{R_1}{\alpha}$$
**Vibration or local shear** intrigue the segregation.
*(Granular matter does not have Brownian motion -> they do not move by themselves)*


### Reality issues for segregation
when products transfer through process containing bins, hoppers, conveyors etc., segregation happens. 
*e.g., pharmaceutical industry -> uniform distribution of active components is desired*

**Silo filling in air flow** increases segregation:
![[64fc40fa0b06e9ba9fa1547c5c2b9379526dcb1c354cd1341547961b6af1a78b.png]]


## Caking
Definition: a powders tendency to form lumps or masses
- Any factor that can **increase attractive forces** may lead to caking
- Chemical or mechanical bonds

**Intrinsic parameters**: 
- Particle size (distribution)
- Hygroscopicity 吸湿性
- Chemical compositions
- Hardness, deformability
- Glass transition

**External factors**:
- Relative humidity
- Temperature
-  Pressure
- Times


## Effect of Liquid on particles
The properties changed in wet granular materials: 
- increased angle of repose
- enhanced strength
- compact packing

Reason - **Capillary interactions**:
![[baa2c1a9b1187b45cdd006914607b9022fd692027bab9ce5bb588e030de0b89e.png]]
-> Increasing **==cohesion==** due to **surface tension** effects

**Cohesions suppresses segregation** 
 <- suppress relative motion of particles
![[347a100aca9c48e4322a83b3e15e7926a4d8bc9078965a04e26206a89ae90f47.png]]****

![[58f1efdd13f5f9e0c5866e9c95d0982e9f1733a67efb4988421d60259757414e.png]]


# Applications of particle technology in practice

Challenges in particle technology: ![[de959d76a81205c6b9e81655bc63b4a63bc0d124ba86da731439bdc8c8738c1d.png]]

## Challenges in Sensors & Measurements
![[6159cf812e4972a8ac1771456b2028b4ac389bb28a7db99c63f1280973e99f77.png]]

![[cfc17c661f9c1671c2ad885d5191b15ee873ab59e192a2d9ecf31d38c2ccdc8f.png]]

![[b472d1330d99c79a9f871df19d2bcfb605fd8e9dad0fa67231950ac3b0fa2b94.png]]


## Challenges in Multiscale model
For Gas and liquid flows
	Typically, no structures at multiple scales, no multiscale models needed
	A continuum model normally gives satisfactory results
![[2e071adc087033b3a117194101f6f8164f88732e2cc5f5bbca2e1f2109a22a9f.png]]

Possible solution: AI-driven model


## Other challenges
### Advanced particles
![[f2593fba3da69bd4df12888b11afe38f275bdb3b9adc45c2c4f7a293f05c94a5.png]]

### Flowability
![[0176c66412faee689d0553fc3b0f1a8aad65e4b930bf094053d5e4c421877ed2.png]]

Remind: 
#### Geldart classification
- **Group C – Cohesive powders**
	- Very fine particles (<30 µm)
	- Poor flowability, strong cohesion
	- ==Difficult to fluidize== 
	  -> channeling, agglomeration, non-uniform flow
- **Group A – Aeratable powders**
	- Fine to medium particles (≈30–100 µm)
	- Good flowability
	- Smooth, easily fluidized, stable fluidization behavior
- **Group B – Sand-like particles**
	- Medium-sized particles (≈100–500 µm)
	- Good flowability
	- Classic ==bubbling fluidization== (Large bubbles, vigorous mixing)
- **Group D – Large/ dense particles**
	- Large or heavy particles (>500 µm)
	- Excellent flowability but heavy
	- Require high gas velocity
	- Spouting or jetting, ==not smooth fluidization==
    
![[d126384d811d0bc18b11ffa9a8dc063c93ce2a42bd1ed8b87c0727433c454a91.png]]

### Sustainability
![[3ef4eb5a64686e104431101d4f279f557857f3b6455ce6ad7870063b05bfdfdc.png]]

### Safety
![[84a34068929e98e8cb3474ed3ea6f42f61a5ebf9ef297586eecb040bcaab0f4a.png]]
