---
date: 2025-10-07
Prof: Zoë J.G. Gromotka
aliases:
  - Tuning PID Controllers
  - Controller Design
---
# Tuning

Desired Response:
![[d7d5f10713e6f127252f28f42ad56d72fba4f2b75cb107723aef7d6dab5b2502.png]]

Goal: shape the response of the system

- Increase any of the parameters of a PID controller: $$C(s)=K\left(1+K_ds+\frac{1}{T_is}\right)$$
![[8c932a613f2a1d4e9138b4a92b12e650141173ed4ab298851814db419c95c2c8.png]]


## Response-based tuning
### Ziegler-Nichols Method

Closed-loop experiment:![[8ff84556b49072aadbc685e58fcb0011757f1e2921427b934c33a8d02f2aecf6.png]]
With different $K_p$
![[b69b670a22b72ea13555d4e489cd367233fd2d7237e568ade67e7023791ad756.png]]
When the system has just right, sustained oscillations(here $K_p=1.67$), 
record $K_u=K_p$ and the period of oscillations, $P_u=T$
Then we can use the table to find $K, T_i,K_d$ (see below)

Properties:
1. very simple
2. **time-consuming**
3. potentially pushing to **instability**
4. Potentially **too aggressive** (parameter modification see below)

![[151c1f44349d267ce68c0ce26b34030edc3954b85edbe6e0c57202afff2dcad3.png]]
![[a7b790aa47baac1c823fb028999d0a4c056abcaa8ab0c4ffef48fbd138572cff.png]]


### Cohen-Coon Method

Open-loop experiment:![[168a432d3ec853d4387b0a6ac6717a6e6a9f5fc26a83b0d283396229157630b7.png]]
No controller in the system, just know how the system reacts
![[cbcecf95cc0aa49a948bf37eaa25a22fc78d9a1c5b23e7d546d02d41dc41138d.png]]
Find a inflection point(where the slope changes), and plot a tangent line. 
When the tangent crosses 0, the time is $\alpha$;
When the tangent crosses $y(\infty)$, the time is $\tau+\alpha$. 
The approximating transfer function:$$G_{app}(s)=\frac{k\,exp(-\alpha s)}{\tau s+1}$$
![[cd5da4fd905dc393775f26914e89a80a21204c725f9b1ee5b6f51aef5b0f9a69.png]]

![[c10da1942aa3d20253423db69b171b5de85e0b26b05d0c09f513fc817aabd8ea.png]]

Properties:
1. **few experiments** required
2. based on **approximation**
3.  **no push for instability** *(as long as the system is stable)*
4. potentially **too aggressive** 
	*no parameter modification, but can be adjusted such as by changing the integration time*
	-Recommendation: use the rule and then make less aggressive manually



- Summary of tuning PID controllers:
	-Parameters are tabularized
	-Performance may require adjustments

- The most common controllers in industry:
	-Simple to design and implement
	-With few parameters to tune - the parameters are directly related to the response
	-Often "sufficiently good" and more complex approaches would not be better
	-Easily extendable



# Controller design

Processes, transfer function, signals
![[737af07847a798a5b9f2574e1e0bef45ad0a15af9935b4f22bedfa8f5caec5bd.png]]

$K_a, K_s$ are just constants that scale the input


## Typical responses
![[e97f3dca3a418bff31d6149254ba2bea506ed1dcabdf899591da71f6bf3fb356.png]]
 $\dot{y}(t)=\frac{dy(t)}{dt}=Ku(t)$
![[35e0221c97a4879dc43e8a391e0f08a7b73788848d74307a459685e32fc4e8a7.png]]
First order - most commonly used
![[a114aeca6fb8bd6ac83d7adabf2edc2ed99787212688115c41a34863d1ae9020.png]]

![[0d15abcc7bc694ea6d96d1622d088a676621672dbdc5c2a6884c73a150db48fe.png]]


## Model based tuning
### Direct Synthesis

For a closed-loop system the transfer function is as desired:$$C_{CL}(s)=\frac{C(s)G(s)}{1+C(s)G(s)}=G_{CL}^{Desired}(s)$$
Solving for C(s):$$C(s)=\frac{1}{G(s)}\frac{G_{CL}^{Desired}(s)}{1-G_{CL}^{Desired}(s)}$$

A common choice - first order system:$$G_{CL}^{Desired}(s)=\frac{1}{\tau_cs+1}$$
Then the controller becomes:$$C(s)=\frac{1}{\tau_cs}\frac{1}{G(s)}$$
The desired closed-loop transfer function $G_{CL}^{Desired}(s)$ must be realistic:
- Systems with delay: $$G(s)=\frac{k\,exp(-\alpha s)}{\tau s+1},G_{CL}^{Desired}(s)=\frac{exp(-\beta s)}{(\tau_{c1}s+1)(\tau_{c2}s+1)}$$
- Systems with inverse response:$$G(s)=\frac{k(1-\eta s)}{(\tau_1s+1)(\tau_2s+1)},G_{CL}^{Desired}(s)=\frac{(1-\eta_c s)}{(\tau_{c1}s+1)(\tau_{c2}s+1)}$$
Inverse response system with transfer function:![[a2fd6e44ac1366527aa344d33a2ffffa0690ada8a6dd418efe901306786edf0b.png]]$$G(s)=\frac{K(-bTs+1)}{(Ts+1)(aTs+1)}$$


> [!Example]
>$$\frac{dc_A}{dt}=\frac{F_r}{V}(c_{A0}-c_A)-k_1c_A-k_3c_A^2$$
>$$\frac{dc_B}{dt}=-\frac{F_r}{V}c_B+k_1c_A-k_2c_B$$
> $F_r$: manipulated variable
> $c_B$: controlled variable
> others: disturbance variables
> 
> Boundary conditions:
> (a) Maximum values:
> 	$c_{B}^{max}=1.5714$.  ->100\% \[mol/L]
> 	$c_B$   -> y\%
> 	Therefore$$c_B=\frac{y}{100}c_{B}^{max}$$
> 	$$y=\frac{100}{1.5714}*c_B\,\,->\,\,Y(s)=CX(s)$$
> 	$F_r^{max}=634.1719$.     ->100% \[L/min]
> 	$F_r$ -> u%
> 	Therefore$$F_r=\frac{u}{100}F_r^{max}$$
> 	Substitute $F_r$ in the equations above:
> 	$$\frac{dc_A}{dt}=\frac{uF_{r,max}}{100V}(c_{A0}-c_A)-k_1c_A-k_3c_A^2$$
> 	$$\frac{dc_B}{dt}=-\frac{uF_{r,max}}{100V}c_B+k_1c_A-k_2c_B$$
> 	
> (b) Steady state values:
> 	$\vec{c_A}=c_A-c_{A,ss}->c_A=\vec{c_A}+c_{A,ss}$
> 	$\vec{c_B}=c_B-c_{B,ss}->c_B=\vec{c_B}+c_{B,ss}$
> 	$\vec{c_{A0}}=c_{A0}-c_{A0,ss}->c_{A0}=\vec{c_{A0}}+c_{A0,ss}$
> 	$\vec{u}=u-u_{ss}->u=\vec{u}+u_{ss}$
> 	Substitute $c_A,c_B,c_{A0},u$ in the equations above:
> 	$$\frac{d\tilde{c_A}}{dt}=\frac{\tilde{F_r}+F_{r,ss}}{V}[(\tilde{c}_{A0}+c_{A0,ss})-(\tilde{c_A}+c_{A,ss})]-k_1(\tilde{c_A}+c_{A,ss})-k_3(\tilde{c_A}+c_{A,ss})^2$$
> 	$$\frac{d\tilde{c_B}}{dt}=-\frac{\tilde{F_r}+F_{r,ss}}{V}(\tilde{c_B}+c_{B,ss})+k_1(\tilde{c_A}+c_{A,ss})-k_2(\tilde{c_B}+c_{B,ss})$$

Summary:
$$\begin{bmatrix}\tilde{c}_A \\[6pt] \tilde{c}_B \end{bmatrix}=A \begin{bmatrix}\tilde{c}_A \\[6pt] \tilde{c}_B \end{bmatrix}+B\,\,\tilde{u}+E \,\tilde{d}$$
$$
A \;=\;
\left.\frac{\partial (f_1,f_2)}{\partial (c_A,c_B)}\right|_{ss}
=
\begin{bmatrix}
\displaystyle \frac{\partial f_1}{\partial c_A}\bigg|_{ss} & \displaystyle \frac{\partial f_1}{\partial c_B}\bigg|_{ss} \\[12pt]
\displaystyle \frac{\partial f_2}{\partial c_A}\bigg|_{ss} & \displaystyle \frac{\partial f_2}{\partial c_B}\bigg|_{ss}
\end{bmatrix}$$
$$
=\begin{bmatrix}
-\dfrac{F_{r,ss}}{V} - k_1 - 2k_3 c_{A,ss} & 0 \\[10pt]
k_1 & -\dfrac{F_{r,ss}}{V} - k_2
\end{bmatrix}
$$

$$
B\;=\;
\left.\frac{\partial (f_1,f_2)}{\partial u}\right|_{ss}
=
\left.\frac{\partial (f_1,f_2)}{\partial F_r}\right|_{ss}\cdot\frac{F_r^{\max}}{100}$$
$$=\frac{F_r^{\max}}{100}
\begin{bmatrix}
\displaystyle \frac{\partial f_1}{\partial F_r}\bigg|_{ss} \\[12pt]
\displaystyle \frac{\partial f_2}{\partial F_r}\bigg|_{ss}
\end{bmatrix}=\frac{F_r^{\max}}{100}
\begin{bmatrix}
\dfrac{c_{A0,ss}-c_{A,ss}}{V} \\[10pt]
-\dfrac{c_{B,ss}}{V}
\end{bmatrix}.
$$

$$
\tilde{y}
=
C
\begin{bmatrix}
\tilde{c}_A \\[6pt]
\tilde{c}_B
\end{bmatrix},
\qquad
C =
\begin{bmatrix}
0 & \dfrac{100}{c_B^{\max}}
\end{bmatrix}.
$$


### Internal Model Control
We have:$$Y(s)=G(s)U(s)+D(s)$$
We want:$$Y(s)=R(s)$$
If we know D(s), then we can set:$$U(s)=\frac{1}{G(s)}(R(s)-D(s))$$
In reality:
- we only have an approximation $\tilde{G}(s)$
- the disturbance $D(s)$ is not measured

We can estimate the disturbance using $\tilde{G}(s)$ and the response of the system Y(s):$$\tilde{D}(s)=Y(s)-\tilde{G}(s)U(s)$$
As we know $\tilde{D}(s)$, we can now get: $$U(s)=C(s)(R(s)-\tilde{D}(s))$$
where $C(s)=\frac{1}{\tilde{G}(s)}$
![[ad9989c308487fb34863997d2755a9a984aeb17e29febda4b49403aac4940283.png]]
![[de0d51958ed5c6575faa75a941bca1267f2da6dbbb8e95a9a26df7340aa00656.png]]
Now we have: $$Y(s)=\frac{C(s)G(s)}{1-C(s)\tilde{G}(s)+C(s)G(s)}R(s)+\frac{1-C(s)\tilde{G}(s)}{1-C(s)\tilde{G}(s)+C(s)G(s)}D(s)$$
If $\tilde{G}(s)=G(s)$ and $C(s)=\frac{1}{G(s)}$, we get perfect control and $Y(s)=R(s)$. However,
- $\tilde{G}(s)=G(s)$ is impossible
- Forcing $C(s)=\frac{1}{G(s)}$ may be impossible
- Setting $C(s)=\frac{1}{\tilde{G}(s)}$ may lead to very large control action


Practical design of IMC controllers:

1. Separate the process model into two parts:$$\tilde{G}(s)=\tilde{G}_+(s)\tilde{G}_-(s)$$
where $\tilde{G}_+(s)$ contains all elements that are impossible to invert: time delays, positive zeros and has steady-state gain. Meanwhile $\tilde{G}_-(s)$ contains everything else. 


2. Choose the controller using $\tilde{G}_-(s)$ as $$C(s)=\frac{1}{\tilde{G}_-(s)}\cdot f(s)$$
where f(s) is a filter, typically:$$f(s)=\frac{1}{(\lambda s+1)^n}$$
with parameters $\lambda$ and $n$ chosen to ensure that C(s) is proper
	*small $\lambda$ - react faster*
	*large $\lambda$ - react slower (more conservative)*
For systems with pure integrators: $$f(s)=\frac{(2\lambda s-g)s+1}{(\lambda s+1)^2}$$
where $g=\frac{dG_+(s)}{ds}$ at s=0


>[!Example]
$$G(s)=\frac{0.3(-0.4s+1)}{(0.6s+1)(0.3s+1)}$$
steady-state gain:$$lim_{s\to0}\tilde{G}_+(s)=1$$
positive zero: $(-0.4s+1)=0$
therefore: $$\tilde{G}_+(s)=-0.4s+1$$$$\tilde{G}_-(s)=\frac{0.3}{(0.6s+1)(0.3s+1)}$$
Now:$$C(s)=\frac{1}{\tilde{G}_-(s)}\cdot f(s)=\frac{(0.6s+1)(0.3s+1)}{0.3}\cdot \frac{1}{(\lambda s+1)^n}$$
>1. How to choose n?: 
proper --- n=3 
but in principle n=2 could work
in exercise we use n=1
>2.  How to choose $\lambda$?:
start with $\lambda=1$, then see how it goes
If not works, increase the value
So now:$$C^{new}(s)=\frac{C(s)}{1-C(s)\tilde{G}(s)}$$
It will be a PID controller: $C(s)=K\left(1+K_ds+\frac{1}{T_is}\right)$


### Pole placement 
---We can choose the parameters of the controllers so that the closed loop has the desired poles. 

If the transfer function is: $$G(s)=\frac{K}{\tau s+1}$$
Choose to use PD controller:$$C(s)=K_p(1+K_ds)$$
Closed-loop transfer function:$$C_{CL}(s)=\frac{KK_p(1+K_ds)}{(KK_pK_d+\tau)s+1+K_p}$$
Desired pole $p_1=-1$, so we need:$$-\frac{1+K_p}{K_pK_d+\tau}=-1$$
Properties:
- Works for simple systems
- Requires some intuition for the choice of the poles – stability is a minimum



Recap - feedback control
![[495f37638bd415ae2aff3ca60c00eddab43ea61120ea2de3dbb98a60e17d28b7.png]]

### Feedforward control
![[b5b771e638bfcd1c77baec6c23d60cba94e38167ac203ca5c4fcf89bd9185584.png]]
We have:$$Y(s)=G(s)U(s)+G_d(s)D(s)$$
We would like to find U(s) so that Y(s)=R(s), thus$$U(s)=\frac{1}{G(s)}R(s)-\frac{G_d(s)}{G(s)}D(s)$$
Introduce: 
- Disturbance rejection: $$C_{ff}(s)=-\frac{G_d(s)}{G(s)}$$
- Setpoint tracking:$$C_{st}(s)=\frac{1}{G(s)}$$
In reality $G^{real}\neq G(s)$ and $G^{real}\neq G_d(s)$:
- Potential offset in steady state
- Mitigation of the disturbance

Feedback and feedforward control complement each other:
- Feedback for setpoint tracking and stabilization
- Feedforward for disturbance rejection

Now:$$Y(s)=\frac{G(s)C(s)}{1+G(s)C(s)}R(s)+\frac{G_d(s)+C_{ff}(s)G(s)}{1+G(s)C(s)}D(s)$$
Properties: 
- Stability and tracking decided by the denominator $1+G(s)C(s)$, independent of feedforward
- If $G_d(s)+C_{ff}(s)G(s)=0$, the effect of disturbances is eliminated 

For a heat exchanger:![[9909a98f8284a1746b60a82f39a21fcbdc2c07b17aadaee4415812883bd26f93.png]]


Four usual options:
- static - $C_{ff}(s)=K_{ff}$
- static with delay -  $C_{ff}(s)=K_{ff}\cdot exp(-sL_{ff})$
- lead-lag -  $C_{ff}(s)=K_{ff}\cdot \frac{1+sT_1}{1+sT_2}$
- lead-lag with delay - $C_{ff}(s)=K_{ff}\cdot \frac{1+sT_1}{1+sT_2}exp(-sL_{ff})$

But in dynamic effect part there might be a derivative ($-32s+\frac{8.8s+1}{10s+1}$), then lead-lag with delay is not practical --- choose static with delay
