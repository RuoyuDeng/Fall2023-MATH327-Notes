

### Classical Gram-Schemidt (CGS)

#### Input & Output

- **<u>Input:</u>** $a_1,...,a_n \in \R^{m \times n}, n \leq m$. (Assume these are linearly independent)
- **<u>Output:</u>** $q_1,...,q_n \text{ is orthonormal } \in \R ^{m \times n}$ s.t:
  - $span\{q_1\} = span\{a_1\}$
  - $span\{q_1,q_2\} = span\{a_1,a_2\}$
  - ….
  - $span\{q_1,...,q_n\} = span\{a_1,...,a_n\}$

#### Algorithm (normalizing in the end)

$$
v_1 = a_1
\\ v_2 = a_2 - \frac{v_1^Ta_2}{v^T_1v_1}v_1 \text{ (the projection of a2 onto v1)}
\\ v_3 = a_3 - \frac{v_1^Ta_3}{v^T_1v_1}v_1 - \frac{v_2^Ta_3}{v^T_2v_2}v_2
\\ ...
\\ v_n = a_n - \frac{v_1^Ta_n}{v^T_1v_1}v_1 - .....\frac{v_{n-1}^Ta_n}{v^T_{n-1}v_{n-1}}v_{n-1}
$$

Removing the orthogonal projections of $a_3$ onto $v_1,v_2$ sequentially gives ==$v_3 \perp v_1 \&v_2$==

- This works only because $v_1,v_2$ are already orthogonal
- *Proof* will be part of `Assignment 2`



We can then <u>**normalize**</u> by defining:
$$
q_1 = \frac{v_1}{\pm ||v_1||}, q_2 = \frac{v_2}{\pm ||v_2||}, ... q_n = \frac{v_n}{\pm ||v_n||}
$$
It is generally preferable to normalize as you go (rather than doing all normalization in the end) to keep the sizes of intermediary vectors bounded. **<u>This prevents potential numerical issues.</u>**



#### Algorithm (normalizing after each step)

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



#### Definition: QR decomposition

The CGS relations packaged in this way defines the <u>**QR**</u> decomposition of $A$.



#### Questions: Is QR decomposition unique?

- No, because when normalizing $q_j$ values, we ==may select + or - sign== to define $q_j$ as $\pm ||v_j||$. However we will see shortly that if you fix the signs, the decomposition becomes unique.



#### Theorem: Existence and Uniqueness of the reduced QR decomposition

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

  

#### Proof: Existence and Uniqueness of the reduced QR decomposition

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



#### Numerical Problem with CGS (Why we need MGS)

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
-  ==$(q_2^Ta_k)q_2$:==  since $q_2$ is imperfectly orthogonal to $q_1$, this adds another $\triangle_2q_1$
- ==$(q_{k-1}^Ta_k)q_{k-1}$:== since $q_{k-1}$ is inperfectly orthogonal to $q_1$, this adds another $\triangle_{k-1}q_1$

So $v_k$ will contain all terms ==$\triangle_1q_1 + \triangle_2q_1 + .. + \triangle_{k-1}q_1$== in the direction of $q_i$ illustrating that the larger $k$, the more you expect $q_1$ to <u>“lose”</u> orthogonality against $q_k$.

You would be lucky and have these $\triangle's$ cancel out but you generally <u>“lose trust”</u> and lose control over the orthogonality when you run `CGS` for a long time.

To slow down the loss of orthogonality of earlier vectors against later vectors, we apply the **==Modified Gram-Schemidt (MGS)==** method, which is mathematically equivalent to `CGS` but numerically preferable.

- **==Note:==** this is the method of choice for long-skinny matrices ==$n << m$== in $\R^{m \times n}$





### Modified Gram-Schemidt (MGS)

- It is more obvious to learn it through [comparison](#Comparing CGS and MGS)



### Comparing CGS and MGS

#### MGS

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



##### Step k in MGS

$$
v_k^{(0)} = a_k
\\v_k^{(1)} = v_k^{(0)} - (q_1^Tv_k^{(0)})q_1 
\\ v_k^{(2)} = v_k^{(1)} - (q_2^Tv_k^{(1)})q_2 
\\ \vdots
\\ v_k = v_k^{(k-1)} = v_k^{(k-2)} - (q_{k-1}^Tv_k^{(k-2)})q_{k-1}
$$





#### CGS

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



##### Step k in CGS

$$
v_k = a_k - (q_1^Ta_k)q_1 - ... (q_{k-1}^Ta_k)q_{k-1}
$$

- **==Note:==** `MGS` has the same number of iterations in practice as `CGS` since to compte the step k in `CGS`, you still need an iterative procedure similar to the $k^{th}$ step in `MGS`. But the advantage of `MGS` is that you <u>**slow down the loss of orthogonality between vectors.**</



### Def: Full QR Decomposition

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