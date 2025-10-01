Algorithm for polynomial interpolation for:
- generating a unique polynomial 
- of degree **less than or equal to $n$** (degree $\leq n$) 
- given $n+1$ interpolating points. 
- The interpolating polynomial goes through each of the $n+1$ points. 

# Neville Methodology
1. Given $n+1$ datapoints of $(x_i, y_i)$ where no 2 $x_i$s are the same
2. Let $p_{ij}$ designate the polynomial of degree $j-i$, which goes through the points $(x_k,y_k)$ for $k=i,i+1,\dots,j$
3. $p_{ij}$ satisfies the recurrence relation:
	1. $p_{i,i}=y_i$ for $0\leq i \leq n$
	2. $p_{i,j}=\frac{(x-x_i)p_{i+1,j}(x)-(x-x_j)p_{i,j-1}(x)}{x_j-x_i}$ for $0\leq i < j \leq n$
4. This recurrence can calculate $p_{0,n}(x)$ which is the **value being sought**

# Triangle Tableau Approach
The recurrence relation for $n=4$, which yields $p_{0,4}(x)$ which is the value of the polynomial going through the $n+1$ datapoints $(x_i,y_i)$ at the point $x$.

![[neville_tableau.png]]
