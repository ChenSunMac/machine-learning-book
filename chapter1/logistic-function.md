## Logistic function


$$
\begin{equation}
f(x) = \frac{1}{1 + e^{-x}}
\end{equation}
$$

Sigmoid function's derivative:

$$
\begin{eqnarray}
f'(x) &=& (\frac{1}{1 + e^{-x}})' \\
    &=& \frac{e^{-x}}{(1 + e^{-x})^2} \\
    &=& \frac{1}{1+e^{-x}} (1 - \frac{1}{1+e^{-x}}) \\
    &=& f(x)(1 - f(x))
\end{eqnarray}
$$

