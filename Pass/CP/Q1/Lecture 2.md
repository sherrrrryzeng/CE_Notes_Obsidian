---
date: 2025-09-10
Prof: Ferdinand Grozema
aliases:
  - Calculus & Nonlinear equations
---
# Calculus
## Function types
- Univariate functions: $f(x)$
- Multivariate functions: $f(x_1,x_2,...)=x_1+x_2^3...$
multi-dimensional domain $D\in R^n$ scalar output
- Vector-valued functions: $f(x_1,x_2,x_3)=y_1,y_2,y_3$
Scalar or multi-dimensional domain $D\in R^n$, but multi-dimensional output $R^m$

## Derivative Univariate functions
- Derivative of a univariate function $f:R$ -> $R$
-f(x) is ==differentiable== at position $a$ 
$$L=\lim_{h\to0}\frac{f(a+h)-f(a)}{h}$$
```
def f(x):return x**2+x
h=0.01
cal_derivative=(f(x+h)-f(x))/(h)
```

### Taylor series
- The **infinite** series: $$T_f(x;a):=lim\sum_{n=0}^{N}\frac{f^{(n)}(a)}{n!}(x-a)^n$$$$=f(a)+f'(a)(x-a)+\frac{f''(a)}{2!}(x-a)^2+\frac{f'''(a)}{3!}(x-a)^3+…$$
**BUT**: It is impossible to compute an infinite series

- Taylor approximation: The **k-th** order Taylor polynomial
$$P_k(x)=lim\sum_{n=0}^{k}\frac{f^{(n)}(a)}{n!}(x-a)^n$$
$$=f(a)+f'(a)(x-a)+\frac{f''(a)}{2!}(x-a)^2+...+\frac{f^k(a)}{k!}(x-a)$$
> [!Example] Taylor approx
> Approximation of $e^x$ at position 0:
> $e^x=1+x+\frac{1}{2}x^2+\frac{1}{6}x^3...$


## Directional Derivative Multivariate Functions
- the gradient of $f$ at point $x_\alpha$:
$$
\nabla f(\mathbf{x}_a) =
\begin{bmatrix}
\frac{\partial f}{\partial x_1}(\mathbf{x}_a) \\
\frac{\partial f}{\partial x_2}(\mathbf{x}_a) \\
\vdots \\
\frac{\partial f}{\partial x_n}(\mathbf{x}_a)
\end{bmatrix} \in \mathbb{R}^n
$$

> [!Example] 
>$$f(x, y) = x^2 + 3y^2 \implies \nabla f(x_a, y_a) =
\begin{bmatrix}
2x_a \\
6y_a
\end{bmatrix}$$

- Directional derivative multivariate function $f:R^n$ -> $R$
$$\nabla_{\mathbf{p}} f(\mathbf{x}_a) := \lim_{h\to 0} \frac{f(\mathbf{x}_a + h \mathbf{p}) - f(\mathbf{x}_a)}{h}
$$
$$
\text{If } f \text{ is differentiable, then } \nabla_{\mathbf{p}} f(\mathbf{x}_a) = \nabla f(\mathbf{x}_a)^T \cdot \mathbf{p}
$$

### Hessian matrix:
The second order derivative of $f$ yields the Hessian matrix:$$
H(f) =
\begin{bmatrix}
\frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\
\frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \cdots & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2 f}{\partial x_n \partial x_1} & \frac{\partial^2 f}{\partial x_n \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_n^2}
\end{bmatrix}$$
\***symmetrical** due to symmetry of second derivatives
$$\frac{\partial}{\partial x}\left(\frac{\partial f}{\partial y}\right)=\frac{\partial}{\partial y}\left(\frac{\partial f}{\partial x}\right)$$


## Jacobian matrix for vector-valued function
 - For a function $f: D$ -> $R^m$, $D\in R^n$, the Jacobian matrix $J$ is defined as:$$J_{\mathbf{f}}(x) =
\begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n}
\end{bmatrix}$$
\*The functions $f_i$ must be **differentiable**.

---

# Nonlinear Equations in R
## Bisection Method

> [!Example] Van der Waals equation
> $$\left( P + a \left(\frac{n}{V}\right)^2 \right) (V - nb) = nRT$$
> given $P,V,T$, n=?
> `f(n)=(P+a*(n/V)**2)*(V-n*b)-n*R*T`

- **Loop intuition**: 
1. Give a guessed initial interval\[$a_0,b_0$]
2. Check: $f(a_0)*f(b_0)<0$
3. Then compute $c_0=(a_0+b_0)/2$
4. if $f(a_0)*f(b_0)>0$ -> $a_1=c_0, b_1=b_0$
   else -> $b_1=c_0, a_1=a_0$

- **Bracketing**: ensure there is at least one root within it
1. Check: if $f(a_1)=0$ -> $a_1$ is the SOLUTION. 
2. Otherwise continue: $c_1=(a_1+b_1)/2$
3. if $f(a_1)*f(c_1)>0$ -> $a_2=c_1, b_2=b_1$
   else -> $b_2=c_1, a_2=a_1$

- **When to stop**: decide the discrepancy we can tolerate
==True error==:  $\epsilon=|y_n-y^{*}|$
$y^{*}$ is rarely available -> Compute ==estimated error==:$$\tilde{\epsilon}=|y_n-y_{n-1}|$$
==Relative error==:$$\epsilon_{rel}=\frac{|y_n-y_{n-1}|}{y_n}$$
Stop the iteration when a certain tolerance is reached

- **Limitations** of the bisection method: ==Edge cases==
If in reality there are multiple roots between \[$a,b$], the bisection solution is not liable
![[808c7274b75fdb62b458ddfb2bedf457cde5ac5bd8fc99d32937277c9c78735b.png]]
Solution: plot the function first


## Fixed-point equations
- rewrite $g(x)$ into $h(x)=x$
![[74f4273fa6de1ed36d212090ef448ba0d75cbc57299411206d418ee2bec8f0e5.png]]
- Start from an initial guess x_0, and iterate: $x_1=g(x_0)$ -> $x_2=g(x_1)$ - ...
General updating rule: $x_{n+1}=g(x_n)$
- Stopping criteria: $|g(x_n)-x_n|<\epsilon_{abs}$

**Limitations** of the fixed-point equations: ==Convergence==
Solution: Convergence proof  $|g'(x)|<1$
![[c99a529ba900c38e5284171fadf85ca6f166d0852d7ef3f5c596bffebfee693e.png]]


## Newton-Raphson method
- Start from initial $x_0$:
$$y_1=f(x_0)+f'(x_0)(x-x_0)$$
- Rearrange x:
$$x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}$$
![[c0b2295a6435cdb4cfb849cbdbc147090b288ad407bed498d52ddd662de53424.png]]

- Stopping criterion: estimated or true error(function value available)