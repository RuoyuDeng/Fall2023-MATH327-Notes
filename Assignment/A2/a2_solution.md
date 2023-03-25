# Q1

## a)

Since we know that $Q$ is a orthogonal matrix, we have: $Q^TQ = I$

1. inner products. needs to show: $(Qu)^T \cdot (Qv) = u^Tv$
   $$
   (Qu)^T \cdot (Qv) = u^TQ^TQv = u^TIv = u^Tv
   $$
   
2. norms. needs to show: $||Qu||_2 = ||u||_2$
   $$
   ||Qu||_2 = |<Qu,Qu>| 
   \\= |(Qu)^T\cdot(Qu)| \\= |u^TQ^TQu| 
   = |u^Tu| 
   \\= |<u,u>|= ||u||_2
   $$
   then we have: $||Qu||_2 = ||u||_2$
   
3. distances. needs to show $||Qu-Qv||_2 = ||u-v||_2$
   $$
   ||Qu-Qv||_2 = |<Qu-Qv, Qu-Qv>| 
   \\= |<Qu,Qu-Qv> - <Qv,Qu-Qv>|
   \\ = |(<Qu,Qu>- <Qv,Qu>) - (<Qu,Qv> - <Qv,Qv>)|
   \\ = |(u^Tu - v^Tu) - (u^Tv - v^Tv) |
   \\ = |(<u,u> - <v,u>) - (<u,v> - <v,v>)|
   \\ = | <u-v,u> - <u-v,v> |
   \\ = | <u,u-v> - <v,u-v> |
   \\ = |<u-v,u-v>|
   \\ = ||u-v||_2
   $$
   then we have: $||Qu-Qv||_2 = ||u-v||_2$
   
4. angles. needs to show: $\angle(Qu,Qv) = \angle(u,v)$
   $$
   \theta = arccos(\frac{<Qu,Qv>}{||Qu|| ||Qv||}) 
   \\
   = arccos(\frac{u^TQ^TQv}{||Qu||_2 ||Qv||_2}) = arccos(\frac{u^Tv}{||u||_2 ||v||_2})
   $$
   which implies that: $\angle(Qu,Qv) = \angle(u,v)$



## b)

### 1) show that the orthogonal projection of u onto v, is the vector in span(v) closest to u

Let $av \in span(v), a\in \mathbb{R}$, then $d(u, av) = ||u-av||$ 

The orthogonal projection of u onto v is denoted by $Proj_v(u)$, which is colinear with $av$. By definition, residual $ r = u - Proj_v(u)$ and $u-Proj_v(u) \perp v$.

Since $av$ and $Proj_v(u)$ are colinear, we have $Proj_v(u) - av$ being colinear with $av$ as well.

Therefore, we have $(u-Proj_v(u)) \perp (Proj_v(u)-av)$, by Pythagoras theorem, we have:
$$
||u-Proj_v(u) +Proj_v(u) - av||^2 
\\ = ||u-Proj_v(u)||^2 + ||Proj_v(u) - av||^2 
\\ = ||u - av||^2 \text{, which is the squared distance between u and any vector from span(v)}
$$
such value is minized when $av = Proj_v(u)$:
$$
||u-Proj_v(u)||^2 + ||Proj_v(u) - av||^2 
\\ =||u-Proj_v(u)||^2 + ||Proj_v(u) - Proj_v(u)||^2
\\ = ||u-Proj_v(u)||^2 = ||u-av||^2
$$
Therefore, the orthogonal projection of u onto v is the vector in span(v) closest to u.



### 2) show that the orthogonal projection of u onto W is the vector inside W closest to u

Let $x \in W$, Since $W$ is a subspace and $Proj_W(u) \in W$, we can find $y = Proj_W(u) + x \in W$
$$
|| u - y||^2 = || u - (Proj_W(u) +x) ||^2 = || (u - Proj_W(u)) -x ||^2
$$
By definition of residual, $u - Proj_W(u) \perp x$, then by Pythagoras theorem, we have:
$$
|| (u - Proj_W(u)) -x ||^2 = ||u-Proj_W(u)||^2 +||x||^2
$$
where $|| (u - Proj_W(u)) -x ||^2$ is the squared distance from u to subspace $W$. The distance is minimized if we have $||x||^2 = 0$, which implies that $||u-y||^2 = || u - Proj_W(u) ||^2 \implies ||u-y|| = || u - Proj_W(u) ||$

Therefore, the orthogonal projection of u onto W is the vector inside W closest to u

The closet vector is not unique because 



### 3) uniquness of closest vector

Assume there are $x,y \in W$ that are both orthogonal projection of $u$ onto $W$, and $||u-x|| \leq || u-y||$

Since $x,y$ are both orthogonal projections of u onto W, we have:
$$
|| u - x|| = ||u- Proj_W(u) ||
\\ || u - y || = ||u- Proj_W(u) ||
$$
Plus $||u-y||$ on both sides of $||u-x|| \leq || u-y||$, we obtain:
$$
|| u - x|| + ||u-y|| \leq ||u-y|| + ||u-y||
\\ 2 ||u- Proj_W(u) || \leq 2 ||u- Proj_W(u) ||
 \implies ||u- Proj_W(u) || \leq ||u- Proj_W(u) ||
$$
Since $||u- Proj_W(u) ||$ is always non-negative, the above inequality implies that $||u- Proj_W(u) || = 0$, which means that the closest vector is indeed unique.





# Q2

## a)

$$
A =\left [
\matrix {1 & 3 & 1 \\ 0 & 1 & 2 \\ 1 & -1 &3 \\ 0 & 0 &4}
\right ]
$$

$$
v_1= a_1 = \left [\matrix {1  \\ 0 \\ 1 \\0}\right ], 
q_1 = \frac{v_1} {||v_1||} = \left [ \matrix {0.7071  \\ 0 \\ 0.7071 \\0} \right ],
||v_1|| = 1.414

\\
v_2 = a_2 - (q_1^Ta_2)q_1 = \left [ \matrix {2  \\ 1 \\ -2 \\0} \right ], 
q_2 = \frac{v_2} {||v_2||} = \left [ \matrix {0.6667  \\ 0.3333 \\ -0.6667 \\0} \right ], q_1^Ta_2 = 1.414,
||v_2|| = 3

\\
v_3 = a_3 - (q_1^Ta_3)q_1 - (q_2^Ta_3)q_2 = \left [ \matrix {-0.1197  \\ 0.4786 \\ 0.1197 \\0.8615} \right ], 
q_3 = \frac{v_3} {||v_3||} = \left [ \matrix {-0.1197  \\ 0.4786 \\ 0.1197\\0.8615}\right]

\\
q_1^Ta_3 = 2.8284,
q_2^Ta_3 = -0.6667,
||v_3|| = 4.6428
$$

$$
Q =\left [ \matrix {
0.7071 & 0.6667 & -0.1197 
\\ 0 & 0.3333 & 0.4786 
\\ 0.7071 & -0.6667 & 0.1197
\\0 & 0 & 0.8615
} \right ]

\\
R = \left [ \matrix {
1.414 & 1.414 & 2.8284
\\ 0 & 3 & -0.6667 
\\ 0 & 0 & 4.6428
} \right ]
$$

## b)

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



## c)

```matlab
function [Q, R] = myGS(A)
[m,n] = size(A);
R = zeros(n,n);
Q = zeros(m,n);
for j = 1:n
	v = A(1:m, j);
	for i = 1:j-1
		R(i,j) = Q(1:m,i)' * A(1:m,j); 
		v = v - R(i,j) * Q(1:m,i);
	end
	R(j,j) = sqrt(v' * v); 
	Q(1:m, j) = v/R(j,j);
end
```



## d)

![image-20230220100807263](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230220100807263.png)



# Q3

## a)

If $v_3$ is orthogonal to both $q_1$ and $q_2$, then we should have:
$$
q_1^T v_3 = 0, q_2^T v_3 =0
$$
Take example of $q_1^Tv_3$, given that $||q_1|| = ||q_2|| =1$, we can express it as:
$$
q_1^T v_3 = q_1^T (a_3 - (q_1^Ta_3)q_1 - (q_2^Ta_3)q_2)
\\ = q_1^Ta_3 - q_1^Tq_1(q_1^Ta_3) - q_1^Tq_2(q_2^Ta_3)
\\ = q_1^Ta_3 -  q_1^Ta_3 -  q_1^Tq_2(q_2^Ta_3)
\\ = -  q_1^Tq_2(q_2^Ta_3)
$$
which is a non-zero term. That is contradictory to the fact that $q_1^Tv_3 = 0$.

Therefore, if $q_1, q_2$ are not orthogonal, the $v_3 = a_3 - (q_1^Ta_3)q_1 - (q_2^Ta_3)q_2$ constructed can not be orthogonal to both $q_1$ and $q_2$.

If $q_1, q_2$ are indeed orthogonal, then we have $q_1^Tq_2 = 0$, which resolves the contradiction.



## b)

- **<u>Input:</u>** $ A= [a_1, ...a_n] \in \R^{m \times n}, m\geq n$, full column rank

- **<u>Algorithm:</u>**

  for j = 1,….n

  ​	$v_j = a_j$

  ​	for i = 1, … j-1

  ​		$R_{ij} = q^T_iv_j$

  ​		$v_j = v_j - R_{ij}q_j$

  ​	end

  ​	$r_{jj} = ||v_j||_2$

  ​	$q_j = v_j /r_{jj}$

  end

- **<u>Output:</u>** $R$ (result matrix) and $Q= [q_1,...q_n]$



##  c)

```matlab
function [Q, R] = myMGS(A)
[m,n] = size(A);
R = zeros(n,n);
Q = zeros(m,n);
for j = 1:n
	v = A(1:m, j);
	for i = 1:j-1
		R(i,j) = Q(1:m,i)' * v;
		v = v - R(i,j) * Q(1:m,i);
	end
	R(j,j) = norm(v,2);
	Q(1:m, j) = v/R(j,j);
end
```

## d)

![image-20230220142227722](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230220142227722.png)



# Q4

## a)

$$
A =\left [
\matrix {1 & 3 & 1 \\ 0 & 1 & 2 \\ 1 & -1 &3 \\ 0 & 0 &4}
\right ]
$$

**<u>Step 1:</u>**

We modify on first and third row to start off.

- $r^2 = 1^2 + 1^2 \implies r = 1.414$
- $c = \frac 1 {1.414} = 0.707$
- $s = - \frac 1 {1.414} = -0.707$

$G_1^T = \left [
\matrix {c & 0 & -s & 0\\ 0 & 1 & 0 &0 \\ s & 0 &c & 0\\ 0 & 0 &0 & 1}
\right ] = \left [
\matrix {0.707 & 0 & 0.707 & 0\\ 0 & 1 & 0 &0 \\ -0.707 & 0 &0.707 & 0\\ 0 & 0 &0 & 1}
\right ]$

$A_1 = G_1^TA = \left [
\matrix {0.707 & 0 & 0.707 & 0\\ 0 & 1 & 0 &0 \\ -0.707 & 0 &0.707 & 0\\ 0 & 0 &0 & 1}
\right ] \left [
\matrix {1 & 3 & 1 \\ 0 & 1 & 2 \\ 1 & -1 &3 \\ 0 & 0 &4}
\right ] =\left [
\matrix {1.414 & 1.414 & 2.828 \\ 0 & 1 & 2 \\ 0 & -2.828 &1.414 \\ 0 & 0 &4}
\right ]$



**<u>Step 2:</u>**

We modify on second and third row

- $r^2 = 1 + (-2.828)^2 \implies r = 3$
- $c = \frac 1 3 = 0.333$
- $s = - \frac {-2.828} 3 = 0.943$

$$
G_2^T =
\left [
\matrix {
	 1 & 0 & 0 & 0
\\ 0 & 0.333 & -0.943 &0 
\\ 0 & 0.943 & 0.333 & 0
\\ 0 & 0 &0 & 1}
\right ]
$$

$$
A_2 = G_2^TG_1^TA =
\left [
\matrix {1.414 & 1.414 & 2.828 \\ 0 & 3 & -0.6674 \\ 0 & 0 &2.3569\\ 0 & 0 &4}
\right ]
$$

**<u>Step 3:</u>**

We modify on third and fourth row

- $r^2 = 2.3569^2 + 4^2 \implies r = 4.643$
- $c = 2.3569 / 4.643 = 0.508$
- $s = -4 / 4.643 = -0.862$


$$
G_3^T =
\left [
\matrix {
	 1 & 0 & 0 & 0
\\ 0 & 1 & 0 &0 
\\ 0 & 0 & 0.508 & 0.862 
\\ 0 & 0 & -0.862 &0.508 }
\right ]
$$

$$
\widetilde R = A_3 = G_3^TG_2^TG_1^TA = 
\left [ \matrix {
1.414 & 1.414 & 2.828
\\ 0 & 3 & -0.667 
\\ 0 & 0 & 4.645
\\ 0 & 0 & 0
} \right ]
$$

$$
\widetilde Q = G_1G_2G_3 = \left[\matrix{0.7070 &   0.6667 &  -0.1196  &  0.2029 \\0 & 0.3330 &  0.4790 &  -0.8129 \\
    0.7070   &-0.6667  &  0.1196 &  -0.2029 \\
         0   &   0  &  0.8620 &   0.5080}\right]
$$



## b)

- **<u>Input:</u>** $ A= [a_1, ...a_n] \in \R^{m \times n}, m\geq n$, full column rank

- **<u>Algorithm:</u>**

  $R = A$

  $Q = I_m$

  for $j = 1 \dots n$ 

  ​	for $i = 0 \dots m-1-j$

  ​		$GT =I_m$

  ​		$x = R_{m-i-1,j}$

  ​		$y = R_{m-i, j}$

  ​		$r = \sqrt{x^2 + y^2}$

  ​		$c = x/r$

  ​		$s = -y/r$

  ​		$GT_{m-i, m-i} = c$

  ​		$GT_{m-i-1, m-i-1} = c$

  ​		$GT_{m-i-1, m-i} = s$

  ​		$GT_{m-i, m-i-1} = -s$

  ​		$R = GT\cdot R$

  ​		$Q = Q \cdot GT^T$		

  ​	end

  end

- **<u>Output:</u>** $\widetilde R$ and $\widetilde Q= [q_1,...q_n,q_{n+1}, \dots, q_m]$



## c)

```matlab
function [Q,R] = myGivens(A)
[m,n] = size(A);
R = A;
Q = eye(m);
for j = 1:n
    for i = 0: m-1-j
        GT = eye(m);
        x = R(m-i-1,j);
        y = R(m-i,j);
        r = sqrt(x^2 + y^2);
        c = x/r;
        s = -y/r;
        GT(m-i, m-i) = c;
        GT(m-i-1, m-i-1) = c;
        GT(m-i-1, m-i) = -s;
        GT(m-i, m-i-1) = s;
        R = GT * R;
        Q = Q * GT';
    end
end
```



## d)

![image-20230220163733752](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230220163733752.png)





# Q5

## a)

$$
A =\left [
\matrix {1 & 3 & 1 \\ 0 & 1 & 2 \\ 1 & -1 &3 \\ 0 & 0 &4}
\right ]
$$

**<u>Step 1:</u>**
$$
u = 
\left [
\matrix {1  \\ 0 \\ 1 \\ 0}
\right ] ,v_1 = \bar v_1 = u - ||u||e_1 = 
\left[\matrix{-0.4142
         \\0
\\    1.0000
  \\       0}\right]
  
  \\H_{v_1} = I_4 - \frac{2v_1v_1^T}{v_1^Tv_1} = 
  \left [
  \matrix{0.7071  &  1  &  0.7071 &   1\\
  0 &        0&         0&         0\\
    0.7071      &   0 &  -0.7071 &         0 \\
         0 &         0&         0&         0}
  \right]
  \\ A_1 = H_{v_1}A = 
  \left[
  \matrix{
         1.4142  &  1.4142  &  2.8284\\
         0   & 1   & 2 \\
					0	 & 2.8284 &  -1.4142\\
         0 &         0   & 4


  }
  \right]
$$
**<u>Step 2:</u>**
$$
u = 
\left [
\matrix {1 \\ 2.8284 \\ 0}
\right ] , 
\bar v_2 = u - ||u||e_2 =  
\left[
\matrix{-2\\
				2.8284\\       
         0}
\right],
v_2 =
\left[
\matrix{
				0\\
				-2\\
				2.8284\\       
         0}
\right]
  
\\H_{v_2} = I_4 - \frac{2v_2v_2^T}{v_2^Tv_2} = 
\left [
\matrix{
    1&         0&         0&         0\\
         0    &0.3333   & 0.9428&         0\\
         0    &0.9428   &-0.3333&         0\\
         0         &0&         0&    1

}
\right]
\\ A_2 = H_{v_2}H_{v_1}A = 
\left[
  \matrix{
    1.4142   & 1.4142 &   2.8284\\
    0   & 3  & -0.6667\\
   -0&   -0 &2.3570\\
         0  &       0    &4
}
  \right]
$$
**<u>Step 3:</u>**
$$
u = 
\left [
\matrix { 2.357 \\ 4}
\right ] , 
\bar v_3 = u - ||u||e_3 =  
\left[
\matrix{-2.2858\\
4 }
\right],
v_3 =
\left[
\matrix{
				0\\
				0\\
			      -2.2858\\
4 
        }
\right]
  
\\H_{v_3} = I_4 - \frac{2v_3v_3^T}{v_3^Tv_3} = 
\left [
\matrix{
        1 &        0 &        0&         0\\
         0 &   1&         0  &       0\\
         0  &       0   & 0.5077   & 0.8615\\
         0   &      0   & 0.8615  & -0.5077



}
\right]
\\ \widetilde R =A_3 = H_{v_3}H_{v_2}H_{v_1}A = 
\left[
  \matrix{
        1.4142   & 1.4142    &2.8284\\
    0& 3&   -0.6667 \\
   -0&   -0&    4.6428 \\
   -0&   -0&    0

}
  \right]
$$

$$
\widetilde Q =H_{v_1}H_{v_2}H_{v_3} = 
\left[

\matrix{
    0.7071   & 0.6667   &-0.1197  & -0.2031\\
         0  &  0.3333    &0.4786  &  0.8123\\
    0.7071 &  -0.6667   & 0.1197  &  0.2031\\
         0&         0 &   0.8615  & -0.5077
}
\right]
$$



## b)

- **<u>Input:</u>** $ A= [a_1, ...a_n] \in \R^{m \times n}, m\geq n$, full column rank

- **<u>Algorithm:</u>**

  $R = A$

  $Q = I_m$

  for $i = 1 \dots n$ 

  ​	$u = R_{i:m,i}$

  ​	$\bar v = u - ||u||e_{i}$

  ​	$v = \left ( 
  \matrix {0_1 \\ \vdots \\0_m}
  \right )$

  ​	$v_{i:m,1} = \bar v$

  ​	$H_v = I_m - 2 \frac {v v^T} {v^Tv}$

  ​	$R = H_vR$

  ​	$Q = Q H_v$

  end

- **<u>Output:</u>** $\widetilde R$ and $\widetilde Q= [q_1,...q_n,q_{n+1}, \dots, q_m]$

## c)

```matlab
function [Q,R] = myHouseHolder(A)
[m,n] = size(A);
Q = eye(m);
R = A;
for i = 1:n
    u = R(i:m, i);
    vb = u - (norm(u,2) * eye(m-i+1, 1));
    v = zeros(m,1);
    v(i:m , 1) = vb;
    Hv = eye(m) - 2 * (v * v') / (v' * v);
    R = Hv * R;
    Q = Q * Hv;
end
```

## d)

![image-20230220200644065](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230220200644065.png)

