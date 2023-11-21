# MATH 2860 RC 1

Presented by Yang Mo

Dear all.

It is my honor to see you still in the honors math course! It is the last honor math  course and I think the MATH 2860 is quite hard. This course concerns mostly about differential equations, linear algebra, complex analysis and series expansions. For me, I think math is not learned until I can apply it. You'll find that, there are always differential equations when you learn about electrodynamics, there will always be linear algebra when you want to do robotics, there will always be Fourier and Laplace transformation when you are studying signals. Last but not least, when everything is put on a complex foundation, things are extremely ridiculous but somehow interesting. Don't think you're bad at math if you find this course hard. Hilbert once said, "You won't master a math course until you studied it for five times." You'll meet all your friends in math in signal processing, electrodynamics, control theories, robotics, ML theory, operating science, financial engineering, fluid dynamics and etc. all the time. Wish you enjoy this course and cherish your time in the last fundamental math course.

Yours sincerely,

Yang Mo



## Implicit Theorem

![image-20230829015525334](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230829015525334.png)

![image-20230829024237967](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230829024237967.png)

We consider the two-dimension case. For $F(x,y) = 0$, suppose we want to study whether the function can be write out explicitly at point $(x_0,y_0)$. If $F$ satisfies:

- $F(x,y) \in C^1(D)$
- $\exist (x_0,y_0)\in D \space s.t. F(x_0,y_0) = 0$
- $(F'_y(x_0,y_0))^2 + (F'_x(x_0,y_0))^2 \ne 0 $

Then  $F(x,y) = 0$ has a explicit form in the neighborhood of point $(x_0,y_0)$ of $y =f(x)$. Besides, $f(x)$ posses a continuous derivative as $
$$
\frac{df}{dx} = - \frac{F'_x(x,y)}{F'_y(x,y)}
$$

#### Note: There is a minus sign!

### Exercise

1. Find the derivative of $F(x,y) = x^3 +y^3-3axy$ at point $(x_0,y_0) = (0,0)$.











2. Prove: For a continuously differentiable function $F$, if $F(x,y,z) =0$, then 


$$
   \frac{\partial x}{\partial y}\cdot \frac{\partial y}{\partial z}\cdot \frac{\partial z}{\partial x} = -1
$$









## Inverse Function Theorem

![image-20230829024659984](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230829024659984.png)

You can understand that with the help of single-dimension case. Find in what case you can have a inverse function for $y=f(x)$.

Also, I want to provide another point of view here to understand the inverse function theorem. For example, for the function $x =x(u,v)$ and $y=y(u,v)$, we can see them as an implicit function:

$F(x,y,u,v) = x   - x(u,v)$ and $G(x,y,u,v) = y - y(u,v) = 0$ and then try to solve  $u = u(x,y)$ and $v=v(x,y)$.















### Exercise

1. Find the derivative of the inverse map of $f (x, y)=(e^x cos(y), e^x sin(y))$.











2. Find the derivative of the inverse map of $f (x, y)=(x^2, y/x)$.











## Lagrange Multipliers for Constrained Extrema

### Finding Free Extrema

Let $\Omega\subset\mathbb{R}^n$ and $f:\Omega\to\mathbb{R}$.

1. $f$ is said to have a *(global) maximum* at $\xi\in\Omega$ if
   $$x\in\Omega\qquad\Rightarrow\qquad f(x)\leq f(\xi).$$
2. $f$ is said to have a *strict (global) maximum* at $\xi\in\Omega$ if
   $$x\in\Omega\setminus\{\xi\}\qquad\Rightarrow\qquad f(x)<f(\xi).$$
3. $f$ is said to have a *local maximum* at $\xi\in\Omega$ if there exists a $\delta>0$ such that
   $$x\in\Omega\cap B_\delta(\xi)\qquad\Rightarrow\qquad f(x)\leq f(\xi).$$
4. $f$ is said to have a *strict local maximum* at $\xi\in\Omega$ if there exists a $\delta>0$ such that
   $$x\in\Omega\cap B_\delta(\xi)\setminus\{\xi\}\qquad\Rightarrow\qquad f(x)<f(\xi).$$

The function $f$ is said to have a (strict) *global/local minimum* at $\xi$ if $-f$ has a (strict) global/local maximum at $\xi$.

**Essential Condition.** Let $\Omega\subset\mathbb{R}^n$, $f:\Omega\to\mathbb{R}$, and $\xi\in\text{int}\,\Omega$. Assume that all partial derivatives of $f$ exist at $\xi$ and that $f$ has a local extremum (maximum or minimum) in $\xi$. Then
$$\nabla f(\xi)=0.$$ If $f$ is differentiable at $\xi$, this implies $Df|_\xi=0$.

**Hessian & Extrema.** Let $\Omega\subset\mathbb{R}^n$ be open, $f\in C^2(\Omega)$, and $\xi\in\Omega$. Let $\nabla f(\xi)=0$ (i.e., $Df|_\xi=0$).

1. If Hess $f|_\xi$ is positive definite, $f$ has a strict local minimum at $\xi$.
2. If Hess $f|_\xi$ is negative definite, $f$ has a strict local maximum at $\xi$.
3. If Hess $f|_\xi$ is indefinite, $f$ has no extremum at $\xi$.

Note: A critical point is not necessarily an extremum. $(0,0)$ is a critical point for $y = x^3$. However, it is merely a *saddle point*.

### The Normal Form of Question

In general, constrained optimization problems can be classified into equality constraints and inequality constraints. Here, we will focus on equality constraints. The general form of such problems is to find the extremum of $f(x)$ subject to the constraints $g_i(x) = 0$, where $i = 1 ,2,3,\dots,n$. We can write the problem as:
$$
\min(\max) f(x)\\
s.t. g_i(x)  = 0,i = 1,2,3,\dots,n
$$

### Lagrange Multipliers

Let $\Omega\subset\mathbb{R}^n$ be open and $f\in C^1(\Omega,\mathbb{R})$, $g\in C^1(\Omega,\mathbb{R}^m)$, $m<n$. Assume that $f$ has a local extremum on the set $E=\{x\in\mathbb{R}^n:g(x)=0\}$ at $\xi\in E$. Assume further that in
$$
Dg|_\xi=\begin{pmatrix}
\frac{\partial g_1}{\partial x_1} & \cdots & \frac{\partial g_1}{\partial x_n} \\
\vdots                            & \ddots & \vdots                            \\
\frac{\partial g_m}{\partial x_1} & \cdots & \frac{\partial g_m}{\partial x_n}
\end{pmatrix},
$$
there exists a submatrix consisting of $m$ columns whose determinant does not vanish. Then there exist $m$ numbers (called Lagrange multipliers)
$$
\lambda_1,\ldots,\lambda_m\in\mathbb{

R}\\ 
\label{2.7.4}
Df|_\xi+\sum_{i=1}^{m}\lambda_i Dg_i|_\xi=0.
$$
In order to find the constrained extrema, we need to solve the $m + n$ equations

These equations are equivalent to the following: 
$$
\frac{\partial f}{\partial x_i}+\lambda_1\frac{\partial g_1}{\partial x_1}+\cdots+\lambda_m\frac{\partial g_m}{\partial x_i} & =0,\qquad\qquad i=1,\ldots,n, \\
g_j(x) =0,\quad\quad\quad j=1,\ldots,m.
$$

$$
F(x_1,\ldots,x_n,\lambda_1,\ldots,\lambda_m) := f(x)+\lambda_1g_1(x)+\cdots+\lambda_mg_m(x).
$$

Then at an extremal point, all partial derivatives of $F$ will vanish.











### Exercise

1. Calculate the maximum and minimum of function $u = x -2y+2z$ s.t. $x^2+y^2+z^2 = 1$.















2. If $x + y + z = 3$, $x, y, z > 0,$ find the maximum of $x + xy + xyz$.





## Eigenvalue Problem

### Eigenvalue Calculation

**Definition**: for a linear map $L ∈ L (V, V)$, if there exists a non-zero vector $v ∈ V$ and a number $λ$ so that $Lv = λv$, we can call λ to be an eigenvalue of L, and v an eigenvector of L. For a given λ, the set $Vλ := {v ∈ V|Lv = λv}$ is called the eigen-space for the eigenvalue $λ$. $dim V$ is called the geometric multiplicity of $λ$. **Independence of Eigenvector**: The eigenvector in different eigen-space are linearly independent.

Now we only discuss $L$ as a matrix. suppose$ L$ is an $n × n$ matrix. 

**calculation**: since $Lv = λv$, we have
$$
(L − λI)v = 0.
$$
In order for $v \ne 0$, $det(L − λI) = 0$. Here, $p(λ) := det(L − λI)$ is called the **characteristic polynomial**. The degree is $n$. By the fundamental theorem of algebra, there are $n$ eigenvalue of L if complex number and multiple root are taken into consideration. For each eigenvalue, its multiplicity of the root is called **algebraic multiplicity**.



### Matrix Diagonalization

Theorem about algebraic multiplicity and geometric multiplicity: In matrix $A$, for a given eigenvalue, the algebraic multiplicity is greater or equal to geometric multiplicity. If for all the eigenvalues, the algebraic multiplicity is equal to geometric multiplicity, then all the eigenvectors will form a basis of $R^n$ . In this kind of situation, we say the matrix A is diagonalizable.

If A is diagonalizable, set $U = (v_1, v_2, . . . , v_n) $to be the corresponding eigenvector of the eigenvalues $λ_1, λ_2, . . . , λ_n$ (for multiple roots, the corresponding eigenvectors have more geometric multiplicity). We have $D = U ^{−1}AU$ And $D = diag(λ_1, λ_2, . . . , λ_n)$. We say $D$ is the diagonal form of $A$.

Notice that $A = UDU^−1$ , so $A^k = UD^kU^{−1}$ . $D^k = diag(λ^k_1 , λ^k_2 , . . . , λ^k_n )$. So as long as A is diagonalizable, we can calculate the close form of A k easily.

### Exercise

1. Diagonalize the matrix

   ![image-20230829034130094](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230829034130094.png)







## Spectral Theorem

In quantum mechanics, also called Hermitian matrix. 

The adjoint of a linear map $L$ is defined as $L^∗$ that satisfy 
$$
<x,Ly>=<L^*x,y>
$$
If $L$ is a real matrix, $L^∗$ is just $L^T$ . If $L$ is a complex matrix, $L^∗$ is $\bar{L^T}$ . If a matrix $A$ is Self-Adjoint, i.e.,$ A = A^∗ $, then there are some good property regarding its eigenvalue and eigen-space, which is called spectral theorem.

If an $n × n$ matrix $A$ is Self-Adjoint, i.e., $A = A^∗$ , then we have: 

- Eigenvalues of $A$ are real. 
- $A$ is diagonalizable. 
- The eigenvalues of A can form an orthonormal base of $R^n$ .

### Exercise

1. $Q$ is a $12 × 12 $ orthogonal matrix $(Q^TQ = I)$. $x = (1, 1, . . . , 1)^T$ , $y = (1, −1, 1, −1, . . . , −1)^T$ .$ x, y ∈ R^{12}$. Calculate $||Qx||$ and $<Qx, Qy>$



## References

- VV286, slide. Horst Hohberger
- RC, slides. TA-Wu Shuyu

For further questions, you can contact me through WeChat.

<img src="C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230515231252742.png" alt="image-20230515231252742" style="zoom: 33%;" />

<img src="C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230903113711638.png" alt="image-20230903113711638" style="zoom: 10%;" />