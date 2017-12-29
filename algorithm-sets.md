## Gradient Descent Method

Gradient descent is a first-order iterative optimization algorithm for finding the minimum of a function. To find a local minimum of a function using gradient descent, one takes steps proportional to the negative of the gradient (or of the approximate gradient) of the function at the current point.

目标：找函数极小值

$$
\begin{equation}
J(\theta) = \frac{1}{2} \sum_{i = 1}^{m} ( h_\theta(x^{(i)}) - y^{(i)}  )^2
\end{equation}
$$

1. 初始化参数$$\theta$$
2. 沿着负梯度方向迭代，更新后的参数$$\theta'$$ 使得$$J(\theta) $$更小:

$$
\begin{equation}
\theta' = \theta - \alpha \frac{\partial J(\theta)}{\partial \theta}
\end{equation}
$$

其中$$\alpha$$是步长，也是learning rate, 梯度方向为:

$$
\begin{equation}
\frac{\partial J(\theta)}{\partial \theta_j} = (h_\theta(x) - y)x_j
\end{equation}
$$

---
#### 批量梯度下降:

Repeat Until Convergence{
    $$
    \begin{equation}
    \theta_j' = \theta_j + \alpha \sum_{i=1}^{m} ( - h_\theta(x^{(i)}) + y^{(i)})x^{(i)}_j
    \end{equation}
    $$
}
