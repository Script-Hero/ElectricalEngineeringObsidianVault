---
~
---
## Systems of Differential Equations


### Ignore this stuff
	Transforms:
	- If a normal matrix $\mathbf{A}$ has items defined at row $i$ and column $j$ as $a_{ij}$
	
	$\mathbf{A}=\begin{pmatrix}3&2-i\\4+3i&-5+2i\end{pmatrix}$
	
	Then:
	- $\mathbf{A^{T}}=(a_{ji})$
	- $\bar{\mathbf{A}}=\begin{pmatrix}3&2+i\\4-3i&-5-2i\end{pmatrix}$  *Complex conjugate*
	- $\mathbf{A^{*}}=\mathbf{\bar{A}^{T}}$


## Chapter 5

### 5.2
For the equation $(x^{2}+1)y''+xy' -y=0$
- Determine the lower bound for the radius of convergence about $x_{0} =0$
	- $P(x)=x^{2}+1$ --> $x_{0}=0$ is not a [[Electronics/Electronics/Root|Root]] so it is an *ordinary point* meaning we can have a [[Power]] series solution
	- Radius of convergence LOWER BOUND is distance between $x_{0}$ and the nearest [[Electronics/Electronics/Root|Root]] of $P(x)$ to $x_{0}$
	- Roots are $x=\pm i$ --> Lower bound of radius of convergence is at least 1 ($R\geq1$) 
- Seek the [[Power]] series solution about $x_{0}=0$ and find recurrence relation
	- $y=\sum\limits_{n=0}^{\infty}a_{n}x^{n}$ --> $y'=\sum\limits_{n=1}^{\infty}na_{n}x^{n-1}$ --> $y''=\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n-2}$ 
	- Then we can replace every instance of $y$,$y'$,$y''$ with the [[Power]] series we found
	- this gives us $x^{2}\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n-2}+\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n-2}+x\cdot\sum\limits_{n=1}^{\infty}na_{n}x^{n-1}-\sum\limits_{n=0}^{\infty}a_{n}x^{n}=0$
	- Then we simplify $\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n}+y''+\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n-2}+\sum\limits_{n=1}^{\infty}na_{n}x^{n}-\sum\limits_{n=0}^{\infty}a_{n}x^{n}=0$
	- We want everything to have $x^{n}$ so we can combine our [[Power]] series. If they don't, we have to do an *index shift* 
	- This looks like $\sum\limits_{n=2}^{\infty}n(n-1)a_{n}x^{n}+y''+\sum\limits_{n=0}^{\infty}(n+2)(n+1)a_{n+2}x^{n}+\sum\limits_{n=1}^{\infty}na_{n}x^{n}-\sum\limits_{n=0}^{\infty}a_{n}x^{n}=0$
		- Basically for the [[Power]] series that had $x^{n-2}$ we shifted the starting index down 2, set all the $n_{old}=n+2$ to accommodate
	- Now we want to make it so that everything starts at the same index. This time around we can just say the starting index is $n=0$ for all of them, because you're not adding anything when you set those terms to that
		- For example on the first one, when $n=0$ you add $0$ and when $n=1$ you add $0$ so it really doesn't matter if we just start at $n=0$ even though it says $n=2$
	- Now we have $\sum\limits_{n=0}^{\infty}n(n-1)a_{n}x^{n}+y''+\sum\limits_{n=0}^{\infty}(n+2)(n+1)a_{n+2}x^{n}+\sum\limits_{n=0}^{\infty}na_{n}x^{n}-\sum\limits_{n=0}^{\infty}a_{n}x^{n}=0$
	- Finally we just combine everything: $n(n-1)a_{n}+(n+2)(n+1)a_{n+2}\cdot x^{n}+(n-1)a_{n}=0$ for all $n=0,1,2,...$ 
	- We finally get the **recurrence relationship** by combining terms and getting $(n+2)a_{n+2}+(n-1)a_{n}=0$
- Find the general term of each solution $y_{1}$ and $y_2$
	- $a_{0}=y(0)$
	- $a_{1}=y'(0)$
	- $a_{2}=\frac{y''(0)}{2!}$
	- We use the **recurrence relationship** to find each value: that is $a_{n+2}=-\frac{(n-1)a_{n}}{n+2}$
	- Using this relationship, we find patterns. In this case, we find there is a different pattern for even and odd $a_{n}$. We find $a_{2k+1}=0$ for all $k>1$ and that $a_{2k}=(-1)^{k-1}\frac{(2k-3)!!}{(2k)!!}a_{0}$ for all $k>1$.
	- From here we find $y=a_{0}(1+\sum\limits_{k=1}^{\infty}(-1)^{k}\frac{(2k-3)!!}{(2k)!!}x^{2k})+a_{1}\cdot x$
		- The coefficient of $a_{0}$ is $y_{1}$ and the coefficient of $a_{1}$ is $y_{2}$ 
- Find the first four terms in each of the solutions and that the Wronskian is not equal to $0$
	- For infinite series you'll find that the matrix is always just the identity matrix which the determinant of is always $1$


### 5.3
For the following equation determine $\phi''(x_{0})$ and $\phi'''(x_{0})$ for the given point $x_{0}$ if $y=\phi(x)$ for $y''+x^{2}y' + (\sin(x))y=0$
- Given initial values $y(0)=a_{0},y'(0)=a_{1}$

To solve:
- first assume $y=\phi(x)$ and thus $\phi(0)=a_{0}$ and $\phi'(0)=a_{1}$
- Now we have $\phi''(x)+x^{2}\phi'(x)+(\sin(x))\phi(x)=0$
- Plug in $x=0$ we get $\phi''(0)=0$ 
- Then we differentiate and get $\phi'''(x)+2x\phi'(x)+x^{2}\phi''(x)+\cos(x)\phi(x)+\sin(x)\phi'(x)=0$
- Plug in $x=0$ again and get $\phi'''(0)=-a_{0}$
- Final answer: $\phi(x)=\sum\frac{\phi^{(n)}(0)}{n!}x^{n}=a_{0}+a_{1}(x)+\frac{0}{2!}x^{2}+\frac{-a_{0}}{3!}x^{3}+...=a_{0}(1-\frac{x^{3}}{6}+...)+a_{1}(x+...)$
- The coefficient attached to $a_{0}$ is our $y_{1}$ and the coefficient attached to $a_{1}$ is $y_{2}$
- 