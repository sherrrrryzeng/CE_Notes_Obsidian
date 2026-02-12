---
date: 2025-11-21
Prof: Jose Palomo Jimenez
aliases:
  - Material Balance 2
---
# Ideal Reactors +
## Graphical analysis
(For isothermal ideal reactors)

![[2ea47dcfb2da02444b5b93289f5efae2ff98b0c99103c0d9696d051cfdde7823.png]]
![[7bee68144ebe8fd83cb12c677b9b3c578c7bce6c136ac32b7d48538f019a4741.png]]

- for CSTR: V = area of rectangle ($\frac{F_{A0}}{-R_A}\cdot X_A$)
- for PFR: V = area under the line

Thus, the volume difference of CSTR and PFR is related to reaction kinetics order. 


# Association of ideal reactors

## Single Reaction
### PFR in series
![[e41ed9810419ed0af549cd0b712b2df4c3b1cbae59f4214ab660aae311f083f6.png]]
-> N PFR in series with total volume $V$ = 1 PFR with volume $V$

### CSTR in series
![[40e7d53b14cb56e353430724cb7adf352571e714b03de15230cceee67dfe9e50.png]]
$$F_{A1}=F_{A0}(1-X_{A1}),\,\,F_{A2}=F_{A0}(1-X_{A2})$$ $$F_{A0}(1-X_{Ai})-F_{A0}(1-X_{Af})=-R_{Af}V_f$$ $$V_f=F_{A0}\frac{X_{Af}-X_{Ai}}{-R_{Af}}$$
![[cc29a7e9b774766660e4ff6e35f3750f1908adc7f236faf78ade3a88be8a143e.png]]

![[d77c5ae3732977c859e97d13bbcdf1a08ca051c23a92df4359ee8e9c27610503.png]]
-> A series of CSTR approaches a single PFR


## Optimum volume for 2 CSTR in series
![[ac446f1ee1ebd471efcf14818d7a14115024160323b0c48895706ba2d2891d07.png]]
![[ed485f9a4094bf2a486c6ceba7133447a26e6586b5dd0f87f3e4b0acde1f21e7.png]]

Exercise 1: $$\frac{dV_{total}}{dX_{A1}}=0$$

## Autocatalytic Reaction
![[0d237213310be875e8cd95d5ea7d0f6a80aaf439ad3508d751913067a2141744.png]]
$$R_A=-kC_{A0}(1-X_A)(C_{Q0}+C_{A0}X_A)$$
![[377602e71acf182cfb889a7d93984713e9c2e80a7613e617f8adee0a2e5c2bd3.png]]

![[72964ac4fd8e6b2210838be8b83e5ead9c4458a33565dd98fd048f49dcbec3c2.png]]
The total volume of CSTR(orange) and PFR(green)

![[83da75c57622233906afc77ada98f9b6b664acbcab518ec7dd87cb92db5862bc.png]]
-> Best configuration: CSTR first + PFR


# Variation in number of moles during reaction
![[00b2866d4bcc968b7a69640ac74a3200d999e006e71df06a8873f55f9cc3eedb.png]]
![[c0f964a1aa00fe63537621f3ed3dc8579708c5048c48a8025b5925ddfc554266.png]]

Consider the change in total flow, $v$ is changing: $$C_A=\frac{F_A}{v}$$ Basic relationships: $$C_T=\frac{F_T}{v}=\frac{P_T}{ZRT},\,\,C_{T0}=\frac{F_{T0}}{v_0}=\frac{P_{T0}}{Z_0RT_0}$$ Thus, $$v=v_0\left(\frac{F_T}{F_{T0}}\right)\left(\frac{P_{T0}}{P_{T}}\right)\left(\frac{T}{T_{0}}\right)$$ Isothermal operation: $$v=v_0\left(\frac{F_T}{F_{T0}}\right)$$ Finally we have: $$C_A=C_{T0}\left(\frac{F_A}{F_T}\right)=\left(\frac{F_{T0}}{v_0}\right)\left(\frac{F_A}{F_T}\right)$$ $$F_T=F_A+F_B+F_{inert}+...=\sum_{i=1}^nF_i$$

## Multiple reactions
### Parallel reactions
*A --r1--> D*, *A --r2--> W* or *A --r1--> D --r2--> W*

==**Important:**==

**Selectivity**: $\frac{\text{moles of the desired product}}{\text{moles of reactant converted or total moles of products}}$$$S_D=\frac{N_D}{N_{A0}-N_A}=\frac{N_D}{N_D+N_W}$$
**Yield**: $\frac{\text{moles of the desired product}}{\text{moles of reactant fed to the reactor}}$ $$Y_D=\frac{N_D}{N_{A0}}=X_AS_D$$
### Series reactions
![[c4a2e228af5d99189c5677912f5095eb37252f85e4f34392d4db5ede9a7e61dd.png]]

Find the optimum volume for D production
![[87328ec4f9918d94df445922461fe4e738cc164a73299d0c380a7ca4e96e7263.png]]
![[44328acc6c1b722c1f110d3a345bfb8b724fa235b8e1303215bd654c5b90c444.png]]


### Semi-batch reactor
Constant density
![[42bc3262d4d06a32854823ae59473ad68ac7602169ead5f7a27d6fb3db6455a6.png]]
![[54a266ad7c0e8624032b9e86347617e584a8230da5b551dc448c88f0961a7d66.png]]

