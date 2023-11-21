# Recitation Class 4: Complex Analysis

by Yang Mo

## Why Complex Analysis

I believe most of you may think complex numbers are just a joke, which is my previous thought. Complex numbers are useful, they can help us solve equations, find root of functions, and so on. But still you may think they're redundent. That's why we need complex analysis! We'll see they're useful,necessary and somewhat meaningful.

![image-20231111021653258](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231111021653258.png)

Calculate the following integral: 
$$
\int _∞ ^{−∞}\frac{cos(x)}{(1 + x^2)^2} dx
$$
Try evaluating an integral in complex plane:

1. Defne a suitable complex function. 

2. Identify and classify all poles of the function. 

3. Defne a toy contour and give parametrizations. 

4. Calculate residues at poles. 5 Evaluate integrals.





Similarly, we can have the derivative of complex function $f(z)$ where $z$ is a complex number:
$$
f'(z) = \lim _{h->0}\frac{f(z+h)-f(z)}{h}
$$
![image-20231111015230243](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231111015230243.png)

Some properties are listed as follows:

1. A holomorphic function is automatically infnitely often diferentiable.
2.  A holomorphic function is automatically analytic. 
3.  For a holomorphic function $f = \sum_{n=0}^∞ a_nz^n $(power series) on its radius of convergence, $f'$ has the same radius of convergence as f.

A function $f$ defined on an open set Ω ⊂ C is said to be analytic (or have a power series expansion) at a point $z_0 ∈ Ω$, if there exists a power series $f = \sum_{n=0}^∞ a_n(z-z_0)^n $  centered at $z_0$, with positive radius of convergence.

![image-20231111015249082](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231111015249082.png)

![image-20231111015308784](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231111015308784.png)

Up till now, all you see is still similar to what we have learned about in previous classes. Appreciate this beautiful world on real numbers! Now we're starting our trip to wired things.



## Cauchy-Riemann Equations

If a function $f = u(x, y) + iv(x, y)$ is holomorphic at $z_0 = x_0 + iy_0$, derivative of $f$ calculated from two directions must coincide. That is
$$
f' (z_0) := lim _{h_1→0, h1∈\R} \frac{f(x_0 + iy_0 + h_1) − f(x_0 + iy_0)}{ h_1}\\ 
 f' (z_0) := lim _{h2→0,h2∈\R} \frac{f(x_0 + i(y_0 + h_2)) − f(x_0 + iy_0)} {ih_2}
$$
This implies
$$
 \frac{∂u}{∂x} = \frac{∂v}{∂y} ,\\
 \frac{∂u}{∂y} = -\frac{∂v} {∂x} .
$$


This is a very important formula that separates complex analysis with multi-variable calculus!

This is actually talking about the characteristic that a function should follow. With simple induction, you can find this implies that
$$
\frac{\partial^2u}{\partial x^2} + \frac{\partial^2v}{\partial y^2} = 0, \\
\frac{\partial^2u}{\partial y^2}+\frac{\partial^2v}{\partial x^2} = 0.
$$
This is actually the Laplace function!

**Liouville's Theorem** 

If $f$ is bounded and analytic on the whole $\C$, $f$ is a constant function.



### Exercise

Give that $u(x,y) = x^2-y^2$, find $f$.

![image-20231112030245942](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030245942.png)









## Integrals along Complex Curves

Integral of complex curve: 
$$
\int_{C^∗} f(z)dz = \int_ I f(γ(t)) · γ' (t)dl
$$
Cauchy’s Theorem: Suppose f is holomorphic in an open set Ω ⊂ C containing a circle C and its interior. Then
$$
\oint_C
f(z)dz = 0.
$$
![image-20231112025517992](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112025517992.png)

### Exercise

Calculate the following integral: 
$$
\int^∞ _{−∞}\frac {cos(x)}{ (1 + x^2)^2} dx
$$



![image-20231112030314518](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030314518.png)



![image-20231112030326684](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030326684.png)
















### Exercise

Calculate the following integral:
$$
\int^ ∞
_0
\frac{sin^3(x)}{
x^3} dx
$$





![image-20231112030350697](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030350697.png)

![image-20231112030359876](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030359876.png)



![image-20231112030417550](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030417550.png)





















## ![image-20231112030143881](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231112030143881.png)

## Reference

TA Yuchen Wang, VV 286, FA 2022.

TA Leyang Zhan, VV286, FA 2021.

TA Yusheng Liu, VV286, FA 2021.
