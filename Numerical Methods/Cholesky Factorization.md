Matrix decomposition for *symmetric, [[Positive Definite]] matrices*. $A$ is decomposed to its *lower triangular matrix $L$* and its transpose $L^T$ such that
$$
A = LL^T
$$
Where
- $L$ is the lower triangular matrix with positive diagonal entries
- $L^T$ is the transpose of $L$ 
# Methodology
1. Ensure $A$ is symmetric ($A=A^T$) and [[Positive Definite]]
2. Decompose $A$ into $L$ and $L^T$ by going row by row
	1. For diagonal entries $L_{ii} = \sqrt{A_{ii}-\sum\limits_{k=1}^{i-1}L_{ik}^2}$
	2. For off-diagonal entries $L_{ij}=\frac1{L_{jj}}(A_{ij}-\sum\limits_{k=1}^{i-1}L_{ik}L_{jk}),\space(j>i)$
3. Faster than [[LU-Factorization]]

