# MATH 223 Final Notes Pack

----

# 1. Complex Numbers 

## 1.1. Concept Definitions

### 1.1.1. Complex Numbers 

$$
a+ib
$$

### 1.1.2. Complex Field

- The field of the complex numbers are all the expression with the form $a + ib$, where
  $$
  {\C = \{a+ib | a \in \R, b \in \R, i^2 = -1\}}
  $$
  **a** is the real part of a complex number, **b** is the imaginary part of a complex number

### 1.1.3. Complex Conjugate 

$$
  \bar z = a - ib
$$

### 1.1.4. Complex Modulus

$$
\begin{align*}
|z| =\sqrt{a^2+b^2}
 \newline |z|^2 = z \cdot \bar z = a^2 + b^2
\end{align*}
$$

### 1.1.5. Multiplicative inverse

$$
z^{-1} = \frac {\bar z }{|z|^2}
$$



### 1.1.6. Operations of complex numbers

#### 1. Addition

$$
a+ib + c+id = a+c+i(b+d)
$$

#### 2. Multiplication

$$
(a+ib) \cdot (c+id) = ac + iad + ibc + i^2bd = (ac-bd) + i(ad+bc)
$$

#### 3. Division

Let ${z = a + ib, w = c + id, \bar z = a-ib,\bar w = c-id}$
$$
\frac{z}{w} = \frac{z \cdot \bar w}{ w \cdot \bar w} = \frac{(a+ib)(c-id)}{c^2+d^2}=\frac{(ac+bd)-i(ad-bc)}{c^2+d^2}
$$
==**Note:**== We ==can not divide a single $i$.== ${\frac{x}{i}}$ is not allowed.

---



## 1.2. Side Notes

- Always use $i^2 = -1$

  if the other way around is needed, we have to define $\sqrt i = \sqrt -1$

- ${\mathbb{N} \in \mathbb{Z} \in \mathbb{Q} \in \mathbb{R} \in \mathbb{C}}$

---



## 1.3. Proof Exercises 

​	**These are easy proofs(write it out in terms of complex numbers, then it is easy algebra)**

1. Show $ {z \cdot z^{-1} = z^{-1} \cdot z}$

​	we know that ${z = a+ib, |z| = \sqrt {a^2+b^2}, z^{-1} = \frac {\bar z }{|z|^2}, \bar z = a-ib}$

​	Therefore $ {z \cdot z^{-1} = (a+ib) \cdot \frac {a-ib }{a^2+b^2} = \frac{a^2-i^2b^2}{a^2+b^2} = \frac{a^2+b^2}{a^2+b^2} = 1}$

2. ${\overline{z+w} = \overline z + \overline w}$ (write it out as $a + ib$)
3. ${\overline {z \cdot w}= \bar z \cdot \bar w} $
4. ${\bar{\bar z} = z} $
5. ${z \in \mathbb{R} \iff z=\bar z}$
6. ${z \cdot \bar z = |z|^2}$

---



## 1.4. Propositions

### 1. Euler's Formula 

- ${e^{i\theta} = cos\theta + isin\theta}$

  ==Advanced application==
  $$
  (e^{i\theta})^n = (cos\theta + isin\theta)^n \\
  e^{i\theta n} = e^{i(\theta n)}= (cos (n\theta) + isin(n \theta)) \\
  \implies \textcolor{cyan}{(cos (n\theta) + isin(n \theta)) =  (cos\theta + isin\theta)^n}
  $$

- $ {e^{i\pi} = cos \pi + isin \pi = -1 + i \cdot 0 = -1}$



### 2. Euler's Identity

- ${e^{i\pi} + 1 = 0}$



### 3. Geometric Interpretation

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210217121534.png" alt="image-20210217121534199" style="zoom:67%;" />

- Express Complex Number as a vector in the complex plane ($z = a+ib$ as a vector)

- ${z = |z|(cos\theta + isin\theta)}$
- $\bar z$ is the mirror inflection of $z$ with respect to the real-axis(the x axis)

---



## 1.5. Theorem

### 1.5.1. Fundamental Theorem of Algebra

- Let $f(t)$ be a (nonzero) polynomial over the complex field $\mathbb{C}$. Suppose $f(t)$ has degree n, then 

  $f(t) = k(t-z_1)(t-z_2)(t-z_3)...(t-z_n)$ where $k,z_i \in \mathbb{C}$, it can split into linear factors

- **Explanation**

  - Let  $f(t) = a_nt^n + a_{n-1}t^{n-1}+....+a_1t + a_0$ (where $a_i \in \mathbb{C}$, they may be real or complex), then $f(t) = 0$ has **exactly** n solutions. (different solutions might appear multiple times). For example:
    $$
    (t-i)(t-i)(t-i)....(t-i) = 0
    $$
    where $t=i $  is a solution showing **n times, n solutions.**

  - My understanding: If we consider complex solutions, then for any **n degree** polynomial, we can find exactly **n solutions (roots).**



### 1.5.2. Conjugate Zero Theorem 

- If $(a+bi)$ is a zero of a **real** polynomial $f(x)$, then ==its conjugate $(a-bi)$ is also a zero of $f(x)$==

- If $a$ is a root of a real polynomial, then its conjugate $\bar a$ must exist as another root of the polynomial as well (complex roots always **paired up** for real polynomial)

  

  Proof by Cases

  ​	The statement **P(n)** is $\bar z^n = \overline {z^n}$

  - Fact
    - $\overline {z^2} = (\overline z)^2$
    - $\overline {z \cdot w} = \bar z \cdot \bar w$
  - Case 1: n is even (n=2k)
    - $\overline {z^{2k}} = \overline {(z^{2}) \cdot (z^2) \dots (z^2)} = \overline {z}^{2} \cdot \overline {z}^{2} \cdot \overline {z}^{2} ... \cdot \overline {z}^{2} $ for k times, which is $\overline {z}^{2k}$
  - Case 2: n is odd (n=2k+1, similar with the even case)
    - $\overline {z^{2k+1}} = \overline {(z^{2})^k \cdot z} = \overline {z}^{2k+1}$
  - Therefore, $P(n)$ holds true

  Since $\bar z^n = \overline {z^n}$, we can know that if $(a+bi)$ is a zero of a **real** polynomial, then its conjugate $(a-bi)$ is also a zero of $f(x)$
  $$
  a_n \bar z^n = a_n \overline {z^n} ,a_{n-1} \bar z^{n-1} = a_{n-1} \overline {z^{n-1}}, etc
  $$


---



## 1.6. Complex Zero (Roots) of Real Polynomials With Degree 2

### 1.6.1. Theorem

​	Let $ax^2+bx +c = f(x)$ such that $a,b,c \in \mathbb{R}$.  Suppose that $f(z) = 0$. Then $f(\bar z) = 0$. $f(x)$ is a **real** polynomial, which means that all its coefficients are **real numbers** 

**Interpretation:** If $z$ is a root of a degree 2 polynomial, then $\bar z$ must be a root of the real polynomial as well in order to keep all coefficient as **real numbers**

### 1.6.2. Proof

​	Let $z = r+is \in \mathbb{C}$ such that $f(z) = 0$, which is same as 

​	$f(r+is) = a(r+is)^2 +b(r+is) +c = 0$

​	**Show that:** 

​	$f(\bar z) = f(r-is) = a(r-is)^2+b(r-is)+c=0$ holds true

​	**First** We observe that:

​	$\overline {z^2} = \overline z^2 = \overline {(r+is)^2}$

- Proof (Let z = r+is)

  ​		$z^2 = r^2-s^2+2rsi,  \overline {z^2} = (r^2-s^2)-2rsi$

  ​		$\overline z = (r-is), (\overline {z})^2= (r^2-s^2)-2rsi$

  ​		Therefore, $(\overline {z})^2=\overline {z^2} = (r^2-s^2)-(2rs)i $

  **We also know** If $A \in \mathbb{R}, \bar A = A$ so $\bar 0 = 0$

  **Then**:

  $f(z) = \overline {f(z)} = 0 = \bar 0$

  $\overline {f(z)} = \overline {az^2+bz+c} = \overline{az^2} + \overline {bz} + \overline c$ Since $a,b,c \in \mathbb{R}$, $\bar a = a, \bar b =b, \bar c = c$

  we can rewrite it as:

$$
\overline {f(z)} = a \overline{z^2}+b \bar z + c
$$

​	   We also know that $\overline {z^2} = (\bar z)^2$:
$$
\overline {f(z)} = a \overline{z^2} +b \bar z +c = a (\overline z)^2 + b \bar z +c = f(\bar z)
$$
​	**Finally**
$$
 \overline {f(z)} = f(\overline z) = f(z)=0
$$
**Proof Done**

### 1.6.3. Conclusion

- We have shown that if $f(t)$ has degree 2 (a degree 2 polynomial) and $z$ is a solution (root) of $f(t=z) = 0$, then $f(t= \overline z) $ is also a solution (root) to $f(t=\bar z) = 0$. These $z, \bar z$ being solutions implies that they can be s of c ertain polynomials.

---



# 2. Vector Spaces

## 2.1. Concept Definitions



### 2.1.1. Field

- A **field** is a **set** on which <u>addition, subtraction, multiplication, and division</u> are defined and behave as the corresponding operations in $\mathbb{R}$ (not exactly the same operations!)

- In this class, **K** will denote a field which will be either $\mathbb{R} , \mathbb{C} , or \; F_2 = \{0,2\}$. 

- **Property:** A field $S$ must satisfy that:

  $\forall a \neq 0, \exists b$ such that $ab = 1$ where $a,b \in S$ 

  -  in $\Z$ (all integers), we can not satisfy such property, therefore $\Z$ is not a field

### 2.1.2. Geometric vectors

>  Arrows in $\mathbb{R}^2$

- 2 vectors are **equal** if they have the same **direction (parallel)** and the same **length**
- $u+v = v+u$ (commutative)
- $cu$ where $c \in \mathbb{R}$, c is called a **scalar**

### 2.1.3. Vector Space

#### 8 Axioms

- **Def:** A **vector space** **V** over a **field** **K** is a non-empty set with two operations:

  - V is the set of vectors and K is the set of scalars
  - addition: **+** or $\boxplus$
  - scalar multiplication: $\cdot $ or $ \boxdot$

  such that **(2 properties)**

  1. for each elements $x,y \in V$, $x + y \in V$ 

  2. $\forall x \in V,\; \forall \; a \in K, \;\text{such that: } ax \in V$

  Furthermore, the following **8 conditions** must be satisfied:

  - A field is said to be a vector space if it can **satisfies all these 8 conditions and the 2 properties above**

  1. $\forall x,y \in V, x+y = y+x$ **(commutativity)**
  2. $\forall x,y,z \in V, (x+y)+z = x+(y+z)$ **(associativity)**
  3. $\exists  \text{ an element in V denoted by } \vec{0} \text{ such that } \forall x \in V, x+ \vec{0}= \vec{0}+x = x$, such element is called as the **zero element**
  4. $\forall x \in V, \exists \text { an element } y \in V \text{ such that } x+y=\vec{0} $, such element **y** is called **additive inverse**
  5. $\forall x \in V, 1 \cdot x = x$, where $1 \in K$
  6. $\forall a,b \in K, \forall x \in V$, we have $(a \cdot b) \cdot x = a \cdot (b \cdot x)$
  7. $\forall a \in K, and \;\forall x,y \in V$, we have $a \cdot(x+y) = a \cdot x + a \cdot y$ **(distributivity)**
  8. $\forall a,b \in K, \forall x \in V$, we have $(a+b) \cdot x = a \cdot x + b \cdot x$
     - The **+** between $a,b$ is different from the **+** between $ax,bx$. They act the same way but not the same thing
     - The element of **K** are called **scalars** and the element of **V** are called **vectors**

- Every time the term **"vector"** is mentioned, we refer it as an element of the **vector space** instead of a geographical interpretation as an arrow

- **Examples:**

  1. We have $\mathbb{R}^n = \{(a_1,a_2,a_3...a_n)|a_i \in \mathbb{R} \forall i\}$, then

     - Addition +: 

       ​	$(a_1,a_2....a_n) +(b_1,b_2....b_n)=(a_1+b_1,a_2+b_2....,a_n+b_n)$

     - Zero Element: $(0,0,0,.....0)$ where we have **n** 0's.

       - In $\mathbb{R}^4$, $\vec{0} = (0,0,0,0)$ because $(1,2,3,4)+ \vec{0} = (1,2,3,4)$

     - Additive Inverse:

       - Given $(a_1,a_2,a_3,a_4) + (b_1,b_2,b_3,b_4) = \vec{0}$ and we want

         $(a_1+b_1,a_2+b_2,a_3+b_3,a_4+b_4) = \vec{0}$ which implies that
         $$
         \left\{{
         \begin{array}
          \\ a_1+b_1 = 0 \implies b_1=-a_1
          \\ a_2+b_2 = 0 \implies b_2=-a_2
          \\ a_3 + b_3 = 0\implies b_3=-a_3
          \\ a_4 + b_4 = 0\implies b_4=-a_4
         \end{array}
         }\right.
         $$

       - Ex: $(1,0,-2,5)$ has an additive inverse: $(-1,0,2,-5)$ 

### 2.1.4. Trivial Vector Space

The set $V=\{0\}$ is a vector space over $\mathbb{C}$, it is called the **Trivial Vector Space.**

**Proof with the 2 properties:**

1. $\forall x,y \in \{0\}, x+y = 0+0 =0\in V (\{0\})$, property 1 holds true
2. the field is $\mathbb{C}$, $\forall a \in \mathbb{C}, \forall x \in V$, we have $ax = a\cdot0=0 \in V$, property 2 holds true
3. **The 8 conditions can be checked as well ...**

**Property of the trivial vector space:** $\vec{0} + x = x+ \vec{0} = x$ for x being an element from the field

Therefore, we have proved that the set $V = \{0\}$ is a vector space over $\mathbb{C}$, we name it as the **trivial vector space**.



## 2.2. Important Remark

- A field is a vector space over itself
- Difference between a vector space and a field
  - **Vector space:** the multiplication operation between vectors is **NOT** part of the vector space structure
    - There is multiplication (dot product, cross product) of vectors, but they are not related to the **vector space structures**
  - **Field:** the multiplication operation **is part of** the **field structure**
- If $\mathbb{K}$ is a field such that $|\mathbb{K}|=+\infty$, then the following is true : The only $\mathbb{K}$-vector space $V$ such that $|V|<+\infty$ is $\{0\}$. 
  - **There is only 1 finite vector space, which is {0}**
  - This fact is proved using the property that $\alpha v\in V$ whenever $\alpha\in\mathbb{K}$ and $v\in V$.



## 2.3. Examples

1. **"Not a vector space":**

   Let $J = \{(x,y) | x\in \mathbb{R}, y\in \mathbb{R}\}, J = \mathbb{R}^2$, we define 2 operations:

   - $\boxplus:$ $(x_1,y_1) \boxplus (x_2,y_2) = (-x_1-x_2,y_1+y_2)$
   - $\boxdot: c \boxdot (x_1,y_1)  = (c \cdot x_1, c \cdot y_1)$

   **Questions: Is $J$ a vector space over $\mathbb{R}$ with respect to $\boxplus \; and \; \boxdot$?**

   <u>**Sol:**</u>

   We begin to verify if these operations are valid by checking **commutativity and associativity**

   - **commutativity:** check if $(x_1,y_1) \boxplus (x_2,y_2) = (x_2,y_2)\boxplus(x_1,y_1) $
     $$
     (x_1,y_1) \boxplus (x_2,y_2) =(-x_1-x_2,y_1+y_2) \\
     (x_2,y_2)\boxplus(x_1,y_1) =(-x_2-x_1,y_2+y_1)  \\
     $$
     we can see that $(x_1,y_1) \boxplus (x_2,y_2) = (x_2,y_2)\boxplus(x_1,y_1) $ is indeed true, therefore the commutativity holds for operation $\boxplus$

   - **associativity: ** check if $(A \boxplus B) \boxplus C = A \boxplus (B\boxplus C)$

     Let $A=(x_1,y_1), B = (x_2,y_2), C = (x_3,y_3),$ $A,B,C \in J$
     $$
     \begin{align*}
     (A \boxplus B) \boxplus C &= (-(-x_1-x_2)-x_3, y_1+y_2+y_3)\\
     &=(x_1+x_2-x_3,y_1+y_2+y_3) \\
     A \boxplus (B\boxplus C) & = (-x_1-(-x_2-x_3),y_1+y_2+y_3) \\
     &=(-x_1+x_2+x_3,y_1+y_2+y_3)
     \end{align*}
     $$
     we can see that the associativity does not hold for operation $\boxplus$. Therefore,

     **<u>Ans:</u> $J$ is not a vector space** over $\mathbb{R}$ with the respect to operation $\boxplus$.

     

## 2.4. Functions (recall)

- **Define** the set of all (real) functions with domain $\mathbb{R}$ and values in $\mathbb{R}$. $f: \mathbb{R} \mathbb{R}ightarrow \mathbb{R}$. We denote this set by $F(\mathbb{R} ,\mathbb{R})$.

  In general, the set of functions from X to K is denoted by $F(X,K).$ $F(\mathbb{R} ,\mathbb{R}) - \{f:\mathbb{R} \mathbb{R}ightarrow \mathbb{R}\}$

- **such as:** cos, sin, ....

- **Define:**

  - addition of two functions: $(f+g)(x) = f(x) + g(x)$
  - scalar multiplication: $(cf)(x) = c(f(x)), with \; c\in \mathbb{R}$

  Then $F(\mathbb{R},\mathbb{R}) with$ + and $\cdot$ is a vector space over $\mathbb{R}$

- **Question: what is the zero vector in this V.S?**

  - <u>Ans:</u> ${\vec{0}} \in F(\mathbb{R},\mathbb{R})$ is the function that takes every $x \in \mathbb{R}$ to 0. ${\vec{0}(x)=0}\; \forall x \in \mathbb{R}$ (sometimes we write it in $0(x) = 0$)

- **Ex:** Let e, cos $\in F(\mathbb{R},\mathbb{R}), 3\in \mathbb{R}$, then we have
  $$
  3(e+cos)(x) = 3(e^x+cos(x))=3e^x+3cos(x)
  $$



## 2.5. Degree of polynomials

- **we have**
  $$
  \begin{align*}
  p(x) &= 3x^5 -x^2 +x -1 \\
  &= -1 +x -x^2+3x^5 \\ 
  &= -1+x-x^2+0x^3+0x^4+3x^5+0x^6 \dots \\
  \end{align*}
  $$
  until all coefficients are 0'suntil all coefficients are 0's

  $Deg(p) = \text{the highest power of x with a non-zero coefficient}$

  **<u>In general</u>**

  $p(x) = a_o + a_1x + a_2x^2 + \dots a_nx^n, a_n \neq 0$, then p has degree = n, we write deg(p) = n

  <u>**Ex:**</u>

  - $p(x) = 3x^0=3$, deg(p) = 0
  - $p(x) =0,$ deg(p) = $-\infty$ or $-1$ or no degree (we can use $-\infty$)

## 2.6. Unique Zero element theorem

**Show that:** Let V be a vector space, then the **zero element is unique,** in anther words, is there any other element (not the zero element) that performs the same function as the zero element in the vector space V?

- ==**Proof:**== Assume we have another zero element $\vec{0'} \neq \vec{0}.$ We know the basic definition of zero element is that $\vec{0} + x = x +\vec{0} = x$. Therefore:

  1. $\vec{0} + \vec{0'} = \vec{0'}$ with $x = \vec{0'}$
  2. $\vec{0'} + \vec{0} = \vec{0}$ with $x=\vec{0}$

  since $\vec{0'}, \vec{0} \in V$, they are commutative, which means that  $\vec{0} + \vec{0'} = \vec{0'} + \vec{0} \implies \vec{0'} = \vec{0} $ which is contradictory to our assumption. Therefore, there must be a unique zero element in a vector space.

# 3. Subspaces

## 3.0. Recall Basic Definitions

### 3.0.1. Linear Combination

A vector(element) **v** in a vector space $V$ over a a field $K$ , is a linear combination of $v_1,v_2...v_n \in V$ if $\exists c_1,c_2...c_n \in K$ such that 

**v** $=c_1v_1 + c_2v_2 + ... c_nv_n$

### 3.0.2. Vector Space Definition

​	If a set $V$ with an addition ${+}$ and scalar multiplication $\bullet$ over a field $K$ is a vector space, then it satisfies:

1. the 8 axioms (see above)

2. $\forall x,y \in V, x+y \in V$. In text, we say it is **closed under addition** or **closure under addition**

3.  $\forall x \in V, \forall c \in K, c \cdot x \in V$. In text, we say it is **closed under scalar multiplication** or **closure under scalar multiplication**

    In fact, **any linear combination** of elements of $V$ is an element of $V$ itself.



## 3.1. Subspaces Definition and Theorem

### 3.1.1. Definition

Let **V** be a V.S over a field K, and let $W \subseteq V$ be a subset. If W is itself a V.S with respect to the **same operations** **as V** and over the same field, then **W is a <u>subspace</u>.**

### 3.1.2. Theorems

#### Thm 1: 3 Conditions of Subspace

> `This is why we do not need to prove 8 axioms again`
>
> Let V be a V.S with respect to +, $\cdot$, K, and $W \subseteq V$ be a subset. Then $W$ is a subspace **if the following holds**:

1. $\forall x,y \in W, x+y \in W$ (closure under addition)
2. $\forall x \in W, \forall c \in K, cx\in W$ (closure under scalar multiplication)
3. $\vec{0}_v \in W$ (the zero vector of V must be in W, this is just a **guarentee that W is not a empty set** $W \neq \O$, if it is empty then it can not be a vector space, ofc not subspace)

##### Proof

 **Assumption:** The operations in **W** (add & multiply) are **induced from V**

> **In V**, we have $1.x+y \in V, 2.\;c \cdot x \in V$ where $x,y\in V, c\in K$. 
>
> Similarly, **in W**, we expect $1.a+b\in W, 2.\;z\cdot a\in W$ where $a,b \in W, z \in K$            where $+ , \cdot$ **should work the same in V and W** 
>
> If we have operations in **W** that act completely differently from the operations in **V**, then W can not be a subspace
>
> - **Ex:** 
>   - define $+: (x,0) +(y,0) = (x+y,0)$ in $V$
>   - define $+: (x,0) + (y,0) = (x^y,0)$ in $W\subseteq V$
>   - Then we have 2 completely different $+$ operations, so $W$ can not be a subspace of $V$ for sure
>
> In another word, W is closed under **addition** and **scalar multiplication** defined in **V**

**Then we need to prove the 8 axioms given the assumption of induced operations:**

1. Let $x,y \in W$, we need to show $x+y = y+x:$ 
   - Since x+y = y+x in V, this property is inherited by virture of being inside V (any 2 elements in W must be in V since $W \subseteq V$)
2. Similarly, $\forall x,y,z \in W, (x+y)+z = x+(y+z)$ (inherited)
3. $0_v \in W$ **by assumption**
4. Let $x \in W$, need to find an element $y \in W$ such that $x+y = 0_v$
   - we know that $x+y = 0_v, \; with \;y \in V$. Since $x \in W, 0_v \in W$, then $y \;must\; \in W$ as well. (will be proved in Assignment 2)
5. $\forall x \in W, 1 \cdot x = x$ 
6. $(ab)x = a(bx)$
7. $a(x+y) = ax +ay$
8. $(a+b)x = ax +bx$

**Note:** axioms 5 to 8 are all inherited from $V$ , which can be stated in the assignment, no need to prove step by step again.



##### Consequence

If $W\subseteq V$ is <u>non-empty,</u>and <u>closed under addition</u> and <u>scalar multiplication</u>, then $W$ is a subspace.

**proof:** 

​	Since $W \neq \O,$ there exists an element $x \in W.$ Since W is closed under scalar multiplication, $0 \cdot x = 0_v \in W$. Now apply the previous theorem because we have:

1. closure under addition
2. closure under scalar multiplication
3. $0_v \in W$

Therefore, as same as the proof above.

---

#### Thm 2: Intersection between Subspaces is Subspace

Let V be a VS over  K, and $W_1, W_2$ be two **subspaces.** Then $W_1 \cap W_2$ is a **subspace.** **(the intersection of 2 subspaces is also a subspace)**

##### Proof

> **Recall:** for $W_1 \cap W_2$ to be a subspace, it must satisfy the following **3 conditions:**
>
> 1. $W_1 \cap W_2 \neq \O \iff 0_V \in W_1 \cap W_2$ (show **either side** of this condition is good)
> 2. $\forall x,y \in W_1 \cap W_2, x+y \in W_1 \cap W_2$ 
> 3. $\forall c \in K, \forall x\in W_1 \cap W_2, cx\in W_1 \cap W_2$

1. Since $W_1,W_2$ are both subspaces, then we have $0_V \in W_1, 0_V \in W_2$. Based on the definition of intersection (A is to be **in the intersection of B,C** if $A\in B$ amd $A\in C$), we can say that $0_V \in W_1 \cap W_2$

2. Let $x,y \in W_1 \cap W_2$. Because $x ,y\in W_1 \cap W_2,$ then $x,y$ must $\in W_1$ (definition of intersection). $W_1$ is a subspace, therefore we can write $x +y \in W_1$. Similarly, $x+y \in W_2$, therefore $x+y \in W_1 \cap W_2$

3. Let $x\in W_1 \cap W_2$ Let $c \in K$, then $x\in W_1, x\in W_2$. Since $W_1,W_2$ are both subspaces, then $cx\in W_1, cx \in W_2$. Therefore, $cx \in W_1 \cap W_2$

   With all these 3 conditions being checked, the claim follows. (the statement holds true).

   

### 3.1.3. Example

![](https://dr282zn36sxxg.cloudfront.net/datastreams/f-d%3Aa0c672e0341e490ed6bbef05913e4f0a351d8697ddb01490b4986eed%2BIMAGE_THUMB_POSTCARD_TINY%2BIMAGE_THUMB_POSTCARD_TINY.1)

Let $V = \mathbb{R}^2, W = \{(x,0) \vert x\in \mathbb{R}\}$ **(the x-axis)** , show that $W$ is a subspace. (We assume the operation + and $\cdot$ are the usual operations in $\mathbb{R}^2$)

<u>**Sol:**</u>

1. since $x \in \mathbb{R}, 0_{\mathbb{R}^2} =(0,0) \in W$ 
   - **Note: **we can also prove this condition by showing **there exists at least one element** in W.
2. Let $(x,0), (x',0) \in W$, then $(x,0)+(x',0)=(x+x',0) \in W$, therefore $W$ is closed under addition
3. Let $(x,0) \in W, c\in \mathbb{R}$, then $c(x,0) = (cx,0) \in W$, therefore $W$ is closed under multiplication

With all these 3 conditions met, we can conclude that $W$ is a subspace.



# 4. Spanning Sets

## 4.1. Concept Definitions

### 4.1.1. Spanning Sets

Let **V be a vector space** over a **field K**, and let **S be a subset** **of V**, then

**Span(S)** is the set of all linear combinations of elements of S:
$$
Span(S) = \{a_1v_1+a_2v_2....+a_nv_n\;|\; a_i \in K,  v_i \in S  \}
$$
**<u>Exp</u>** Take $V = \mathbb{R}^3$ under +, $\cdot$ and over field $\mathbb{R}$

Let $S = \{(1,1,0),(1,2,3)\}$, then: $Span(S) = \{a_1(1,1,0)+a_2(1,2,3) \;|\; a_1,a_2 \in R\}$

#### Remarks

1. If $S= \emptyset,$ then $Span(S) = \{0_V\}$ (The definition, just accept it)

2. we say that a vector $v\in Span(S)$ if $v=a_1v_1+a_2v_2+...a_nv_n$ for $a_i \in K, v_i \in S$ (if we can write v as a linear combination of the elements in S, we say that it is in $Span(S)$)

3. $Span(S)$ is a subspace of V

   ==**Proof:**==

   1. $0_V \in Span(S)$ because:

      1. if $S \neq \emptyset$, then $\exists\; x\in S $ such that $0 \cdot x = 0_V \in Span(S)$ 

         (The $a_i \in K$ can be 0, which means it is possible to form a linear combination of $0_V$ with element $x \in S$)

      2. if $S = \emptyset$, then by definition, $Span(S) = \{0_V\}$. ($\{0_V\}$ is a subspace itself)

   2. $Span(S)$ is closed under addition because:

      if $x,y\in Span(S),$ then 
      $$
      x = a_1v_1+a_2v_2+...a_nv_n \\
      y = b_1v_1+b_2v_2+...b_mv_m
      $$
      where $a_i, b_j \in K, v_i,v_j \in S$ 

      $m,n$ might be different, but we can always pair them up by plusing more 0-coefficient terms ($b_{m+1},b_{m+2}... =0$):
      $$
      y = b_1v_1+b_2v_2+....b_mv_m+b_{m+1}v_{m+1}+...b_nv_n
      $$
      Then we can write: 
      $$
      x+y = (a_1+b_1)v_1 +(a_2+b_2)v_2 +....(a_n+b_n)v_n
      $$
      where $a_i +b_j \in K$, therefore $x+y$ is a new linear combination of S, which implies that $x+y \in Span(S)$

   3. If $x\in Span(S),$ then $x = a_1v_1+a_2v_2+....+a_nv_n$, let $c \in K$, then
      $$
      cx = c(a_1v_1+a_2v_2+....+a_nv_n)=ca_1v_1+ca_2v_2+....+ca_nv_n
      $$
      where $ca_i \in K$, therefore $cx \in Span(S)$

   **Therefore:** $Span(S)$ is a subspace of V, where $S \subseteq V$



# 5. Linear Independence and Dependence

## 5.1. Concept Definitions

### 5.1.1. Linear Dependence

- Linear Dependence **(LD)**

Suppose that $V$ is a vector space and that $v_1,v_2...v_k$ ,$k$ is finite, are vectors in $V$ Then the set $\{v_1,v_2...v_k\}$ is **LD** if $a_1v_1 +a_2v_2+...+a_kv_k=0$ for some scalars $a_1,a_2....a_k$ and **at least one** of $a_1,a_2....a_k$ is **non-zero.** 

In short words, a set $S \subset V$ is said to be **LD** if there is a **non-trivial** linear relations between the elements in $S$ 

==Note: $det(A) \implies$ that A is linearly Independent==



#### Example

1. Let $S = \{v_1,v_2,v_3\}=\{(1,2,3),(3,5,7),(5,9,13)\}$

- Since $v_3 = 2v_1 + v_2$, then $v_3$ is not necessary. $Span(v_1,v_2) = Span(S)$
- Since $v_2 = v_3-2v_1$, then $v_2$ is not necessary. $Span(v_1,v_3) = Span(S)$
- Since $v_1 = \frac 12(v_3 -v_2),$ then $v_1$ is not necessary. $Span(v_2,v_3) = Span(S)$

Since one vector in $S$ can be expressed as a linear combination of the remaining vectors. we say that such set $S$ is said to be **Linearly Dependent (LD)**

2. Let $V = \mathbb{R}^3, +, \cdot, \;over \;\mathbb{R}$, the set $S= \{v_1,v_2\}=\{(1,0,0),(0,2,0)\}$ is said to be **Linearly Independent (LI)** because

   - $(1,0,0) \neq a(0,2,0),a\in \mathbb{R}$
   - $(0,2,0) \neq b(1,0,0),b\in \mathbb{R}$
   - $v_1$ can not be written as a linear combination of $v_2$, so do $v_2$

3. Let $V = \mathbb{R}^3, (+, \cdot, \;over \;\mathbb{R}, \text{(usually assumed)})$

   $S = \{(1,3,5),(2,5,9),(-3,9,3)\}$

   1. Is S LD?

      We need to find scalars $a_1,a_2,a_3$ with at least one of them nonzero such that: 
      $$
      a_1(1,3,5)+a_2(2,5,9) +a_3(-3,9,3)= 0_V \\
      (a_1,3a_1,5a_1)+(2a_2,5a_2,9a_2)+(-3a_3,9a_3,3a_3)=0_V
      $$

      $$
      \left(
       \begin{array}{ccc|c}
         1 & 2 & -3 &0 \\
         3 & 5 & 9 &0\\
         5 & 9 & 3 &0
        \end{array}
        \right)
      \stackrel{RREF}{=}
        \left(
       \begin{array}{ccc|c}
         1 & 0 & 33 &0 \\
         0 & 1 & -18 &0\\
         0 & 0 & 0 &0
        \end{array}
        \right) \\ a_1 = -33a_3, a_2=18a_3,a_3 \text{ is a free variable}
      $$

      

      then $a_3$ is a free variable, $a_3$ can be non-zero, which implies that there are non-trivial solutions of this system, we can let $a_3$ be whatever we want.

      - **trivial solution:** $a_1,a_2,a_3 = 0$ is one solution of the augmented matrix

      To be more specific, let $a_3 = 1, a_1=-33a_3=-33, a_2=18a_3=18$, which is a **non-trivial solution**, then we have:
      $$
      \begin{align}
      a_1(1,3,5)+a_2(2,5,9) +a_3(-3,9,3)
      &= -33(1,3,5)+18(2,5,9)+(-3,9,3)  \\
      &= (-33,-99,-165)+(36,90,162)+(-3,9,3) \\
      &=(0,0,0) = 0_V
      \end{align}
      $$
      Therefore,the fact that we are able to find solutions of the augmented matrix **implies** that $\{a_1,a_2,a_3\}$ is **LD**.

### 5.1.2. Linear Independence

**Def:** Suppose that $V,+,\cdot, K$ is a vector space. Then the set of vectors $S=\{v_1,v_2...v_k\} \subset V$ is **Linearly Independent (LI)** if we can obtain $a_1v_1+a_2v_2+....a_kv_k = 0_v$ when scalars $a_1=a_2=...a_k = 0 \in K$ **(The only solution of the system is a trivial solution).**

#### Example

1. V = $\mathbb{R}^2,+,\cdot, \mathbb{R}$, $S = \{(1,0),(0,1)\}$ **Is S LI?**

   **Sol:** If S is LD, then we should have
   $$
   a_1(1,0)+a_2(0,1) = 0_v \\
   \implies a_1+0 = 0, 0+a_2 = 0
   $$
   **Therefore,** $a_1,a_2$ must be 0 for the equation to hold, S is LI.

2. $V = \mathbb{R} ^3,+,\cdot, \mathbb{R}, S = \{(1,2,3),(3,2,9),(5,2,1)\}$. **Is S LI?**

   **only scalars $a_1,a_2...a_k \in K$ such that Sol:** assume we have

   $a_1(1,2,3) + a_2(3,2,9)+a_3(5,2,-1) = (0,0,0)$ $\implies\left\{\matrix{a_1+3a_2+5a_3=0
   \\2a_1+2a_2+2a_3=0
   \\3a_1 + 9a_2-a_3 = 0} \right.$

   which is an augmented matrix <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210215113547.png" alt="image-20210215113546908" style="zoom: 67%;" />

   

   we use RREF, then we get <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210215113608.png" alt="image-20210215113608607" style="zoom:67%;" />

   

   Which implies that $a_1=a_2=a_3=0$, therefore S is LI.

3. Let $P(\mathbb{R})$ be the vector space of all real polynomials. Let:

4. $$
   S = \{1+3x+2x^2, 3+x+2x^2,2x+x^2\}
   $$

   Is S LI?

   $a_1(1+3x+2x^2) + a_2(3+x+2x^2) + a_3(2x+x^2)\\=a_1+3a_1x+2a_1x^2 + 3a_2+a_2x+2a_2x^2 + 2a_3x + a_3x^2\\= (a_1+3a_2) + (3a_1+a_2+2a_3)x+(2a_1+2a_2+a_3)x^2 \\ = 0 + 0x + 0x^2$
   $$
   \left \{
   \begin{array}
   \\a_1+3a-2 = 0
   \\3a_1+a_2+2a_3=0
   \\2a_1+2a_2+a_3 = 0
   \end{array}
   \right.
   $$
   By solving this linear system, we can see that $a_2$ is a free variable, which measn we have infinite many solutions, so there might be a non-trivial solution, therefore S is not **LI, its LD.**

### 5.1.3. Remakrs

1. Suppose $S= \{v_1,v_2,v_3..v_n\}$ Suppose that one of the vectors $v_i = 0_V$. Then $S$ must be **LD** because the coefficient in front of $v_i$ is not limited to 0.

   **Any set containing the zero vector must be LD.**

2. If $v \neq 0_v$, then $\{v\}$ is **LI**.

3. If $S_1 \subset S_2\subset V, S_2$ is LI, then $S_1$ is also LI b . 

4. If $S_1 \subset S_2 \subset V$ If $S_1$ is LD, then $S_2$ is LD.

---

# 6. Basis of a Vector Space

## 6.1. Concept Definitions

### 6.1.1. Basis

**Def:** Let V denote a VS and $S =\{u_1,u_2...u_n\}$ a subset of V. S is called a **basis** for V if the followings are true:

1. **S spans V**
2. **S is LI**

**Examples:**

1. $\mathbb{R}^2$, $S = \{(1,0),(0,1)\}$:

   1. $\forall v_i \in \mathbb{R}^2, v_i = x(1,0) + y(0,1), \; where\; x,y \in \mathbb{R}$, Thus S spans $\mathbb{R}^2$
   2. Show that S is LI. Because $a_1(1,0) + a_2(0,1) = (0,0)$, $a_1 = a_2 =0$, which is the only and the trivial solution, therefore S is LI.

   Thus, S is a **basis** for $\mathbb{R}^2$. In particular, it is called a standard basis for $\mathbb{R}^2$.

   In genenral, the **standard basis** for $\mathbb{R}^n$ will be $S=\{(1,0,0,.....0), (0,1,0,0,0,0,....0),...(0,0,0,0...,1)\}$ where there are **n vectors** in S, in each vector there is only 1 **one** and n-1 **zeros**

### 6.1.2.  Unique Linear Representation

**Def:** If V is a VS and B is an **ordered basis** of v, then we know that every vector $v \in V$ can be expressed a linea combination of the vectors of B in a **unique way.** 

In other words, $\exists$ scalars $c_1,c_2....c_n$ such that $v = c_1u_1+c_2u_2+..c_nu_n$, which can be represented as an **n-tuple vector** as $(c_1,c_2,....c_n)$.

**Exp:**

In $\mathbb{R}^2$ , let there be one basis:

$B = \{u,u'\}$, where $u,u'$ are vectors in $\mathbb{R}^2$. Then any point $v \in \mathbb{R}^2$ can be expressed in a way such that
$$
v = au+a'u', a,a' \in \R^2
$$
The basis itself does not have an order. 

**But their order will matter if we decide to describe a coordinate in $\mathbb{R}^2$. **

Given a random point in $\mathbb{R}^2,$ denoted as $p = au_1+a'u_2, \; u_1,u_2\in \{u,u'\}$  (both $u_1,u_2$ can be $u $ or $u'$)

- If we decide to make $u$ as point **p's first vector ** $u= u_1$, then we will have $p = au +a'u'$.  Then the **tuple representation** of such coordinate will be $(a,a')$
- On the other hand, if we decide to make **u' as** **p's first vector** $u' = u$, then we will have $p = au'+a'u$. Then the **tuple representation** will be $(a',a)$

![image-20210205180443524](https://gitee.com/ruoyu666/blogimage/raw/master/img/image-20210205180443524.png)

**Conclusion:** With **different ways of assigning the vectors order from basis,** we will obtain different **tuple representations** of the **same vector.** **(a',a) and (a,a') both describe the same point in $\mathbb{R}^2$, they are different tuple representations because we choose to assign their first vector to different vector in basis.**



## 6.2. Standard Basis

1. $P_2(\mathbb{R}):$ this is the V.S of real polynomials of degree $\leq 2$. The standard basis is $\{1,x,x^2\}$

   **Ex:** Any poly in $P_2(\mathbb{R})$ can be expressed as a linear combination of $\{1,x,x^2\}$
   $$
   f(x) = 2x^2+2x+1 = 2(x^2)+2(x)+1(1)
   $$
   **In general,** $P_n(\mathbb{R})$ has basis $\{1,x,x^2...x^n\}$, and $P(\mathbb{R})$ is the V.S of all polynomials, the standard basis of $P(\mathbb{R})$ will be inifinite.

2. $M_{n\times m}(\mathbb{R})$ is the VS of $n \times m$ matrices with real entries.

   **Ex:**

   ![image-20210215113814289](https://gitee.com/ruoyu666/studyimg/raw/master/images/20210215114205.png)

   This has the following standard basis:

   ![image-20210215113837017](https://gitee.com/ruoyu666/studyimg/raw/master/images/20210215113837.png)



## 6.3. Theorems

### Thm 1: Unique Linear Combination with basis

Let V be a VS and $S = \{u_1,u_2...u_n\}$ is a basis of V. Then every vector of V can be written in a **unique way** as linear combinations of vectors of $S$.

==**Proof:**==

Suppose that $v \in V$ can be expressed in **two different ways** in terms of $u_1,u_2,u_3...u_n$ 

Then $\exists c_1,c_2....c_n \in K$ such that :

1. $v = c_1u_1 +c_2u_2+....c_nu_n$
2. $v = d_1u_1 +d_2u_2+....d_nu_n$, $\exists d_1,d_2....d_n \in K$ such that at least one $d_i \neq c_i$ (assuming we have 2 different equations) 

So
$$
c_1u_1 +c_2u_2+....c_nu_n = d_1u_1 +d_2u_2+....d_nu_n \\
(c_1-d_1)u_1 + (c_2-d_2)u_2 +.....(c_n-d_n)u_n = 0
$$
 But we know that $S$ is **Linearly Independent**, therefore we must have

$c_1-d_1 = c_2-d_2 =...c_n-d_n=0$ to obtain the only solution being the trivial solution. 

Therefore $c_i=d_i$, we conclude that elements of V can **only be expressed in a unique way** in terms of a basis.

**Remark:** we say that a vector $v \in V$ has a **unique** **representation** with respect to the basis S. The scalars used in the linear combination are called as **the coordinates** of the vector



---



### Thm 2: Bases have same dimension

Let V be a VS such that **one basis has m vectors** and **another basis has n vectors.** Then:
$$
m=n
$$
**==Proof:==** In the textbook `Theorem 4.12`

---

### Fact 1: Add vector that is not in span(S) to basis gives basis

[Theorem 3](###Thm 3 (Using Fact 1))

Let V be a VS, suppose that $S=\{v_1,v_2....v_n\} \in V$ **be LI.** If w is any vector of V, which is not in **span(S),** then $S'=\{v_1,v_2....v_n,w\}$ **is LI too.**

> In other words, if **S (is LI) does not span the entire VS V, (meaning there is some vector `w` can not be obtained by span(S)),** we can add that vector `w` to S to form a new set S', which is also **LI.**

**Main idea:**

- Since w is not in span, w can not be expressed as a linear combination of vectors in S. And we know S is LI already, then adding w to S will not change the fact that it is still LI.

---

**<u>Proof (by contradiction):</u>** 

<u>Assumption:</u> Let $w \notin span(S)$, and **suppose S' being LD.** Then $\exists$ scalars $a_1....a_n,b$ **not all 0**, such that $a_1v_1 +....a_nv_n+bw = 0_V$

1. Case 1: If **b = 0**, then we will obtain:
   $$
   a_1v_1 +a_2v_2+....a_nv_n = 0_V
   $$
   where **at least one of $a_i$ is non-zero**, which makes the set $S$ LD, causing contradiction.

2. Case 2: If ${b \neq 0}$, then we will have:
   $$
   a_1v_1 +a_2v_2+....a_nv_n = -bw \\
   w = \frac {-1}b (a_1v_1 +a_2v_2+....a_nv_n)
   $$
   which implies that **w can be written as a linear combination of elements of S,** which means $w \in span(S)$, which is contradictory to our assumption

**Conclusion:** Since b can not be 0 or non zero for our assumption to hold, we can tell that our assumption is wrong. **S' is LI.**



### Thm 3: Extend LI subset to a Basis of V

Knowing [Fact 1](###Fact 1)

Let $V \ne \{0_V\}$ be a finite-dimensional VS (non-zero, finite VS), then **every LI subset of V can be completed (extended) to a basis of V.**

**<u>Explanation:</u>**

Let dimV = 5, and $\{v_1,v_2\} \in V$ being LI. Then $\exists$ basis of V containing $v_1,v_2$ (might be something like:)
$$
\{v_1,v_2,w_1,w_2,w_3\}
$$
==**Proof:**==

Let $S =\{v_1,v_2...v_k\}$ be a **finite LI subset of V**, then we will have 2 cases:

1. $span(S) = V$, in such case, we are done, S is a basis of V already
2. $span(S) \neq V,$ then by **Fact 1**, we know that there exists a vector **w** $\in V$ but not in $span(S)$. We can then form a new LI subset $S'$ by add this **vector w to S**. Now we go back to check **case 1.**

By <u>repeating</u> these 2 cases, since V is a **finite dimensional VS,** we can eventually stop at some point when we have a basis after adding all vectors that are not initially in subset $S$. Hence, proof done.

# 7. Dimension of Subspaces

## 7.1. Concept Definitions

### 7.1.1. Dimension

**Def:** A ==VS== V is of finite dimension **n (or n-dimensional)** will have **dim(V) = n**, if V has a basis with **n elements**

<u>**Note:**</u> 

1. If V has a basis with infinitely many vectors, then it is **infinite-dimensional**
2. If $V=\{0_V\}$, then basis of V is $\O$ and **dim(V) = 0**

### Example 1

Let $V= \mathbb{R}^3$ and $W= \{(a,b,c) \in \mathbb{R}^3 | b = 2a, a,b,c \in \mathbb{R}\}$. What is the dimension of W? 

- **Sol:** It is easy to verify that W is a subspace, therefore we can use subspace property on W. 

  One way to find the dimension is to find the basis and count the number of vectors in it, then our goal is to find a **basis S for W (2 conditions need to check):**

  1. **S spans W:**

     Let $x \in W, b =2a$, then:

  $$
  x = (a,b,c)=(a,2a,c)= a(1,2,0)  + c(0,0,1)
  $$

  ​		Thus $S=\{(1,2,0),(0,0,1)\}$ spans W.

  2. **S is LI:**

     Set $a(1,2,0)  + c(0,0,1)=0_V$. then we have
     $$
     \left\{
     \matrix{
     a+0=0\\
     2a+0=0\\
     c=0}
     \right.
     $$
     which leads to $a=0, c=0$. Therefore S is LI.

  3. **Conclusion:** We have shown that $S=\{(1,2,0),(0,0,1)\}$ is a basis of W, then **dim(W) = 2** since S has only 2 vectors inside.

---



### Example 2

Let $V= M_{2\times2}(\mathbb{R})$ and W be the subspace of **symmetric matrices**. Find **dim(W)**

> **Recall: A is symmetric if **$A = A^T$

​		**Sol:** Let  $ A= \left( \matrix{ a & b\\  c& d } \right) \in W $, so $A = A^T \implies \left( \matrix{ a & b\\  c& d } \right) = \left( \matrix{ a & c\\  b& d } \right) \implies c=b$, a,b are free variables

​		We can write $A= \left( \matrix{ a & b\\  c& d } \right)= \left( \matrix{ a & b\\  b& d } \right) = a\left( \matrix{ 1 & 0\\ 0& 0 } \right)+b\left( \matrix{ 0 & 1\\ 1& 0 } \right) + d\left( \matrix{ 0 & 0\\ 0& 1 } \right)$

​		Then $S = \left\{\left( \matrix{ 1 & 0\\ 0& 0 } \right), \left( \matrix{ 0 & 1\\ 1& 0 } \right), \left( \matrix{ 0 & 0\\ 0& 1 } \right)\right\}$ **spans W.**

​		**S is LI** because $a=b=c=0$ after we solve that $a\left( \matrix{ 1 & 0\\ 0& 0 } \right)+b\left( \matrix{ 0 & 1\\ 1& 0 } \right) + d\left( \matrix{ 0 & 0\\ 0& 1 } \right) = \left( \matrix{ 0 & 0\\ 0& 0 } \right)$

​		Therefore, S is a basis of W, **dim(W) = 3.**

 



# 8. Sum and Direct Sum of Subspaces

## 8.1. Concept Definitions

### 8.1.1. Sum

**Def:** Let V be a VS, and W,U are subspaces of V.
$$
U+W=\{u+w | u\in U, w\in W\}
$$
**Note:**

1. Since $0_V \in W, 0_V\in U$ then we might have $u+0_V, v+0_V \in U+W$, which implies $\matrix{1.W\subset W+U \\ 2.U \subset W+U}$
2. **Commutativity:** $U+W = W+U$

### 8.1.2. Direct Sum

**Def:** Let V be a VS, and ==W,U are subspaces== of V. $U+W=\{u+w | u\in U, w\in W\}$. The vector space V is said to be the **Direct Sum** of its subspaces U and W, denoted by $ {V = U \oplus W},$ if every $v \in V$ can be ==written in **a unique way**== as $v = u+w$ with $v\in V, w\in W, u \in U$

==Remark:==

- Uniqueness of the sum implies that ==$0_V = 0_U + 0_W$ must be the unique only way== because if there are any other ways, it will not be unique.
- $V = U \oplus W \implies U \cap W = \{0\}$



**<u>Note:</u>** The symbol $\oplus$ is reserved for the direct sum.









## 8.2. Theorems

### Thm 1: Sum of subspaces is subspace

Let V be a VS and U,W be subspaces, then $U+W$ is also subspace. **Strightforward proof, seen in Tut.**



### Thm 2: Dimention theorem

Let V be a **finite dimensional VS** and U, W be subspaces of V. Then
$$
dim(U+W)=dim(U)+dim(W)-dim(U\cap W)
$$
==**Graphical Intuition:**==

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/image-20210206233108094.png" alt="image-20210206233108094" style="zoom: 80%;" />

==**<u>Proof:</u>**==

Let **dimU = m , dimW = n, dim(U+W) = r.** Let $\{v_1,v_2...v_r\}$ be a basis of $U\cap W$.

Since $U\cap W \subset U$, then we can extend $\{v_1,v_2...v_r\}$ to a basis of U: $\{v_1,v_2...v_r,u_1....u_{m-r}\} \implies$ Basis of U

Similarly, we can extend it to a basis of W: $\{v_1,v_2...v_r,w_1....w_{n-r}\} \implies$ Basis of W

**Then, let** $B = \{(v_1,v_2...v_r),(u_1....u_{m-r}),(w_1....w_{m-r})\}$ with size $|B| = r+ (m-r) +(n-r)=m+n-r$

Observe that **B spans U+W** because any element $\in U+W$ can be written as a linear combination with elements from B. 

**Now, we will show B is LI:** 

Let $\left \{\matrix {\begin{align} &(a_1v_1+a_2v_2 +...a_rv_r +b_1u_1+....b_{m-r}u_{m-r})+c_1w_1+...c_{n-r}w_{n-r} =0_V\\ &X=a_1v_1+a_2v_2 +...a_rv_r +b_1u_1+....b_{m-r}u_{m-r} \end{align}} \right.$, then we can rewrite:

$X = -c_1w_1-...-c_{n-r}w_{n-r} \implies X\in W$ because $c$ are constant and $w \in W,$ W is closed under addition

Since $X$ is a linear combination of elements from $U$, then $X \in U$. 

Therefore $\left.\matrix {X \in W\\ X\in U} \right\} \implies X\in U \cap W\implies (X=d_1v_1 +d_2v_2+...d_rv_r $ since $\{v_1,v_2...v_r\}$ is a basis of $U\cap W)$.

**Then, we plug in X back to the expression:** $d_1v_1 +d_2v_2+...d_rv_r + +c_1w_1+...c_{n-r}w_{n-r} =0_V$

Note that  $\{v_1,v_2...v_r,w_1....w_{n-r}\} $ is a **basis of W**, therefore we have shown that $d_1=d_2=...=d_r=c_1=...=c_{n-r} = 0, X=0_V,$

Since $X= a_1v_1+a_2v_2 +...a_rv_r +b_1u_1+....b_{m-r}u_{m-r} = 0_V\\ a_1=a_2=...b_1=...=b_{m-r}=0 \\ c_1=...=c_{n-r} = 0$, thus **B is LI** , which implies that **B is a basis with m+n-r elements,** which leads to:
$$
dim(U+W)= m+n-r=dim(U)+dim(W)-dim(U\cap W)
$$

### Thm 3: Direct Sum Conditions

The vector space V is the Direct Sum of its subspaces V and W **if and only if:**

1. V = U + W

2. $U \cap W = \{0_V\}$

   

==Proof:==

Name $A:V = U \oplus W $, $B:\left \{\matrix {\begin{align} &1. V= U+W \\ &2. U\cap W = \{0_V\} \end{align}} \right.$

We need to show $A\iff B $

1. Show $A \implies B$

   $V = U \oplus W \implies v= u+w, v\in V, u\in U, w\in W$ in a unique way, therefore $V = U +W$ is true

   Since $0_V \in U, 0_V \in W$,  let $x\in V$. Assume that $U \cap W \neq \{0_V\}$ and $x \in U \cap W$. Then we can say that $x \in U, x \in W$. We can then write $\left \{\matrix{x = x+ 0_V, x\in U, 0_V \in W \\x= 0_V+x, x\in W, 0_V \in U} \right.$

   There are 2 different ways to express x using elements from U and W (not unique), which contradicts our assumption. x must be $0_V$ for the above 2 equations to be the same **(unique)**. Therefore $U \cap W = \{0_V\}$

   

2. Show $B \implies A$

   Let $x \in V$, since $V = U+W$, we know $x= u+w, x\in V, u\in U, w\in W$. Assume there is a **different way** to express $x \in V, x = a+b, a\in U, b \in W$ and $a \neq u, b \neq w$. Since $x = x,$ then:
   $$
   u+w = a+b \implies
   u-a = b-w
   $$
   $(u-a)=(b-w) \in U, (b-w)=(u-a) \in W$, therefore $(u-a)=(b-w) \in U \cap W$. According to our assumption, $U \cap W = \{0_V\}$, then $u-a=b-w=0_V \implies u =a, b=w$ which shows that we can only write $x$ in an unique way of $u+w$

**Conclusion:** Thus, $A \iff B$.

---

# 9. Linear Mappings (Transformation)

## 9.0. Recalls

### 9.0.1. Function

==Function:== A function f from a set A to a set B is denoted by $f: A \to B$ is a rule by which each element of A is assigned to an element of B

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210209232141.png" alt="image-20210209232141425" style="zoom:50%;" />

==**A:**== the domain of f

==**B:**== the co-domain of f (target set of f)

==**range:**== the set of images under f

We have $f(1) = c$ and we call $c$ is ==the image of 1== and 1 is ==the pre-image of $c$==



<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210209232914.png" alt="image-20210209232914731" style="zoom:50%;" /> This is not a function because $f(5)$ is not defined (having 2 images)

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210209233548.png" alt="image-20210209233548082" style="zoom:50%;" /> This is indeed a valid function because $f(1),f(2),f(3)$ are all defined (even same image)





### 9.0.2. Onto / Surjective

==Def:== Let $f : A \to B$ be a function, Then $f$ is ==onto (or surjective)== if every element of B is an image for some element in A. In other words, $f$ is onto if and only if $range(f) = B$ (every output has some input pointing at it)



### 9.0.3. One-to-one / Injective

==Def:== A function $f: A \to B$ is ==one to one (injective, or 1-1)== if each element in $range(f)$ has a unique pre-image. In other words, $f(a) = f(b) \implies a= b$ (every output has exactly unique 1 input into it)

==Ex:==<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210209234940.png" alt="image-20210209234940210" style="zoom:33%;" />



### 9.0.4. Bijective

==Def:== A function that is both ==injective== and ==surjective== is called ==**bijective**==

==Ex:==<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216161919.png" alt="image-20210216161919822" style="zoom:50%;" />



---



## 9.1. Concept Definitions

### 9.1.1. Linear Mappings

==Def:== Let V and W be vector spaces over <u>the same field $ K$</u>. A mapping  $F: V \to W$ is called ==linear transformation== if the followings are satisfied:

1. F(x+y) = F(x) + F(y)  for ==all $ x,y \in V$==
2. F(cx) = cF(x) for ==all $x\in V, c \in K$==
3. **Note:** in a linear mapping F, F(0) = 0. It must map zero vector to zero vector.

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216162907.png" alt="image-20210216162907834" style="zoom:50%;" />



#### Examples

1. Let F: $\mathbb{R}^3 \to \mathbb{R}^3$, $F(x,y,z) = F(x,y,0)$, which is called the `projection` becase the `z-coordinate` is 0. 

   Is F linear ?

   ==Sol:==

   Let $v = (x,y,z), w=(x',y',z')$, then $F(v+w) = F((x,y,z) + (x',y',z')) = F((x+x',y+y',z+z')) = (x+x',y+y',0)$

   

   On the other hand:

   $F(v) + F(w) = F((x,y,z)) + F((x',y',z')) = (x,y,0) + (x',y',0)$ $ = (x+x',y+y',0)$

   Therefore: ==$F(v+w) = F(v) + F(w)$==

   Let $c\in \mathbb{R}$, then $F(c(x,y,z)) = (cx,cy,0) = c(x,y,0) = cF((x,y,z))$ ==$\implies F(cv) =cF(v)$==

   ==Therefore, F is linear==

   

   ---

   

2. Let $T: \mathbb{R}^2 \to \mathbb{R}^2$, $T((x,y) = (x+1,y+2)$. Is T linear?

   ==Sol:== 

   Let $v=(x,y), w =(x',y')$, 

   1. $ \left \{\matrix{T(v+w) = T((x+x',y+y')) = (x+x'+1,y+y'+2)\\  T(v) +T(w) = (x+1,y+2) +(x'+1,y'+2) = (x+x'+2,y+y'+4)} \right.$

   Since $T(v+w) \neq T(v) +T(w)$, so T ==is not linear.==

---

### 9.1.2. Isomorphism

==Def:== If F is a linear mapping, which is also <u>bijective</u>, then it is called an ==isomorphism.==

$F: V \to W$ is an isomorphism, then we say that V and W are ==isomorphic==



### 9.1.3. Kernel and Image

==Def:== Let V and W be vector spaces and let $T: V \to W$ be a linear map. 

1. We define the ==Kernel (or null space)== of T to be ==the set of all vectors of V, which map to $0_W$.== In other words, $Kernel(T) = N(T) = \{x \in V | T(x) = 0_W\}$

   <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216184811.png" alt="image-20210216184806576" style="zoom: 50%;" />

   ==All values in V such that they output $0_W$==, such set is called Kernel (null space)

   

2. We define the ==Image (or range)== of T denoted by $R(T),$ to be ==the set of vectors of W that are in the range of T.== In other words: $R(T) = \{ y\in W | \exists x\in V , T(x) =y\}$

   <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216185209.png" alt="image-20210216185209090" style="zoom:67%;" />

   Such green circle indicates the range of T, which simply means that ==all possible outputs of the function $T$==





#### Examples

1. Let V, W be VS, and let $I: V\to V$ such that $I(x) = x$, such function is called the ==Identity Map==

   Let $T_0: V \to W$ such that $T_0(x) = 0_W$ for all $x \in V$

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216190409.png" alt="image-20210216190409545" style="zoom: 70%;" />

- Range(I) = V ==AND== N(I) = $\{0_V\}$ (only the $0_V$ goes to $0_V$)
- Range$(T_0)$ = $\{0_W\}$. ==AND== N($T_0$) = V (all values in V plug in $T_0$ will result in $0_W$)

---



2. Let $T: \mathbb{R}^3 \to \mathbb{R}^2$

   $T((a_1,a_2,a_3)) = (a_1-a_2,2a_3)$, therefore $T((1,2,3)) = (-1,6)$. Then what is $N(T)$?

   **Sol:** we want $a_1-a_2 = 0, 2a_3 = 0 \implies a_1 = a_2, a_3 = 0$ 

   Therefore: $N(T) = \{(a,a,0) \in \mathbb{R}^3\}$

   

### 9.1.4. Nullity and Rank

==Def:== we define the following:
$$
dim(N(T)) = \text{nullity}(T) \\
dim(R(T)) = \text{rank} (T)
$$

- Nullity is the dimension of a Null space
- Rank is the dimension of the range

---



## 9.2. Theorems



### Thm 1: Vector Space and its Field are Isomorphic

Let V be an ==n-dimentional vector space== over a field K ($\mathbb{R}$ or $\C$). Then V and $K^n$ are ==isomorphic==

==Proof:==

Isomorphic implies: $\left\{ \matrix{\text{1. Bijective} \\ \text{2. Linearity}} \right.$, therefore we need to prove these 2 conditions:

1. ==Bijective==

   Let $B=\{v_1,v_2,...v_n\}$ be an ordered ==basis== of V. Then any $x \in V$ can be written in ==an unique way== of linear combination: $x = a_1v_1 + a_2v_2+....a_nv_n$

   Now define the map$\left\{ \matrix{F: V\to K^n\\a_1v_1+a_2v_2 +...a_nv_n \to (a_1,a_2....a_n)}\right. $ 

   $F$ is one to one (==injective==) because every term ($\{b_1,...b_n\}$) in $K^n$ has ==an unique element== $b_1v_1 + ... b_nv_n \in V$ 

   In addition, for every element $\{b_1,...b_n\}$) in $K^n$, $\exists x \in V$ such that $x=b_1v_1 + ... b_nv_n$, therefore F is onto (surjective, ==each output must has a corresponding input==)

   Thus, F is ==bijective==

2. ==Linearity==

   Let $x,y \in V$ $\left \{ \matrix{x = a_1v_1+....a_nv_n \\y = b_1v_1+....b_nv_n}\right.$
   $$
   F(x+y) = F((a_1+b_1)v_1 +(a_2+b_2)v_2+.....(a_n+b_n)v_n) \\= (a_1+b_1,a_2+b_2,....a_n+b_n)\\=(a_1,a_2,....a_n) + (b_1,b_2....b_n) \implies F(x) + F(y)
   $$
   Let $c\in V$
   $$
   F(cx) = F((ca_1v_1+ca_2v_2+....ca_nv_n))=(ca_1,ca_2....ca_n) = c(a_1,a_2...a_n) \implies cF(x)
   $$
   Therefore, we have shown the ==Linearity==

3. ==Conclusion:== $F:V \to K^n$ is ==isomorphic==

---



### Thm 2: If linear map: T(0~V~) maps to 0~W~  /  T(-v) = -T(v)

Let $T:V\to W$ be a linear mapping. Then: $\left \{ \matrix{1.T(0_V) =0_W \\ 2.T(inverse(v)) = inverse(T(v))} \right.$

==**Proof:**==

1. Let $z \in W$ such that $z + T(0_V) = 0_W$ (==z is the additive inverse of $ T(0_v)$==), then we have
   $$
   T(0_V) = T(0_V +0_V) =  T(0_V) + T(0_V)\text{ add z both sides} \\
   z+ T(0_V) = z+  T(0_V) + T(0_V) \\
   0_W = 0_W + T(0_V)\\
   T(0_V) = 0_W
   $$

​	==Therefore condition 1 is checked.== The $0$ in V has been mapped to the 0 in W. <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216175156.png" alt="image-20210216175156698" style="zoom:50%;" />

2. Let $x \in V,$ such that ==$x+y = 0_V$== $\implies$ y is the inverse of x

   and $z,T(x) \in W$ such that ==$z + T(x) = 0_W$== $\implies$ z is the inverse of T(x)

   Therefore, we need to show that $T(inverse(x)) = inverse(T(x)) \implies T(y) = z$ 
   $$
   T(x+y) = T(0_V) = 0_W \\
   T(x) + T(y) = 0_W\\
   z + T(x) + T(y)= z + 0_W \\
   0_W + T(y) = z \implies T(y) = z
   $$

---



### Thm 3: if linear map: N(T) and R(T) are subspaces

Let V,W be VS and $T: V \to W$ be a linear map. Then ==$N(T)$ is a subspace of V and $R(T)$ is a subspace of W.==

==**Proof**:==

- $N(T) \subseteq V$ is a subspace

  1. By [Thm 2](###Thm 2), we know that $T(0_V) = 0_W$, therefore $0_V \in N(T)$

  2. Let $x,y \in N(T)$, need to show $x+y \in N(T)$. Since $x,y \in N(T)$, $T(x) = T(y) = 0_W$

     Since $T$ is linear map, based on the [definition of linear mapping,](###9.1.1. Linear Mappings) we know that $T(x+y) = T(x) +T(y)$

     Since $T(x) + T(y) = 0_W,$ ==$T(x+y) = 0_W$==, thus $x+y \in N(T)$

  3. Let c be a scalar, and $x\in N(T)$

     Since $T(cx) = cT(x)$ (T is linear), $cT(x) = c0_W = 0_W = T(cx)$, therefore $cx \in N(T)$

  ==Conclusion:== Since ==1,2,3== holds, $N(T)$ is a subspace

  

- $R(T)$ is a subspace

  1. Since T is linear, $T(0_V) = 0_W$, $0_W$ is the image of $0_V$ in W, therefore $0_W \in R(T)$ 

  2. Let $y_1,y_2 \in R(T)$, need to show $y_1+y_2 \in R(T)$

     Since $ y_1,y_2 \in R(T)$, then $y_1,y_2$ are the images of certain element in V. Therefore:

     - $y_1 \in R(T) \implies T(x_1)=y_1, \exists x_1 \in V$
     - $y_2 \in R(T) \implies T(x_2)=y_2, \exists x_2 \in V$

     Notice that $T(x_1) + T(x_2) = T(x_1+x_2) = y_1+y_2,$ which impliese that $y_1+y_2$ is the image of $x_1+x_2$, thus $y_1+y_2 \in R(T)$

  3. Let c be a scalar, $y \in R(T)$, we need to show $cy \in R(T)$

     $y \in R(T) \implies T(x) = y, \exists x \in V$

     We know that $cT(x) =T(cx) =  cy,$ therefore we can tell that $cy$ is a image of $cx$, thus $cy \in R(T)$

  ==Conclusion:== Based on ==1,2,3,== we show that $R(T)$ is a subspace

Thus we have proved the Thm.

---



### *Thm 4: Dimension Thm* *

Let V, W be VS. Let $T: V\to W$ be a linear map. If ==V is finite dimensional.== Then we have the following:

- ==nullity(T) + rank(T) = dim(V)==

 

#### Proof

**==Proof:==** Since $N(T)$ is a subspace (known from [Thm 3](###Thm 3)), then $N(T)$ will have a basis $\{v_1.....v_k\}$. We can ==complete it to a basis of V== by adding some extra elements:
$$
A = \{v_1,v_2.....v_k, \textcolor{cyan}{v_{k+1},v_{k+2}....v_n} \}
$$
Now, we want to prove that $\textcolor{cyan}{S=\{T(v_{k+1}),T(v_{k+2})....T(v_n)\}}$ is a basis for $R(T)$, we need to show;

1. ==$S$ spans $R(T)$==

   Let $y \in R(T)$,then $\exists \;x \in V$ such that $T(x) = y$. Since $x \in V,$ we can write:
   $$
   x = a_1v_1+a_2v_2+....a_kv_k +a_{k+1}v_{k+1} +......+a_nv_n
   $$
   Therefore: 
   $$
   y=T(x) = T((a_1v_1+a_2v_2+....a_kv_k +a_{k+1}v_{k+1} +......+a_nv_n))\\
   =a_1T(v_1)+..a_kT(v_k)+\textcolor{cyan}{a_{k+1}T(v_{k+1}) + a_{k+2}T(v_{k+2})....+a_nT(v_n)}
   $$
   We know that ==$B = \{v_1.....v_k\}$ is a basis== ==of $N(T),$== then $v_1,v_2....v_k \in N(T) \implies T(v_1) =T(v_2) =..T(v_k) = 0_W$

   Thus:
   $$
   y = T(x) = \textcolor{cyan}{a_{k+1}T(v_{k+1}) + a_{k+2}T(v_{k+2})....+a_nT(v_n)}
   $$
   which is equivalent of saying $y \in span(S)$. Every element $y \in R(T)$ are $\in span(S)$, therefore we can say ==$S \text{ spans } R(T)$==



2. ==$S$ is LI==

   Let $b_{k+1}T(v_{k+1}) + .....+b_nT(v_n) = 0_W$ be a linear combination. Since T is linear, we can rewrite the linear combination:
   $$
   b_{k+1}T(v_{k+1}) + .....+b_nT(v_n) = T(b_{k+1}v_{k+1}) + .... +T(b_nv_n) = T(\textcolor{cyan}{b_{k+1}v_{k+1} + .....+b_nv_n}) = 0_W \\
   \text{Let } \textcolor{cyan}{b_{k+1}v_{k+1} + .....+b_nv_n} \text{ denote as } Z
   $$
   Since $T(Z) = 0_W$, we can say that $Z \in N(T) \implies Z$ can be written in terms of ==$B = \{v_1.....v_k\}$==(the basis of $N(T)$):
   $$
   Z = \textcolor{cyan}{b_{k+1}v_{k+1} + .....+b_nv_n} = c_1v_1+.....c_kv_k \;\;\; c_1,c_2...c_k \text{are scalars}\\ \implies c_1v_1+.....c_kv_k - (\textcolor{cyan}{b_{k+1}v_{k+1} + .....+b_nv_n})  = 0_V
   $$
   since $\{v_1,v_2.....v_k, \textcolor{cyan}{v_{k+1},v_{k+2}....v_n} \}$ is ==a basis of V,== $\{v_1,v_2....v_k,v_{k+1}....v_n\}$ are LI, which implies that $c_1 = c_2 ....=b_k=b_{k+1}  ...=b_n =0 \implies $ ==$b_k=b_{k+1}  ...=b_n =0$== ==must be the unique trivial solution of $b_{k+1}v_{k+1} + .....+b_nv_n  = 0_V$==. Then such ==unique trivial solution holds for:==
   $$
   T((b_{k+1}v_{k+1} + .....+b_nv_n))  = b_{k+1}T(v_{k+1}) + .....+b_nT(v_n) = 0_W
   $$
   That is why we can conclude that ==$S=\{T(v_{k+1}),T(v_{k+2})....T(v_n)\}$ is LI==

3. ==Conclusion:== $S=\{T(v_{k+1}),T(v_{k+2})....T(v_n)\}$ is a basis of $R(T)$



==Final Conclusion:==

Initially, we have $A = \{v_1,v_2.....v_k, \textcolor{cyan}{v_{k+1},v_{k+2}....v_n} \}$ ==as any random basis of V:== 
$$
dim(A) = dim (V) = \textcolor{orange}{dim( \{v_1,v_2.....v_k \})} + \textcolor{lime} {dim(\{v_{k+1},v_{k+2}....v_n\})}
$$

1. $\{v_1,v_2.....v_k \}$ is a basis of $N(T)$ because $N(T)$ is a subspace, then $\textcolor{orange}{dim(\{v_1,v_2.....v_k \}) = dim(N(T))=nullity(T)}$

2. $\textcolor{cyan} {\{T(v_{k+1}),T(v_{k+2})....T(v_n)\}}$ (the set of images of $\textcolor{cyan}{ \{v_{k+1},v_{k+2}....v_n\}} $ ) is indeed a basis of $R(T)$ (==which is the main goal of this proof==), then $\textcolor{lime}{dim (\{v_{k+1},v_{k+2}....v_n\}) = dim({\{T(v_{k+1}),T(v_{k+2})....T(v_n)\}}) = dim(R(T)) = rank(T)}$



By plugging in, we finally get: $dim(V) =\textcolor{orange}{nullity(T)} + \textcolor{lime}{rank(T)}$



#### Example

1. $T: \R^3 \to \R^5$ Can T be onto (surjective) ?

   ==Sol:== 

   In order for T to be onto, we need to have $range(T) = \R^5 \implies dim(range(T)) = dim(\R^5)=rank(T) = 5$ 

   

   By the [Dimension Theorem](###*Thm 4 (Dimension Thm)* *), we know that ==nullity(T) + rank(T) = dim(V)==, then $dim(\R^3) = nullity(T) + rank(T)$

   which is $3 = nullity(T) + 5$.

   Since $nullity(T)$ can not be negative, we know it contradicts the assumption. Therefore $T$ ==can not be onto.==

   **Note:** $ 0\leq nullity(\R^3) \leq 3$



---

### Thm 5: N(T) = {0~V~} iff T is one to one, both directions

Let V and W be VS, and $T: V\to W$ be linear, then ==T is one to one (injective) iff $N(T) = \{0_V\}$==

**==Proof:==**

1. $\implies$ 

   Knowing T to be one to one (injective). Let $x \in N(T)$, then $T(x) = 0_W$

   Since T is linear, then $T(0_V) =0_W$. Because T is injective, $0_W$ can only have one input pointing at it, which must be $0_V$ in this case. $N(T)$ can contain only one element, which is $x = 0_V$

   ==Thus $x = 0_V$, $N(T) = \{0_V\}$==



2. $\Longleftarrow$

   Knowing $N(T) = \{0_V\}$ ==(or nullity(T) = 0)==, Let $x,y \in V$ such that $T(x) = T(y)$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210216234228.png" alt="image-20210216234228852" style="zoom:67%;" /> 

   we want to show that ==x and y are in fact the same element==, in such way, we can show one to one (injective)

   we know $T(x) - T(y) = 0_W$ and T is linear

   therefore: $T(x)- T(y) = T(x-y) = 0_W$ as well, which implies that $x-y \in N(T)$

   But we know that $N(T) = \{0_V\}$, so $x- y = 0_V \implies x=y$, we have shown one to one.

   

3. ==Conclusion:== we have shown $\implies and \; \Longleftarrow$, therefore ==T is one to one (injective) $\iff$ $N(T) = \{0_V\}$==



---

# 10. Matrix Representation of Linear Maps

## 10.0 Recall Standard Basis

1. For $\R^3$, the standard basis is $\{(1,0,0),(0,1,0),(0,0,1)\}$
2. For $M_{2 \times2}(\R),$ it has standard basis<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210224133346.png" alt="image-20210218223557217" style="zoom:50%;" />

3. $P_2(\R)$ has standard basis $\{1,x,x^2\}$

## 10.1. Concept Definitions

### 10.1.1. Coordinate Vector

==Def:== Let $B = \{v_1,v_2...v_n\}$ be an **<u>ordered basis</u>** for a finite dimensional VS V. For $x\in V$, $\exists $ unique $a_1,....a_n$ such that $x = a_1v_1 +....a_nv_n$ we define the ==coordinate vector of x relative to $B$ by:==
$$
[x]_B = \left (\matrix{a_1\\a_2\\a_3\\ \vdots\\a_n} \right)
$$
==Example:==

Let $V = P_2(\R)$, $B = \{1,x,x^2\}$. Let $f\in V: f(x) = 4+6x-7x^2$, then
$$
[f]_B = \left (\matrix{4\\6\\-7} \right)
$$
so $f(x) = 4(1) + 6(x) -7(x^2)$ and it is only meaningful when we specified which ==basis we are using relative to (B in this case)==





### 10.1.2. Change of Coordinates Matrix

==Change between different bases==

Let V be a VS with bases $\beta  \; and\;\beta'$, then the change of bases is $[I]^{\beta'}_\beta$ where $I: V \to V$ is the ==identity map== ($I(x) =x$)

$I([x]_\beta) = [x]_{\beta'}$

#### Example

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210305184737.png" alt="image-20210305184737768" style="zoom:50%;" />

Linear transformation between $[x]_\beta \iff [x]_{\beta'}$ ==(changes of basis of the same VS)==

Let $V=\R^2, \beta = \{(1,1),(1,-1)\}, \beta' = \{(2,4),(3,1)\}$ be 2 bases of $\R^2$

1. Use $\beta,$ we write it in the matrix form: $ c = \left( \matrix{  1 & 1\\  1 & -1 } \right) $

   Then we use $c$ to multiply the ==standard basis of $\R^2$==

   - $c\left( \matrix{  1 \\ 0 } \right) =\left( \matrix{  1 & 1\\  1 & -1 } \right) \left( \matrix{  1 \\ 0 } \right) =  \left( \matrix{  1 \\ 1} \right) $, where $\left( \matrix{  1 \\ 0 } \right)$ is expressed in $\beta$ because $(1,1) = 1\cdot(1,1) + 0 \cdot(1,-1) = (1,1)$
   - $c \left( \matrix{  0\\ 1 } \right) = \left( \matrix{  1 & 1\\  1 & -1 } \right)\left( \matrix{  0 \\ 1 } \right)  =  \left( \matrix{  1 \\ -1} \right) $, similarly, $(1,-1) = 0\cdot (1,1) + 1 \cdot(1.-1) = (1,-1)$
   - What the ==c== can do it to: take the inputs from $\beta$ (1,0), (0,1) and outputs vectors in the standard word (outside of $\beta, \beta'$)
   - $c$ changes standard basis in $\R^2:\{(1,0),(0,1)\}$ into basis in $\beta =\{(1,1),(1,-1)\}$ 
   - $c^{-1}$ transpose does the opposite

2. Similarly, we write $c'$ using $\beta'$, $ c' = \left( \matrix{  2 & 3\\  4 & 1 } \right) $

   - $c'\left( \matrix{  1 \\ 0 } \right) =\left( \matrix{  2 & 3\\  4 & 1 } \right) \left( \matrix{  1 \\ 0 } \right) =  \left( \matrix{  2 \\ 4} \right) $
   - similarlly, $c'$ will take inputs from $\beta'$ and output to standard

3. ==NOTE==: Both c and c' are invertible (which means c^-1^ and c'^-1^ exists)

4. ==Therefore, if we need a matrix that takes inputs in  $\beta '$  and output something in  $\beta $, we will have:==
   $$
   \beta '  (\text{using c'})  \to standard (\text{using } c^{-1})  \to\beta
   $$
   $c^{-1} = \left( \matrix{  0.5 & 0.5\\  0.5 & -0.5 } \right)$ 

   Then, the matrix representation $Q$ of the change from $\beta'$ to $\beta$ can be found with:

   $c^{-1} \beta' =  \left( \matrix{  0.5 & 0.5\\  0.5 & -0.5 } \right)\left( \matrix{  2 & 3\\  4 & 1 } \right) = \left( \matrix{  3 & 2\\  -1 & 1 } \right)  = Q$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210305190330.png" alt="image-20210305190330843" style="zoom:33%;" />

   



### 10.1.3. Matrix Representation of linear mapping operation (transformation)

==Prenote==: Let $T: V \to W$ be linear. Let $\textcolor{orange}{\beta = \{v_1,v_2...v_n\}}$ be ==ordered== basis for V, $ \textcolor{cyan}{\gamma = \{w_1,w_2...w_m\}}$ be a ==ordered== basis for W. Then $\forall 1 \leq j \leq n$ and $\forall 1 \leq i \leq m$, there exists unique scalars $a_{ij}$ such that:
$$
T(\textcolor{orange}{v_j}) = \textcolor{cyan}{a_{1j} w_1 + a_{2j}w_2+......a_{mj}w_m}
$$
==Def:== Using the notation above, we call ==the $m \times n$ matrix== $A$ defined by $A_{ij} = a_{ij}$ as the ==Matrix representation of T in the ordered bases $\beta \text{ and }\gamma$==, and write 
$$
A = [T]^{\gamma}_{\beta}, \text{ where }T: V \to W
\\ \text{This denotes a linear transformation between standard basis from} \; \beta \to \; \gamma
$$
==Note:== If $\beta = \gamma$, instead of writting $[T]^{\beta}_{\beta}$, we write $[T]_{\beta}$.

- Let $\beta, \beta'$ be basis of V. Then there exists an invertible matrix, called as ==the change of basis matrix,== that changes coordinates of any vector expressed in $\beta$ to coordinates expressed in $\beta'$

==In short words, $$[T]^{\gamma}_{\beta}$$ is the matrix representation of "how to take inputs vectors in V and change them into vectors in W". It is a matrix representation of the **CHANGE**, such change can happen between 2 different basis of the **same vector space**==



#### Example

1. Let $T:\R^2 \to \R^3$ be linear $T(a_1,a_2)= (a_1+3a_2,0,2a_1-4a_2)$

   Let $\beta = \{(1,0),(0,1)\} \;\;\;\;\;\;\;\; \gamma = \{(1,0,0),(0,1,0),(0,0,1)\}$

   $T(1,0) = (1+3 \cdot 0,0,2-4\cdot0) = (1,0,2)\;\;\;\; T(0,1) = (3,0,-4)$

   Therefore, $[T]^{\gamma}_{\beta} = \left(\matrix{1&3 \\ 0&0\\ 2&-4} \right)$ It is $3 \times 2$ because we want a $3 \times 3$ as result. (==$(3\times 2) (2\times 3) = 3\times 3 $==) otherwise it is not $\R^3$

   **==Note:==** if we times some $2 \times 3$ matrix with such $[T]^{\gamma}_{\beta} $, then we are able to `perform the linear transformation from` $\R^2 $ to $\R^3$. 这个线性变化操作，作为matrix的表现形式，就是这个$[T]^{\gamma}_{\beta} $。

   ![image-20210320121625499](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320121625499.png) 横着两个，竖着三个，所以take input of 2 dimension into output to 3 dimensions

2. let $T: \R^3 \to \R^2$, $T(a_1,a_2,a_3) = (2a_1+3a_2-a_3,a_1+a_3)$

   Let $S_1 = \{(1,0,0),(0,1,1),(0,0,1)\}$ as standard basis of $\R^3$,  $ S_2 = \{(1,0),(0,1)\}$ as standard basis of $\R^2$, Find $[T]_{S_1}^{S_2}$ (change from S1 to S2)

   ==Sol:==

   $T(1,0,0) = (2,1), T(0,1,0) = (3,0), T(0,0,1) = (-1,1)$, then we obtain: $[T]^{S_2}_{S_1} = \left(\matrix{2&3 & -1\\ 1&0&1} \right)$ ![image-20210320121727306](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320121727306.png) 横着三个，竖着两个，所以take input of 3 dimension and output 2 dimension

   Let $\gamma = \{(1,1),(1,3)\}$ be a basis for $\R^2$, let $C  =  \left(\matrix{1&1 \\ 1&3} \right), C^{-1}  =  \left(\matrix{\frac32 &\frac{-1}2 \\ \frac{-1}2&\frac12} \right)  $, C will change vectors in $\gamma$ to vectors in $S_2$, and C^-1^ does the opposite, it changes vectors in $S_2$ to vectors in  $\gamma$, 

   <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210305193429.png" alt="image-20210305193428902" style="zoom:50%;" /> Such matrix multiplication gives the changes from $S_1$ to $\gamma$ 

   

   ​	$[T]_{S_1}^\gamma = C^{-1}[T]_{S_1}^{S_2} = \left(\matrix{\frac32 &\frac{-1}2 \\ \frac{-1}2&\frac12} \right) \left(\matrix{2&3 & -1\\ 1&0&1} \right)  = \left(\matrix{\frac 52 & \frac92 & -2\\ -\frac12 &-\frac32&1} \right)$

   ---

   Now, let's take another basis in $\R^3$: Let $\beta = \{(1,1,1), (1,0,0),(0,0,1)\}$

   We have the matrix A that changes from $\beta$ to $S_1$, then A^-1^ shoud change from $S_1$ to $\beta$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210305194931.png" alt="image-20210305194931418" style="zoom:35%;" />

   Then, the change from $\beta$ to $\gamma$ is caculated using <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210305195030.png" alt="image-20210305195030669" style="zoom:50%;" />

   ​                              
   $$
   [T]_\beta^\gamma = C^{-1}[T]_{S_1}^{S_2} A
   $$
   ==In short words:==

   This is used to solve the linear transformation in matrix form question. If we are asked to find such "matrix of linear transformation between a and b where $a\in V, b\in W$", there are few steps to follow:

   1. First of all, we need to find the standard basis of V and W, It is easy that we transform from a to standard basis of V and transfer from b to standard basis of W
   2. Then, it is also esay to find the transformation matrix from the standard basis of V to the standard basis of W
   3. With all these transformation among standard basis, we can build the relationship between $a$ and $b$, which are some non-standard basis of V and W.

#### Good Example To Review

Let T: $P_3(\R) \to P_2(\R)$ be linear such that: $T(f(x) ) = f'(x)$

$\beta = \{1,x,x^2,x^3\}$,               $\gamma = \{1,x,x^2\}$ are standard basis of $P_3(\R),  P_2(\R),$

We need to find the ==matrix representation of $[T]^{\gamma}_\beta$==

Then we have:
$$
T(1) = (1') = 0 \cdot 1 +  0 \cdot x + 0 \cdot x^2\\
T (x) = (x') = 1 \cdot 1 + 0 \cdot x + 0 \cdot x^2 \\
T(x^2) = (x^2)' = 0 \cdot 1 + 2 \cdot x + 0 \cdot x^2\\ 
T(x^3) = (x^3)' = 0 \cdot 1 + 0 \cdot x + 3 \cdot x^2
$$

$$
[T]^\gamma_\beta = \left( \matrix{0&1&0&0\\ 0&0&2&0 \\ 0&0&0&3}\right) \textcolor{orange}{\text{ The whole matrix is a representation of "derivative" operation}}
$$

![image-20210320122105972](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320122105972.png) since we are changing from $T:$$P_3(\R) \to P_2(\R)$, where standard basis has size changed from 4 to 3 (by studying the change on basis, we know the change of the whole vector space). Horizontally, there are 4 numbers and vertically there are 3, thus we take a input of 4 dimensions into an output of 3 dimensions. ==Such transformation matrix (obtained from studying the change of basis) can take input of any vector in 4 dimension and change it into a 3 dimension output.== It is called the matrix representation of linear maps.



​	Let $p(x) = 2 +3x-x^2+2x^3 \in P_3(\R)$,  	$T(p(x)) = p'(x) = $ $\textcolor{cyan}{3-2x+6x^2} ( \text{by hand})$



​	$[p(x)]_\beta = \left (\matrix{2\\3\\-1\\2} \right)$, then we do matrix multiplication: $\left( \matrix{0&1&0&0\\ 0&0&2&0 \\ 0&0&0&3}\right)  \left (\matrix{2\\3\\-1\\2} \right) =  $ $\textcolor{cyan}{\left (\matrix{3\\-2\\6} \right)}$



​	We can see that the solutions maintained in both ways are the same.



​	In such way, we can still maintain the solution of $T(p(x))$ by matrix multiplication between the ==matrix representation of derivative and the function itself==



​	==Note:将求导的过程矩阵化，从而可以implement in computer 来进行求导运算。==

---

#### A3 Example

<img src="C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320131154436.png" alt="image-20210320131154436" style="zoom: 50%;" />

==Q (b):==

1. By using $T(f(x))$ on every element in $\beta$, which is a basis of $P_2(\R)$. Then we obtain a basis in $M_{2 \times 2}(\R)$, which is the set of $\mu =\{m_1,m_2,m_3\}$, each $m_i$ consists 4 numbers, and where:

   1. $m_1 =$![image-20210320131407495](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320131407495.png)
   2. $m_2=$![image-20210320131411819](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320131411819.png)
   3. $m_3=$![image-20210320131435560](C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210320131435560.png)

2. Then, we need to find the transformation matrix such that it is able to

   ==change from $\beta = \{1,1+x,1+x^2\}$ to $\mu=\{m_1,m_2,m_3\}$== , input 3 numbers and output 4 numbers, thus 横3竖立4的matrix. Each element in $\mu$ can be expressed as a linear combination of the bases of $\alpha$. Such expression is the ==transformation matrix== These standard bases happen to be the basis in $\alpha$. Thus, it shows how the linear transformation ends up being.

   ---

   

### 10.1.4. Composition of Maps (U o T)

Let $T: V \to W$ and $U: W\to R$ be linear maps. Then the composition is denoted as ($\circ$ is the composition sign):
$$
U\circ T: V \to R
$$
is a linear map.

If $\alpha,\beta,\gamma$ are basis from $V,W,R$ respectively, ==then $[U \circ T]_\alpha ^\gamma= [U]_\beta^\gamma[T]_\alpha^\beta$==



## 10.2. Theorems

### Thm 1: Transformation on Basis is Transformation on VS

> - **<u>Main goal</u>** of the proof:  shows that to ==understand the behavior of a linear transformation on a vector space V,==  we just need to ==understand what does it== (the linear mapping function $T(x)$ or something else) ==do to the basis of the vector space V==

Let **V and W be VS** over K, and suppose that ==$B = \{v_1,v_2....v_n\}$ is a basis== for V. For any vectors $w_1,w_2....w_n \in W$ 

==There exists a unique linear map==. For each $v_i$ we choose, there is only one unique map to some $w_i$

$T: V \to W$ such that $T(v_i) = w_i, 1\leq i \leq n$ 

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/image-20210218210641249.png" alt="image-20210218210641249" style="zoom: 67%;" />

==Note:==

- There are no restrictions on $w_1,w_2...w_n$, which means they can be equal $w_1 = w_2....$

  <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/image-20210218211145147.png" alt="image-20210218211145147" style="zoom:67%;" /> ==This is unique map of $v_i$== because every $v_i$ only gets mapped once even to a duplicate $w_1$ value, which is fine. We only care about keeping ==one unique way starting from $v_i$== 

  （我们只在乎v是不是一定会被map出去，map到哪个w我们不关心，只要v能被map且只被unique map出去即可）

==**Proof:**==

Let $x \in V$. Then $x = a_1v_1 + a_2v_2+....a_nv_n$, where $a_i$ are unique scalars (only gives $x$). Now define: (==A function does the mapping==)
$$
Def:\;T(x) = a_1w_1+a_2w_2+....a_nw_n\\
where \; x= a_1v_1 + a_2v_2+....a_nv_n
$$
==Step 1. Show T is linear map== 

1. Let $x,y \in V$

   $x = a_1v_1 + a_2v_2+....a_nv_n$

   $y = c_1v_1 + c_2v_2+....c_nv_n$ where $a_i,c_i$ are unique (which does not mean $a_i \neq a_{i+1}...$)

   $T(x+y) = T((a_1+c_1)v_1+....(a_n+c_n)v_n) $ 

   $= (a_1+c_1)w_1+(a_2+c_2)w_2+....(a_n+c_n)w_n $ based on our $Def$.

   $=(a_1w_1+...a_nw_n) + (c_1w_1+c_2w_2+...c_nw_n) = T(x) + T(y)$. Then ==$T(x+y) = T(x)+T(y)$==

2. Let $k \in K$ be scalars

   $T(kx) = T(ka_1v_1+ka_2v_2+.....k_na_nv_n)$

   $=ka_1w_1+...ka_nw_n = k(a_1w_1+....a_nw_n)=kT(x)$

3. Therefore, T is linear based on $\textcolor{cyan}{1 \& 2}$



==Step 2. Show $T(v_i) = w_i $, each $v_i$ map to $w_i$==

Let $v_1 \in B.$ Then $v_1 = 1v_1+0v_2+.....0v_n$, Then $T(v_1)= 1w_1+0w_2+...0w_n = w_1$

In general, $T(v_i) = w_i$ by definition of $T(x)$



==Step 3. Show such linear map is **Unique**:==

Suppose $F: V \to W$ is linear and $F(v_i) = w_i$ (==shown in Step 1 and Step 2==)



==小结 Step 1,2,3:==

1. Step 1: we show that $\textcolor{cyan}{\text{It is a linear mapping}}$
2. Step 2: we show that mapping $\textcolor{cyan}{\text{map each }v_i \text{ to some }w_i}$
3. Step 3: we show that such mapping $\textcolor{cyan}{\text{is a unique mapping for each } v_i}$

---

<u>**Recall:**</u> 2 functions $f,g$ are equal if $f(x) = g(x)$ for all $x$

---

Let $x \in V, x = a_1v_1 + a_2v_2+....a_nv_n$, then we have:
$$
F(x) = F(a_1v_1+...a_nv_n)=a_1F(v_1)+....+a_nF(v_n) \text{ As proved in Step 1 (linearity)}\\ 
= a_1w_1+a_2w_2+....a_nw_n \text{ As seen in Step 2 (each vi to wi)}\\
=T(x)
$$
Which means we have shown $F(x) = T(x) \implies Uniqueness$ of $T(x)$==. $T(x)$ is unique.==



#### Concequence

If $F,T: V \to W$ are ==linear== and $F(v_i) = T(v_i)$ for all vectors $v_i$ in the basis of V, then $F = T$. 

In other words, any 2 functions (mapping) that agree on (perform the same things) the basis of a vector space, are the same mappings.



#### Example

Let $T: \R^2 \textcolor{cyan}{\to} \R^2$ be linear map that: $(a_1,a_2)\textcolor{orange}{\longmapsto} (2a_2-a_1,3a_1) $[^1]

If we know that a linear map $F: \R^2 \to \R^2$ such that $F((1,2))  = (3,3), F((1,1) )= (1,3)$, Then ==$F = T$==

==Because==

$B = \{(1,2),(1,1)\}$ is a basis for $\R^2$, and we find out that 

- $T((1,2)) = (2\cdot2-1, 3\cdot 1) = (3,3)$
- $T((1,1)) = (2\cdot1 -1, 3\cdot 1) = (1,3)$
- ==WOW!== We realized that $T$ treat the basis of $\R^2:$ $B = \{(1,2),(1,1)\},$ ==exactly same as $F$== such that they obtain the same results ==(3,3) and (1,3).== They behave the same on the basis $B = \{(1,2),(1,1)\}$

Therefore, by [Theorem 1](###Thm 1), we can know that $F = T$ are in fact the same linear mapping on all elements in $\R^2$

[^1]: This  $\textcolor{orange}{\longmapsto}$ means "from some element maps to some other elements", where  $\textcolor{cyan}{\to}$ (function) means "from some space maps to some other space", 



## 10.3. Properties*

Let $T,U : V \to W$ be linear maps, where $V,W$ are VS with bases $\beta$ (for V) and $\gamma$ (for W)

Then:

1. we have

   - $T+ U : V \to W$ is defiend as $(T+U)(x) = T(x) + U(x)$

   - $(cT)(x) = cT(x) ,c \in K$

2. $T+U, cT$ are linear

3. $[T+U]^\gamma_\beta = [T]^\gamma_\beta + [U]^\gamma_\beta$

4. $[cT]^\gamma_\beta = c[T]^\gamma_\beta, \forall c\in K$

---

# 11. Inner Product Spaces

## 11.1. Concept Definition

### 11.1.1. Inner product properties

#### Def (3 properties given)

==Def== Let V be a VS over a field K (K = $\R$ or K =$\C$). Suppose that to each vectors $x,y \in V$, we assign a number 

`<x,y>` $\in K$ (special notation for ONE number), such that, the following holds:

1. $<ax+y,z> = a<x,z> + <y,z> $ for all $x,y,z \in V, a\in K$ ==Linearality==

2. $<x,y> = \overline{<y,x>}$ for all $x,y \in V$ ==Symmetry==
3. If $x \neq 0_V$, then $<x,x> \in \R$ and $<x,x> > 0$ ==Positive Definitness==
   1. but if $x = 0_V$, then $<x,x> \geq 0$

such number is called the ==inner product==. A vector space can have several ==different inner product==

---

#### Example

It is easy to verify that the dot product you know is an inner product:

Let x = (1,2), y = (3,-1) $\in \R^2$  <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210310191250.png" alt="image-20210310191249839" style="zoom: 33%;" />

also, $<x,x> = (1,2) \cdot (1,2) = 1^2 + 2^2 = 5 >0$, which satisfies the ==positive definiteness== of inner product

**The outcomes of doing dot product on x and y is the same as doing inner product as <x,y>, thus dot product is same as doing inner product.**





### 11.1.2. Inner product space

A vector space with an inner product is called ==an inner product space== 

- If the field is $\R$, then it is called the ==real inner product space==
- If the field is $\C$, it is called the ==complex inner product space==



==Note:==

- In some books, inner product can be denoted by (x,y), (x|y),<x|y> or $x \cdot y$

---

### 11.1.3. Norm of inner product

#### Def

Let V be an IPS (inner product space), for $x \in V,$ we define ==the norm (length)== of x by:
$$
||x|| = \sqrt{<x,x>} 
$$

---

#### Example

1. In $\R^2$, $\R^2$ has an inner product which we call ==dot product==, let x = (1,2)$\in \R^2$, then we have the ==norm of x as:==
   $$
   ||x|| = \sqrt{<x,x>} = \sqrt{x \cdot x} = \sqrt{1 \cdot 1 + 2\cdot 2} = \sqrt{5}
   $$
   such property holds true as well in $\R^n$

   

2. Find Norm in $\C^2$ (When we deal with dot product in complex field, we times its conjugate)
   $$
   <x,(i,1)> = <x,i(1,0)+(0,1)> = \bar i<x,(1,0)> +<x,(0,1)> = (x_1 \cdot \bar i) + (x_2 \cdot 1)
   $$

---



#### Example (Find Norm in Complex Field)

1. In $\C^3$, we have $<(1,i,1+i),(i,2-i,0)>$, it equals to:

$$
(1)(\bar i) + i\overline{(2-i)} =  (1)(-i) + i(2+i)=-i+2i-1=i-1
$$



2. Let $u = (1,i,1+i) \in \C^3$, then find $u^\perp = \{(x,y,z) \in \C^3 | <(x,y,z),(1,i,1+i)>=0\}$

   we set $<(x,y,z),(1,i,1+i)>=0$, then solve for x,y,z

   $\implies$ $x-iy+z(1-i) = 0$, thus $x = iy -z(1-i) = iy+z(i-1)$ and we have:
   $$
   (x,y,z) = (iy+z(-1+i),y,z) = y(i,1,0) + z(i-1,0,1)
   $$
   we name them $w_1=(i,1,0), w_2 = (i-1,0,1)$ and we can verify that $w_1, w_2$ are LI.

   1. $<u,w_1> = 1(-i)+i(1)+(1+i)(0) = -i+i +0=0$, thus $u \perp w_1$
   2. $<u,w_2> = -i-1+0+1+i= 0,$ thus $u\perp w_2$

---



####   Example (Fourier analysis)

If V is the VS of **continuous** function $f: [0,1] \to \R$, then $<f,g> = \int^1_0f(x)g(x)dx$, we can denote it as $f \perp g$ and is called Fourier analysis (傅里叶分析)

---



## 11.2. More Inner product properties

Let V be an IPS (inner product space) ==(automatically, we know it is a vector space)== over a field K ($K = \R, \C$)

Let x,y,z $\in V$, $a\in K$, we have properties:

1. $<x,0_V> = 0, <0_V,x> = 0$

2. $<x,ay+z> = \bar a<x,y> + <x,z>$

3. $<ax,y> = a<x,y>$

4. $<x,ay> = \bar a<x,y>$

5. $<x,y> \cdot <y,x> = <x,y>\overline{<x,y>} = |<x,y>|^2$

6. If $K = \R,$ then $<x,y> = <y,x>$

   

### Proof

1. From the ==Linearality== of the given 3 properties of inner product space, we can say that:

$<0_V,x> = <0_V+0_V,x> = <0_V,x>+<0_V,x>,$ thus $<0_V,x> = 0$. Also, based on ==Symmetry== in the 3 properties, we know that $<0_V,x> = \overline{<x,0_V>} = \bar 0 = 0$

Thus: $<0_V,x> = <x,0_V> = 0$

---

2. Now we want to prove `2:`$<x,ay+z> = \bar a<x,y> + <x,z>$
   $$
   <x,ay+z> = \overline{<ay+z,x>}\\=\overline{a<y,x> + <z,x>}\\=\bar a \overline{<y,x>} + \overline{<z,x>} \\= \bar a <x,y> + <x,z>
   $$
   Thus, we have proved the property.

---

3. ==proof of **property 6**== we know that $<x,y> = \overline{<y,x>}.$ In $\R,$ we know that $\overline{<y,x>} = <y,x> $, thus $<x,y> = <y,z>$ with $K =\R$
   - Exp:<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210310195050.png" alt="image-20210310195050344" style="zoom:50%;" />

### <u>Remark</u>

Suppose $<x,y> = <y,x>,$ then:
$$
0 < <ix,ix> \\ <ix,ix>= i<x,ix>\\
=i<ix,x> (\text{since <x,y> = <y,x>}) \\
= i \cdot i<x,x> = -1 \cdot<x,x><0 , \text{ which contradicts our assumption}
$$
Thus, $<x,y> \neq <y,x>$ in $\C$, ==only in $\R$==, that is why we need $<x,y> = \overline{<y,x>}$





## 11.3. Theorems

### Thm 1: Cauchy-Schwanz and Triangle inequality

Let V be an IPS over $\C$, then for all x,y $\in V$ and c $\in \C$, the followings are true:

1. $||cx|| = |c|\cdot||x||$
2. $||x|| = 0 \iff x = 0_V$
   1. in all cases, $||x|| \geq 0$
3. ==Cauchy-Schwanz inequality:== $|<x,y>| \leq ||x|| \cdot ||y||$
4. ==Triangle inequality:== $||x+y|| \leq ||x|| + ||y||$



#### Proof

1. $||cx|| = |c|\cdot||x||$: ==Note: $c\bar c = |c|^2$ known at begining of the course==

   $||cx|| = \sqrt{<cx,cx>} = \sqrt{c\cdot\bar c<x,x>} = \sqrt{|c|^2 \cdot <x,x>} = |c| \cdot ||x||$



2. want to show: $||x|| = 0 \iff x = 0_V$

   1. $\Longleftarrow$: by definition, we know that $<x,0_V> = 0 \;\forall x \in V$. Since $x = 0_V$ (given), we then know that

      ||x|| = $\sqrt{<x,x>} = \sqrt{0} = 0$

   2. $\Longrightarrow$: given $$||x|| = 0 \implies x = 0_V$$

      By definition, we know that  $x\neq 0_V \implies <x,x>  \neq 0$, by using the ==contrapositive proof:==

      we can conclude that $<x,x> = 0 \implies x = 0_V$

3. ==The tricky and important Property: Cauchy-Schewanz inequality==

   show   $|<x,y>| \leq ||x|| \cdot ||y||$

   1. if $y = 0_V$, then $|<x,y>| = |<x,0_V>| = |0|=0$, by ==property 2==, $||y|| = 0$ because $y = 0_V$

      thus $||x|| \cdot||y|| = ||x|| \cdot 0=|<x,y>| = 0$, thus the property holds ==if $y = 0_V$==\

   2. ==if $y\neq 0_V$==, then take any $c \in \C,$ and consider $x-cy \in V$ as some vector in V

      By definition, we know: $0 \leq ||x-cy||^2 = <x-cy,x-cy>$ by the definition of the norm

      rewrite:
      $$
      <x-cy,x-cy> = <x-cy,x>+<x-cy,-cy> \text{by property of inner product}
      \\=<x,x> -c<y,x>+<x,-cy>-c<y,-cy>\\
      =<x,x>-c<y,x>-\bar c<x,y>-c\cdot(-\bar c)<y,y>
      \\ =<x,x>-c<y,x>-\bar c<x,y>+c\cdot(\bar c)<y,y>
      $$
      ==Someone made a smart choice: Let==
      $$
      c = \frac{<x,y>}{<y,y>}
      $$
      then:
      $$
      <x-cy,x-cy> =<x,x>-c<y,x>-\bar c<x,y>+c\cdot(\bar c)<y,y>
      \\=<x,x> - \frac{<x,y>}{<y,y>}<y,x>- \overline{\frac{<x,y>}{<y,y>}}<x,y>+|c|^2<y,y>
      
      \\ = <x,x> - \frac{<x,y>}{<y,y>}<y,x>- {\frac{<y,x>}{<y,y>}}<x,y> + \left| \frac{<x,y>}{<y,y>} \right|^2<y,y>
      
      \\=<x,x> - 2 \frac{<x,y><y,x>}{<y,y>} + \frac{|<x,y>|^2}{<y,y>}
      
      \\ = <x,x> - 2 \frac{|<x,y>|^2}{<y,y>} + \frac{|<x,y>|^2}{<y,y>}
      
      \\= <x,x> - \frac{|<x,y>|^2}{<y,y>} \geq 0
      \\ \\ \\ 
      \\ \text{then, we have:}   <x,x> \geq \frac{|<x,y>|^2}{<y,y>}
      \\ <x,x><y,y> \geq |<x,y>|^2
      \\||x||^2||y||^2 \geq |<x,y>|^2
      \\ ||x|| \cdot||y|| \geq |<x,y>| \textcolor{cyan}{ \; Proof Done}
      $$

4. ==Proof of triangle inequality==: want to show  $||x+y|| \leq ||x|| + ||y||$

   we know that $||x+y||^2 = <x+y,x+y>$, then
   $$
   ||x+y||^2 = <x+y,x+y>
   \\ = <x,x+y>+<y,x+y>
   \\ = <x,x> +<x,y> + <y,x> + <y,y>
   \\ = ||x||^2+ (<x,y> +\overline{<x,y>}) + ||y||^2
   \\ = ||x||^2 + ||y||^2 + 2Re(<x,y>) \\
   \text{Recall: adding a complex number and its conjugate gives its real part times 2}
   $$

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311162348.png" alt="image-20210311162347852" style="zoom:50%;" />

​		since $<x,y>$ is a complex number, which means that its real part is always smaller than its norm:
$$
z = a+ib, |z| \geq Re(z) \text{ as shown above}
\\
\text{Thus: }Re(<x,y>) \leq |<x,y>|
$$
​		Therefore, $||x+y||^2 = ||x||^2 + ||y||^2 + 2Re(<x,y>) \leq ||x||^2 + ||y||^2 + 2|<x,y>| $

​		By ==Cauchy-Schewanz inequality==, we know that ==$|<x,y>| \leq ||x|| \cdot||y||$==

​		Thus: $||x||^2 + ||y||^2 + 2|<x,y>| \leq ||x||^2 + ||y||^2 + 2||x||\cdot||y|| $
$$
||x+y||^2 \leq ||x||^2 + ||y||^2 + 2||x||\cdot||y|| = (||x|| + ||y||)^2
\\\implies ||x+y|| \leq ||x|| + ||y||
$$

---

# 12. Angles Between Vectors

## 12.1. Concept Definition

### 12.1.1. Angle between Vectors

#### Def

For any non-zero vectos $u,v$ in a ==real IPS== V, the ==angle between $u,v$== is defiend to be the ==angle $\theta$== such that

1. $0 \leq \theta \leq \pi$
2. <img src="C:\Users\a1893\AppData\Roaming\Typora\typora-user-images\image-20210311183729479.png" alt="image-20210311183728989" style="zoom: 67%;" />



#### Remark

By the [Cauchy-Schwanz inequality](###Thm 1 (Cauchy-Schwanz inequality)), we know that $|<u,v>| \leq ||u|| \cdot ||v||$, therefore

we can say that (by removing the absolute value sign):
$$
-1 \leq \frac{<u,v>}{||u|| \cdot ||v||} \leq 1
$$
which is the same range as $cos \theta$



#### Example

1.  ==(angle between vectors)==

    let $u = (2,3,5), v=(1,-4,3), in \; \R^3$

    thus, $<u,v> = u\cdot v = 2\cdot 1 + 3\cdot -4 + 5 \cdot 3 = 5$

    $||u|| = \sqrt{4+9+25} = \sqrt{38}$, $||v|| = \sqrt{1+16+9} = \sqrt{26}$

    $cos \theta = \frac{5}{\sqrt{38 \cdot 26}}  \implies \theta = 80.85^{\circ}$

2. ==Angles between functions==

   Let $f(t) = 3t -5, g(t) = t^2$ be vectors in $P(t),$ which is the VS of all polynomials

   Then, the inner product on $P(t)$ is $<f,g> = \int^1_0f(t)g(t)dt$, **what is the angle between f and g?**

   ==Sol:==

   1. calculate $<f,g>$

   $$
   <f,g> = \int_0^1 (3t-5)(t^2)dt = \int_0^13t^3dt-\int_0^15t^2dt
   \\ = \left. 3\frac{t^4}{4} \right |^1_0 - \left. 5\frac{t^3}{3} \right |^1_0 =\frac34 - \frac 53=-\frac{11}{12}
   $$

   2. find $||f||$
      $$
      ||f|| = \sqrt{<f,f>} = \int^1_0(3t-5)^2dt=\dots =\sqrt{13}
      $$

3. find $||g||$
   $$
   ||g|| = \sqrt{<g,g>} = \int^1_0 t^4dt =... = \frac{\sqrt{5}}5
   $$

Combine 1,2,3, we find:
$$
   cos\theta = \frac{-\frac{11}{12}}{\sqrt{13} \cdot\frac{\sqrt{5}}5 }\\
   \theta = cos^{-1}\left (\frac{-\frac{11}{12}}{\sqrt{13} \cdot\frac{\sqrt{5}}5 } \right)=something
$$

### 12.1.2. Orthogonality between Vectors

==Note:== the vector mentioned here are not necessarily "the vectors", they are the elements in Vector Space (can be functions)

#### Def

Let V be an IPS. The vectors $u,v \in V$ are said to be ==orthogonal (or u is orthogonal to v)== if ==$<u,v> = 0$==

#### Remark

1. $0_V$ is orthogonal to any vector in V because by the [first property of extra properties on inner product](##11.2. Some extra Inner product properties), we know that $<x,0_V> = <0_V,x> = 0$  $\forall x \in V$
2. $<u,v> = 0 \iff<v,u> = 0$ ==if u is orthogonal to v, v is obviously orthogonal to u==
3. $<u,v> = 0 \implies $ u is orthogonal to v $\implies cos\theta =0$ where $\theta $ is the angle between $u$ and $v$. $\theta = \frac{\pi}2$ in radians

4. if $<u,v> = 0$, we write ==$u\perp v$== 

#### Examples

1. Let $u = (1,1,1), v =(1,2,-3), w= (1,-4,3), u,v,w \in \R^3$. Find the vectors that are orthogonal

   - $<u,v> = u\cdot v = 1+2-3=0 \implies u \perp v$

   - $<u,w> = u\cdot w = 1-4+3=0 \implies u\perp w$

   - $<v,w> = v\cdot w =1-8-9=-16 \neq 0 \implies$ v is not orthogonal to w

   - ==Graphical Iterpretation==

     ![image-20210311210140683](https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311210140.png)

   

2. Find a non-zero vector $w \in \R^3$ such that it is orthogonal to both $u_1 = (1,2,1), u_2 = (2,5,4)$

   ==Sol:==

   let $w = (x,y,z)$, we need to find:

   1. $<w,u_1>=x+2y+z = 0$

   2. and $<w,u_2>=2x+5y+4z = 0$

   3. we obtain a linear system with infnity many solutions (2 equations with 3 unknowns)

      ![image-20210311210517100](https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311210517.png)

   ==Thus,== we obtain $w = (3z,-2z,z) = z(3,-2,1)$. If we take $w = (3,-2,1)$

   $<w,u_1> = 3-4+1 =0, <w,u_2> =6-10+4=0$

---

### 12.1.3. Orthogonal Complements (S perp)

#### Def

Let S be a ==non-empty subset== of an IPS V. The <u>==Orthogonal Complement==</u> of S, denoted by $S^{\perp}$, read as `S perp`

consists of all vectors that ***are orthogonal to every vector of S***. In other words:
$$
S^\perp = \{ v \in V | <u,v> = 0 \;\;\;\forall u \in S\}
$$

#### Example

In $\R^2$, we have: 

the white line $S^\perp$ is the ==Orthogonal Complements==

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311211714.png" alt="image-20210311211714236" style="zoom:80%;" />

---

### 12.1.4. Orthogonal Sets and Bases

#### Def

Consider a set $S = \{u_1,u_2.....u_n\}$ of non-zero vectors in an IPS V. 

S is called ==pariwise orthogonal== if each pair of vectors of S are orthogonal.

==For example:== if $S = \{u_1,u_2\}$, then S is orthogonal if $<u_1,u_2> = 0$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311213451.png" alt="image-20210311213451448" style="zoom: 50%;" />



==In addition,== S is also called <u>==Orthonormal==</u> if S is orthogonal and each vector has ==norm = 1 (which is called the unit length)==



#### Example

In $\R^4:$ $S = \{(1,1,0,-1),(1,0,0,1),(0,0,1,0)\}$

1. Is S orthogonal?
   - Yes, since each pair of vectors in $S$ are orthogonal, calculation is easy
2. Is S orthonormal?
   - No, because $||(1,1,0,-1)|| = \sqrt{(1,1,0,-1) \cdot(1,1,0,-1)}=\sqrt{1+1+1} \neq 1$
3. How to create an ==orthonormal set $S'$== from an orthogonal $S$? 
   - we look at each vector $v_i$ and divide it by its length $\frac1{||v_i||}$(such process is called ==normalizing==)
   - such S' will look like: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311214951.png" alt="image-20210311214951249" style="zoom:67%;" />
   - For example: $(1,1,0,-1) \cdot \frac1{\sqrt{3}} = (\frac1{\sqrt{3}},\frac1{\sqrt{3}},0,-\frac1{\sqrt{3}} )$

---

### 12.1.5. Projections and Fourrier Coefficient

#### Def

Let V be an IPS, and $v,w \in V$ be non-zero vectors.

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210311221510.png" alt="image-20210311221509843" style="zoom:50%;" />

where $v-cw$ is ==operation between vectors==

We know that $v-cw,w$ are orthogonal, thus:
$$
<v-cw,w> = 0\\
<v-cw,w> = <v,w>-c<w,w> =0\\
\text{then, we know that: }
\\ c = \frac{<v,w>}{<w,w>}
$$
where c is called as ==the Fourrier Coefficient==, we write it as:
$$
proj(v,w) = cw = \frac{<v,w>}{<w,w>} \cdot w
$$

==$cw$== is written as $proj(v,w)$, and read as ==projection of v onto w==

---

#### Generalization of Def

Suppose $w_1,w_2...w_r$ form an orthogonal set of non-zero vectors (each pair of $w_i,w_j$ are orthogonal) in V. Let $v \in V$.

We define ==$v' = v - (c_1w_1+c_2w_2+....c_rw_r)$== where
$$
c_i = \frac{<v,w_i>}{<w_i,w_i>} , 1\le i \le r
$$
Then ==$v'$ is orthogonal to all $w_i$.==

##### Proof

$v' \perp w_1$ since $<v',w_1> = <v - (c_1w_1+c_2w_2+....c_rw_r),w_1>$

Then the distributive property of inner product:
$$
<v - (c_1w_1+c_2w_2+....c_rw_r),w_1>
\\=<v,w_1> -c_1<w_1,w_1>-c_2<w_2,w_1>.....-c_r<w_r,w_1>
\\\text{we know that } w_1,w_2...w_r \text{ forms an orthogonal set, thus:}<w_2,w_1> ....=<w_r,w_1> = 0

\\\text{then:}
\\ <v - (c_1w_1+c_2w_2+....c_rw_r),w_1> = <v,w_1>-c_1<w_1,w_1>
\\=<v,w_1> - \frac{<v,w_1>}{<w_1,w_1>} \cdot <w_1,w_1> =0
$$
Similarly, $v' \perp w_i \;\;\; \forall i$ since we can shown that:
$$
<v',w_i> = <v,w_i> - c_i<w_i,w_i> =<v,w_i> - \frac{<v,w_i>}{<w_i,w_i>} \cdot <w_1,w_1> =0
$$
Thus, end of proof.


---

### 12.1.6. Gram-Schmidt Orthogonalization Process (GSOP)*

> - It is an algorithm
> - Input a random set and output an orthogonal set
>   - if we input a basis, then it will output an ==orthogonal basis==

#### Def (how the algorithm works)

Suppose $\{v_1,v_2....v_n\}$ is a basis fro an IPS V. We can constract an orthogonal basis $\{w_1,w_2...w_n\}$

of IPS V as follows:

1. we choose $w_1 = v_1$
2. $w_2 = v_2-proj(v_2,w_1) = v_2 - \frac{<v_2,w_1>}{<w_1,w_1>} \cdot w_1$ 
3. $w_3 = v_3 - proj(v_3,w_2) - proj(v_3,w_1)$
4. ETC.....
5. $w_n = v_n - proj(v_n,w_{n-1}) - proj(v_n,w_{n-2})...-proj(v_n,w_1)$

---

#### Example

Apply the GSOP (Gram-Schmidt Orthogonalization Process) to find an orthogonal basis and then an orthonormal basis for $U \sub \R^4,$ where $U = span\{(1,1,1,1), (1,2,4,5),(1,-3,-4,-2)\}$ ==It is given that $v_1,v_2,v_3$ forms a basis==

we have $v_1 = (1,1,1,1), v_2 = (1,2,4,5),v_3= (1,-3,-4,-2)$ 

Now let's run the algorithm:

1. $w_1 = v_1 = (1,1,1,1)$
2. $w_2 = v_2 - proj(v_2,w_1) = v_2 - \frac{<v_2,w_1>}{<w_1,w_1>} \cdot w_1 = (1,2,4,5) - (1,1,1,1) \cdot \frac{(1,2,4,5)(1,1,1,1)}{(1,1,1,1)(1,1,1,1)} \\= (1,2,4,5) - (1,1,1,1)\frac{12}{4} = (-2,-1,1,2)$
3. $w_3 = v_3 - proj(v_3,w_2) - proj(v_3,w_1) = \dots=(\frac85,-\frac{17}{10}.-\frac{13}{10},\frac75) = (16,-17,-13,14)$
4. Thus, we have found the ==orthogonal basis of $\{v_1,v_2,v_3\}$==

**<u>To Normalize, we just multiply each vector $w_1$</u>** by $\frac1{||w_i||}$ to get the ==orthognormal basis==

---

### 12.1.7. Conjugate Transpose

> - 字如其名，先conjugate再transpose

#### Def

The ==conjugate transpose== of a <u>complex matrix: A</u> is denoted by ==$A^*$==. and it is given by:

$A^* = \overline{ (A)}^T$, where $\bar A$ is the conjugate of A.

---

#### Example

1. Given a complex matrix: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316142905.png" alt="image-20210316142850634" style="zoom: 50%;" />

   then we can obtain $\bar A$ = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316143104.png" alt="image-20210316143104762" style="zoom: 50%;" />, where we just conjugate all entries

   thus, $A^* = \bar A ^T=$  <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316143121.png" alt="image-20210316143121301" style="zoom: 50%;" />

---

#### Properties of Conjugate Transpose

Let A,B be complex matrices and $c \in \C$

1. $(A^*)^* = A$
2. $(A+B)^* = A^* + B^*$
3. $(cA)^* =\bar c A^*$
4. $(AB)^* = B^* \cdot A^*$

---

### 12.1.8. Unitary and Orthogonal Matrix

#### Def

A complex matrix A is called the ==unitary== if: 

1. $A^{-1} = A^* \implies$ ($AA^* = A^*A = I$)
2. In particular, when A is real ==(A has real entries)==, then $A^* = A^T$, and if $A^TA = AA^T = I$ (In other words: $A^{-1} = A^T$), we call: $ A $ is an ==orthogonal matrix==. 

---

#### Example

Given: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316144244.png" alt="image-20210316144244143" style="zoom:50%;" />, then is A unitary? (since A is not real, it can not be orthogonal matrix)

==<u>Sol</u>:==

$AA^* = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316155819.png" alt="image-20210316155818898" style="zoom:50%;" /> = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316155914.png" alt="image-20210316155914414" style="zoom:50%;" />



$A^*A = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316155926.png" alt="image-20210316155926194" style="zoom:50%;" /> as well using similary method. Thus we have shown that $AA^* = A^*A = I$, then A is indeed unitary.













## 12.2. Theorems

### Thm 1: Orthogonal Complement of a non-empty set is Subspace

Let S be a non-empty <u>subset</u> of an IPS V. Then $S^\perp$ is a subspace of V

#### Proof

1. we know that $<0_V,u> =0 \;\;\; \forall u \in S$ based on the property of inner product, thus $0_V \in S^\perp$

2. Let $v_1,v_2 \in S^\perp$, we need to show that $v_1+v_2 \in S^\perp$ , which is: $<v_1+v_2,u> =0 \;\;\; \forall u\in S$

   we know that $<v_1+v_2,u> = <v_1,u>+<v_2,u>$ and $v_1, v_2 \in S^\perp$

   Thus $<v_1+v_2,u> = 0+0 = 0, v_1+v_2 \in S^\perp$

3. Let $v \in S^\perp$ and $c \in K$ we need to show that $cv \in S^\perp$, which is $<cv,u> = 0 \;\; \forall u\in S$

   we know that $<cv,u> = c<v,u>=c\cdot 0 = 0$ based on the property of inner product

4. ==Thus, $S^\perp$ is a subspace of V based on 1,2,3==

---



### Thm 2: Non-zero Orthogonal Set is LI

Suppose S is orthogonal set of non-zero vectors. Then S is LI.

#### Proof

Let $S = \{u_1,u_2.....u_n\}$ be orthogonal. Consider $a_1u_1 + ......,a_nu_n = 0_V$ where $a_1,a_2...a_n \neq 0$ ==Not 0 YET!!! (will be proved below)==

Consider

$<a_1u_1 + ......a_nu_n,u_1> = 0 $ since $ a_1u_1 + ......a_nu_n = 0_V$
$$
<a_1u_1 + ......a_nu_n,u_1> = a_1<u_1,u_1> + a_2<u_2,u_1>......a_n<u_n,u_n>
$$
since we have assumed that ==$S = \{u_1,u_2.....u_n\}$ be orthogonal==, then each pair of inner product in S is 0:
$$
<u_1,u_1>=<u_2,u_1>......=<u_n,u_n> = 0
$$
but we said that ==$S$ is orthogonal set of **none zero** vectors==, then $<u_1,u_1> \neq 0$ based on the property of inner product

Thus, $a_1$ must be 0 so that $a_1<u_1,u_1> = 0$ can hold true.

**We reapeat the same process with $u_2,u_3.....u_n$** as:
$$
<a_1u_1 + ......a_nu_n,u_2>\\
<a_1u_1 + ......a_nu_n,u_3>\\
\vdots\\
<a_1u_1 + ......a_nu_n,u_n>
$$
in each step with $<a_1u_1 + ......a_nu_n,u_i>,$ we can obtain $a_i = 0$ for $1\leq i \leq n$, thus we have shown that

==A orthogonal set **S** with non-zero vectors is LI.==

---

### Thm 3: Extend Orthogonal Basis mantains

Suppose $S = \{w_1,....w_r\}$ is an ==orthogonal basis== for $W.$ And we know that $W \subseteq V$. Then we can extend $S$ to an ==orthogonal basis for $V$==



#### Proof

First, complete S to a basis of V ==(Extending basis: a thm proved before)== $\implies$ $S = \{w_1,...w_r,w_{r+1},,,,w_n\}$ where $\{w_1....w_r\}$ is an orthogonal set but $\{w_{r+1}.....w_n\}$ we do not know yet, need to prove

Now, apply GSOP to $\{w_{r+1}.....w_n\}$ to obtain an orthogonal basis for V. ==END OF PROOF==



#### Example

Denote the vectors in the ==extended part of orthogonal basis of V be:== $u_i$ where $r+1\le n$, then:

1. $u_{r+1} = w_{r+1} - proj(w_{r+1},w_r) - proj(w_{r+1},w_{r-1}) \dots$
2. 以此类推, get all $u_i$

---

### Thm 4: VS is Direct Sum of W and W perp

Let W be a subspace of V. ==Then $V = W \oplus W^\perp$==

#### Proof

Let $S = \{w_1,.....w_r\}$ be a basis for W.

1. First, we extend S to an ==orthogonal basis== of V as $\{w_1,...w_r,w_{r+1}.....w_n\}$

2. Then, give $x \in V$, can be written as: $x = a_1w_1+a_2w_2....+a_rw_r+a_{r+1}w_{r+1} ....+a_nw_n$

Since  $\{w_1,...w_r,w_{r+1}.....w_n\}$ is an orthogonal basis, then by definition, we know that each pair of vectors are orthogonal, thus we can seperate them into 2 groups: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210314170821.png" alt="image-20210314170821668" style="zoom:33%;" />

because $w_{r+1}....w_n$ are all orthogonal to $w_1,w_2...w_r$. That is why they can be grouped into $W^\perp$

Thus, $x \in W + W^\perp \implies V = W + W^\perp$ 

==Side Note: the size of W and $W^\perp$ can be different, if so we can obtain another different direct sum==

 

Now, we need to show that $W \cap W^\perp = 0_V$. Take randomly the $x \in W \cap W^\perp$, and logically, we can know that x must be orthogonal to itself, thus:
$$
<x,x> = 0_V \iff x = 0_V \text{ by definiton of Inner Product}
$$
Thus, we have shown that $x \in W \cap W^\perp$ must be $0_V$, then $W \cap W^\perp = \{0_V\}$

Then, $V = W \oplus W^\perp$ ==END OF PROOF==

---

### Thm 5: Another way to prove Unitary / Orthogonal matrix

- An $n \times n$ complex ==(or real)== matrix $A$ is unitary ==(or orthogonal)== $\iff$ the columns / rows vectors form an orthonormal set of $\C^n$ (==$\R^n$==) 
  - $\textcolor{cyan}{\text{Just check either columns or rows vectors, do not check both}}$
  - look at rows vectors is one way
  - look at columns vectors is another way

---

#### Proof

Let A be a real matrix such that: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316161241.png" alt="image-20210316161241753" style="zoom:50%;" />

A is orthogonal $\iff$ $AA^T = A^TA=I_{n \times n}$, and in particular,

$AA^T = $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316161513.png" alt="image-20210316161513532" style="zoom:55%;" />which is equivalent as saying:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316161700.png" alt="image-20210316161700538" style="zoom:50%;" /> $\implies$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210316161755.png" alt="image-20210316161755261" style="zoom:50%;" />

and $<a_{12},a_{11}> = 0 \implies a_{12} \perp a_{11}$ and such must hold true for all matrix multiplication for columns and rows (such that we can obtain the identiy matrix's first column, a ==1== and a bunch of ==0's==). With $AA^T$, we ==checked the rows of A.==



Similarly, with $A^TA$, we can check the theorem holds for the ==columns of A==



It is a purely computational proof. ==END OF PROOF==

----

# 13. Determinants Review

## 13.1. Determinant Definition

Given a 2 by 2 matrix $ M= \left( \matrix{  a & b\\  c & d  } \right) $, then the determinant of M, denoted by ==det(M)==, is the number :
$$
det(M) = ad -bc
$$
Geometrically speaking, it is the area of $v_1,v_2$ in $\R^2$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318191111.png" alt="image-20210318191058963" style="zoom: 33%;" />

In $\R^3$, the $det(M)$ indicates the volume of parallelpiped, which looks like <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318191302.png" alt="image-20210318191258439" style="zoom:33%;" />

---

## 13.2. Properties of Determinants

> Use without proving them

1. Given a ==square== matrix A, ==$det(A) = det(A^T)$== 
2. Given a ==square matrix== A, if A has a <u>**row or column of zeros**</u>, then ==$det(A) = 0$== 
3. If A has 2 identical rows (columns), then ==$ det(A) = 0$==

4. If A is ==triangular==, then ==$det(A) = $ product of diagonal entries==

   - A has all zeros above or below the diagonal, then A is triangular (upper or lower depends on situation)

   - ==Example:== Let A = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200713.png" alt="image-20210318192125126" style="zoom:33%;" />, then $det(A) = 1\cdot3\cdot1\cdot1\cdot2 = 6$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200714.png" alt="image-20210318192215392" style="zoom: 33%;" />

5. If B is obtained from A by interchanging rows (columns), then ==$det(B) = -det(A)$== 
   - <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200715.png" alt="image-20210318192343902" style="zoom: 33%;" />, such change is called ==interchange of rows==

6. If a row (column) in A is multiplied by a scalar c to obtain a matrix B, then ==$det(B) = cdet(A)$== 
   -  <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200716.png" alt="image-20210318192558305" style="zoom:50%;" />



7. If B is obtained from A by adding a multiple of a row (column) to another one, then ==$det(A)= -(-det(B))=det(B)$== 

8. Given 2 sqauare matrix A,B. ==$det(AB) = det(A)\cdot det(B)$== 

   1. If A is invertible, then ==$det(A^{-1}) = \frac 1{det(A)}$== 

   2. If A is invertible, then necessarily $det(A) \neq 0$
   3. ==A is invertible $\iff$ $det(A)\neq0$==

9. The followings are equivalent: ==$1 \iff 2 \iff 3 \iff 4$== everything is the same

   1. $A$ is invertible

   2. $Ax = 0 $ has only the zero solution

      - Let $A,x \in V$, the linear transformation $T: V\to \R$ has $N(T) ={0_V}$ since x can only be $0_V$ so that $Ax=0$,

        which implies ==1 to 1.==

   3. Rows (columns) of A are LI

   4. $det(A) \neq 0$

10. If A and B are ==similar==, then $det(A) = det(B)$ (only one way $\implies$)

    since $det(B) =det(Q^{-1}AQ) = det(Q^{-1})\cdot det(A)\cdot det(Q)= \frac1{det(Q)} \cdot det(A)\cdot det(Q)=det(A)$

    - ==Recall:== Matrices A,B are ==similar== if $\exists$ an invertible matrix Q such that $B =Q^{-1}AQ$

11. ==Warning:== $det(A+B) \neq det(A) + det(B)$ in general

12. **==Block Matrices==**

    Matrix A can always be subdivided into smaller matrices

    - Example: $A = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200717.png" alt="image-20210318195030756" style="zoom:33%;" /> $=$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210318200718.png" alt="image-20210318195055415" style="zoom:33%;" />, In this case, $A_3 = 0_{matrix}$. 

      Thus A is block-upper triangular. So $det(A) =det(A_1) \cdot det(A_4)$ 

    - ==Fact:== suppose M is upper (lower) triangular block matrix with diagonal block matrices $A_1,.....A_n$, then we have $det(M) = det(A_1)\cdot det(A_2).....\cdot det(A_n)$

13. A linear map $T: V \to V$ is called a ==linear operator== since it maps to itself (V to V). 

    Once we have chosen an ordered basis $\beta$ of V, then $T$ can be expressed as a matrix $[T]_\beta$. 

    For any other basis $\alpha$ of V, we have ==$[T]_\alpha = Q^{-1}[T]_\beta Q$==

    thus: $det([T]_\alpha) = det( Q^{-1}[T]_\beta Q) =det([T]_\beta)$. This implies that $det(T)$ is ==independent of the choice of basis== since we get the samething when choose $\alpha$ or $\beta$ as basis

14. Given $F,G $ are 2 linear operators on V, then we have the following:

    1. $det(F \circ G) = det(F) \cdot det(G) $
    2. $F$ is invertible $\iff$ $det(F) \neq 0$

---

# 14. Diagonalization

> - Eigen values and Eigen vectors

## 14.0. Motivation (why we need this)

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161448.png" alt="image-20210320155559094" style="zoom: 50%;" />

- Finding invariant "directions" of T is important because if $\beta = \{x_1,x_2\}$ is a basis of $\R^2$ such that $x_1,x_2$ are eigenvectors, $[T]_\beta$ is ==diagonal with== diagonal entries equal to the corresponding eigenvalues
- If $T: \R^2 \to \R^2$, $\alpha $ is a bais. <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161449.png" alt="image-20210320155950041" style="zoom:50%;" />

- but in $[T]_\beta$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161450.png" alt="image-20210320160023254" style="zoom:50%;" />

### Example (calculation is easy with eigenvalue and eigenvectors)

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161451.png" alt="image-20210320160124607" style="zoom:67%;" />, compute $M^{1000}$, which is too huge.

But if we are given an diagonal matrix: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161452.png" alt="image-20210320160209757" style="zoom:33%;" />

---

## 14.1. Concept Definitions

### 14.1.1. Diagonalizable (implies similar matrix)

#### Def

We say A matrix A is ==diagonalizable== if there exists an invertible matrix $Q$ such that:
$$
D = Q^{-1}AQ \text{ (A is similar matrix to D, the diagonal matrix)}
$$
where $D$ is a ==diagonal matrix.== 

And also, ==$A$ is similar to $D$== 

---

#### <u>Remark</u>

If A is diagonalizable, then to compute $A^n$, we do the following:
$$
\exists D = Q^{-1}AQ \\ QD= QQ^{-1}AQ = IAQ = AQ\\QDQ^{-1}=AQQ^{-1} =AI=A\\Thus: A =QDQ^{-1} 
$$
where $D$ is diagonal. Then we have:
$$
A^n = QDQ^{-1} \cdot   QDQ^{-1} \cdot.... QDQ^{-1} \text{ for n times}
\\ = QDIDIDIDI.......IDQ^{-1} = QD^nQ^{-1}
$$
thus when ==$A$ is diagonalizable, we have $A^n = QD^nQ^{-1}$==

---

#### SideNote: Polynomials of Matrices

==Exp:== Let $f(t) = 3t^2 - t +5$, we can apply $f$ to a square matrix as follows:

Let A = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161453.png" alt="image-20210320161435011" style="zoom:33%;" />  , $f(A) = $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161624.png" alt="image-20210320161624706" style="zoom:33%;" /> = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320161716.png" alt="image-20210320161716524" style="zoom:33%;" />, where we made the constant times the ==Identity Matrix==

---

The same is true for a polynomial of ==linear operators==

==Exp:== Let $T: \R^2 \to \R^2$, $f(t) = 3t^2-t+5$, $f(T) = 3(T\circ T) - T +5I$, where $I $ is a function that: $I(x) = x$

---

### 14.1.2. Eigenvector and Eigenvalue

#### Def

Let $T: V \to V$ be a linear operator on a VS V. A <u>**non-zero**</u> vector $v \in V$ is called an ==eigenvector== if there exists a scalar ==$\lambda$==, such that $T(v) = \lambda v$. The scalar $\lambda$ is called the ==eigenvalue== corresponding to the ==eigenvector $v$==



The same definition applies to matrix (since matrix is one form of representation of linear transformation)$A:$

 v is an ==eigenvector of $A$== if ==$v \neq 0_V$== and $\exists \lambda \in K$ such that ==$Av = \lambda v$==, $A$ can be think of the matrix form of $T$, thus $Av$ or $T(v)$ are the same thing in such situation.

---

### 14.1.3. Characteristic Polynomial of Matrix

#### Def

Let $A \in M_{n \times n}$. The polynomial $f(\lambda) = det(A - \lambda I_n)$ is called the ==characteristic polynomial== of $A$.

---

### 14.1.4. Characteristic Polynomial of  Linear Operator

#### Def

Let T be a linear operator ($T: V \to V$) on an n-dimension VS V with order basis $\beta$. We define the ==characteristic polynomial== of T, $f(\lambda)= det([T]_\beta - \lambda I_n)$

---

### 14.1.5. Algebraic Multiplicity

#### Def

Let $\lambda$ be an eigenvalue of a linear operator matrix with characteristic polynomial $f(t)$. The ==(algebraic) multiplicity== of $\lambda$ is the ==largest positive integer== $k$ for which $(t-\lambda)^k$ is a factor of $f(t)$

#### Example

$f(t) = (t - \lambda_1)^5(t-\lambda_2)^2$ will have algebraic multiplicity of 5 ==(highest power)==

---

### 14.1.6. Eigenspace

#### Def

Let $T$ be a linear operator on a VS V, and $\lambda$ be an eigenvalue of $T.$ 

Define $E_\lambda = \{x\in V | T(x) = \lambda x\} $, we call $E_\lambda$ as ==the eigenspace== of $T$ corresponding to $\lambda$, and each vector ==excpet the zero vector $0_V$,== in $E_\lambda$ must be a eigenvector.

- ==Each eigenvalue corresponds to ONE separate eigenspace!==

---

### 14.1.7. Splites Over Fields

#### Def

A polynomial $f(t) $ in $P(K)$ ==splits over K== if there are scalars $c,a_1....a_n \in K$ such that $f(t) = c(t-a_1)(t-a_2)....(t-a_n)$ (Note $a_i$ are not necessarily distinct). 

#### Example

- $f(t) = t^2 -1$ ==splits over $\R$== because $f(t) = (t-1)(t-1)$

- $f(t) = t^3+t$ does not split over $\R$ since $f(t) = t(t^2+1)$ 
  - However, $f(t)$ splits over $\C$ since $ f(t) = t(t-i)(t+i)$

----

### 14.1.8. Direct Sum Among 3 or more Subspaces

#### Def

Let $W_1, W_2....W_k$ be subspaces of V. Then:

1. $W_1+W_2+....W_K = \{x_1+x_2...x_k | x_i \in W_i\}$

2. We say that $V$ is the ==<u>direction sum</u>== of $W_1......W_k,$ denoted by: $V =W_1 \oplus W_2 \oplus W_3....\oplus W_k$ if 

   $V = W_1+W_2+....W_K$ and $W_j \cap \sum_{i\neq j} W_i = \{0\}$ for each $j, 1 \leq i \leq k$ 

   (==$W_j$ intersects with the sum of all other subspaces but itself must be the 0 set==)

   - For example, if $V = W_1 + W_2 + W_3$, then we need:
     - $W_1 \cap (W_2 + W_3) = \{0\}$
     - $W_2 \cap (W_1 + W_3) = \{0\}$
     - $W_3 \cap (W_1 + W_2) = \{0\}$

---

## 14.2. Theorems and Facts

### Fact 1: Diagonalizable: Concequence and Proof Conditions

A linear operator $T: V\to V$ on a ==finite-dimensional== VS V is diagonalizable ==iff== there exists an ordered basis $\beta$ consisting of eigenvectors. 

Furthermore, if $T$ is ==diagonalizable==, $\beta = \{v_1,v_2....v_n\}$ is an ordered basis of eigenvectors of T, then:

$[T]_\beta = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320163207.png" alt="image-20210320163206918" style="zoom:50%;" />

---

### Fact 2 : Eigenspace is a Subspace

Let $T$ be a linear operator on a VS V, and $\lambda$ be an eigenvalue of $T.$ 

Define $E_\lambda = \{x\in V | T(x) = \lambda x\} $, we call $E_\lambda$ as ==the eigenspace== of $T$ corresponding to $\lambda$, and each vector in $E_\lambda$ must be a eigenvector.

We also know that: ==$E_\lambda$ is a  subspace of V.== 

#### Proof

1. Since $T$ is linear, then $T(0_V) = 0_V = \lambda 0_V$, thus $0_V \in E_\lambda$

2. Let $x,y \in E_\lambda$, need to show that $x+y \in E_\lambda$ ($T(x+y) = \lambda(x+y)$)

   `Process: ` $T(x+y) = T(x) +T(y) = \lambda x + \lambda y = \lambda(x+y)$

3. For $ c\in K$ and $x \in E_\lambda$, we have $T(cx) = c T(x) = c\lambda x = \lambda(cx) \implies cx \in E_\lambda$

Thus, by `1,2,3`, we have shown that $E_\lambda$ is a subspace of $V$.

----

### Fact 3 : Similar matrices have same Characteristic Polynomial

If A and B are similar $n \times n$ matrices, then they have the ==same characteristic polynomial==

#### Proof

A similar to B means that $\exist Q$ such that $A = Q^{-1}BQ$. Need to show that:
$$
det(B-\lambda I_n) = det(A - \lambda I_n) \implies det(B-\lambda I_n) = det( Q^{-1}BQ-\lambda I_n)
$$
Let's start from $det( Q^{-1}BQ- \lambda I_n)= det( Q^{-1}BQ- \lambda Q^{-1}I_nQ)=det( Q^{-1}(B- \lambda I_n)Q) $

then: $det( Q^{-1}(B- \lambda I_n)Q) = det(Q^{-1}) \cdot det(B-\lambda I_n) \cdot det(Q)=det(B- \lambda I_n)$

==Recall: $det(Q) \cdot det (Q^{-1}) = 1$==



---

### Thm 1: Eigenvalue's iff Condition  (Eigenvalue is a root of characteristic polynomial)

Let $A \in M_{n \times n} (K)$. Then a scalar $\lambda$ is an eigenvalue of $A$ if and only if ==$det(A-\lambda I_n) = 0$==

#### Proof

$\lambda$ is an eigenvalue $\iff$ $\exists$ ==non-zero vector $v$== such that $Av = \lambda v$	(==why? By def of eigenvalue==)

$\iff$ $Av-\lambda v = 0_V \iff (A-\lambda I_n) (v) = 0_V$							  (==why? Matrix is distributive==)

We know that $v \neq 0_V$ by assumption and we also know that <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320164528.png" alt="image-20210320164528487" style="zoom: 67%;" />

$\iff det(A- \lambda I_n) = 0$. ==END OF PROOF==

because in this situation, $det(A- \lambda I_n)$ must be 0, to maintain the equation: ==$(A-\lambda I_n) (v) = 0_V$==



==Note:== since we connect all our logic steps with $\iff,$ no need to show both direction

---

#### Example

1. 

Given <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320164941.png" alt="image-20210320164941055" style="zoom:50%;" />, we have:

 <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320164955.png" alt="image-20210320164955676" style="zoom:50%;" /> = <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210320165030.png" alt="image-20210320165030247" style="zoom: 50%;" />

$(\lambda + 2)(\lambda -5) = 0$, ==$\lambda_1 =-2, \lambda_2 = 5$ are 2 eigenvalues==

---

### Thm 2: Cayley-Hamilton Theorem: Square Matrix is root of Char. Poly

==Every square matrix is a root (solution) of its characteristic polynomial==



==Note:== prove this in HW5, otherwise use it without proof

----

### Thm 3: Eigenvectors with distincet eigenvalues are LI

Suppose $v_1,v_2.....v_n$ are eigenvectors of a matrix $A$ corresponding to ==distinct== eigenvalues $\lambda_1 ,\lambda_2...\lambda_n$

Then $v_1,v_2...v_n$ are LI. ==Note: eigenvectors are non-zero vector==

#### Proof

We do `Proof by contradiction`.

Suppose $v_1....v_n$ are LD. Then choose the minimum LD subcollection of $v_1....v_n$.

Let $v_1....v_s$ be such minimum LD subcollection. $a_1v_1 +a_2v_2+....a_sv_s = 0$. There must exists a ==$v_j = v_1 \neq 0$==

We can assume without loss of generality that ==$v_1 = b_2v_2+....+b_sv_s$== where we have renamed the non-zero $v_j \to v_1, a_j \to a_1, b_i = \frac{-a_i}{a_1}$

then we have:
$$
Av_1  = A(b_2v_2+....b_sv_s) \\ \implies
\lambda_1v_1 = b_2Av_2 +....b_sAv_s \
\\\implies \lambda_1v_1=b_2\lambda_2v_2 +b_3\lambda_3v_3 +....b_s\lambda_sv_s
$$
we now have:

1. $v_1 = b_2v_2+....+b_sv_s$

2. $ \lambda_1v_1=b_2\lambda_2v_2 +b_3\lambda_3v_3 +....b_s\lambda_sv_s$

3. From `1`, we get: $\lambda_1 v_1 = b_2\lambda_1v_2+....+b_s\lambda_1v_s$

4. From `2` and `3`, we have the equation:
   $$
   b_2\lambda_1v_2+....+b_s\lambda_1v_s = b_2\lambda_2v_2 +b_3\lambda_3v_3 +....b_s\lambda_sv_s
   \\ \implies b_2(\lambda_2-\lambda_1)v_2 + b_3(\lambda_2-\lambda_1)v_3 +.....b_s(\lambda_2-\lambda_1)v_s = 0
   $$

5. Then, we must have the set of $\{v_2,v_3....v_s\}$ be ==LI== since $\{v_1....v_s\}$ was the ==smallest LD set==. If $\{v_2,v_3....v_s\}$ was LD, then our assumption must be contradictory.

6. Sicne $\{v_2,v_3....v_s\}$ is LI, the coefficients must be 0: ==$ b_2(\lambda_2-\lambda_1) =  b_3(\lambda_2-\lambda_1) =.... b_s(\lambda_2-\lambda_1) = 0$== 

   However, since we have distinct eigenvalues ($ (\lambda_2-\lambda_1) \neq 0$), thus $b_2= b_3 =....b_s = 0$ must be true.

   Thus, $v_1 = b_2v_2+....+b_sv_s = 0+0+0+....+0=0$, which is a `contradiction` since we have assumed that $v_1 \neq 0$. 

7. In conclusion, $v_1....v_n$ can not be LD, they must be ==LI==.

---

### Thm 4: Characteristic Poly of matrix A ,with product of distinct factors, is similar to Diagonal Matrix

Suppose the ==characteristic polynomial== of an ==$n \times n$ matrix A== is the product of $n$ ==distinct factors==
$$
f(\lambda) = (\lambda - \lambda_1) \cdot(\lambda - \lambda_2).....\cdot(\lambda - \lambda_n)\\
\text{where: } \lambda_i \neq \lambda_j, i\neq j
$$
Then A is similar to $ D= $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210323212152.png" alt="image-20210323212152047" style="zoom:33%;" />

#### Proof

Since the eigenvalues are distinct, the corresponding eigenvectors are LI. Since we have n eigenvector and the vector space is of $dim = n,$ the eigenvectors form a basis. Since we ==have a basis of eigenvectors,== Based on the [Diagonalizable Fact](####Fact (Diagonalizable: Concequence and Proof Conditions)), we can know that A must be diagonalizable, which implies that A must be similar to D, the diagonal matrix.



1.    <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210323213307.png" alt="image-20210323213307458" style="zoom:50%;" />

2.    <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210323213333.png" alt="image-20210323213333414" style="zoom:50%;" />

----

### Thm 5: Dimension of Eigenspace relates to Algebraic Multiplicity

Let T be a linear operator on a finite dimensional vector space V. 

Let $\lambda$ be an eigenvalue of $T$ having ==(algebraic) multiplicity $m$.== Then we have the following:
$$
1 \leq dim(E_\lambda) \leq m
$$

#### Proof

1. $1 \leq dim(E_\lambda)$

   Recall $\lambda$ is a solution to $det([T]_\beta - \lambda I_n) = 0$, where $n = dim(V), \beta$ is an ordered basis of V.

   - The iff condition of eigenvector $\lambda$

     Having $det(M) = 0 \implies M$ is not invertible, which $\iff$ $M$ has non-trivial nullspace, so $N(M)$ contains a non-zero vector `v`. So that we have: 
     $$
     ([T]_\beta - \lambda I_n)v = 0_V \implies [T]_\beta v - \lambda I_n v = 0_V
     \\ \implies [T]_\beta v = \lambda v
     $$
     thus $\iff$ ==v is an eigenvector== $\iff v \neq 0_V \in E_\lambda \iff dim(E_\lambda) \geq 1$ 

     since we have shown that eigenspace has at least one non-zero vector

2. $dim(E_\lambda) \leq m$

   Choose an ordered basis $\{v_1,v_2....v_p\}$ for $E_\lambda$, so $dim(E_\lambda) = p, $ and we need to show that $p \leq m$

   - Now, we extend this basis to an ordered basis of ==$V: \gamma = \{v_1,v_2....v_p,v_{p+1}...v_n\}$==

     What does $[T]_\gamma$ look like? Let's look at a small example first

     - ==Example:== <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210327155429.png" alt="image-20210327155429372" style="zoom:50%;" />

       By the definition of the eigenvalues, we have $Av_i = \lambda_i v_i, A$ in here is expressed in $[T]_\gamma$,

       thus we have: ==$[v_1]_\gamma$ means express $v_1$ with the bases of the ordered basis $\gamma$==

        <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210327162251.png" alt="image-20210327162250849" style="zoom:50%;" />

       where $v_1,v_2$ are basis of eigenspace $E_\lambda$ 

     

   - Back to the general case, now we know what $[T]_\gamma$ looks like:

     <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210327162621.png" alt="image-20210327162621332" style="zoom:33%;" />

     ​	where the block matrix on the top right `B` or at bottom left `zero matrix` are not necessarily square.

     thus ==$det([T]_\gamma - tI_n) = $== <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210327162810.png" alt="image-20210327162810588" style="zoom:50%;" />

     $= det((\lambda -t)I_p) \cdot det(A -tI_{n-p})$ ==$ = (\lambda -t)^p \cdot det(A -tI_{n-p})$== 

     Thus $\lambda$ has multiplicity at least p, thus $m \geq p = dim(E_\lambda)$

     ---

     

==**Overall logic:**== Given any ordered basis $\beta$ of $E_\lambda$, we can always extend it to a ordered basis of V since $E_\lambda$ is a subspace of V. With that extended ==ordered basis $ \gamma$,== we can compute the maximum possible `multiplicity` of $\lambda$, where we can prove that with $[T]_\gamma,$ $det([T]_\gamma - tI_n) =  (\lambda -t)^p \cdot det(A -tI_{n-p}) $, which implies that ==the multiplicity of $\lambda$,  which is m,== must be at least $p, \implies m \geq p = dim(E_\lambda)$. 

==Such property holds true even for the largest basis we can possibly have, thus it always hold true.==

---

### Lemma 1: Sum of eigenvectors is zero vector => they are ALL ZERO Vectors

Let T be a linear operator, and $\lambda_1,\lambda_2....\lambda_k$ be distinct eigenvalues. For each $i = 1,2,3...k$. Let $v_i \in E_{\lambda_i}$ ($v_i$ must be an eigenvector ==unless== it is the 0 vector $0_V$)

If $v_1 + v_2 +.....v_k = 0_V$, then $v_1 = v_2 =....0_V$

#### Proof

Suppose otherwise (prove by contradiction): there are non-zero vectors in $v_1 + v_2.... +v_k = 0_V$.

Then we will have: <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210330182410.png" alt="image-20210330182410717" style="zoom: 50%;" />

We rearrange the sum to list the non-zero vectors ==at the beginning== and relabel them as:

$w_1, w_2 ,....w_l$ thus they are non-zero eigenvectors and $w_1 + w_2 + \dots +w_l = 0_V$ (it is true because we have removed all ==zero vectors== and left with all non-zero vectors)

But if so, it causes contradiction since $w_1,w_2,\dots w_l$ will be LD, which is impossible since the ==eigenvectors from distinct eigenspaces are LI (thm learnt before)== 



- **Thus the opposite of our assumption is true: if $v_1 + \dots v_k = 0_V$, then necessarily, $v_1 = v_2 = ..v_k = 0_V$**

----

### Thm 6: Finite Subset of Eigenspace (distinct eigenvalues) are LI

> - Using Lemma 1

Let T be a linear operator on a VS V, and let $\lambda_1,\lambda_2...\lambda_k$ be `distinct eigenvalues of T`

For each $i = 1,2....k$, Let $S_i$ be a finite LI subset of $E_{\lambda_i}$, then $S = S_1 \cup S_2 \cup S_3...\cup S_k$ is LI.

#### Proof

Let $S_i = \{v_{i1},v_{i2}.....v_{in_i}\}$, and $S_i \in E_{\lambda_1}$

For example:

1. $S_1 = \{v_{11}, v_{12}.....v_{1n_1}\}$
2. $S_2 = \{v_{21}, v_{22}.....v_{2n_2}\}$
3. $S_3 = \{v_{31}, v_{32}.....v_{3n_3}\}$

==Need to show that $S_1 \cup S_2 \cup S_3$ is LI==

Thus, we let $a_{11}v_{11} + a_{12}v_{12} +...a_{1n_1}v_{1n_1} +  \\a_{21}v_{21} + a_{22}v_{22} +...a_{2n_2}v_{2n_2} +\\a_{31}v_{31} + a_{32}v_{32} +...a_{3n_3}v_{3n_3} = 0_V$ and we want to show all of their coefficients are 0.

we denote them into: $w_1 + w_2 +w_3 = 0_V$, we know that $w_1 \in E_{\lambda_1} \\ w_2 \in E_{\lambda_2} \\w_3 \in E_{\lambda_3}$

By `Lemma 1`, we have $w_1 = w_2 = w_3 = 0_V$

which implies: $a_{11}v_{11} + a_{12}v_{12} +...a_{1n_1}v_{1n_1} = 0_V \implies a_{11} = a_{12} =.... a_{1n_1} = 0$ since we chose $w_1$ to be LI.

Similar process holds true for $w_2, w_3$ and more generally.

----

### Thm 7: Diagonalizability: iff conditions and One More Concequence

Let $T: V \to V$ be a linear operator such that the characteristic polynomial of T ==splits==.

Let $\lambda_1....\lambda_k$ be distinct eigenvalues of T. Then:

1. $T$ is diagonalizable if and only if the (algebraic) multiplicity of $\lambda_i$ is equal to $dim(E_{\lambda_i})$ for all $1 \leq i \leq k$ (given T splits)

2. If $T$ is diagonalizable, and $\beta_i$ is an ==ordered basis== for $E_{\lambda_i}$ for $1 \leq i \leq k$, then $ \beta = \beta_1 \cup \beta_2.... \cup \beta_k $, where $\beta$ is an ordered basis of V. (In Thm 6, we know that $\beta_1,\beta_2....\beta_k$ will be LI)
   - ==<u>Note:</u>== You will need to make choice of order of $E_{\lambda_i}$

---

### Thm 8: Test for Diagonalizability (formal version of Thm 7)

Let T be a linear operator on an n-dimensional vector space. Then T is diagonalizable if and only if the following ==2 conditons hold: (both hold)==

1. The characteristic polynomial of T ==splits==
2. The (algebraic) ==multiplicity of each eigenvalue== ($\lambda$) is equal to the ==dimension of the corresponding eigenspace.==

==**Same holds true for matrices.** If fact, we need to transform the T into a matrix first==

----

### Thm 9: Direct Sum of Eigenspaces Leads to Diagonalizability

A linear operator T on a finite-dimensional vector space V is diagonalizable if and only if V is the direct sum of the eigenspaces of T.

- ==Just use it==



#### Example

1. Is <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210401170731.png" alt="image-20210401170731625" style="zoom:50%;" /> diagonalizable over $\R$?

   1. ==First, check determinant:== $det(A - \lambda I_3) = det$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210401171027.png" alt="image-20210401171026870" style="zoom:33%;" /> $= (3- \lambda)(3- \lambda)(4- \lambda)$, so the characteristic polynomial ==splits over $\R$==, we have 2 eigenvalues: 

      - $\lambda_1 = 3$ with algebraic multiplicity = 2 (highest power being 2)
      - $\lambda_2 = 4$ with algebraic multiplicity = 1 (highest power being 1)
      - ==Thus, the first condition is checked: the characteristic polynomial does split==

   2. ==Then, we need to check second condition: multiplicity is same as dimension of eigenspace==

      Let $v = \left ( \matrix{x \\ y \\ z} \right)$, test $\lambda_1 = 3,$ $Av = 3v \implies$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210401171617.png" alt="image-20210401171617583" style="zoom:50%;" />

      which implies that <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210401171642.png" alt="image-20210401171642781" style="zoom:33%;" /> $\implies y=0, z = 0$

      so <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210401171736.png" alt="image-20210401171736008" style="zoom:33%;" />, we can choose $(1,0,0)$ to be the ==eigenvector,== since we only have one non-zero eigenvector, we have $E_{\lambda_1} = \{x(1,0,0) | x \in \R\}$, thus $dim(E_{\lambda_1}) = 1$, which is ==not equal to 2 (multiplicity of eigenspace of $\lambda_1 = 3 $==. Thus the second condition failed

   3. ==Conclusion:== **A is not diagonalizable.**

---



## 14.3. Diagonalization Examples

### Example 1: How to get eigenvalues and eigenvectors

Let $A = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325181959.png" alt="image-20210325181959775" style="zoom:33%;" /> be a matrix in $M_{2 \times 2}(\R).$ Is A diagonalizable?

1. We first find the ==characteristic polynomial of A==:

   $det(A -\lambda I_2) = det$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325182238.png" alt="image-20210325182238095" style="zoom:33%;" /> = $(1- \lambda)(2-\lambda) - 12$ = $\lambda^2 - 3\lambda - 10 = (\lambda+2)(\lambda-5)$

   thus we have $det(A -\lambda  I_2) =  (\lambda+2)(\lambda-5), \lambda_1 = -2, \lambda_2=5$. We have 2 distinct eigenvalues, thus $A$ is diagonalizable.

   so we will have $D=$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325182840.png" alt="image-20210325182839921" style="zoom:33%;" /> or $D = $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325182926.png" alt="image-20210325182926343" style="zoom:33%;" /> (either one works)

   

2. Now we find ==eigenvectors:== Let $v \in \R^2$ such that $Av = \lambda_1 v_1   = -2 v_1 $

 <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325191426.png" alt="image-20210325191425875" style="zoom:33%;" />, which means that $v_1 = $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325191527.png" alt="image-20210325191527776" style="zoom:33%;" />

thus we have one eigenvector $v_1 = \left(\matrix{1 \\-1} \right)$

 ==Note: any multiple (excluding 0) of,== $\left(\matrix{1 \\-1} \right)$, ==is also an eigen vector==

---

for $\lambda_2 = 5,$ similar process:

 <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325191957.png" alt="image-20210325191957039" style="zoom:50%;" />, thus we have $v_2 = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325192021.png" alt="image-20210325192021080" style="zoom:33%;" />

we can take $v_2 = \left(\matrix{3 \\4} \right)$ as the ==second eigenvector==

----

3. we know that <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325192219.png" alt="image-20210325192219512" style="zoom:33%;" />, and $D = Q^{-1}AQ$

   where <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325192449.png" alt="image-20210325192449043" style="zoom:50%;" />

   the first column is the ==first eignevector $v_1$==, the second column is the ==second eigenvector $v_2$==

   Then it is easy to verify that $D = Q^{-1}AQ$ actually holds true now since we know $D,A,Q$ at this point.

---

### Example 2: Real Field fails

- Is $A = \left(\matrix{0 &1 \\-1 & 0} \right) \in M_{2 \times 2}(\R)$ diagonalizable?

$det(A - \lambda I_2) = det \left(\matrix{-\lambda &1 \\-1 & -\lambda} \right) = \lambda^2 +1$ which has ==no root in $\R$==. ==We say that $A$ is not diagonalizable over $\R$==



----

### Example 3: Complex Field works

- Is $A = \left(\matrix{0 &1 \\-1 & 0} \right) \in M_{2 \times 2}(\C)$ diagonalizable? ==(In complex filed now)==

$det(A - \lambda I_2) = det \left(\matrix{-\lambda &1 \\-1 & -\lambda} \right) = \lambda^2 +1 \implies \lambda_1 = i, \lambda_2 = -i$ 

we are able to find the ==eigenvalues now, thus we say that A is diagonalizable over $\C$==. Field matters.

Similar process as in Example 1, we obtain:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325193218.png" alt="image-20210325193218195" style="zoom:50%;" />

---

### Example 4: Algebraic Multiplicity and Geometric Multiplicity*

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325193355.png" alt="image-20210325193355475" style="zoom:50%;" /> Is A diagonalizable?

$det(A - \lambda I_2) = det \left(\matrix{1-\lambda &0 \\1 & 1-\lambda} \right) = (1-\lambda)^2  \implies \lambda = 1$. ==We have only 1 eigenvalue==

we say that $\lambda$ has ==algebraic multiplicity as 2==

- algebraic multiplicity is the power (degree) of the $\lambda$ factor. In here, we have it equals to 2.



Now, we find eigenvector:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325193724.png" alt="image-20210325193724068" style="zoom:50%;" />

where we can say that $v =\left(\matrix{0 \\1} \right)$ is <u>an</u> eigenvector corresponding to $\lambda = 1$

We say that $\lambda$ has ==geometric multiplicity as 1==

- geometric multiplicity is the number of eigenvector (the basic format) we find that correspond to the same eigenvalue. ==Note: one eigenvalue can give more than one eigenvector==



Since we only find ==1 eigenvector== in  (we need at least 2 eigenvectors to form a basis of $\R^2$), thus A ==is not diagonalizable==. We also say that $\lambda$ is `deficient`

- `deficent:` will be explained later



---

### Example 5: Is diagonalizable

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325194409.png" alt="image-20210325194409721" style="zoom:50%;" />, is A diagonalizable?



$det(A - \lambda I_3) = det$ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325194440.png" alt="image-20210325194440576" style="zoom:33%;" /> = $(1 - \lambda)^3 \implies \lambda = 1$ with ==algebraic multpicity = 3==

we calculate the eigenvectors:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210325195023.png" alt="image-20210325195023856" style="zoom:50%;" /> $=x \left(\matrix{1 \\0 \\0} \right) +y \left(\matrix{0 \\1 \\0} \right) + z \left(\matrix{0\\0 \\1} \right)$

thus we have ==3 eigen vectors== associated with one eigenvalue $\lambda = 1$, thus the ==geometric multiplicity = 3==

and we say that A is ==diagonalizable== since we have enough eigenvectors to form the basis of $\R^3$

---

# 15. Minimal Polynomial

## 15.1. Concept Definitions

### 15.1.1. Monic Polynomial

#### Def

A polynomial $f(t)$ is ==monic== if its leading coefficient equals 1

- ==leading coefficient: the coefficient of the highest power term in the polynomial==



#### Example

1. $f(t) = t^3 -t +1$ is monic since $1 \cdot t^3$

2. $f(t) = 2t^2 - 1$ is ==not monic== since $2 \cdot t^2$ and $2 \neq 1$

-----

### 15.1.2. Minimal Polynomial

#### Def

Let A be a matrix of size $n \times n$, the ==minimal polynomial, $m_A(t)$== of A is the ==monic polynomial of least degree== such that $m_A(A) = 0_{n \times n}$



#### <u>Explanation</u>

Given a square matrix A, look at all possible polynomial $f(t)$ such that $f(A) = 0$

- ==Note:== there is ==at least one== such polynomial: ==by Cayley-Hamilton==, the characteristic polynomial $f_A(t)$ satisfies $f_A(A) = 0_{n \times n}$ (every square matrix is a root of its own characteristic polynomial)

-------

### 15.1.3. Companion Matrix

> - when $f_A(t) = m_A(t)$, we can 反推 what is matrix A that satisfies such conditon (it is the companion matrix)

#### Def

Consider ==the monic== polynomial: $f(t) = t^n + a_{n-1}t^{n-1} +a_{n-2}t^{n-2} ... a_0$

Let $C(f)$ be the $n \times n$ matrix having the following form:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411175348.png" alt="image-20210411175348630" style="zoom:50%;" />

- Where except the subdiagonal and the last column, everywhere else are 0.

Then, the ==characteristic polynomial of $C(f)$ is $f(t)$,== and in this case, the ==minimal polynomial of $C(f)$ is also equal to $f(t)$==



#### Example 1

Find a matrix A such that $f_A(t) = m_A(t) = t^2 - 5t +1$

Our $C(f)$ will look like <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411175753.png" alt="image-20210411175753056" style="zoom:33%;" />

Now let's verify if such matrix satisfies the condition

$det(C(f) - tI_2) = $<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411183255.png" alt="image-20210411183255203" style="zoom:33%;" /> $= -5t+t^2 + 1$ which is exactly same as $f_A(t) = m_A(t)$

Thus $A = C(f) $

----

#### Example 2

$f(t) = t^4 - t^4 +5t^3 -4t^2 +3t +10$, then the ==companion matrix== $C(f)$ looks like:

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411183909.png" alt="image-20210411183909769" style="zoom:33%;" />

which can be verified that $det(C(f) - t I_5) = f_{C(f)}(t) = m_{C(f)}(t)$ (ez calculation)



------

## 15.2. Theorems

### Thm 1: Divisibility and Uniqueness of Minimal Polynomial

Let $m_A(t)$ be a minimal polynomial of an $n \times n$ matrix A, then:

1. For any polynomial $g(t),$ if $ g(A) = 0_{n \times n}$, then $m_A(t)$ ==divides== $g(t)$. In particular, $m_A(t)$ divides the characteristic polynomial of A
   - ==Divides $\implies g_A(t)/m_A(t) $ will give another polynomial without remainder==

2. The minimal polynomial of A is ==unique.== 



#### Proof

1. Let $g(t)$ be a polynomial such that $g(A) = 0_{n \times n}$

   By the long division algorithm, there exists polynomials $q(t), r(t)$ such that
   $$
   g(t) = q(t) m_A(t) + r(t)
   $$
   with $deg(r(t)) < deg(m_A(t))$ ==(fact)==, Then we plug in $A$:
   $$
   g(A) = q(A)m_A(A) + r(A)\\ g(A) = 0_{n \times n} , m_A(A) = 0_{n \times n} \text{ by definition}\\
   then: 0_{n \times n} = q(A) \cdot 0_{n \times n} + r(A)\implies 0_{n \times n} = r(A)
   $$


   thus the remainder $r(A)$ is zero matrix, thus $m_A(t)$ divides $g(t)$ ==PROOF 1 DONE==

2. Suppose $m_A(t)$ and $m_A'(t)$ are both minimal polynomial for A, then $m_A(A) = m_A'(A) = 0_{n \times n}$

   By ==Proof 1,== we must have $\left\{\matrix{1. m_A'(t) \text{ divides } m_A(t) \\ 2. m_A'(t)\text{ divides }m_A'(t)} \right.$ both be true, which implies that $m_A'(t) = m_A(t)$

   thus, ==PROOF 2 DONE==

    <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210408180951.png" alt="image-20210408180951592" style="zoom: 50%;" />

----

### Thm 2: Same irreducible factors for characteristic and minimal polynomial (iff conditions)

The characteristic polynomial and the minimal polynomial of a square matrix A have the same ==irreducible factors==

- A factor is irreducible if it can not be factored further. For example, ==$(t-1)$== is irreducible.

-----

### Thm 3: Roots of minimal polynomial are Eigenvalues

> - Since characteristic polynomial and minimal polynomial have the same ==irreducible factors==, then the roots of minimal polynomial must be the roots of characteristic polynomial, and the roots of characteristic polynomial are eigenvalues (short informal proof)

A scalar $\lambda$ is an eigenvalue of the square matrix A ==if and only if== $\lambda$ is a root of $m_A(t)$ (the minimal polynomial of A)

----

### Thm 4: Multiply degree 1 linear factors with distinct eigenvalues means Diagonalizable (iff condition)

Let A be a square matrix, then A is diagonalizable ==if and only if== the minimal polynomial of A $m_A(t) = (t -\lambda_1 ) \cdot (t -\lambda_2 ) \cdot (t -\lambda_3 )...(t -\lambda_k)$ where $\lambda_1,\lambda_2...\lambda_k$ are ==distinct eigenvalues of A==.

- In descriptive words, if one can write the minimal polynomial into ==multiples of linear factors with degree 1 (meaning of writing in such form)==

#### Example:

If A is diagonalizable and the characteristic polynomial of A is $f_A(t) = (t-1)^3(t-2)^2(t-6)$

Then based on the theorem, we know the minimal polynomial of A ==must be== $m_A(t) = (t-1)(t-2)(t-6)$ where all eigenvalues are distinct and each linear factor `(t-1), (t-2), (t-6)` has power of 1.

==In other words, if $deg(m_A(t)) \neq 1$, then matrix A can not be diagonalizable (one factor among the linear factors does not have degree 1)==

------

### Thm 5: char. poly Divides minimal poly to the power of n

Let A be a square matrix with characteristic polynomial $f_A(t),$ and minimal polynomial $m_A(t).$

Suppose A is $n \times n$, then $f_A(t)$ ==divides== $[m_A(t)]^n$

####  Example:

Suppose: $f_A(t) = (t^2+1)^{\textcolor{red}3}(t-1)^{\textcolor{red}2}(t-3)^{\textcolor{red}1}$ and $m_A(t) = (t^2+1)(t-1)(t-3)$

we know $n = 3 +2 + 1 = 6$ (==sum of the powers of linear factors in $f_A(t) $==)

then $[m_A(t)]^{\textcolor{red}6} = (t^2+1)^6(t-1)^6(t-3)^6 = [(t^2+1)^3(t-1)^2(t-3)^1] \cdot [(t^2+1)^3(t-1)^4(t-3)^5] $



==Note:== If A is $n \times n$, then $deg(f_A(t)) = n$

--------------

## 15.3. Examples

### Example 1: Find the minimal polynomial (try all plug-in possibilities)

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210408184641.png" alt="image-20210408184641431" style="zoom:33%;" />, find the minimal polynomial of A

==Sol:== 

$det(A-tI_3) = - (t-2)^2(t-3)$ where $(t-2), (t-3)$ are irreducible factors, by ==Thm 2,== we know that these 2 factors must appear in $m_A(t)$

<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210408184906.png" alt="image-20210408184906596" style="zoom:50%;" />

Now we need to decide which one we choose for the answer by ==plug in A back into these 2 functions== 

==The only way we solve these kind of question is by Trying All Possible Functions by plug in A==

Check $(A- 2I_3) (A -3 I_3)$ is $0_{n \times n}$ or not. It turns out that it is $0_{n \times n}$, by the uniqueness, we obtain:
$$
m_A(t) = (t-2)(t-3)
$$
==Note:==

1. each of the term must be monic (leading coefficient is +/- 1)

2. if $f_A(t) = (t^2+1)(t-1)^3(t-3)^2(t-5)$ is characteristic polynomial for A where $A \in M_{n \times n} (\R)$

   then $m_A(t)$ must have: $(t^2+1),(t-1),(t-3),(t-5)$, all possible solutions are listed:

$$
(t^2 + 1)^1(t-1)^{1,2,3}(t-3)^{1,2}(t-5)^1
$$

we plug in $A$ into all these different possibilites and to find the minimal polynomial

3. If $A \in M_{n \times n}(\C)$, then all possible cases become:

$$
(t-i)(t+i)(t-1)^{1,2,3}(t-3)^{1,2}(t-5)^1
$$

-----

### Example 2: Find Matrix that makes a poly equal to 0 matrix

Find all matrices $A \in M_{2 \times 2} (\R)$ such that $A^2 -3A +2I_2 = 0_M$ ==Note: this polynomial is NOT the char. polynomial==

==<u>**Sol**</u>==

Let $g(t) = t^2 - 3t +2$, then $g(A) = 0_M$

we know $g(t) = (t-1)(t-2)$ so the minimal polynomial must divide $g(t)$ based on ==Thm 1==, Thus: $m_A(t) = \left \{\matrix{t-1  \;\;\ or \\ t-2 \;\;\ or\\ (t-1)(t-2)} \right.$



==**<u>Quick Reminder:</u>** $m_A(A) = 0_M$ is the definition of minimal polynomial==

One of these 3 possibilities must be the answer:

1. If $m_A(t) = t-1$, then $m_A(A) = A - I_2 = 0_M , A = I_2$

2. If $m_A(t) = t-2,$ then $m_A(A) = A - 2I_2 = 0_M, A = 2I_2$

3. If $m_A(t) = (t-1)(t-2),$ then $m_A(A) = (A-I_2)(A-2I_2) = 0_M$ and $m_A(t-1)(t-2)$ is indeed the ==minimal polynomial based on Thm 4.== with eigenvalues $1,2$ and $A$ is ==diagonalizable== as well based on ==Thm 4==

   Based on Thm 4 from 14. Diagonalization, we know that

   - <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411191942.png" alt="image-20210411191942469" style="zoom: 80%;" />

   Thus, we can say that $A$ is similar to $D=$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411190529.png" alt="image-20210411190529090" style="zoom: 50%;" />

==Final Answer:== 

Since we have 3 cases, thus $A$ can be any of these following cases:

1. $A = I_2$
2. $A = 2I_2$
3. $A$ is similar to <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210411190529.png" alt="image-20210411190529090" style="zoom: 50%;" />

where $A^2 -3A +2I_2 = 0_M$ can be satisfied.

----

### Example 3:  Using Thm 4 to show Diagonalizable

Let $ A \in M_{2 \times 2} (\R)$ such that $A^3 = A$

1. **Prove that $A $ is diagonalizable**

   ==<u>**Sol**</u>==

   1. Derive into a polynomial formula: $A^3 =A \implies A^3-A = 0_M$, Let $g(t) = t^3 -t,g(A) = A^3 -A=0_M$

   thus the minimal polynomial $m_A(t)$ must divide $g(t) = t^3 - t = t(t+1)(t-1)$

   2. $m_A(t) = \left \{ \matrix{t \\ t+1 \\ t-1\\t(t-1) \\t(t+1) \\(t-1)(t-1) \\t(t-1)(t+1)}\right.$ since all of them divides $g(t)$ and $m_A(t)$ can ==only be one of them==

   3. By ==Thm 4:== A is diagonalizable if and only if $m_A(t) = (t- \lambda_1) \cdot  (t- \lambda_2).... (t- \lambda_n)$ with ==distinct linear factors with power of 1==

   4. Since all possible cases here can be written with ==distinct linear factors with power of 1 and $m_A(t)$ is one of them,== thus A is diagonalizable
      - ==Note:== If there is a possible case such as $(t^2+1)$, then $A$ is diagonalizable if $m_A(t) = $ all other cases but $(t^2 +1)$ since if that is the case, A is ==no longer dinagonalizable== （分情况）, thus we know that $A$ is 100% diagonalizable

   -----

   

2. **Suppose $B^3 + B = 0_M, B \in M_{n \times n} (\R). $ When is B diagonalizable?**

   ==**<u>Sol</u>**==

   We can derive $g(t) = t^3 +t = t(t^2+1)$ and we know $m_B(t)$ must divide $g(t)$

   Therefore we have 3 possible cases:

   1. $t$
   2. $t^2 +1$
   3. $t(t^2+1)$

   Based on ==Thm 4,== $B$ is only diagonalizable if $m_B(t) = t$ (the other 2 cases are not)

   **<u>==But what is B exactly?==</u>**

   ​	Since we know that $m_B(B) = 0_M$ (def of minimal polynomial) and $m_B(t) = t$

   ​	thus $B = 0_M$ and only if that is the case, B will be diagonalizable.

   ==Note:== If we change the field into $\C$,then we have:

   <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210413105738.png" alt="image-20210413105653715" style="zoom: 50%;" />

   since all possible cases of minimal polynomial are distinct factors of degree 1, then $B$ is diagonalizable (==Thm 4 again==)

-------

### Example 4: Find Minimal Polynomial of Linear Operator & Check Digaonalizable

3. **Let $D$ be the linear operator on $P_2(\R)$, $D: P_2(\R) \to P_2(\R)$ such that $D(g(x)) = g'(x)$, Compute the minimal polynomial of $D$**

   **<u>==Sol==</u>**

   Let $\beta = \{1,x,x^2\}$ be the standard matrix of $P_2(\R),$ then

   - $D(1) = 0 = 0 + 0x +0x^2$ $ \implies (0,0,0)$
   - $D(x) = 1 = 1 +0x + 0x^2$ $  \implies(1,0,0)$
   - $D(x^2) = 2x =0 +2x +0x^2$ $ \implies(0,2,0)$

   Thus, $[D]_\beta =$<img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210413110528.png" alt="image-20210413110528425" style="zoom:50%;" />, and characteristic polynomial of $D$ is:

   $det([D]_\beta - tI) = $ <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210413110807.png" alt="image-20210413110807047" style="zoom:33%;" /> = $-t^3$

   Since char. poly of $D$ has irreducible factor $t$, then the possible cases of $m_{[D]_\beta}(t)$ are:

   1. $t$
   2. $t^2$
   3. $t^3$

   ==We are given the char. poly, thus we can compute what exactly is the minimal poly of $[D]_\beta $ by tring pluging in all possible cases==

   1. If $m_{[D]_\beta} (t) = t, then\; m_{[D]_\beta} ([D]_\beta) = [D]_\beta = 0_M$, but we know that $[D]_\beta \neq 0_M$, thus $t$ is not the case
      - As a consequence, we know $[D]_\beta$ is ==not diagonalizable== since $m_{[D]_\beta}(t) \neq t$ which is the only case that can make $[D]_\beta$ diagonalizable
   2. If $m_{[D]_\beta}(t) = t^2, then \; m_{[D]_\beta} ([D]_\beta) = ([D]_\beta)^2 = 0_M $, by using calculator, we know <img src="https://gitee.com/ruoyu666/studyimg/raw/master/images/20210413112123.png" alt="image-20210413112123742" style="zoom:33%;" /> $ \neq 0_M$. thus $m_{[D]_\beta} (t) \neq t^2$
   3. If $m_{[D]_\beta}(t) = t^3, then \; m_{[D]_\beta} ([D]_\beta) = ([D]_\beta)^3 = 0_M $, since the other 2 cases failed to be the minimal polynomial, $m_{[D]_\beta} (t)$ must be $t^3$ and it is easy to verify that $[D]_\beta]^3 = 0_M$ 

==**Conclusion: B is not diagonalizable**==































































