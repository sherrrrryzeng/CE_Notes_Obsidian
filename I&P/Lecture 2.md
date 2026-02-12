---
date: 2025-11-14
Prof: Ruud van Ommen
aliases:
  - Particle Characterization
---
# Particle Size and Shape
## Size descriptors
### One-dimensional size descriptors
- Feret diameter $D_F$
	distance between two parallel tangents on opposite sides of the image of a randomly oriented particle (sometimes average)
- Martin diameter $D_M$
	diameter of the particle at the point that divides an randomly oriented particle into 2 equal projected areas (sometimes average)
- Breadth $B$
	minimum Feret diameter of the projection of a particle, when it is resting in its position of maximum stability
- Length $L$
	Feret diameter perpendicular to the breadth (sometimes the maximum Feret diameter)
- Chord length $CL$
- Thickness $T$
![[64a9449d6ae283258c18965867e04464c7bbdeadaf86fce8e490c711135c0d0f.png]]

### Equivalent spheres
![[938ae35ec97dddf2bce76462541c12e6a5628b3111dad696692f1f3b6edd60c7.png]]
**\* ==Sieving conditions== will influence outcome in practice**
\* ==Reynolds number== will also influence equivalent spheres of the sedimentation

## Particle Size Distributions (PSDs)
- Number-based
- Area-based
- Volume-based
- Others (e.g., light scattering model)
- Recalculation
![[68671e53497b5b6ef99e528d441ffd91ee8d79159f30fc82d49c26ad0d876382.png]]

When drawing PSDs:
![[7af110144681d8e82cf8a0ad8f67ac66ebd0747801d4e1d2a0c3a63a9050bcf4.png]] There is a problem: ![[48f1d132f3fb0d35e4ca808255232f14adba161be45b2dfc7739b047c2181ea4.png]]
-> **The distribution depends on the sieves, thus it's better to use frequency.** 
-> Divide the frequency by the width of the bin. Then the influence of different bin sizes is removed and the area under the curve is now 1. 
->![[765130b373535b812001bbc0601a7f95f55009a9aef9abbcdc9ce6d4d59cd15d.png]]

\* Surface-Volume equivalent: the ratio of surface/volume


### Characteristic size distribution parameters
1. $D_{10},\,\,D_{50},\,\,D_{90},\,\,etc.$ 
2. **Mode**: peak *(the highest)* ![[b84ec10deb802dda9adfc3dc53f01013e5fa7313acf2fa3fac84b3d9c524850d.png]]
3. **Weighted mean values** (moments)![[8c4e5bee000d3328e239d05a37c0a21be5ccc4ed38efb6a7736b2f6ec582979a.png]]
4. **Size distribution width** *(e.g., $D_{90}-D_{10}$)*

### Model Distributions
![[4c44281f5e304d041bd7d617ab17918b286704229beb667f129e36a5c31849b4.png]]
- Bottom-up (aggregation): several small -> one large
- Top down (grinding): One large -> several small


## Shape Description
### Qualitative description of shape
- equant 等轴状
- columnar
- acicular 针状
- fibrous
- lath 板条状
- plate
- flake
- dendritic 树枝状
- angular
- granular 颗粒状
- irregular
- rounded

### Macroshape descriptors
![[aab0b633482e392898f6a1babeaf4797a86a5afe3a139d5b2d43b25249cbdfd6.png]]

### Fractal shape analysis
![[14e034252159e45c53b6840f9ec6f54fa4298e10c077e58eb107937cf170d13b.png]]
![[d864f301c939cc2d7913711c031a9de7d7f0f88f928f9885af5f551d6dfa4c3d.png]]
*( $D_f$ is the fractal dimension $\delta$ )*
![[7bed0d0530de1846b3617254adbd01c9469d084aad1b148adcfaff1283c14181.png]]


# How to determine Particle Size?
## Separation Techniques
- Air classification
- Electrical mobility analysis 
- Hydrodynamic chromatography 流体动力色谱 (HDC)
- Impaction
- **Sedimentation**
	gravity; centrifugal; flow field fractionation 场流分离 (FFF)
- **Sieving**
	Particles need to be large enough
- Size exclusion

## Fingerprint Techniques
- **Microscopy
	- **Optical Microscope**: 
		==Great for particles== > 1µm
		But not very precise
	- **SEM(Scanning Electron Microscopy)**: 
	    Particle morphology & ==surface morphology==
	    1 nm - 500 µm
	    Elemental analysis
	- **TEM(Transmission Electron Microscopy)**: 
		Particle morphology 2D projection - ==internal structure==
		0.5 nm - 5 µm
		Elemental analysis & Electron diffraction &
		EELS (electron energy loss spectroscopy)
	SEM vs. TEM: ![[c3d2b714d4f8fe0b3ee24eed3f44593421b3cc9555d5ccdefcd7d5fc04f867e3.png]]
	
	**Pros & Cons of -EM Techniques**: 
	- +:
		direct
		Morphology
		Elemental analysis
	- +/-:
		individual particles
		only solids
	- -:
		small volumes studied
		possible damage due to electron beam
	
- **Image analysis**
- Chord length 弦长
- **Electrical sensing zone** 电感区法
- Flow cytometry 流式细胞术
- Optical particle counters 光学颗粒计数器 (OPC)
- Phase Doppler anemometry 相位多普勒测速法 (PDA / PDPA)
- Time of flight 飞行时间法 (TOF)

## Particle Ensemble Techniques
- Dynamic light scattering (Brownian motion) 动态光散射 (DLS)
- Electro-acoustic 电声法
- **Laser diffraction (Mie theory)**
	![[160edd2a057ead6c3faa5774b2418831590dd6bcc0282cbe811618ca976dcabf.png]] Calculation of Laser diffraction![[41ca86a1a8792c6169740fc386b2c43f676a34e4d71487f37dadbd92cc624c6a.png]]
	
- Ultrasound extinction 超声衰减法
- Nuclear magnetic resonance (NMR)
- Small-angle X-ray scattering (SAXS)


## Golden rules Sampling
- Use representative samples
- Quantify and optimize sampling errors
- Sample where material is well mixed
- Sample when material is in motion
- Use proper sampling containers
- Make for each product a Protocol & SOP (Standard Operating Procedure)