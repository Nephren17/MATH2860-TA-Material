# MATH 2860 RC 3 Differential Equations

Provided by Mo Yang

Differential equations are a category of equations that involve functions and their derivatives. In essence, they describe how a certain quantity changes with respect to another, often with respect to time or space. These equations play a central role in mathematics, physics, engineering, and many other disciplines because they can describe a wide range of phenomena, from the simple to the extraordinarily complex. It is very common in our life to find differential equations, say, population growth, circuit analysis, economics, control problems,etc.

However, mostly, it is hard to find solutions. You'll meet different problems when you're trying to learn the way to solve. For most equations, we don't know how to solve. But for engineers, in many case, solving them numerically is enough.

In this course, you'll learn some classic equations that we can deal with, and later move to some general solutions to more common equations with the help of series.



## Separate the Variables

![image-20231014235201085](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231014235201085.png)

Ex 1: Find the solution of equation
$$
(1+x^2)ydy + \sqrt{1-y^2}dx = 0
$$
 











Ex 2: Find the solution of equation
$$
\frac{dx}{dy} = \frac{x+y}{x-y}
$$












## First Order Linear Equations

![image-20231014235250886](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231014235250886.png)

To make things more understandable, we can go through how this formula is raised for homogeneous conditions:











For inhomogeneous equations, things get a bit harder but still solvable:













Another way that is quite useful for dealing with inhomogeneous equations is "changing the constants into variable", which may be unexpectedly useful when you deal with some kind of differential equations:









## Equations that can be changed into FODE

Bernoulli's Equation:
$$
\frac{dy}{dx} + p(x)y=Q(x)y^n
$$
 











Ex 3: Find the solution of equation
$$
\frac{dy}{dx} = xy+x^3y^3
$$














## Reference

Yi Cheng, USTC, Mathematic Analusis I.

TA Letian Chen, VV 286, FA 2022.

TA Leyang Zhan, VV286, FA 2021.

TA Yusheng Liu, VV286, FA 2021.

![image-20231015011000954](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20231015011000954.png)

(Small Joke here, as Bernoulli's family contribute a lot to fluid mechanics and aerodynamics)