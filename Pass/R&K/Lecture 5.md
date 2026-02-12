---
date: 2025-11-25
Prof: Jose Palomo Jimenez
aliases:
  - Energy Balance
---
# Energy Balance
## General expressions
![[195003cb68baadfb5198a63f5c4f4286ba8969ba401d752db53ae5d8a74db31a.png]]
$$\frac{dE}{dt}=E_{in}-E_{out}+E_{reaction}+\dot{Q}+\dot{W}$$
The unit is typically $[J/s=W]$

### Important parameters
- **Heat Capacity** $C_P\,\,[J/K]$ 
	Molar heat Capacity $c_P\,\,[J/(mol\cdot K)]$ 
	*$C_P\,\,\&\,\,c_P$ are both used. Mind the units!*$$\frac{dE}{dt}=nc_P\frac{dT}{dt}$$
	When molecules with different molar heat capacity values are present: $$\frac{dE}{dt}=\sum_in_ic_{p,i}\frac{dT}{dt}$$
- **Molar flow rate** $F_{in}\,\,[mol/s]$
	Flow in: $E_{in}=F_{in}C_PT_{in}\,\,[J/s]$
	Flow out: $E_{out}=F_{out}C_PT_{out}\,\,[J/s]$
	Difference: $$E_{in}-E_{out}=FC_P(T_{in}-T)$$
	
- **Reaction enthalpy** $\triangle H_R\,\,[J/mol]$
	reaction rate $r\,\,[mol/(m^3\cdot s)]$ 
	With reactor volume V: $$E_{reaction}=-\triangle H_R rV$$
- **Heat transfer coefficient** $U\,\,[J/(m^2\cdot s\cdot K)]$
	heating/cooling area $A\,\,[m^2]$
	Heat transfer rate is proportional to the temperature difference: $$\dot{Q}=UA(T_C-T)$$

-> Demystified energy balance equation: $$\sum_in_iC_{P,i}\frac{dT}{dt}=FC_P(T_{in}-T)-\triangle H_RrV+UA(T_C-T)$$*($\dot{W}$ in this course will be neglected)*


### Situations
- CSTR - steady state $$\frac{dE}{dt}=0$$
- Batch reactor $$E_{in}-E_{out}=0$$
- Adiabatic $$\dot{Q}=0$$

## PFR
From material balance $$\frac{dC_A}{d\tau}=v\frac{dC_A}{dV}=R_A$$ $$V=\int_0^VdV=v\int_{C_{A0}}^{C_A}\frac{1}{R_A}dC_A$$ or $$\tau=\int_{C_{A0}}^{C_A}\frac{1}{R_A}dC_A$$Using conversion $$\frac{dX_A}{dV}=-\frac{R_A}{vC_{A0}}$$ $$\frac{dX_A}{dl}=\frac{r}{vC_{A0}}\frac{\pi D^2}{4}$$
From Energy balance $$E_{in}-E_{out}=FC_P(T|_l-T|_{l+\triangle l})$$ $$E_{reaction}=-\triangle H_Rr\triangle V=-\triangle H_Rr\pi\left(\frac{D^2}{4}\right)\triangle l$$ $$\dot{Q}=U\triangle A(T_c-T)=U\pi D\triangle l(T_c-T)$$
Rearranging and taking $\triangle l\to 0$ :$$FC_P\frac{dT}{dl}=\pi D\left[-\triangle H_Rr\left(\frac{D}{4}\right)+U(T_c-T)\right]$$ $$FC_P\frac{dT}{dX_A}=vC_{A0}[-\triangle H_R+\frac{4U(T_c-T)}{Dr}]$$