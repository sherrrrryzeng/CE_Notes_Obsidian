# Chemical Equilibrium

## Definition
Chemical equilibrium is the state in which both the reactants and products are present in concentrations which have **no further tendency** to change with time, so that there is no observable change in the properties of the system.
$$r_{\text{forward}}=r_{\text{backward}}$$


## Reaction equilibrium
**Extend of reaction** $\varepsilon$ $[mol]$ : the number of times a reaction event occurs![[61ceb82aa619b5af1fe2ce3fc84e0acce560e4c861baa850d484ac749c476da3.png]]

Reaction equilibrium: $$dG=-SdT+VdP+\sum_j\mu_j dn_j$$From **chemical potential** $\mu_j$ to **activity** $a_j$  $$\mu_j=G_j^\circ+RT\ln{a_j}$$then to **fugacity** $f_j$ $$a_j=\frac{f_j}{f_j^\circ}=\frac{P_j}{1\,atm}=y_jP$$*$f_j^\circ$ : The fugacity of component j in the standard state 
   (1 atm and the system temperature)*
$$
K=\Pi_ja_j^{v_j}=\frac{P_P}{P_IP_B}=\frac{y_P}{y_Iy_BP}$$
![[48a35e2c9f643d72d3990bf60241f0904c538727acfff8970f764429fa60cd19.png]]


## Temperature dependence
Definition of **equation constant**$$K=\exp({\frac{-\triangle G^\circ}{RT}})$$-> K is a function of T but not P or composition
-> Only **temperature** matters

van't Hoff equation: $$\frac{\partial\ln K}{\partial T}=\frac{\triangle H^\circ}{RT^2}$$When the standard heat capacity change of reaction is negligible
-> $\triangle H^\circ$ is constant -> $$\ln(\frac{K_2}{K_1})=-\frac{\triangle H^\circ}{R}(\frac{1}{T_2}-\frac{1}{T_1})$$


# Material Balance - Ideal Reactors
Mole balance: $$\frac{\partial N_i}{\partial t}=F_{i,in}-F_{i,out}+\int_Vv_ir\,dV$$
## Single reactor
### Batch reactor
Constant V : $$\frac{dN_A}{dt}=0-0+\int_0^VR_AdV=R_AV$$$N_A=VC_A$ : $$\frac{dC_A}{dt}=R_A$$
with $X_A$: $$X_A=\frac{N_{A0}-N_A}{N_{A0}}=\frac{C_{A0}-C_A}{C_{A0}}$$ $$-\frac{N_{A0}dX_A}{dt}=R_AV\,\,\,\,\,\,-\frac{C_{A0}dX_A}{dt}=R_A$$


### CSTR
$$\frac{\partial N_A}{\partial t}=F_{A,0}-F_{A}+R_AV$$with $X_A$ : $$X_A=\frac{F_{A0}-F_A}{F_{A0}}$$Steady state: $$F_{A0}-F_A=F_{A0}X_A=-R_AV$$
$F_A=v\,C_A$ :$$v_0C_{A0}-vC_A=-R_AV$$$v=v_0$ *(input=output)*: $$C_{A0}-C_A=C_{A0}X_A=-R_A\frac{V}{v_0}$$Define **==space time==** : 
	*time required to process one reactor volume of speed* $$\tau=\frac{V}{v_0}\,\,\,[\text{time}]$$
	**==Space velocity==** : $$s=\frac{1}{\tau}\,\,\,\,[\text{time}^{-1}]$$
	with $\tau$ : $$\frac{C_{A0}-C_A}{\tau}=\frac{C_{A0}X_A}{\tau}=-R_A$$



### PFR
Shell balance : $$\frac{dN_A}{dt}=F_{A|l}-F_{A|l+\triangle l}+R_AA\triangle l$$
Steady state : $$\frac{F_{A|l+\triangle l}-F_{A|l}}{A\triangle l}=R_A$$$\triangle l\to 0$: $$\frac{dF_A}{A\,dl}=\frac{dF_A}{dV}=R_A$$$F_A=v\,C_A$ , $\tau=\frac{V}{v_0}$ :$$\frac{dC_A}{d\tau}=R_A$$with $X_A$ :$$-\frac{F_{A0}X_A}{dV}=R_A\,\,\,\,\,\,-\frac{C_{A0}X_A}{d\tau}=R_A$$


## Volume Comparison
### Single CSTR vs PFR
![[2ea47dcfb2da02444b5b93289f5efae2ff98b0c99103c0d9696d051cfdde7823.png]]
![[7bee68144ebe8fd83cb12c677b9b3c578c7bce6c136ac32b7d48538f019a4741.png]]

- CSTR: V = area of rectangle ($\frac{F_{A0}}{-R_A}\cdot X_A$)
- PFR: V = area under the line
*\*  both related to reaction kinetics order*


### Reactors in series
- PFR in series: 
	N PFR in series with total volume $V$ = 1 PFR with volume $V$

- CSTR in seires:![[c7eccb591a10c5ed987331acdd41f43368ace4c0071b2ae1e8b2fd3fe55dce77.png]] ![[639ec0fae696d04342bd97dce0218d98093975e9df1465e9abcfccc1d7e5007d.png]]



### Autocatalytic reactions
![[88a6c507a22453ffb609634efbe6cb1a7b5e116c5646e7aaeacdefec2b2da4d7.png]]![[ec1eefefcb6d335ccfe62997903a28ab82ebb0d1b1477d90f7a00c139d39bc0e.png]]


# Material Balance - Complex situations
## Variation in number of moles during reaction
When the system density changes or there is a variation in the number of moles -> Flow would change! $$v=v_0(\frac{F_T}{F_{T0}})(\frac{P_{T0}}{P_{T}})(\frac{T}{T0})$$
- $(\frac{P_{T0}}{P_{T}})=1$ if total pressure of the system is constant.
- $(\frac{T}{T0})=1$ if the operation is isothermal. 



## Parallel & Series reactions
![[6cf6e8c5418274d38d25d8b2f1b3d605b9beb7700224705125219caf404ef428.png]]

Define:
- **==Selectivity==** $$S=\frac{\text{moles of the desired product}}{\text{moles of converted reactant}}=\frac{N_D}{N_{A0}-N_A}$$$$S=\frac{\text{moles of the desired product}}{\text{moles of total products}}=\frac{N_D}{N_D+N_W}$$
- **==Yield==**$$Y=\frac{\text{moles of the desired product}}{\text{moles of total reactant fed to the reactor}}=\frac{N_D}{N_{A0}}$$   Relationship with selectivity: $$Y_D=X_AS_D$$

## Semi-batch reactor (isothermal)
In batch reactor add B into A while reacting
-> keep $C_B$ relatively low to avoid undesired reactions
-> increase selectivity towards desired product

Volume changes -> 
 Need to calculate using moles $N$ instead of concentrations $C$

For A: $$\frac{dN_A}{dt}=\frac{d(VC_A)}{dt}=V\frac{dC_A}{dt}+C_A\frac{dV}{dt}=R_AV$$For B: $$\frac{dN_B}{dt}=\frac{d(VC_B)}{dt}=V\frac{dC_B}{dt}+C_B\frac{dV}{dt}=v_0C_{B0}+R_BV$$Global mass balance: $$\frac{dm}{dt}=\frac{d(\rho V)}{dt}=v_0\rho_0$$If density is constant: $$\frac{dV}{dt}=v_0$$

# Energy Balance
$$\frac{dE}{dt}=E_{in}-E_{out}+E_{reaction}+\dot{Q}+\dot{W}$$

## Equation Analysis
### Accumulation term $\frac{dE}{dt}$ 
$$\frac{dE}{dt}=\sum_in_iC_{P,i}\frac{dT}{dt}=nC_P\frac{dT}{dt}\,\,\,[J/s]$$
\* Reminder: 
	$C_P$ could be molar heat capacity or specific heat capacity. Check the unit! 

**Steady state =0**


### Flow terms $E_{in}\,\&\,E_{out}$ 
$$E=FC_PT$$
$$E_{in}-E_{out}=F_{in}C_PT_{in}-F_{out}C_PT=FC_P(T_{in}-T)\,\,[J/s]$$

### Reaction term $E_{reaction}$
$$E_{reaction}=-\triangle H_RrV\,\,[J/s]$$
- $\triangle H_R\,\,[J/mol]$: reaction enthalpy (-)
- $r\,\,[mol/(m^3s)]$: reaction rate


### External heat term $\dot{Q}$
$$\dot{Q}=UA(T_c-T)$$
- $U\,\,[J/(m^2sK)]$: heat transfer coefficient
- $A\,\,[m^2]$: heating/cooling area

**Adiabatic = 0**


## Energy balance in PFR
Material shell balance: $$\frac{dN_A}{dt}=A\triangle l\frac{dC_A}{dt}=vC_A|_l-vC_A|_{l+\triangle l}+R_AA\triangle l$$Steady state, $\triangle l\to 0$ : $$\frac{v\,dC_A}{A\,dl}=\frac{v\,dC_A}{dV}=R_A$$$$V=v\int_{C_{A0}}^{C_A}\frac{dC_A}{R_A}\,\,\,\,\,or\,\,\,\,\,\tau=\int\frac{dC_A}{R_A}$$
Energy balance, steady state: $E_{in}-E_{out}+E_{reaction}+\dot{Q}=0$ where $$E_{in}-E_{out}=FC_P(T|_l-T|_{l+\triangle l})$$$$E_{reaction}=-\triangle H_RrV=-\triangle H_Rr\cdot\pi(\frac{D^2}{4})\triangle l$$$$\dot{Q}=U\triangle A(T_c-T)=U\cdot\pi D\triangle l\cdot(T_c-T)$$$\triangle l\to 0$: $$FC_P\frac{dT}{dl}=[-\triangle H_Rr\frac{D}{4}+U(T_c-T)]\pi D$$
As in PFR  $-F_{A0}\frac{dX_A}{dV}=R_A$  and  $dV=\pi(\frac{D^2}{4})dl$ :$$FC_P\frac{dT}{dX_A}=F_{A0}[-\triangle H_R+\frac{4U(T_c-T)}{Dr}]$$


# Non-ideal Reactors - RTD
## Residence Time Distribution
![[7d1b1367a851e7ac9ab0194d16cd48543756a7dbbe7595e7ac5b4f9c41039c7e.png]]

**Pulse input** -> $C(t)$: experimental determination
- -> $E(t)$: **residence time distribution function (RTD)** $$E(t)=\frac{C_A(t)}{\int_0^\infty C_Adt}$$ $E(t)dt$: fraction of fluid that have left the reactor and have spent at time inside between t and dt. $$\int_0^\infty E\,dt=1$$
**Step input** -> $C(t)$: experimental determination
- -> $F(t)$: **cumulative distribution function** $$F=\int_0^t Edt\,\,\,\,\,\,\,\,E=\frac{dF}{dt}$$ F(t) is the fraction of effluent that has been in reactor for less than time t.

![[c0f9a39a3aff3c5c5a3d187b878f08507b93b77d8ffc2ab9dccf82557ddb1a8a.png]]


## Mean and Variance
Measure concentrations vs. time:
- **MRT - Mean Residence Time**: $$t_m=\frac{\int_0^\infty tE(t)dt}{\int_0^\infty E(t)dt}=\int_0^\infty tE(t)dt$$
- **Variance of the residence time**: $$\sigma^2=\int_0^\infty(t-t_m)^2E(t)dt$$

## Dimensionless RTD
Use **residence time** $$\tau=\frac{V}{v}$$ to make RTD dimensionless: $$\theta=\frac{t}{\tau}$$Dimensionless RTD: $$E(\theta)=\tau E(t)$$($\int E(\theta)d\theta=\int E(t)dt=1$)



- Ideal CSTR (pulse injection): $$t_m=\tau\,\,\,\,\,\,\,\,\,\,\,\,\theta=1$$$$\sigma^2=\tau^2\,\,\,\,\,\,\,\,\,\,\,\,\sigma_{\theta}^2=1$$
- Ideal PFR (pulse injection):$$t_m=\tau\,\,\,\,\,\,\,\,\,\,\,\,\sigma^2=0$$
- Any reaction system: $$\theta_m=\int \theta E(\theta)d\theta =\frac{t_m}{\tau}$$$$\sigma^2_\theta=\int(\theta-\theta_m)^2E(\theta)d\theta=\frac{\sigma^2}{\tau^2}$$


## RTD Analysis
### Non-ideal CSTR
![[98c408e2fe1a4888df9bee9e186a59d5c4062caedb042c6244fdff8700cb1ca8.png]]
- **Stagnant zone** 
	$$V_{mixing}<V_{design}$$$$\tau_{RTD}<\tau_{ideal}$$
- **Short circuiting**
	$$v_{reaction}<v_{feed}$$$$\tau_{RTD}>\tau_{ideal}$$

### Non-ideal PFR

- **Channeling**
	 Two peaks
	
- **Dead zone**
	 Similar to stagnant zone $\tau_{RTD}<\tau_{ideal}$ 
	 **Early peak with ==long tail==**



# Non-ideal Reactors - Quality of Mixing

## Zero adjustable parameters
To predict the upper and lower limits of $X_A$ 
### Segregation model (Minimum)
![[7bc2f2c6618ba7773d13b5d2e9bce3a5bb912611639e087eb6739e63019ae83c.png]]
Consider each globule to be a batch reactor.
From RTD analyses we can have a distribution of the time these globule spend in the reactor. $$X_{A,real}=\int X_A(t)E(t)dt$$
### Maximum mixedness
Molecules are free to move everywhere in the reactor. 
![[122e23614770f5a62a5f9acb2f42d2e5c61f9f013ed78f4466e5a7e911e35aca.png]]


RTD tells us about residence times, but does not provide information on mixing.
For **1st order** reactions, the results from Segregtion model and Maximum mixedness model are the same -> accurate $X_A$.
For reactions other than 1st order, knowledge of RTD alone is insufficient to predict reactor performance, **degree of mixing** must also be quantified.


## One adjustable parameter model
Models account for degree of mixing

### Tank in series
![[75cfb855f36cededeb7d34755c2027eabf15355631ab405319d64b6b5345f2ec.png]]
$$n=\frac{t_m^2}{\sigma^2}$$
![[0e7fe11dc9ea6a6c8baa8727c65a48cbc47a5a734dda6a935bad7d18e2550f93.png]]
$$n=\frac{\triangle t_m^2}{\triangle\sigma^2}$$

To calculate $X_A$: $$X_A=1-\frac{1}{(1-k\tau_n)^n}\,\,\,\,\,\,\tau_n=\frac{V_{total}}{n\,v}$$


### Axial Dispersion model
![[2a47f2df5793abe2d0e7c4eba05d42ecd909aba8ab09578deb6b9bfb038a1ef4.png]]
Consider all intermixing (diffusion) of fluids along axial direction. $$\frac{\partial C}{\partial t}=D_{ax}\frac{\partial^2C}{\partial z^2}$$Notation alert: 
- Peclet number: $$Pe=\frac{\text{convection}}{\text{diffusion}}=\frac{uL}{D_M}$$
- **Bodenstein number**: $$Bo=Pe_{reactor}=\frac{\text{convection}}{\text{dispersion}}=\frac{uL}{D_{ax}}$$

Axial dispersion model is suitable for long tubes with laminar flow and packed beds. 
In PFR: $$\frac{\partial C_A}{\partial t}=D_{ax}\frac{\partial^2C_A}{\partial z^2}-u\frac{\partial C_A}{\partial z}$$
![[48241fd0f0044881357dfa465d6a649163bd9b177d7a1ec5bff29fad6d4e07f8.png]]


**Small extent of dispersion** 
-> closed-closed vessel = open-open vessel
**==Dispersion number==**: 
$$\frac{1}{Pe_{reactor}}=\frac{D_{ax}}{uL}<0.01$$
![[dc85fc2a53a0ed79e31d25e6dd4e2f004c329cfd9ee276191589d3657442b520.png]]
$$t_m=\tau\,\,\,\,\,\,\,\,\,\,\frac{\sigma^2}{t_m^2}=2(\frac{1}{Pe_{reactor}})$$


**Large extent of dispersion** 
-> closed-closed vessel != open-open vessel
$$\frac{1}{Pe_{reactor}}=\frac{D_{ax}}{uL}>0.01$$
![[00647b79bc4042b7a55e2013c8a9448fdad81db1b6a41eb3cdede0c09e30f02b.png]]


