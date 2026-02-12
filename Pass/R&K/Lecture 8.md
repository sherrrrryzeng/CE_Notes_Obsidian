---
date: 2025-12-09
Prof: Atsushi Urakawa
aliases:
  - Chemical Kinetics
---
# Elementary reaction

**Elementary reaction**: 
	A chemical reaction in which one or more chemical species (typically one or two) react directly to form products in a single reaction step and with a single transition state.
	*Example:* $$CH_3COCH_3\to \cdot CH_3+\cdot CH_3CO$$

**Elementary reaction kinetics**:
	direct use of stoichiometry coefficient![[7a55d0032c62a31861530620f279245e31cd9b1d861c6077cda1c135455c6647.png]]

**Reaction rate constant** $k$ :
	Analogy - climbing mountains ![[62bdbc7c2d10cc13a53ae0be29d5af952286810880681fcced79a78955eef5d8.png]]
	$E_a$ : **Activation Energy**


# Real reaction

**Potential Energy Diagram**:
	Each step is an elementary reaction ![[84c1f7cb6610283d5f105a144f24bffa2029c4570700601e67d5104a7d887ead.png]]


## Reaction Equilibrium Assumption
**Rate-determining(limiting) step**:
	slow step determines the total duration
	-> **==Reaction equilibrium assumption (REA)==**: 
	fast step $r=0$ ![[9f8aad4295f7cf57d4cb07b4ea360ee464e16961255a425168d918b79c0f6ccc.png]]
	With **conservation of mass** we can have one ODE to solve analytically ![[7cdd1152916b9175f7ac381229e96c5b2142582f7b8f2a50877165e6d2c681b0.png]]


## Quasi-Steady-State-Assumption
**Quasi-steady-state assumption (QSSA)**:
	Production rate of short-lived intermediate(s) (typically small amounts) does not change over time. ![[fbad27f570d13940d4b95a514e0f6274bc72619ed19d661558be130f9b24e5e7.png]]![[2079dc3badcfc7e8e493eca0e1b8d3724974f8fbc8c8b8b18f9b7e5a06fe53e7.png]]
	Reason to use QSSA: In practice, many reactions involve elementary steps for which rate constants are difficult to be determined directly 
	  *(e.g. impossibility to measure concentration such as radicals – no radicals at the reactor outlet…).*


### Analytical solution with QSSA
*Example: Batch reactor, no density change* ![[4c1fc0cc1f062123951b0c64a381fe849e6826d8de726e2002a5dfc312b85e4a.png]]
QSSA solution: $$\frac{dC_A}{dt}=-k_1C_A\,\,\,\to\,\,\,C_A=C_{A0}e^{-k_1t}$$$$\frac{dC_B}{dt}=k_1C_A-k_2C_B=0\,\,\,\to\,\,\,C_B=\frac{k_1}{k_2}C_A$$$$\frac{dC_C}{dt}=k_2C_B=k_1C_A\,\,\,\to\,\,\,C_C=C_{A0}(1-e^{-k_1t})$$ 
Numerical solution (Python) vs Analytical solution (QSSA): ![[cda977d223c2f11e2a90a9fc9588ffa615ae636517436ebe80ff2c98c5b5fb51.png]]



## REA vs QSSA
![[5f33c026809510ac780af54afdd6134f29203bb776149532651240c88600e54f.png]]