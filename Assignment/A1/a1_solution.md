# Question 1

## a)

Let vectors $u = a_nx^n+a_{n-1}x^{n-1}+...+a_0$, $ v = b_nx^n+b_{n-1}x^{n-1}+...+b_0$ where $u,v \in P_n(\R), a_i,b_j \in \R$, we also have scalars $m,l \in \R$, we can show the followings:

1. $$
   u + v = (a_nx^n+a_{n-1}x^{n-1}+...+a_0) + (b_nx^n+b_{n-1}x^{n-1}+...+b_0)\\ = (a_n+b_n)x^n +(a_{n-1}+b_{n-1})x^{n-1} +...(a_0+b_0) \\= c_nx^n + c_{n-1}x^{n-1} + ...c_0 \in P_n(\R), c_i \in \R
   $$

2. $$
   mu = m (a_nx^n+a_{n-1}x^{n-1}+...+a_0)  \\
   = ma_nx^n+ma_{n-1}x^{n-1}+...+ma_0 \\
   = c_nx^n + c_{n-1}x^{n-1} + ...c_0 \in P_n(\R), c_i \in \R
   $$

3. let vector $w = d_nx^n +d_{n-1}x^{n-1} + ...d_0, w\in P_n(\R), d_i \in \R$, then
   $$
   (u+v) + w = (a_nx^n+a_{n-1}x^{n-1}+...+a_0 + b_nx^n+b_{n-1}x^{n-1}+...+b_0) + d_nx^n +d_{b-1}x^{n-1} + ...d_0 
   \\ = a_nx^n+a_{n-1}x^{n-1}+...+a_0 + (b_nx^n+b_{n-1}x^{n-1}+...+b_0 + d_nx^n +d_{n-1}x^{n-1} + ...d_0)
   \\=u+(v+w)
   $$
   
4. $$
   m(lu) = m(la_nx^n+la_{n-1}x^{n-1}+...+la_0)
   \\ = ml(a_nx^n+a_{n-1}x^{n-1}+...+a_0)
   \\= (ml)u
   $$

5. $$
   u + v = (a_nx^n+a_{n-1}x^{n-1}+...+a_0) + (b_nx^n+b_{n-1}x^{n-1}+...+b_0)
   \\ = (b_nx^n+b_{n-1}x^{n-1}+...+b_0) +  (a_nx^n+a_{n-1}x^{n-1}+...+a_0)
   \\ = v+u
   $$

6. $$
   (m+l)u = (m+l) a_nx^n + (m+l)a_{n-1}x^{n-1} +...(m+l)a_0
   \\ =ma_nx^n + la_nx^n +ma_{n-1}x^{n-1} +la_{n-1}x^{n-1} + ...ma_0 + la_0
   \\ = (ma_nx^n+ma_{n-1}x^{n-1}+ ...ma_0) + (la_nx^n++la_{n-1}x^{n-1} + ...la_0)
   \\ = mu + lu
   $$

   

7. $$
   m(u+v) = m(a_nx^n+a_{n-1}x^{n-1}+...+a_0 + b_nx^n+b_{n-1}x^{n-1}+...+b_0)
   \\ =ma_nx^n+ma_{n-1}x^{n-1}+...+ma_0 + mb_nx^n+mb_{n-1}x^{n-1}+...+mb_0
   \\ = m(a_nx^n+a_{n-1}x^{n-1}+...+a_0) + m (b_nx^n+b_{n-1}x^{n-1}+...+b_0)
   \\ = mu + mv
   $$

8. let vector $w = d_nx^n +d_{n-1}x^{n-1} + ...d_0, w\in P_n(\R), d_i \in \R$, we know that $w = \vec 0 \in P_n(\R)$ if $ \forall d_i = 0$
   $$
   w + u = 0x^n +0x^{n-1} +...0 +a_nx^n+a_{n-1}x^{n-1}+...+a_0
   \\ = a_nx^n+a_{n-1}x^{n-1}+...+a_0 
   \\ =u
   $$
   Thus $\exists\vec 0 \in P_n(\R)$

9. We know that $-1 \in \R$, thus we know if $u \in P_n(\R), \forall u$, then we must have $-1u \in P_n(\R)$
   $$
   u -1u =a_nx^n+a_{n-1}x^{n-1}+...+a_0 - (a_nx^n+a_{n-1}x^{n-1}+...+a_0)
   \\ = (a_n-a_n)x^n + (a_{n-1}-a_{n-1})x^{n-1} +...(a_0-a_0)
   \\ = 0x^n + 0x^{n-1} + ...+0
   \\ = \vec 0
   $$
   
10. We know $1 \in \R$
    $$
    1u  = 1(a_nx^n+a_{n-1}x^{n-1}+...+a_0)
    \\ = 1a_nx^n+1a_{n-1}x^{n-1}+...+1a_0
    \\ = a_nx^n+a_{n-1}x^{n-1}+...+a_0
    \\ = u
    $$

With all the above rules being satisfied, we can conclude that $(P_n(\R), \R, +, \cdot)$ equipped with the usual polynomial addition and scalar multiplication is a vector space.



## b)

1. For $N(T)$, let $u,v \in N(T)$, then $T(u) = T(v) = 0$. We know that $N(T) = \{v \in V: T(v) =0 \in W\}$, thus $N(T) \subseteq V$

   1. Since $T:V \to W$ is a linear transformation, we have: $T(u+v) = T(u) + T(v) = 0+0 = 0$, thus $u+v \in N(T)$
   2. Let $a \in \R$, then we have $T(au) = aT(u) = a 0 =0$, thus $au \in N(T)$
   3. Since $V,W$ are vector spaces, both of them must contain the zero vector. $\vec 0_v \in V,\vec 0_w \in W$. We thus have $T(\vec 0_v) = \vec 0_w$, which implies that $\vec 0 \in N(T)$

   Therefore, $N(T)$ is the subspace of $V$.

   

2. For $Im(T)$, let $u,v \in Im(T),$ then there must be $u', v' \in V$ such that $u = T(u'), v = T(v')$

   1. $T(u'+v') = T(u') + T(v') = u+v$, thus $u+v \in Im(T)$
   2. Let $a \in \R$, then $T(au') = aT(u') = au$, thus $au \in Im(T)$
   3. Since $V,W$ are vector spaces, we have $\vec 0_v \in V,\vec 0_w \in W$, $\vec0_w=T(\vec0_v)$, thus $\vec0 \in Im(T)$

   Therefore, $Im(T)$ is the subspace of $W$.





# Question 2

## a)

The set $\{v_1,v_2,v_3\}$ are linearly independent if the following equation has one trivial solution where $x_1 = x_2 = x_3 = 0$
$$
x_1\left [
\matrix 
{
1 
\\
1
\\
1
}
\right ]

+
x_2\left [
\matrix 
{
2
\\
2
\\
3
}
\right ]
+
x_3
\left [
\matrix 
{
2 
\\
-1
\\
1
}
\right ]

=\left [
\matrix 
{
0 
\\
0
\\
0
}
\right ]
$$
we can write the equation in the following format:
$$
\left [

\begin{array}{ccc|c}
   1 & 2 & 2 &0 \\
   1 & 2 & -1 &0\\
   1 & 3 & 1 &0
  \end{array}
  
\right ] \stackrel{RREF}{=}

\left [

\begin{array}{ccc|c}
   1 & 0 & 0 &0 \\
   0 & 1 & 0 &0\\
   0 & 0 & 1 &0
  \end{array}
  
\right ]
$$
There is no free variable, which implies that the set $\{v_1,v_2,v_3\}$ are linearly independent.

## b)

Since the set $\{v_1,v_2,v_3\}$ has a degree of 3 and it is linearly independent, thus $\{v_1,v_2,v_3\}$ spans $\R^3$

## c)

Since the set $\{v_1,v_2,v_3\}$ is linearly independent and it spans $\R^3$, thus it is a basis of $\R^3$.

## d)

$$
\left[
\begin{array}{ccc|c}
   1 & 2 & 2 &1 \\
   1 & 2 & -1 &-2\\
   1 & 3 & 1 &5
  \end{array}

\right ] \stackrel{RREF}{=}

\left[
\begin{array}{ccc|c}
   1 & 0 & 0 &-11 \\
   0 & 1 & 0 &5\\
   0 & 0 & 1 &1
  \end{array}
  
\right ]
$$

Thus we have:
$$
v =
\left [
\matrix 
{
1 
\\
-2
\\
5
}
\right ]
= -11 v_1 + 5 v_2 + v_3
$$


# Question 3

## a)

1. $||x||_1 = \sum_{i=1}^n|x_i|$

   1. Need to prove: $x = \vec 0 \iff ||x||_1 \geq 0, ||x||_1 =0$

      1. $x= \vec 0 \implies ||x||_1 \geq 0, ||x||_1 =0$

         If we have $x = \vec0$, then $x_i = 0 \forall x_i \in \R$, which then implies that $\sum_{i=1}^n|x_i| \geq 0, \sum_{i=1}^n|x_i| = 0 \implies ||x||_1 \geq 0, ||x||_1 =0$

      2. $||x||_1 \geq 0, ||x||_1 =0 \implies x= \vec 0$, since we have $|x_i| \geq 0 \forall x_i \in \R$ and $\sum_{i=1}^n|x_i| =0$, if we have $x_j > 0, \exists j\in[1, n]$, then we will have $||x||_1 = \sum_{i=1}^n|x_i| > 0$, which contradicts with our assumption. Thus there must be no $x_j > 0$, combined with $|x_i| \geq 0 \forall x_i \in \R$, we have $x_i = 0 \forall i \in [1,n]$, thus $x = \vec 0$

      After proving 2 directions, we have $x = \vec 0 \iff ||x||_1 \geq 0, ||x||_1 =0$

   2. Need to prove: $||ax||_1 = |a| ||x||_1, a \in \R$
      $$
      ||ax||_1 = \sum_{i=1}^n|ax_i| = \sum_{i=1}^n|a||x_i| = |a|\sum_{i=1}^n|x_i| = |a|||x||_1
      $$

   3. Need to prove: $||x+y||_1 \leq ||x||_1 + ||y||_1$ where $y = (y_1,y_2,...y_n)^T \in \R^n$
      $$
      ||x + y||_1= \sum_{i=1}^n|x_i+y_i| \leq \sum_{i=1}^n|x_i| +|y_i| \text{ by triangle inequality}
      $$
      we know that
      $$
      \sum_{i=1}^n|x_i| +|y_i| = \sum_{i=1}^n|x_i| +\sum_{i=1}^n|y_i| = ||x||_1 + ||y||_1
      $$
      Thus, we have shown $||x + y||_1 \leq ||x||_1 + ||y||_1$

   With all 3 rules being satisfied, we know that $|| \cdot ||_1$ defines norms.

2. $||x||_2 = (x^Tx)^{1/2}$

   1. Need to prove: $x = \vec 0 \iff ||x||_2 \geq 0, ||x||_2 =0$

      1. $x= \vec 0 \implies ||x||_2 \geq 0, ||x||_2 =0$

         If we have $x = \vec 0$, then we know $x_i = 0 \forall i \in [1,n]$, which results in $x^Tx = x_1^2 + x_2^2+...x_n^2 = 0$. Thus $||x||_2 = (x^Tx)^{1/2} =0$

      2. $||x||_2 \geq 0, ||x||_2 =0 \implies x= \vec 0$

         If $||x||_2 = (x^Tx)^{1/2} = 0$, then we must have: $x_1^2 + x_2^2+...x_n^2 = 0$, since $x^2_i \geq 0$ and if we assume $\exists j\; s.t\; x_j^2 > 0$, then $x_1^2 + x_2^2+...x_n^2 >0$, which is contradictory to our prior condition. Thus $x_i^2 = 0 \implies x_i = 0\forall i\in[1,n]$, thus we have $x = \vec 0$

   2. Need to prove: $||ax||_2 = |a| ||x||_2, a \in \R$
      $$
      ||ax||_2 =(ax^Tax)^{1/2} = (a^2)^{1/2}(x^Tx)^{1/2} = |a| (x^Tx)^{1/2} = |a| ||x||_2
      $$

   3. Need to prove: $||x+y||_2 \leq ||x||_2 + ||y||_2$ where $y = (y_1,y_2,...y_n)^T \in \R^n$

      By Cauchy-Schwarz’s inequality, we have:
      $$
      ||x+y||^2_2 = <x+y,x+y>
      \\ = ||x||^2_2 + <x,y> +<y,x> + ||y||_2^2
      \\ \leq ||x||^2_2 + 2|<x,y>| + ||y||_2^2
      \\ \leq ||x||^2_2 + 2||x||_2||y||_2 + ||y||_2^2 \text{ by Cauchy-Schwarz’s inequality}
      \\ \leq (||x||_2+||y||_2)^2
      $$
      By taking square root on both sides, we obtain:
      $$
      ||x+y||_2 \leq ||x||_2 + ||y||_2
      $$

   With all 3 rules being satisfied, we know that $|| \cdot ||_2$ defines norms.

3. $||x||_\infty = \max\limits_{i} |x_i|$

   1. Need to prove:  $x = \vec 0 \iff ||x||_\infty \geq 0, ||x||_\infty =0$

      1. $x= \vec 0 \implies ||x||_\infty \geq 0, ||x||_\infty =0$

         $x = \vec 0 \implies x_i = 0 \forall i \in [1,n]$, therefore $\max\limits_{i} |x_i| = 0, \max\limits_{i} |x_i| \geq 0$ by the definition of $\max\limits_i$.

      2. $  ||x||_\infty \geq 0, ||x||_\infty =0 \implies x= \vec 0$

         Given $\max\limits_{i} |x_i| = 0, \max\limits_{i} |x_i| \geq 0$, then if $\exists x_j > 0, j\in [1,n]$, then $$\max\limits_{i} |x_i| > 0$$, which is contradictary to our assumption. Therefore $x_i = 0 \forall i\in [1,n]$, which implies that $x = \vec0$

   2. Need to prove: $||ax||_\infty = |a| ||x||_\infty, a \in \R$
      $$
      ||ax||_\infty =\max\limits_{i} |ax_i| = \max\limits_{i} |a||x_i| = |a| \max\limits_{i} |x_i| = |a| ||x||_\infty
      $$
   
3. Need to prove: $||x+y||_\infty \leq ||x||_\infty + ||y||_\infty$ where $ y = (y_1,y_2,...y_n)^T \in \R^n$
      $$
      ||x+y||_\infty =\max\limits_{i} |x_i + y_i| 
      \\ \leq \max\limits_{i} (|x_i| + | y_i|) \text{ by triangle inequality}
      \\ \leq \max\limits_{i} |x_i| + \max\limits_{i} |y_i|
      \\ \leq ||x||_\infty + ||y||_\infty
      $$

With all 3 rules being satisfied, we know that $|| \cdot ||_\infty$ defines norms.

## b)

1. $||x||_1 = \sum_{i=1}^n|x_i|$

   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230129232442366.png" alt="image-20230129232442366" style="zoom:50%;" />

2. $||x||_2 = (x^Tx)^{1/2}$

   <img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230129232451098.png" alt="image-20230129232451098" style="zoom:50%;" />

3. $||x||_\infty = \max\limits_{i} |x_i|$

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230129232458107.png" alt="image-20230129232458107" style="zoom:50%;" />



# Question 4

## a)

1. Let $x = (x_1,x_2...x_n)^T, y = (y_1,y_2...y_n)^T, x,y \in \R^n$
   $$
   <x,y> = x^Ty = x_1y_1 + x_2y_2 + ....x_ny_n \\
   <y,x> = y^Tx = y_1x_1 + y_2x_2 + ....y_nx_n
   $$
   we know that $x_iy_i = y_ix_i \forall x_i,y_i \in \R$, therefore we have $<x,y> =<y,x>$

2. Let $a \in \R$, then
   $$
   <ax,y> = (ax^T)y
   \\ = ax_1y_1 + ax_2y_2 + ....ax_ny_n 
   \\ = a(x_1y_1 + x_2y_2 + ....x_ny_n) 
   \\= a(x^Ty) = a<x,y>
   $$

3. Need to show: $<x,x> \geq 0, <x,x> = 0 \iff x = \vec0$

   1. $<x,x> \geq 0, <x,x> = 0 \implies x = \vec 0$
      $$
      <x,x> = x^Tx = x_1^2 + x_2^2 +... + x_n^2 \geq 0
      \\ x^Tx = x_1^2 + x_2^2 +... + x_n^2 = 0
      $$
      then we must have $x_i = 0 \forall i \in [1,n]$. Therefore, we have $x = (0_1,0_2,0_3...0_n)^T = \vec 0$

   2. $x = \vec 0 \implies <x,x> \geq 0, <x,x> = 0  $

      $x = \vec 0 \implies x = (0_1,0_2,0_3...0_n)^T $, then we have $<x,x> = x^Tx = 0 \cdot 0 + 0 \cdot 0 + ... + 0 \cdot 0 = 0, <x,x> \geq 0$

   Thus, we proved that $<x,x> \geq 0, <x,x> = 0 \iff x = \vec 0$

With all 3 rules being true, we proved that $<x,y> = x^Ty$ defines an inner product.

## b)

If $v = \vec 0$, then we have $|<u,v>| = ||u|| ||v|| = 0$

If $v \neq \vec 0$, we have the residual $r = u - Proj_v(u) = u - \frac{<u,v>} {<v,v>}v$, $u = r + \frac{<u,v>} {<v,v>}v$
$$
|| u ||^2 = || r + \frac{<u,v>} {<v,v>}v||^2
\\ = ||r||^2 + ||\frac{<u,v>} {<v,v>}v||^2 \text{ by Pythagoras therorem since v is orthogonal to r}
\\ = \frac{|<u,v>|^2} {|<v,v>|^2}||v||^2 + ||r||^2
\\ = \frac{|<u,v>|^2} {(||v||^2)^2}||v||^2 + ||r||^2
\\ = \frac{|<u,v>|^2} {||v||^2}  + ||r||^2
\\ \geq \frac{|<u,v>|^2} {||v||^2}
$$
By rewriting the above equation, we obtain:
$$
|<u,v>|^2 \leq ||u||^2||v||^2 \implies <u,v> \leq ||u||||v||
$$
For such inequality to be equality, we must have following 2 directions being true:

1. $u =av \implies |<u,v>| = ||u|| \;||v|| $
   $$
   u = av \implies r = av - \frac{a<v,v>}{<v,v>}v = av - av =0
   $$
   If $r = 0$, then we will have:
   $$
   || u ||^2 = \frac{|<u,v>|^2} {||v||^2}  + ||r||^2  = \frac{|<u,v>|^2} {||v||^2}
   \\ \implies |<u,v>| = ||u|| \;||v||
   $$
   
2. $|<u,v>| = ||u|| \;||v|| \implies u =av$

   Similarly, if we know $|<u,v>| = ||u|| \;||v||$, then we must have $r = 0$ from above eqution.

   With residual $r = 0$, we know that $u,v$ must be collinear, which is equivalent with $u  = av, a\in \R$

Therefore, we have proved that $|<u,v>| = ||u|| \;||v|| \iff u =av$



## c)

Given $||v|| = <v,v>^{1/2}$

1. Need to prove: $||v|| \geq 0, ||v|| = 0 \iff v = \vec 0$

   1. $||v|| \geq 0, ||v|| = 0  \implies v = \vec 0$
      $$
      ||v|| = <v,v>^{1/2} = (v^Tv)^{1/2} \geq 0,(v^Tv)^{1/2} = 0
      $$
      since $v^2_i \geq 0$ and if we assume $\exists j\; s.t\; v_j^2 > 0$, then $v_1^2 + v_2^2+... = (v^Tv)^{1/2} >0$, which is contradictory to our prior condition. Thus $v_i^2 = 0 \implies v_i = 0$, thus we have $v = \vec 0$

   2. $v = \vec 0 \implies ||v|| \geq 0, ||v|| = 0 $

      we have $v_i =0 \forall v_i \in \R$, then we know that $||v|| = (v^Tv)^{1/2} = (v_1^2 + v_2^2 +...)^{1/2} = 0$, and $||v|| \geq 0$

   Therefore, we proved that $||v|| \geq 0, ||v|| = 0 \iff v = \vec 0$

2. Need to prove: Let $a\in \R$, then we have $||av||= |a| ||v||$
   $$
   ||av|| = <av,av>^{1/2}= (a^2<v,v>)^{1/2} = |a| <v,v>^{1/2} = |a| ||v||
   $$

3. Need to prove: $||u+v|| \leq ||u|| + ||v||$ where $v  \in V$
   $$
   ||u+v||^2 = <u+v,u+v>
   \\ = ||u||^2 + <u,v> +<v,u> + ||v||^2
   \\ \leq ||u||^2 + 2|<u,v>| + ||v||^2
   \\ \leq ||u||^2 + 2||u||||v|| + ||v||^2 \text{ by Cauchy-Schwarz’s inequality}
   \\ \leq (||u||+||v||)^2
   $$

With all 3 rules being satisfied, we know that $||v|| = <v,v>^{1/2}$ is a norm.





We know that the parallelogram law is implicitly dervied from inner product with L2 norm.
$$
||x||^2 + ||y||^2 = ||x+y||^2 + ||x-y||^2
$$
**Counter Example: take $||x||_\infty = \max\limits_{i} |x_i|$**, we will show that the parallelogram law does not hold with $||x||_\infty$.
$$
||x+y||_\infty^2  + ||x-y||_\infty^2=(\max\limits_{i} |x_i + y_i|)^2 + (\max\limits_{i} |x_i - y_i|)^2
\\ = \max\limits_i (x_i+y_i)^2 + \max\limits_i (x_i-y_i)^2  
\\ = \max\limits_i (x^2_i+2x_iy_i+y^2_i) + \max\limits_i (x^2_i-2x_iy_i+y^2_i)  
\\ = \max\limits_i x_i^2 + \max\limits_i x_i^2 + \max\limits_i y_i^2 + \max\limits_i y_i^2
\\ = 2 \max\limits_i x_i^2 + 2\max\limits_i y_i^2
\\ = 2 \max\limits_i |x_i|^2 + 2\max\limits_i |y_i|^2
\\ = 2 (||x||^2_\infty + ||y||^2_\infty)
\\ \neq ||x||^2_\infty + ||y||^2_\infty
$$
therefore, we found a counter example $|| \cdot || _\infty$ which can not be induced by an inner product in such a way.

# Question 5

## a)

Let $u = (u_1,u_2,u_3)^T_{\beta_3}$, $v = (v_1,v_2,v_3)^T_{\beta_3}$, $u,v \in \R^3$, take $a \in \R$

We know that $T((x_1,x_2,x_3)_{\beta_3}^T) = (2x_1 + 3x_2-x_3,x_1+2x_3)_{\beta_2}^T$

1. $$
   T(u+v) = T((u_1+v_1,u_2+v_2,u_3+v_3)^T_{\beta_3})
   \\ = (2(u_1+v_1)+3(u_2+v_2)-(u_3+v_3), u_1+v_1+3(u_3+v_3))_{\beta_2}^T
   \\ = ((2u_1 + 3u_2 -u_3) + (2v_1 + 3v_2 -v_3), (u_1 + 3u_3) + (v_1+3v_3))^T_{\beta_2}
   \\ = (2u_1 + 3u_2 -u_3, u_1 + 3u_3)^T_{\beta_2} + (2v_1 + 3v_2 -v_3, v_1 + 3v_3)^T_{\beta_2} 
   \\ = T(u) + T(v)
   $$

2. $$
   T(au) =(2au_1 + 3au_2 -au_3, au_1 + 3au_3)^T_{\beta_2}
   \\ = (a(2u_1 + 3u_2 -u_3), a(u_1 + 3u_3))^T_{\beta_2}
   \\ = a (2u_1 + 3u_2 -u_3, u_1 + 3u_3)^T_{\beta_2}
   \\ = aT(u)
   $$

With the 2 rules above being satisfied, we can say that $T$ is a linear transformation.



## b)

$$
T: \R^3 \to \R^2 := \left [
\matrix 
{
2 & 3 & -1
\\
1 & 0 & 2
}
\right ]

\left [
\matrix 
{
e_1
\\
e_2
\\
e_3
}
\right ] = 

\left [
\matrix 
{
2e_1+3e_2-e_3
\\
e_1 + 2e_3
}
\right ]
$$



## c)




$$
\left [
\begin{array}{ccc|c}
   2 & 3 & -1 &0 \\
   1 & 0 & 2 &0\\
  \end{array}
\right]

=
\left [
\begin{array}{ccc|c}
   1 & 0 & 2 &0 \\
   0 & 1 & -5/3 &0\\
  \end{array}
\right]
$$
we thus have:
$$
e_1 = -2e_3 
\\ e_2 = \frac53 e_3
\\ e_3 \text{ is free }
$$
$N(T) = \{a (-2, \frac 53, 1)^T : a\in \R \}$, since there is 1 free variable in $N(T)$, $Nullity(T) = 1$

Since we observe 2 pivots in the reduced matrix form, we can express the last column as a linear combination of the other two columns: $(-1, 2)^T = 2(2,1)^T - \frac 53 (3,0)^T$, thus $Im(T) = span(\{(2,1)^T, (3,0)^T\}), rank(T) = 2$.
