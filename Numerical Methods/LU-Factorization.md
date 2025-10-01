AKA LU-Decomposition. Given a **square matrix** $A$, reduce it into lower triangular matrix $L$ and upper triangular matrix $U$, such that $A=LU$
# Methodology

1. Initialize $U=I$, the identity matrix 
2. Reduce $A$ to RREF like normal. This gives you $U$ 
3. While finding $U$, Record the multipliers used in the elimination process into lower triangular matrix $L$ 
4. You can then use $L$ and $U$ to solve systems like $AX=B$:
	1. Solve $LY=B$ using *forward substitution*
		1. This gets you $Y$, which are intermediate values that guess us to our solution
	2. Solve $UX=Y$ using *back substitution*
		1. Using the $Y$ we just solved for, we find what we really care about, $X$ :)
## $A=LDU'$ factorization
- Where $D$ is a diagonal matrix containing the diagonal elements of $U$
- $U'$ is dividing each row of $U$ by the corresponding diagonal element in $D$ so that $U'$ has $1$s on the diagonal

