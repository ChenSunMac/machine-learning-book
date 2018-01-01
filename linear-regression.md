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


---

## 用最大似然估计解释最小二乘法\(cost function\)

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
\begin{equation}
\log(L(\theta)) = m\log(\frac{1}{\sqrt{2\pi\sigma^2}}) - \frac{1}{\sigma^2}\frac{1}{2} \sum_{i = 1}^{m} (y^{(i)} - \theta^Tx^{(i)})^2
\end{equation}
$$


所以我们希望cost function尽量的小, 这也是和我们的 quadratic cost function 一致的:


$$
\begin{equation}
J(\theta) = \frac{1}{2} \sum_{i = 1}^{m} (y^{(i)} - \theta^Tx^{(i)})^2
\end{equation}
$$


---

# 求解 $$\theta$$

M个N维样本组成矩阵 $$X_{M\times N}$$, 每一行对应一个样本\(Measurement\), 每一列对应一个维度\(regressors\), 通常还会有额外的一列常数项，全为1.

目标函数:


$$
\begin{equation}
J(\theta) = \frac{1}{2} (X\theta - y)^T (X\theta - y)
\end{equation}
$$


目标函数的梯度为：


$$
\begin{eqnarray}
\nabla_{\theta} J(\theta) &=& \nabla_{\theta}  (\frac{1}{2} (X\theta - y)^T (X\theta - y))\\
            &=& \nabla_{\theta} (\frac{1}{2} (\theta^TX^TX\theta - \theta^TX^Ty - y^TX\theta + y^Ty )  )        \\
            &=& \frac{1}{2}(2 X^TX\theta - X^Ty - (y^TX)^T) = X^TX\theta - X^Ty            
\end{eqnarray}
$$


根据最小值求驻点，我们得到:


$$
\begin{eqnarray}
\theta = (X^TX) ^{-1}X^Ty         
\end{eqnarray}
$$


为了防止$$(X^TX)$$不可逆 或者 过度拟合, 我们增加扰动项 \($$\lambda$$\)，


$$
\begin{eqnarray}
\theta = (X^TX + \lambda I) ^{-1}X^Ty         
\end{eqnarray}
$$


---

在增加了扰动之后，我们的目标函数/平方和损失可以写成如下形式：

* L2 norm: 


$$
\begin{equation}
J(\theta) = \frac{1}{2} \sum_{i = 1}^{m} (y^{(i)} - \theta^Tx^{(i)})^2 + \lambda\sum^n_{j=1}\theta^2_j
\end{equation}
$$


* L1 norm:


$$
\begin{equation}
J(\theta) = \frac{1}{2} \sum_{i = 1}^{m} (y^{(i)} - \theta^Tx^{(i)})^2 + \lambda\sum^n_{j=1}|\theta_j|
\end{equation}
$$


### 如何处理L1-norm的梯度

难度在于如何处理$$|\theta_j|$$这个绝对值的梯度。

近似：


$$
\begin{equation}
|x| \approx \frac{1}{\alpha} \log (1 + e^{-\alpha x} + 1 + e^{\alpha x})
\end{equation}
$$


其梯度可以近似为:


$$
\begin{equation}
\nabla|x| \approx \frac{1}{1 + e^{-\alpha x}} - \frac{1}{1 + e^{\alpha x}}
\end{equation}
$$


二阶导:


$$
\begin{equation}
\nabla^2 |x| \approx \frac{2\alpha e^{\alpha x}}{(1 + e^{\alpha x})^2}
\end{equation}
$$


# Logistic Regression

这里其实和linear Regression是一类问题，只是我们的模型 $$h_\theta(x)$$ 不再是线性模型，而是Logistic/Sigmoid Function:


$$
\begin{equation}
h_\theta(x) = g(\theta^t x) = \frac{1}{1 + e^{-\theta^T x}}
\end{equation}
$$


### SoftMax Function

Softmax function, or normalized exponential function is a generalization of the logistic function that "squashes" a K-dimensional vector $$z$$ of arbitrary real values to a K-dimensional vector $$\sigma(z)$$ of real values in the range \[0, 1\] that add up to 1.

那这个softmax具体怎么解释呢，max的话是直接取最大值，但是这样会导致我们一直取最大，其他相对较小的值会"饥饿"，那么我们希望分值大的那些元素经常能取到，其他的元素偶尔也能够出现，而不至于全部都被滤掉，所以我们用softmax：

$$
\begin{equation}
\sigma : R^k \rightarrow [0, 1]^k
\end{equation}
$$

$$
\begin{equation}
\sigma (z)_j = \frac{e^{z_j}}{\sum^{K}_{k=1} e^{z_k}}, ~~j = 1,..., K
\end{equation}
$$

其实从形式上看就是一个对输入向量的概率的归一化. 

那么如果我们需要做K-分类的话，第k类的参数为$$\theta_k$$，从而组成一个二维的矩阵 $$\theta_{K\times n}$$

那么样本向量 x 属于第k个分类的概率可以写作：

$$
\begin{equation}
p(c = k | x; \theta) = \frac{e^{\theta^T_k x}}{\sum^{K}_{k=1} e^{z_k}}
\end{equation}
$$






