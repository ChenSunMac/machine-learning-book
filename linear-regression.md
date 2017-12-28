# Linear Regression

Single Parameter:

$$
\begin{equation}
y  = ax +b
\end{equation}
$$

Multiple Parameters:

$$
\begin{equation}
y  = \sum \theta_i x_i 
\end{equation}
$$

## 用最大似然估计解释最小二乘法(cost function)
假如我们建立了 Linear Regression 模型 $$\theta^T$$, 那么对应于第i组实际输入和输出，我们有

$$
\begin{equation}
y^{(i)}  = \theta^T x^{(i)} + \epsilon^{(i)} 
\end{equation}
$$

其中， $$\epsilon^{(i)} $$ 是误差，在很多随机现象中，该误差可以看作是独立同分布，也就是高斯分布，即

$$
\begin{equation}
p(\epsilon^{(i)}) =\frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(\epsilon^{(i)})^2}{2\sigma^2}}
\end{equation}
$$

那么把$$y^{(i)}$$ 和 $$x^{(i)}$$带入就有:

$$
\begin{equation}
p(y^{(i)} | x^{(i)}; ~\theta) = \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(y^{(i)} - \theta^Tx^{(i)})^2}{2\sigma^2}}
\end{equation}
$$

那么基于Maximum Likelihood method, 那么我们有:
$$
\begin{equation}
L(\theta) = \prod_{i = 1}^m \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(y^{(i)} - \theta^Tx^{(i)})^2}{2\sigma^2}}
\end{equation}
$$

两边同时取对数，我们得到

$$
\log(L(\theta)) = m\log(\frac{1}{\sqrt{2\pi\sigma^2}}) - \frac{1}{\sigma^2}\frac{1}{2} \sum_{i = 1}^{m} ()
$$







