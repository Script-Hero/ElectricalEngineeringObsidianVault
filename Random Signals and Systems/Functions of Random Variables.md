#Chapter5 

Consider the [[Random Variable]] $X$ and the function $g(\cdot)$, $Y=g(X)$ is also a random variable 
- The [[Probability Mass Function]] of $Y$ can be calculated with the PMF of $X$, $p_x$ as $p_{Y}(y)=\sum_{\{x|g(x)=y\}}p_{X}(x)$
- Meaning that we are summing the probability $p_{X}(x)$ for all values of $x$ that when you apply the function $g(x)$ , the output is $y$. That's the $\{x|g(x)=y\}$ part of the summation.

####  Example:
- if $p_{X}(x)=\begin{cases}\frac{1}{9}&\mbox{if } x \mbox{ is an integer in the range } [-4,4] \\ 0 & \mbox{otherwise.}\end{cases}$ 
- and $Y=|X|$
- Compute the PMF of $Y$:
	- $p_Y(0)=p_{X}(0)=\frac{1}{9}$
	- $p_{Y}(1)=p_{X}(1)+p_{X}(-1)=\frac{1}{9}+\frac{1}{9}=\frac{2}{9}$
- The PMF of $Y$ is $p_{Y}=\begin{cases}\frac{2}{9}&\mbox{if }y\in\{1,2,3,4\}\\ \frac{1}{9}&\mbox{if } y=0\\0&\mbox{otherwise}\end{cases}$


