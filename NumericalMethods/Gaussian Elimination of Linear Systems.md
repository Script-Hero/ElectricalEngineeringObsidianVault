Normal matrix solving from linear algebra. Given "coefficient matrix" $A$ and "solution matrix" $b$, you set up the classic $[A|b]$ style row reduction. Reduce to RREF form, creating an *upper triangular matrix*, then solve using *back substitution* (solving the lower row with only one variable and the rest zeros, then feed that solution into the row above and etc.) 

