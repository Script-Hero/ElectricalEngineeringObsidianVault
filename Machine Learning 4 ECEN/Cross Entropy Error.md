[[In-Sample Error]] metric for [[Logistic Regression]]
$$
E_\text{in}(w)=\frac 1 N \sum\limits_{n=1}^N\ln(1+e^{-y_n\cdot w^Tx})
$$
- Is based on an intuitive probabilistic interpretation of $h$
- Mathematically 'easy' to minimize 