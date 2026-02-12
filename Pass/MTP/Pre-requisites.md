# 1. Mathematics
##  Differential Equations 

if $y = \frac{u}{v}$: $$y' = \frac{u'v - uv'}{v^2}$$$$\frac{d}{dx}(a^x) = a^x \ln a \quad (a > 0, a \neq 1)$$$$\frac{d}{dx}(\log_a x) = \frac{1}{x \ln a} \quad (a > 0, a \neq 1)$$$$\frac{d}{dx}(\tan x) = \sec^2 x= \frac{1}{\cos^2 x}$$$$\frac{d}{dx}(\cot x) = -\csc^2 x= -\frac{1}{\sin^2 x}$$$$\frac{d}{dx}(\sec x) = \sec x \tan x$$$$\frac{d}{dx}(\csc x) = -\csc x \cot x$$$$\frac{d}{dx}(\arcsin x) = \frac{1}{\sqrt{1-x^2}}$$$$\frac{d}{dx}(\arccos x) = -\frac{1}{\sqrt{1-x^2}}$$$$\frac{d}{dx}(\arctan x) = \frac{1}{1+x^2}$$
### 1. The Chain Rule
if `y = f(u)` and `u = g(x)`：
$$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$

### 2. First-Order Homogeneous ODEs
$$\frac{dy}{dx} = F(\frac{y}{x})$$
`v = y/x,y = vx`:
1. **$\frac{dy}{dx} = v + x\frac{dv}{dx}$
2. **$v + x\frac{dv}{dx} = F(v)$
3. **$\frac{dv}{F(v)-v} = \frac{dx}{x}$
4. Integrate and Solve

#### E.p. 1
> [!Example]
> $$\frac{dy}{dx} = \frac{x^2 + y^2}{xy}$$
>then: $$\frac{dy}{dx} = \frac{1 + (\frac{y}{x})^2}{\frac{y}{x}}$$
>$F(v) = \frac{1 + v^2}{v}$ (where $v = \frac{y}{x}$)
>$$v + x\frac{dv}{dx} = \frac{1 + v^2}{v}$$
>Simplify: $$x\frac{dv}{dx} = \frac{1 + v^2}{v} - v = \frac{1}{v}$$
>Separate: $$v  dv = \frac{dx}{x}$$
>Integrate: $$\int v  dv = \int \frac{1}{x}  dx$$
$$\frac{1}{2}v^2 = \ln|x| + C$$
>Back-Substitute for General Solution: $$y^2 = 2x^2 (\ln|x| + C)$$

---






### 3. First-Order Non-Homogeneous Linear ODEs

$$\frac{dy}{dx} + P(x)y = Q(x)$$

1. ==Find Integrating Factor==：$$\mu(x) = e^{\int P(x)dx}$$
2. Multiply by Integrating Factor：$$\mu(x)\frac{dy}{dx} + \mu(x)P(x)y = \mu(x)Q(x)$$
3. Convert to Exact Differential: $$\frac{d}{dx}[y \cdot \mu(x)] = \mu(x)Q(x)$$
4. Integrate and Solve：$$y = \frac{\int \mu(x)Q(x)dx + C}{\mu(x)}$$
#### E.p.2
> [!Example] 
> $$\frac{dy}{dx} + \frac{3}{x}y = x^2$$
>$$P(x) = \frac{3}{x}, \quad Q(x) = x^2$$
>Compute Integrating Factor: $$\text{IF} = e^{\int P(x)dx} = e^{\int \frac{3}{x}dx} = e^{3\ln|x|} = |x|^3$$(Usually we take $x^3$)
>Multiply by Integrating Factor: $$x^3 \frac{dy}{dx} + 3x^2 y = x^5$$
>Convert to Exact Differential Form:$$\frac{d}{dx}(y \cdot x^3) = x^5$$
>Integrate Both Sides: $$y \cdot x^3 = \int x^5 dx = \frac{1}{6}x^6 + C$$
$$y = \frac{1}{6}x^3 + \frac{C}{x^3}$$


---





### 4. Second-Order Homogeneous Constant-Coefficient ODEs
$$a\frac{d^2y}{dx^2} + b\frac{dy}{dx} + cy = 0$$
1. ==Form Characteristic Equation==： $y = e^{rx}$ 
$$ar^2 + br + c = 0$$
2. ==Solve Based on Root Cases==：

a. Distinct Real Roots ($r_1 \neq r_2$)
$$y = C_1e^{r_1x} + C_2e^{r_2x}$$
b. Repeated Real Roots ($r_1 = r_2$)$$y = (C_1 + C_2x)e^{rx}$$c. Complex Conjugate Roots)($r = \alpha \pm i\beta$)
$$y = e^{\alpha x}(C_1\cos\beta x + C_2\sin\beta x)$$

#### E.p.3 
> [!Example] 
> $$\frac{d^2y}{dx^2} - 5\frac{dy}{dx} + 6y = 0$$
>Form Characteristic Equation:$$r^2 - 5r + 6 = 0$$
>Get two distinct real roots: $$r_1 = 2, \quad r_2 = 3$$
Substitute specific values:$$y = C_1e^{2x} + C_2e^{3x}$$
>Verify the Solution:
>-Find first derivative:$$\frac{dy}{dx} = 2C_1e^{2x} + 3C_2e^{3x}$$
>-Find second derivative:$$\frac{d^2y}{dx^2} = 4C_1e^{2x} + 9C_2e^{3x}$$
>-Substitute into original equation to verify: $$(4C_1e^{2x} + 9C_2e^{3x}) - 5(2C_1e^{2x} + 3C_2e^{3x}) + 6(C_1e^{2x} + C_2e^{3x}) = 0$$
Simplify:
$$(4 - 10 + 6)C_1e^{2x} + (9 - 15 + 6)C_2e^{3x} = 0$$
Indeed satisfies the original equation

#### E.p.4

> [!Example] 
>$$\frac{d^2y}{dx^2} + 4\frac{dy}{dx} + 13y = 0$$
>$$r^2 + 4r + 13 = 0$$
>Using quadratic formula: $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
$$r = \frac{-4 \pm \sqrt{4^2 - 4 \cdot 1 \cdot 13}}{2} = \frac{-4 \pm \sqrt{16 - 52}}{2} = \frac{-4 \pm \sqrt{-36}}{2}$$
>Get a pair of complex conjugate roots:$$r = \frac{-4 \pm 6i}{2} = -2 \pm 3i$$
 real part $\alpha = -2$, imaginary part $\beta = 3$
>$$y = e^{-2x}(C_1\cos 3x + C_2\sin 3x)$$
>Verify the Solution:
>-Find first derivative:$$\frac{dy}{dx} = -2e^{-2x}(C_1\cos 3x + C_2\sin 3x) + e^{-2x}(-3C_1\sin 3x + 3C_2\cos 3x)$$
求二阶导数 (Find second derivative):
$$\frac{d^2y}{dx^2} = 4e^{-2x}(C_1\cos 3x + C_2\sin 3x) - 4e^{-2x}(-3C_1\sin 3x + 3C_2\cos 3x) $$
$$+ e^{-2x}(-9C_1\cos 3x - 9C_2\sin 3x)$$
>Substituting into the original equation, all terms will cancel out to give 0, satisfying the original equation.


---



### 5. Application of ==Taylor Expansions== in Differential Equations
$$f(x) \approx f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \cdots$$

*Function: Approximating and Simplifying Nonlinear Equations)*

> [!Example] the Pendulum Equation
>$$\frac{d^2\theta}{dt^2} + \frac{g}{L}\sin\theta = 0$$
>Taylor Expansion(a=0):$$\sin\theta = \theta - \frac{\theta^3}{3!} + \frac{\theta^5}{5!} - \cdots$$Small Angle Approximation ($|\theta| \ll 1$):$$\sin\theta \approx \theta$$$$\frac{d^2\theta}{dt^2} + \frac{g}{L}\theta = 0$$
>Simple Harmonic Motion Solution:
$$\theta(t) = A\cos(\omega t) + B\sin(\omega t)$$
>where $\omega = \sqrt{\frac{g}{L}}$

## Intergal
$$\int \tan x  dx = -\ln |\cos x| + C$$
$$\int \sec^2 x  dx = \tan x + C$$
$$\int \sin^2 x  dx = \frac{x}{2} - \frac{\sin 2x}{4} + C$$
$$\int \cos^2 x  dx = \frac{x}{2} + \frac{\sin 2x}{4} + C$$
$$\int a^x  dx = \frac{a^x}{\ln a} + C \quad (a > 0, a \neq 1)$$
$$\int \frac{1}{x}  dx = \ln |x| + C$$
$$\int \ln x  dx = x \ln x - x + C$$
$$\int \frac{1}{\sqrt{1-x^2}}  dx = \arcsin x + C$$
$$\int \frac{1}{1+x^2}  dx = \arctan x + C$$
- Hyperbolic Functions:
$$\sinh x = \frac{e^x - e^{-x}}{2}$$
$$\cosh x = \frac{e^x + e^{-x}}{2}$$$$\int \sinh x  dx = \cosh x + C$$$$\int \cosh x  dx = \sinh x + C$$
- Integration by Parts:
$$\int u  dv = uv - \int v  du$$
$$\int \frac{1}{x^2+a^2}  dx = \frac{1}{a} \arctan \frac{x}{a} + C$$

## Statistics
### The law of large numbers
- **Weak Law of Large Numbers**: The sample average converges in probability towards the expected value as the sample size grows. 
- **Strong Law of Large Numbers**: The sample average converges almost surely to the expected value as the sample size grows.

### Gaussian(Normal) distribution
$$\mathcal{N}(x \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)$$
Common notation: $$X\sim\mathcal{N}(\mu,\sigma^2)$$
### General formulas (mean square, variance, standard deviation)
-  Mean $\mu$ :
$$\mu= \frac{1}{N}\sum_{i=1}^{N}x_i$$
- Variance  $\sigma^2$:  
$$\sigma^2 = \frac{1}{N}\sum_{i=1}^{N}(x_i - \mu)^2$$
- Standard Deviation  $\sigma$:
$$\sigma = \sqrt{\sigma^2} = \sqrt{\frac{1}{N}\sum_{i=1}^{N}(x_i - \mu)^2}$$
- ==Based on mean and mean of squares==:
$$\sigma^2 = (\text{Mean of Squares}) - (\text{Mean})^2= \frac{\sum x_i^2}{N} - \mu^2 $$
> [!Derivation] 
> $$\begin{aligned}
\sigma^2 &= \frac{1}{N}\sum (x_i - \mu)^2 \\
&= \frac{1}{N}\sum (x_i^2 - 2\mu x_i + \mu^2) \\
&= \frac{1}{N}\sum x_i^2 - \frac{2\mu}{N}\sum x_i + \frac{\mu^2}{N}\sum 1 \\
&= \frac{\sum x_i^2}{N} - 2\mu^2 + \mu^2 \\
&= \frac{\sum x_i^2}{N} - \mu^2
\end{aligned}
$$

###  Sample Formulas

- Sample Mean  $\bar{x}$ :
$$\bar{x}= \frac{1}{n}\sum_{i=1}^{n}x_i$$
- Sample Variance (Unbiased Estimate)  $s^2$:
$$s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2$$
- Sample Standard Deviation $s$:
$$s = \sqrt{s^2} = \sqrt{\frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2}$$
- Computational Formula: 
$$s^2 = \frac{1}{n-1}\left(\sum x_i^2 - n\bar{x}^2\right)$$
> [!Derivation] 
> $$\begin{aligned}
s^2 &= \frac{1}{n-1}\sum (x_i - \bar{x})^2 \\
&= \frac{1}{n-1}\left(\sum x_i^2 - 2\bar{x}\sum x_i + \sum \bar{x}^2\right) \\
&= \frac{1}{n-1}\left(\sum x_i^2 - 2n\bar{x}^2 + n\bar{x}^2\right) \\
&= \frac{1}{n-1}\left(\sum x_i^2 - n\bar{x}^2\right)
\end{aligned}
$$

\***Degrees of Freedom Explanation**:
When using sample mean $\bar{x}$, $\sum(x_i - \bar{x}) = 0$, only $n-1$ deviations can vary freely.

#### E.p.5
> [!Example] 
>Sample: [2,4,6,8]
   >$\sum x_i = 20$, $\bar{x} = 5$
   >$\sum x_i^2 = 4 + 16 + 36 + 64 = 120$
   >$s^2 = \frac{1}{3}(120 - 4 \times 25) = \frac{20}{3}$


# 2. Transport Phenomena
## Concepts

| Concepts                              | description                                                                                                                                                                       |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| steady state                          | system properties do not change with time                                                                                                                                         |
| quasi steady state                    | system change so slowly - can be treated as steady-state                                                                                                                          |
| transient                             | time-dependent state before reaching steady state                                                                                                                                 |
| batch reactor                         | closed system, no flow in or out                                                                                                                                                  |
| plug flow reactor(PFP)                | flow in tubular reactor without mixing in flow direction(axial), but mixing radially                                                                                              |
| stirred tank reactor                  | perfect mixing, output composition equals inside composition                                                                                                                      |
| Poiseuille flow                       | laminar, pressure-driven flow in a pipe/channel with parabolic velocity profile                                                                                                   |
| incompressible flow                   | flow where density remains constant (most liquids, low-speed gases)                                                                                                               |
| dimensionless number                  | pure numbers that have no physical units. (often a ratio)                                                                                                                         |
| Reynolds number(Re)                   | Ratio of inertial to viscous forces. Determines laminar vs. turbulent flow. $$Re = \frac{\rho V L}{\mu}$$                                                                         |
| inertial force                        | force du to fluid mass and acceleration (tends to keep motion going)                                                                                                              |
| drag force                            | resistive force experienced by an object moving through a fluid                                                                                                                   |
| no slip boundary condition            | fluid velocity at a solid boundary equals wall velocity (usually 0)                                                                                                               |
| no shear boundary condition           | shear stress at the boundary is 0 (common at free surface)                                                                                                                        |
| zero flux boundary condition          | no transport(hear, mass, momentum) across boundary (for insulated/impermeable/symmetric boundaries)                                                                               |
| continuity of flux boundary condition | flux across an interface is continuous (no sudden jump)                                                                                                                           |
| continuum approximation               | treat fluid as continuous, ignoring molecular discreteness; valid when Kn<<1                                                                                                      |
| Knudsen number(Kn)                    | Ratio of molecular mean free path to characteristic length$$Kn = \frac{\lambda}{L}$$                                                                                              |
| diffusive transport                   | transport due to random molecular motion (Fourier’s law for heat, Fick’s law for mass, Newton’s second law for momentum)                                                          |
| convective transport                  | transport due to bulk motion of fluid (advection)                                                                                                                                 |
| Peclet number(Pe)                     | ratio of convective to diffusive transport $$heat:Pe = \frac{L V}{\alpha}=Re·Pr$$$$mass:Pe = \frac{L V}{D}=Re·Sc$$$Pe<1$ :Diffusion;  $Pe>1$: Advection                           |
| penetration theory                    | Mass/heat transfer model: fluid elements contact surface for limited time before replacement, allowing unsteady diffusion$$N_A = 2 \sqrt{\frac{D}{\pi t_c}}  (C_s - C_{\infty})$$ |

## Laws & Equations
|               Equation Name                | Formula                                                                                                                                                     |
| :----------------------------------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
|            Newton’s Second Law             | $$F = m a = \frac{d(mv)}{dt}$$                                                                                                                              |
|       Fick’s Second Law of Diffusion       | $$\frac{\partial C}{\partial t} = D \frac{\partial^2 C}{\partial x^2}$$                                                                                     |
|       Fick’s First Law of Diffusion        | $$J = - D \frac{\partial C}{\partial x}$$                                                                                                                   |
|      Fourier’s Law of Heat Conduction      | $$q = - k \frac{\partial T}{\partial x}$$                                                                                                                   |
|         Hagen–Poiseuille Equation          | $$Q = \frac{\pi R^4}{8 \mu L} \, \Delta P$$                                                                                                                 |
| Navier-Strokes Equation (Momentum balance) | $$\rho \left( \frac{\partial \mathbf{v}}{\partial t} + \mathbf{v} \cdot \nabla \mathbf{v} \right) = -\nabla p + \mu \nabla^2 \mathbf{v} + \rho \mathbf{g}$$ |
|                                            |                                                                                                                                                             |
- where:

| Symbol       | Represents                        | Physical Meaning                                                                                                                       |
| :----------- | :-------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| $\rho$       | Density                           | Mass per unit volume of the fluid.                                                                                                     |
| $\mathbf{v}$ | Velocity vector                   | The flow velocity field ($v_x, v_y, v_z$).                                                                                             |
| $t$          | Time                              | The independent time variable.                                                                                                         |
| $p$          | Pressure                          | The thermodynamic pressure in the fluid.                                                                                               |
| $\mu$        | Dynamic viscosity                 | Measure of the fluid's resistance to shear flow.                                                                                       |
| $\mathbf{g}$ | Gravitational acceleration vector | Body force (e.g., gravity) per unit mass acting on the fluid.                                                                          |
| $\nabla$     | Del operator                      | Vector differential operator ($\frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z}$).                |
| $\nabla^2$   | Laplacian operator                | Second order spatial derivative $\frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + \frac{\partial^2}{\partial z^2}$. |

\*Term Breakdown:

*   $\rho \frac{\partial \mathbf{v}}{\partial t}$: **Unsteady acceleration term** - Rate of change of momentum due to local acceleration.
*   $\rho (\mathbf{v} \cdot \nabla) \mathbf{v}$: **Convective acceleration term** - Rate of change of momentum due to fluid particle moving to a new location in the velocity field.
*   $-\nabla p$: **Pressure gradient force** - Force due to differences in pressure within the fluid.
*   $\mu \nabla^2 \mathbf{v}$: **Viscous force term** - Force due to the diffusion of momentum from shear stresses (friction within the fluid).
*   $\rho \mathbf{g}$: **Body force term** - External force acting on the entire fluid body (e.g., gravity, centrifugal force).

\*Simplifications:
- Steady flow:  no $\frac{\partial \mathbf{v}}{\partial t}$
- Incompressible flow: $\nabla\mathbf{v}=0$
- Fully developed laminar pipe flow: only axial velocity depends on radius.


### Drag Force Formula
general formula:
$$F_d = C_d \cdot \frac{1}{2} \rho_f v^2 \cdot A$$
Where:  
- $C_d$ is the drag coefficient (dimensionless, depend on Reynolds number)  
- $\rho_f$ is the fluid density  
- $v$ is the relative velocity between particle and fluid  
- $A$ is the cross-sectional area of the sphere  

---
==Stokes Drag Law==:
$$F_d = 6\pi \mu r v$$
Where:  
- $\mu$ is the dynamic viscosity of the fluid  

**Applicability**: Valid for low Reynolds number flow ($\mathrm{Re} \ll 1$, usually $Re<0.1$), where viscous forces dominate and inertial effects are negligible.

\*Reynolds Number Formula:
$$\mathrm{Re} = \frac{\rho_f v d}{\mu}$$
---

## Background Literature
| Coordinate System | Key Use              | Coordinates         | Volume Element $dV$                  |
| :---------------- | :------------------- | :------------------ | :----------------------------------- |
| Cartesian         | Box-like symmetry    | $(x, y, z)$         | $dx  dy  dz$                         |
| Cylindrical       | Cylindrical symmetry | $(r, \theta, z)$    | $r  dr  d\theta  dz$                 |
| Spherical         | Spherical symmetry   | $(r, \theta, \phi)$ | $r^2 \sin\theta  dr  d\theta  d\phi$ |


# 3. Physical Chemistry

## Mean Free Path
$$\lambda = \frac{1}{\sqrt{2}\pi d^2 n}$$
- The average distance a molecule travels before colliding with another molecule.  
- Depends on molecular diameter and number density.   


## Equipartition of Energy
- In thermal equilibrium, energy is equally distributed among all quadratic **degrees of freedom (DOF)**.  
- Each degree of freedom contributes $\tfrac{1}{2}k_B T$ of energy per molecule.  

Examples:  
- Translational (3 DOF): $\tfrac{3}{2}k_B T$
- Rotational: 2 or 3 DOF depending on molecule  
- Vibrational: 2 per mode (kinetic + potential)  


## Maxwell–Boltzmann Distribution
$$f(v) = 4\pi \left(\frac{m}{2\pi k_B T}\right)^{3/2} v^2 e^{-\frac{mv^2}{2k_BT}}$$
- Probability distribution of molecular speeds in an ideal gas at equilibrium.  
![[Pasted image 20250829112736.png]]
- The distribution curve depends on **Temperature (T)** and **Molecular Mass (m)** - Higher temperature makes the curve wider and flatter, with a greater fraction of molecules at high speeds. Heavier molecules have a narrower distribution, clustered around lower speeds.

## Ideal Gas Law
Molar form:  
$$
PV = nRT
$$

Molecular form:  
$$
PV = Nk_B T
$$
- **Assumptions of an Ideal Gas**: Molecules have zero volume; molecules exert no forces on each other except during instantaneous elastic collisions. 
- Conditions for Validity: **Low pressure** and **high temperature**. 
