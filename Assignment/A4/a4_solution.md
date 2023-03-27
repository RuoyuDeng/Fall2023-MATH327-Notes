# Question 1

## a)

Let $X = [x_1 \;x_2\;x_3]^T \in \{x \in \R^3: ||x||_2 \leq 1\}$, then by applying the $\Sigma$ to the unit ball, we have:
$$
\Sigma X =  \begin{bmatrix}
3 & 0& 0  \\
0 & 2& 0 \\
0 & 0& 0\\
\end{bmatrix} \begin{bmatrix}
x_1 \\
x_2 \\
 x_3 \\
\end{bmatrix} =  \begin{bmatrix}
3x_1 \\
2x_2 \\
 0 \\
\end{bmatrix} = \begin{bmatrix}
y_1 \\
y_2 \\
 y_3 \\
\end{bmatrix}
$$
and since $x_1^2 + x_2^2 + x_3^2 \leq 1$, we have:

1. Boundary of unit ball:
   $$
   \begin{aligned}
   1 &= x_1^2 + x_2^2 + x_3^2 \\
   &\geq x_1^2 + x_2^2 \\
   &\geq(\frac{y_1}3)^2 + (\frac{y_2}2)^2
   \end{aligned}
   $$
   Thus the boundary of the unit ball has been mapped to the interior of the unit circle in $\R^2$

2. Interior of unit ball:
   $$
   \begin{aligned}
   1 &\geq x_1^2 + x_2^2 + x_3^2 \\
   &\geq x_1^2 + x_2^2 \\
   &\geq(\frac{y_1}3)^2 + (\frac{y_2}2)^2
   \end{aligned}
   $$
   Thus the interior of the unit ball has also been mapped to the interior of the unit circle in $\R^2$





## b)

Let $X$ be a unit sphere $\in \{x \in \R^n: ||x||_2 \leq 1\}$

### Case: $m \geq n$

We have $\Sigma = diag(\sigma_1, \dots , \sigma_n)$, and since some axes of the ellipse might be zero, we have: $r \leq n, \sigma_1 \geq \sigma_2  \dots \geq \sigma_r$
$$
Y =\Sigma X = \begin{bmatrix}
\sigma_1 x_1 \\
\sigma_2 x_2 \\ \vdots \\ \sigma_r x_r \\ \vdots \\ \sigma_n x_n \\ \vdots \\ \sigma_m x_m
\end{bmatrix} = \begin{bmatrix}
y_1 \\
y_2 \\ \vdots \\ y_r \\\vdots \\ y_n \\ \vdots \\ y_m
\end{bmatrix}
$$
since we have $n$ of singular values, thus all $x_i's \in X$ will be mapped to the surface of the ellipse even some of them might have a zero singular value $\sigma_i$. 



#### Subcase: m > n

1. Boundary of unit ball:
   $$
   \begin{aligned}
   1 &= x_1^2 + x_2^2 +\dots+ x_n^2 \\
   &\geq(\frac{y_1}{\sigma_1})^2 + \dots +(\frac{y_r}{\sigma_r})^2
   \end{aligned}
   $$
   Thus the boundary of the unit ball has been mapped to the interior of the n-dimenstional ellipse in $\R^m$ with $r$ of non-zero axes.

2. Interior of unit ball:
   $$
   \begin{aligned}
   1 &\geq x_1^2 + x_2^2 +\dots+ x_n^2 \\
   &\geq(\frac{y_1}{\sigma_1})^2 + \dots +(\frac{y_r}{\sigma_r})^2
   \end{aligned}
   $$
   Thus the interior of the unit ball has been mapped to the interior of the n-dimenstional ellipse in $\R^m$ with $r$ of non-zero axes.



#### Subcase: m = n

1. Boundary of unit ball:
   $$
   \begin{aligned}
   1 &= x_1^2 + x_2^2 +\dots+ x_n^2 \\
   &= x_1^2 + \dots + x_m^2 \\
   &=(\frac{y_1}{\sigma_1})^2 + \dots +(\frac{y_r}{\sigma_r})^2
   \end{aligned}
   $$
   When $m = n$, we have the boundary of the unit ball mapped to the boundary of the n-dimensional ellipse in $\R^m$ with r of non-zero axes.

2. Interior of unit ball: identical with subcase m > n.

   



### Case: $n > m$

We have $\Sigma = diag(\sigma_1, \dots , \sigma_m)$, and since some axes of the ellipse might be zero, we have: $r \leq m, \sigma_1 \geq \sigma_2  \dots \geq \sigma_r$
$$
Y =\Sigma X = \begin{bmatrix}
\sigma_1 x_1 \\
\sigma_2 x_2 \\ \vdots \\ \sigma_r x_r \\ \vdots \\ \sigma_m x_m
\end{bmatrix} = \begin{bmatrix}
y_1 \\
y_2 \\ \vdots \\ y_r \\ \vdots \\ y_m
\end{bmatrix}
$$
By definition, the set $\widetilde X = \{x_i : i \in [m+1, n]\}$ partitioned from the unit sphere set will not get mapped to the surface to the ellipse since they do not have corresponding $\sigma_i$ sigular values.

The set $X \setminus \widetilde X$ is the part of the surface of the unit ball which do map to the surface of the ellipse.

1. Boundary of unit ball:
   $$
   \begin{aligned}
   1 &= x_1^2 + x_2^2 +\dots+ x_n^2 \\
   &\geq x_1^2 + \dots + x_m^2 \\
   &\geq(\frac{y_1}{\sigma_1})^2 + \dots +(\frac{y_r}{\sigma_r})^2
   \end{aligned}
   $$
   Thus the boundary of the unit ball has been mapped to the interior of the m-dimenstional ellipse in $\R^m$ with $r$ of non-zero axes.

2. Interior of unit ball:
   $$
   \begin{aligned}
   1 &\geq x_1^2 + x_2^2 +\dots+ x_n^2 \\
   &\geq x_1^2 + \dots + x_m^2 \\
   &\geq(\frac{y_1}{\sigma_1})^2 + \dots +(\frac{y_r}{\sigma_r})^2
   \end{aligned}
   $$
   Thus the interior of the unit ball has been mapped to the interior of the m-dimenstional ellipse in $\R^m$ with $r$ of non-zero axes.





# Question 2

## Matlab function

```matlab
function plotMatrixImage(A,N,n)
theta = linspace(0, 2*pi, N+1);
x = cos(theta);
y = sin(theta);

figure();
% plot the circles
plot(x, y, 'b');
hold on;

circleVals = [x; y];
ATimesCircle = A * circleVals;
% plot the A times circles
plot(ATimesCircle(1,:), ATimesCircle(2,:), 'r');

randPoints = randn(2,n);
ATimesPoints = A * randPoints;
% plot the random points and the results after multiplying matrix A
plot(randPoints(1,:), randPoints(2,:), 'go');
plot(ATimesPoints(1,:), ATimesPoints(2,:), 'm*');

legend('Circle', 'Image of A multiply Circle', 'Random Points', 'Image of A multiply Random Points');
xlabel('e1-axis');
ylabel('e2-axis');
title('Geometry of Action of A on the Unit Circle and Randomly Generated Points');
end

```

## plotMatrixImage(A,20,100)

![image-20230326205956335](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230326205956335.png)



## plotMatrixImage(A,20,1000)

![image-20230326210008388](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230326210008388.png)



## plotMatrixImage(A,20,10000)

![image-20230326210020051](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230326210020051.png)





# Question 3

Given: $A \in \R^{m \times n}, A = U\Sigma V^T$, $U = span\{u_1, u_2, ..u_m\}, V =span\{v_1,v_2, ... v_n\}, u_i \in \R^m, v_j \in \R^n$

Denote $r' = min(m,n)$

Rewrite $A =\sum_{k=1}^{r} \sigma_k u_k v_k^T$ where $ r \leq r', \sigma_1 \geq \sigma_2\geq....\geq\sigma_r >0$

## a)

### $Null(A)$

For any $v= \alpha_1v_1 + \alpha_2v_2 + ... +\alpha_nv_n \in \R^n, \in Null(A)$, we have:
$$
\begin{aligned}
Av &= U\Sigma V^T v = 0\\
\end{aligned}
$$

$$
\begin{aligned}
U^T U\Sigma V^T v &= U^T0\\
\Sigma V^T v &= 0 \\
 \begin{bmatrix}
\sigma_1 v_1^Tv_1\alpha_1\\
\vdots \\
\sigma_{r} v_{r}^Tv_{r}\alpha_{r} \\
\vdots \\
\sigma_{r'} v_{r'}^Tv_{r'}\alpha_{r'}
\end{bmatrix} & = 0 \\
 \begin{bmatrix}
\sigma_1 \alpha_1\\
\vdots \\
\sigma_{r} \alpha_{r} \\
\vdots \\
\sigma_{r'} \alpha_{r'}
\end{bmatrix} & = 0
\end{aligned}
$$

Thus $Null(A) = Null(\Sigma V^T)$ and the nullity depends on the number of zero singular values in $\Sigma$. By our definition, $r$ is the number of non-zero singular values, thus the dimension of $Null(A)$ is $n -r$.



### $Range(A)$

For any $v = \alpha_1v_1 + .... +\alpha_nv_n \in \R^n$
$$
\begin{aligned}
Av &=\sum_{k=1}^{r} \sigma_k u_k v_k^T (\alpha_1v_1 + .... +\alpha_nv_n) \\
&=\sum_{k=1}^{r} \sigma_k \alpha_ku_k 
\end{aligned}
$$
Thus $Range(A) = span \{u_1, u_2 ,... u_r\}$, which implies that the dimension of $Range(A)$ is $r$.



### $Range(A)^{\perp}$

Let set $S = span\{u_1, u_2, ..u_m\} \setminus span \{u_1, u_2 ,... u_r\} = span\{u_1, u_2, ..u_m\} \setminus Range(A)$. Since $[u_1, ..., u_m]$ is an orthonormal basis of $\R^m$ and $S$ is a subset of such orthonormal basis, we know that $\forall u_i \in S , \forall u_j \in Range(A), j\neq i, u_i \perp u_j$ 

Therefore, $Range(A)^\perp = S$, and its dimension is $m - r$.



## b)

Given $A = U\Sigma V^T, A^T = U^T\Sigma^T V$. By the nature of $\Sigma$, we know that $\Sigma^T$ will have the same number of non-zero singular values as well as $\Sigma$.

As we proved in question 3 a), we know that $dim(colspace(A)) = r, dim(colspace(A^T))=r$

We also know $colspace(A^T) = rowspace(A)$

Therefore:
$$
dim(colspace(A)) = dim(rowspace(A)) = r
$$


## c)

### 2-norm

$$
\begin{aligned}
||A||_2 &= \max_{\matrix{||x|| = 1 \\ x \in \R^n}} ||Ax||_2\\
&= \max_{\matrix{||x|| = 1 \\ x \in \R^n}} || U\Sigma V^Tx||_2 \\
&=  \max_{\matrix{||x|| = 1 \\ x \in \R^n}} ||\Sigma x||_2 \text{ since multiplying orthogonal matrices does not effect norm}
\end{aligned}
$$

The maximum is reached when we take $x =  \begin{bmatrix}
1 \\
 \vdots \\
 0 \\
\end{bmatrix}_{n \times 1}$ because by definition of the singular values, we have it sorted in a descending order: $\sigma_1 \geq \sigma_2 ...\geq \sigma_{min(m,n)}$. Thus $||A||_2 = |\sigma_1| = \sigma_1$



### F-norm

$$
\begin{aligned}
||A||_F &= ||U\Sigma V^T||_F \\
&= || \Sigma ||_F
\end{aligned}
$$

By definition of F-norm, we obtain: $||A||_F = ||\Sigma||_F = \sqrt{\sum_{i =1} ^ {min(m,n)} \sigma^2_i}$



## d)

### $A^TA$

Since we know that $U,V$ are square orthogonal matrix, we can write:
$$
A^TA =(V\Sigma^T U^T)(U\Sigma V^T) = V\Sigma^T\Sigma V^T  \\
=V  \begin{bmatrix}
\sigma_1^2 & \dots & 0\\
 0 & \ddots & 0\\
0 & 0 & \sigma_{r'}^2 \\
\end{bmatrix}_{n \times n} V ^T = \begin{bmatrix}
\sigma_1^2 & \dots & 0\\
 0 & \ddots & 0\\
0 & 0 & \sigma_{r'}^2 \\
\end{bmatrix}
$$
Then the eigenvalues of $A^TA$ are $\sigma_i^2, i \in [1, r']$ where $r'$ denotes $min(m,n)$



### $AA^T$

$$
AA^T = (U\Sigma V^T)(V\Sigma^T U^T) = U\Sigma\Sigma^T U^T \\
= U  \begin{bmatrix}
\sigma_1^2 & \dots & 0\\
 0 & \ddots & 0\\
0 & 0 & \sigma_{r'}^2 \\
\end{bmatrix}_{m \times m} U ^T = \begin{bmatrix}
\sigma_1^2 & \dots & 0\\
 0 & \ddots & 0\\
0 & 0 & \sigma_{r'}^2 \\
\end{bmatrix}
$$

Then the eigenvalues of $AA^T$ are $\sigma_i^2, i \in [1, r']$ where $r'$ denotes $min(m,n)$



# Question 4

## a)

### $||A||_2$

$$
||A||_2 = \sigma_1 = 4
$$

### $||A||_F$

$$
||A||_F = ||\Sigma||_F = \sqrt{4^2 + 3^2+2^2 + 1} \approx 5.477
$$



### $$||U||_2$$

$$
||U||_2 = \max_{\matrix{||x|| = 1 \\ x \in \R^n}} ||Ux||_2 = \max_{\matrix{||x|| = 1 \\ x \in \R^n}} ||x||_2 = 1
$$





### $rank(A)$

We observe that there are 4 non-zero singular values in $\Sigma$, thus $rank(A) = 4$



## b)

### $range(A)$

$$
range(A) = span\left\{        
 \begin{bmatrix}
0 \\
\frac1{\sqrt3} \\
-\frac1{\sqrt3} \\
\frac1{\sqrt3} \\
0\\
\end{bmatrix},

 \begin{bmatrix}
1 \\
0 \\
0 \\
0 \\
0\\
\end{bmatrix},

 \begin{bmatrix}
0 \\
-\frac1{\sqrt2} \\
-\frac1{\sqrt2} \\
0 \\
0\\
\end{bmatrix},

 \begin{bmatrix}
0 \\
0 \\
0 \\
0 \\
1\\
\end{bmatrix}

\right\}
$$

thus the basis for $range(A)$ is:
$$
\left\{        
 \begin{bmatrix}
0 \\
\frac1{\sqrt3} \\
-\frac1{\sqrt3} \\
\frac1{\sqrt3} \\
0\\
\end{bmatrix},

 \begin{bmatrix}
1 \\
0 \\
0 \\
0 \\
0\\
\end{bmatrix},

 \begin{bmatrix}
0 \\
-\frac1{\sqrt2} \\
-\frac1{\sqrt2} \\
0 \\
0\\
\end{bmatrix},

 \begin{bmatrix}
0 \\
0 \\
0 \\
0 \\
1\\
\end{bmatrix}

\right\}
$$
and the dimension is 4



### $null(A)$

Since there is no non-zero singular values in $\Sigma$, we know that the nullity of $A$ is 0, which implies that $Null(A) = \{ \vec 0\}$



## c)

Reduced SVD:
$$
A = 
\begin{bmatrix}
0 & 1 & 0 & 0\\
\frac1{\sqrt3} & 0 & -\frac1{\sqrt2}  & 0 \\
-\frac1{\sqrt3} & 0 & -\frac1{\sqrt2} & 0 \\
\frac1{\sqrt3}  & 0 & 0 & 0\\
0  & 0 & 0 &  1\\
\end{bmatrix}

\begin{bmatrix}
4 & 0 & 0 & 0\\
0 & 3 & 0  & 0 \\
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 1\\
\end{bmatrix}

\begin{bmatrix}
0 & 1 & 0 & 0\\
0 & 0 & -1  & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1\\
\end{bmatrix}
$$


## d)

$$
A^TA = V(\Sigma^T\Sigma)V^T = 

\begin{bmatrix}
0 & 0 & 1 & 0\\
1 & 0 & 0  & 0 \\
0 & -1 & 0 & 0 \\
0 & 0 & 0 & 1\\
\end{bmatrix}

\begin{bmatrix}
4^2 & 0 & 0 & 0\\
0 & 3^2 & 0  & 0 \\
0 & 0 & 2^2 & 0 \\
0 & 0 & 0 & 1^2\\
\end{bmatrix}


\begin{bmatrix}
0 & 1 & 0 & 0\\
0 & 0 & -1  & 0 \\
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1\\
\end{bmatrix}
$$

Based on what we have showned in question 3, d), we know that the eigenvalues of $A^TA$ are: $16, 9, 4, 1$

Since this product of three $4 \times 4$ matrices is also a $SVD$ for $A^TA$ because $V,V^T$ are orthogonal matrices and the matrix in the middle has descending diagonal values and it is a diagonal matrix. Thus the singular values of $A^TA$ are: $16,9,4,1$, which are identical with its eigenvalues.



## e)

Let 
$$
A = \sum_{i=1}^{min (m,n)} \sigma_iu_iv_i^T
$$


Based on hint note given in class, we know that:
$$
||A-A_2||_2  = ||\sum_{i=1}^{min (m,n)} \sigma_iu_iv_i^T - \sum_{i=1}^2\sigma_iu_iv_i^T||_2 \\
= ||\sum_{i=3}^{min (m,n)} \sigma_iu_iv_i^T ||_2 \\
=\sqrt{\sigma_3^2 + \dots +\sigma_{min(m,n)}^2}
$$
where:
$$
A_2 = \sum_{j=1}^2\sigma_ju_jv_j^T
$$




# Question 5

## a)

![image-20230327163714371](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230327163714371.png)

where the title $A_i$ refers to the visual change after applying the approximation matrix on the original $A$.



## b) the ratio of $\sigma_i$ only for A or A~k~ as well?

### $E_k$ against $k$

![image-20230327170040538](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230327170040538.png)

As we observe, the $k$ value needs to be at least 16 to ensure that $E_k = ||A_k-A||_2 / ||A||_2 \leq 0.05$



### $\sigma_i / \sigma_1$ ratio

![image-20230327170317590](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230327170317590.png)



## c)??hint

since the singular values are sorted on diagonal in descending order, we guarantee that the sum of first k number will be larger than any other sum of k singular values out of the diagonal. To minimize the error, we want to maximize A~k~, thus ~~ is the solution.