## Soft Condensed Matter
### **Soft Matter**
Soft matter is a subfield of condensed matter comprising a variety of **physical states** that are easily deformed by thermal stresses or thermal fluctuations. 
*They include liquids, colloids, polymers, foams, gels, granular materials, and a number of biological materials.* 

**Why soft matter is soft:**
$E\approx k_BT$: These materials share an important common feature: predominant physical behaviours occur at an energy scale comparable with **==room temperature thermal energy==**. 


### **Relaxation time**
Relaxation time is the time taken by a soft material to **respond** to an applied stress (physical or thermal) through molecular or atomic **rearrangement**. 


### **Experimental time**
Experimental time is the amount of time needed to **observe** a response or change in configuration in soft matter systems. Depending on the time of observation, different properties from the same material maybe obtained. 


### **Glassy state**
Glassy state is a state of matter in which a liquid is cooled fast enough that it forms an **amorphous** state of **lower density** as compared to that of a crystal. 
At low temperature Arrhenius viscosity breaks down, as a soft matter in glassy state demonstrates a **infinite apparent viscosity**. In reality the timescale of the observation (experimental time) is not long enough to observe the flow of such a material. 


### **Lennard Jones potential**
![[Pasted image 20260117110653.png]]

![[e312c8bca1e61c40bf30a06289cd153e4ceea66159a7e366c0551bdb8b674d3d.png]]
The above is a schematic of the periodic potential of a lattice of a metallic solid. As observed the atoms rest on the deep well in the potential that is at the **equilibrium distance** of atoms. 
The Lennard-Jones potential is a pair wise potential that approximates the potential of the entire solid by including only interactions of the nearest neighbours while **neglecting others**. 
By neglecting the **higher order terms** in the representation of the potential, we only shift the depth of the well by scaling factor and not change the behaviour of the material. Hence it is sufficient to explain the Young's modulus of the material. 

*(The Lennard-Jones potential primarily accounts for nearest neighbour interactions; contributions from more distant molecules are considered higher-order effects and hence can be considered negligible in comparison.)*


## Colloidal Dispersions
### **Colloids**
A colloidal dispersion is a heterogeneous system in which particles of solid or droplets of liquid with dimensions of order 10 $\mu m$ or less are dispersed in a liquid medium. 

**Why are colloidal dispersions considered as soft matter?**
Colloidal dispersions are dominated by thermal fluctuations, Brownian motion, surface forces, and weak interparticle interactions. Their structure and properties change easily under small **thermal stresses**, which is the characteristic of soft matter.


### **Brownian motion**
Brownian motion is the random, jittery motion of small particles resulting from constant collisions with solvent molecules. 
We can use **Random Walk** model to approach modelling it, using **Langevin** equation or diffusion equation(**Stokes-Einstein** relation). 


### **Molecular interactions**
Macroscopic surfaces are rough at micro- and nano- scales, so only a tiny fraction of atoms or molecules get close enough for strong van der Waals attraction.
*Cling film adheres better because soft polymers can **deform and conform to surface irregularities**, increasing real contact area.* 
*Metallic solid is still and can not conform.*

### **Hard-sphere model (HS)**
Spherical particles feel an infinity force whenever their surfaces contact due to the presence of very small alkanes on the silica surface. 

**With long polymer chains:**
Long polymer chains create a thick **steric brush**, causing an additional soft, repulsive, entropic force when polymer layers overlap. The interaction becomes soft-repulsive instead of hard-sphere-like. 

**Additional polymers**:
When the additional polymers are non-adsorbing, the interaction becomes polymer-induced **depletion attraction**:
	Higher molar mass → larger polymer coils → larger excluded volume → stronger and longer-ranged attractive depletion force.

**In water:**
silica surfaces ionize and become charged; electrostatic double layers create long-ranged repulsion → strong deviation from HS behaviour.

**Adding salt:**
Low salt:
   longer Debye length → long-ranged electrostatic repulsion
High salt: 
   screening is strong → short-ranged interaction.


## Polymers
### **Tacticity**
Tacticity describes how the side groups on polymer backbone are arranged in space. It's a stereochemical property. 
The different types are: 
- isotactic
- syndiotactic
- atactic
A highly crystalline polymer could have either isotactic or syndiotactic arrangement. 

### **Kuhn length & Contour length**
For the correlations of real chains, we replace monomer length with an **effective segment length**, which is the Kuhn length. It means the length of an equivalent freely jointed segment that reproduced the real chain's statistic.
Contour length is the **fully stretched** length of the polymer. 
The end-to-end distance of a polymer:
$$<R^2>=C_{\infty}Na^2=Nb^2$$

### **Radius of gyration**
The radius of gyration of a polymer is defined as the root-mean-square (RMS) distance of all monomers of the polymer from the **common centre of gravity**. For a Gaussian coil $R_g=\sqrt{\frac{<R^2>}{6}}$. 


### **Good solvent**
Polymer segments prefer good solvents, in which they swell by the excluded-volume exponent $v\approx 0.6$. 
In theta solvent polymer-solvent interactions cancel excluded volume effects. So the system is similar to ideal chain model, where $v=0.5$. 
In poor solvent monomer-monomer attraction dominates and chain collapses into a globule. Scaling $v\approx 1/3$. 
End-to-end distance correlates with the number of monomers: $$R\sim N^v$$

### **Rouse model & Reptation model**
The Rouse model treats polymer as beads connected by springs, which is applicable to **short chains in melt**. It predicts diffusion and relaxation time scaling like $$\tau_R\sim N^2$$
The reptation model considers chains as being constrained to move inside a "tube" formed by surrounding chains, which applied to **long, entangled polymer melts**. It predicts relaxation time scaling like $$\tau_d\sim N^{3\sim 3.4}$$


## Gels
### **Reptation time**
Reptation time $\tau_d$ is the time taken by a polymer chain to 'reptate' or navigate through an imaginary 'tube' formed by entanglements, which results in stress relaxation. It's also known as the terminal time $T_t$. 

**Does it exist only in long, entangled polymer melts?**
No. The phenomenon of reptation is primarily found in long-chain polymer melts, but it also occurs in ==**concentrated polymer solutions**==. 


### **Gel**
A gel is a soft material composed of subunits that are able to bond with each other to form a **network** of macroscopic dimensions, in which all subunits are connected by bonds. 
A gel exhibits the **mechanical properties characteristic of a solid**, such as the ability to sustain shear stress with a spanning network, even though it may contain a high volume fraction of liquid solvent. 

**Two kinds of gels based on interactions:**
Chemical gels consist of network cross-linked by **covalent bonds**; Physical gels are formed by non-covalent interactions such as hydrogen bonds, van der Waals forces, etc. 
Chemical cross-linked gels have higher rheological properties as compared to physical gels. 


### **Gelation**
For gelation, we start with individual subunits, to which bonds are added at random. As the bonds between subunits increase, clusters of points are formed. Ultimately the clusters joint to form a network which spans the entire system. The gel fraction abruptly rises from zero at the gel point. 


## Phase Transition
### **Phase Diagram**
  A phase diagram for any given substance or molecular system is a graphic representation of the phases that **the substance/system can take as a function of "appropriate" variables**. Usually the phase relate to a molecular or supramolecular structure and the "appropriate" variables can be chosen according to the situation. 
  For instance, in a binary system such as for a polymer solution (polymer + solvent) at constant volume and pressure, it is convenience to represent the phase diagram on the plane defined by temperature against polymer concentration. 

### **Interaction Parameter $\mathcal{X}$**
  The interaction parameter is defined as the ratio between the mutual pair interaction energies ($u_{AA},u_{AB},u_{BB}$) between two molecular species in the system and the absolute temperature. 
  $\mathcal{X}$ is therefore $\sim\frac{1}{T}$.  Assuming that those interaction energies do not vary significantly with temperature, one can represent the phase diagram of binary mixtures by using T or $\mathcal{X}$ in one of the axis.

### **Spinodal Decomposition**
Spinodal decomposition is the spontaneous phase separation that occurs when a binary mixture is brought to the **unstable** region of the phase diagram. 
The lever rule: $$f_1 = \frac{\phi_{coex}^2 - C_0}{\phi_{coex}^2 - \phi_{coex}^1}\,\,\,\,\,\,\,\,\,\,f_2 = \frac{C_0 - \phi_{coex}^1}{\phi_{coex}^2 - \phi_{coex}^1}$$
### **Nucleation**
The spontaneous formation of a **droplet or aggregate** of one component in another component.

- **Homogeneous nucleation** 
	A nucleus may be formed when ==thermal fluctuations== bring molecules closer and they interact with each other to form a small particle. 
- **Heterogeneous nucleation**
    An ==impurity== (dust/dirt) can provide a surface on which the molecules aggregate to form a nucleus. 
	
The latter is more energy efficient since the energy to form an interface of a small droplet in the other substance is quite high and that interface is usually small in the case of heterogeneous nucleation.


### **Optimum Domain Size**
The growth of droplets of one substance, say **A**, in the bulk of the other substance, say **B**, in a binary mixture A–B implies that molecules of A should be able to diffuse through B to join an aggregate of A molecules.

In case the droplets of A are too big, the **distance** between them is too large and molecules of A have to diffuse very long distance to join an aggregate.

If the droplets of A are too small, the amount of **interface** created by too many small droplets costs too much energy.

The balance between the two arguments above indicates that there is an optimum that favours growth of the aggregates.


## Self Assembly
### **Supramolecular Self-assembly**
The process by which molecules assemble spontaneously to form architectures that are larger than the size of a gew molecules (typically in the order of nm to $\mu m$). 

*Based on non-covalent chemical bonds (hydrogen bonding, hydrophobic effect, van der Waals, etc.*

### **CMC**
In term of surfactants, critical micelle concentration is the minimum concentration at which aggregation of molecules is observed resulting in the formation of micelles. 

### **Morphology of micelles**
The packing parameter determines the morphology of the self-assembled aggregate. $$P=\frac{v_0}{a_0l}$$In the case of diblock or triblock copolymers, the block length is related to the packing parameter and hence determines the shape. 

| **Packing Parameter (P)** | **Molecular Geometry** | **Aggregate Morphology**             |
| ------------------------- | ---------------------- | ------------------------------------ |
| $P \le 1/3$               | Conical                | Spherical Micelles               |
| $1/3 < P \le 1/2$         | Truncated Conical      | Cylindrical (Worm-like) Micelles |
| $1/2 < P \le 1$           | Cylindrical            | Flexible Bilayers / Vesicles     |
| $P \approx 1$             | Planar / Cylindrical   | Planar Bilayers (Lamellae)       |
| $P > 1$                   | Inverted Conical       | Inverted Structures              |

### **Micelle size distribution**
**Worm like micelles** are formed by surfactant molecules with usually a packing parameter that promotes supramolecular cylindrical structures. Under thermal equilibrium, scission may happen with equal probability at any point along the cylindrical micelle (except at the ends). Hence at thermal equilibrium, a broad distribution of cylindrical lengths is possible. 
