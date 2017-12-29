## Gradient Descent Method

Gradient descent is a first-order iterative optimization algorithm for finding the minimum of a function. To find a local minimum of a function using gradient descent, one takes steps proportional to the negative of the gradient (or of the approximate gradient) of the function at the current point.

目标：找函数极小值

$$
\begin{equation}
J(\theta) = \frac{1}{2} \sum_{i = 1}^{m} ( h_\theta(x^{(i)}) - y^{(i)}  )^2
\end{equation}
$$

1. 