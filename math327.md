# Intro: Before Things Start

## What is Math: Model

- <u>**Modelling:**</u> ==is the process of associating the mathematical structure with real world systems. Also it’s the process of formalizing real world phenomena.==



## Reasons to Model

1. To understand essential principals which govern a system
2. Forecast (predict the future)



## Modelling Process

1. Association between <u>real world</u> and <u>mathematical conceptualization</u> (Not a formal process, ie. rules of modelling are not spelt out, ==not unique==)
2. ==<u>**!! KEY POINT !!: Validation**</u>==, the comparison between the <u>forcast of the model</u> and the <u>real world system</u>. Generally for a model to be considered <u>***scientific***</u>, it requires to be validated (validatable).



## Fields where Modelling Fails

- Examples of fields where modles work increasingly poorly:
  - Physics ==(least complicated/chaotic)==
  - Chemistry
  - Biology
  - Psychology
  - Economics and Finance
  - Political Model ==(most complicated/chaotic)==

**As one can observe, the level of complexity and chaoticity increases as the list goes downwards.**

---

# Topic 0: Review and Preview

## Numerical Analysis (Approximation Theory: Pre-computer)

### Definition

==**<u>(Informal) Def:</u>**== It is the study of approximating “complicated” objects with “simpler” objects.

- Similar to modelling, but not connecting to the world
- understand the behavior of the “complicated” objects by finding and analyzing the “simpler” objects

### Reasons of Numerical Analysis

1. If we understand how the simple objects behave and they approximate the complex objects, we may be able infer how the complex object behaves.
2. ==Computability:== we are often unable to perform computations on complex objects directly. Instead we approximate by simple ones and perform the computations on them.
   - <u>E.g:</u> Linear algebra in $\R / \C$ uses only addition & multiplication and a limit set of numbers.
   - <u>E.g:</u> to compute $e^x = 1 + x + \frac {x^2} {2!} + ....+\frac {x^k} {k!} + \frac {\omega^{k+1}} {(k+1)!}, \omega \in (0,x)$ using **Taylor Series**
   - <u>E.g:</u> use **Taylor Series** to approximate $\int e^{x^2} dx$



## Numerical Linear Algebra

### Concepts Recall* (need for the course)

#### Big Picture

- **In picture, we have the concepts: **

  **Vector Space -> Metric V.S -> Normed V.S -> Inner Product Spaces -> Hilbert Space**

  -   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230109230948963.png" alt="image-20230109230948963" style="zoom:50%;" />

#### Definitions

##### Def: Vector Space

A vector space is a quadraplet (V, $\mathbb{K}$, +, •), where $\mathbb{K} = \R$ or $\C$, and it is a field

- ==V:== set of vectors
- ==+:== vector addition
- ==•:== scalar-vector multiplication

which satisfies the **<u>following rules</u>**:

1. <u>Closure for +:</u> $\forall u,v \in V \implies u+v \in V$ 
2. <u>Closure for •:</u> $\forall u \in V, \alpha \in \mathbb{K} \implies \alpha u \in V$ 
3. <u>Associativity for +:</u> $\forall u,v,w \in V \implies (u+v) + w = u +(v+w)$ 
4. <u>Associativity for •:</u>  $\forall u \in V, a,b \in \mathbb{K} \implies a(b \cdot u) = (ab) \cdot u$
   - <u>*Note: The scalar multiplication in here is scalar multiplication between scalar and scalar*</u> 
5. <u>Commutativity for +</u>: $\forall u, v \in V \implies u+v = v+u$
6. <u>Distributivity for scalars over vectors:</u> $\forall a,b \in \mathbb{K}, u \in V \implies (a+b)u = au + bu$
7. <u>Distributivity for vectors over scalars:</u> $\forall a \in \mathbb{K}, u,v \in V \implies a(u+v) = au + av$
8. <u>$\exists$ zero vector:</u> $\exists  \vec 0 \in V s.t. \; \forall u \in V \implies \vec 0 + u = u$
9. <u>$\exists$ additive inverse vector:</u> $\forall u \in V, \;\exists (-u) \;s.t. u + (-u) = \vec0$
10. <u>The multiplicative identity:</u> satisfies $\forall u \in V \implies 1u =u, 1 \in \mathbb{K}$



###### Examples

1. $\R^n$
2. $\C^n$
3. Continuous functions on an interval
4. Polynomials



##### Def: Metric Vector Spaces

A metric vector space is a V.S equipped with a *distance function*



##### Def: Distance Function

Distance Function on (V, $\mathbb{K}$, +, •) -> (treat this quadraplet as vector space)

is a map 

==$d: V \times V \rightarrow [0, \infty] \; s.t. \forall u,v,w \in V$== 

we have the <u>following rules:</u>

1. $d(u,v) \geq 0, d(u,v) =0 \iff u=v$ <u>(positive rule)</u>
2. $d(u,v) = d(v,u)$ <u>(symmetry rule)</u>
3. $d(u,w) \leq d(u,v) + d(v,w)$ <u>($\triangle$ Inequality rule)</u>



##### Def: Norm

A norm on (V, $\mathbb{K}$, +, •) is a map 

==$||\cdot ||$:  $V \rightarrow [0, \infty]$ s.t. $\forall u,v \in V, a \in \mathbb{K}$== 

with the <u>follow rules:</u>

1. $||u|| \geq 0, ||u|| =0 \iff u = \vec 0$
2. $||au|| = |a| ||u||$ where `| |` is an absolute value function defined on $\mathbb{K}$
3. $||u + v|| \leq ||u|| + ||v||$

**==Note:==**

- Every norm induces a distance via: $d(u,v) = ||u-v||$. However, not every distance is inducible by a norm.
- The connection between L2 norm and inner product: $||x||^2 = <x,x>$





##### Def: Inner Product Space

An inner product space on (V, $\mathbb{K}$, +, •) is a map

==$<\cdot, \cdot>: V \times V \rightarrow \R \; or \; \C$ s.t $\forall u,v \in V, a,b \in \mathbb{K}$==

with the <u>following rules:</u>

1. $<u,v> = <v,u>$ in $\R$ <u>(symmetry)</u>

    $<u,v> = \overline{<v,u>}$ in $\C$ <u>(conjugate symmetry)</u>

2.  $<au, v> = a<u,v>$ and $<u+v, w> = <u,w> + <v,w>$

   which can be merged into one expression: $<au+bv, w> = a<u,w> + b<v,w>$

   **(Linearity in the first component)**

3. $<u,u> \geq 0, <u,u>=0 \iff u = \vec0$ <u>(positive definitness)</u>

**==Note:==** In this course **(except for specific assignment questions)** we will work almost always in $\R ^n$ and occasionally $\C^n$ with the full inner product space infrastrucutre. In this context our main inner product functions will be captured by the following:

- $<u,v> = u^Tv \text{ in } \R^n $
- $<u,v> = u^Hv = \bar u^T v \text{ in } \C^n$



##### Def: Subspace

Assumes (W, $\mathbb{K}$, +, •), $W \subseteq V$ is a subspace, <u>iff:</u>

1. Closure under +
2. Closure under •
3. $0 \in W$ (Non-empty)

-> closureness + non-emptieness

**==Note:==** It is sometimes easiest to use $0 \notin W$ to show that the subset $W$ is not a subspace





##### Def: Linear Combination

Given vectors $v_1,v_2....v_n \in V$ and scalars $a_1, a_2....a_n \in \mathbb{K}$, a linear combination of these vectors and scalars is an expression of the form: ==$v = a_1v_1 + a_2v_2 + .... a_nv_n$==

**==Note:==** The linear combination is always finite



##### Def: Span

Given a set $S \in V$, ==$span(S) = \{a_1s_1 +..a_ns_n | a_j \in \mathbb{K}, s_j \in S \}$==



##### Def: Linear Dependency (finite & infinite subsets of vectors)

- <u>(finite case):</u> Given vectors $v_1, ....v_n \in V$ are (linearly) dependent, ==**iff**== $\exists a_1,...a_n \in \mathbb{K}$ s.t. $a_1v_1 + ... +a_nv_n = 0$ where <u>not all $a_j$ are 0</u> (they can not all be zeros).
  - The essensce of this: remove the redundant vectors that can be generated out of the others
- <u>(infinite case, a more general definition which includes finite case):</u> $S \subseteq V$ is dependent ==**iff**== $\exists a_1,...a_n \in \mathbb{K}$ and $s_1, ...s_n \in S$ s.t  $a_1s_1 + ... +a_ns_n = 0$ where <u>not all $a_j$ are 0</u> (they can not all be zeros).
  - **==Note:==** The set $S$ in infinite case can potentially contain infinite many vectors and $s_1, s_2...s_n$ only form a subset of $S$, not the whole set $S$.



##### Def: Linear Independency

A set of vectors is independent if they are not dependent.

- In the finite case, this means: if $a_1v_1+...+a_nv_n = 0$ $\implies a_1=a_2=...=a_n=0$

**==Note:==** 

- Dependence captures the idea of redundancy
- Independence also captures the idea (as a consequence) of uniqueness of construction (in the scalars)



##### Def: Dimension

The number of elements in a basis of a VS is called the <u>**dimension**</u> of V, written as $dim(V)$



##### Def: Basis

$\beta \subseteq V$ ==(a V.S) -> as Vector Space== is a basis <u>iff:</u>

1. $span(\beta) = V$
2. $\beta$ is independent



###### <u>Theorem: VS always has basis</u>

Assuming **<u>the axiom of choice</u>**, every vector space has a basis.

- since we stick with $\R,\C$ as our $\mathbb{K}$, we do not need to worry about the special case where the axiom of choice does not hold



###### <u>Theorem: Set extends to basis</u>

Every independent set $S \subseteq V$ can be extended to a basis. **(not unique)**



###### <u>Theorem: unique rep of vector with basis</u>

Given a basis $\beta$ of V, we can represent every $v \in V$ <u>**uniquely**</u> as:

==$v = a_1v_1 + a_2v_2 + .... a_kv_k$== Where $a_j \in \mathbb{K}, v_j \in \beta$



**==Note:==** The fact that $\beta$ is independent means that if any vector $v$ has two different representations, then if you subtract them you get a non-trivial linear combination to equal to $\vec 0$, which would contradict independence.



###### <u>Theorem: same bases cardinality</u>

Any two bases of a vector space have the same cardinality **(dimension is constant)**, i.e. the same number of elements



##### Def: Orthogonality

$u,v \in V$, (V is a V.S) are orthogonal <u>iff:</u> $<u,v> = 0$

- In $\R^n: u^Tv=0$ (u,v column vectors)
- In $\C^n:u^Hv=0$ ($u^H = \bar u^T$)

**==Note:==** $u^H$ is the typical notation used in Numerical Matrix Analysis



##### Def: Projection

The projection of $u$ onto $v$ is defined by:
$$
Proj_v(u) := u_v := \frac{<u,v>}{<v,v>} v
$$
In $\R^n:$ 
$$
\frac{u^Tv}{v^Tv}v
$$


In $\C^n:$
$$
\frac{u^Hv}{v^Hv}v
$$


**==Note:==** you can not simplify the $v$ since we are doing dot product in the fraction rather than a simple multiplication

<u>Geometry:</u>

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230116180745223.png" alt="image-20230116180745223" style="zoom:50%;" />

- We will extend this notation to projection onto subspaces using projection matrices later on.





##### <u>Theorem (Pythagoras)</u>

If $u,v \in V$ are orthogonal, then: $||u\pm v||^2 = ||u||^2 + ||v||^2$ where $|| \cdot ||$ is the norm induced by the underlying I.P. (Inner Product Space)



##### <u>Theorem (Cauchy-Schwarz)</u>

For every $u,v \in V:$

==$|<u,v>| \leq ||u|| \;||v||$, equivalently, $<u,v>^2 \leq <u,v> \cdot <u,v> = <u,u> \cdot <v,v>$==

- **==Note:==** In most cases, our inner product will be dot product, thus we can rewrite the formula as:
  $$
  |u^Tv| = |u \cdot v| \leq ||u|| \; ||v||
  $$
  

The above is an equality <u>iff</u> $u,v$ are <u>collinear</u> ==(one is a scalar multiple of the other, $u = av$ or $v = au$)==

- Whenever any two provided vectors are **parallel to the same given line**, they can be considered to be collinear vectors



The Cauchy - Schwartz inequality allows to define the concept of an angle assuming: ==$u,v \neq 0$== 



##### Def: Angle btw Vector

Given $u,v \in V,$ both non-zero, define:
$$
cos (\theta(u,v)) := \frac{<u,v>}{||u|| \; ||v||}
$$
where $\theta(u,v)$ is the ==angle btw $u,v$==, note that in this case, $\theta(u,v)$ <u>**is not defined uniquely in the above formula.**</u>

Normally we define:
$$
\theta:= arccos(\frac{<u,v>}{||u|\; ||v||})
$$
which ==**defines $\theta$ uniquely.**==



**<u>==Next we define linear functions, called Linear Transformations or Linear Maps or Linear Operator between vector spaces==</u>**



##### Def: Linear Transformation 

Let V, W be vector spaces over the <u>same field of scalars</u> $\mathbb{K}$

A Linear Transformation between V and W is a function $T: V \rightarrow W$ s.t. $\forall v_1,v_2\in V, a \in \mathbb{K}$, we have:

1. $T(v_1 + v_2) = T(v_1) + T(v_2)$

2. $T(av_1) = aT(v_1)$

3. <u>We can also express the above in a single expression:</u> $T(a_1v_1 + a_2v_2) = a_1T(v_1) + a_2T(v_2)$, or equivalently,

   $T(a_1v_1 + ...+a_kv_k) = a_1T(v_1) + ....a_kT(v_k)$ (even more general)

**Visually:**

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230116185021819.png" alt="image-20230116185021819" style="zoom:50%;" />

**==Note:==** Sometimes these are bijective -> invertible -> preserve information, sometimes they are injective (but not bijective), in which case you lose information.

- **E.g) $T(v) =0 , \forall v \in V$** is a valid linear transformation, but it’s not bijective, thus we can not invert the linear transformation since information is lost



##### Def: Null space (Kernel)

Let $T: V \rightarrow W$ be a linear transformation. The null space (or kernel) of $T$ is defined by $N(T) = \{v \in V: T(v) =0 \in W\}$

- Can also be denoted by: $Null(T)$



##### Def: Image

The image of $T$ is defined by $Im(T) = \{w = T(v) : v\in V, w\in W\}$



##### Def: Nullity

The <u>nullity</u> of a linear transformation $T: V \rightarrow W$ is defined by $dim(Null(T))$



##### Def: Rank

The <u>rank</u> of a linear transformation $T: V \rightarrow W$ is defined by $dim(Im(T))$

- Also, <u>rank</u> is **the maximum number of its linearly independent columns (or rows) of a matrix**



##### <u>Theorem: sum of nullity and rank</u>

Let V be a finite dimensional V.S, then $dim(V) = Nullity(T) + rank(T) = dim(Null(T)) + dim (Im(T))$



##### <u>Theorem: Injective</u>

Let $T: V\rightarrow W$ be a linear transformation, then $T$ is injective <u>iff</u> $N(T) = \{\vec 0 \}$

- ==Injective:== Every element in $V$ is mapped to at most one elemetn in $W$, not necessarily all elements are mapped
- ==Surjective:== Every element in $V$ MUST be mapped to some $w$ in $W$, one $w$ can be mapped from several different elements $v$ from $V$
- ==Bijective:== Injective + Surjective 

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230306113707324.png" alt="image-20230306113707324" style="zoom:50%;" />



##### Concept: Matrix Representation

Every linear transformation between finite dimensional vector space is ==representable by a Matrix.==

Thus, when you study matrices, you are studying all possible linear transformations because of this representation.



##### Def: Orderd Basis

An <u>ordered basis</u> for a finite dimensional V.S is a basis where the order is important: $\beta = (v_1....v_k)$

This is relevant because it allows to ==construct matrices corresponding to linear transformations== explicitly.



###### Example: matrix vector multiplication

$A = \left ( \matrix{ 1 & 4 & 7 \\ 2 & 5 & 8 \\ 3 & 6 & 9} \right ), v = \left ( \matrix{ 1  \\ 1 \\ 2} \right )$

How do you think of $Av$ ?

**There are two ways to think about it:**

1.     <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230117175604646.png" alt="image-20230117175604646" style="zoom:67%;" />
   - ==A linear transformation appliled to vector $v$==

2. <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230117175821999.png" alt="image-20230117175821999" style="zoom:80%;" />
   - A linear combination of the columns of the matrix $A$, where $v = \left(\matrix{a_1 \\ a_2 \\ a_3} \right)$ contains the coefficients for the linear combinations.

**==Note:==** 

- In abstract linear algebra, you often use the first interpretation, while in numerical linear algebra, it is often compuationally convenient to take the second interpretation.
- One useful application of the 2^nd^ interpretation is in showing that vectors are **<u>independent</u>**, or that **<u>they form a basis</u>** by row reduction (for independence) & invertibility (for basis).





##### <u>Theorem: importance of ordered basis</u>

Let $V, W$ be finite dimensional V.S and let $\beta_v := (v_1,...v_n)$ and $\beta_w = (w_1,...w_m)$ be ordered bases for $V, W$ respectively. 

Let $T: V \rightarrow W$ be a linear transformation.

We can write the following:
$$
T(v_1) = a_{11}w_1 + a_{12}w_2 + ... + a_{1m} w_m 
\\ T(v_2) = a_{21}w_1 + a_{22}w_2 + ... + a_{2m} w_m  
\\ ....
\\ T(v_n) = a_{n1}w_1 + a_{n2}w_2 + ... + a_{nm} w_m
$$
where each linear combination is unique because $\beta_w$ is a basis.

- ==Recall:== every vector in a vector space can be uniquely identified by a linear combination of a basis.

If you take all coefficients $a_{ij}$ and package them into a matrix, you get the matrix representation of the linear transformation as:

$$
 \begin{pmatrix}
T(v_1) \\
T(v_2) \\
\vdots \\
T(v_n)\\
\end{pmatrix}_{n \times 1} =

\begin{pmatrix}
a_{11} & a_{12}& \dots &  a_{1m} \\
a_{21} & a_{22}& \dots &  a_{2m}\\
\vdots \\

a_{n1} & a_{n2}& \dots & a_{nm}
\end{pmatrix}_{n \times m}
 \begin{pmatrix}
w_1 \\
w_2 \\
\vdots \\
w_m\\
\end{pmatrix}_{m \times 1}
$$


The ordering is important because it tells us the exact position of each coefficient.



## Context of the Course (Assumptions)

Going forward, we will work with the following <u>context:</u>

1. <u>Field:</u> $\mathbb{K} = \R$ (occasionally $\C$)
2. <u>Vector Space:</u> $V = \R^n$ (occasionally $\C^n$) where our vectors are <u>**columns**</u>, we will use $v^T$ to define a <u>**row vector**</u>
3. <u>Inner Product:</u> 
   - $<u,v> = u^Tv \text{ in } \R^n $
   - $<u,v> = u^Hv = \bar u^T v \text{ in } \C^n$



## Theorems (Topics) to Be Covered

1. Orthogonalization
2. Linear Least Squares
3. The Singular Value Decomposition
4. Linear Equations
5. Eigenvalue Problems



# Topic 1: Orthogonalization

## Orthogonal set and orthonormal

- Two vectors $u,v \in \R^n$ are orthogonal <u>iff</u> $u^Tv = 0$

- in extend: vectors $v_1....v_n$ forms an ==orthogonal set== <u>if (no longer if and only if):</u>
  $$
  v_i^T v_j = 
  \left \{ 
  \begin{aligned}
  ||v_i||^2 > 0, i = j\\
  0, i\neq j \\ 
  \end{aligned}
  
  \right.
  $$
  
- 



**==Note:==** in textbooks, it is assumed that when we talk about an orthogonal set of vectors, we exclude the zero vector.

Also, the set $\{v_1,....v_n\}$ is ==orthonormal== if (special case of orthogonal set): 
$$
v_i^T v_j = \left \{ \matrix{1, i = j \\ 0, i \neq j}\right.
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
= \left [
\matrix {1 & 0 & ... & 0 \\ 0 & 1 & ... & 0 \\ \vdots & &\ddots \\ 0 & ... & & 1}
\right ]

= I_n
$$





## Packaging Orthogonal/Orthonormal Matrix

> - We can encode orthogonality and orthonormality by packaging a (finite) collection of orthogonal or orthonormal vectors in to a matrix.
>
>   This way we compress the represtation and simplify the notation. This way we can derive and then use the properties of matrices.

### Example

If $v_1,...v_k \in \R^n$ are orthognal, we can write $A := \left [
\matrix 
{
v_1 &  ... & v_k
}
\right ] $, and orthogonality is expressed as:
$$
A^T A = \left [
\matrix 
{
v_1^T
\\
\vdots
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


Similarly, if $q_1,...q_k \in \R^n$ are orthonormal. Letting $Q := [q_1, ... q_k]$ (with shape $n \times k$), orthonormality is expressed as $Q^TQ = I_{k\times k}$ ($k \times n \cdot n\times k = k\times k$)

- Note: $Q^TQ = I \centernot\implies QQ^T = I$, The implicication only holds for $k = n$ (square matrix)

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

1. ==For $k = n$ (square matrix),== if $Q$ has <u>orthonormal</u> columns, it is called an <u>orthogonal</u> matrix
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



Therefore (plug in the new $\alpha, \beta$ coefficients), the ==Orthogonal Projection of $u$ onto $v$ is:==
$$
Proj_v(u) = \sum_{j=1}^n \frac{v_j^Tu}{v_j^Tv_j} v_j = \sum_{j=1}^n(q_j^Tu)q_j
$$

Here, $\frac{v_j^Tu}{v_j^Tv_j}$ is the projection coefficient of $u$ onto $v_j$

and $q_j^Tu$ is the projection coefficient of $u$ onto $q_j$

---



We think a little bit deeper about these expressions.

Let $u,v \in \R^n$, The orthogonal projection of $u$ onto $v$, geometrically, is a vector $\alpha v$ s.t. 

- ==$ u - \alpha v \perp v$== , where $ u - \alpha v = Proj_v(u)$

![image-20230123234548730](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230123234548730.png)

i.e. $v^T (u-\alpha v) = 0$

solving for $\alpha$ gives $v^Tu = \alpha v^Tv \implies  \alpha = \frac{v^Tu}{v^Tv}$

This is why in expressing $u$ in orthogonal bases or orthonormal bases uses these expressions, which are interpreted as <u>coefficients of orthogonal projections</u>





### 2nd Interpretation: Linear Map (orthogonal projector)

Let’s interprete the object
$$
\frac{v^Tu}{v^Tv} v
$$
There are ==two ways== to express it and think about it. The first one we just saw.

The second is as a ==**linear map**== applied to this vector $u$. To see that, we rewrite as
$$
\frac{v^Tu}{v^Tv}v = v\frac{v^Tu}{v^Tv}  = \frac{vv^T}{v^Tv} u
$$

- Note that $\frac{v^Tu}{v^Tv}$ is a scalar, thus we can move it after $v$
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
Proj_v(u) = \sum_{j=1}^n \frac{v_j^Tu}{v_j^Tv_j} v_j = \sum_{j=1}^n(q_j^Tu)q_j
$$


Where $\frac{v_j^Tu}{v_j^Tv_j}$ and $q_j^Tu$ are the ==orthogonal projection coefficients== onto $v_j$ and $q_j$ respectively

And also, the coefficients of the linear combination representing $u$ in bases $[v_1, ...v_n]$ and $[q_1,...q_n]$

These projections can be interpreted as “calibrated (校准的)” scalars and they can alternatively by interpreted as “calibrated” linear mappings applied to $u$.

- <u>e.g</u> $(q_i^Tu)q_i =q_i(q_i^Tu) =(q_iq_i^T)u$, where $q_iq^T$ is a $n \times n$ matrix

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

$(q_1q_1^T + q_2q_2^T)$ is the **orthogonal projector** because $r := u - (q_1q_1^T + q_2q_2^T)u \perp span\{q_1,q_2\}$

- **<u>Note:</u>** ==r, the residual,== is the dashed line that’s perpenticular to the plane formed by $span\{q_1,q_2\}$
- $q_1q_1^T + q_2q_2^T$, in this case, is the **orthogonal projector** of $u$ onto $span\{q_1,q_2\}$

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
\right ]$

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

We will <u>assume</u> that $a_1,...,a_n$ are <u>**linearly independent**</u>. This is to ensure that orthogonalization algorithms run to completion. In practice, we do not know a prior if $a_1,...,a_n$ are independent but we find out while running the algorithms and reaching a point of breakdown.



If you package $a_1,..a_n$ into a matrix as $A = \left [
\matrix 
{
a_1 & ... & a_n
}
\right ]$ another way to express the assumption of linear independence of the $a_j$ is to say that $A$ is <u>full column rank ($rank(A) = n$)</u>

- **Note:** A has shape $m \times n$, which is not necessarily *square matrix*



## Orthogonalization Methods (Overview)

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





## Classical Gram-Schemidt (CGS)

### Input & Output

- **<u>Input:</u>** $a_1,...,a_n \in \R^{m \times n}, n \leq m$. (Assume these are linearly independent)
- **<u>Output:</u>** $q_1,...,q_n \text{ is orthonormal } \in \R ^{m \times n}$ s.t:
  - $span\{q_1\} = span\{a_1\}$
  - $span\{q_1,q_2\} = span\{a_1,a_2\}$
  - ….
  - $span\{q_1,...,q_n\} = span\{a_1,...,a_n\}$

### Algorithm (normalizing in the end)

$$
v_1 = a_1
\\ v_2 = a_2 - \frac{v_1^Ta_2}{v^T_1v_1}v_1 \text{ (the projection of a2 onto v1)}
\\ v_3 = a_3 - \frac{v_1^Ta_3}{v^T_1v_1}v_1 - \frac{v_2^Ta_3}{v^T_2v_2}v_2
\\ \vdots
\\ v_n = a_n - \frac{v_1^Ta_n}{v^T_1v_1}v_1 - .....\frac{v_{n-1}^Ta_n}{v^T_{n-1}v_{n-1}}v_{n-1}
$$

Removing the orthogonal projections of $a_3$ onto $v_1,v_2$ sequentially gives ==$v_3 \perp v_1 \&v_2$==

- This works only because $v_1,v_2$ are already orthogonal
  - One can indeed test it by finding whether:
    - $v_1^Tv_3 = 0$
    - $v_2^Tv_3=0$
  
  - Both of them need to be 0, indicating that $v_3$ is orthogonal to $v_1$ and $v_2$ at the same time
  
- *Proof* will be part of `Assignment 2`



We can then <u>**normalize**</u> by defining:
$$
q_1 = \frac{v_1}{\pm ||v_1||}, q_2 = \frac{v_2}{\pm ||v_2||}, ... q_n = \frac{v_n}{\pm ||v_n||}
$$
It is generally preferable to normalize as you go (rather than doing all normalization in the end) to keep the sizes of intermediary vectors bounded. **<u>This prevents potential numerical issues.</u>**



### Algorithm (normalizing after each step)

$$
v_1 = a_1, q_1 = \frac {v_1}{||v_1||}, \text{ choose + sign for || || }
\\ v_2 = a_2 - (q_1^Ta_2)q_1, q_2 = \frac {v_2}{||v_2||}
\\ ...
\\ v_n = a_n - (q_1^Ta_n)q_1 - ... (q_{n-1}^Ta_n)q_{n-1}, q_{n} = \frac {v_{n}}{||v_{n}||}
$$

Reorganizing the equations of the 2nd version of CGS (normalizing after each step), we can write:
$$
a_1 = v_1 = ||v_1||q_1 
\\ a_2 = (q_1^Ta_2)q_1 + v_2 =  (q_1^Ta_2)q_1 + ||v_2|| q_2
\\ ...
\\ a_n = (q_1^Ta_n)q_1 + (q_2^Ta_n)q_2 + .... + (q_{n-1}^Ta_n)q_{n-1} + ||v_n||q_n
$$
These are the same relations written in a way as to emphasize how the original vectors $a_1,....,a_n$ can be expressed as linear combinations of the $q_1,...q_n$. We can package these relations into a matrix product as follows:



![image-20230130181818804](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230130181818804.png)

- regular matrix multiplication, but interpreted differently: column $a_1$ is the result of linear combination of $q_1$ and the first column of $R$ ($a_1 = q_1 ||v_1||$)  



### Definition: QR decomposition

The CGS relations packaged in this way defines the <u>**QR**</u> decomposition of $A$.



### Questions: Is QR decomposition unique?

- No, because when normalizing $q_j$ values, we ==may select + or - sign== to define $q_j$ as $\pm ||v_j||$. However we will see shortly that if you fix the signs, the decomposition becomes unique.



### Theorem: Existence and Uniqueness of the reduced QR decomposition

Given a matrix $A \in \R^{m \times n}, $ full column rank (same as: linearly independent columns).

$\exists Q \in \R^{m \times n}$ with orthonormal columns and $R \in \R ^{n \times n}$ upper $\triangle$ s.t. $A = QR$

also written as:
$$
\left [
\matrix 
{
a_1 & ... & a_n
}
\right ]

=

\left [
\matrix 
{
q_1 & ... & q_n
}
\right ]

\left [
\matrix 
{
r_{11} & r_{12}  & ... & r_{1n}
\\
  & r_{21} & ... & r_{2n}
\\
&  & \ddots
\\ 
& & & r_{nn}
}
\right ]
$$
**<u>Moreover if we fix the signs of $r_{jj}$ to be positive (or other fixed specific patterns), then Q and R became unique.</u>**

- see proof below

  

### Proof: Existence and Uniqueness of the reduced QR decomposition

We already showed existence by construction by CGS iterator. For uniqueness, step-through the iteration backwards, i.e. starting from QR and realize that each step recovers the quantities in CGS. Use induction:

Given:
$$
\left [
\matrix 
{
a_1 & ... & a_n
}
\right ]

=

\left [
\matrix 
{
q_1 & ... & q_n
}
\right ]

\left [
\matrix 
{
r_{11} & r_{12}  & ... & r_{1n}
\\
  & r_{21} & ... & r_{2n}
\\
&  & \ddots
\\ 
& & & r_{nn}
}
\right ]
$$
<u>**Step 1:**</u> ==$a_1 = r_{11}q_1$== 

==Note: $r_{11}$ can not be 0 because the matrix A has its columns linearly independent==

Apply constraints (take norm on both sides). Firstly $||a_1||= r_{11} ||q_1||$

- we know that $q_i$ is orthonormal (the output), thus $||q_1|| = 1, ||a_1|| = r_{11}$ ($a_1$ is input, so we know now that $r_{11}$ is fixed)
- Then, $q_1 = \frac{a_1}{r_{11}}$ is also unique since we just fixed $r_{11}$ to be unique



**<u>Step 2:</u>** ==$a_2 = r_{12}q_1 + r_{22}q_2$== 

Where:

- $q_1$ is determined from **<u>Step 1</u>**
- $r_{12}, r_{22}, q_2$ remain as unknown

Since $q_1,....q_n$ is orthonormal, $q_1^Tq_2 = 0, q_1^Tq_1 = 1$, thus we can find $r_{12}$ through the following way:
$$
q_1^Ta_2 = r_{12}q_1^Tq_1 + r_{22}q_1^Tq_2 = r_{12}
$$
Therefore, we can fix ==$r_{12}$== 

Then, we need to find $r_{22}, q_2$:
$$
a_2 - r_{12}q_1 = r_{22} q_2
$$
Again, we take norms on each side, and we know $r_{22} > 0$ from linearly independence, we can fix ==$r_{22}$== 
$$
||a_2 - r_{12}q_1 ||= ||r_{22} q_2||
\\ ||a_2 - r_{12}q_1|| = r_{22} \to \text{ determined (unique)}
$$
Then we can ==fix $q_2$:==
$$
\frac{a_2 - r_{12}q_1}{r_{22}} = q_2 \to \text{ determined (unique)}
$$
Assume $q_1,...,q_{k-1}$ and their corresponding $r's$ are unique, <u>then at step k, we have:</u>

$$
a_k = r_{1k}q_1 + r_{2k}q_2 + r_{3k}q_3 + ... r_{(k-1)k}q_{k-1} + r_{kk}q_k
$$
Where the ==$r$ values== are fixed as follows:

- $r_{1k} = q_1^Ta_k \to$ unique

- $r_{2k} = q_2^Ta_k \to$ unique
- …..

- $r_{(k-1)k} = q_{k-1}^Ta_k \to$ unique



<u>Finally, we can take norm similarly as above:</u>
$$
a_k - r_{1k}q_1 - ... - r_{k-1}q_{k-1} = r_{kk}q_k
\\ ||a_k - r_{1k}q_1 - ... - r_{k-1}q_{k-1} || = || r_{kk}q_k||
\\ ||a_k - r_{1k}q_1 - ... - r_{k-1}q_{k-1} || = r_{kk} \to \text {determined (unique)}
\\ \text{ Also, we can determin uniquness of }q_k
\\ q_k = \frac{a_k - r_{1k}q_1 - ... - r_{k-1}q_{k-1}}{r_{kk}} \to \text{determined (unique)}
$$
- For simplicity, we denote: $a_k - r_{1k}q_1 - ... - r_{k-1}q_{k-1} =  *$

Taking norms shows that $|| * || = r_{kk} \to $ unique

Then $q_k = \frac {*} {r_{kk}} \to$ unique

==<u>**This completes the uniqueness proof.**</u>==



### Numerical Problem with CGS (Why we need MGS)

If $q_1,...q_k$ are computed via CGS in the presence of rounding errors, they are generally not perfectly orthogonal to each other. As a consequence, when computing the thrid vector $q_3$ as:
$$
||v_3|| q_3 = v_3 = a_3 - (q_1^Ta_3)q_1 - (q_2^Ta_3)q_2
$$

- ==$a_3 - (q_1^Ta_3)q_1$:== This will not perfectly remove components of $q_1$ from $a_3$ due to rounding error.
- ==$(q_2^Ta_3)q_2$:== Moreover, since $q_2$ is also not perfectly orthogonal to $q_1$, it also adds a component of $q_1$ into the computation of $v_j$ and $q_j$

Thus, as you expand the iterator:
$$
||v_k||q_k = v_k = a_k - (q_1^Ta_k)q_1 - (q_2^Ta_k)q_2 - ...- (q_{k-1}^Ta_k)q_{k-1}
$$

- ==$a_k - (q_1^Ta_k)q_1$==: inperfect so up to there you still have a small $\triangle_1q_1$ in the result
-  ==$(q_2^Ta_k)q_2$:==  since $q_2$ is imperfectly orthogonal to $q_1$, by further minusing this term, adds another $\triangle_2q_1$
- ==$(q_{k-1}^Ta_k)q_{k-1}$:== since $q_{k-1}$ is inperfectly orthogonal to $q_1$, by further minusing this term, this adds another $\triangle_{k-1}q_1$

So $v_k$ will contain all terms ==$\triangle_1q_1 + \triangle_2q_1 + .. + \triangle_{k-1}q_1$== in the direction of $q_i$ illustrating that the larger $k$, the more you expect $q_1$ to <u>“lose”</u> orthogonality against $q_k$.

You would be lucky and have these $\triangle's$ cancel out but you generally <u>“lose trust”</u> and lose control over the orthogonality when you run `CGS` for a long time.

To slow down the loss of orthogonality of earlier vectors against later vectors, we apply the **==Modified Gram-Schemidt (MGS)==** method, which is mathematically equivalent to `CGS` but numerically preferable.

- **==Note:==** this is the method of choice for long-skinny matrices ==$n << m$== in $\R^{m \times n}$





## Modified Gram-Schemidt (MGS)

- It is more obvious to learn it through [comparison](#Comparing CGS and MGS)



## Comparing CGS and MGS

### MGS

$$
v_1 = a_1, q_1 = \frac {v_1}{||v_1||}
\\ v_2 = a_2 - (q_1^Ta_2)q_1, q_2 = \frac {v_2}{||v_2||}
\\ \text{so far, the first 2 steps are same as CGS...} 
$$

- Add additional orthogonalization by not asuuming $q_1, q_2$ orthogonal (without doing more operations)

$$
v_3^{(0)} = a_3
\\ v_3^{(1)} = a_3 - (q_1^Ta_3)q_1
\\ v_3 = v_3^{(2)} = v_3^{(1)} - (q_2^Tv_3^{(1)})q_2
$$

- The whole chunk above is <u>**Step 3**</u>
- In the extra operations, we remove the projection of $q_2$ from the whole package $v_3^{(1)}$



#### Step k in MGS

$$
v_k^{(0)} = a_k
\\v_k^{(1)} = v_k^{(0)} - (q_1^Tv_k^{(0)})q_1 
\\ v_k^{(2)} = v_k^{(1)} - (q_2^Tv_k^{(1)})q_2 
\\ \vdots
\\ v_k = v_k^{(k-1)} = v_k^{(k-2)} - (q_{k-1}^Tv_k^{(k-2)})q_{k-1}
$$



### CGS

$$
v_1 = a_1, q_1 = \frac {v_1}{||v_1||}
\\ v_2 = a_2 - (q_1^Ta_2)q_1, q_2 = \frac {v_2}{||v_2||}
$$

- The third step starts to differ from `MGS`

$$
\\ v_3 = a_3 - (q_1^Ta_3)q_1- (q_2^Ta_3)q_2, q_3 = \frac{v_3}{||v_3||}
$$

​	Where the mathematically equivalent terms between `MGS` and `CGS` are:

- $a_3 (CGS) = v_3^{(0)} (MGS)$
- $a_3 - (q_1^Ta_3)q_1 (CGS) = v_3^{(1)}(MGS) $



#### Step k in CGS

$$
v_k = a_k - (q_1^Ta_k)q_1 - ... (q_{k-1}^Ta_k)q_{k-1}
$$

- **==Note:==** `MGS` has the same number of iterations in practice as `CGS` since to compte the step k in `CGS`, you still need an iterative procedure similar to the $k^{th}$ step in `MGS`. But the advantage of `MGS` is that you <u>**slow down the loss of orthogonality between vectors.**</u>



## Def: Full QR Decomposition

> - So far, we have dicussed the <u>reduced</u> QR decomposition, now let’s talk about <u>full</u> QR decomposition

Given $A = [a_1 .... a_n] \in \R^{m \times n}, n\leq m$, full column rank.

The full <u>QR</u> decomposition $A =\bar Q \bar R$ is the extension of the reduced QR decompose as follows:

![image-20230131191114805](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230131191114805.png)

Where $q_{n+1}^c,...q_m^c$ extend $q_1,...q_n$ to a basis for $\R^m$

- **==Note:==**

  You can just write $A = QR + Q^cO$ where the full QR decomposition has two main uses:

  1. It contains not only an orthonormal basis for $span\{a_1, ...a_n\}$ but also an orthonormal basis for the orthogonal complement of this space
  2. Some algorithms such as `Given’s` and `Householders` are incapable of constructing the reduced QR decomposition, but only the full QR. 
     - **==Note:==** $q_{n+(\cdot)}^c, ....q_m^c$ are not unique



## Before Givens Method: Recall Orthogonal Matrices Properties

Last time, we conpleted discussion about the QR decomposition via `CGS` and `MGS` and we extended the decomposition to <u>full QR</u>

The `CGS` and `MGS` construct the (reduced) $QR$ decomposition by focusing on constructing $Q$ and obtaining $R$ as a by-product. The next two methods focus on taking $A$ and applying orthogonal transformations to it until obtaining a matrix $R$ as defined in the $QR$ decomposition, and generating the orthogonal matrix $Q$ as a by-product.

Moreover, these methods produce the full $QR$ decomposition of $A$ where $Q = [q_1,...,q_n,q_{n+1},...q_m]$ in which $q_1,...q_n$ form an orthonormal basis for $span\{a_1,...a_n\}$ (column space of $A$) and $q_{n+1},...,q_m$ is an orthonormal basis for the orthogonal complement of that space (column space of $A$).





### Theorems: properties of orthogonal matrices

let $Q, Q_1,Q_2 \in \R^{m \times m}$ be orthogonal (i.e. $Q^TQ = QQ^T=I$)

1. $Q$ preserves inner products and the corresponding norms, distances and angles.
   - e.g: $<Qu,Qv> = (Qu)^T \cdot (Qv)= u^TQ^TQv = u^Tv = <u,v>$
2. $det(Q) = \pm 1$
3. $Q_1$ and $Q_2$ orthogonal $\implies Q_1Q_2$ is orthogonal
4. $Q^{-1}$ is orthogonal





### Proofs of Theorems Above

1. We did it before.

2. $$
   1 = det(I) = det(Q^TQ) = det(Q^T)det(Q) = det(Q)^2  
   \\\implies det(Q) = \pm1
   $$


3. By rerification: $(Q_1Q_2)^T(Q_1Q_2) = Q_2^TQ_1^TQ_1Q_2 = I$

   And since they are square, the same holds if you commute the product (switch order of $Q_1,Q_2$)

1. 
2. 

4. $(Q^{-1})^TQ^{-1} =(Q^{-1})^TQ^T = (QQ^{-1})^T = I$
   1. Recall 1: Since $Q$ is orthogonal matrix, we have $Q^{-1} = Q^T$
   2. Recall 2: Since $Q$ is orthogonal matrix, thus it implies that it’s square matrix. For any square matrix $A$, we have $AA^{-1} = I$



Geometrically orthogonal matrices represent rigid motion (as defiend by preservation of Inner Product, norm, distances and angles)

There are two kinds of motions which preserve these quantities.

1. The <u>rotation</u> “moves” all vectors except $\vec 0$, no invariant vector. <u>Rotation</u> corresponds to the case $det(Q) = + 1$ `(Givens Matrix)`
2. The <u>reflection</u> has an invariant subspace (we will see an example when constructing $QR$ using `Householder`). <u>Reflection</u> corresponds to the case $det(Q) = -1$





## Givens Matrices (Rotation)

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



### Example of Action

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



### Problem

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
- $s = sin\theta = \frac{-y}r$ (picking negative sign so that we have the rotation goes clockwise on picture, to map the basis vector to matrix $A$, the nature of `Givens` matrix is to rotate the basis vector $\left ( 
  \matrix 
  {
  1
  \\
  0
  }
  \right )$ )

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

### Abstract Example

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



### Detailed Example*

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



#### Result

This gives $A = \widetilde {Q}  \widetilde {R} = QR$, where:

- $\widetilde {Q} = G_1G_2G_3 =$ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213010031273.png" alt="image-20230213010031273" style="zoom:25%;" />

- $ \widetilde {Q} \widetilde {R}$ is the full QR decomposition
- $QR$ is the reduced QR decomposition

We can rewrite: $A = \widetilde{Q}\widetilde{R} = (Q \; Q^c) \left(\matrix {R \\0} \right) = QR$ 

#### Givens QR Algorithm Operation Pattern

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
	R(j,j) = sqrt(v' * v); # L2 norm
	Q(1:m, j) = v/R(j,j);
end
```



## Householder Matrices (Reflection)

Like Givens, these are structured, special-case matrices which play a key role in many matrix algorithms: $QR$ decomposition, Single Value Decomposition and Eigen Value Decomposition.

We first define them as a stand-alone topic, explore some of their properties and then see how to use them to construct the $QR$ decomposition.



### Def: Householder reflector matrices

Given $v \in \R^m, v \neq 0,$ the `Householder` matrix corresponding to $v$ is defined by:
$$
H_v = I_m - \frac {2vv^T} {v^Tv}
$$
or if we normalize $v$ as $q = \frac v {||v||}$, this becomes: $I_m - 2qq^T$ (the normalized form will be used seldomly)

- *<u>Interesting observation:</u>* $(I_m - qq^T)u = u - qq^Tu$, which is the projection of $u$



### Actions of Householder Matrices

Let’s explore the action of this matrix on vectors in $\R^m$. Complete $v$ to an ==orthogonal basis== $\{v, v_2....v_m\}$ for $\R^m$ and consider the action of $H_v$ on the following <u>3 cases</u>:

1. Action on $v$

   - $H_vv=v -  \frac {2v(v^Tv)} {v^Tv} = -v$

2. Action on $v_2,...v_m$ 

   - $H_vv_j = v_j - \frac {2v(v^Tv_j)} {v^Tv} = v_j - 0 = v_j$ (orthogonal basis property)
   - ==Note: $span\{v_2,..v_m\} =v^\perp$==, orthogonal complement, **a subspace of vectors where all of the vectors in it are orthogonal to all of the vectors in a particular subspace**

3. Action on a general vector in $\R^m$

   - Consider $u \in \R^m$ to be arbitrary, write: $u = \alpha v + \alpha_2 v_2 + .. \alpha_m v_m$

   - $H_v u= H_v \alpha v + H_v(\alpha_2 v_2 + .. \alpha_m v_m)=-\alpha v + \alpha_2 v_2 + .. \alpha_m v_m$ (a combined result from `Action 1` and `Action 2`)

   - Geometrically, $H_v$ acts as a reflection across the subspace $span\{v_2,...v_m\} = v^\perp$

     <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213180859669.png" alt="image-20230213180859669" style="zoom:50%;" />

     where $\tilde v = \alpha_2 v_2 + .. \alpha_m v_m$



### Properties of $H_v$ (thm)

1. $H_v$ is an orthogonal matrix

2. $H_v$ is symmetric ($H_v^T = H_v$)

3. $(H_v)^2 = I_m$ (reflection applied twice is the identity)

4. The eigenvalues of $H_v$ are:

   1. $\lambda =-1$ with algebraic & geometic multiplicity 1
   2. $\lambda =1$ with algebraic & geometic multiplicity $m-1$

5. $det(H_v) = -1$

6. If $H_v$ is a `Householder` matrix with vector $v$, then taking taking 

   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213182605002.png" alt="image-20230213182605002" style="zoom:50%;" />

   produces the new `Householder` matrix:
   $$
   H_{\tilde v} = 
   \left [
   \matrix {I_k & 0^T_{k\times n} \\ 0_{n\times k} & H_v }
   \right ]
   $$
   where $0_{n\times k}, 0^T_{k\times n}$ are zero blocks

   

### QR Decomposition using Householder matrices

<u>**Idea:**</u> similar to `Givens`, taking $A \in \R^{m \times m}, m \geq n,$ full column rank and applying `Householder` matrices on the left.

- $\widetilde R= \left [
  \matrix {R \\ 0}
  \right ] = H_{v_n}H_{v_{n-1}}....H_{v_1}A $
- and then use $ \widetilde Q = [Q, Q^c] = H_{v_1} ... H_{v_n}$
- knowing the fact that: $H_{v_j}^{-1} = H_{v_j}$



To see this, start with a single vector $\left ( 
\matrix {u_1 \\ \vdots \\u_m}
\right )$, and find $v \in \R^m $ s.t $H_vu = \left ( 
\matrix {r \\ 0 \\ \vdots \\0}
\right ) = re_1$, which satisfying all the Euclidean weight into the first entry. Remember, this means we are not changing the 2-norm of the vector because $H_v$

is an orthogonal matrix.



==**Note:**==

- If $u$ already is $\left ( 
  \matrix {r \\ 0 \\ \vdots \\0}
  \right )$, then do nothing i.e) $I$ operation. To construct a proper `Householder` matrix, we are assuming $u \neq \left ( 
  \matrix {r \\ 0 \\ \vdots \\0}
  \right )$

![image-20230214171519381](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214171519381.png)

Take ==$v = u - ||u||e_1$== (taking $r = ||u||$ since we don’t want to change the norm, so that the reflected vector has same length as the mapped one)

To see this $v$ actually works, verify formally:

<u>We have:</u>
$$
H_v = I -  \frac {2vv^T} {v^Tv}
\\ H_v u = u - \frac {2v(v^Tu)} {v^Tv}
\\ = u - \frac {2(u - ||u||e_1)((u^T - ||u||e_1^T)u)} {(u^T - ||u||e_1^T)(u - ||u||e_1)}
\\ = u - \frac {2(u - ||u||e_1)(u^Tu - ||u||e_1^Tu)} {u^Tu - ||u||u^Te_1 -||u||e_1^Tu + ||u||^2}
\\ = u - \frac {2(u - ||u||e_1)(u^Tu - ||u||e_1^Tu)} {2||u||^2 - 2||u||e_1^Tu}
\\ = u - u + ||u||e_1
\\ = ||u||e_1 \text{ which is the target result we want}
$$
**==Note:==** the denominator is non-zero ($2||u||^2 - 2||u||e_1^Tu \neq 0$) because $||u||^2 = ||u||e_1^Tu$ implies $||u|| = e_1^Tu$

which can only occur if $u = \left ( 
\matrix {||u|| \\ 0 \\ \vdots \\0}
\right )$ which we handled separately.



The above calculation means that with $v = u - ||u||e_1$ (assuming $u$ is not already in the form $\left ( 
\matrix {r \\ 0 \\ \vdots \\0}
\right )$), the `Householder` matrix $H_v$ maps the vector $u$ to the vector $\left ( 
\matrix {r \\ 0 \\ \vdots \\0}
\right ) = \left ( 
\matrix {||u|| \\ 0 \\ \vdots \\0}
\right )$



### Schematic Example

$A = \left ( 
\matrix {a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \\ a_{41} & a_{42} & a_{43}}
\right )$, assume full column rank

- The first operation shifts all weights from $a_{21} , a_{31},  a_{41}$ to $a_{11}$

**==Note: The change is applied on each column, not just on the one that we focus on, just the one we focus on turn into 0’s, the others do not==**



**<u>Step 1:</u>**

- we focus on <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214180748796.png" alt="image-20230214180748796" style="zoom:50%;" /> 

Take $u = \left ( 
\matrix {a_{11}  \\ a_{21}  \\ a_{31}  \\ a_{41} }
\right )$ and let $v_1 = u - ||u||e_1$. This generates a `Householder` matrix: $H_{v_1} = I_4 - \frac{2v_1v_1^T}{v_1^Tv_1}$

$A_1 = H_{v_1}A = \left ( 
\matrix {a_{11}^{(1)} & a_{12}^{(1)} & a_{13}^{(1)} \\ 0 & a_{22}^{(1)} & a_{23}^{(1)} \\ 0 & a_{32}^{(1)} & a_{33}^{(1)} \\ 0 & a_{42}^{(1)} & a_{43}^{(1)}}
\right )$

**<u>Step 2:</u>**

- we focus on <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214180838497.png" alt="image-20230214180838497" style="zoom:50%;" />

Take $u = \left ( 
\matrix {a_{22}^{(1)}  \\ a_{32}^{(1)}  \\ a_{42}^{(1)} }
\right ) $ and let $\bar v_2 = u - ||u||e_1,$ and take $v_2 = \left ( 
\matrix {0 \\ \bar v_2}
\right )$

$H_{v_2} = I_4 - \frac{2v_2v_2^T}{v_2^Tv_2} = \left ( 
\matrix {1  & 0^T\\ 0 & H_{\bar v_2}}
\right )$

Then $H_{v_2} A_1 = H_{v_2}H_{v_1}A = \left ( 
\matrix {a_{11}^{(2)} & a_{12}^{(2)} & a_{13}^{(2)} \\ 0 & a_{22}^{(2)} & a_{23}^{(2)} \\ 0 & 0 & a_{33}^{(2)} \\ 0 & 0 & a_{43}^{(2)}}
\right )$



**<u>Step 3:</u>**

- we focus on <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214180857184.png" alt="image-20230214180857184" style="zoom:50%;" />

Take $u = \left ( 
\matrix {a_{33}^{(2)} \\ a_{43}^{(2)}}
\right )$ and let $\bar v_3 = u - ||u|| e_1$ and $v_3 = \left ( 
\matrix {0 \\ 0\\ \bar v_3}
\right )$

Then $H_{v_3} = I_4 - \frac{2v_3v_3^T}{v_3^Tv_3} = $ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214180349947.png" alt="image-20230214180349947" style="zoom:33%;" />

with $H_{v_3}H_{v_2}H_{v_1}A = \left ( 
\matrix {a_{11}^{(3)} & a_{12}^{(3)} & a_{13}^{(3)} \\ 0 & a_{22}^{(3)} & a_{23}^{(3)} \\ 0 & 0 & a_{33}^{(3)} \\ 0 & 0 & 0}
\right ) = \left ( \matrix{R \\ 0} \right)$



then $\widetilde Q = [Q, Q^c] = H_{v_1}H_{v_2}H_{v_3}$

In $*$ notattion, `Householder` does this: <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214184324567.png" alt="image-20230214184324567" style="zoom:50%;" />



### Concrete Numeric Example

Start with $A = \left ( 
\matrix {1 & 1 \\ 0 & 2 \\ 1 & 2}
\right )$

**<u>Step 1:</u>** $u = \left ( 
\matrix {1 \\ 0 \\1}
\right )$, with $v = u - ||u||e_1 = \left ( 
\matrix {1 \\ 0 \\1}
\right ) - 1.414 \left ( 
\matrix {1 \\ 0 \\0}
\right ) = \left ( 
\matrix {-0.414 \\ 0 \\1}
\right )$

$H_{v_1} = I_3 - \frac{2v_1v_1^T}{v_1^Tv_1} = eye(3,3) - \frac{2v_1 *v_1'}{v_1' *v_1} = \left ( 
\matrix {0.7071 & 0 & 0.7071  \\ 0 & 1 & 0 \\ 0.7071 &0 &-0.7071 }
\right )$

Then $H_{v_1}A = \left ( 
\matrix {R \\ 0 }
\right ) = \left ( 
\matrix {1.414 & 2.121  \\ 0 & 2 \\ 0 &-0.7071 }
\right )$



**<u>Step 2:</u>**

Then take $u = \left ( 
\matrix { 2 \\-0.7071}
\right )$

<u>Mathmatical computation:</u>

- $\bar v_2 = u - ||u||e_1 = \left ( 
  \matrix {-0.121 \\ -0.7071}
  \right )$

- $v_2 = \left ( 
  \matrix {0 \\ \bar v_2}
  \right ) = \left ( 
  \matrix {0 \\-0.121 \\ -0.7071}
  \right )$

  

<u>Matlab code for computation:</u>

- $u = [2;-0.7071]$
- $v_2b = u - norm(u) *eye(2,1)$
- $v_2 (2:3,1) =v_2b $
  - which is same as first do $v_2 = zeros(3,1)$ and then $v_2(2:3,1) = v_2b$ 



then $H_{v_2} = eye(3,3) - 2(v_2 * v_2')/(v_2' * v_2) = I_3 - \frac{2v_2v_2^T}{v_2^Tv_2}= \left ( 
\matrix {1 & 0 & 0  \\ 0 & 0.9429 & -0.333 \\ 0 &-0.333 & -0.9429 }
\right )$



then $ \widetilde R = H_{v_2}H_{v_1}A = \left ( 
\matrix {R \\ 0 }
\right ) = \left ( 
\matrix {1.414 & 2.121  \\ 0 & 2.121 \\ 0 &0 }
\right )$

and $\widetilde Q = H_{v_1}H_{v_2} = $<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230214182253095.png" alt="image-20230214182253095" style="zoom:50%;" />



## High level Computation Notes of All Orthogonalization Methods

|                            | Givens QR                                                    | Householder QR                                               | MGS (CGS) QR                                                 |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Computational time (order) | $3mn^2-n^3$ flops                                            | $2mn^2-2n^3/3$ flops                                         | $2mn^2$ flops                                                |
| if $(m \approx n)$         | $2n^3$ flops + additional work needed to accumulate $\widetilde Q$ | $\frac {4n^3}3$ flops + additional work to accumulate $\widetilde Q$ | $2n^3$ flops and if explicitly gives $Q$ (not $\widetilde Q$) |

Generally, if $Q$ is not needed explicity, `Householder` and `Givens` do not accumulate it. In such a case, one also avoids constructing the `Givens` OR `Householder` matrices explicitly.

Instead, you can store the `Householder` and `Givens` matrices as procedures.

- <u>e.g 1)</u> Information stored in $v$ is enough to understand the action of the `Householder` matrix by writing a routine which applies this matrix on a vector. For example, you can write a function: `household(v,u)` and returns the value $u-2v(v^Tu)/v^Tv$
- <u>e.g 2)</u> Similarly, `Givens` contains a tiny piece of information $(c,s,i,j) \to$ 4 numbers only, so you could write `givens(c,s,i,j,u)` which applies a `Givens` rotation on $u$ without constructing $G$.

To apply `Householder` or `Givens` to full matrices, you could either write corresponding routines or use $GA = G[a_1,... a_n] = [Ga_1,Ga_2,...Ga_n]$ and similarly for `Householder`.



# Topic 2: Regression & Linear Least Squares

> - Linear Least Squares is a specific type of regression

## Def: Regression

==<u>**Regression**</u>== refers to the collection of techniques for describing (capturing) dependencies between different data sets using “simple” functional relationship. We do this by specifying the functional relationship as:
$$
y = f_\lambda (x) + r
$$

- <u>Note:</u> sometimes, we denote $r$ as $\epsilon$

where:

- ==$f$== is the functional relationship
- ==$r$== is some kind of noise factor or secondary order effects not captured by the functional relationship
- ==$\lambda$==: we use $\lambda$ in $f_\lambda$ to emphasize that when defining the functional form, we use <u>**a family of functions**</u> to describe the model. Then we convert the regression model to an optimization problem over the parameter space defined by $\lambda$. We then solve the optimization problem to find  the specific functions (within the family) which <u>“best”</u> fits into the data we have at hand.
  - but what does <u>“best”</u> mean in here? $\to$ Here, <u>“best”</u> means that you have a measure of closeness between function and data, usually expressd as a norm on **<u>==r==</u>**. In otherwords, we are minimizing the residual in a given norm.

In the context of linear algebra, we usually take our functional form to be a linear combination of vectors. This appears restrictive, however many non-linear problems can be reduced to linear problems by increasing the dimension of the independent variable space (example will be given shortly)



## Linear Least Squares Regression

> - LLSP: Linear Least Squares Problem

### Definition

Given $y \in \R^m, v_1,...v_n \in \R^m, m \geq n$,

-  **==Side Note:==** $m = n$ means that the data can be fully captured by the relationship with the residual $r = 0$

find $\alpha = \left [
\matrix {\alpha_1 \\ \vdots \\ \alpha_n}
\right ] \in \R^n$ ($\alpha \neq \lambda$ showed before) such that $y \approx \alpha_1v_1 + \dots + \alpha_nv_n$

<u>**Formally, LLSP is:**</u>
$$
\min\limits_{\alpha \in \R^n\text{ (param space)}} ||y- A \alpha||_2
\\ \text{where: }
 A = [v_1, ... v_n], \alpha = \left [
\matrix {\alpha_1 \\ \vdots \\ \alpha_n}
\right ] \in \R^n
$$
The overwhelming majority of all regressions are $LLS$ regressions because:

1. Simple to formulate
2. Simple to solve
3. Many more sophisticated models do not perform much better



### Schematic Example

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230220181546270.png" alt="image-20230220181546270" style="zoom: 50%;" />

Suppose in the picture above, you <u>believe</u> that this relationship is captured by a quadratic dependency. Then you model it as a parabola by stating:
$$
y = \alpha_0 + \alpha_1x + \alpha_2x^2 + r
$$
In vector form, we can write:
$$
\left ( 
\matrix {y_1 \\ \vdots \\y_m}
\right )
=
\alpha_0
\left ( 
\matrix {1 \\ \vdots \\1}
\right )

+
\alpha_1
\left ( 
\matrix {x_1 \\ \vdots \\x_m}
\right )

+
\alpha_2
\left ( 
\matrix {x_1^2 \\ \vdots \\x_m^2}
\right )

+
\left ( 
\matrix {r_1 \\ \vdots \\r_m}
\right )
$$

- where $y, x \in \R^m$



We can also write in matrix-vector form:
$$
y =A \alpha + r
\\ \text{where: } A = \left ( 
\matrix {1 & x_1 & x_1^2 \\ \vdots & \vdots & \vdots \\1 & x_m & x_m^2}
\right )
, \alpha = \left ( 
\matrix {\alpha_0 \\ \alpha_1 \\\alpha_2}
\right )
$$
And: $v_1 = \left ( 
\matrix {1 \\ \vdots \\1}
\right )$, $v_2 = \left ( 
\matrix {x_1 \\ \vdots \\x_m}
\right )$, $v_3 = \left ( 
\matrix {x_1^2 \\ \vdots \\x_m^2}
\right )$​

To solve, find $\min\limits_{\alpha \in \R^3} || y - A\alpha||_2$



### Existence and Uniquness of LLSP

#### Existence

The set $A \alpha , \alpha \in \R^n$ defines a subspace spanned by the column of $A$, and the problem $\min\limits_{\alpha \in \R^3} || y - A\alpha||_2$ has a minimum defined by the projection of $y$ onto that space. `(A2Q1)`



#### Uniqueness

1. If $A$ is full-column rank, then the columns of $A$ form a basis for $colspace(A)$ so the $proj_{colspace(A)} (y)$ is written uniquely in that basis.
2. If $A$ is not full-column rank (i.e. have redundancy from basis point of view in the columns of $A$), then $proj_{colspace(A)} (y)$ can be written in infinitely many ways (i.e. infinitely many $\alpha$‘s achieve that projection)

### Approches to Solve LLSP 

**<u>Recall LLSP:</u>**
$$
\min\limits_{\alpha \in \R^n} ||y- A \alpha||_2
\\ \text{where: }
 A = [v_1, ... v_n] \in \R^{m \times n}, m \geq n 
\\ 
\alpha = \left [
\matrix {\alpha_1 \\ \vdots \\ \alpha_n}
\right ] \in \R^n

,y = \left [
\matrix {y_1 \\ \vdots \\ y_m}
\right ] \in \R^m
$$
This is the $LLS$ Regression expressed as a minimization problem.

Let’s look at techniques for solving this:

#### First Approach: Normal Equation

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230221175457251.png" alt="image-20230221175457251" style="zoom:50%;" />

Use the fact that $r \perp W = colspace(A)$. This is expressed by saying that for every basis vector $v$ of $W$, $r \perp v, v^Tr = 0$. $||r||$ will be minimum since it’s the residual from $y$ to $colspace(A)$ 

For the full column rank matrix $A$, the columns of $A$ are a basis so we express this orthogonality condition as:
$$
\left .
\matrix{
v_1^T r = 0\\

v_2^T r = 0\\
\vdots \\
v_n^T r = 0\\
}
\right\} \implies A^Tr = 0
$$
This is the basic idea of normal equation.



Replace $r$ by $y-A \alpha$ and rewrite as:
$$
0 = A^T(y-A \alpha) 
\\ 0 = A^Ty-A^TA \alpha
\\ A^TA\alpha = A^Ty
$$
==also known as the normal equations==

Such rewriting reduces the original minimization problem to a linear system with $A^TA$ <u>square</u>

- shape of $A^TA = n \times m \cdot m\times n \to n \times n$

**==Note:==**

- this theory of closest vector using Inner Product expressions and orthogonality only applies to the 2-norm, i.e. theone induced by the I.P.



Here since $A$ has rank $n$ (which is the condition of full column rank & the fact that $m \geq n$), then $A^TA$ is invertible 

- ==**Note:**== such magical logic inferrence will be proved in `A4` using `SVD`

Thus the solution to the $LLSP$ is: $\alpha = (A^TA)^{-1}(A^Ty)$



#### Second Approach: QR decomposition

This is a variant of the normal equations because we derive the solution using the same orthogonality condition, however instead of using the columns of $A$ as a basis for the subspace $W = \{A \alpha: \alpha \in \R^n\}$, we use the columns of $Q$ in the <u>**reduced**</u> $QR$ decomposition, again assuming that $A$ is full column rank.

Given: $A = QR$ (obtained through reduced QR decomposition)

we have:
$$
\begin{aligned}
0 &= Q^Tr 
\\ &= Q^T(y-A\alpha)
\\ &= Q^T(y-QR\alpha) \text{ Reduced QR decomposition}
\\&= Q^Ty-Q^TQR\alpha \text{ Note: }( Q^TQ = I \text{, identity n x n}\ )
\\ &= Q^Ty - R\alpha

\end{aligned}
$$
Then:
$$
R\alpha = Q^Ty
$$
This equation does not need matrix inversion to be solved because $R$ is upper triangular so the solution is found by backward substituition.



#### Third Approach: Singular Value Decomposition

- TO BE SEEN LATER!



### Comparing the 3 Approches

1. The normal equations work well when both following conditons hold:

   1. $m >> n$
   2. *condition number* of $A$ is small (close to 1)
      - *condition number:* to be defined later. For now, just know it’s the largest singular value over the smallest singular values

   when we have these 2 conditions, **<u>approach 1</u>** is good to use numerically & practically because it’s a simple approach

2. When both $m \;\& \;n$ are large, <u>**approch 2**</u> is a good method numerically, more precise than <u>**approch 1**</u>

   Both **<u>approch 1</u>** & **<u>approch 2</u>** require $A$ to be full column rank

3. **<u>approch 3</u>** is particularly good if $A$ is rank-deficient (不足的) (i.e. $rank(A) < n$)  or nearly so. There is one condition which we will make more precise later.





### Concrete Example

==<u>Question:</u>==

Experimental data produces the following table:

| $t_i$ | $y_i$ |
| ----- | ----- |
| 1.00  | 1.84  |
| 1.10  | 1.96  |
| 1.30  | 2.21  |
| 1.50  | 2.45  |
| 1.90  | 2.94  |

You believe that this is a quadratic $y \approx \alpha_0 + \alpha_1t + \alpha_2t^2$, and you wish to find which quadratic fits this data optimally on the Least Squares sense.



==<u>Solution:</u>==

write as $LLSP:$
$$
\left [
\matrix {
1.84 \\
 1.96 \\
 2.21 \\
 2.45 \\
 2.94 \\
}
\right ]
= \left [
\matrix {1 & 1 & 1 \\ 1 & 1.1 & 1.21 \\ 1 & 1.3 & 1.69 \\ 1 & 1.5 & 2.25 \\ 1 & 1.9 & 3.61}
\right ]

\left [
\matrix {
\alpha_0 \\
\alpha_1 \\
\alpha_2 \\

}
\right ]
$$

$$
\Updownarrow
\\y =A \alpha
$$



Let’s solve by QR decomposition (in exam, use the fastest possible approach)
$$
A =QR \text { (reduced) }
$$
$Q=$ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230221183732627.png" alt="image-20230221183732627" style="zoom:40%;" />

$R= $ <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230221183747447.png" alt="image-20230221183747447" style="zoom:40%;" />

Then solve $R\alpha = Q^Ty$ by backwards substitution (use Matlab) to get:

$\alpha = \left [
\matrix {0.6061 \\ 1.2387  \\ -0.0055}
\right ]$

==This completes the answer, the following statement is observation which is not part of the answer if not asked==

Here (without going to statistical testing), you can observe that $\alpha_2 \approx 0$ so that your assumption of quadratic is like inacurate & a linear interpolation.





