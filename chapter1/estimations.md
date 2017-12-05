## Central Limit Theorem

设随机变量 $$X_1, X_2, ...$$ 互相独立，服从同一分布，并且具有相同的期望 $$\mu$$ 和 方差 $$\sigma^2$$, 那么随机变量Y: 



$$
\begin{equation}
Y_n = \frac{1}{\sqrt{n}\sigma}(\sum_{i = 1}^{n}X_i - n\mu)
\end{equation}
$$

的分布收敛到标准正态分布。


实际生活中，很多随机现象可以看做许多因素的独立影响的综合反映，往往近似服从正态分布


## Maximum likelihood estimation (MLE)

最大似然估计, a method of **estimating the parameters** of a statistical model **given observations**, by finding the parameter values that **maximize the likelihood** of making the observations given the parameters.

简单来说，就是从采样数据$$[X_1, ..., X_n]$$，以及估计的概率分布模型D,($$f_D(\theta_1,..., \theta_k)$$)，来求概率分布的参数 $$\theta_1,..., \theta_k$$