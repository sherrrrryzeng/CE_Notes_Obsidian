---
date: 2026-01-06
Prof: Atsushi Urakawa
aliases:
  - Catalytic Reactions
---
## Generalised Form of Internal Diffusion
In practice just use: $$\eta_i=\frac{\tanh(\phi)}{\phi}$$
Generalised form: *(no need to remember)* ![[818b17435755d556931a05f577cb5d0355f74c0cf699f48a6c08cafbc3c9f819.png]]
For nth order reaction ($n>2$), reaction rate is related to the surface concentration $C_S$ in the power of $\frac{n+1}{2}$
The apparent reaction order CHANGES!


Consider different external mass transfer regimes:![[0707e1a7a033f19ffd9d404f1f5f36378e30ea2b9b30bb9eb5aaef5e5c110e1b.png]]

$$k_{obs}=\frac{1}{L}\left(\sqrt{\frac{2}{n+1}k_VD}\right)$$$$\frac{d\ln(k_{obs})}{dT}=\frac{1}{2}\left(\frac{d\ln{k_V}}{dT}+\frac{d\ln{D}}{dT}\right)$$ Assuming Arrhenius-type behaviour $k=Ae^{-E/RT}$ $$E_{obs}=\frac{1}{2}(E_\text{{surface reaction}}+E_{\text{diffusion}})$$ If pore diffusion limits reaction strongly ($E_\text{{surface reaction}}>>E_{\text{diffusion}}$) $$E_{obs}\approx \frac{1}{2}E_\text{{surface reaction}}$$

Falsified kinetics - Fischer Tropsch Synthesis: ![[d75ec441f7180cc5de1d1b94fd486e3e8b35634e134e6da92c2ad6529a91f639.png]]


# Mass Transfer Limitations
![[175259bf1c52e27ca22bbb8a053ba40b29531146adc231ee508b3cc5502a4a14.png]]

![[b5ffe7fd0b59e6a2f4f83e41d587986cf4068531ea2d08bdce1a389387fd0f07.png]]

![[5f292b7f93fff9c37613eb6e7937e2cdc4cd1e5d54852f55dbc96381100e0820.png]]
Flow rate increases
-> film thickness decreases
-> conversion increases

![[491021370bfea125653c8cdd81d60a43c7ebc3f2242f558231e2789f1d88c7a1.png]]


## Combined Internal & External Mass Transfer
![[6b4064c2bee70b6fbf21ed34aed61a16bfaeb48d33d4c58472360d8af422148c.png]]
![[4ed2190dce0d41ac840c78e9b925b4c9d3e304b610710082a277f1c2453ea588.png]]

### Biot number $Bi_m$
$$Bi_m=\frac{\text{rate of external mass transfer}}{\text{rate of internal diffusion}}=\frac{k_mL}{D_{eff}}=\frac{\phi^2}{Da_{II}}$$
Overall effectiveness factor: $$\eta=\frac{\tanh{\phi}}{\phi(1+\frac{\phi\tanh{\phi}}{Bi_m})}$$
Reference number: ![[be7d3afdbd3c5f8d19f40ca06f1532cc9cf86b4a95d955f2140a1a54969ba50a.png]]
*Usually in reality we have internal control*


### Prater number $\beta_i$
![[d0b26efec0ad20892959a86033c23b2e04ef82f54b23af2a603daf9d332b4c15.png]]
$$\beta_i=\frac{D_e(-\triangle H)C_S}{\lambda_eT_S}$$
Exothermal -> $\triangle H<0$ -> $\beta_i>0$
Endothermal -> $\triangle H>0$ -> $\beta_i<0$ -> $\eta_i<1$

![[516f4f3e0bead0f7e242c0342eb435994506bb5c366088ba9c34aae05df48777.png]]


Answers:
C
A
D
B (B stays inside)
A (film thickness)
D (A reacts and cannot reaches inside)
D
E ($(0.8)^3\sim 0.5$ the diameter of the empty volume is about 0.8, A only reaches 0.2)
skip A?
skip C
skip D
D (catalyst does not change enthalpy)
A
