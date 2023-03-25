# Midterm Guide

- 20% of points are from definitions, thus study !!! (Topic 0: Review part)



# Sample Midterm 2019 Solution

> - Note: This was done 2 weeks earlier & is missing the LLSP topic (we will be tested on this). 2019 version only contains review (topic 0) + QR methods (topic 1)



## Q1: Definitions (20% of the grade)

### a)

Define span of vectors in a V.S.

**==Solution:==**

Given $(V, \mathbb{K}, + , \cdot)$ a V.S and a subset $S \subseteq V$ of vectors.
$$
span(S) = \{a_1s_1 + \dots + a_ns_n : s_i \in S, a_i \in \mathbb{K}, n \in \N\}
$$
which is the set of all finite linear combinations.



### b)

Let $(V, \mathbb{K}, + , \cdot, <\cdot, \cdot>)$ be an Inner Product Space. State the properties satisfied by the Inner Prodcut map

**==Solution:==**

1. $<u,v> = <v,u>$ (symmetry)
2. $<au,v> = a<u,v>, <u+v,w> = <u,w> + <v,w>$ (Linearity in the first and second component)
3. $<u,u> \geq 0 \iff u = \vec 0$ (positivity)

**<u>Note:</u>** The descriptions in the bracket are good to have, but not required in the exam.



### c)

Consider $\R^n$ equipped with the usual vector addition, scalar product and inner product $< u, v >= u^T v$, and let $u, v \in \R^n$, and $W \subset R^ n$ be a subspace. Define orthogonal projection of u onto v. Define orthogonal projection of u onto W

**==Solution:==**

use a formula or explain in words by expressing the appropriate condition.

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230221193408725.png" alt="image-20230221193408725" style="zoom:50%;" />

<u>In formula:</u> $proj_v(u) = \frac{(v^Tu)}{v^T v}v$

<u>In words:</u> $proj_v(u)$ is the vector $u_v$ in $span\{v\}$ s.t the residual $r = u - u_v \perp span\{v\}$

The orthogonal projection of $u$ onto $W$ is te vector $u_w \in W$ s.t. $u - u_w \perp W$



### d)

In what sense is MGS an improvement over CGS?

**==Solution:==**

MGS slows down the loss of orthogonality relative to CGS when applying these processes in the presence of rounding errors.



### e)

State the Full and Reduced QR decompositions for a full column rank matrix A ∈ Rm×n. Is the reduced QR factorization always unique? What about the full QR factorization? Briefly explain conditions which may ensure uniqueness - if any (no detailed proof required).

**==Solution:==**

Given $A \in \R^{m \times n}, m \geq n$, full-column rank (which implies $m \geq n$)

- <u>Reduced QR decomposition:</u>

  $A = QR$ where 

  - $Q$  has orthonormal columns. ($Q$ is NOT a orthogonal matrix since it’s NOT a square matrix!)
  - $R$ is upper triangular matrix.

- <u>Full QR decomposition:</u>

  $A = \widetilde{Q}\widetilde R = [Q, Q^c]  \begin{bmatrix}
  R \\
   0 \\
  \end{bmatrix}$ where

  - $\widetilde Q$ is an orthogonal matrix, shape $m \times (n + (m-n))$
  - $R$ is upper triangular matrix, shape $(n+(m-n)) \times n$

Here the reduced decomposition is not unique but can be made unique by putting a constraint on the signs of the diagonal elements of $R$ (e.g. all positive, all negative)

The full decomposition is generally not unique because $Q^c$ can be made of any orthogonormal basis to $colspace (Q)$



## Q2

![image-20230306175949897](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230306175949897.png)

### a)

Write the linear combination a1v1 +a2v2 +a3v3 as a matrix-vector product. Are the v1,v2,v3 linearly independent? Do they span R3? Are they a basis for R3? Justify.

**==Solution:==**

Let $A = [v_1, v_2, v_3], \alpha =  \begin{pmatrix}
a_1 \\
 a_2 \\
a_3 \\
\end{pmatrix}$

The linear combination can be written as $A \alpha$ (details are needed for exam)

The vectors are dependent because:

1. $A$ can not be row-reduced to $I$ (get a row-vector of zeros)
2. $det(A)$
3. noticed that $v_1 + v_2 - v_3 = 0$



As well since these 3 vectors are dependent & $dim(\R^3) = 3$, then they can not span $\R^3$ & are not a basis.



### b)

Can you write v as a linear combination of v1,v2,v3? Justify your answer.

**==Solution:==**

Row reduced the augmented system
$$
\left(
\begin{array}{ccc|c}
   1 & 1 & 2 &2 \\
   1 & 0 & 1 &4\\
   0 & 2 & 2 &2
 \end{array}
\right) \stackrel{RREF}{=} \left(
\begin{array}{ccc|c}
   1 & 1 & 2 &2 \\
   0 & -1 & -1 &2\\
   0 & 0 & 0 &6
 \end{array}
\right) 
\implies \text{ not solvable }
$$


## Q3

### a) Skip, see A2 solution

### b)

If you were to find the QR factorization of A using the Modified Gram Schmidt algorithm, which method do you expect to provide more precise answer for this matrix? Briefly justify.

**==Solution:==**

In this case, they are exactly the same up to step 2. To solve this matrix $A$, we only need 2 steps, thus they are identical. (If the solving steps take more than 2 steps, then MGS give more precise result)



## Q4

### a)

For the matrix A in Question 3, state a Given’s matrix G such that GA puts the weight of the (3, 1) element into the (1, 1) element of A, and hence creates a zero in the (3,1) position. Multiply this matrix to the left of A and compute the resulting product.

**==Solution:==**

$G =  \begin{pmatrix}
c & 0 & -s \\
0 & 1 & 0 \\
 s & 0 & c \\
\end{pmatrix}$, where $r = \sqrt{a_{11}^2 + a_{31}^2}$, $c = \frac{a_{11}}r, s =- \frac{a_{31}}r$



### b) Skip, see A2 solution



### c)

From computation in **(b)**, yous should arrive at $A = \widetilde Q \widetilde R = $ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230306183414227.png" alt="image-20230306183414227" style="zoom: 25%;" />

Here columns of $Q$ are orthornormal basis for $colspace(A)$

Here columns of $Q^c$ are orthornormal basis for $colspace(A)^\perp$





## Q5

### a) Skip, see A1 solution (exact question)



### b)

Let B = [v1,v2,v3] where v1,v2,v3 are defined in Question 2. What are the Null Space, Image, Rank and Nullity of B? For the Null Space and Image, specify them by finding a basis and using span notation.



**==Solution:==**

$N(B) = \{\alpha =  \begin{pmatrix}
\alpha_1 \\
 \alpha_2 \\
\alpha_3 \\
\end{pmatrix} \in \R^3: B\alpha = 0\}$

We did a partial row reduction in previous question, continue from there
$$
\begin{pmatrix}
   1 & 1 & 2 \\
   0 & -1 & -1\\
   0 & 0 & 0 
\end{pmatrix} = \begin{pmatrix}
   1 & 1 & 2 \\
   0 & 1 & 1\\
   0 & 0 & 0 
\end{pmatrix} = \begin{pmatrix}
   1 & 0 & 1 \\
   0 & 1 & 1\\
   0 & 0 & 0 
\end{pmatrix} 
$$

$$
\alpha_1 + \alpha_3 = 0  \implies \alpha_1  = - \alpha_3\\
\alpha_2 + \alpha_3 = 0 \implies  \alpha_2 = -\alpha_3\\
$$

thus we have:

$\alpha = \alpha_3\begin{pmatrix}
-1 \\
 -1 \\
	1 \\
\end{pmatrix}$, $N(B) = \left\{\alpha_3\begin{pmatrix}
-1 \\
 -1 \\
	1 \\
\end{pmatrix} : \alpha_3 \in \R \right\} = span\left\{\begin{pmatrix}
-1 \\
 -1 \\
	1 \\
\end{pmatrix}\right\}$ is a basis for $N(B)$ and $Nullity(B) = rank(Null(B)) =1$, $Rank(B) = 3 - Null(B) = 2$



<u>For Im(B):</u>

$Im(B) = \left \{ B \alpha \in \R^3: \alpha \in \R^3\right\} = span (cols(B)) = colspace(B)$

- ==Note:== when row-reducing, you preserve the solution coefficients to the equation, but you destory the column space of the original matrix

Here are two ways to solve for $Im(B)$

1. Pick $v_1, v_2$ as sufficient for basis basis for $colspace(B) = Im(B)$
2. Column reduce (equivalent to row reducing the transpose). This presvers the column space





## Q6

