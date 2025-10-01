#Chapter11 

A [[Joint Probability Mass Function]] for [[Multiple Continuous Random Variables]].


Given 2 [[Continuous Random Variable]]s $X$ and $Y$, their *joint [[Random Signals and Systems/Probability Density Function|Probability Density Function]]* $f_{X,Y}(\cdot,\cdot)$ is 
$$
P((X,Y)\in S)=\int_{x\in S}\int_{y\in S} f_{X,Y}(x,y)dxdyu
$$

### Properties
- $\int\limits_{x=-\infty}^{+\infty}\int\limits_{y=-\infty}^{+\infty}f_{(X,Y)}(x,y)dxdy=1$
	- adding all the probabilities for all combinations of $x,y\in S$.

### [[Expected Value]]
For some function $g$ of jointly continuous random variables $X$ and $Y$
$E[g(X,Y)] = \int\limits_{x=-\infty}^{+\infty}\int\limits_{y=-\infty}^{+\infty}g(x,y)f_{(X,Y)}(x,y)dxdy$
- Maintains [[Linearity of Expectation]] with $E[aX + bY]=aE[X]+bE[Y]$
	- $a$ and $b$ are constants 

### If $X$ and $Y$ are [[Independent Random Variable]]
then $F_{X,Y}(x,y)=F_X(x)F_Y(y)$ 











