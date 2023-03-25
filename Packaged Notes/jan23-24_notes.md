# Topic 1: Orthogonalization

## Orthogonal set and orthonormal

- Two vectors $u,v \in \R^n$ are orthogonal <u>iff</u> $u^Tv = 0$

- in extend: vectors $v_1....v_n$ forms an ==orthogonal set== <u>if (no longer if and only if):</u>
  $$
  v_i^T v_j = \left \{ \matrix{0, i\neq j \\ ||v_i||^2 > 0, i= j}\right.
  $$



**==Note:==** in textbooks, it is assumed that when we talk about an orthogonal set of vectors, we exclude the zero vector.

Also, the set $\{v_1,....v_n\}$ is ==orthonormal== if (special case of orthogonal set): 
$$
v_i^T v_j = \left \{ \matrix{0, i\neq j \\ 1, i= j}\right.
$$


It is customary, when discussing orthonormal sets of vectors, to use $q_1, ....q_n$.

You can package these vectors into a matrix:
$$
Q = \left [ \matrix{q_1  & q_2 & ... & q_n}\right]
$$
where ==$Q \in \R ^{m \times n}$== 

you can then write the orthonormality condition as 

$$
Q^TQ = \left [
\matrix 
{
q_1^T 
\\
q_2^T
\\
...
\\q_n^T
}
\right ] \left [
\matrix 
{
q_1  & q_2 & ... & q_n
}
\right ]
= \left [
\matrix 
{
q_1^Tq_1 & q_1^Tq_2 & ...& q_1^Tq_n
\\
q_2^Tq_1 & q_2^Tq_2 & ...& q_2^Tq_n
\\
...
\\
q_n^Tq_1 & q_n^Tq_2 & ...& q_n^Tq_n
}
\right ]
= I_n
$$





## Packaging Orthogonal/Orthonormal Matrix

> - We can encode orthogonality and orthonormality by packaging a (finite) collection of rothognal or orthonormal vectors in to a matrix.
>
>   This way we compress the represtation and simplify the notation. This way we can derive and then use the properties of matrices.

### Example

If $v_1,...v_k \in \R^n$ are orthognal, we can write $A := $, and orthogonality is expressed as:
$$
A^T A = \left [
\matrix 
{
v_1^T
\\
...
\\
v_k^T
}
\right ] 

\left [
\matrix 
{
v_1 &  ... & v_k
}
\right ] 
= 

\left [
\matrix 
{
||v_1||^2 & &
\\
& \ddots
\\
& & ||v_k||^2
}
\right ]
$$


Similarly, if $q_1,...q_k \in \R^n$ are orthonormal. Letting $Q := [q_1, ... q_n]$, orthonormality is expressed as $Q^TQ = I_{k\times k}$

- Note: $Q^TQ = I \centernot\implies QQ^T = I$, The implicication only holds for $k = n$

- <u>E.g)</u>
  $$
  q_1 = \left [
  \matrix 
  {
  1 
  \\
  0
  \\
  0
  }
  \right ], q_2 = \left [
  \matrix 
  {
  0
  \\
  1
  \\
  0
  }
  \right ], Q = \left [
  \matrix 
  {
  1 & 0
  \\
  0 & 1
  \\
  0 & 0
  }
  \right ]
  
  \\ Q^TQ = 
  \left [
  \matrix 
  {
  1 & 0 & 0
  \\
  0 & 1 & 0
  \\
  }
  \right ]
  
  \left [
  \matrix 
  {
  1 & 0
  \\
  0 & 1
  \\
  0 & 0
  }
  \right ]
   = 
   \left [
  \matrix 
  {
  1 & 0
  \\
  0 & 1 
  \\
  }
  \right ]
  
  \\
  
  QQ^T = \left [
  \matrix 
  {
  1 & 0
  \\
  0 & 1
  \\
  0 & 0
  }
  \right ] 
  
  \left [
  \matrix 
  {
  1 & 0 & 0
  \\
  0 & 1 & 0
  \\
  }
  \right ] = 
  
  \left [
  \matrix 
  {
  1 & 0 & 0
  \\
  0 & 1 &0
  \\
  0 & 0&0
  }
  \right ]
  \neq I
  $$

### Orthogonal Matrix

1. For $k = n$ (square matrix), if $Q$ has <u>orthonormal</u> columns, it is called an <u>orthogonal</u> matrix
2. If $Q$ has <u>orthogonal</u> (but not orthonormal) columns, we just say <u>“a matrix with orthogonal columns”</u>



As a linear transformation on orthogonal matrix preserves a number of characteristics as expressed in the following theorem (or if $Q$ has orthonromal columns, $k<n$, say $Q$ has orthonormal column):



#### <u>Theorem</u>

Let $u,v \in \R^n$ and consider $Q: \R^m \to \R^n$ (an <u>orthogonal</u> matrix denoted as a linear transformation), then:

==True $\forall u,v \in \R^n$==

1. $(Qu)^T \cdot (Qv) = u^Tv$
2. $||Qu|| = ||u||$
3. $\angle (Qu, Qv) = \angle(u,v)$



##### Proof of Theorem 1st outcome

$(Qu)^T \cdot (Qv) = u^TQ^TQv = u^TIv = u^Tv$



==**Note:**== In $\C^n$, orthogonal matrices are refered to as <u>unitary</u> matrices, here we have $Q^HQ =I$, and $QQ^H = I$ if $k = n$. The behavior is similar (e.g. prior theorem holds)



## Orthogonal Projections

### 1st Interpretation: Coefficients

Some properties of vectors expressed in terms of orthogonal or orthonormal <u>bases:</u>

Say $v_1, ... v_n \in \R^n$ is an orthogonal basis, $q_1,...q_n \in \R^n$ is an orthonormal basis & let $u \in \R^n$ be given. 

We can write $u$ as:

- $u = \alpha_1 v_1 + ...\alpha_n v_n , \alpha_j \in \R$
- $u = \beta_1 q_1 + ...\beta_n q_n , \beta_j \in \R$

The coefficients $\alpha_j, \beta_j$ can be easily found by taking inner products of the basis vectors with $u$



$v_1^T u = v_1^T (\alpha_1 v_1 + ...\alpha_n v_n) = \alpha_1v_1^Tv_1$, so $\alpha_1 = \frac{v_1^Tu}{v_1^Tv_1}$, similarly, $\alpha_j = \frac{v_j^Tu}{v_j^Tv_j}$



This simplifies even further when using the orthonormal basis becuase $q_j^Tq_j = 1$, so $\beta_j= q_j^Tu$



Therefore (plug in the new $\alpha, \beta$ coefficients),
$$
u = \sum_{j=1}^n \frac{v_j^Tu}{v_j^Tv_j} v_j = \sum_{j=1}^n(q_j^Tu)q_j
$$

Here, $\frac{v_j^Tu}{v_j^Tv_j}$ is the projection coefficient of $u$ onto $v_j$

and $q_j^Tu$ is the projection coefficient of $u$ onto $q_j$

---



We think a little bit deeper about these expressions.

Let $u,v \in \R^n$, The orthogonal projection of $u$ onto $v$, geometrically, is a vector $\alpha v$ s.t. 

- ==$u - \alpha v \perp v$== 

![image-20230123234548730](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230123234548730.png)

i.e. $v^T (u-\alpha v) = 0$

solving for $\alpha$ gives $v^Tu = \alpha v^Tv \implies  \alpha = \frac{v^Tu}{v^Tv}$

This is why in expressing $u$ in orthogonal bases or orthonormal bases uses these expressions, which are interpreted as <u>coefficients of orthogonal projections</u>





### 2nd Interpretation: Linear Map

Let’s interprete the object
$$
\frac{v^Tu}{v^Tv} v
$$
There are ==two ways== to express it and think about it. The first one we just saw.

The second is as a ==**linear map**== applied to this vector $u$. To see that, we rewrite as
$$
\frac{v^Tu}{v^Tv}v = v\frac{v^Tu}{v^Tv}  = \frac{vv^T}{v^Tv} u
$$

- Note that $\frac{v^Tu}{v^Tv}$ is a scalar, thus we can move it before $v$
- By matrix multiplication associativity, we have $v(v^Tu) = (vv^T)u$



This allows to show that orthogonal projections are linear transformations expressed through the matrices

$ \frac{vv^T}{v^Tv}$ where $ vv^T$ is a `n x n` matrix and $v^Tv$ is a scalar. The matrix $vv^T$ is called an outer product of $v$ with $v$. In general you define as $vu^T$.



#### Example

$$
v = 
\left [
\matrix 
{
1 
\\
2 
\\
3 
}
\right ],

u =

\left [
\matrix 
{
1 
\\
-1
\\
0 
}
\right ]
\\
\text{outer product between } u,v 
\\ vu^T = 

\left [
\matrix 
{
1 
\\
2 
\\
3 
}
\right ]


\left [
\matrix 
{
1  & -1 & 0
}
\right ]

=
\left [
\matrix 
{
1 & -1 & 0
\\
2 & -2 & 0
\\
3 & -3 & 0
}
\right ]

=
\left [
\matrix 
{
1v & -1v & 0v
}
\right ]
$$

- Their outer product is a rank 1, $n \times n$ matrix.





## Orthogonal Projector

We saw that if we have $v_1,... v_n$ orthogonal vectors 

and $q_1,...q_n$ orthonormal vectors in $\R^n$ 

and $u$ is an arbitrary vector in $\R^n$

we can express $u$ as follows
$$
u = \sum_{j=1}^n \frac{v_j^Tu}{v_j^Tv_j} v_j = \sum_{j=1}^n(q_j^Tu)q_j
$$


Where $\frac{v_j^Tu}{v_j^Tv_j}$ and $q_j^Tu$ are the orthogonal projection coefficients onto $v_j$ and $q_j$ respectively

And also, the coefficients of the linear combination representing $u$ in bases $[v_1, ...v_n]$ and $[q_1,...q_n]$

These projections can be interpreted as “calibrated (校准的)” scalars and they can alternatively by interpreted as “calibrated” linear mappings applied to $u$.

- <u>e.g</u> $(q_i^Tu)q_i = (q_iq_i^T)u$, where $q_iq^T$ is a $n \times n$ matrix

This way, we can abstract (remove or let vary) $u$ and think of this mapping ==**$q_iq_i^T$ as the orthogonal projector**== onto $span(\{q_i\})$



**==Note:==** projecting onto a vector is the same as projecting onto the linear space spanned by this vector

- ![image-20230124175158748](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230124175158748.png)



The reason to use spaces rather than vectors when discussing projections is to allow us to <u>generalize more easily.</u>

Let’s see how this works with two vectors and the general case follows inductively.



Let $q_1,q_2 \in \R^n$ be orthonormal. We saw that for $u \in \R^n$:
$$
Proj(u) = (q_1^Tu)q_1 + (q_2^Tu)q_2
\\ = (q_1q_1^T)u + (q_2q_2^T)u
$$
Then we can write:

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230124181334071.png" alt="image-20230124181334071" style="zoom:80%;" />



In picture:

![image-20230124180531569](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230124180531569.png)

$(q_1q_1^T + q_2q_2^T)$ is the orthogonal projection because $r := u - (q_1q_1^T + q_2q_2^T)u \perp span\{q_1,q_2\}$

- **<u>Note:</u>** ==r, the residual,== is the dashed line that’s perpenticular to the plane formed by $span\{q_1,q_2\}$
- $q_1q_1^T + q_2q_2^T$, in this case, is the orthogonal projector of $u$ onto $span\{q_1,q_2\}$

- Extending the argument for 2 orthonormal vectors to $k \leq n$ orthonormal vectors give the following <u>==theorem==</u>

### <u>Theorem</u>

Let $q_1, .... q_k \in \R^n$ be an orthonormal set of vectors and define $W = span \{q_1,...q_k\}$ and let $Q:= \left [
\matrix 
{
q_1 & q_2 & ... q_k
}
\right ]$

then $QQ^T = q_1q_1^T + ... +q_kq_k^T$ is the orthogonal projector onto $W$.



This means:

1. residual $(r = u - QQ^Tu) \perp W$
2. $QQ^Tu$ is the vector in $W$ closest to $u$ (in the $|| \;||$, the norm induced by the inner product)
   -  *This is a question in `A2`*

**==Note:==** what happens if $v_1,...v_k$ are <u>not orthogonal.</u> What is $VV^T$ where $V = \left [
\matrix 
{v_1 & ... & v_k}
\right ]$?

- This is still a projection onto $span\{v_1,...v_k\}$ but no longer orthogonal projection. It is an *oblique projection*.

- *Another `A2` question* 





## Orthogonalization Problem

> - **==Note:==** Going forward, we will use matrices of size $m \times n$, where:
>
>   - m: number of rows
>
>   - n: number of columns
>
>   ​	and we will reserve $k,i,j$ as running indices because we are going to talk about iterations.
>
> - We will also assume long matrices ($n \leq m$) rather than wide matrices

Given $a_1,a_2... a_n \in \R^m$, $n \leq m$, we construct orthonormal $q_1,...q_n \in \R^m$  such that 

- ==$span\{q_1,..q_n\} = span\{a_1,..a_n\}$== 

We will <u>assume</u> that $a_1,...,a_n$ are <u>**linearly independent**</u>. This is to ensure that orthogonalization algorithms run to completion. In practice, we do not know a priori if $a_1,...,a_n$ are independent but we find out while running the algorithms and reaching a point of breakdown.



If you package $a_1,..a_n$ into a matrix as $A = \left [
\matrix 
{
a_1 & ... & a_n
}
\right ]$ another way to express the assumption of linear independence of the $a_j$ is to say that $A$ is <u>full column rank ($rank(A) = n$)</u>

- **Note:** A has shape $m \times n$, which is not necessarily *square matrix*



### Orthogonalization Methods

We will see the following **==orthogonalization methods:==**

1. Classical Gram - Schemidt

   & Modified Gram - Schemidt

   - Slows down loss of orthogonality in classicial G-S due to rounding errors

2. Given’s Rotation method

3. Householder Reflections Method

All of these are equivalent in theory, but have different properties in the presence of rounding errors.



==**High-level:**== 

- Householder is prefered to Given’s (except in specific cases)

- Given’s is prefered to MGS
- MGS is preferd to CGS

The CGS is only used to construct the theory but rarely used in large applications.



In theory, these methods are equivalent under <u>1 assumption</u> which we will see next time.

They are all encoded (packaged) in the QR decomposition of A.