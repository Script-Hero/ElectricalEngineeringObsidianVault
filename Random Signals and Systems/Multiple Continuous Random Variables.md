#Chapter11 

[[Multiple Random Variables]] that are [[Continuous Random Variable]]s.
	
### Associated Math Objects
- [[Joint Probability Density Function]]
- [[Conditional Probability Density Function]]
- [[Joint Cumulative Distribution Function]]
### Independence
 **If $X$ and $Y$ are *independent***
	- $E[XY]=E[X]E[Y]$
	- $E[g(X)h(Y)]=E[g(X)]E[h(Y)]$ for any 2 function $g$ and $h$ 
	- the [[Variance]] $\text{Var}[aX + bY]=a^2Var[aX]+b^2Var[Y]$  
	- If $X$ and $Y$ are independent then their [[Joint Probability Density Function]] $F_{X,Y}(x,y)=F_{X}(x)F_Y(y)$

**Sum of Two Independent Continuous Random Variables**
- If $Z=X+Y$, you can find the [[Probability Density Function]]s of $Z$ in terms of the 
- $\int\int_{X+Y\leq Z}f_{X,Y}(x,y)dxdy$
- $\rightarrow \int\limits_{y=-\infty}^{\infty}f_YF_X(z-y)dy$
- $\rightarrow f_Z=\frac{d}{dz}\int_{y=-\infty}^{\infty}f_Y(y)F_X(z-y)dy$
- $\rightarrow \int_{y=-\infty}^\infty f_Y(y)f_X(z-y)dy$                       **(ANSWER)**


