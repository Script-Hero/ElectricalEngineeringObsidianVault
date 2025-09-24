#Chapter7 

For [[Multiple Random Variables]] $X$ and $Y$, consider a third random variable $U=g(X,Y)$ where $g(\cdot,\cdot)$ is a real-valued function.

- [[Probability Mass Function]] of $U$ is $p_{U}(u)=\sum\limits_{\{(x,y)|(g(x,y)=u\}}p_{X, Y}(x,y)$
- [[Expected Value]] of $U$ is $E[U]=E[g(X,Y)]=\sum\limits_{x}\sum\limits_{y}g(x,y)p_{X,Y}(x,y)$
- [[Affine Function]] of multiple variables where $U = X + Y + b$, ($b$ is a constant), $E[U]=E[X+Y+b]=E[X]+E[Y]+b$
	- if $U=\sum\limits_{i=1}^n a_{i}X_{i}$ then the [[Expected Value]] is $E[U]=\sum\limits_{i=1}^n a_{i}\mu_{i}$ 
		- Where $\mu_{i}=E[X_{i}]$

