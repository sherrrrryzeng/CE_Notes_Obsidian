---
date: 2025-12-02
Prof: Jose Palomo Jimenez
aliases:
  - Non-ideal Reactors
---
# The Quality of Mixing

Non-ideal Reactor model
- Macromixing -> Residence Time Distribution (RTD)
	 It is not enough if we only know space-time calculated from RTD
- **Micromixing -> The Quality of Mixing** (Reactor Model)
	 describes how molecules of different ages encounter one another in the reactor. 

-> For reactions other than 1st order, knowledge of RTD alone is insufficient to predict reactor performance, degree of mixing must also be quantified.
-> In general, models that account for degree of mixing must be developed.


# Models for predicting conversion using RTD data
## Zero adjustable Parameters - two limits
![[3e58fa94ff1572271c3b6a24a1e772c71677e1bc200416aa64741dcee82ff9a9.png]]

### Total segregation model (lower limit)
![[020ead2c084f8ec0d3fdd617f83dc207771ee5ab304479c4c00f807eae1f1420.png]]

Consider each globule to be a batch reactor:
![[470183051b883cd2601492a52e625aa5455f875ce1aad9e9c7910c93cb67977b.png]]
$$X_{A,real}=\int_0^\infty X_A(t) E(t) dt$$

### Maximum mixedness (upper limit)
![[186aedaec7524659d46f35f407365bf998ff5781d0055f028dbf72ef361928d3.png]]



## One adjustable parameter
### Tank in series
![[d428a6b1dddcc70a9ef6b076793534ec3039c0803c99fc95222ef40361a9171f.png]]
Non-dimensional: 
![[993ab40174bf248d7470342a145891181eb868551053c1c8ba2148b504fa07db.png]]

For any arbitrary input: $$\triangle t_m^2=(t_{m,out}-t_{m,in})^2,\,\,\,\triangle\sigma^2=\sigma^2_{out}-\sigma^2_{in}$$
The number of tanks: $$n=\frac{\tau^2}{\sigma^2}\,\,\,\,\to\,\,\,\,\,n=\frac{\triangle t_m^2}{\triangle \sigma^2}$$

### Axial dispersion model
![[1d38b52fbe4e447fd74ce83905236780cbf5de5be95a200d99d3a40cd6d0b37e.png]]
Reasons:
- Velocity profile
- Turbulent mixing
- Molecular diffusion
- etc.

![[9bd2cb56bc6a999ebf42632b7bd3748d97fef30a3191e8d0c07a0c1407439810.png]]

Peclet number $$Pe=\frac{uL}{D_M}=\frac{\text{convection}}{\text{diffusion}}$$
Dispersion number $$D=\frac{D_M}{u L}$$
**Bodenstein number** $$Bo=Pe_{reactor}=\frac{uL}{\mathbf{D}_{ax}}=\frac{\text{convection}}{\text{dispersion}}$$

![[fde35650762117f6b2ecc011d0c62cb42bd695b869cd6da7c59cf2c408a276f8.png]]

![[35ccf4bdc8dfa7410410dbf4e0650429598148a95d9099967331f438514f537d.png]]

![[acea05f9cecaafddd17d01a5a02bce50c4523cd8453d66636e1996a8edfd3c90.png]]

![[1e87178c1b3eb1ede14af6d144891a67ac501292c6edf115e5ccb49066f07ba2.png]]

![[09f70d24236f83a32483f6955ab0856838e0be6cba178de2c3b3eca02d638235.png]]

![[5271fab873deac6b9e85a779b62c39525f7a9190626f7900283b67ba139dcddd.png]]

![[facbc3636016b2abaf8750bcca4c98e089506104892f704cb3fa454ab9842e2b.png]]

or from diagrams

