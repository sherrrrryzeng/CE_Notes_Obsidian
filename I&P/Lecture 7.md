---
date: 2025-12-01
Prof: Ruud van Ommen
aliases:
  - Flowing systems
---
# Flow: which forces?

1. Gravitational force $F_g=mg$
2. Pressure gradient $F_P=A\triangle P$
3. Drag force 
	- **General equation**: $$F_D=\frac{1}{2}\rho v_{rel}^2C_DA$$*$C_D$: drag coefficient*
	
	- $Re<<1$ (**laminar flow**)-> Stokes' law $$F_D=6\pi\eta\alpha v$$
	- $5\cdot 10^2<Re<10^5$ -> Newton's law $$C_D\approx 0.44$$
	The relationship between $C_D$ and Reynolds number: ![[8906eda53718947368c3ff7086398e20a18a9dbd737f21bd3fa8cd4fb1189c19.png]]
	
- *Other forces : buoyancy, interparticle forces, surface tension, etc.*


There are many solution (flow meters) for single-phase flow. BUT quite complex for multi-phase flow.


# Flow regimes

 Reynolds' number: $$Re=\frac{\rho uD}{\eta}$$
- Laminar regime
- Regime transition - $Re=\,\sim 2000\to 13000$ 
- Turbulent regime

 
## Flow regimes with not-fully-liquid flow
### Gas-Liquid Flow
**Vertical G-L flow**![[ac8a14669acc7fab6184ad951822c8d950447a800f466ed13ef4ee852ea3c67d.png]]

**horizontal G-L flow** ![[541f4333554155c366d558c68a4bab11d53452a90b24393b4dd7ab001a488b63.png]]


### Liquid-Solid Flow
**Horizontal L-S flow** ![[278de71a688989a78376226448b289c818ab719d0066477580b5e763732e8171.png]]
- homogeneous flow
- heterogeneous flow
- saltation flow
- stationary bed


## Gas-Solid Flow
### Geldart's powder classification
![[2c439e8e5c25531154eade471a4c3e6325ca0bfde267360d1b84d526e05b7072.png]]

- **Geldart A: Aeratable powders**
	 Aeratable($U_{mb}>U_{mf}$) material has a significant deaeration time. 
		 $U_{mb}$: minimum bubbling velocity
		 $U_{mf}$: minimum fluidization velocity
	 Used in **catalyst reactions**
	
- **Geldart B: Sand-like particles**
	 Bubbles above $U_{mf}$ ($U_{mb}\approx U_{mf}$)
	 Used in **combustion or gasification**
	
- **Geldart C: Cohesive powders**
	 Interparticle forces are too strong *(flour, fly ash)*
	 **Hardly used**
	
- **Geldart D: Spoutable particles** *(Wheat)*
	 Particle size is large that interparticle forces can be ignored compared to gravity and inertial forces. 
	 Used in **drying or PE production**


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
	- Spouting or jetting, ==not smooth fluidization


**Vertical G-S flow - Fluidization regimes**
![[cc580c65ca6a02186922adcfa0ed3d07a54aed6f1aaf32f45d7ed02e784b5403.png]]
![[781da8f887a0c1fa244a57d294341f6e41c2840c9851b2814ddb0a064bad6f58.png]]


**Horizontal G-S flow**
![[3edb157cd225297a0aaa5f36a93aeb3f67c3d408021654db042285ced1d09f1f.png]]


## GLS-system
(Gas bubble in a neutrally buoyant L-S system)
*only gas going through, while liquid and solid stay still*



# Jamming
![[5d4750a993b9ec11f932b36a9780396c11a3646b9619afa6e9c981abe3d9db1b.png]]

Find the suitable **==force**== for **yielding** between the **jammed (solid)** side and the **flowing (liquid)** side. 

## Jamming Phase Diagram 
![[6e0e58c37f93f9fc156b18825a3f41907abed7417ab99e72b64e56bd74d47207.png]]

Axis:
- **Temperature (T):** At high temperatures, particles have higher kinetic energy($k_BT$), allowing them to overcome local barriers and flow easily.
- **1/Density:** Represents the **degree of crowding**. As this value decreases (density increases), particles become physically packed, leading to a "structural arrest" where they can no longer move past one another.
- **Load (Shear Stress, σ):** Applying sufficient external force can force a jammed substance to flow. 

- Vertical Axis ($\frac{k_B​T}{U}$): The ratio of **thermal energy $k_BT$ to attractive interaction energy $U$**. A smaller value indicates that the attraction is dominant, which leads to **irreversible aggregation**. 
- Horizontal Axis ($\frac{\sigma}{\sigma_0}$): The **normalized stress** (or yield stress). It measures the external force required to break the structural network of the material. 
- Side Axis ($\frac{1}{ϕ}$): The reciprocal of the **volume fraction** (ϕ). Similar to 1/Density, it tracks the transition from a dilute state to a dense, packed state. 

| Dimension     | Core Variable                         |       Conditions for Jamming       | Conditions for Flow<br>(Un-jamming) |
| ------------- | ------------------------------------- | :--------------------------------: | ----------------------------------- |
| **Energy**    | $k_BT$ & $U$                          | **Low T** or **Strong Attraction** | **High T** (Melting)                |
| **Space**     | $1/\text{Density}$ or $1/\phi$        |     **High Density** (Packing)     | **Low Density** (Dilution)          |
| **Mechanics** | $\sigma$ or $\frac{\sigma}{\sigma_0}$ |   **Low Stress** (Consolidation)   | **High Stress** (Yielding)          |

## Consolidation
![[867fd0f0646ac3020a90ba1adcf58fab3f2aa5f776d8a2f8f8239e3bdd69fcc9.png]]
Find the moderate **==imposed stress==** on powder between **fluidised** and **consolidated** conditions. 


# Mixing

Mixing power formula:$$P=P_0\rho N^3D^5$$
- $P_0$: dimensionless power number (impeller geometry);
- $\rho$: density of the fluid;
- $N$: rotational speed, typically rotations per second;
- $D$: diameter of the impeller. 


## The effect of stirrer
- centrifugal force
- speed
- **Impeller**
	- **Position:** ![[06de865f20493c6e15f16a467bd9ae6e44fc844989fb185aa7e9ef0cff7212e8.png]]
	- **Shape:** ![[adcc4d3783786081075a237021e7457fb960bfc5b095303c55215e52ac9c97a4.png]]
	- **Diameter** $$D/T=\frac{\text{Impeller Diameter}}{\text{Tank Diameter}}$$![[effbb766b1a1aea4868cab44cbe88f537d5480c45d09167291aea7aa6cca3621.png]]


- Centrifugal force
- Speed
- **Impeller**
	- **Position**
		1. no baffles: **tangential flow** (circular motion) 
		   -> poor top-to-bottom mixing
		2. with baffles: **axial** and **radial** flow patterns
		   -> rapid and uniform mixing
		3. incorrect position: asymmetrical flow cause mechanical **vibrations**(no good for machine).
		   -> dead zones
	- **Shape
		1. **Axial impellers**: High Flow / Low Shear
		   -> Mixing, Solids Suspension
		2. **Radial impellers**: Low Flow / High Shear
		   -> Gas-Liquid Dispersion, Emulsification
	- **Diameter** $$D/T=\frac{\text{Impeller Diameter}}{\text{Tank Diameter}}$$        $0.3<D/T<0.5$ is considered as optimal. 

Mixing of particles:
	stirrers in different shape (helix, spiral, double-spirals, etc)

**Applications**: X-ray imaging
	 fluidized bed of cohesive powder 