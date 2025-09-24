[[Linear Regression]] can learn *any* real valued target function.
- For example $y_n=\pm1$
- Use linear regression to get $w$ with $w^Tx_n\approx y_n=\pm1$
- Then $\text{sign}(w^Tx_n)$ will likely agree with $y_n=\pm1$
- These can be good initial weights for classification
