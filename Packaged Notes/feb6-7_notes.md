

### Before Givens Method: Recall Orthogonal Matrices Properties

Last time, we conpleted discussion about the QR decomposition via `CGS` and `MGS` and we extended the decomposition to <u>full QR</u>

The `CGS` and `MGS` construct the (reduced) $QR$ decomposition by focusing on constructing $Q$ and obtaining $R$ as a by-product. The next two methods focus on taking $A$ and applying orthogonal transformations to it until obtaining a matrix $R$ as defined in the $QR$ decomposition, and generating the orthogonal matrix $Q$ as a by-product.

Moreover, these methods produce the full $QR$ decomposition of $A$ where $Q = [q_1,...,q_n,q_{n+1},...q_m]$ in which $q_1,...q_n$ form an orthonormal basis for $span\{a_1,...a_n\}$ (column space of $A$) and $q_{n+1},...,q_m$ is an orthonormal basis for the orthogonal complement of that space (column space of $A$).





#### Theorems: properties of orthogonal matrices

let $Q, Q_1,Q_2 \in \R^{m \times m}$ be orthogonal (i.e. $Q^TQ = QQ^T=I$)

1. $Q$ preserves inner products and the corresponding norms, distances and angles.
   - e.g: $<Qu,Qv> = (Qu)^T \cdot (Qv)= u^TQ^TQv = u^Tv = <u,v>$
2. $det(Q) = \pm 1$
3. $Q_1$ and $Q_2$ orthogonal $\implies Q_1Q_2$ is orthogonal
4. $Q^{-1}$ is orthogonal





#### Proofs of Theorems Above

1. We did it before.

2. $$
   1 = det(I) = det(Q^TQ) = det(Q^T)det(Q) = det(Q)^2  
   \\\implies det(Q) = \pm1
   $$

3. By rerification: $(Q_1Q_2)^T(Q_1Q_2) = Q_2^TQ_1Q_1Q_2 = I$

   And since they are square, the same holds if you commute the product (switch order of $Q_1,Q_2$)

4. $$
   (Q^{-1})^T(Q^{-1}) =(Q^{-1})^T(Q^{T})  = (QQ^{-1})^T = I
   $$



Geometrically orthogonal matrices represent rigid motion (as defiend by preservation of Inner Product, norm, distances and angles)

There are two kinds of motions which preserve these quantities.

1. The <u>rotation</u> “moves” all vectors except $\vec 0$, no invariant vector. <u>Rotation</u> corresponds to the case $det(Q) = + 1$
2. The <u>reflection</u> has an invariant subspace (we will see an example when constructing $QR$ using `Householder`). <u>Reflection</u> corresponds to the case $det(Q) = -1$





### Givens Matrices (Rotation)

A <u>Givens Matrices</u> is one of the form:
$$
G = \left ( 
\matrix 
{
c &  -s
\\
s & c

}
\right )
$$
where $c^2 + s^2 = 1$



This is equivalant to writing:
$$
G = \left ( 
\matrix 
{
cos(\theta) &  -sin(\theta)
\\
sin(\theta) & cos(\theta)
}
\right ), \theta \in [0,2\pi)
$$
This rotates as follows:

- Case 1:

$$
\left ( 
\matrix 
{
cos(\theta) &  -sin(\theta)
\\
sin(\theta) & cos(\theta)
}

\right) \left ( 
\matrix 
{
1
\\
0
}
\right )
= \left ( 
\matrix 
{
cos(\theta)
\\
sin(\theta)
}
\right )
$$

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206181906197.png" alt="image-20230206181906197" style="zoom:50%;" />

- Case 2:

$$
\left ( 
\matrix 
{
cos(\theta) &  -sin(\theta)
\\
sin(\theta) & cos(\theta)
}

\right) \left ( 
\matrix 
{
0
\\
1
}
\right )
= \left ( 
\matrix 
{

- sin(\theta)
\\
cos(\theta)
}
\right )
$$

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206181946624.png" alt="image-20230206181946624" style="zoom:35%;" />

and this transformation rotates a general vector by $\theta$ in the ==counter-clockwise direction== by acting on the $\left ( 
\matrix 
{
1
\\
0
}
\right ), \left ( 
\matrix 
{
0
\\
1
}
\right )$ vectors.



The inverse of a `Givens Matrix` is its transpose
$$
\left(
\matrix 
{
c &  s
\\
-s & c

}
\right )

\left(
\matrix 
{
c &  -s
\\
s & c

}
\right )
=
\left(
\matrix 
{
c^2+s^2 &  -cs + sc
\\
-sc + cs & (-s)^2 + c^2

}
\right )

= \left(
\matrix 
{
1 &  0
\\
0 & 1

}
\right )
$$
The inverse corresponds undering what $G$ is doing, <u>i.e) inverse rotation</u> (if you put the negative angle, you get the transpose which is itself also a `Givens matrix`)



We can extend these structured matrices to $\R^{m \times m}$ as follows:

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206182851162.png" alt="image-20230206182851162" style="zoom: 50%;" />

- e.g) <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206182945770.png" alt="image-20230206182945770" style="zoom:50%;" />



The action of $G_{ij}$ is that it preserves all entries of a vector $ x = \left ( 
\matrix 
{
x_1
\\
\vdots
\\
x_m
}
\right )$ except the ones in the $i^{th} \&  \;j^{th}$ position by acting as a rotation only in hte $\R^2$ plane defined by the $i^{th} \&  \;j^{th}$ components of $x$.



#### Example of Action

$$
G_{ij} x = G_{ij} \left ( 
\matrix 
{
x_1
\\
\vdots
\\
x_{i-1}
\\
x_{i}
\\
\vdots
\\
x_{j}
\\
\vdots
\\
x_m
}
\right ) 

=\left ( 
\matrix 
{
x_1
\\
\vdots
\\
x_{i-1}
\\
cx_i - sx_j
\\
\vdots
\\
sx_i + cx_j
\\
\vdots
\\
x_m
}
\right )
$$

we can observe that $i^{th} \&  \;j^{th}$ positions of $x$ did not change



#### Problem

Given $\left ( 
\matrix 
{
x
\\
y
}
\right ) \in \R^2$, find a `Givens matrix` $G^T= \left(\matrix {c &  -s\\s & c}\right )$ s.t $G^T \left ( 
\matrix 
{
x
\\
y
}
\right ) = \left ( 
\matrix 
{
r
\\
0
}
\right ), r > 0 $

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206184207288.png" alt="image-20230206184207288" style="zoom:50%;" />

Where:

- $r = + \sqrt{x^2+y^2}$ (preserving length <u>i.e:</u> norm)
- $c = cos \theta = \frac xr$
- $s = sin\theta = \frac{-y}r$ (picking negative sign so that we have the rotation goes clockwise on picture)

**==Caution:==** we need to correctly pick the sign. If unsure, just verify algebraically:
$$
\left(\matrix {c &  -s\\s & c}\right )
\left ( 
\matrix 
{
x
\\
y
}
\right )
 = 
 \left(\matrix {x/r &  y/r\\-y/r & x/r}\right )\left ( 
\matrix 
{
x
\\
y
}
\right ) = \left ( 
\matrix 
{
\frac{x^2+y^2}r
\\
0
}
\right )

= 

\left ( 
\matrix 
{
r
\\
0
}
\right )
$$
**==Note:==** we assume $\left ( 
\matrix 
{
x
\\
y
}
\right ) \neq 0$, <u>i.e.</u> has rank 1, then reorganizing gives:

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206184858639.png" alt="image-20230206184858639" style="zoom:50%;" />

#### Abstract Example

Let $A = \left ( 
\matrix 
{
a_{11} & a_{12}
\\
a_{21} & a_{22}
\\
a_{31} & a_{32}
}
\right )$ full column rank. The `Givens method` for constructing $QR$ operates as follows:

1. **Step 1:** Find $G_1^T s.t$

   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206185218310.png" alt="image-20230206185218310" style="zoom:50%;" />

2. **Step 2:** Find $G_2^T s.t$

   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206204240698.png" alt="image-20230206204240698" style="zoom:70%;" />

3. **Step 3:** Find $G_3^T s.t$

   ![image-20230206204439030](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206204439030.png)

Here we have $A = G_1G_2G_3R$, and $Q = G_1G_2G_3$

$G_3$ looks like:

![image-20230206204459192](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230206204459192.png)

**==Note:==** $G_1,G_3$ look identical, but they are different by value



#### Detailed Example*

Continuing the topic of $QR$ (full) factorization by Givens rotations. Here is a concrete example:

Let $A = \left ( 
\matrix {1 & 1\\ 0 & 2 \\1 & 2  }
\right )$

==**<u>Step 1:</u>**==

 <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213003514013.png" alt="image-20230213003514013" style="zoom:15%;" />

Let

- $r^2 = x^2 + y^2 =1 \implies r = +1$ (we choose the + sign here)

- $c = \frac xr = 0$
- $s = - \frac yr = -1$

Then we take:
$$
G_1^T = 
\left ( 
\matrix {1 & 0 & 0\\ 0 & c & -s \\0 & s& c}
\right ) 
=
\left ( 
\matrix {1 & 0 & 0\\ 0 & 0 & 1 \\0 & -1& 0}
\right )
$$
Then we have:
$$
A_1 = G_1^TA = \left ( 
\matrix {1 & 0 & 0\\ 0 & 0 & 1 \\0 & -1& 0}
\right ) 
\left ( 
\matrix {1 & 1\\ 0 & 2 \\1 & 2}
\right )
=\left ( 
\matrix {1 & 1\\ 1 & 2 \\0 & -2}
\right )
$$
Note that:<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213004030372.png" alt="image-20230213004030372" style="zoom:10%;" /> $G_1^T$ acts on the blue block part of $A$



**<u>==Step 2:==</u>**

 <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213004155623.png" alt="image-20230213004155623" style="zoom:13%;" />

- $r^2 = x^2 +y^2 = 2 \implies r = \sqrt 2 \approx 1.414$ (we use estimate value to simplify notations)
- $c = \frac xr = \frac 1 {\sqrt2} \approx 0.707$
- $s = -\frac yr = -\frac 1 {\sqrt2} \approx -0.707$

Then:
$$
A_2 = G_2^TA_1 = G_2^TG_1^TA =\left ( 
\matrix {c & -s & 0\\ s & c & 0 \\0 & 0& 1}
\right ) \left ( 
\matrix {1 & 1\\ 1 & 2 \\0 & -2}
\right )
= \left ( 
\matrix {0.707& -0.707 & 0\\ -0.707 & 0.707 & 0 \\0 & 0& 1}
\right ) 
\left ( 
\matrix {1 & 1\\ 1 & 2 \\0 & -2}
\right )

=

\left ( 
\matrix {1.414 & 2.121\\ 0 & 0.707 \\0 & -2}
\right )
$$
**<u>==Step 3:==</u>**

 <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213004659143.png" alt="image-20230213004659143" style="zoom:18%;" />

- $r^2 = x^2 +y^2 = 4.5 \implies r  \approx 2.121$
- $c = \frac xr = \frac {0.707} {2.121} \approx 0.333$
- $s = -\frac yr = -\frac {2} {2.121} \approx -0.943$

Note: $G_3^T, G_1^T$ have the same layout, but $c,s$ values are different
$$
G_3^TA_2 =G_3^TG_2^TG_1^TA =\left ( 
\matrix {1& 0 & 0\\ 0 & 0.333 & -0.943 \\0 & 0.943& 0.333}
\right )
\left ( 
\matrix {1.414 & 2.121\\ 0 & 0.707 \\0 & -2}
\right )
= \left ( 
\matrix {1.414 & 2.121\\ \bar 0 & 2.121 \\\bar 0 & \bar 0}
\right )
$$
where $\bar 0$ denote the zeros up to rounding



##### Result

This gives $A = \widetilde {Q}  \widetilde {R} = QR$, where:

- $\widetilde {Q} = G_1G_2G_3 =$ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213010031273.png" alt="image-20230213010031273" style="zoom:25%;" />

- $ \widetilde {Q} \widetilde {R}$ is the full QR decomposition
- $QR$ is the reduced QR decomposition

We can rewrite: $A = \widetilde{Q}\widetilde{R} = (Q \; Q^c) \left(\matrix {R \\0} \right) = QR$ 

##### QR Algorithm Operation Pattern

The `Gives QR algorithm` operates in the following pattern:

![image-20230213010936734](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213010936734.png)



### Side Note: A2-Q2 (b) Pseudocode template

- **<u>Input:</u>** $ A= [a_1, ...a_n] \in \R^{m \times n}, m\geq n$, full column rank

- **<u>Algorithm:</u>**

  for j = 1,….n

  ​	$v_j = a_j$

  ​	for i = 1, … j-1

  ​		$R_{ij} = q^T_ia_j$

  ​		$v_j = v_j - R_{ij}q_j$

  ​	end

  ​	$r_{jj} = ||v_j||_2$

  ​	$q_j = v_j /r_{jj}$

  end

- **<u>Output:</u>** $R$ (result matrix) and $Q= [q_1,...q_n]$



### Side Note: A2-Q2 (b) Matlab code

```matlab
function [Q, R] = myGS(A)
[m,n] = size(A);
for j = 1:n
	v = A(1:m, j);
	for i = 1:j-1
		R(i,j) = Q(1:m,i)' * A(1:m,j); # ': transpose
		v = v - R(i,j) * Q(1:m,i);
	end
	R(i,j) = sqrt(v' * v); # L2 norm
	Q(1:m, j) = v/R(j,j);
end
```











