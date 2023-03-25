# Question 1

## a)

To show $H_v$ is an orthogonal matrix, which means we need to show: $H_v^T H_v = I$
$$
H_v^T = (I- 2\frac {vv^T}{v^Tv})^T = I - 2\frac {(vv^T)^T}{(v^Tv)^T}  = I - 2\frac {vv^T}{v^Tv}
\\ H_v = I- 2\frac {vv^T}{v^Tv} = H_v^T
\\
\begin{aligned}
 H_v^TH_v &=(I - 2\frac {vv^T}{v^Tv}) (I - 2\frac {vv^T}{v^Tv}) 
\\&= I -4\frac {vv^T}{v^Tv} +4 \frac {vv^Tvv^T}{v^Tvv^Tv}
\\ &= I -4\frac {vv^T}{v^Tv}+4 \frac {v^Tvvv^T}{v^Tvv^Tv}
\\ &= I -4\frac {vv^T}{v^Tv}+4 \frac {vv^T}{v^Tv}
\\ &= I
\end{aligned}
$$

## b)

To show $H_v$ is symmetric, we need to show: $H_v = H_v^T$
$$
H_v^T = (I- 2\frac {vv^T}{v^Tv})^T = I - \frac {2}{v^Tv} (vv^T)^T = I - 2\frac {vv^T}{v^Tv}
\\ H_v = I- 2\frac {vv^T}{v^Tv} = H_v^T
$$

## c)

From b, we know that $H_v =H_v^T$, thus $H_v^2 = H_v^TH_v$

From a, we know that $H_v^TH_v = I$

Thus by combining the result from a and b, we know that $H_v^2 = I$





## d)

Expand a orthogonal basis $\{v, v_2,...v_m\}$ of $\R^m,$ we have the following:
$$
v^Tv = 1, H_v v = v -2\frac {vv^Tv}{v^Tv} = v - 2v = -v
$$
Then the eigen value is $-1$ and the eigen vector associated with it is $v$
$$
v^Tv_j = 0, H_v v_j = v_j - 2\frac {vv^Tv_j}{v^Tv} = v_j - 0 = v_j, v_j \in \{v_2,...v_m\}
$$
The eigen value is $1$, and there are $m-1$ corresponding eigen vectors since that’s the cardinality of $\{v_2,...v_m\}$ when we execlude $v$ out of it. 



## e)

We know that $det(H_v)$ equals to the product of the eigenvalues of $H_v$, thus combine with d, we have:
$$
det(H_v) = -1 \times 1 = -1
$$


# Question 2

## a)

Given $v = \left [
\matrix {0  \\  \tilde v}
\right ]$, then we have $v^Tv = \tilde v^T\tilde v$, $vv^T = \left [
\matrix {0_{k\times k} & 0_{k\times n} \\ 0_{n\times k} & \tilde v\tilde v^T }
\right ]$ by the nature of matrix multiplication.
$$
H_v = I_{n+k} - 2\frac {vv^T}{v^Tv} = I_{n+k} - 2\frac {vv^T}{\tilde v^T\tilde v}
$$
since we have $vv^T = \left [
\matrix {0_{k\times k} & 0_{k\times n} \\ 0_{n\times k} & \tilde v\tilde v^T }
\right ]$ being a square matrix with dimension $n+k$ by $n+k$, we can rewrite the above equation to:
$$
H_v =  I_{n+k} - 2\frac {vv^T}{\tilde v^T\tilde v} = \left [
\matrix {I_{k\times k} & 0_{k\times n} \\ 0_{n\times k} & I_{n \times n}-2 \frac {\tilde v\tilde v^T}{{\tilde v^T\tilde v}} }
\right ] =  \left [
\matrix {I_{k\times k} & 0_{k\times n} \\ 0_{n\times k} & H_{\tilde v} }
\right ] 
$$




## b)?

$v = \left [
\matrix {1  \\  1}
\right ] \in \R^2, H_v = I - \frac{2vv^T}{v^Tv} = \left [
\matrix {1 & 0 \\ 0 & 1}
\right ] - \left [
\matrix {1 & 1 \\ 1 & 1}
\right ] =  \left [
\matrix {0 & -1 \\ -1 & 0}
\right ]$

The space that the Householder matrix $H_v$ reflect across is $span(v^{\perp})$. Say we have $w =  \begin{bmatrix}
w_0 \\
 w_1 \\
\end{bmatrix} \perp v$

then $v^Tw = w_0 + w_1 = 0, \implies w_0=-w_1 \implies w =  \begin{bmatrix} -w_1\\ w_1\\
\end{bmatrix}$. Thus $H_v$ reflect across $span( \begin{bmatrix}
-1 \\ 1 \\ \end{bmatrix})$

Visually, it is drew as the red dotted line below.

<img src="/Users/ruoyu/Library/Application Support/typora-user-images/image-20230303232732942.png" alt="image-20230303232732942" style="zoom:33%;" />
$$
H_v u =\left [\matrix {0 & -1 \\ -1 & 0} \right ] \left [\matrix {1 \\ 2 } \right ] 
=\left [\matrix {-2 \\ -1 } \right ]
$$


# Q3

## a)

$$
\left [
\matrix {
5.1 \\
 5.79 \\
 6.53 \\
 7.45 \\
 8.44 \\
}
\right ]
= \left [
\matrix {1 & 1 \\ 1 & 1.25  \\ 1 & 1.5  \\ 1 & 1.75 \\ 1 & 2 }
\right ]

\left [
\matrix {
\alpha_0 \\
\alpha_1 \\

}
\right ]

\\
\Updownarrow
\\y =A \alpha
$$

The normal equations will be:


$$
A^T(y-A\alpha) = 0 \\ 
A^Ty -A^TA\alpha = 0\\
\alpha = (A^TA)^{-1}A^Ty \\

\begin{aligned}
\alpha& = \left (\left [
\matrix {1 & 1 & 1 & 1& 1  \\ 1 & 1.25 & 1.5 & 1.75 & 2 }
\right ]\left [
\matrix {1 & 1 \\ 1 & 1.25  \\ 1 & 1.5  \\ 1 & 1.75 \\ 1 & 2 }
\right ] \right )^{-1} \left [
\matrix {1 & 1 & 1 & 1& 1  \\ 1 & 1.25 & 1.5 & 1.75 & 2 }
\right ]\left [
\matrix {
5.1 \\
 5.79 \\
 6.53 \\
 7.45 \\
 8.44 \\
}
\right ]

\\ &= \left [
\matrix {
 1.658 \\
 3.336 \\
}
\right ]
\end{aligned}
$$
thus $y \approx 1.658  + 3.336x$







## b)

$$
A^T(y-A\alpha) = 0
\\ A^Ty -A^TA\alpha = 0
\\
\begin{aligned}
\alpha &= (A^TA)^{-1}A^Ty \\
				& = \left (\left [
\matrix {1 & 1 & 1 & 1& 1  \\1 & 1.25 & 1.5 & 1.75 & 2  \\ 1 & 1.5625 & 2.25 & 3.0625 & 4 }
\right ]\left [
\matrix {1 & 1 & 1  \\1 & 1.25 & 1.5625  \\1 & 1.5 & 2.25  \\1 & 1.75 & 3.0625  \\ 1 &2 & 4 }
\right ] \right )^{-1} \left [
\matrix {1 & 1 & 1 & 1& 1  \\1 & 1.25 & 1.5 & 1.75 & 2  \\ 1 & 1.5625 & 2.25 & 3.0625 & 4 }
\right ]\left [
\matrix {
5.1 \\
 5.79 \\
 6.53 \\
 7.45 \\
 8.44 \\
}
\right ]\\
 & = 
 \begin{bmatrix}
3.5523 \\
 0.6617 \\
 0.8914 \\
\end{bmatrix}
\end{aligned}
$$

thus $y \approx 3.5523  + 0.6617x + 0.8914x^2$





# Question 4

## a)

$$
Q^T(y-A\alpha) = 0, A= QR \\
Q^Ty - Q^TQR\alpha = 0\\
Q^Ty = R\alpha
$$

From matlab function call: `[Q,R] = qr(A, 0)` with $A =  \begin{bmatrix} 1 & 1 & 1  \\1 & 1.25 & 1.5625  \\1 & 1.5 & 2.25  \\1 & 1.75 & 3.0625  \\ 1 &2 & 4\end{bmatrix}$

we obtain:
$$
Q =  \begin{bmatrix}
0.4472&   -0.6325&    0.5345 \\
0.4472&   -0.3162&   -0.2673\\
0.4472&         0&   -0.5345\\
0.4472&    0.3162&   -0.2673\\
0.4472&    0.6325&    0.5345\\
\end{bmatrix}, 

Q^T =  \begin{bmatrix}
  0.4472&    0.4472&    0.4472&    0.4472&    0.4472\\
   -0.6325&   -0.3162&         0&    0.3162&    0.6325\\
    0.5345&   -0.2673&   -0.5345&   -0.2673&    0.5345
\end{bmatrix}
\\

R =  \begin{bmatrix}
 2.2361&     3.3541  &   5.3107\\
         0&     0.7906&     2.3717\\
         0 &         0&     0.2339
\end{bmatrix}, \alpha =  \begin{bmatrix}
\alpha_0 \\
\alpha_1 \\
\alpha_2\\
\end{bmatrix}
$$

$$
\begin{aligned}
Q^Ty &=
\begin{bmatrix}
  0.4472&    0.4472&    0.4472&    0.4472&    0.4472\\
   -0.6325&   -0.3162&         0&    0.3162&    0.6325\\
    0.5345&   -0.2673&   -0.5345&   -0.2673&    0.5345
\end{bmatrix}

\begin{bmatrix}
5.1 \\
 5.79 \\
 6.53 \\
 7.45 \\
 8.44 \\
\end{bmatrix}\\
&= 
 \begin{bmatrix}
14.8967 \\
2.6373 \\
 0.2085 \\
\end{bmatrix}
\end{aligned}
$$

Thus we have:
$$
\begin{aligned}
\left \{ 
\matrix{

0.2339\alpha_2 = 0.2085 \\
2.3717\alpha_2 + 0.7906\alpha_1 = 2.6373 \\
5.3107\alpha_2 + 3.3541\alpha_1 + 2.2361\alpha_0= 14.8967
}
\right.
\end{aligned}
\\ 
\implies 
\begin{aligned}
\left \{ 
\matrix{

\alpha_2 = 0.8914 \\
\alpha_1 =0.6617\\
\alpha_0= 3.5523
}
\right.
\end{aligned}
$$
$y \approx 3.5523 + 0.6617 x + 0.8914x^2$



## b)

```matlab
function alpha = solveLS(y, A)
[Q,R] = qr(A, 0);
n = size(R,1);
qTy = Q' * y;
alpha = zeros(n,1);
alpha(n) = qTy(n)/R(n,n);
for i = n-1:-1:1
    alpha(i) = (qTy(i) - R(i,i+1:n)*alpha(i+1:n))/R(i,i);
end

```

![image-20230305202016047](/Users/ruoyu/Library/Application Support/typora-user-images/image-20230305202016047.png)





# Question 5

I first assume that the polynomial relationship between the execution time $y$ of running $inv(A)$ where $A$ is a $n \times n $ matrix is as follow:
$$
y = \alpha_0  + \alpha_1 n + \alpha_2n^2
$$
Considering the computation resources limitations, I ran 10 experiments of executing $inv(A)$ and kept track of the time of each run. $A$ is randomly initialized for each run of experiment, and the size of it is increasing as experiments go. Here is my whole experiement code:

```matlab
for i=1:10
	A = randn(i * 3000, i * 3000);
	tic
	inv(A);
	toc
end
```

I obtain:
$$
\begin{bmatrix}
0.614477 \\
 4.100077 \\
 12.074519 \\
 30.684360 \\
59.414220 \\
103.630225 \\
 161.962510\\
 242.159408 \\
353.229978 \\
533.150282 
\end{bmatrix}
= 
 \begin{bmatrix}
1 & 3000 & 9000000 \\ 
1 & 6000 & 36000000 \\ 
1 & 9000 & 81000000 \\ 
1 & 12000 & 144000000 \\ 
1 & 15000 & 225000000 \\ 
1 & 18000 & 324000000 \\ 
1 & 21000 & 441000000 \\ 
1 & 24000 & 576000000 \\ 
1 & 27000 & 729000000 \\ 
1 & 30000 & 900000000 \\ 
\end{bmatrix}
 \begin{bmatrix}
\alpha_0 \\
\alpha_1 \\
\alpha_2 \\
\end{bmatrix}
$$
Where:
$$
y =\begin{bmatrix}
0.614477 \\
 4.100077 \\
 12.074519 \\
 30.684360 \\
59.414220 \\
103.630225 \\
 161.962510\\
 242.159408 \\
353.229978 \\
533.150282 \\
\end{bmatrix}, 

A=   \begin{bmatrix}
1 & 3000 & 9000000 \\ 
1 & 6000 & 36000000 \\ 
1 & 9000 & 81000000 \\ 
1 & 12000 & 144000000 \\ 
1 & 15000 & 225000000 \\ 
1 & 18000 & 324000000 \\ 
1 & 21000 & 441000000 \\ 
1 & 24000 & 576000000 \\ 
1 & 27000 & 729000000 \\ 
1 & 30000 & 900000000 \\ 
\end{bmatrix}
$$


Using the method I defiend above: `solveLS(y, A)`, I solved for $\alpha$, which is: 
$$
\alpha =  \begin{bmatrix}
 58.6698\\
   -0.0160\\
    0.0000\\
\end{bmatrix}
$$
But due to rounding errors, it’s not a satisfying solution. 

I realized that my assumption should be adjusted since the size of the matrix $A$ is $n \times n$, thus it makes more sense to have only the square relationship:
$$
y \approx \alpha_0 n^2
$$

$$
y =\begin{bmatrix}
0.614477 \\
 4.100077 \\
 12.074519 \\
 30.684360 \\
59.414220 \\
103.630225 \\
 161.962510\\
 242.159408 \\
353.229978 \\
533.150282 
\end{bmatrix}, 

A=   \begin{bmatrix}
 9000000 \\ 
 36000000 \\ 
 81000000 \\ 
 144000000 \\ 
 225000000 \\ 
 324000000 \\ 
 441000000 \\ 
 576000000 \\ 
 729000000 \\ 
 900000000 \\ 
\end{bmatrix}
$$

solve for $\alpha$ again, I got:
$$
\alpha = [4.8770 \times 10^{-7}]
$$
Which is way better than the previous estimation, as $y \approx 4.8770 \times 10^{-7}n^2$





