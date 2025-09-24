Decomposes a matrix $A$ into $A=QR$ where
- $Q$ is an *orthogonal* matrix meaning $Q^TQ=I$ (columns of $Q$ are orthonormal)
- $R$ is an *upper triangular matrix*
# Methodology
1. **Gram-Schmidt Process**
	1. Start with the first column of $A$ as $q_1=\frac{a_1}{||a_1||}$ where $a_1$ is the first column of $A$ 
	2. Orthogonalize subsequent columns
		1. For the $j$th column of $A$, subtract the projections of $a_j$ onto all previous $q_i$ such that $v_j=a_j-\sum\limits_{i=1}^{j-1}(q_i^Ta_j)q_i$
		2. Normalize $v_j$ to get $q_j=\frac{v_j}{||v_j||}$
	3. Form $Q$ by stacking $q_j$ columns
	4. $R$, the upper triangular matrix, is formed with $R_{ij} = \begin{cases} q_i^Ta_j,& i\leq j \\ 0,&i>j \end{cases}$# Least-Squares
After solving for $Q$ and $R$ matrices, we can solve least-squares regression with $Rx=Q^Tb$
