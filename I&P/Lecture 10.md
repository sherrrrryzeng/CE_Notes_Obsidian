---
date: 2025-12-12
Prof: Ruud van Ommen
aliases:
  - Production of Solid Particles
---
Two approaches for making particles:
- Top-down (bulk -> fragment -> particles)
- Bottom-up (particles <- clusters <- atoms)

# Particle Production Methods
## Flame Spray Pyrolysis (FSP)
A "bottom-up" approach
Based on the exothermic combustion of a **==liquid==** **precursor spray**

*From ChatGPT:*
- **Precursor Preparation:** A liquid precursor is dissolved or mixed in an organic solvent (like alcohol).
- **Aerosolization and Combustion:** This liquid mixture is pumped through a **nozzle** and **atomized** (dispersed) using a high-pressure gas (often oxygen) to create a fine aerosol spray. The aerosol is then immediately ignited by a pilot flame (e.g., methane/oxygen).
- **Nanoparticle Formation:** The solvent's combustion provides the energy for the process - the metallorganic precursors decompose, vaporize, and oxidize, forming metal vapor or oxyanions in the gas phase. These vapors then undergo rapid nucleation (formation of tiny clusters) and growth by collision and sintering, forming primary nanoparticles.
- **Quenching and Collection:** The particles quickly pass out of the high-temperature zone, which causes rapid quenching (cooling), resulting in fine, crystalline, and often non-aggregated nanoparticles. The final powders are collected using a **filter** system.

Types: 
- Vapour-fed Aerosol Flame Synthesis (VAFS)
- Flame Spray Pyrolysis (FSP) *(liquid solution)*
- Flame Assisted Spray Pyrolysis (FASP)

Two-nozzle flame spray synthesis of compound catalyst

*Example:* Flame synthesis of (fumed) silica ![[f778a31ddfa75e846a1db2ff04be0ccf5e152c02c61b28ab3aa923c2dd8f012b.png]]
- **Aggregates** are permanently bonded by strong chemical or sinter forces and cannot be easily dispersed
- **Agglomerates** are loosely held together by weak cohesive forces (like van der Waals) and can be broken apart by mechanical agitation.


## Spray Drying
A unit operation were a **==fluid==** feed is transformed into a dry form by spraying it into a gaseous medium. 
Four phases:
1. Atomisation nozzle
2. Contact between air and spray
3. Drying the spray
4. Separation of the dried product

Types - choose based on your product (quality & quantity)
- **co-current**
	 with evaporation the temperature stays relatively low
- **counter-current**
	 particles reach high temperature later -> low moisture

![[00f53bef1019672e0eb11e5fc8c18b98cc6d638a31dfd21f0339aaa40e80a86b.png]]

### The process of drying
![[1aad9592cdc0e93b40d8c52872315f605f68be063a6aefa2eae0ad83e606e429.png]]

Enthalpy:$$dH=mC_pdT$$Specific enthalpy: $$dh=C_PdT$$
The enthalpy of air and water is high. 
-> Try to get the liquid concentrated as much as possible before entering a spray dryer. 


#### Nozzle types
- **pressure nozzle**
	 quite large flow rates
	 steady liquid flow needed
	 little variation possible in droplet sizes
- **twin fluid nozzle**
	 flexible droplets size setting
	 fluctuating flows possible
- **rotary atomisers**
	 large flow rates possible
	 broad size distribution
	 some droplet size influence possible


### Spray drying and Agglomeration
Mechanism of spray drying and **agglomeration**: ![[21981a28910fab73fe3164cbd3fa47791d9a00ad21a1382ebf51ad6b6f2f438e.png]]

**Spray dried product**: 
- Particle size 10-50 um (Geldart C)
- Dusty material
- Often poor flowability
- Poor dispersibility

**Agglomerated product**:
- Size from 100-1000 um (Geldart B/D)
- Product has instant properties
- Low dusting
- Free or easy flowing


### Prilling
![[555b8c644535ef281a4578190fd73c760f850ea24ed657c3671aed520612946e.png]]
- **Molten material as input**
- **Counter-current - cold air**
-> everything becomes **==spherical==** particle (prills) 
	 - larger particles *(500-4000mm)*
	 - good flowability
   
Application: large-scale products *(urea, ammonium nitrate, lead shot)*



## Crystallization
To provoke crystallization the state of a solution is shifted from **(under)saturated to supersaturated** by an external action

The nature of the external action determines the method: 
- **Crystallisation from solution**
	- Evaporative crystallisation
	- Cooling crystallisation
	- Anti-solvent crystallisation
	- Precipitation
- **Melt crystallisation**

### Cooling Crystallisation
Principle: direct or indirect cooling ![[518658b6e9f69315ebea02f0872811778dc5a1947fd2d8fd065176e8b5d54b92.png]]
Phase diagram: 
- Easily soluble compounds (10-300 kg/m3)
- Solubility curve has a steep, positive slope
- Solubility at low temperature is low

Pros:
+ low energy consumption; 
+ mild operating conditions; 
+ large crystals of high quality
Cons:
- recovery (limited yield: loss of soluble product)
- scaling on cooling surface


### Evaporative Crystallisation
Application: sea salt production
Principle: Solvent removal by adding heat and reduced pressure
![[ea7cfb3c085dc51940f0bee3024a839f8d544b8d0e9e98d73b131f898f0ee666.png]]
Phase diagram:
- Easily soluble compounds (10-300kg/m3)
- The only choice if solubility curve is flat

Pros:
+ high yield is possible
+ large crystals of high quality
+ less scaling
Cons:
- high energy consumption
- less mild process conditions
- more complicated equipment


### Anti-solvent Crystallisation
Principle: mixing solution with an anti-solvent
![[d68313008ecdc328e132fb577a2a5455b7245916092e02dc129069126577c103.png]]
Phase diagram:
- solute is well-soluble in the solvent, but slightly soluble $(10^{-3}-1\, kg/m^{-3})$ in the anti-solvent

Pros:
+ low final solubility: yield can be high
+ low temperature
Cons:
- Non uniform process conditions due to mixing of inlet streams
- low product quality (small agglomerated crystals & impure product )
- heat of mixing can be substantial
- recovery of solvent and antisolvent needed


### Precipitation
Principle: mixing of two well-soluble reactants to give a slightly soluble product
![[6bed5b1fcd0844338f57b00b9b1c29dd770436adb82e3c322c5f9366ccac517a.png]]
Phase diagram: 
- Sparingly soluble compounds $(10^{-3}-1\, kg/m^{-3})$ 
- Supersaturation $$S = \frac{a_A\cdot a_B}{K_{sp}}$$
- High local supersaturations at inlets

Pros:
+ only method for slightly soluble salts
+ production of small particles
Cons:
- high residence times required for aging to larger particle size
- Non uniform process conditions due to mixing of inlet streams
- low product quality (agglomeration/impurities)



### Melt Crystallization
Principle: cooling
- The **melting point** is a function of the purity of the crystalline phase
- Decrease the temperature below the melting point
![[9f20348895e7fd8546bc070c8e40df9028b0be3dc7485750107189e96c644557.png]]
![[3f65b012b037d5440118352e6dd3d009ea024961eed7643fe5c80b7a274be8c9.png]]
- In a Eutectic system: Obtain crystalline A without B 
- In a solid solution system: Obtain A and B together. 

Phase diagram:
- For compounds at a high (>90 wt%) concentration (eutectic systems)
- For solid solutions (not for solid azeotropes)
- Melting point between 0 and 100 °C

Pros:
+ ultra pure product (>99.99 to 99.999 wt%)
+ mild operation conditions/ lower energy usage
Cons:
- Often multiple stages needed
- Expensive equipment


### Crystallization method selection
![[51c9363f37cc6462e931d2345b0239c6ffea2abeb171fa5fb6400259b84ee2ff.png]]

Summary:
## Comparison of Crystallization Methods

| Method                           | Solubility / Phase Diagram                                      | Pros                                                                            | Cons                                                              |
| :------------------------------- | :-------------------------------------------------------------- | :------------------------------------------------------------------------------ | :---------------------------------------------------------------- |
| **Precipitation**                | Sparingly soluble compounds ($10^{-3}–1$ kg/$m^3$)              | + ==Only method== for slightly soluble salts<br>+ Production of small particles | - Agglomeration & impurities<br>- High residence time for aging   |
| **Anti-solvent Crystallization** | Well-soluble in solvent;<br>slightly soluble in anti-solvent    | + High yield<br>+ Low temperature                                               | - Small agglomerated crystals<br>- Solvent recovery needed        |
| **Cooling Crystallization**      | Easily soluble; <br>steep positive solubility curve             | + Large, high-quality crystals<br>+ Low energy usage                            | - Limited yield (loss of product)<br>- Scaling on cooling surface |
| **Evaporative Crystallization**  | Easily soluble; <br>==only choice== if solubility curve is flat | + High yield possible<br>+ Large, high-quality crystals                         | - High energy consumption<br>- Complex equipment                  |
| **Melt Crystallization**         | High concentration (>90%); <br>Eutectic or Solid Solution       | + ==Ultra pure== product (>99.99%)<br>+ Mild conditions                         | - Multiple stages often needed<br>- Expensive equipment           |


# Milling/Grinding
Top-down

Why crush/grind particles?
- To release valuable minerals from ores
- To increase the specific surface area
- To produce particles of certain size/shape

Cons: 
- High energy consumption
- Low efficiency
- Too empirical models

Main mechanisms of breaking a particle: Tension & Shear
![[2015e860ac37a370a5220fdc3a03fad2b90c290779a80c8a7a41f04dfba63377.png]]


### Single Particle Breakage
![[9b3cc5348829d53291fc96d3764ef70a42f8a2c2f59035942670863551b5eeed.png]]
- Hooke's Law $$\sigma=Y\varepsilon$$ $Y$ : stiffness or elasticity tensor
- Stress $$\sigma=\frac{F}{A}$$
- Strain: $$\varepsilon=\frac{x}{L_0}$$

### Predicting Energy Requirements
- Rittinger(1867): Energy required is proportional to amount of **new surface** created.$$\frac{k_s}{k_v\rho_p}(\frac{1}{x_2}-\frac{1}{x_1})\,\,\to\,\,E=C_R(\frac{1}{x_2}-\frac{1}{x_1})$$ *x1: feed particles size; x2: product particle size*

- Kick(1885): Energy requirement is related to ratio **feed size/product size**. $$E=C_K\ln\frac{x_1}{x_2}$$ *usually under predicts for fine grinding*

- Bond(1952): Based on large amount of experimental data. $$E_B=W_I(\frac{10}{\sqrt{X_2}}-\frac{10}{\sqrt{X_1}})$$ Feed X1, Product X2: **sieve size** through which 80% passes (in $\mu m$)
  ==**most often used**== of the three presented.

![[e4b20ec5bd553ed8e0965151dd753bca80a04b56556c9906b8369bb471edae1a.png]]


### Grinding Equipment
How to choose: rely on common sense
Take into account: 
- Feed size
- Desired product size
- Feed composition/chemical structure
- Desired production rate

Grinding machine and feed particle size:
![[58846d6cb6eaf48cd3f4c318da549987d6b5ded795e8e147ed9e83e0609d5170.png]]


General considerations regarding particle properties - **Toughness**: 
- Tough materials are difficult to break/shatter
- Deform rather than break
- Lowering temperature may change material from tough to brittle (polymers)
- Use a cutting action rather than compressive forces

Grinding machine and the material hardness properties:
![[9d68480427b0b9e772350aff2c74ca5a68b063e59be189751164390a5c00d566.png]]


### Sol-gel method
![[bfda6b142d9998bacc9352917a855fe6af91bfd4323d084839884b78f57d7cc5.png]]


## Nanoparticle synthesis
- Conventional Electrospray
- Laser pyrolysis of a volatile precursor
- Spark Discharge
