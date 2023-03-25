### Householder Matrices (Reflection)

Like Givens, these are structured, special-case matrices which play a key role in many matrix algorithms: $QR$ decomposition, Single Value Decomposition and Eigen Value Decomposition.

We first define them as a stand-alone topic, explore some of their properties and then see how to use them to construct the $QR$ decomposition.



#### Def: Householder reflector matrices

Given $v \in \R^m, v \neq 0,$ the `Householder` matrix corresponding to $v$ is defined by:
$$
H_v = I_m - \frac {2vv^T} {v^Tv}
$$
or if we normalize $v$ as $q = \frac v {||v||}$, this becomes: $I_m - 2qq^T$ (the normalized form will be used seldomly)

- *<u>Interesting observation:</u>* $(I_m - qq^T)u = u - qq^Tu$, which is the projection of $u$



#### Actions of Householder Matrices

Let’s explore the action of this matrix on vectors in $\R^m$. Complete $v$ to an ==orthogonal basis== $\{v, v_2....v_m\}$ for $\R^m$ and consider the action of $H_v$ on the following <u>3 cases</u>:

1. Action on $v$

   - $H_vv=v -  \frac {2v(v^Tv)} {v^Tv} = -v$

2. Action on $v_2,...v_m$ 

   - $H_vv_j = v_j - \frac {2v(v^Tv_j)} {v^Tv} = v_j - 0 = v_j$
   - ==Note: $span\{v_2,..v_m\} =v^\perp$==, orthogonal complement, **a subspace of vectors where all of the vectors in it are orthogonal to all of the vectors in a particular subspace**

3. Action on a general vector in $\R^m$

   - Consider $u \in \R^m$ to be arbitrary, write: $u = \alpha v + \alpha_2 v_2 + .. \alpha_m v_m$

   - $H_v u= H_v \alpha v + H_v(\alpha_2 v_2 + .. \alpha_m v_m)=-\alpha v + \alpha_2 v_2 + .. \alpha_m v_m$ (a combined result from `Action 1` and `Action 2`)

   - Geometrically, $H_v$ acts as a reflection across the subspace $span\{v_2,...v_m\} = v^\perp$

     <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230213180859669.png" alt="image-20230213180859669" style="zoom:50%;" />

     where $\tilde v = \alpha_2 v_2 + .. \alpha_m v_m$



#### Properties of $H_v$ (thm)

1. $H_v$ is an orthogonal matrix

2. $H_v$ is symmetric

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

   

#### QR Decomposition using Householder matrices

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



#### Schematic Example

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



#### Concrete Numeric Example

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



### High level Computation Notes of All Orthogonalization Methods

|                            | Givens QR                                                    | Householder QR                                               | MGS (CGS) QR                                                 |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Computational time (order) | $3mn^2-n^3$ flops                                            | $2mn^2-2n^3/3$ flops                                         | $2mn^2$ flops                                                |
| if $(m \approx n)$         | $2n^3$ flops + additional work needed to accumulate $\widetilde Q$ | $\frac {4n^3}3$ flops + additional work to accumulate $\widetilde Q$ | $2n^3$ flops and if explicitly gives $Q$ (not $\widetilde Q$) |

Generally, if $Q$ is not needed explicity, `Householder` and `Givens` do not accumulate it. In such a case, one also avoids constructing the `Givens` OR `Householder` matrices explicitly.

Instead, you can store the `Householder` and `Givens` matrices as procedures.

- <u>e.g 1)</u> Information stored in $v$ is enough to understand the action of the `Householder` matrix by writing a routine which applies this matrix on a vector. For example, you can write a function: `household(v,u)` and returns the value $u-2v(v^Tu)/v^Tv$
- <u>e.g 2)</u> Similarly, `Givens` contains a tiny piece of information $(c,s,i,j) \to$ 4 numbers only, so you could write `givens(c,s,i,j,u)` which applies a `Givens` rotation on $u$ without constructing $G$.

To apply `Householder` or `Givens` to full matrices, you could either write corresponding routines or use $GA = G[a_1,... a_n] = [Ga_1,Ga_2,...Ga_n]$ and similarly for `Householder`.