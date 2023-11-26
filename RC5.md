# RC 5 Power Series

If you find it is very hard to do Fourier transformation, don't worry. You'll be expert of it if you take VE216. Today we'll focus on power series.

![image-20231126021126431](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231126021126431.png)

## The Power Series  Solution

For an ODE
$$
 x'' + p(t)x' + q(t)x = 0
$$


 If $p(t)$ and $q(t)$ have power series expansion with radius $ρ_1$ and $ρ_2$, then the solution $x$ has power series expansion of at least $min{ρ_1, ρ_2}$. (assume the center is t = 0) 

Then we can assume $x(t) = \sum_∞^k a_k t^k$ , plug into the equation, let the coefficients to be 0 and solve out ai .



### Excercise

Discuss the solution for the Legendre Function at $x = 0$:
$$
(1-x^2)\frac{d^2y}{dx^2} -2x\frac{dy}{dx}+l(l+1)y = 0
$$
Legendre Function is important in mathematical physics, especially electromegnetics. You'll find further explanation and calculation if you take VE 230 (or VP260).

Some website you can reference for this famous problem:

https://mathworld.wolfram.com/LegendreDifferentialEquation.html

http://zhiqihuang.top/mmp/lectures/MMP25_PlYlmMore.pdf

































## Regular Singular Points

The point is, if you met a sigular point at the point you want to find a approximate solution, what should you do?

Absolutely, it is impossible for you to find solutions for all the cases. We need to find the case where we can write out with finite number of  series with minus sign, which is the intuition of "regular" singular points.

For equation 
$$
P(t)x'' + Q(t)x'  + R(t)x = 0
$$


 If $P(t_0) = 0$, then the solution $x(t) = \sum_∞ ^k a_k (t − t_0) ^k$ may fail.

The equation 
$$
t^2 x'' + αtx' + βx = 0
$$


is called Euler’s Equation.

For $t > 0$ and $t < 0$, assume x = t^r , plug into the ODE, we have: 
$$
r^2 + (α − 1)r + β = 0
$$
 The general solution is 
$$
x(t) = \left\{ 
\begin{array}{ll}
c_1|t|^{r_1} + c_2|t|^{r_2} & \text{r is real} \\
c_1|t|^{r_1} + c_2|t|^{r_1} \ln |t| & \text{$r_1 = r_2$} \\
c_1|t|^\lambda \cos(\mu \ln |t|) + c_2|t|^\lambda \sin(\mu \ln |t|) & \text{if } r = \lambda \pm \mu i
\end{array} 
\right.
$$

For equation 
$$
x'' + p(t)x' + q(t)x = 0
$$
if either $p$ or $q$ is not analytic at $t = t_0$, then $t_0$ is called a singular point for this ODE.
If $p$ has a pole of order not more than 1 and $q$ has a pole of order not
more than 2 at $t_0$, then $t_0$ is called a regular singular point.
For example, Euler equation
$$
t^2 x'' + αtx' + βx = 0
$$
has regular singular point $ t = 0$.
For equation
$$
x'' + p(t)x'  + q(t)x = 0,
$$
we only cares about the situation where $(t-t_0)p(t)$ and $(t-t_0)^2q(t)$ is analyatic.


## The Method of Frobenius

For equation $x'' + p(t)x' + q(t)x = 0$ with regular singular point at `t = 0`, we rewrite the ODE as 
$$
t^2 x'' + t(tp(t))x' + t^2 q(t)x = 0`.
$$
`

Then assume $x(t) = t^r \sum_{k=0}^{∞} a_k t^k$.

Denote $p_i$ the Taylor coefficient for $t p(t)$, $q_i$ the Taylor coefficient for $t^2 q(t)$. Set $F(x) := x(x − 1) + p_0x + q_0$. Our conclusion is:

- $F(r) = 0$
- $a_m F(r + m) = − \sum_{k=0}^{m-1} (q_{m-k} + (r + k)p_{m-k})a_k$, for $m ≥ 1$

Two solutions of $r$ should give two independent solutions.

General Steps (Condition 1):

1. Calculate $r_1$, $r_2$, $p_i$, $q_i$.
2. For $r_1$, calculate $a_1$. $a_0$ is typically arbitrary, and can be set to 1.
3. Derive recurrence relation for $a_i$.
4. For $r_2$, if $r_1 ≠ r_2$, use the same method. Otherwise, proceed to condition 2.

Theorm: If $z_0$ is the sigular point of the function
$$
\frac{d^2w}{dz^2}+p(z)\frac{dw}{dz} + q(z)w=0,
$$
then in the circular area $0 < |z - z_0| < R$ where $p(z)$ and $q(z)$ are both analytic, two linearly independent solution are:
$$
w_1(z) = (z-z_0)^{r_1}\sum^\infin_{k=0}c_k(z-z_0)^k\\
w_2(z) = gw_1ln(z-z_0)+(z-z_0)^{r_2}\sum^\infin_{k=0}d_k(z-z_0)^k\\
$$
where $r_1$, $r_2$, and $g$ are constants.

### Exercise

Find the solution for Bessel Function at $x = 0$:
$$
\frac{d^2y}{dx^2}+\frac{1}{x}\frac{dy}{dx}+(1-\frac{\nu^2}{x^2})y = 0
$$
Suppose $\nu \notin \N$.















 





















<img src="C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231126024433165.png" alt="image-20231126024433165" style="zoom: 33%;" />

## Reference

Chongshi Wu, Mathematical Physics Methods.

Shuyu Wu, TA-VV286.

