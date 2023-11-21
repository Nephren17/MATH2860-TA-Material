# MATH 2860 RC 2

Presented by Yang Mo

## Matrix diagonalization

### Steps for Matrix Diagonalization

1. **Find the Eigenvalues and Eigenvectors**: For a given $n \times n$ matrix \(A\), we first find its eigenvalues and eigenvectors.
2. **Construct the Diagonal Matrix and Transformation Matrix**: Use the found eigenvalues to construct a diagonal matrix \(D\) and the eigenvectors to create a transformation matrix \(P\).
3. **Verify Diagonalization**: We can verify that we obtained the correct \(D\) by computing $P^{-1}AP$.

### Example

Consider the following matrix:

$A = \begin{bmatrix} 6 & 2 \\ 2 & 3 \end{bmatrix}$

**Step 1**: Find the eigenvalues and eigenvectors

To find the eigenvalues, we solve the equation:

$\text{det}(A - \lambda I) = 0$

where

$A - \lambda I = \begin{bmatrix} 6-\lambda & 2 \\ 2 & 3-\lambda \end{bmatrix}$

Solving this gives the eigenvalues $\lambda_1 = 7$ and $\lambda_2 = 2$.

Now we find the eigenvectors. For $\lambda = 7$, we have:

$(A - 7I)v = 0$

which gives an eigenvector $v_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix}$.

For $\lambda = 2$, we find another eigenvector $v_2 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$.

**Step 2**: Construct the diagonal matrix and transformation matrix

Using the eigenvalues and eigenvectors we found, we can construct the diagonal matrix \(D\) and transformation matrix \(P\):

$D = \begin{bmatrix} 7 & 0 \\ 0 & 2 \end{bmatrix}$

$P = \begin{bmatrix} 1 & -1 \\ 1 & 1 \end{bmatrix}$

**Step 3**: Verify diagonalization

Now we verify $D = P^{-1}AP$:

$P^{-1}AP = \begin{bmatrix} 1 & -1 \\ 1 & 1 \end{bmatrix}^{-1} \begin{bmatrix} 6 & 2 \\ 2 & 3 \end{bmatrix} \begin{bmatrix} 1 & -1 \\ 1 & 1 \end{bmatrix} = \begin{bmatrix} 7 & 0 \\ 0 & 2 \end{bmatrix} = D$

Thus, we have correctly diagonalized the matrix \(A\).

## Conditions to Diagonalize

The condition for a transformation $A$ in the $n$ dimensional space $V$ can be diagonalized is can be: 

1. A has $n$ independent eigenvectors
2. $dim \space V = dim \space V _{\lambda 1}+dim \space V _{\lambda 2}+...+dim \space V _{\lambda n}$, where $\lambda_i$ stands for the $i^{th}$ eigenvalue, and $V_{\lambda_i}$ stands for the space expanded through the eigenvectors corresponding to the $i^{th}$ eigenvalue.
3. $V$ can be written as the sum of direct sum of $V _{\lambda 1}$, $V _{\lambda 2}$,..., $V _{\lambda n}$



However, in some cases you cannot find enough eigen-vectors to reach the dimension of $V$. In this cases, you need to find some vectors that can be led to eigen-vectors through the matrix.



 ![image-20230920231807635](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230920231807635.png)

 ![image-20230920231832885](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230920231832885.png)

## Nilpotent Operators

Suppose $\exist l \in N^* $ and linear transformation $A$ satisfies that $A^l = 0$, we take the smallest $l$ as the least nilpotent exponent. This suggest that for $A$, $A^{l-1} \ne 0$ but $A ^l = 0$. We say $A$ is a nilpotent transformation.

Lemma: Suppose $A$ is a linear transformation on $F$, if $A^m \alpha \ne 0$ while $A^{m-1} = 0$, it can be concluded that $\alpha, A\alpha, \dots, A^{m-1}\alpha $ is independent with each other.

![image-20230921005938308](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230921005938308.png)



## Jordan Normal Form

### Steps to Find the Jordan Normal Form of a Matrix

1. **Find the eigenvalues**: As with finding eigenvectors, we first find the matrix's eigenvalues.
2. **Find the eigenvectors and generalized eigenvectors**: In addition to the regular eigenvectors, we need to find so-called “generalized eigenvectors” which will help us form Jordan chains.
3. **Form the Jordan chains**: Using the eigenvectors and generalized eigenvectors, we form Jordan chains.
4. **Construct the Jordan blocks**: Each Jordan chain corresponds to a Jordan block. A Jordan block is a square matrix with the eigenvalue on the diagonal and ones just above the diagonal.
5. **Construct the Jordan Normal Form**: We place all the Jordan blocks into a larger diagonal matrix to form the Jordan Normal Form.

For a 3 × 3 matrix A: 

1. Write out the characteristic polynomial and the eigenvalues 
2. If there is only one eigenvalue λ, calculate $(A − λI)^3$ and $(A − λI)^2$
3. Solve $(A − λI)^3 v = 0$ and choose a $v^{(3)}$  so that $(A − λI)^2 v \ne 0$ 
4. Obtain $v^{(2)}$ by $v^{(2)} = (A − λI)v^{(3)}$ 
5. Obtain $v^{(1)}$ by $v^{(1)}  = (A − λI)v^{(2)}$
6. Set $U = (v^{(1)}, v^{(2)}, v^{(3)})$ and calculate $U^{−1}AU$.

Check whether the matrix A below is diagonalizable and find its Jordan normal form. 

$A = \begin{bmatrix} 1 & 0 & 3 \\ 0 & 1 & 4 \\ 3 & 4 & 1 \\ \end{bmatrix}$

```mathematica
(* Step 1: Define matrix A *)
A = {{1, 0, 3}, {0, 1, 4}, {3, 4, 1}};

(* Step 2: Find the eigenvalues and eigenvectors *)
{eigenvalues, eigenvectors} = Eigensystem[A];

(* Step 3: Construct the transformation matrix P *)
P = Transpose[eigenvectors];

(* Step 4: Construct the diagonal matrix D *)
D = DiagonalMatrix[eigenvalues];

(* Step 5: Verify the diagonalization *)
PInverse = Inverse[P];
DiagonalizedA = PInverse . A . P;

(* Output the results *)
Print["Eigenvalues: ", eigenvalues];
Print["Eigenvectors: ", eigenvectors];
Print["Transformation matrix P: ", P];
Print["Diagonal matrix D: ", D];
Print["Verification of diagonalization (should equal D): ", DiagonalizedA];

```

![image-20230921001818974](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230921001818974.png)

*Note*: For all self-adjoint matrix, it is diagnolizable.


Consider the following $2 \times 2$ matrix:

$
A = \begin{bmatrix} 3 & 1 \\ 0 & 3 \end{bmatrix}
$

**Step 1**: Find the eigenvalues

We find the eigenvalues by solving the equation $ \text{det}(A - \lambda I) = 0$, where$ I$ is the identity matrix, and $\lambda$ is the eigenvalue.

$\text{det}(A - \lambda I) = \text{det}\left(\begin{bmatrix} 3-\lambda & 1 \\ 0 & 3-\lambda \end{bmatrix}\right) = (3-\lambda)^2 = 0$

This gives a repeated eigenvalue of $\lambda = 3$.

**Steps 2 and 3**: Find the eigenvectors and form the Jordan chains

We find the eigenvectors by solving $ (A - \lambda I)v = 0$:

$\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$

We get an eigenvector as $\begin{bmatrix} 1 \\ 0 \end{bmatrix}$.

Now we need to find a vector that is not an eigenvector but satisfies $ (A - \lambda I)v = \text{eigenvector}$. We solve the equation:

$\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$

We find another vector $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$ that forms a Jordan chain with the previously found eigenvector.

**Steps 4 and 5**: Construct the Jordan blocks and Jordan Normal Form

We end up with the following Jordan block:

$J = \begin{bmatrix} 3 & 1 \\ 0 & 3 \end{bmatrix}$

This also happens to be our Jordan Normal Form.





## Matrix for Jordon Normal Form

![image-20230921010055133](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230921010055133.png)

![image-20230921010128093](C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230921010128093.png)





## References

- VV286, slide. Horst Hohberger
- RC, slides. TA-Huang YuCheng

For further questions, you can contact me through WeChat.

<img src="C:\Users\Nephr\AppData\Roaming\Typora\typora-user-images\image-20230515231252742.png" alt="image-20230515231252742" style="zoom: 33%;" />

![此情可待成追忆——《葬送的芙莉莲》漫画推荐 - 哔哩哔哩](https://th.bing.com/th/id/OIP.IbqV0B5oht3La1m1wNYAYAHaGk?pid=ImgDet&rs=1)